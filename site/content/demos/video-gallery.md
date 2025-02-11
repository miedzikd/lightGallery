---
title: 'Video gallery'
description:
    'lightGallery supports YouTube, Vimeo, VK, DailyMotion, Wistia and all other
    types of HTML5 video formats. Such as MP4, WebM, Ogg, etc.'
lead:
    'lightGallery supports YouTube, Vimeo, Wistia and all other types of HTML5
    video formats. Such as MP4, WebM, Ogg, etc.'
date: 2020-10-06T08:48:57+00:00
lastmod: 2020-10-06T08:48:57+00:00
draft: false
images: []
menu:
    demos:
        parent: 'Demos'
weight: 2
toc: true
---

##### External videos

<p>To display YouTube, Vimeo and Wistia, videos, you just need to paste the video URL, or share URL of the video in the data-src attribute. The same way you display images in the gallery. lightGallery will check the data-src attribute and if it is a video URL, it will create the respective video slide.</p>

<p>You can also provide poster image for each videos. Poster images will be loaded instead of videos. So user will be able to navigate to other slides by using mouse drag or swipe. Poster images improve performance, and maintain the flexibility of your gallery without effecting user experience. Videos will be loaded when a user clicks on the poster images. You can place poster image url in the data-poster attribute.</p>

<p>lightGallery allows you to load thumbnail images automatically from YouTube and Vimeo. You can specify the size of the thumbnails in the settings. Videos will be automatically paused when a user starts to navigate to another slide.</p>

##### HTML5 videos

<p>For displaying HTML5 videos, you need to construct an object with array of video sources and types, and videos attributes objects as shown below and pass it via data-video attribute</p>
Note - data-src should not be provided when you use html5 videos

```js
{
    source: [
        {
            src: '/videos/video1.mp4',
            type: 'video/mp4',,
        },
        ...
    ],
    attributes: { preload: false, controls: true },
};
```

{{< videos-gallery id="gallery-videos-demo">}}

##### HTML structure

```html
<div id="gallery-videos-demo">
    <!-- YouTube Video --->
    <a
        data-lg-size="1280-720"
        data-src="//www.youtube.com/watch?v=egyIeygdS_E"
        data-poster="https://img.youtube.com/vi/egyIeygdS_E/maxresdefault.jpg"
        data-sub-html="<h4>Visual Soundscapes - Mountains | Planet Earth II | BBC America</h4><p>On the heels of Planet Earth II’s record-breaking Emmy nominations, BBC America presents stunning visual soundscapes from the series' amazing habitats.</p>"
    >
        <img
            width="300"
            height="100"
            class="img-responsive"
            src="https://img.youtube.com/vi/egyIeygdS_E/maxresdefault.jpg"
        />
    </a>

    <!-- VImeo Video --->
    <a
        data-lg-size="1280-720"
        data-src="//vimeo.com/112836958"
        data-poster="/images/demo/vimeo-video-poster.jpg"
        data-sub-html="<h4>Nature</h4><p>Video by <a target='_blank' href='https://vimeo.com/charliekaye'>Charlie Kaye</a></p>"
    >
        <img
            width="300"
            height="100"
            class="img-responsive"
            src="/images/demo/vimeo-video-poster.jpg"
        />
    </a>

    <!-- Wistia Video --->
    <a
        data-lg-size="1280-720"
        data-src="https://private-sharing.wistia.com/medias/mwhrulrucj"
        data-poster="/images/demo/wistia-video-poster.jpeg"
        data-sub-html="<h4>Thank You!</h4><p> Sample Wistia video </p>"
    >
        <img
            width="300"
            height="100"
            class="img-responsive"
            src="/images/demo/wistia-video-poster.jpeg"
        />
    </a>

    <!-- HTML5 Video --->
    <a
        data-lg-size="1280-720"
        data-video='{"source": [{"src":"/videos/video1.mp4", "type":"video/mp4"}], "attributes": {"preload": false, "controls": true}}'
        data-poster="/images/demo/youtube-video-poster.jpg"
        data-sub-html="<h4>'Peck Pocketed' by Kevin Herron | Disney Favorite</h4>"
    >
        <img
            width="300"
            height="100"
            class="img-responsive"
            src="/images/demo/youtube-video-poster.jpg"
        />
    </a>
</div>
```

##### JavaScript

```js
lightGallery(document.getElementById('gallery-videos-demo'));
```

### Videojs example

<a href="https://videojs.com/" target="_blank">Video.js</a> is a web video
player built from the ground up for an HTML5 world. lightGallery has inbuilt
Video.js Support. To enable videojs in lightGallery you just need to pass
`videojs`: `true` via lightGallery settings. You can also pass the videojs
options via `videojsOptions`

Note - Make sure that you pass proper JSON object in data-video attribute

##### Demo

{{< html5-video-gallery id="gallery-videojs-demo">}}

##### HTML structure

```html
<div id="gallery-videojs-demo">
    <a
        data-lg-size="1280-720"
        data-video='{"source": [{"src":"/videos/video1.mp4", "type":"video/mp4"}], "attributes": {"preload": false, "controls": true}}'
        data-poster="/images/demo/youtube-video-poster.jpg"
        data-sub-html="<h4>'Peck Pocketed' by Kevin Herron | Disney Favorite</h4>"
    >
        <img
            width="300"
            height="100"
            class="img-responsive"
            src="/images/demo/youtube-video-poster.jpg"
        />
    </a>
    ...
</div>
```

##### JavaScript

```js
lightGallery(document.getElementById('gallery-videojs-demo'), {
    videojs: true,
    videojsOptions: {
        muted: true,
    },
});
```
