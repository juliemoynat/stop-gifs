#Bookmarklet to stop all GIFs in a webpage

Minified JavaScript code taken from the ["Stopping GIF Animation Programmatically" Stackoverflow subject](https://stackoverflow.com/questions/3688460/stopping-gif-animation-programmatically#answer-4276742)

1. Copy this code and create a new empty bookmark in your web browser.
2. Paste this code in the "address" field.
3. When you go to a web page with animated GIFs, click on the bookmark and all GIFs will be stopped.

```
javascript:(function(){function is_gif_image(e){return/^(?!data:).*\.gif/i.test(e.src)}function freeze_gif(t){var i=document.createElement("canvas"),e=i.width=t.width,a=i.height=t.height;i.getContext("2d").drawImage(t,0,0,e,a);try{t.src=i.toDataURL("image/gif")}catch(e){for(var r,g=0;r=t.attributes[g];g++)i.setAttribute(r.name,r.value);t.parentNode.replaceChild(i,t)}}[].slice.apply(document.images).filter(is_gif_image).map(freeze_gif);}) ()
```
