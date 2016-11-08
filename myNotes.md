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
