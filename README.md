# Fancy-Music-Player
A modern looking music player -- Built with HTML 5 Audio API

Tech Stack: HTML, CSS, Vanilla JS (No Framework!), [HTML5 Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)

*** IMPLEMENTATION ***
 * Here we used html5 [audio](https://www.w3schools.com/tags/ref_av_dom.asp) element without `controls` attributes, so that we can control things with javascript.
 * We have stored all image, song, artist in form of object and put them inside an array.
 * On the page load, one song from the song array get selected and populated in the player with help of `loadSong` function.
 * When an user click on `play` icon, it'll first check whether a song is playing or not. To do that, there is a variable `isPlaying` which is set to `false` by default.
 * Now if a song is not playing, then the `playSong` function get executed which leads to change `isPlaying` to `true` and turn `play` icon into `pause` icon and execute [play](https://www.w3schools.com/tags/av_met_play.asp) method on audio element to start playing the song.
 * But if a song is playing, then the `pauseSong` function get executed which leads to change `isPlaying` to `false` and turn `pause` icon into `play` icon and execute [pause](https://www.w3schools.com/tags/av_met_pause.asp) method on audio element to stop playing the song.