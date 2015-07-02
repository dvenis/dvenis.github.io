---
layout: page
title: Radio
permalink: /radio/
---

Listen the garbage I like to listen to!

Mainly denpa and moe Japanese pop. Adding more music overtime...


<div id="audio_controller">
  <audio id="radio_audio" src="http://104.167.119.161:8001/test" >
    Your browser doesn't support HTML5 audio. :(
  </audio>

  <input id="play_button" value="Play" type="button"></input>
  <input id="volume_control" type="range" value="50" min="0" max="100"></input>

</div>

<script src="//ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js"></script>
<script src="/assets/js/jquery.shoutcast.min.js"></script>

<h1 id="songtitle">no song.</h1>

<script>

$( "#play_button" ).click(function() {

  var pausing = $("#play_button").val() === 'Pause';
  $("#play_button").val(pausing ? 'Play' : 'Pause');

  if (pausing) {
    console.log('pausing');
    $('#radio_audio').trigger("pause");
  } else {
    console.log('playing')
    $('#radio_audio').trigger("play");
  }

  return false;
});

$( "#volume_control" ).on("change mousemove", function() {
  console.log("chyaning volume: " + $(this).val() / 100.0);
  $("#radio_audio").prop("volume", $(this).val() / 100.0);
});


</script>
