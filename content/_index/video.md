+++
#fragment = "embed"
fragment = "content"
#disabled = false
date = "2017-09-09"
weight = 110
background = "light"

title = ""
#subtitle = "Easily embed media (videos, iframes etc.)"
#title_align = "left" # Default is center, can be left, right or center
#media_source = "https://www.youtube.com/embed/MMXbrxOQwC8"
#media = '<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/MMXbrxOQwC8?rel=0&amp;showinfo=0" allowfullscreen></iframe>'
ratio = "16by9" # 21by9, 16by9, 4by3, 1by1 - Default: 4by3
#size = "100" # 25, 50, 75, 100 (percentage) - default: 75
+++
<style>    .youtube-player {        position: relative;        padding-bottom: 56.23%;        /* Use 75% for 4:3 videos */        height: 0;        overflow: hidden;        max-width: 100%;        background: #000;        margin: 5px;    }        .youtube-player iframe {        position: absolute;        top: 0;        left: 0;        width: 100%;        height: 100%;        z-index: 100;        background: transparent;    }        .youtube-player img {        bottom: 0;        display: block;        left: 0;        margin: auto;        max-width: 100%;        width: 100%;        position: absolute;        right: 0;        top: 0;        border: none;        height: auto;        cursor: pointer;        -webkit-transition: .4s all;        -moz-transition: .4s all;        transition: .4s all;    }        .youtube-player img:hover {        -webkit-filter: brightness(75%);    }        .youtube-player .play {        height: 72px;        width: 72px;        left: 50%;        top: 50%;        margin-left: -36px;        margin-top: -36px;        position: absolute;        background: url("//i.imgur.com/TxzC70f.png") no-repeat;        cursor: pointer;    }</style>

<script>    /* Light YouTube Embeds by @labnol */    /* Web: http://labnol.org/?p=27941 */    document.addEventListener("DOMContentLoaded",        function() {            var div, n,                v = document.getElementsByClassName("youtube-player");            for (n = 0; n < v.length; n++) {                div = document.createElement("div");                div.setAttribute("data-id", v[n].dataset.id);                div.innerHTML = labnolThumb(v[n].dataset.id);                div.onclick = labnolIframe;                v[n].appendChild(div);            }        });    function labnolThumb(id) {        var thumb = '<img src="https://i.ytimg.com/vi/ID/sddefault.jpg">',            play = '<div class="play"></div>';        return thumb.replace("ID", id) + play;    }    function labnolIframe() {        var iframe = document.createElement("iframe");        var embed = "https://www.youtube.com/embed/ID?autoplay=1";        iframe.setAttribute("src", embed.replace("ID", this.dataset.id));        iframe.setAttribute("frameborder", "0");        iframe.setAttribute("allowfullscreen", "1");        this.parentNode.replaceChild(iframe, this);    }</script>

<div class="youtube-player" data-id="MMXbrxOQwC8"></div> 