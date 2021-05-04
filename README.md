
### Historical only, this is deprecated.. will point at new project soon


## MultiLink - Links With Choice
_Daniel Smith - javajoint at gmail dot com_
_8 March 2012_

MultiLink enables a menu of multiple web addresses from a click.  It's a great way to provide choice.  A picture tells the story:

<img style="border: 1px solid black" src="http://daniel.org/buckybits/wp-content/uploads/2012/02/ml2-brooklyn-example.png">

### Check out the Demo: http://daniel.org/demos/MultiLink3/ 
### Blog Post: http://daniel.org/cafebucky/2012/03/01/one-link-many-paths-clicking-choice-multilink-part-3/

MultiLink is built on 3 ideas:

* use the HTML5 "data" attribute to refer to lists of Link IDs and/or Tags
* use blocks of JSON data to organize IDs, Labels, URLs, and Tags
* tie it together with JavaScript (making good use of jQuery)

## Repository

The Gihub repo is a simple clone of my demo.  It's meant to be self-contained, with the lone exception being an include to get jQuery from code.jquery.com

## Quick Concepts

On the HTML side, a data attribute is set up such as:

    <a id="beer1" class="multilink"
         data-dls-links="sierranevada, fosters, pilsnerurquell">beer</a>


Which is a simple list that is matched up with some data that originated from a block of JSON:


        "sierranevada": {
            "label" : "Sierra Nevada",
            "url"   : "http://www.sierranevada.com/",
            "tags"  : ["beer", "ale"]
        },

It gets much more interesting when you look for tags, instead of absolute Link IDs:

    <ul>
        <li>Here is <a id="nyctag" class="multilink" data-dls-links=".nyc">"nyc"</a></li>
        <li>and ... <a id="bridgetags" class="multilink" data-dls-links=".bridge">"bridge"</a></li>

You can have lists of tags (".la, .nyc. ,sf, .london"), which will simply add whatever links are matched.

You can also get very specific:

        <li><a id="nycandbridge" class="multilink" data-dls-links=".nyc + .bridge">"nyc AND bridge (+)"</a></li>
        <li><a id="nycwobridge" class="multilink" data-dls-links=".nyc - .bridge">"nyc WITHOUT bridge (-)"</a></li>
        <li><a id="nycorbridge" class="multilink" data-dls-links=".nyc | .bridge">"nyc OR bridge (|)"</a></li>
        <li><a id="nycorbridgenolon" class="multilink" data-dls-links=".nyc | .bridge - .london">"nyc OR bridge, without London (| and -)"</a></li>
    </ul>

There is much more detail to be found in the <a href="http://daniel.org/demos/MultiLink3/">Demo</a> and the <a href-"http://daniel.org/cafebucky/2012/03/01/one-link-many-paths-clicking-choice-multilink-part-3/">Blog Post</a>

## Summary

MultiLink provides a powerful, flexible, and simple to set up means of giving choices for clickable items on a page.  It's not meant to replace menus used for site navigation, but rather, to open up the ideas of making the writing style of a site easer to read (how many times have you seen someone say "additional info at here, here, or here", when they could write "additional info at these places").  It also opens up the idea of writing HTML that uses placeholders for links, with the details of how they get resolved left to the actual data present when the item is clicked.




