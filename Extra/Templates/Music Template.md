---
title: {{title}}
in:
  - "[[Index]]"
genre:
  - "[[]]"
created: "[[{{date}}]]"
updated: "[[{{date}}]]"
---
> [!Collections]- up {{title}}
>```dataview
>TABLE WITHOUT ID
>file.link as Note, updated as Updated, file.link.title as Title
>WHERE
>contains(up,this.file.link) 
>  and !contains(file.name, "Template") 
>  and file.name != "{{title}}" 
>SORT updated desc
>```

> [!Collections]- in {{title}}
>```dataview
>TABLE WITHOUT ID
>file.link as Note, updated as Updated, file.link.title as Title
>WHERE
>contains(in,this.file.link) 
>  and !contains(file.name, "Template") 
>  and file.name != "{{title}}" 
>  and !regexmatch("Z\d+", file.name)
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
>  and (regexmatch("F\d+ - .*", file.name) or regexmatch("I\d+ - .*", file.name))
>SORT updated desc
>```

> [!Collections]- ######  {{title}} Books
>```dataview
>TABLE WITHOUT ID
>file.link as Note, file.link.book_number as Number, file.link.title as Title, updated as Updated
>WHERE
>contains(in,this.file.link) 
>  and !contains(file.name, "Template") 
>  and file.name != "{{title}}"  
>  and endswith(file.name, "Book")
>SORT updated desc
>```