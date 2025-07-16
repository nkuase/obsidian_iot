---
Title: {{VALUE:year}} {{VALUE:title}}
in:
  - "[[{{VALUE:title}} Calendar]]"
created: "[[{{date}}]]"
updated: "[[{{date}}]]"
---

```dataviewjs
let keyword = "{{VALUE:title}}";
let year = "{{VALUE:year}}";
let path = `"Calendar/{{VALUE:year}}/Daily"`; 

const {TopicSearch} = await cJS()

TopicSearch.topicSearch1(dv, path, keyword, year);     
TopicSearch.topicSearch2(dv, path, keyword, year);  
```
