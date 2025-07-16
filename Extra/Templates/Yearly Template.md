---
title: {{title}}
quarters: ["[[{{title}}-Q1]]","[[{{title}}-Q2]]","[[{{title}}-Q3]]","[[{{title}}-Q4]]"]
months: ["[[{{title}}-01]]","[[{{title}}-02]]","[[{{title}}-03]]","[[{{title}}-04]]","[[{{title}}-05]]","[[{{title}}-06]]","[[{{title}}-07]]","[[{{title}}-08]]","[[{{title}}-09]]","[[{{title}}-10]]","[[{{title}}-11]]","[[{{title}}-12]]"]
prev_next: ["[[<% moment(tp.file.title,'YYYY').add(-1,'year').format("YYYY") %>]]", "[[<% moment(tp.file.title,'YYYY').add(1,'year').format("YYYY") %>]]"]
created: "[[<% tp.date.now("YYYY-MM-DD") %>]]"
updated: "[[<% tp.date.now("YYYY-MM-DD") %>]]"
---

> [!Resources]- {{title}}
> ``` dataview
> TABLE WITHOUT ID
>Letter as L, rows.file.link as Note,  rows.updated as Updated, rows.file.path as Path
> WHERE 
>  (endswith(file.name,  "{{title}}") or startswith(file.name, "{{title}}"))
>  and !contains(file.path, "Daily") and !contains(file.path,  "{{title}}-")
> and file.name != "{{title}}"
>GROUP BY substring(file.name, 0, 1) as Letter
>SORT Letter asc
> ```

>[!Info]- ## Cards
>> [!Resources]- Card/Fleeting Card
>> ``` dataview
>> TABLE  WITHOUT ID
>>  file.link as Link, created as Created, title as Title
>> FROM "Cards/Fleeting Card/{{title}}"
>> SORT number(replace(file.name, "F", "")) asc
>> ```
>
>> [!Resources]- Cards/Idea Card
>> ``` dataview
>> TABLE  WITHOUT ID
>>  file.link as Link, created as Created, title as Title
>> FROM "Cards/Idea Card/{{title}}"
>> SORT number(replace(file.name, "I", "")) asc
>> ```
>
>> [!Resources]- Cards/Source Card
>> ``` dataview
>> TABLE  WITHOUT ID
>>  file.link as Link, created as Created, title as Title
>> FROM "Cards/Source Card/{{title}}"
>> SORT number(replace(file.name, "I", "")) asc
>> ```

>[!Info]- ## Efforts
>> [!Resources]- Efforts/Explorations
>> ``` dataview
>> TABLE  WITHOUT ID
>>  file.link as Link, created as Created, title as Title
>> FROM "Efforts/Exploration/{{title}}"
>> SORT number(replace(file.name, "E", "")) asc
>> ```
>
>> [!Resources]- Efforts/Project
>> ``` dataview
>> TABLE  WITHOUT ID
>>  file.link as Link, created as Created, title as Title
>> FROM "Efforts/Project/{{title}}"
>> WHERE !endswith(file.name, "Description")
>> SORT number(replace(file.name, "P", "")) asc
>> ```
>

>[!Info]- ## Tags
>> [!Resources]- #todo/{{title}}
>> ``` dataview
>> TABLE WITHOUT ID 
>>  Letter as L, rows.file.link, rows.updated as Updated, rows.file.link.title as Title
>> FROM #todo/{{title}}
>> FLATTEN file.tags AS tag
>> WHERE tag = "#todo/{{title}}"
>>GROUP BY substring(file.name, 0, 1) as Letter
>>SORT Letter asc
>> ```
>
>> [!Resources]- #eyeopener/{{title}}
>> ``` dataview
>> TABLE WITHOUT ID 
>>  Letter as L, rows.file.link, rows.updated as Updated, rows.file.link.title as Title
>> FROM #eyeopener/{{title}}
>> FLATTEN file.tags AS tag
>> WHERE tag = "#eyeopener/{{title}}"
>>GROUP BY substring(file.name, 0, 1) as Letter
>>SORT Letter asc
>> ```
>
>> [!Resources]- #eyeopener/{{title}}
>> ``` dataview
>> TABLE WITHOUT ID 
>>  Letter as L, rows.file.link, rows.updated as Updated, rows.file.link.title as Title
>> FROM #good/{{title}}
>> FLATTEN file.tags AS tag
>> WHERE tag = "#good/{{title}}"
>>GROUP BY substring(file.name, 0, 1) as Letter
>>SORT Letter asc
>> ```