--- layout: post title: HTML5 study notes date: 2011-10-19 16:08:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: www.ashang.org blogger\_author: Aaron Shang blogger\_d06f7f5bcdfeb296283c00dcf750b675\_permalink: '1251469331774787470' \_oembed\_1686bbedd9d0c1e189205d8649b808bf: "{{unknown}}" author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

HTML5 learning notes

 

HTML5 ~= HTML + CSS + JS
<a href="http://slides.html5rocks.com/" class="ot-anchor">http://slides.html5rocks.com</a>

 

<a href="http://slides.html5rocks.com/" class="ot-anchor B-u-Y-j">HTML5 Presentation</a>

 

 

<span class="QD"></span>Web Storage
// use localStorage for persistent storage
// use sessionStorage for per tab storage

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:07:25 AM"> </span></span>

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:07:25 AM"> </span></span>

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:07:25 AM"> </span></span>

<span class="QD"></span>Web SQL Database
var db = window.openDatabase("DBName", "1.0", "description", 5\*1024\*1024); //5MB
db.transaction(function(tx) {
tx.executeSql("SELECT \* FROM test", \[\], successCallback, errorCallback);
});

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:08:48 AM"> </span></span>

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:08:48 AM"> </span></span>

<span class="zj"> </span>

<span class="zj">IndexedDB</span>

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:08:56 AM"></span></span>

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:08:56 AM">
</span></span>

wss://<a href="http://html5rocks.websocket.org/echo" class="ot-anchor">html5rocks.websocket.org/echo</a>
Error:Your browser does not have native support for WebSocket
Build identifier: Mozilla/5.0 (X11; Linux x86\_64; rv:6.0.2) Gecko/20100101 Firefox/6.0.2

about:buildconfig

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:10:08 AM (edited Sep 19, 2011 11:11:07 AM)"> </span></span>

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:10:08 AM (edited Sep 19, 2011 11:11:07 AM)"> </span></span>

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:10:08 AM (edited Sep 19, 2011 11:11:07 AM)"> </span></span>

File / Hardware Access Deeper integration with the Operating System
Native Drag & Drop
Desktop Drag-In (File API) / Drag-Out
Asynchronously write a file to a sandboxed file system using JavaScript
Geolocation
Device Orientation

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:14:39 AM"> </span></span>

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:14:39 AM"> </span></span>

Semantics & Markup
More meaningful elements
Markup for applications
working...
3/4 complete
Microdata
New form types
Form field types on mobile -- Input / Keyboard sensitive

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:17:36 AM"> </span></span>

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:17:36 AM"> </span></span>

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:17:36 AM"> </span></span>

<span class="QD"></span>Graphics / Multimedia 2D & 3D
Audio + Video
Canvas 2D
Canvas 3D (WebGL)
Inline SVG
&lt;circle
fill="url(\#myGradient)"
onmousedown="alert('hello');"/&gt;

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:18:37 AM"> </span></span>

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:18:37 AM"> </span></span>

<span class="Lm"><span class="hl" title="Sep 19, 2011 11:18:37 AM"> </span></span>

<span class="QD"></span>CSS3 Presentation & Styling
CSS Selectors:
.row:nth-child(even) {
background: \#dde;
}
Webfonts
@font-face{
font-family: 'LeagueGothic';
src: url(LeagueGothic.otf);
}

@font-face{
font-family: 'Droid Sans';
src: url(Droid\_Sans.ttf);
}

Text wrapping
Text stroke
Columns
Opacity
Transitions
Animations
~~~ ...
