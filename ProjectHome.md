## Note ##

This repository is no longer updated.  The plugin has moved to [GitHub](https://github.com/flipbit/jquery-image-annotate).


---


A jQuery Image Annotation plugin that can create Flickr-like comments on images embedded in web pages.


This plugin works with jQuery 1.2.6 and 1.3.2.


Full details on this plugin's usage can be seen [in this blog post](http://blog.flipbit.co.uk/2009/03/jquery-image-annotation-plugin.html).  Your can also see a [live demonstration](http://www.flipbit.co.uk/jquery-image-annotation.html) of the plugin.


## Using the plugin ##

To use the plugin you first need to reference the jQuery and jQuery UI libraries in your page.  Add the `jquery.annotate.js` and `annotation.css` files to enable the plugin.

```
<script type="text/javascript" src="js/jquery-1.2.6.min.js"></script>
<script type="text/javascript" src="js/jquery-ui-1.5.3.min.js"></script>
<script type="text/javascript" src="js/jquery.annotate.js"></script>

<style type="text/css" media="all">@import "css/annotation.css";</style>
```

Once you've added in the necessary scripts, hook up an image on the page by using the following syntax:

```
<script language="javascript">
  $(window).load(function() {
    $("#toAnnotate").annotateImage({
      editable: true,
      useAjax: false,
      notes: [ { "top": 286, 
                 "left": 161, 
                 "width": 52, 
                 "height": 37, 
                 "text": "Small people on the steps", 
                 "id": "e69213d0-2eef-40fa-a04b-0ed998f9f1f5", 
                 "editable": false },
               { "top": 134, 
                 "left": 179, 
                 "width": 68, 
                 "height": 74, 
                 "text": "National Gallery Dome", 
                 "id": "e7f44ac5-bcf2-412d-b440-6dbb8b19ffbe", 
                 "editable": true } ]	
    });
  });
</script>
```

It is important to use the `$(window).load(function()` function as this will fire once
the page and all it's images have loaded.  Failing to do so will result in the plugin executing before the image dimensions have been determined.


The HTML markup for the page looks like this:

```
<html>
  <head>
    <title>Demo Page</title>
  </head>
  <body>
    <div>
      <img id="toAnnotate" src="images/trafalgar-square-annotated.jpg" alt="Trafalgar Square" />
    </div>
  </body>
</html>
```

A copy of all this code is included in the release.