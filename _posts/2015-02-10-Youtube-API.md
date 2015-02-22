---
layout: post
title: Quick Guide to Using the YouTube API
---

### Update

I put together a [working demo](https://github.com/jpetto/YouTubeAPIDemo), if you're in to that sort of thing.

***

The [documentation](https://developers.google.com/youtube/js_api_reference) is pretty good, but doesn't provide a simple view of code I have to hunt down and reverse engineer every 3 months or so.

This post is largely for my own personal reference. But it'd be great if anyone else finds it useful.

The following assumes you're fond of the whole IIFE thing.

{% highlight html %}
<!-- YouTube embed will replace the following with iframe -->
<div id="video-blah"></div>
{% endhighlight %}

{% highlight javascript %}
if (typeof MyApp == 'undefined') {
    window.MyApp = {};
}

// YouTube requires this exactly named function in the global scope
function onYouTubeIframeAPIReady() {
    MyApp.onYouTubeIframeAPIReady();
}

(function() {
    var videoBlah;
    
    // Add YouTube API JS
    // call whenever YouTube should be initialized
    var initYouTube = function() {
        var tag = document.createElement('script');

        tag.src = 'https://www.youtube.com/iframe_api';
        var firstScriptTag = document.getElementsByTagName('script')[0];
        firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);
    };
    
    // This function will be called when the YoutTube API is ready
    var onYouTubeIframeAPIReady = function() {
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
    };

    // expose the private function above to the global scope
    window.MyApp.onYouTubeIframeAPIReady = onYouTubeIframeAPIReady;
})(window.MyApp);
{% endhighlight %}
