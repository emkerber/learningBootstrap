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

    <div class="row">
      <div class="col-sm-9">

    The above code means that inside our row we want a column that takes up nine spaces.

By default all of the columns have to add up to twelve because it's a twelve-column grid system.

The middle two letters (xs, sm, md, lg) create media query break points. Whenever our screen gets to be a certain width (e.g. small devices are 768 pixels, so when the view port or browser is larger than 768 pixels) we can control the layout with our specified number of columns. Anything smaller than this will not be effected by the column specifications and will stack.

If we're using the sm column structure and a regular container class, if the browser/view port becomes larger than 768, the width of the container will be set to a bit smaller than this (e.g. 750 pixels) and padding is added to each side of the container.

# Column layouts

column layouts....
