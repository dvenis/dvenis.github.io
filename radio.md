---
layout: page
title: Radio
permalink: /radio/
---

Listen the garbage I like to listen to!

Mainly denpa and moe Japanese pop. Adding more music overtime...


<div id="audio_controller" class="radio_controller">
  <audio id="radio_audio" src="http://104.167.119.161:8001/test" >
    Your browser doesn't support HTML5 audio. :(
  </audio>

  <a href="#" title="Play video" class="play_button">&#x25ba;</a>
  <div class="volume_control">
    <input id="volume_control" type="range" value="50" min="0" max="100"></input>
  </div>

</div>

<script src="//ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js"></script>
<script src="/assets/js/jquery.shoutcast.min.js"></script>

<h1 id="songtitle">no song.</h1>

<script>

$( "#volume_control" ).on("change mousemove", function() {
  $("#radio_audio").prop("volume", $(this).val() / 100.0);
});

$( ".play_button" ).click(function() {
   $(this).toggleClass('paused');
   if ($(this).hasClass('paused')) {
     $('#radio_audio').trigger("play");
     $(this).html("&#9612;&#9612;");  
   } else {
     $('#radio_audio').trigger("pause");
     $(this).html("&#x25ba;");
   }

   return false;
});

</script>
