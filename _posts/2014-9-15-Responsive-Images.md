---
layout: post
title: Responsive Images
---

Responsive images are tricky!

```
.banner {
  background-image: url('banner.jpg');
}

@media (-webkit-min-device-pixel-ratio: 1.5), (min-resolution: 192dpi) {
  .banner {
    background-image: url('banner@2x.jpg');
  }
}
```
