---
title: {{title}}
date_info: ["[[<% tp.date.now("GGGG") %>]]", "[[<% tp.date.now("GGGG-[Q]Q") %>]]", "[[<% tp.date.now("GGGG-MM") %>]]"]
prev_next: ["[[<% moment(tp.file.title,'YYYY-MM').add(-1,'month').format("YYYY-MM") %>]]", "[[<% moment(tp.file.title,'YYYY-MM').add(1,'month').format("YYYY-MM") %>]]"]
created: "[[<% tp.date.now("YYYY-MM-DD") %>]]"
updated: "[[<% tp.date.now("YYYY-MM-DD") %>]]"
---

### 2025 Notes
* [[2025 Learning#{{title}}]]
* [[2025 Q & A#{{title}}]]
* [[2025 Idea#{{title}}]]

## Cards 
>[!Info]- ### Cards Created in {{title}}
>> [!Resources]- Cards/Fleeting Card
>> ``` dataview
>> TABLE WITHOUT ID 
>>  file.link as Link, created as Created, title as Title
>> FROM "Cards/Fleeting Card/2025" 
>> WHERE !endswith(file.name, "Description")
>>  AND contains(string(created), "{{title}}") and updated = created 
>> SORT number(replace(file.name, "F", "")) asc
>> ```
>
>> [!Resources]- Cards/Idea Card
>> ``` dataview
>> TABLE  WITHOUT ID 
>>  file.link as Link, created as Created, title as Title
>> FROM "Cards/Idea Card/2025"
>> WHERE !endswith(file.name, "Description")
>>  AND contains(string(created), "{{title}}") and updated = created 
>> SORT number(replace(file.name, "I", "")) asc
>> ```
>
>> [!Resources]- Cards/Source Card
>> ``` dataview
>> TABLE  WITHOUT ID 
>>  file.link as Link, created as Created, title as Title
>> FROM "Cards/Source Card/2025"
>> WHERE !endswith(file.name, "Description")
>>  AND contains(string(created), "{{title}}") and updated = created 
>> SORT number(replace(file.name, "S", "")) asc
>> ```

>[!Info]- ### Cards Updated in {{title}}
>> [!Resources]- Cards/Fleeting Card
>> ``` dataview
>> TABLE WITHOUT ID 
>>  file.link as Link, updated as Updated, title as Title
>> FROM "Cards/Fleeting Card/2025" 
>> WHERE !endswith(file.name, "Description")
>>  AND contains(string(updated), "{{title}}") and updated != created 
>> SORT number(replace(file.name, "F", "")) asc
>> ```
>
>> [!Resources]- Cards/Idea Card
>> ``` dataview
>> TABLE  WITHOUT ID 
>>  file.link as Link, updated as Updated, title as Title
>> FROM "Cards/Idea Card/2025"
>> WHERE !endswith(file.name, "Description")
>>  AND contains(string(updated), "{{title}}") and updated != created  
>> SORT number(replace(file.name, "I", "")) asc
>> ```
>
>> [!Resources]- Cards/Source Card
>> ``` dataview
>> TABLE  WITHOUT ID 
>>  file.link as Link, updated as Updated, title as Title
>> FROM "Cards/Source Card/2025"
>> WHERE !endswith(file.name, "Description")
>>  AND contains(string(updated), "{{title}}") and updated != created 
>> SORT number(replace(file.name, "S", "")) asc
>> ```

## Efforts 
>[!Info]- ### Efforts Created in {{title}}
>> [!Resources]- Efforts/Exploration
>> ``` dataview
>> TABLE WITHOUT ID 
>> file.link as Link, created as Created, title as Title
>> FROM "Efforts/Exploration/2025"
>> WHERE !endswith(file.name, "Description")
>>  AND contains(string(created), "{{title}}") and updated = created
>> SORT number(replace(file.name, "E", "")) asc
>> ```
>
>> [!Resources]- Efforts/Project
>> ``` dataview
>> TABLE WITHOUT ID 
>> file.link as Link, created as Created, title as Title
>> FROM "Efforts/Project/2025"
>> WHERE !endswith(file.name, "Description")
>>  AND contains(string(created), "{{title}}") and updated = created
>> SORT number(replace(file.name, "P", "")) asc
>> ```

>[!Info]- ### Efforts Updated in {{title}}
>> [!Resources]- Efforts/Exploration
>> ``` dataview
>> TABLE WITHOUT ID 
>> file.link as Link, updated as Updated, title as Title
>> FROM "Efforts/Exploration/2025"
>> WHERE !endswith(file.name, "Description")
>>  AND contains(string(updated), "{{title}}") and updated != created
>> SORT number(replace(file.name, "E", "")) asc
>> ```
>
>> [!Resources]- Efforts/Project
>> ``` dataview
>> TABLE WITHOUT ID 
>> file.link as Link, updated as Updated, title as Title
>> FROM "Efforts/Project/2025"
>> WHERE !endswith(file.name, "Description")
>>  AND contains(string(updated), "{{title}}") and updated != created
>> SORT number(replace(file.name, "P", "")) asc
>> ```

---

## Tags
>[!Info]- ### Tags in {{date}}
>> [!Resources]- #todo/2025/05
>> ``` dataview
>> TABLE WITHOUT ID 
>>  Letter as L, rows.file.link, rows.created as Created, rows.title as Title
>> FROM #todo/2025/05
>> FLATTEN file.tags AS tag
>> WHERE tag = "#todo/2025/05"
>> and file.name != "{{title}}"
>>GROUP BY substring(file.name, 0, 1) as Letter
>>SORT Letter asc
>> ```
>
>> [!Resources]- #eyeopener/2025/05
>> ``` dataview
>> TABLE  WITHOUT ID 
>>  Letter as L, rows.file.link, rows.created as Created, rows.title as Title
>> FROM #eyeopener/2025/05
>> FLATTEN file.tags AS tag
>> WHERE tag = "#eyeopener/2025/05"
>> and file.name != "{{title}}"
>>GROUP BY substring(file.name, 0, 1) as Letter
>>SORT Letter asc
>> ```
>
>> [!Resources]- #good/2025/05
>> ``` dataview
>> TABLE  WITHOUT ID 
>>  Letter as L, rows.file.link, rows.created as Created, rows.title as Title
>> FROM #good/2025/05
>> FLATTEN file.tags AS tag
>> WHERE tag = "#good/2025/05"
>> and file.name != "{{title}}"
>>GROUP BY substring(file.name, 0, 1) as Letter
>>SORT Letter asc
>> ```
