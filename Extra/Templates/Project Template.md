---
title: {{title}}
up:
  - "[[Project 2025]]"
in:
  - "[[Project]]"
created: "[[{{date}}]]"
updated: "[[{{date}}]]"
---
## GAS 
### SMART Check
- [ ] Specific
- [ ] Measurable
- [ ] Achievable
- [ ] Relevant
- [ ] Time Constraint

### Goal

### Asking Questions

### Search Solutions

## AS
### Answers

### Share

## MoC
> [!Collections]- up {{title}}
>```dataview
>TABLE WITHOUT ID
>file.link as Note, updated as Updated, file.link.title as Title
>WHERE
>contains(up,this.file.link) 
>  and !endswith(file.name, "Template") 
>  and file.name != "{{title}}" 
>SORT updated desc
>```

> [!Collections]- in {{title}} (no cards & books)
>```dataview
>TABLE WITHOUT ID
>file.link as Note, updated as Updated, file.link.title as Title
>WHERE
>contains(in,this.file.link) 
>  and !endswith(file.name, "Template") 
>  and file.name != "{{title}}" 
>  and !(regexmatch("F\d+ - .*", file.name) or regexmatch("I\d+ - .*", file.name) or regexmatch("S\d+ - .*", file.name))
>  and !endswith(file.name, "Book")
>SORT updated desc
>```

> [!Collections]- {{title}}  Related Cards
>```dataview
>TABLE WITHOUT ID
>file.link as Note, updated as Updated, file.link.title as Title
>WHERE
>contains(in,this.file.link) 
>  and !contains(file.name, "Template") 
>  and file.name != "{{title}}"
>  and (regexmatch("F\d+ - .*", file.name) or regexmatch("I\d+ - .*", file.name) or regexmatch("S\d+ - .*", file.name))
>SORT updated desc
>```
