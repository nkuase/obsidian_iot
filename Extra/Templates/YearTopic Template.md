---
Title: {{year}} {{topic}}
in:
  - "[[{{topic}} Calendar]]"
created: "[[{{date}}]]"
updated: "[[{{date}}]]"
---

```dataviewjs
let keyword = "{{topic}}";
let year = "{{year}}";
let path = `"Calendar/{{year}}/Daily"`; 

const {TopicSearch} = await cJS()

TopicSearch.topicSearch1(dv, path, keyword, year);     
TopicSearch.topicSearch2(dv, path, keyword, year);  
```