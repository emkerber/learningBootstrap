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
