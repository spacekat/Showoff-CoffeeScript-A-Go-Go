!SLIDE
# Part III
## Enhancing with Rails
![](my_melody_ajax.png)
### Picking Favorite Bands ###


!SLIDE bullets incremental transition=fade
![](bff.gif)
## Rails 3.1 + CoffeeScript = BFF
* <span class="callout">.coffee</span> files in /app/assets/javascripts
* jQuery is included by default

!SLIDE bullets incremental
# Setting up the Rails app #

* <span class="callout">Database:</span> New table "Bands" that stores a band name, and a favorite flag.
* <span class="callout">Routes:</span> Added route to /favorite
<!-- (config/routes.rb) -->


!SLIDE bullets incremental

* <span class="callout">Bands Model:</span> Added the function <br />"def toggle_favorite"
<!-- (to app/models/band.rb) -->
* <span class="callout">Bands View:</span> Dynamically loaded with bands from the database. 
<!-- (in app/views/bands/index.html.erb) -->
* <span class="callout">Bands Controller:</span> Added action called "favorite"
<!-- (app/controllers/bands_controller.rb) -->


!SLIDE
# Whew! 
## Okay, lets add an AJAX request

!SLIDE fullscreen
![](ajax_01.gif)

!SLIDE fullscreen
![](ajax_02.png)

!SLIDE fullscreen
![](ajax_03.png)

!SLIDE fullscreen
![](ajax_04.png)

!SLIDE incremental
## Adding the AJAX request #

    @@@ javascript
    $ ->
      $("a").click (e) ->
        selectedLink = ($ this)
        e.preventDefault()
        $.ajax {
          type: "PUT"
          dataType: 'json'
          url: $(this).attr('href')
          success: (res) ->
            selectedLink
              .toggleClass("fave whatevs")
        }
        false  

<span class="caption">bands.coffee</span>


!SLIDE
# Hooray!
## Now the favorites are saved to the database ##
![](saved.png)

!SLIDE bullets incremental
# Even better
## Use Rails' <span class="callout">Remote Links</span>
* Powered by the UJS driver, rails.js
* Allow us to override click events with AJAX submissions
* Easy to setup with HTML5 'data-' tags

!SLIDE bullets incremental
# Setup the view to use Remote Links #

* Update the star HREF with data- tags
* data-remote="true"
* data-method="put"

!SLIDE
## Before ##
    @@@ html
    <a href="<%= favorite_band_path(band) %>" 
    class="star favorite-manual 
    <%= band.favorite ? "fave" : "whatevs" %>"></a>
    
## After ##
    @@@ ruby
    <%= link_to "", favorite_band_path(band),
      :remote => true,
      :method => :put,
      :class => "favorite-rails star 
      #{band.favorite ? "fave" : "whatevs"}" %>

<span class="caption">/app/views/bands/index.erb</span>


!SLIDE
## Scratch that big ajax() call #
### Instead, bind the event "ajax:success" to the link
    @@@ javascript
    $ ->
      $("a").bind 'ajax:success', ->
        $(this).toggleClass("fave whatevs")

<span class="caption">bands.coffee</span>

!SLIDE
# Woot! 
## Now it only uses 3 lines of CoffeeScript.