##Full Stack Web Development - Coursera Specialization
#### Module 2 - Front-End Web UI Frameworks and Tools
###### by **The Hong Kong University of Science and Technology**
###Getting Started with Bootstrap

By the end of the following steps, we are going to have the following Home Page:

![Home Page](img/Home.png?raw=true "Home Page")
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
####**Create a basic navigation bar**
* We will now add a simple navigation bar to the web page so that it provides links to the other pages on the website. Start by adding the following code to the body just above the header jumbotron.
```
 <nav class="navbar navbar-inverse navbar-fixed-top" role="navigation">
            <div class="container">
                <ul class="nav navbar-nav">
                    <li class="active"><a href="#">Home</a></li>
                    <li><a href="#">About</a></li>
                    <li><a href="#">Menu</a></li>
                    <li><a href="#">Contact</a></li>
                </ul>
            </div>
        </nav>       
```
In the above code, we can see the use of the nav element to specify the navigation information for the website. This nav element is styled by the navbar that declares it as a navigation bar, and the *navbar-inverse* class to specify that the page should use the dark navigation bar. In addition the inner *ul* is used to specify the items to be put in the navigation bar. This *ul* is styled with *nav* and *navbar-nav* classes to specify that the items should be displayed inline inside the navigation bar. We also use the container class inside the navigation bar. This navigation bar does not use responsive design at the moment.

####**Creating a responsive navigation bar**
* We would like the navigation bar elements to collapse for shorter screens, to be replaced by a toggle button so that the items can be toggled on or off when required on smaller screens. This can be achieved by adding the following code to the navigation bar, just below the container div.
```
 <div class="navbar-header">
     <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#navbar" aria-expanded="false" aria-controls="navbar">
                        <span class="sr-only">Toggle navigation</span>
                        <span class="icon-bar"></span>
                        <span class="icon-bar"></span>
                        <span class="icon-bar"></span>
                    </button>
                    <a class="navbar-brand" href="#">Ristorante Con Fusion</a>
                </div>
```
You will now notice the addition of a link to the left of the Home link with the name of the restaurant. This is the brand name for the website. You can replace this with the logo for the website. This is created by the `<a class="navbar-brand">` tag. The other part is the creation of a button with three horizontal lines. For larger screens, this button is hidden. For smaller screens, this button becomes visible. This button will act as the toggle for the navbar items on small screens. At the moment you still see the items being displayed in the navigation bar even for smaller screens. We will fix this in the next step.

* To hide the items from the navigation bar for smaller screens, we need to enclose the ul within another navigation bar as follows:
```
<div id="navbar" class="navbar-collapse collapse">
    <ul class="nav navbar-nav"> ... </ul>
</div>
```

By doing this, we are specifying that this *navbar* with the id *navbar* will be collapsed on smaller screens, but can be toggled on or off when the toggle button is clicked. Note the use of *data-toggle="collapse" data-target="#navbar" aria-expanded="false" aria-controls="navbar"* within the button. This specifies that the menu items are collapsed on smaller screens when the toggle button is visible. They can be displayed or hidden by clicking the toggle button.

* Note that the navbar scrolls when the web page in the browser is scrolled. If we wish to keep the navigation bar always visible at the top of the page when the page is scrolled, then we should change the navbar-static-top to navbar-fixed-top. Let us do this now. Note that after the change, the navigation bar remains visible at the top of the page even when the page is scrolled.

####**Adding a Dropdown Menu to the Navigation Bar**
* The next modification adds a Dropdown menu to the navigation bar. Let us target the "Menu" item in the navigation bar and turn it into a dropdown menu item. When this item is clicked, a dropdown menu will be displayed. To do this, modify the list item for the "Menu" item in the navigation bar by replacing it with the following code:
```
 <li class="dropdown">
     <a href="#" class="dropdown-toggle" data-toggle="dropdown"
     role="button" aria-haspopup="true" aria-expanded="false">
     Menu <span class="caret"></span></a>
     <ul class="dropdown-menu">
         <li><a href="#">Appetizers</a></li>
         <li><a href="#">Main Courses</a></li>
         <li><a href="#">Desserts</a></li>
         <li><a href="#">Drinks</a></li>
         <li role="separator" class="divider"></li>
         <li class="dropdown-header">Specials</li>
         <li><a href="#">Lunch Buffet</a></li>
         <li><a href="#">Weekend Brunch</a></li>
    </ul>
</li>
```
* In this modification, the "Menu" list item is now replaced with a dropdown-toggle, which when pressed will show the selection menu below the navigation bar. The structure of this code has similarities with the toggle button that we used above for showing and hiding the navbar items for small screens.

####**Modifications to the CSS styles**
* We would like to have the navigation bar displayed in darker blue color, instead of black. In addition, we would like the navigation bar to indicate the current page by highlighting the item with a darker background in the navbar. In addition, when we use the fixed navigation bar, we should give the body of the page an upper margin of 50px, so that the top 50px of the page does not get hidden under the navigation bar. We accomplish these by adding these CSS customisations to the *mystyles.css* file.
```
body{
    padding:50px 0px 0px 0px;
    z-index:0;
}

.navbar-inverse {
     background: #303F9F;
}

.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
    color: #fff;
    background: #1A237E;
}

.navbar-inverse .navbar-nav > .open > a,
 .navbar-inverse .navbar-nav > .open > a:hover,
 .navbar-inverse .navbar-nav > .open > a:focus {
    color: #fff;
    background: #1A237E;
}

.navbar-inverse .navbar-nav .open .dropdown-menu> li> a,
.navbar-inverse .navbar-nav .open .dropdown-menu {
    background-color: #303F9F;
    color:#eeeeee;
}

.navbar-inverse .navbar-nav .open .dropdown-menu> li> a:hover {
    color:#000000;
}
``` 
####**Using Icon Fonts and Other CSS classes**
* The last part of the exercise is to make use of the glyphicons that are provided as part of Bootstrap. In addition we will also use two additional popular font icons.
*  One of the most popular iconic font toolkit is Font Awesome. Go to its website https://fortawesome.github.io/Font-Awesome/ and download the zip file and move it to the conFusion folder and unzip it. You will find the *font-awesome-4.4.0* folder being created. Go into this folder and move the contents of the css folder to conFusion/css and the contents of the fonts folder to *conFusion/fonts* folder. Then you can delete the *font-awesome-4.4.0* folder.
* Download the *bootstrap-social.css *file to *conFusion/css* folder. This is a modified version of the bootstrap-social available on the http://lipis.github.io/bootstrap-social/. We added in support for G+ and YouTube 
*  We now need to include the css files for font awesome and bootstrap-social in the index.html file. Add the following code to the head of the file after the links for importing Bootstrap CSS classes:buttons.
```
<link href="css/font-awesome.min.css" rel="stylesheet">
<link href="css/bootstrap-social.css" rel="stylesheet">
```
* Let us now use some font icons in our web page and decorate it. First use the glyphicons that is part of Bootstrap to add a home icon to the Home link on the navigation bar. Update the home list item as follows:
```
<li class="active"><a href="#"><span class="glyphicon glyphicon-home"
aria-hidden="true"></span> Home</a></li>
```
* Next, go down to the address in the footer of the page and replace the "Tel.", "Fax" and "Email" with the corresponding font awesome based icons as follows:
```
<i class="fa fa-phone"></i>: +852 1234 5678<br>
<i class="fa fa-fax"></i>: +852 8765 4321<br>
<i class="fa fa-envelope"></i>: 
    <a href="mailto:confusion@food.net">confusion@food.net</a>
```
* Finally, let us use the bootstrap-social CSS classes to create the social buttons in the footer by replacing the social sites' links with the following code:
```
<div class="nav navbar-nav" style="padding: 40px 10px;">
    <a class="btn btn-social-icon btn-google-plus" href=
    "http://google.com/+"><i class="fa fa-google-plus"></i></a>
    <a class="btn btn-social-icon btn-facebook" href=
    "http://www.facebook.com/profile.php?id="><i class="fa fa-facebook"></i></a>
    <a class="btn btn-social-icon btn-linkedin" href=
    "http://www.linkedin.com/in/"><i class="fa fa-linkedin"></i></a>
    <a class="btn btn-social-icon btn-twitter" href="http://twitter.com/"><i class="fa fa-twitter"></i></a>
    <a class="btn btn-social-icon btn-youtube" href="http://youtube.com/"><i class="fa fa-youtube"></i></a>
    <a class="btn btn-social-icon" href="mailto:"><i class="fa fa-envelope-o"></i></a>
</div>
```
####**ccccc**
####**ccccc**


#### Updated: 2016-11-01
