<%-*
const title = tp.file.title;
tp.date.title = (format, offset=0, unit="day") => {
  const momentDate = window.moment(title, "YYYY-MM-DD").add(offset, unit);
  return momentDate.format(format);
}
-%>
---
title: {{title}}
date_info: [
  "[[<% tp.date.title("GGGG") %>]]",
  "[[<% tp.date.title("GGGG-[Q]Q") %>]]",
  "[[<% tp.date.title("GGGG-MM") %>]]",
  "[[<% tp.date.title("GGGG-[W]WW") %>]]"
]
prev_next: [
  "[[<% tp.date.title("YYYY-MM-DD", -1, "day") %>]]",
  "[[<% tp.date.title("YYYY-MM-DD", 1, "day") %>]]"
]
created: "[[<% tp.date.now("YYYY-MM-DD") %>]]"
updated: "[[<% tp.date.title("YYYY-MM-DD") %>]]"
related:
  - "[[]]"
---
```dataviewjs
const {Money} = await cJS()
// this day
let res = await Money.displayCollectMoney(dv, `"Calendar/<% tp.date.title("GGGG") %>"`, (page) => page.file.name == "<% tp.file.title %>", false);
```

## Log

---

## MoC
```dataviewjs
 let datestring =  "{{title}}";
 const {MocGen} = await cJS()
 MocGen.displayDateCreated(dv,datestring);
 ```
```dataviewjs
 let datestring =  "{{title}}";
 const {MocGen} = await cJS()
 MocGen.displayDateUpdated(dv,datestring);
 ```
```dataviewjs
 let datestring =  "{{title}}";
 const {MocGen} = await cJS()
 MocGen.displayAlpha(dv,datestring);
 ```