##Full Stack Web Development - Coursera Specialization
#### Module 2 - Front-End Web UI Frameworks and Tools
###### by **The Hong Kong University of Science and Technology**
###Getting Started with Bootstrap
----------
* Insert the following code in the head of *index.html* file before the title.

```
 <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- The above 3 meta tags *must* come first in the head; any other head 
         content must come *after* these tags -->
```
* Add the following code in the head after the title. This will include Bootstrap CSS into your web page.
```
  <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">
    <link href="css/bootstrap-theme.min.css" rel="stylesheet">

    <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
    <!--[if lt IE 9]>
      <script src="https://oss.maxcdn.com/html5shiv/3.7.2/html5shiv.min.js"></script>
      <script src="https://oss.maxcdn.com/respond/1.4.2/respond.min.js"></script>
    <![endif]-->
```

* Note the subtle change in the fonts of the content of the web page. This is the Bootstrap typography effect coming into play. The default Bootstrap typography sets the font to Helvetica Neue and selects the appropriate font size based on the choice of the heading style and paragraph style for the content.

* At the bottom of the page, just before the end of the body tag, add the following code to include the JQuery library and Bootstrap's Javascript plugins. Bootstrap by default uses the JQuery Javascript library for its Javascript plugins. Hence the need to include JQuery library in the web page.

```
<!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
    <!-- Include all compiled plugins (below), or include individual files as needed -->
    <script src="js/bootstrap.min.js"></script>
```

####**Using a Container class**

* We use the container class to keep content within a fixed width on the screen, determined by the size of the screen. The alternative is to use the container-fluid class to make the content automatically to span the full width of the screen.  Add the container class to the top most div in the file as follows.
```
<div class="container"> ...
```

####**Dividing the content into rows**
* Let us now add the class row to the first-level inner div elements inside the container. This organizes the page into rows of content. I
```
<div class="row"> ...
```
####**Creating a Jumbotron**

* Let us add the class jumbotron to the header class as shown below. This turns the header element into a Bootstrap component named Jumbotron. A jumbotron is used to showcase key content on a website. In this case we are using it to highlight the name of the restaurant.
```
<header class="jumbotron"> ... 
```
* In the header add a container class to the first inner div and a row class to the second inner div.

####**Creating a footer**

Finally, in the footer add a container class to the first inner div and a row class to the second inner div.

####**Bootstrap Grid System and Responsive Design**
Bootstrap is designed to be mobile first, meaning that the classes are designed such that we can begin by targeting mobile device screens first and then work upwards to larger screen sizes. The starting point for this is first through media queries. We have already added the support for media queries, where we added this line to the head:
```
 <meta name="viewport" content="width=device-width, initial-scale=1">
```
The *viewport* meta tag ensures that the screen width is set to the device width and the content is rendered with this width in mind. This brings us to the second issue, designing the websites to be responsive to the size of the viewport. This is where the Bootstrap grid system comes to our aid. Bootstrap makes available four sizes, xs for extra small, sm for small, md for medium and lg for large screen sizes. We have already seen the basics of responsive design. In this exercise, we will employ the Bootstrap grid classes to design the websites. We have already divided the content into rows. Each row in Bootstrap grid system is divided into 12 columns. We would like our website to have the content stacked on extra small devices, but become horizontal within each row for smaller devices and beyond. Towards this goal, we will make use of the classes .col-xs-*, .col-sm-*, col-md-*, and .col-lg-* for defining the layouts for the various device sizes. We can specify how many columns each piece of content will occupy within a row, all adding up to 12 or a multiple thereof.

####**Applying column classes within each row**
* In the header row, we will display the restaurant name and the description to occupy 8 columns, while we will leave four columns for displaying the restaurant logo in the future. Let us go into the jumbotron and define the classes for the inner divs as follows:
```
<div class="col-xs-12 col-sm-8"> ... </div>

<div class="col-xs-12 col-sm-4"> ... </div>
```
* For the remaining three div rows that contain content, let us define the classes for the inner divs as follows:
```
<div class="col-xs-12 col-sm-3"> ... </div>

<div class="col-xs-12 col-sm-9"> ... </div>
```
* For the footer, let us define the classes for the inner divs as follows:
```
<div class="col-xs-6 col-sm-3"> ... </div>

<div class="col-xs-6 col-sm-5"> ... </div>

<div class="col-xs-12 col-sm-4"> ... </div>

<div class="col-xs-12"> ... </div>
```
Now you can see how the web page has been turned into a mobile-first responsive design layout.

####**Using Push, Pull and Offset with column layout classes**
* In the content rows, we would like to have the title and description to alternate so that it gives an interesting look to the web page. For extra small screens, the default stacked layout works best. This can be accomplished by using the .col-sm-push-* and .col-sm-pull-* for the first and the third rows as follows:
```
<div class="col-xs-12 col-sm-3 col-sm-push-9"> ... </div>

<div class="col-xs-12 col-sm-9 col-sm-pull-3"> ... </div>

```
* For the div containing the <ul> with the site links, update the class as follows:
```
<div class="col-xs-5 col-xs-offset-1 col-sm-2 col-sm-offset-1">
```
####**List styles**

* You can use several list styles to display lists in different formats. We will use the unordered list style *list-unstyled* to display the links at the bottom of the page without the bullets. To do this, go to the links in the footer and update the ul as follows
```
 <ul class="list-unstyled"> ... </ul>
```
####**Using Custom CSS classes**

We can define our own custom CSS classes in a separate CSS file, and also customize some of the built-in CSS classes. 

* Create a file named *mystyles.css* in the css folder. Open this file to edit the contents. Add the following CSS code to the file:
```
.row-header{
    margin:0px auto;
    padding:0px auto;
}

.row-content {
    margin:0px auto;
    padding: 50px 0px 50px 0px;
    border-bottom: 1px ridge;
    min-height:400px;
}

.row-footer{
    background-color: #AfAfAf;
    margin:0px auto;
    padding: 20px 0px 20px 0px;
}
```
* Include the mystyles.css file into the head of the index.html file as follows:
```
<link href="css/mystyles.css" rel="stylesheet">
```
* Then add these classes to the corresponding rows in the *index.html* file as follows. See the difference in the *index.html* file in the browser. The first one is for the row in the `<header>`, the next three for the rows in the content, and the last one directly to the `<footer>` tag.
```
 <div class="row row-header"> ... </div>

<div class="row row-content"> ... </div>

<div class="row row-content"> ... </div>

<div class="row row-content"> ... </div>

<footer class="row-footer"> ... </footer>
```
* Our last set of customization is to the jumbotron and the address. Add the following to mystyles.css file:
```
.jumbotron {
    padding:70px 30px 70px 30px;
    margin:0px auto;
    background: #7986CB ;
    color:floralwhite;
}

address{
    font-size:80%;
    margin:0px;
    color:#0f0f0f;
}
```

####**ccccc**
####**ccccc**
####**ccccc**
####**ccccc**




![Home Page](img/Home.png?raw=true "Home Page")




#### Updated: 2016-11-01
