# Fancy-Music-Player [[Link]](https://frabjous-kelpie-a8730d.netlify.app/)
A modern looking music player -- Built with HTML 5 Audio API

Tech Stack: HTML, CSS, Vanilla JS (No Framework!), [HTML5 Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API).

* Attention: The music files are not hosted online -- So no music!....SORRY!.
             But works properly in local machine. To see, please clone....

SCREENSHOTS: 
https://user-images.githubusercontent.com/84492460/186226372-503130c1-ef3c-44c0-94d8-b83157806472.mp4


*** IMPLEMENTATION ***
 * Here we used html5 [audio](https://www.w3schools.com/tags/ref_av_dom.asp) element without `controls` attributes, so that we can control things with javascript.
 * We have stored all image, song, artist in form of object and put them inside an array.
 * On the page load, one song from the song array get selected and populated in the player with help of `loadSong` function.
 * When an user click on `play` icon, it'll first check whether a song is playing or not. To do that, there is a variable `isPlaying` which is set to `false` by default.
 * Now if a song is not playing, then the `playSong` function get executed which leads to change `isPlaying` to `true` and turn `play` icon into `pause` icon and execute [play](https://www.w3schools.com/tags/av_met_play.asp) method on audio element to start playing the song.
 * But if a song is playing, then the `pauseSong` function get executed which leads to change `isPlaying` to `false` and turn `pause` icon into `play` icon and execute [pause](https://www.w3schools.com/tags/av_met_pause.asp) method on audio element to stop playing the song.
 * Next, on click of Previous Song, Next Song button, these two functions `prevSong`, `nextSong` get executed accordingly, which basically increase / decrease the global variable `songIndex` & pass it to `loadSong` function. Atlast, execute `playSong` function.
 * Next Task :-- Progress Bar, Current Time, Total duration .
 * To get the current playback position, we listen for [timeupdate](https://www.w3schools.com/tags/av_event_timeupdate.asp) event on the audio element.
 * When this `event` get fired, `updateProgressBar` function executes which do the heavy lifting task of all the maths & calculation of finding `currentTime`, `duration` from audio element and update the Progress Bar
 according as the current playback position changes.
 * Also, to update the current playback position on the click at different position on the Progress Bar,
 `setProgressBarByClick` function executes which finds `clientWidth`, `offsetX` on the Progress Bar element
 and evaluate the percentage of `offsetX` in `clientWidth` along Total Duration.
 * Then change `currentTime` property of audio element to trigger `timeupdate` event which leads to change of
 all things like ProgressBar growth, current time, current playback position.
 * Final Task :-- switch to next song in line when current song runs out
 * To do that, we listen for [ended](https://www.w3schools.com/tags/av_event_ended.asp) which fires when the current playlist is ended and execute `nextSong` function.
