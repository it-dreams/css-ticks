# css-ticks

### Html Table in Zebra fromat with 3 colors
> HTML
```
<table>
        <tr>
            <td>1</td>
            <td>2</td>
            <td>3</td>
            <td>4</td>
        </tr>
        <tr>
            <td>5</td>
            <td>6</td>
            <td>7</td>
            <td>8</td>
        </tr>
        <tr>
            <td>9</td>
            <td>10</td>
            <td>11</td>
            <td>12</td>
        </tr>
        <tr>
            <td>13</td>
            <td>14</td>
            <td>15</td>
            <td>16</td>
        </tr>
        <tr>
            <td>1</td>
            <td>2</td>
            <td>3</td>
            <td>4</td>
        </tr>
        <tr>
            <td>5</td>
            <td>6</td>
            <td>7</td>
            <td>8</td>
        </tr>
        <tr>
            <td>9</td>
            <td>10</td>
            <td>11</td>
            <td>12</td>
        </tr>
        <tr>
            <td>13</td>
            <td>14</td>
            <td>15</td>
            <td>16</td>
        </tr>
    </table>
   ```

> CSS
```
table tr td {
  border: 1px solid #333;
}

table tr:nth-child(n) {
  background-color: #fff;
  color: #000;
}
table tr:nth-child(2n) {
  background-color: #000;
  color: #fff;
}
table tr:nth-child(3n) {
    background-color: yellow;
    color: #fff;
}
```

> **Flexslide – Media Carousel 
**Stop Video when move to next slide

1. **HTML (artcle-detail.html)
i) Add YouTube API
<script type="text/javascript" src="http://www.youtube.com/player_api"></script>

ii) **Youtube iframe	
<iframe data-type="youtube" id="vid001" src="https://www.youtube.com/embed/FWUNKl3lLhg?rel=0&wmode=Opaque&enablejsapi=1" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

iii). **Video tag	
<video data-type="mp4" id="vid004" poster="./assets/images/RecipeDetailsPageImages/video-poster.jpeg" controls>
src="./assets/images/RecipeDetailsPageImages/demo_video.mp4" type="video/mp4">
src="./assets/images/RecipeDetailsPageImages/demo_video.ogg" type="video/ogg">
support the video tag.
</video>



2. **JS (artcle-detail.js)
```
<script> 
var ytPlayer = []; 
function onYouTubePlayerAPIReady() {
let youtubeVideoLength = $("iframe[data-type='youtube']").length;
for(i=0; i<youtubeVideoLength; i++) {
     videoId = $("iframe[data-type='youtube']").eq(i).attr('id');
     ytPlayer[videoId] = new YT.Player(videoId);
  }
}
</script>
```

3. **JS (carousel.js)
```
before: function(slider) {
        var videoType = $(slider).find('.flex-active-slide     [datatype]').attr('data-type'),
        videoId = $(slider).find('.flex-active-slide [id]').attr('id');
        if(videoType == 'youtube') {
           ytPlayer[videoId].stopVideo();
        } else {
           $('#'+videoId).trigger('pause');
        }
}
```


**Image Border Issue fixed with safari 
```
.band-page-markup2 .img-section{
	position: absolute;
	display: block;
}

.band-page-markup2 .img-section::after {
    position: absolute;
    pointer-events: none;
    top: -1px;
    left: 0;
    right: 0;
    bottom: -1px;
    content: '';
    width: 100%;
    height: 101%;
    background: url(/content/dam/Asia/kelloggs_in/images/icons/imgBorder/border-top.png) repeat-x center top, url(/content/dam/Asia/kelloggs_in/images/icons/imgBorder/border-right.png) repeat-y right center, url(/content/dam/Asia/kelloggs_in/images/icons/imgBorder/border-bottom.png) repeat-x center bottom, url(/content/dam/Asia/kelloggs_in/images/icons/imgBorder/border-left.png) repeat-y left center;
} 
```

**Image Border Issue fixed with safari 
```
/* safari (Replace with Old) */
_::-webkit-full-page-media,
_:future,
:root .mediacarouselcomp .flex-viewport ul.slides li > div img,
:root .mediacarouselcomp .flex-viewport ul.slides li > div iframe {
  top: 1px;
  left: 1px;
  right: 1px;
  bottom: 1px;
  width: 99%;
  height: 99%;
}
```

**Image Border Issue fixed with FireFox 
```
/* Mozila (Replace  with Old) */
@media screen and (-webkit-min-device-pixel-ratio:0) and (min-resolution:.001dpcm) {
  .mediacarouselcomp .flex-viewport ul.slides li > div img,
  .mediacarouselcomp .flex-viewport ul.slides li > div iframe {
    top: 1px !important;;
    bottom: 1px !important;;
    height: 99% !important;;
  }

  .markuptext .article-50-50-img-section table tr td::after,
  .edenmediacarousel .article-slider-holder .flex-viewport .article-video-list::after,
  .mediacarouselcomp .flex-viewport ul.slides li > div > div::after,
  .band-page-markup2 .img-section::after {
    left: -1px;
    right: -1px;
    width: 101%;
  }
  .edenrecipelist .recipe-list .recipe-list-item a:first-of-type::after {
    top: -1px;
    left: -1px;
    right: -1px;
    bottom: -1px;
    width: 101%;
    height: 101%;
  }
}		
```
