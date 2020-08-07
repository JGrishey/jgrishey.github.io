---
layout: post
title:  "How to use Feather's icons with Stimulus"
date:   2020-08-06 21:14:00 -0400
categories: posts
---

Hey folks,

I have been playing around with Stimulus lately and one of the icon packages that I use on a lot of my projects is [Feather](https://github.com/feathericons/feather) icons by Cole Bemis.

Getting these icons to work with Stimulus is actually pretty easy:

1. Install Stimulus. If you don't know how to do this, the people over at Basecamp/Rails have done a great job explaining the framework and installation process [here](https://stimulusjs.org/handbook/introduction).

2. Set up a Stimulus controller to watch for `<i>` tags:

```javascript
// controllers/feather_controller.js
import { Controller } from "stimulus"
import feather from "feather-icons"

export default class extends Controller {
  connect() {
    feather.replace()
  }
}
```

3. That's it! Now you can use `<i>` tags in your HTML like so:

```html
<body>
...
  <i data-controller="feather" data-feather="icon-name"></i>
...
</body>
```

And Stimulus/Feather will automatically populate the icon with an SVG!

Check out the Stimulus [docs](https://github.com/stimulusjs/stimulus) and Feather [docs](https://github.com/feathericons/feather) for more options.
