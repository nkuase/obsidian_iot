---
theme: project_style
marp: true 
html: true
size: 4:3
_class: lead
paginate: true
---

# Course Project: ...
---
> Expense is a money spending and analysis tracking app.
> Using this app, we trace how much we spend on what items. 
---
> To analyze a program, we must understand these three ideas.

1. Data Structure
2. User Interface
3. Program Structure
---
> We need to understand:
1. What is the core data structure of the application?
2. What UI components are used for widgets and states?
2. What are the class's service functions, and how do they work?
3. How are these service functions used to structure the program?

---
## 1. Data structure
- When we develop applications, we need to understand the data structure. 
- The data structure is represented as a class. 
- For this program
---
### Transaction Class
- The 
```

```
---
## 2. Service functions

---

## 3. User interface
<style scoped> 
li { font-size: 0.7em; line-height: 1.5;} 
</style> 
- main.dart
- NewTransaction (new_transaction.dart)
- TransactionList (transaction_list.dart)
- ChartBar (chart_bar.dart)
- Chart (chart.dart)
---
### Program analysis tip
1. Read the source code and follow the logic.
2. Use a debugger and breakpoints to trace the code.
3. Give the source code to LLM and discuss. 
---
### main.dart

![w:240pt](p1.webp)

----
- It has the classic Flutter program structure.

```
void main() => runApp(MyApp());
class MyApp extends StatelessWidget {
  Widget build(BuildContext context) {
    return MaterialApp(home: MyHomePage(),);
  }
}
class MyHomePage extends StatefulWidget {
  _MyHomePageState createState() => _MyHomePageState();
}
class _MyHomePageState extends State<MyHomePage> { ... }
```

---
#### \_MyHomePageState widget structure
```
Widget build(BuildContext context) {
  return Scaffold(

```
---
#### Scaffold: appBar
---
#### Scaffold: body

---
#### Scaffold: FloatingActionButton

---
### APIs (service functions)
- The \_startAddNewTransaction method displays
---

### widget structure
```
TextField(...),
TextField(...),
Container(
  child: Row(
    children: <Widget>[
      Expanded(child: Text(...),
      TextButton(
        style: TextButton.styleFrom(...)
        child: Text(...),
        onPressed: _presentDatePicker,
      ),
    ],
  ),
),
ElevatedButton(
  child: Text('Add Transaction'),
  onPressed: _submitData,
),
```
---

### ChartBar(chart_bar.dart)
- ChartBar

![w:90pt](./pic/chartbar.webp)

---
#### Widget Structure
- It is a column with a text, FractionallySizedBox, and a label. 
```
return Column(
  children: <Widget>[
    Container(child: FittedBox(...)),
    Container(
      child: Stack(
        children: <Widget>[FractionallySizedBox(...),],
      ),
    ),
    Text(label),
  ],
...
```
---

---
## 4. Program structure
- This application uses MVC (Model-View-Controller) architecture.
<style scoped> 
pre code { font-size: 0.7em !important; line-height: 1.2;} 
</style> 
```
├── main.dart
├── model
│   └── transaction.dart
├── theme
│   └── main_theme.dart
└── view
    ├── chart_bar.dart
    ├── chart.dart
    ├── new_transaction.dart
    └── transaction_list.dart
```
---
### 
---
## Self-grading for HW 
<style scoped> 
li { font-size: 0.8em !important; line-height: 1.2;} 
</style> 

- You analyze the whole code once (30%).
- You analyze the whole code twice using a different method (60%).
    - Make a summary of widgets that you did not know before (what and how to use them). 
- You understand how the code works (80%).
- You can use the programming techniques in this example to make team and individual projects (100%). 


 
