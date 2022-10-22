---
title: "CSS Selectors CheatSheet"
date: 2022-10-22T18:40:02+08:00
tags: ["CSS","Selectors"]
categories: ["CSS","CheatSheet"]
---
# CSS Combinator Selectors 
- Descendant
	-  Matching all elements inside parent.
	  
```
    <!-- Descendant -->
.container img {
	max-width: 100;
}
```


- Child
	- Applies to only direct children of parent, further nested elements wont be selected.
			
```
   <!-- Child -->
.nav > li {
	padding: 10px;
}
```
- Chained
	- Will select both class names.
```
     <!-- Chained -->
.class6.class3 {
	color:black
}
```
- Sibling
	- Selects elements next to sibling.
```
      <!-- Sibling -->
h4 ~ a {
	font-weight:bold;
}
```
  
  - Adjacent sibling
	  - Used to select element directly after a specific element.
```
  <!-- Adjacent sibling -->
p + img {
	background-color: #1f2335;
}
```
