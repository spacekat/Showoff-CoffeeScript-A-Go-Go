!SLIDE
# Part II
## Standalone website
![](my_melody.png)
### Picking Favorite Bands 

!SLIDE
## File tree
![](file_tree.gif)
### Take a peek if you would like:
### <span class="callout">https://github.com/spacekat</span> ###
### CoffeeScript-jQuery-demo--favorite-bands ###

!SLIDE code-sample
## HTML for listing a single band ##
    @@@ html
    <li>
      <h2>OMD</h2>
      <a href="#" class="star whatevs"></a>
      <div class="clear"></div>
    </li>

<span class="caption">index.html</span>

!SLIDE code-sample
## HTML for including JavaScript ##
    @@@ html
    <!-- jQuery imported from Google -->
    <script 
      src="http://ajax.googleapis.com/ajax/libs/jquery/1.6.2/jquery.min.js" 
      type="text/javascript"></script>

    <!-- import your generated JavaScript file -->
    <script src="js/bands.js" type="text/javascript"></script>

<span class="caption">index.html</span>

  
!SLIDE code-sample
## .star classes ##
![](star_sprite.jpg)
<span class="caption">style.css</span>

!SLIDE
# jQuery Snack Break #
![](Adventure_Time.gif)
## http://api.jquery.com/ ##
<span class="caption">Adventure Time</span>

!SLIDE code-sample execute incremental coffeescript
## Add .click() and .toggleClass() ##
    @@@ javascript
    $(document).ready ->

      $('a').click (event) ->
        event.preventDefault()
        $(this).toggleClass('fave whatevs')
        
<span class="caption">bands.coffee</span>

!SLIDE code-sample
## Watch and compile #
    @@@ Shell
    $ coffee -wc js/
    
!SLIDE bullets incremental
# It works! But... #

* All in the browser, no database.
* If you refresh, your faves are blown away.
* So, lets fix that with Rails.