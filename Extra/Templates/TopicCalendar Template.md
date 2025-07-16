---
title: {{topic_calendar}}
up: "[[{{topic}}]]"
in:
  - "[[MoC]]"
  - "[[Calendar]]"
created: "[[{{date}}]]"
updated: "[[{{date}}]]"
---

## MoC
```dataviewjs
 let pagestring =  "{{topic_calendar}}";
 const {MocGen} = await cJS() 
 MocGen.displayUp(dv,pagestring); 
 ```
```dataviewjs
 let pagestring =  "{{topic_calendar}}";
 const {MocGen} = await cJS() 
 MocGen.displayIn(dv,pagestring); 
 ```
 ```dataviewjs
 let pagestring =  "{{topic_calendar}}";
 const {MocGen} = await cJS() 
 MocGen.displayRelated(dv,pagestring); 
 ```
   ```dataviewjs
 let pagestring =  "{{topic_calendar}}";
 const {MocGen} = await cJS() 
 MocGen.displayWith(dv,pagestring); 
 ```