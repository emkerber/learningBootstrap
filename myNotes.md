# Sourcing

In HTML, source Bootstrap CSS then your own CSS, and then the viewport meta tag.
Also in HTML, source jQuery (use link on Bootstrap site), then Bootstrap JS, and then our own JS.
Example uses the Bootstrap CDN from their site, rather than hosting it locally.

# Container class

Containers wrap the content that you want to control with the Bootstrap grid system.
Two versions: default and container fluid class.
The default container class centers the content on a fixed width, which is responsive depending on the width of the viewport.
The container fluid class makes the layout completely responsive so it adjusts to the width of the browser/viewport.
Both versions of the container add padding to the sides to content isn't touching the edges of the viewport.

    <div class="container"></div>
    or
    <div class="container-fluid"></div>

The container div should begin just within the opening <body> tag and close at the end of the body (but should not contain script tags).

# Rows and columns

A new row means you want to start something on a new line. A column means you want to create a horizontal division within a row.

    <div class="row">

The row class assumes we're going to be using some sort of columns, so any padding associated with being within a container div is ignored.

    <div class="row">
      <div class="col-sm-3">

    The above code means that inside our row we want a column that takes up three spaces.

    -----

    <div class="row">
      <div class="col-sm-9">

    The above code means that inside our row we want a column that takes up nine spaces.

By default all of the columns have to add up to twelve because it's a twelve-column grid system.

The middle two letters (xs, sm, md, lg) create media query break points. Whenever our screen gets to be a certain width (e.g. small devices are 768 pixels, so when the view port or browser is larger than 768 pixels) we can control the layout with our specified number of columns. Anything smaller than this will not be effected by the column specifications and will stack.

If we're using the sm column structure and a regular container class, if the browser/view port becomes larger than 768, the width of the container will be set to a bit smaller than this (e.g. 750 pixels) and padding is added to each side of the container.

# Column layouts

  <article class="col-sm-4">

  The above code means each article will be in a grid where each of the elements will take four out of the 12 columns. Therefore, three should be in a row.

# Finishing the layout

Containers should go around sections, not the entire page. For example, they could go around sections that are styled similarly with Bootstrap.  

It's a great idea to add comments after closing divs that explain what they're closing; classes or IDs can be used as descriptors.

# Basic navigation

  <header>
    <nav>
      <ul class="nav nav-tabs">
        <li><a href="/home">Home</a></li>
        <li><a href="/other">Other</a></li>
      </ul>
    </nav>    
  </header>  

  This produces tabbed navigation, styled by Bootstrap.

  -----

  <li class="active"><a href="home">Home</a></li>

  If on the Home page, you can indicate it on the Home nav tab.

  -----

  <li class="disabled"><a href="/other">Other</a></li>

  This tab will be disabled, and cannot be clicked.

Best practice is to use the class "nav navbar-nav" rather than "nav nav-tabs" or "nav nav-pills". Additionally, add classes to the <nav> tag of navbar and either navbar-default or navbar-inverse. This will look like:

  <nav class="navbar navbar-default">
    <ul class="nav navbar-nav">
      <li class="active"><a href="/home">Home</a></li>
      <li><a href="/other">Other</a></li>
    </ul>
  </nav>    

Navbar-default produces darkened text when hovered over (and "active" has a darkened background), and navbar-inverse produces inverse colors with a black (or darker-colored) background with text that lightens when hovered over (and "active" has a very, very slightly darker background by default).

To help with accessibility, you should have a role tag within the <nav> tag.

  <nav class="navbar navbar-default" role="navigation">

The navbar should also be placed within a container, like so:

  <nav class="navbar navbar-default" role="navigation">
    <div class="container">
      <ul class="nav navbar-nav">
        <li class="active"><a href="/home">Home</a></li>
        <li><a href="/other">Other</a></li>
      </ul>
    </div> <!-- container -->  
  </nav>   

If you want a logo/text to the left of the navigation, use a <div> with class of "navbar-header", and a class in the anchor tag of "navbar-brand". This will look like:

  <nav class="navbar navbar-default" role="navigation">
    <div class="container">
      <div class="navbar-header">
        <a class="navbar-brand" href="/featured">Wisdom <span class="subhead">Pet Medicine</span></a>
      </div> <!-- navbar-header -->
      <ul class="nav navbar-nav">
        <li class="active"><a href="/home">Home</a></li>
        <li><a href="/other">Other</a></li>
      </ul>
    </div> <!-- container -->  
  </nav>   

Bootstrap, by default, adds a border radius, so you can change it in the .css file to:

  .navbar {
    border-radius: 0;
  }

# Controlling navigation positions

If you want to align an element to the right of the navigation, add a navbar-right class on the UL.

  <nav class="navbar navbar-default" role="navigation">
    <div class="container">
      <div class="navbar-header">
        <a class="navbar-brand" href="/featured">Wisdom <span class="subhead">Pet Medicine</span></a>
      </div> <!-- navbar-header -->
      <ul class="nav navbar-nav navbar-right">
        <li class="active"><a href="/home">Home</a></li>
        <li><a href="/other">Other</a></li>
      </ul>
    </div> <!-- container -->  
  </nav>   

You can align the navigation to either the top or the bottom of the page by finding the navbar-default class, and adding a class of navbar-fixed-top. Now, when you scroll, the navigation will stay put and content will be under it.

  <nav class="navbar navbar-default navbar-fixed-top" role="navigation">
    <div class="container">
      <div class="navbar-header">
        <a class="navbar-brand" href="/featured">Wisdom <span class="subhead">Pet Medicine</span></a>
      </div> <!-- navbar-header -->
      <ul class="nav navbar-nav navbar-right">
        <li class="active"><a href="/home">Home</a></li>
        <li><a href="/other">Other</a></li>
      </ul>
    </div> <!-- container -->  
  </nav>   

To align the navigation to the bottom of the page, use navbar-fixed-bottom instead. This will keep the navbar at the very bottom of the view, and content will move under it. Remember to leave a bit of space below your last content so it's not covered by the nav bar.

When the size of the browser becomes smaller, at a certain point the navigation will switch to a single-column layout.
You can control when this happens by creating a custom version of Bootstrap. Go to the Bootstrap website, then the "Customize and download" page, find the "Grid system" header, and change the "@grid-float-breakpoint-max" to the desired size.

You can create a collapsable button, which will make the navigation collapse to a button when it becomes smaller. The code is complicated, so you can copy and paste from the Bootstrap site. The "data-target" class needs to point to an ID on the page, so you will have to create an element with that ID. After the closing <div> tag for the navbar-header and before the <ul> tag, create a <div> with a class of "collapse navbar-collapse" and an ID of "collapse". The <div> should wrap around the <ul>.

# Building a footer layout

This will build a two-column footer, with contact information on one side and a nav on the other. The nav content is alligned to the right. The footer's content is not aligned with the container applied to the rest of the page, but instead is aligned with the edges of the screen, because "container-fluid" is used.

  <footer>
    <div class="content container-fluid">
      <div class="row">
        <div class="col-sm-6">
          <p>Call us toll-free at <span class="phone">888-555-1212</span></p>
          <p>All contents &copy; 2014 <a href="http://lynda.com">Lynda.com</a>. All rights reserved. </p>
        </div> <!-- col-sm-6 -->  
        <div class="col-sm-6">
          <nav class="navbar navbar-default" role="navigation">
            <ul class="nav navbar-nav navbar-right">
              <li><a href="/">Terms of Use</a></li>
              <li><a href="/">Privacy Policy</a></li>
            </ul>
          </nav>
        </div> <!-- col-sm-6 -->  
      </div> <!-- row -->  
    </div> <!-- content container-fluid -->    
  </footer>  

In CSS, you can make the background of the footer transparent.

footer .navbar-default {
  background: transparent;
}

# Adding a basic carousel

  <div class="carousel slide" data-ride="carousel" id="featured">
    <div class="carousel-inner">
      <div class="item active"><img src="images/lifestyle.jpg" alt="Lifestyle Photo"></div>
      <div class="item"><img src="images/mission.jpg" alt="Mission Photo"></div>
      <div class="item"><img src="images/vaccinations.jpg" alt="Vaccinations Photo"></div>
      <div class="item"><img src="images/fish.jpg" alt="Fish Photo"></div>
      <div class="item"><img src="images/exoticAnimals.jpg" alt="Exotic Animals Photo"></div>
    </div> <!-- carousel-inner -->  

    <a class="left carousel-control" href="/featured" role="button" data-slide="prev">
      <span class="glyphicon glyphicon-chevron-left"></span>
    </a>
    <a class="right carousel-control" href="/featured" role="button" data-slide="next">
      <span class="glyphicon glyphicon-chevron-right"></span>
    </a>
  </div> <!-- featured carousel -->

The carousel, in the example, is within the header, below the navigation.  

The <div> attribute data-ride="carousel" tells the JavaScript where to find and advance the carousel.

Every carousel needs and ID so you can link the navigation of the carousel to the particular carousel that you're advancing.

Each image goes within its own <div>, and traditionally the first item/carousel element has a class of "active", but you can actually place this anywhere to make any of the carousel elements active at the moment.

Carousels traditionally have two parts:
* the carousel itself
* navigation

You could modify the "carousel-inner" class to include a container class.

You can allow the user to control carousel navigation. Create an anchor tag between the carousel-inner and the closing featured console <div>, and the href should target the carousel ID.

# Creating basic page styles

Things you can do to personalize your Bootstrap style:

* change the default fonts (Google Fonts cited as resource)
  - font-family
  - font-weight
  - font-size

* control the carousel with Javascript
  - interval: amount of time to delay before automatically cycling an item; if false the carousel will not automatically  cycle
  - pause: pauses the cycling of the carousel on mouseenter and resumes cycling on mouseleave
  - wrap: whether the carousel should cycle continuously or have hard stops
  - keyboard: whether the carousel should react to keyboard events

# Modifying Bootstrap navigation styles

It's useful to "Inspect Element" in Chrome to see which classes/IDs are controlling colors/padding/etc.  

Examples:
- background-color: transparent;
- border: none;
- link styling (text color, hover color, coloring/font-weight of active tab)
- clear text-shadow, which Bootstrap sometimes adds by default

# Working with the branding and toggle styles

Toggle: when you resize the navigation and eventually it collapses into a single button.

# Overcoming injection issues

In CSS, you can use a media query, which targets elements only when they are a certain size.

  @media only screen
  and (max-width: 768px) {
    header .navbar-collapse.in {
      background-color: rgba(0, 0, 0, .5);
    }
  }
