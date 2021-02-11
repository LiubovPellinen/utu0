This is simple example of  web-page  for ordering flowers  from a web store. 
 Project consist of 2 files index.html and style.css.
>The using of the table construction for the product basket is not a good idea in the real project. But I used it simply like an example of using table construction on web-page.

**1.index.html**.

 Web-page  consist of following parts: navigation menu (class: .header), basket of order(class: .basket), order’s form(class: .basketorder). In  the code of page  are used following constructions:link(names of products in the table), table(products), image (photos of products), form(orders form) , select(field in the form, where chose delivery method),   input fields “text” , “tel”(fields in the order’s form) and “number”( is used for entering the amount of products) , “submit”(button –“Submit” in the form)  and labels .

**HTML code of Navigation menu**.

```
<header class="header">
        <a href="" class="logo"><i>FLOWER</i></a>
        <input class="menu-btn" type="checkbox" id="menu-btn" />
        <label class="menu-icon" for="menu-btn"><span class="navicon"></span></label>
        <ul class="menu">
            <li><a href="#flowers">Our flowers</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </header>
```
Following part of <heder>  
```<input class="menu-btn" type="checkbox" id="menu-btn" 
<label class="menu-icon" for="menu-btn"><span class="navicon"></span></label>
```
is used to make navigation menu more responsible.
When window's width becomes smaller than 768px, the navigation menu is changed and the small
icon  appears in the up right corner. Navigation menu is opened and closed by clicking on it.
These label and checkbox participate in the handling of this event. The main part of handling is described in the style.css.

**2. style. css** includes description of styles of all objects which is using in the index.html- code and all events of its changings:

1. Color of links,  which is used like names of products in the table,  is changed  on the green and  links are underlined by hovering mouse over it.
```
#baskettable a:hover {
    color: rgb(11, 201, 21);
    text-decoration: underline;
}
```
2. Font size of links becomes  smaller   by clicking on it.
```
#baskettable a:active {
font-size: 90%;
}
```
3. Changing of navigation element’s  color  by hovering mouse over it:
```
.header li a:hover,
.header .menu-btn:hover {
    background-color: #f4f4f4;
}
```
4. Handling of event “clicking on the icon of navigation menu”.
```
.header .menu-btn:checked ~ .menu {
    max-height: 240px;
  }
```
5. Opening menu by clicking on the icon.
```
.header .menu-btn:checked ~ .menu {max-height: 240px; }
```
In the style.css-code are used different  ID and class selectors and different  combinators.
For example:

```
quantity + td {  width:110px; height:110px;  }
```
 
``` 
#baskettable { position: relative; top: 80px;}
```
   
```.
header .menu-btn:checked ~ .menu {max-height: 240px; }
```

Also is used specificity to make one row in the product table  different from other.(background is yellow, font of price  is red )
```
  #pricesale {  text-decoration: line-through; font-weight: bold;}
  #newprice{ color: red; }
```

The main moments  of responsive navigation menu:

1. Drawing menu icon.
```
.header .menu-icon .navicon:before,
.header .menu-icon .navicon:after {
    background: #333;
    content: '';
    display: block;
    height: 100%;
    position: absolute;
    transition: all .2s ease-out;
    width: 100%;
}
.header .menu-icon .navicon:before {
    top: 5px;
}
.header .menu-icon .navicon:after {
    top: -5px;
}
```
2. Handling of event “clicking on the icon of navigation menu”.

```
.header .menu-btn:checked ~ .menu {
    max-height: 240px;
  }
Adaptation of the menu to work in full window mode.( 48em = 768px)
  @media (min-width: 48em) {
    .header li {
      float: left;
    }
    .header li a {
      padding: 20px 30px;
    }
    .header .menu {
      clear: none;
      float: right;
      max-height: none;
    }
    .header .menu-icon {
      display: none;
    }
}
```
