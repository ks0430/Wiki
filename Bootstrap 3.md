# Bootstrap 3

Bootstrap is a free front-end framework for faster and easier web development.

Bootstrap includes HTML and CSS based design templates for typography, forms, buttons, tables, navigation, modals, image carousels and many other, as well as optional JavaScript plugins

> **What is Responsive Web Design?**
> Responsive web design is about creating web sites which automatically adjust themselves to look good on all devices, from small phones to large desktops.
> Reference:[Bootstrap 3](https://www.w3schools.com/bootstrap4/bootstrap_get_started.asp)



## .Container
The main part of the whole layouts.The fluid one provides a full width of container.
```html
<!-- Basic Container -->
<div class="container">
...
</div>

<!--Full Container-->
<div class="container-fluid">
...
</div>
```
## Grid System 
Bootstrap grid system is built with flexbox and allows up to 12 to colums across the page.

The grid system is responsive, and the colums will re-arrange automatically depending on the screen size.

**4 main classes**
| class    | Introduce                               |
| -------- | --------------------------------------- |
| .col-xs- | small devices - screen width >= 576px   |
| .col-sm- | medium devices - screen width >= 768px  |
| .col-md- | large devices - screen width >= 992px   |
| .col-lg- | xlarge devices - screen width >= 1200px |

### How to create coloums

Always with a row line.Put colums under row.
```html
<div class="row">
  <div class="col-xs">.col</div>
  <div class="col-xs">.col</div>
  <div class="col-xs">.col</div>
</div>
```

## Typography

Bootstrap's global default font-size is 14px, with a line height of 1.428.
This is applied to the `<body>` element and all paragraphs.
In addition, all `<p>` elements have a bottom margin that equals halp of their computed line-height.
So `<p>` have half line-height space each line.

### Title and subtitle

BS have 6 titles,`<h1>` to `<h6>`
```html
<h1>This is the title</h1>
<h1><small>This is the subtitle</small></h1>
```
### mark

Highlight some words.

```html
<p>This is the <mark>highlight</mark> word.</p>
```

### abbr

Tips: An abbreviation and an acronym are both shortened versions of something else.Both are often represented as a series of letters.
Making up abbreviations can give useful information to browers, translation systems and search engine.

BS will styled the element `<abbr>` in the following way:
```html
<p>The <abbr title="World Health Orinization">Who</abbr> is founded in 1948.</p>
```

### blackquote
```html
<blackquote>
This is the paragraphy which is quoted.
<footer> This is the footer </footer>
</blackquote>
```

### dl

Defined as description list.
```html
<dl>
<!-- Title -->
<dt>Coffee</dt>

<!-- Description -->
<dd> black not hot </dd>
</dl>
```

### code
Embedded code like `code` .
```html
<p>This is the important <code>word</code>.</p>
```

### kbd

Defined as keyboard element. BS will styled it in the following way:
```html
<p>Use <kbd>ctrl + p</kbd> to open the Print dialog box.</p>
```

### pre

For mutiple lines of code, use `<pre>` element.
```html
<pre>
Pre element is displayed in a fixed-width font, and it presevers both spaces and line breaks.
</pre>
```

### Text Styles

BS default text styles provides following class: `text-muted` 
, `text-primary`, `text-success`, `text-info`, `text-warning`， `text-danger`
If you want use blackground color, use following class: `bg-primary`...

```html
<p class="text-muted">The text is muted.</p>
```

## BS Tables

A basic BS table only have a light padding and only horizontal dividers.
The `.table` class adds basic styling to a table.

### Basic Table

```html
<table class="table">
    <thead>
        <tr>
            <td>Name</td>
            <td>Age</td>
        </tr>
    </thead>
    <tbody>
        <tr> <!--table row-->
            <td>Evelyn</td> <!--table description-->
            <td>23</td>
        </tr>
    </tbody>
</table>
```

### Striped-Rows

Add a `table-striped` class to table element, it will styled as striped rows

```html
<table class="table table-striped">
    ...
</table>
```
### Bordered Table

Add a `table-bordered` class to table element,it will add a border to table.

```html
<table class="table table-bordered">
    ...
</table>
```

### Hover rows

Add a `table-hover` class to table element,it will add a hover effect to table.

```html
<table class="table table-hover">
    ...    
</table>
```

### Condensed Table

Add a `table-condensed` class to table element,it will make a table more compact by cutting cell padding in half.

```html
<table class="table table-condensed">
    ...
</table>
```

### Contextual Classes

Contentual classes can be used to color table rows `tr` or `tb`

## BS Navbar

### Collapsible Navbar
>The navgation bar always takes up too much place on a small screen.
>To hide the navgation bar, only show it when it needed.
>From w3 school

There are some points when use navBar:

- Use `nav` element to start a navbar
- Use `container-fluid` class to expand to the max width
- Use `navbar-header` class to show a header on whatever devices
- Use a button and add custom id `myNavbar2` point to the following content
- Use three `span` element to draw the hamburger icon...

```html
<nav class="navbar navbar-inverse">
  <div class="container-fluid">
    <div class="navbar-header">
      <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#myNavbar">
        <!--Hamburger icon-->
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span> 
      </button>
      <a class="navbar-brand" href="#">WebSiteName</a>
    </div>
    <div class="collapse navbar-collapse" id="myNavbar">
      <!-- nav overwrite each element style,nav-bar overwrite it in one row-->
      <ul class="nav navbar-nav">
        <li class="active"><a href="#">Home</a></li>
        <li><a href="#">Page 1</a></li>
        <li><a href="#">Page 2</a></li> 
        <li><a href="#">Page 3</a></li> 
      </ul>
      
      <!-- Add an input box to the left-->      
      <form class="navbar-form navbar-left" action="/action_page.php">
      <div class="input-group">
        <input type="text" class="form-control" placeholder="Search">
        <div class="input-group-btn">
          <button class="btn btn-default" type="submit">
            <i class="glyphicon glyphicon-search"></i>
          </button>
        </div>
      </div>
     </form>
      
      <!--Right actions buttons-->
      <ul class="nav navbar-nav navbar-right">
        <li><a href="#"><span class="glyphicon glyphicon-user"></span> Sign Up</a></li>
        <li><a href="#"><span class="glyphicon glyphicon-log-in"></span> Login</a></li>
      </ul>
      
    </div>
  </div>
</nav>
```

## BS Pagination

> If you have a web sites with lots of pages, add the `.pagination class` to an `<ul>` element.
> From W3school
>

**Class definations**

| Class          | Style             | Function | Position |
| -------------- | ----------------- | -------- | -------- |
| .active        | Blue background   | Actived  | `<li>`   |
| .disable       | Grey color        | Disabled | `<li>`   |
| .pagination-lg | Large size        | Larger   | `<ul>`   |
| .pagination-sm | Small size        | Smaller  | `<ul>`   |
| .breadcrumbs   | Like bread crumbs | Style    | `<ul>`   |

```html
<ul class="pagination">
  <li><a href="#">1</a></li>
  <li class="active"><a href="#">2</a></li>
  <li class="disable"><a href="#">3</a></li>
  <li><a href="#">4</a></li>
  <li><a href="#">5</a></li>
</ul>
```

## BS Page

> Pager is also a form of pagination, it provides previous and next buttons.
>

| Class                 | Style             | Function                                | Postion |
| --------------------- | ----------------- | --------------------------------------- | ------- |
| .pager                | Default           | Previous & Next Buttons                 | `<ul>`  |
| .previous </br> .next | Sides of the page | Align each one to the sides of the page | `<li>`  |

```html
<ul class="pager">
  <li class="previous"><a href="#">Previous</a></li>
  <li class="next"><a href="#">Next</a></li>
</ul>
```

## BS List Groups

List group is the customized list type of Bootstrap.

| Class            | Position | Style   | Fuction             |
| ---------------- | -------- | ------- | ------------------- |
| .list-group      | `<ul>`   | Default | Define list group   |
| .list-group-item | `<li>`   | Default | Define list element |

**Linked group**

| Class            | Position | Style   | Fuction      |
| ---------------- | -------- | ------- | ------------ |
| .list-group      | `<div>`  | Default | Linked group |
| .list-group-item | `<li>`   | Default | Linked group |

**Styles**

| Class | Position | Style | Fuction |
| ----- | -------- | ----- | ------- |
| .badges | `<span>`  Right inside `<li>` | Badges & Signs |
| .active | `<a>` or `<li>` | Blue background | Actived |
| .disable |  `<a>` or `<li>` | Grey color | Disabled |
| .list-group-item-success | `<a>` or `<li>` after `.list-group-item` | Green | Success |
| .list-group-item-info | / | Blue | Info |
| .list-group-item-warning | / | Yellow | Warning |
| .list-group-item-danger |  | Red | Danger |


**Customized Text**

| Class                    | Position                             | Style               | Fuction |
| ------------------------ | ------------------------------------ | ------------------- | ------- |
| .list-group-item-heading | Titles: eg.`<h1>` </br> Inside `<a>` | Selected from h1-h6 | Titles  |
| .list-group-item-text    | `<p>` </br> Inside `<a>`             | Paragraph           | /       |

```html
<div class="list-group">
  <a href="#" class="list-group-item active">
    <h4 class="list-group-item-heading">First List Group Item Heading</h4>
    <p class="list-group-item-text">List Group Item Text</p>
  </a>
  <a href="#" class="list-group-item">
    <h4 class="list-group-item-heading">Second List Group Item Heading</h4>
    <p class="list-group-item-text">List Group Item Text</p>
  </a>
  <a href="#" class="list-group-item">
    <h4 class="list-group-item-heading">Third List Group Item Heading</h4>
    <p class="list-group-item-text">List Group Item Text</p>
  </a>
</div>
```
## BS Panels
A panel in BS is a bordered box with some padding around its content.


| Class          | Position                 | Style                   | Fuction        |
| -------------- | ------------------------ | ----------------------- | -------------- |
| .panel         | `<div>`                  | Basic                   | Basic required |
| .panel-default | `<div>` after `.panel`   | Default                 | Default style  |
| .panel-body    | `<div>`  inside `.panel` | Default                 | Content inside |
| .panel-heading | `<div>`  inside `.panel` | Heading                 | /              |
| .panel-group   | `<div>`  before `.panel` | Clean the bottom margin | /              |

## BS Tabs

## BS Question & Attension

Q:Carousel中图片大小不一致会导致左右箭头上下偏移。

Q:如果CSS文件一直不更新
A:osx 按住command + shift + r 强制刷新，单纯清除cache没用。

Q:Container cannot embeded twice.
A:

Q:fade and show didn't work
A:It's the feature of BS4 not BS3.