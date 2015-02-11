---
layout: post
title: Quick Guide to Using the YouTube API
---

# Quick Guide to Using the YouTube API

The [documentation](https://developers.google.com/youtube/js_api_reference) is pretty good, but doesn't provide a simple view of code I have to hunt down and reverse engineer every 3 months or so.

This post is largely for my own personal reference. But it'd be great if anyone else finds it useful.

The following assumes you're fond of the whole IIFE thing.

```
<!-- YouTube embed will replace the following with iframe -->
<div id="video-blah"></div>
```

```
if (typeof MyApp == 'undefined') {
    window.MyApp = {};
}

// YouTube requires this exactly named function in the global scope
function onYouTubeIframeAPIReady() {
    MyApp.onYouTubeIframeAPIReady();
}

(function() {
    var videoBlah;
    
    // This function will be called when the YoutTube API is ready
    function onYouTubeIframeAPIReady() {
        // This creates and embeds the video
        videoBlah = new window.YT.Player(document.querySelector('#video-blah'), {
            width: '640',
            height: '360',
            videoId: 'dUtQix8nXjo',
            events: {
                // There are other events in the docs
                // https://developers.google.com/youtube/js_api_reference#Events
                'onReady': function(e) {
                    console.log('onReady!');
                    console.log(e);
                },
                'onStateChange': function(e) {
                    console.log('onStateChange!');
                    console.log(e);
                }
            }
        });
    }
    
    // expose the private function above to the global scope
    window.MyApp.onYouTubeIframeAPIReady = onYouTubeIframeAPIReady;
})(window.MyApp);
```
