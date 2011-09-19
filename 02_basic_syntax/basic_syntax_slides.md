!SLIDE top
# Part I #
## Parlez-vous CoffeeScript?
### Basic syntax

!SLIDE fullscreen
![](buggles.jpg)

!SLIDE code-sample
## Variables, strings, numbers, interpolation ##
<!-- <a href="" class="minibutton run">Run it.</a>
<div class="repl_results">Results go here.</div> -->

<div>
<textarea id="string-assignment">
</textarea>
</div>

<script type="text/javascript">
$(document).ready(function() {
  // Unbind showoff's keyHandler for playback so I can type in the codemirror textarea.
  function keyHandler(event) {
    var key = event.keyCode;
    this.onkeydown = null;
    if (key == 37) // Left arrow
         {
             prevStep()
         }
     else if (key == 39) // Right arrow
         {
             nextStep()
         }
  }

  document.onkeydown = keyHandler;
  document.onkeyup = function() {
    this.onkeydown = keyHandler;
  };

myTextArea = document.getElementById("string-assignment");
myEditor = CodeMirror.fromTextArea(myTextArea, {tabMode: "shift"});

});
</script>

<span class="caption"><b>The Buggles</b> / Video Killed The Radio Star</span>


!SLIDE fullscreen
![](joan_jett.jpg)

!SLIDE code-sample
## Functions
<div>
<textarea id="functions">
</textarea>
</div>

<script type="text/javascript">
myTextArea = document.getElementById("functions");
myEditor = CodeMirror.fromTextArea(myTextArea, {tabMode: "shift"});
</script>

<span class="caption">
  <b>Joan Jett & The Blackhearts</b> / I Love Rock-n-Roll <br /> 
  <b>Information Society</b> / Lay All Your Love On Me
</span> 

!SLIDE bottom fullscreen
![](the_cure.jpg)

!SLIDE code-sample
## Objects #
<div>
<textarea id="objects">
quiteMoody =
  monday: "feel blue" 
  tuesday: "feel gray"
  wednesday: "feel gray again"
  thursday: "do not care about you"
  friday: "am in love"
</textarea>
</div>

<script type="text/javascript">
myTextArea = document.getElementById("objects");
myEditor = CodeMirror.fromTextArea(myTextArea, {tabMode: "shift"});
</script>
    
<span class="caption"><b>The Cure</b> / Friday I'm in Love</span>

!SLIDE fullscreen
![](when_in_rome.jpg)

<!-- !SLIDE
## Logical Operators ##
![](logical_operators.gif) -->

!SLIDE code-sample   
## Conditions ##

<div>
<textarea id="conditions">
</textarea>
</div>

<script type="text/javascript">
myTextArea = document.getElementById("conditions");
myEditor = CodeMirror.fromTextArea(myTextArea, {tabMode: "shift"});
</script>   

<span class="caption"><b>When In Rome</b> / The Promise</span>

!SLIDE 
# Want the examples?
## https://gist.github.com/1225971