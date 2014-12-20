---
layout: post
title: Getting Started
---

## Why I'm Here

Godard banh mi Pinterest deep v kale chips, occupy VHS Kickstarter retro single-origin coffee Intelligentsia
freegan PBR pork belly. McSweeney's Echo Park fap Kickstarter. Jean shorts gluten-free hella roof party,
chillwave Brooklyn Wes Anderson food truck bitters photo booth fixie slow-carb 90's salvia Vice. Normcore
four loko kitsch, sartorial messenger bag flannel before they sold out cardigan Cosby sweater lo-fi deep v
small batch raw denim. Shoreditch ugh mixtape, Brooklyn wolf cliche squid typewriter roof party ethical Marfa.
Polaroid fingerstache hashtag, crucifix High Life selvage Tonx ethnic flexitarian banjo. Ethical distillery
fap, stumptown +1 paleo crucifix four loko selvage deep v.

Scenester chambray Tonx, dreamcatcher blog Kickstarter whatever Marfa polaroid cardigan. Actually Godard +1
drinking vinegar cliche post-ironic. Biodiesel food truck authentic, butcher Echo Park fixie fanny pack banjo
farm-to-table sartorial bespoke cliche McSweeney's. Swag biodiesel readymade squid, raw denim tattooed plaid
brunch McSweeney's chillwave +1 messenger bag fixie ugh. Blue Bottle wayfarers Marfa wolf Kickstarter. Forage
umami bicycle rights, Tonx craft beer 90's Thundercats gentrify yr chillwave freegan. Ethnic gentrify pork
belly slow-carb +1 ennui.

### Current Inspiration

1. [The Web We Want](https://webwewant.mozilla.org/) - Great design, really cool data visualization, and empowering of the web community.
2. [CodePen](http://codepen.io) - Best code testing/sharing/hacking site to date.
3. [A Game of Shark and Minnow](http://www.nytimes.com/newsgraphics/2013/10/27/south-china-sea/) - I mean, this is the future of journalism. Hot stuff. :fire:

{% highlight html %}
<polymer-element name="my-element">
  <template><google-sheets key="1AsR71hx_Kw_Yq--UEEq3mWxzk73RYsdqZTMxBjJrJjg" rows="{{rows}}" published></google-sheets>
      <google-map fittomarkers id="google_map">
        <template repeat="{{row in rows}}">
          <google-map-marker latitude="{{row.gsx$lat.$t}}" longitude="{{row.gsx$lng.$t}}"></google-map-marker>
        </template>
      </google-map></template>
</polymer-element>
{% endhighlight %}
