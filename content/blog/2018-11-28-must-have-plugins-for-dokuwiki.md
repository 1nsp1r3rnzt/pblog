---
title: A list of Best Plugins for Dokuwiki
date: 2018-11-28T20:49:27+00:00
url: /plugins-dokuwiki/
header:
  teaser: /assets/images/uploads/2018/11/dokuwiki-plugin-header.png
classes: wide
image:
  path: /assets/images/uploads/2018/11/dokuwiki-plugin-header.png
categories:
  - Software
tags:
  - DokuWiki
  - Linux
  - Installation 
---

After successfully [installing DokuWiki](/dokuwiki-farm/), next step is to install all the essential plugins.
I use the following plugins.

## Must Have Plugins

- [Backup plugin](https://www.dokuwiki.org/plugin:backup) : a complete backup solution for DokuWiki. 

- [DocuBookMark plugin](http://gareus.org/wiki/dokubookmark): for saving bookmarks in your wiki

- [Drop Files](https://dokuwiki.org/plugin:dropfiles): Drop files into the edit area to upload them

- [Edit Tables](http://www.dokuwiki.org/plugin:edittable):  For editing table visually.   
![edit-tables-dokuwiki](/assets/images/uploads/2018/11/edit-tables-dokuwiki.png)

- [Html Comment](https://www.dokuwiki.org/plugin:htmlcomment): allows HTML style comments to be used.

- [Index Menu Plugin](https://www.dokuwiki.org/plugin:indexmenu) : Best navigation generation plugin.![Dokuwiki-index-menu plugin](/assets/images/uploads/2018/11/Dokuwiki-index-menu plugin.png)

- [Include Plugin](https://www.dokuwiki.org/plugin:include)   

```
{% raw %}
##########Usage##########
{{page>[id]&[flags]}}
{{section>[id]#[section]&[flags]}}
{{namespace>[namespace]#[section]&[flags]}}
{{tagtopic>[tag]&[flags]}}
{% endraw %}
```

- [MarkDownu](https://www.dokuwiki.org/plugin:markdowku) for using parsing markdown automatically.

- [Move plugin](https://www.dokuwiki.org/plugin:move) Allows to move namespaces.

- [NsPages Plugin](https://www.dokuwiki.org/plugin:nspages): create TOC for pages dynamically.

- [Search Index](http://www.dokuwiki.org/plugin:searchindex): Regenerate Complete Index

- [Snippeter Plugin](https://github.com/geco2/snippeter): Allows you to insert saved template as snippets during editing.

- [TemplatePageName Plugin](https://www.dokuwiki.org/plugin:templatepagename) : configurable names for templates. eg c_template

## Search And Tags

- [Tag Plugin](https://www.dokuwiki.org/plugin:tag): Assign category tags to wiki pages.  


``` 
{% raw %}
# Usage 
{{tag>[list of tags]}}
{{topic>[tag]&[flags]}}
{{searchtags&[flags]}}
{% endraw %}
```

- [Cloud Plugin](https://www.dokuwiki.org/plugin:cloud)

```
SYNTAX
~~CLOUD~~
~~CLOUD:number~~
~~TAGCLOUD~~
~~TAGCLOUD:number~~
~~TAGCLOUD:number>namespace1:subns11|.|namespace2~~
~~SEARCHCLOUD~~
~~SEARCHCLOUD:number~~

```

- [Tag Entry on Edit Page](https://www.dokuwiki.org/plugin:tagentry): Displays all tags below the edit form.

## Extra aesthetic features

- [BootStrap Wrapper plugin](http://www.dokuwiki.org/plugin:bootswrapper)

- [BlockQuote plugin](https://www.dokuwiki.org/plugin:blockquote) 

![quotes-plugin-dokuwiki](/assets/images/uploads/2018/11/quotes-plugin-dokuwiki.png)

Good for quick Addition

- [add new page](http://www.dokuwiki.org/plugin:addnewpage)

Usage:

```
{% raw %}
Put {{NEWPAGE}} or {{NEWPAGE>namespace}}
{% endraw %}

```


- [Ajax edit plugin](http://dokuwiki.org/plugin:ajaxedit) : For easier editing

## Data Mangement 

[bureaucracy](https://www.dokuwiki.org/plugin:bureaucracy): allows to create HTML forms to save data using pages.



## Task Management plugins

- [Do plugin](https://www.dokuwiki.org/plugin:do)

```
<do USER DATE>TEXT</do>
```

## Blog and Journal

- [Blog](https://www.dokuwiki.org/plugin:blog) : Allows to create a blog using DokuWIki
- [YearBox Plugin](https://www.dokuwiki.org/plugin:yearbox): create a calendar based journal in a table.

## Multi WIkis

[Farmer Plugin](https://www.dokuwiki.org/plugin:farmer)



## Most Versatile Template

- [Bootstrap3 Template](https://www.dokuwiki.org/template:bootstrap3): Customizable Bootstrap based template, responsive.

