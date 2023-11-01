# MSDS 458 Bird Classification
 

<!DOCTYPE html>
<!-- saved from url=(0141)https://htmtopdf.herokuapp.com/ipynbviewer/temp/76b2494a59eaa356c37baa3190c2ff46/CNN_V6_MSDS_458_Image_Classification_NN.html?t=1692251437780 -->
<html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">

<title>CNN_V6_MSDS_458_Image_Classification_NN</title>

<script src="./CNN_V6_MSDS_458_Image_Classification_NN_files/require.min.js.download"></script>
<script src="./CNN_V6_MSDS_458_Image_Classification_NN_files/jquery.min.js.download"></script>



<style type="text/css">
    /*!
*
* Twitter Bootstrap
*
*/
/*!
 * Bootstrap v3.3.7 (http://getbootstrap.com)
 * Copyright 2011-2016 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */
/*! normalize.css v3.0.3 | MIT License | github.com/necolas/normalize.css */
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  margin: 0;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
main,
menu,
nav,
section,
summary {
  display: block;
}
audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden],
template {
  display: none;
}
a {
  background-color: transparent;
}
a:active,
a:hover {
  outline: 0;
}
abbr[title] {
  border-bottom: 1px dotted;
}
b,
strong {
  font-weight: bold;
}
dfn {
  font-style: italic;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
mark {
  background: #ff0;
  color: #000;
}
small {
  font-size: 80%;
}
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
sup {
  top: -0.5em;
}
sub {
  bottom: -0.25em;
}
img {
  border: 0;
}
svg:not(:root) {
  overflow: hidden;
}
figure {
  margin: 1em 40px;
}
hr {
  box-sizing: content-box;
  height: 0;
}
pre {
  overflow: auto;
}
code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 1em;
}
button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}
button {
  overflow: visible;
}
button,
select {
  text-transform: none;
}
button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}
button[disabled],
html input[disabled] {
  cursor: default;
}
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
input {
  line-height: normal;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: textfield;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
}
optgroup {
  font-weight: bold;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}
/*! Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */
@media print {
  *,
  *:before,
  *:after {
    background: transparent !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }
  a,
  a:visited {
    text-decoration: underline;
  }
  a[href]:after {
    content: " (" attr(href) ")";
  }
  abbr[title]:after {
    content: " (" attr(title) ")";
  }
  a[href^="#"]:after,
  a[href^="javascript:"]:after {
    content: "";
  }
  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }
  thead {
    display: table-header-group;
  }
  tr,
  img {
    page-break-inside: avoid;
  }
  img {
    max-width: 100% !important;
  }
  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }
  h2,
  h3 {
    page-break-after: avoid;
  }
  .navbar {
    display: none;
  }
  .btn > .caret,
  .dropup > .btn > .caret {
    border-top-color: #000 !important;
  }
  .label {
    border: 1px solid #000;
  }
  .table {
    border-collapse: collapse !important;
  }
  .table td,
  .table th {
    background-color: #fff !important;
  }
  .table-bordered th,
  .table-bordered td {
    border: 1px solid #ddd !important;
  }
}
@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot');
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff2') format('woff2'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff') format('woff'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
.glyphicon {
  position: relative;
  top: 1px;
  display: inline-block;
  font-family: 'Glyphicons Halflings';
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.glyphicon-asterisk:before {
  content: "\002a";
}
.glyphicon-plus:before {
  content: "\002b";
}
.glyphicon-euro:before,
.glyphicon-eur:before {
  content: "\20ac";
}
.glyphicon-minus:before {
  content: "\2212";
}
.glyphicon-cloud:before {
  content: "\2601";
}
.glyphicon-envelope:before {
  content: "\2709";
}
.glyphicon-pencil:before {
  content: "\270f";
}
.glyphicon-glass:before {
  content: "\e001";
}
.glyphicon-music:before {
  content: "\e002";
}
.glyphicon-search:before {
  content: "\e003";
}
.glyphicon-heart:before {
  content: "\e005";
}
.glyphicon-star:before {
  content: "\e006";
}
.glyphicon-star-empty:before {
  content: "\e007";
}
.glyphicon-user:before {
  content: "\e008";
}
.glyphicon-film:before {
  content: "\e009";
}
.glyphicon-th-large:before {
  content: "\e010";
}
.glyphicon-th:before {
  content: "\e011";
}
.glyphicon-th-list:before {
  content: "\e012";
}
.glyphicon-ok:before {
  content: "\e013";
}
.glyphicon-remove:before {
  content: "\e014";
}
.glyphicon-zoom-in:before {
  content: "\e015";
}
.glyphicon-zoom-out:before {
  content: "\e016";
}
.glyphicon-off:before {
  content: "\e017";
}
.glyphicon-signal:before {
  content: "\e018";
}
.glyphicon-cog:before {
  content: "\e019";
}
.glyphicon-trash:before {
  content: "\e020";
}
.glyphicon-home:before {
  content: "\e021";
}
.glyphicon-file:before {
  content: "\e022";
}
.glyphicon-time:before {
  content: "\e023";
}
.glyphicon-road:before {
  content: "\e024";
}
.glyphicon-download-alt:before {
  content: "\e025";
}
.glyphicon-download:before {
  content: "\e026";
}
.glyphicon-upload:before {
  content: "\e027";
}
.glyphicon-inbox:before {
  content: "\e028";
}
.glyphicon-play-circle:before {
  content: "\e029";
}
.glyphicon-repeat:before {
  content: "\e030";
}
.glyphicon-refresh:before {
  content: "\e031";
}
.glyphicon-list-alt:before {
  content: "\e032";
}
.glyphicon-lock:before {
  content: "\e033";
}
.glyphicon-flag:before {
  content: "\e034";
}
.glyphicon-headphones:before {
  content: "\e035";
}
.glyphicon-volume-off:before {
  content: "\e036";
}
.glyphicon-volume-down:before {
  content: "\e037";
}
.glyphicon-volume-up:before {
  content: "\e038";
}
.glyphicon-qrcode:before {
  content: "\e039";
}
.glyphicon-barcode:before {
  content: "\e040";
}
.glyphicon-tag:before {
  content: "\e041";
}
.glyphicon-tags:before {
  content: "\e042";
}
.glyphicon-book:before {
  content: "\e043";
}
.glyphicon-bookmark:before {
  content: "\e044";
}
.glyphicon-print:before {
  content: "\e045";
}
.glyphicon-camera:before {
  content: "\e046";
}
.glyphicon-font:before {
  content: "\e047";
}
.glyphicon-bold:before {
  content: "\e048";
}
.glyphicon-italic:before {
  content: "\e049";
}
.glyphicon-text-height:before {
  content: "\e050";
}
.glyphicon-text-width:before {
  content: "\e051";
}
.glyphicon-align-left:before {
  content: "\e052";
}
.glyphicon-align-center:before {
  content: "\e053";
}
.glyphicon-align-right:before {
  content: "\e054";
}
.glyphicon-align-justify:before {
  content: "\e055";
}
.glyphicon-list:before {
  content: "\e056";
}
.glyphicon-indent-left:before {
  content: "\e057";
}
.glyphicon-indent-right:before {
  content: "\e058";
}
.glyphicon-facetime-video:before {
  content: "\e059";
}
.glyphicon-picture:before {
  content: "\e060";
}
.glyphicon-map-marker:before {
  content: "\e062";
}
.glyphicon-adjust:before {
  content: "\e063";
}
.glyphicon-tint:before {
  content: "\e064";
}
.glyphicon-edit:before {
  content: "\e065";
}
.glyphicon-share:before {
  content: "\e066";
}
.glyphicon-check:before {
  content: "\e067";
}
.glyphicon-move:before {
  content: "\e068";
}
.glyphicon-step-backward:before {
  content: "\e069";
}
.glyphicon-fast-backward:before {
  content: "\e070";
}
.glyphicon-backward:before {
  content: "\e071";
}
.glyphicon-play:before {
  content: "\e072";
}
.glyphicon-pause:before {
  content: "\e073";
}
.glyphicon-stop:before {
  content: "\e074";
}
.glyphicon-forward:before {
  content: "\e075";
}
.glyphicon-fast-forward:before {
  content: "\e076";
}
.glyphicon-step-forward:before {
  content: "\e077";
}
.glyphicon-eject:before {
  content: "\e078";
}
.glyphicon-chevron-left:before {
  content: "\e079";
}
.glyphicon-chevron-right:before {
  content: "\e080";
}
.glyphicon-plus-sign:before {
  content: "\e081";
}
.glyphicon-minus-sign:before {
  content: "\e082";
}
.glyphicon-remove-sign:before {
  content: "\e083";
}
.glyphicon-ok-sign:before {
  content: "\e084";
}
.glyphicon-question-sign:before {
  content: "\e085";
}
.glyphicon-info-sign:before {
  content: "\e086";
}
.glyphicon-screenshot:before {
  content: "\e087";
}
.glyphicon-remove-circle:before {
  content: "\e088";
}
.glyphicon-ok-circle:before {
  content: "\e089";
}
.glyphicon-ban-circle:before {
  content: "\e090";
}
.glyphicon-arrow-left:before {
  content: "\e091";
}
.glyphicon-arrow-right:before {
  content: "\e092";
}
.glyphicon-arrow-up:before {
  content: "\e093";
}
.glyphicon-arrow-down:before {
  content: "\e094";
}
.glyphicon-share-alt:before {
  content: "\e095";
}
.glyphicon-resize-full:before {
  content: "\e096";
}
.glyphicon-resize-small:before {
  content: "\e097";
}
.glyphicon-exclamation-sign:before {
  content: "\e101";
}
.glyphicon-gift:before {
  content: "\e102";
}
.glyphicon-leaf:before {
  content: "\e103";
}
.glyphicon-fire:before {
  content: "\e104";
}
.glyphicon-eye-open:before {
  content: "\e105";
}
.glyphicon-eye-close:before {
  content: "\e106";
}
.glyphicon-warning-sign:before {
  content: "\e107";
}
.glyphicon-plane:before {
  content: "\e108";
}
.glyphicon-calendar:before {
  content: "\e109";
}
.glyphicon-random:before {
  content: "\e110";
}
.glyphicon-comment:before {
  content: "\e111";
}
.glyphicon-magnet:before {
  content: "\e112";
}
.glyphicon-chevron-up:before {
  content: "\e113";
}
.glyphicon-chevron-down:before {
  content: "\e114";
}
.glyphicon-retweet:before {
  content: "\e115";
}
.glyphicon-shopping-cart:before {
  content: "\e116";
}
.glyphicon-folder-close:before {
  content: "\e117";
}
.glyphicon-folder-open:before {
  content: "\e118";
}
.glyphicon-resize-vertical:before {
  content: "\e119";
}
.glyphicon-resize-horizontal:before {
  content: "\e120";
}
.glyphicon-hdd:before {
  content: "\e121";
}
.glyphicon-bullhorn:before {
  content: "\e122";
}
.glyphicon-bell:before {
  content: "\e123";
}
.glyphicon-certificate:before {
  content: "\e124";
}
.glyphicon-thumbs-up:before {
  content: "\e125";
}
.glyphicon-thumbs-down:before {
  content: "\e126";
}
.glyphicon-hand-right:before {
  content: "\e127";
}
.glyphicon-hand-left:before {
  content: "\e128";
}
.glyphicon-hand-up:before {
  content: "\e129";
}
.glyphicon-hand-down:before {
  content: "\e130";
}
.glyphicon-circle-arrow-right:before {
  content: "\e131";
}
.glyphicon-circle-arrow-left:before {
  content: "\e132";
}
.glyphicon-circle-arrow-up:before {
  content: "\e133";
}
.glyphicon-circle-arrow-down:before {
  content: "\e134";
}
.glyphicon-globe:before {
  content: "\e135";
}
.glyphicon-wrench:before {
  content: "\e136";
}
.glyphicon-tasks:before {
  content: "\e137";
}
.glyphicon-filter:before {
  content: "\e138";
}
.glyphicon-briefcase:before {
  content: "\e139";
}
.glyphicon-fullscreen:before {
  content: "\e140";
}
.glyphicon-dashboard:before {
  content: "\e141";
}
.glyphicon-paperclip:before {
  content: "\e142";
}
.glyphicon-heart-empty:before {
  content: "\e143";
}
.glyphicon-link:before {
  content: "\e144";
}
.glyphicon-phone:before {
  content: "\e145";
}
.glyphicon-pushpin:before {
  content: "\e146";
}
.glyphicon-usd:before {
  content: "\e148";
}
.glyphicon-gbp:before {
  content: "\e149";
}
.glyphicon-sort:before {
  content: "\e150";
}
.glyphicon-sort-by-alphabet:before {
  content: "\e151";
}
.glyphicon-sort-by-alphabet-alt:before {
  content: "\e152";
}
.glyphicon-sort-by-order:before {
  content: "\e153";
}
.glyphicon-sort-by-order-alt:before {
  content: "\e154";
}
.glyphicon-sort-by-attributes:before {
  content: "\e155";
}
.glyphicon-sort-by-attributes-alt:before {
  content: "\e156";
}
.glyphicon-unchecked:before {
  content: "\e157";
}
.glyphicon-expand:before {
  content: "\e158";
}
.glyphicon-collapse-down:before {
  content: "\e159";
}
.glyphicon-collapse-up:before {
  content: "\e160";
}
.glyphicon-log-in:before {
  content: "\e161";
}
.glyphicon-flash:before {
  content: "\e162";
}
.glyphicon-log-out:before {
  content: "\e163";
}
.glyphicon-new-window:before {
  content: "\e164";
}
.glyphicon-record:before {
  content: "\e165";
}
.glyphicon-save:before {
  content: "\e166";
}
.glyphicon-open:before {
  content: "\e167";
}
.glyphicon-saved:before {
  content: "\e168";
}
.glyphicon-import:before {
  content: "\e169";
}
.glyphicon-export:before {
  content: "\e170";
}
.glyphicon-send:before {
  content: "\e171";
}
.glyphicon-floppy-disk:before {
  content: "\e172";
}
.glyphicon-floppy-saved:before {
  content: "\e173";
}
.glyphicon-floppy-remove:before {
  content: "\e174";
}
.glyphicon-floppy-save:before {
  content: "\e175";
}
.glyphicon-floppy-open:before {
  content: "\e176";
}
.glyphicon-credit-card:before {
  content: "\e177";
}
.glyphicon-transfer:before {
  content: "\e178";
}
.glyphicon-cutlery:before {
  content: "\e179";
}
.glyphicon-header:before {
  content: "\e180";
}
.glyphicon-compressed:before {
  content: "\e181";
}
.glyphicon-earphone:before {
  content: "\e182";
}
.glyphicon-phone-alt:before {
  content: "\e183";
}
.glyphicon-tower:before {
  content: "\e184";
}
.glyphicon-stats:before {
  content: "\e185";
}
.glyphicon-sd-video:before {
  content: "\e186";
}
.glyphicon-hd-video:before {
  content: "\e187";
}
.glyphicon-subtitles:before {
  content: "\e188";
}
.glyphicon-sound-stereo:before {
  content: "\e189";
}
.glyphicon-sound-dolby:before {
  content: "\e190";
}
.glyphicon-sound-5-1:before {
  content: "\e191";
}
.glyphicon-sound-6-1:before {
  content: "\e192";
}
.glyphicon-sound-7-1:before {
  content: "\e193";
}
.glyphicon-copyright-mark:before {
  content: "\e194";
}
.glyphicon-registration-mark:before {
  content: "\e195";
}
.glyphicon-cloud-download:before {
  content: "\e197";
}
.glyphicon-cloud-upload:before {
  content: "\e198";
}
.glyphicon-tree-conifer:before {
  content: "\e199";
}
.glyphicon-tree-deciduous:before {
  content: "\e200";
}
.glyphicon-cd:before {
  content: "\e201";
}
.glyphicon-save-file:before {
  content: "\e202";
}
.glyphicon-open-file:before {
  content: "\e203";
}
.glyphicon-level-up:before {
  content: "\e204";
}
.glyphicon-copy:before {
  content: "\e205";
}
.glyphicon-paste:before {
  content: "\e206";
}
.glyphicon-alert:before {
  content: "\e209";
}
.glyphicon-equalizer:before {
  content: "\e210";
}
.glyphicon-king:before {
  content: "\e211";
}
.glyphicon-queen:before {
  content: "\e212";
}
.glyphicon-pawn:before {
  content: "\e213";
}
.glyphicon-bishop:before {
  content: "\e214";
}
.glyphicon-knight:before {
  content: "\e215";
}
.glyphicon-baby-formula:before {
  content: "\e216";
}
.glyphicon-tent:before {
  content: "\26fa";
}
.glyphicon-blackboard:before {
  content: "\e218";
}
.glyphicon-bed:before {
  content: "\e219";
}
.glyphicon-apple:before {
  content: "\f8ff";
}
.glyphicon-erase:before {
  content: "\e221";
}
.glyphicon-hourglass:before {
  content: "\231b";
}
.glyphicon-lamp:before {
  content: "\e223";
}
.glyphicon-duplicate:before {
  content: "\e224";
}
.glyphicon-piggy-bank:before {
  content: "\e225";
}
.glyphicon-scissors:before {
  content: "\e226";
}
.glyphicon-bitcoin:before {
  content: "\e227";
}
.glyphicon-btc:before {
  content: "\e227";
}
.glyphicon-xbt:before {
  content: "\e227";
}
.glyphicon-yen:before {
  content: "\00a5";
}
.glyphicon-jpy:before {
  content: "\00a5";
}
.glyphicon-ruble:before {
  content: "\20bd";
}
.glyphicon-rub:before {
  content: "\20bd";
}
.glyphicon-scale:before {
  content: "\e230";
}
.glyphicon-ice-lolly:before {
  content: "\e231";
}
.glyphicon-ice-lolly-tasted:before {
  content: "\e232";
}
.glyphicon-education:before {
  content: "\e233";
}
.glyphicon-option-horizontal:before {
  content: "\e234";
}
.glyphicon-option-vertical:before {
  content: "\e235";
}
.glyphicon-menu-hamburger:before {
  content: "\e236";
}
.glyphicon-modal-window:before {
  content: "\e237";
}
.glyphicon-oil:before {
  content: "\e238";
}
.glyphicon-grain:before {
  content: "\e239";
}
.glyphicon-sunglasses:before {
  content: "\e240";
}
.glyphicon-text-size:before {
  content: "\e241";
}
.glyphicon-text-color:before {
  content: "\e242";
}
.glyphicon-text-background:before {
  content: "\e243";
}
.glyphicon-object-align-top:before {
  content: "\e244";
}
.glyphicon-object-align-bottom:before {
  content: "\e245";
}
.glyphicon-object-align-horizontal:before {
  content: "\e246";
}
.glyphicon-object-align-left:before {
  content: "\e247";
}
.glyphicon-object-align-vertical:before {
  content: "\e248";
}
.glyphicon-object-align-right:before {
  content: "\e249";
}
.glyphicon-triangle-right:before {
  content: "\e250";
}
.glyphicon-triangle-left:before {
  content: "\e251";
}
.glyphicon-triangle-bottom:before {
  content: "\e252";
}
.glyphicon-triangle-top:before {
  content: "\e253";
}
.glyphicon-console:before {
  content: "\e254";
}
.glyphicon-superscript:before {
  content: "\e255";
}
.glyphicon-subscript:before {
  content: "\e256";
}
.glyphicon-menu-left:before {
  content: "\e257";
}
.glyphicon-menu-right:before {
  content: "\e258";
}
.glyphicon-menu-down:before {
  content: "\e259";
}
.glyphicon-menu-up:before {
  content: "\e260";
}
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
html {
  font-size: 10px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  line-height: 1.42857143;
  color: #000;
  background-color: #fff;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
a {
  color: #337ab7;
  text-decoration: none;
}
a:hover,
a:focus {
  color: #23527c;
  text-decoration: underline;
}
a:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
figure {
  margin: 0;
}
img {
  vertical-align: middle;
}
.img-responsive,
.thumbnail > img,
.thumbnail a > img,
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  display: block;
  max-width: 100%;
  height: auto;
}
.img-rounded {
  border-radius: 3px;
}
.img-thumbnail {
  padding: 4px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  max-width: 100%;
  height: auto;
}
.img-circle {
  border-radius: 50%;
}
hr {
  margin-top: 18px;
  margin-bottom: 18px;
  border: 0;
  border-top: 1px solid #eeeeee;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
[role="button"] {
  cursor: pointer;
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
}
h1 small,
h2 small,
h3 small,
h4 small,
h5 small,
h6 small,
.h1 small,
.h2 small,
.h3 small,
.h4 small,
.h5 small,
.h6 small,
h1 .small,
h2 .small,
h3 .small,
h4 .small,
h5 .small,
h6 .small,
.h1 .small,
.h2 .small,
.h3 .small,
.h4 .small,
.h5 .small,
.h6 .small {
  font-weight: normal;
  line-height: 1;
  color: #777777;
}
h1,
.h1,
h2,
.h2,
h3,
.h3 {
  margin-top: 18px;
  margin-bottom: 9px;
}
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 9px;
  margin-bottom: 9px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
h1,
.h1 {
  font-size: 33px;
}
h2,
.h2 {
  font-size: 27px;
}
h3,
.h3 {
  font-size: 23px;
}
h4,
.h4 {
  font-size: 17px;
}
h5,
.h5 {
  font-size: 13px;
}
h6,
.h6 {
  font-size: 12px;
}
p {
  margin: 0 0 9px;
}
.lead {
  margin-bottom: 18px;
  font-size: 14px;
  font-weight: 300;
  line-height: 1.4;
}
@media (min-width: 768px) {
  .lead {
    font-size: 19.5px;
  }
}
small,
.small {
  font-size: 92%;
}
mark,
.mark {
  background-color: #fcf8e3;
  padding: .2em;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.text-center {
  text-align: center;
}
.text-justify {
  text-align: justify;
}
.text-nowrap {
  white-space: nowrap;
}
.text-lowercase {
  text-transform: lowercase;
}
.text-uppercase {
  text-transform: uppercase;
}
.text-capitalize {
  text-transform: capitalize;
}
.text-muted {
  color: #777777;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.text-success {
  color: #3c763d;
}
a.text-success:hover,
a.text-success:focus {
  color: #2b542c;
}
.text-info {
  color: #31708f;
}
a.text-info:hover,
a.text-info:focus {
  color: #245269;
}
.text-warning {
  color: #8a6d3b;
}
a.text-warning:hover,
a.text-warning:focus {
  color: #66512c;
}
.text-danger {
  color: #a94442;
}
a.text-danger:hover,
a.text-danger:focus {
  color: #843534;
}
.bg-primary {
  color: #fff;
  background-color: #337ab7;
}
a.bg-primary:hover,
a.bg-primary:focus {
  background-color: #286090;
}
.bg-success {
  background-color: #dff0d8;
}
a.bg-success:hover,
a.bg-success:focus {
  background-color: #c1e2b3;
}
.bg-info {
  background-color: #d9edf7;
}
a.bg-info:hover,
a.bg-info:focus {
  background-color: #afd9ee;
}
.bg-warning {
  background-color: #fcf8e3;
}
a.bg-warning:hover,
a.bg-warning:focus {
  background-color: #f7ecb5;
}
.bg-danger {
  background-color: #f2dede;
}
a.bg-danger:hover,
a.bg-danger:focus {
  background-color: #e4b9b9;
}
.page-header {
  padding-bottom: 8px;
  margin: 36px 0 18px;
  border-bottom: 1px solid #eeeeee;
}
ul,
ol {
  margin-top: 0;
  margin-bottom: 9px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}
.list-unstyled {
  padding-left: 0;
  list-style: none;
}
.list-inline {
  padding-left: 0;
  list-style: none;
  margin-left: -5px;
}
.list-inline > li {
  display: inline-block;
  padding-left: 5px;
  padding-right: 5px;
}
dl {
  margin-top: 0;
  margin-bottom: 18px;
}
dt,
dd {
  line-height: 1.42857143;
}
dt {
  font-weight: bold;
}
dd {
  margin-left: 0;
}
@media (min-width: 541px) {
  .dl-horizontal dt {
    float: left;
    width: 160px;
    clear: left;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .dl-horizontal dd {
    margin-left: 180px;
  }
}
abbr[title],
abbr[data-original-title] {
  cursor: help;
  border-bottom: 1px dotted #777777;
}
.initialism {
  font-size: 90%;
  text-transform: uppercase;
}
blockquote {
  padding: 9px 18px;
  margin: 0 0 18px;
  font-size: inherit;
  border-left: 5px solid #eeeeee;
}
blockquote p:last-child,
blockquote ul:last-child,
blockquote ol:last-child {
  margin-bottom: 0;
}
blockquote footer,
blockquote small,
blockquote .small {
  display: block;
  font-size: 80%;
  line-height: 1.42857143;
  color: #777777;
}
blockquote footer:before,
blockquote small:before,
blockquote .small:before {
  content: '\2014 \00A0';
}
.blockquote-reverse,
blockquote.pull-right {
  padding-right: 15px;
  padding-left: 0;
  border-right: 5px solid #eeeeee;
  border-left: 0;
  text-align: right;
}
.blockquote-reverse footer:before,
blockquote.pull-right footer:before,
.blockquote-reverse small:before,
blockquote.pull-right small:before,
.blockquote-reverse .small:before,
blockquote.pull-right .small:before {
  content: '';
}
.blockquote-reverse footer:after,
blockquote.pull-right footer:after,
.blockquote-reverse small:after,
blockquote.pull-right small:after,
.blockquote-reverse .small:after,
blockquote.pull-right .small:after {
  content: '\00A0 \2014';
}
address {
  margin-bottom: 18px;
  font-style: normal;
  line-height: 1.42857143;
}
code,
kbd,
pre,
samp {
  font-family: monospace;
}
code {
  padding: 2px 4px;
  font-size: 90%;
  color: #c7254e;
  background-color: #f9f2f4;
  border-radius: 2px;
}
kbd {
  padding: 2px 4px;
  font-size: 90%;
  color: #888;
  background-color: transparent;
  border-radius: 1px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
}
kbd kbd {
  padding: 0;
  font-size: 100%;
  font-weight: bold;
  box-shadow: none;
}
pre {
  display: block;
  padding: 8.5px;
  margin: 0 0 9px;
  font-size: 12px;
  line-height: 1.42857143;
  word-break: break-all;
  word-wrap: break-word;
  color: #333333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 2px;
}
pre code {
  padding: 0;
  font-size: inherit;
  color: inherit;
  white-space: pre-wrap;
  background-color: transparent;
  border-radius: 0;
}
.pre-scrollable {
  max-height: 340px;
  overflow-y: scroll;
}
.container {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
@media (min-width: 768px) {
  .container {
    width: 768px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 940px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
  }
}
.container-fluid {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
.row {
  margin-left: 0px;
  margin-right: 0px;
}
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-left: 0px;
  padding-right: 0px;
}
.col-xs-1, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9, .col-xs-10, .col-xs-11, .col-xs-12 {
  float: left;
}
.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}
.col-xs-pull-12 {
  right: 100%;
}
.col-xs-pull-11 {
  right: 91.66666667%;
}
.col-xs-pull-10 {
  right: 83.33333333%;
}
.col-xs-pull-9 {
  right: 75%;
}
.col-xs-pull-8 {
  right: 66.66666667%;
}
.col-xs-pull-7 {
  right: 58.33333333%;
}
.col-xs-pull-6 {
  right: 50%;
}
.col-xs-pull-5 {
  right: 41.66666667%;
}
.col-xs-pull-4 {
  right: 33.33333333%;
}
.col-xs-pull-3 {
  right: 25%;
}
.col-xs-pull-2 {
  right: 16.66666667%;
}
.col-xs-pull-1 {
  right: 8.33333333%;
}
.col-xs-pull-0 {
  right: auto;
}
.col-xs-push-12 {
  left: 100%;
}
.col-xs-push-11 {
  left: 91.66666667%;
}
.col-xs-push-10 {
  left: 83.33333333%;
}
.col-xs-push-9 {
  left: 75%;
}
.col-xs-push-8 {
  left: 66.66666667%;
}
.col-xs-push-7 {
  left: 58.33333333%;
}
.col-xs-push-6 {
  left: 50%;
}
.col-xs-push-5 {
  left: 41.66666667%;
}
.col-xs-push-4 {
  left: 33.33333333%;
}
.col-xs-push-3 {
  left: 25%;
}
.col-xs-push-2 {
  left: 16.66666667%;
}
.col-xs-push-1 {
  left: 8.33333333%;
}
.col-xs-push-0 {
  left: auto;
}
.col-xs-offset-12 {
  margin-left: 100%;
}
.col-xs-offset-11 {
  margin-left: 91.66666667%;
}
.col-xs-offset-10 {
  margin-left: 83.33333333%;
}
.col-xs-offset-9 {
  margin-left: 75%;
}
.col-xs-offset-8 {
  margin-left: 66.66666667%;
}
.col-xs-offset-7 {
  margin-left: 58.33333333%;
}
.col-xs-offset-6 {
  margin-left: 50%;
}
.col-xs-offset-5 {
  margin-left: 41.66666667%;
}
.col-xs-offset-4 {
  margin-left: 33.33333333%;
}
.col-xs-offset-3 {
  margin-left: 25%;
}
.col-xs-offset-2 {
  margin-left: 16.66666667%;
}
.col-xs-offset-1 {
  margin-left: 8.33333333%;
}
.col-xs-offset-0 {
  margin-left: 0%;
}
@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }
  .col-sm-pull-12 {
    right: 100%;
  }
  .col-sm-pull-11 {
    right: 91.66666667%;
  }
  .col-sm-pull-10 {
    right: 83.33333333%;
  }
  .col-sm-pull-9 {
    right: 75%;
  }
  .col-sm-pull-8 {
    right: 66.66666667%;
  }
  .col-sm-pull-7 {
    right: 58.33333333%;
  }
  .col-sm-pull-6 {
    right: 50%;
  }
  .col-sm-pull-5 {
    right: 41.66666667%;
  }
  .col-sm-pull-4 {
    right: 33.33333333%;
  }
  .col-sm-pull-3 {
    right: 25%;
  }
  .col-sm-pull-2 {
    right: 16.66666667%;
  }
  .col-sm-pull-1 {
    right: 8.33333333%;
  }
  .col-sm-pull-0 {
    right: auto;
  }
  .col-sm-push-12 {
    left: 100%;
  }
  .col-sm-push-11 {
    left: 91.66666667%;
  }
  .col-sm-push-10 {
    left: 83.33333333%;
  }
  .col-sm-push-9 {
    left: 75%;
  }
  .col-sm-push-8 {
    left: 66.66666667%;
  }
  .col-sm-push-7 {
    left: 58.33333333%;
  }
  .col-sm-push-6 {
    left: 50%;
  }
  .col-sm-push-5 {
    left: 41.66666667%;
  }
  .col-sm-push-4 {
    left: 33.33333333%;
  }
  .col-sm-push-3 {
    left: 25%;
  }
  .col-sm-push-2 {
    left: 16.66666667%;
  }
  .col-sm-push-1 {
    left: 8.33333333%;
  }
  .col-sm-push-0 {
    left: auto;
  }
  .col-sm-offset-12 {
    margin-left: 100%;
  }
  .col-sm-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-sm-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-sm-offset-9 {
    margin-left: 75%;
  }
  .col-sm-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-sm-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-sm-offset-6 {
    margin-left: 50%;
  }
  .col-sm-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-sm-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-sm-offset-3 {
    margin-left: 25%;
  }
  .col-sm-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-sm-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-sm-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
  .col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }
  .col-md-pull-4 {
    right: 33.33333333%;
  }
  .col-md-pull-3 {
    right: 25%;
  }
  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: auto;
  }
  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: auto;
  }
  .col-md-offset-12 {
    margin-left: 100%;
  }
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }
  .col-lg-pull-12 {
    right: 100%;
  }
  .col-lg-pull-11 {
    right: 91.66666667%;
  }
  .col-lg-pull-10 {
    right: 83.33333333%;
  }
  .col-lg-pull-9 {
    right: 75%;
  }
  .col-lg-pull-8 {
    right: 66.66666667%;
  }
  .col-lg-pull-7 {
    right: 58.33333333%;
  }
  .col-lg-pull-6 {
    right: 50%;
  }
  .col-lg-pull-5 {
    right: 41.66666667%;
  }
  .col-lg-pull-4 {
    right: 33.33333333%;
  }
  .col-lg-pull-3 {
    right: 25%;
  }
  .col-lg-pull-2 {
    right: 16.66666667%;
  }
  .col-lg-pull-1 {
    right: 8.33333333%;
  }
  .col-lg-pull-0 {
    right: auto;
  }
  .col-lg-push-12 {
    left: 100%;
  }
  .col-lg-push-11 {
    left: 91.66666667%;
  }
  .col-lg-push-10 {
    left: 83.33333333%;
  }
  .col-lg-push-9 {
    left: 75%;
  }
  .col-lg-push-8 {
    left: 66.66666667%;
  }
  .col-lg-push-7 {
    left: 58.33333333%;
  }
  .col-lg-push-6 {
    left: 50%;
  }
  .col-lg-push-5 {
    left: 41.66666667%;
  }
  .col-lg-push-4 {
    left: 33.33333333%;
  }
  .col-lg-push-3 {
    left: 25%;
  }
  .col-lg-push-2 {
    left: 16.66666667%;
  }
  .col-lg-push-1 {
    left: 8.33333333%;
  }
  .col-lg-push-0 {
    left: auto;
  }
  .col-lg-offset-12 {
    margin-left: 100%;
  }
  .col-lg-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-lg-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-lg-offset-9 {
    margin-left: 75%;
  }
  .col-lg-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-lg-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-lg-offset-6 {
    margin-left: 50%;
  }
  .col-lg-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-lg-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-lg-offset-3 {
    margin-left: 25%;
  }
  .col-lg-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-lg-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-lg-offset-0 {
    margin-left: 0%;
  }
}
table {
  background-color: transparent;
}
caption {
  padding-top: 8px;
  padding-bottom: 8px;
  color: #777777;
  text-align: left;
}
th {
  text-align: left;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 18px;
}
.table > thead > tr > th,
.table > tbody > tr > th,
.table > tfoot > tr > th,
.table > thead > tr > td,
.table > tbody > tr > td,
.table > tfoot > tr > td {
  padding: 8px;
  line-height: 1.42857143;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table > thead > tr > th {
  vertical-align: bottom;
  border-bottom: 2px solid #ddd;
}
.table > caption + thead > tr:first-child > th,
.table > colgroup + thead > tr:first-child > th,
.table > thead:first-child > tr:first-child > th,
.table > caption + thead > tr:first-child > td,
.table > colgroup + thead > tr:first-child > td,
.table > thead:first-child > tr:first-child > td {
  border-top: 0;
}
.table > tbody + tbody {
  border-top: 2px solid #ddd;
}
.table .table {
  background-color: #fff;
}
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
  padding: 5px;
}
.table-bordered {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;
}
.table-striped > tbody > tr:nth-of-type(odd) {
  background-color: #f9f9f9;
}
.table-hover > tbody > tr:hover {
  background-color: #f5f5f5;
}
table col[class*="col-"] {
  position: static;
  float: none;
  display: table-column;
}
table td[class*="col-"],
table th[class*="col-"] {
  position: static;
  float: none;
  display: table-cell;
}
.table > thead > tr > td.active,
.table > tbody > tr > td.active,
.table > tfoot > tr > td.active,
.table > thead > tr > th.active,
.table > tbody > tr > th.active,
.table > tfoot > tr > th.active,
.table > thead > tr.active > td,
.table > tbody > tr.active > td,
.table > tfoot > tr.active > td,
.table > thead > tr.active > th,
.table > tbody > tr.active > th,
.table > tfoot > tr.active > th {
  background-color: #f5f5f5;
}
.table-hover > tbody > tr > td.active:hover,
.table-hover > tbody > tr > th.active:hover,
.table-hover > tbody > tr.active:hover > td,
.table-hover > tbody > tr:hover > .active,
.table-hover > tbody > tr.active:hover > th {
  background-color: #e8e8e8;
}
.table > thead > tr > td.success,
.table > tbody > tr > td.success,
.table > tfoot > tr > td.success,
.table > thead > tr > th.success,
.table > tbody > tr > th.success,
.table > tfoot > tr > th.success,
.table > thead > tr.success > td,
.table > tbody > tr.success > td,
.table > tfoot > tr.success > td,
.table > thead > tr.success > th,
.table > tbody > tr.success > th,
.table > tfoot > tr.success > th {
  background-color: #dff0d8;
}
.table-hover > tbody > tr > td.success:hover,
.table-hover > tbody > tr > th.success:hover,
.table-hover > tbody > tr.success:hover > td,
.table-hover > tbody > tr:hover > .success,
.table-hover > tbody > tr.success:hover > th {
  background-color: #d0e9c6;
}
.table > thead > tr > td.info,
.table > tbody > tr > td.info,
.table > tfoot > tr > td.info,
.table > thead > tr > th.info,
.table > tbody > tr > th.info,
.table > tfoot > tr > th.info,
.table > thead > tr.info > td,
.table > tbody > tr.info > td,
.table > tfoot > tr.info > td,
.table > thead > tr.info > th,
.table > tbody > tr.info > th,
.table > tfoot > tr.info > th {
  background-color: #d9edf7;
}
.table-hover > tbody > tr > td.info:hover,
.table-hover > tbody > tr > th.info:hover,
.table-hover > tbody > tr.info:hover > td,
.table-hover > tbody > tr:hover > .info,
.table-hover > tbody > tr.info:hover > th {
  background-color: #c4e3f3;
}
.table > thead > tr > td.warning,
.table > tbody > tr > td.warning,
.table > tfoot > tr > td.warning,
.table > thead > tr > th.warning,
.table > tbody > tr > th.warning,
.table > tfoot > tr > th.warning,
.table > thead > tr.warning > td,
.table > tbody > tr.warning > td,
.table > tfoot > tr.warning > td,
.table > thead > tr.warning > th,
.table > tbody > tr.warning > th,
.table > tfoot > tr.warning > th {
  background-color: #fcf8e3;
}
.table-hover > tbody > tr > td.warning:hover,
.table-hover > tbody > tr > th.warning:hover,
.table-hover > tbody > tr.warning:hover > td,
.table-hover > tbody > tr:hover > .warning,
.table-hover > tbody > tr.warning:hover > th {
  background-color: #faf2cc;
}
.table > thead > tr > td.danger,
.table > tbody > tr > td.danger,
.table > tfoot > tr > td.danger,
.table > thead > tr > th.danger,
.table > tbody > tr > th.danger,
.table > tfoot > tr > th.danger,
.table > thead > tr.danger > td,
.table > tbody > tr.danger > td,
.table > tfoot > tr.danger > td,
.table > thead > tr.danger > th,
.table > tbody > tr.danger > th,
.table > tfoot > tr.danger > th {
  background-color: #f2dede;
}
.table-hover > tbody > tr > td.danger:hover,
.table-hover > tbody > tr > th.danger:hover,
.table-hover > tbody > tr.danger:hover > td,
.table-hover > tbody > tr:hover > .danger,
.table-hover > tbody > tr.danger:hover > th {
  background-color: #ebcccc;
}
.table-responsive {
  overflow-x: auto;
  min-height: 0.01%;
}
@media screen and (max-width: 767px) {
  .table-responsive {
    width: 100%;
    margin-bottom: 13.5px;
    overflow-y: hidden;
    -ms-overflow-style: -ms-autohiding-scrollbar;
    border: 1px solid #ddd;
  }
  .table-responsive > .table {
    margin-bottom: 0;
  }
  .table-responsive > .table > thead > tr > th,
  .table-responsive > .table > tbody > tr > th,
  .table-responsive > .table > tfoot > tr > th,
  .table-responsive > .table > thead > tr > td,
  .table-responsive > .table > tbody > tr > td,
  .table-responsive > .table > tfoot > tr > td {
    white-space: nowrap;
  }
  .table-responsive > .table-bordered {
    border: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:first-child,
  .table-responsive > .table-bordered > tbody > tr > th:first-child,
  .table-responsive > .table-bordered > tfoot > tr > th:first-child,
  .table-responsive > .table-bordered > thead > tr > td:first-child,
  .table-responsive > .table-bordered > tbody > tr > td:first-child,
  .table-responsive > .table-bordered > tfoot > tr > td:first-child {
    border-left: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:last-child,
  .table-responsive > .table-bordered > tbody > tr > th:last-child,
  .table-responsive > .table-bordered > tfoot > tr > th:last-child,
  .table-responsive > .table-bordered > thead > tr > td:last-child,
  .table-responsive > .table-bordered > tbody > tr > td:last-child,
  .table-responsive > .table-bordered > tfoot > tr > td:last-child {
    border-right: 0;
  }
  .table-responsive > .table-bordered > tbody > tr:last-child > th,
  .table-responsive > .table-bordered > tfoot > tr:last-child > th,
  .table-responsive > .table-bordered > tbody > tr:last-child > td,
  .table-responsive > .table-bordered > tfoot > tr:last-child > td {
    border-bottom: 0;
  }
}
fieldset {
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
}
legend {
  display: block;
  width: 100%;
  padding: 0;
  margin-bottom: 18px;
  font-size: 19.5px;
  line-height: inherit;
  color: #333333;
  border: 0;
  border-bottom: 1px solid #e5e5e5;
}
label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: bold;
}
input[type="search"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
input[type="radio"],
input[type="checkbox"] {
  margin: 4px 0 0;
  margin-top: 1px \9;
  line-height: normal;
}
input[type="file"] {
  display: block;
}
input[type="range"] {
  display: block;
  width: 100%;
}
select[multiple],
select[size] {
  height: auto;
}
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
output {
  display: block;
  padding-top: 7px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
}
.form-control {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.form-control:-ms-input-placeholder {
  color: #999;
}
.form-control::-webkit-input-placeholder {
  color: #999;
}
.form-control::-ms-expand {
  border: 0;
  background-color: transparent;
}
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
  background-color: #eeeeee;
  opacity: 1;
}
.form-control[disabled],
fieldset[disabled] .form-control {
  cursor: not-allowed;
}
textarea.form-control {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: none;
}
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  input[type="date"].form-control,
  input[type="time"].form-control,
  input[type="datetime-local"].form-control,
  input[type="month"].form-control {
    line-height: 32px;
  }
  input[type="date"].input-sm,
  input[type="time"].input-sm,
  input[type="datetime-local"].input-sm,
  input[type="month"].input-sm,
  .input-group-sm input[type="date"],
  .input-group-sm input[type="time"],
  .input-group-sm input[type="datetime-local"],
  .input-group-sm input[type="month"] {
    line-height: 30px;
  }
  input[type="date"].input-lg,
  input[type="time"].input-lg,
  input[type="datetime-local"].input-lg,
  input[type="month"].input-lg,
  .input-group-lg input[type="date"],
  .input-group-lg input[type="time"],
  .input-group-lg input[type="datetime-local"],
  .input-group-lg input[type="month"] {
    line-height: 45px;
  }
}
.form-group {
  margin-bottom: 15px;
}
.radio,
.checkbox {
  position: relative;
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
.radio label,
.checkbox label {
  min-height: 18px;
  padding-left: 20px;
  margin-bottom: 0;
  font-weight: normal;
  cursor: pointer;
}
.radio input[type="radio"],
.radio-inline input[type="radio"],
.checkbox input[type="checkbox"],
.checkbox-inline input[type="checkbox"] {
  position: absolute;
  margin-left: -20px;
  margin-top: 4px \9;
}
.radio + .radio,
.checkbox + .checkbox {
  margin-top: -5px;
}
.radio-inline,
.checkbox-inline {
  position: relative;
  display: inline-block;
  padding-left: 20px;
  margin-bottom: 0;
  vertical-align: middle;
  font-weight: normal;
  cursor: pointer;
}
.radio-inline + .radio-inline,
.checkbox-inline + .checkbox-inline {
  margin-top: 0;
  margin-left: 10px;
}
input[type="radio"][disabled],
input[type="checkbox"][disabled],
input[type="radio"].disabled,
input[type="checkbox"].disabled,
fieldset[disabled] input[type="radio"],
fieldset[disabled] input[type="checkbox"] {
  cursor: not-allowed;
}
.radio-inline.disabled,
.checkbox-inline.disabled,
fieldset[disabled] .radio-inline,
fieldset[disabled] .checkbox-inline {
  cursor: not-allowed;
}
.radio.disabled label,
.checkbox.disabled label,
fieldset[disabled] .radio label,
fieldset[disabled] .checkbox label {
  cursor: not-allowed;
}
.form-control-static {
  padding-top: 7px;
  padding-bottom: 7px;
  margin-bottom: 0;
  min-height: 31px;
}
.form-control-static.input-lg,
.form-control-static.input-sm {
  padding-left: 0;
  padding-right: 0;
}
.input-sm {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-sm {
  height: 30px;
  line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
  height: auto;
}
.form-group-sm .form-control {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.form-group-sm select.form-control {
  height: 30px;
  line-height: 30px;
}
.form-group-sm textarea.form-control,
.form-group-sm select[multiple].form-control {
  height: auto;
}
.form-group-sm .form-control-static {
  height: 30px;
  min-height: 30px;
  padding: 6px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.input-lg {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-lg {
  height: 45px;
  line-height: 45px;
}
textarea.input-lg,
select[multiple].input-lg {
  height: auto;
}
.form-group-lg .form-control {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.form-group-lg select.form-control {
  height: 45px;
  line-height: 45px;
}
.form-group-lg textarea.form-control,
.form-group-lg select[multiple].form-control {
  height: auto;
}
.form-group-lg .form-control-static {
  height: 45px;
  min-height: 35px;
  padding: 11px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.has-feedback {
  position: relative;
}
.has-feedback .form-control {
  padding-right: 40px;
}
.form-control-feedback {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  display: block;
  width: 32px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  pointer-events: none;
}
.input-lg + .form-control-feedback,
.input-group-lg + .form-control-feedback,
.form-group-lg .form-control + .form-control-feedback {
  width: 45px;
  height: 45px;
  line-height: 45px;
}
.input-sm + .form-control-feedback,
.input-group-sm + .form-control-feedback,
.form-group-sm .form-control + .form-control-feedback {
  width: 30px;
  height: 30px;
  line-height: 30px;
}
.has-success .help-block,
.has-success .control-label,
.has-success .radio,
.has-success .checkbox,
.has-success .radio-inline,
.has-success .checkbox-inline,
.has-success.radio label,
.has-success.checkbox label,
.has-success.radio-inline label,
.has-success.checkbox-inline label {
  color: #3c763d;
}
.has-success .form-control {
  border-color: #3c763d;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-success .form-control:focus {
  border-color: #2b542c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
}
.has-success .input-group-addon {
  color: #3c763d;
  border-color: #3c763d;
  background-color: #dff0d8;
}
.has-success .form-control-feedback {
  color: #3c763d;
}
.has-warning .help-block,
.has-warning .control-label,
.has-warning .radio,
.has-warning .checkbox,
.has-warning .radio-inline,
.has-warning .checkbox-inline,
.has-warning.radio label,
.has-warning.checkbox label,
.has-warning.radio-inline label,
.has-warning.checkbox-inline label {
  color: #8a6d3b;
}
.has-warning .form-control {
  border-color: #8a6d3b;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-warning .form-control:focus {
  border-color: #66512c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
}
.has-warning .input-group-addon {
  color: #8a6d3b;
  border-color: #8a6d3b;
  background-color: #fcf8e3;
}
.has-warning .form-control-feedback {
  color: #8a6d3b;
}
.has-error .help-block,
.has-error .control-label,
.has-error .radio,
.has-error .checkbox,
.has-error .radio-inline,
.has-error .checkbox-inline,
.has-error.radio label,
.has-error.checkbox label,
.has-error.radio-inline label,
.has-error.checkbox-inline label {
  color: #a94442;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .input-group-addon {
  color: #a94442;
  border-color: #a94442;
  background-color: #f2dede;
}
.has-error .form-control-feedback {
  color: #a94442;
}
.has-feedback label ~ .form-control-feedback {
  top: 23px;
}
.has-feedback label.sr-only ~ .form-control-feedback {
  top: 0;
}
.help-block {
  display: block;
  margin-top: 5px;
  margin-bottom: 10px;
  color: #404040;
}
@media (min-width: 768px) {
  .form-inline .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .form-inline .form-control-static {
    display: inline-block;
  }
  .form-inline .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .form-inline .input-group .input-group-addon,
  .form-inline .input-group .input-group-btn,
  .form-inline .input-group .form-control {
    width: auto;
  }
  .form-inline .input-group > .form-control {
    width: 100%;
  }
  .form-inline .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio,
  .form-inline .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio label,
  .form-inline .checkbox label {
    padding-left: 0;
  }
  .form-inline .radio input[type="radio"],
  .form-inline .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .form-inline .has-feedback .form-control-feedback {
    top: 0;
  }
}
.form-horizontal .radio,
.form-horizontal .checkbox,
.form-horizontal .radio-inline,
.form-horizontal .checkbox-inline {
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 7px;
}
.form-horizontal .radio,
.form-horizontal .checkbox {
  min-height: 25px;
}
.form-horizontal .form-group {
  margin-left: 0px;
  margin-right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .control-label {
    text-align: right;
    margin-bottom: 0;
    padding-top: 7px;
  }
}
.form-horizontal .has-feedback .form-control-feedback {
  right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .form-group-lg .control-label {
    padding-top: 11px;
    font-size: 17px;
  }
}
@media (min-width: 768px) {
  .form-horizontal .form-group-sm .control-label {
    padding-top: 6px;
    font-size: 12px;
  }
}
.btn {
  display: inline-block;
  margin-bottom: 0;
  font-weight: normal;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  border-radius: 2px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
.btn:hover,
.btn:focus,
.btn.focus {
  color: #333;
  text-decoration: none;
}
.btn:active,
.btn.active {
  outline: 0;
  background-image: none;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
  cursor: not-allowed;
  opacity: 0.65;
  filter: alpha(opacity=65);
  -webkit-box-shadow: none;
  box-shadow: none;
}
a.btn.disabled,
fieldset[disabled] a.btn {
  pointer-events: none;
}
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.btn-default:focus,
.btn-default.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.btn-default:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active:hover,
.btn-default.active:hover,
.open > .dropdown-toggle.btn-default:hover,
.btn-default:active:focus,
.btn-default.active:focus,
.open > .dropdown-toggle.btn-default:focus,
.btn-default:active.focus,
.btn-default.active.focus,
.open > .dropdown-toggle.btn-default.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  background-image: none;
}
.btn-default.disabled:hover,
.btn-default[disabled]:hover,
fieldset[disabled] .btn-default:hover,
.btn-default.disabled:focus,
.btn-default[disabled]:focus,
fieldset[disabled] .btn-default:focus,
.btn-default.disabled.focus,
.btn-default[disabled].focus,
fieldset[disabled] .btn-default.focus {
  background-color: #fff;
  border-color: #ccc;
}
.btn-default .badge {
  color: #fff;
  background-color: #333;
}
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary:focus,
.btn-primary.focus {
  color: #fff;
  background-color: #286090;
  border-color: #122b40;
}
.btn-primary:hover {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active:hover,
.btn-primary.active:hover,
.open > .dropdown-toggle.btn-primary:hover,
.btn-primary:active:focus,
.btn-primary.active:focus,
.open > .dropdown-toggle.btn-primary:focus,
.btn-primary:active.focus,
.btn-primary.active.focus,
.open > .dropdown-toggle.btn-primary.focus {
  color: #fff;
  background-color: #204d74;
  border-color: #122b40;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus {
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}
.btn-success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success:focus,
.btn-success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.btn-success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active:hover,
.btn-success.active:hover,
.open > .dropdown-toggle.btn-success:hover,
.btn-success:active:focus,
.btn-success.active:focus,
.open > .dropdown-toggle.btn-success:focus,
.btn-success:active.focus,
.btn-success.active.focus,
.open > .dropdown-toggle.btn-success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  background-image: none;
}
.btn-success.disabled:hover,
.btn-success[disabled]:hover,
fieldset[disabled] .btn-success:hover,
.btn-success.disabled:focus,
.btn-success[disabled]:focus,
fieldset[disabled] .btn-success:focus,
.btn-success.disabled.focus,
.btn-success[disabled].focus,
fieldset[disabled] .btn-success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.btn-info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info:focus,
.btn-info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.btn-info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active:hover,
.btn-info.active:hover,
.open > .dropdown-toggle.btn-info:hover,
.btn-info:active:focus,
.btn-info.active:focus,
.open > .dropdown-toggle.btn-info:focus,
.btn-info:active.focus,
.btn-info.active.focus,
.open > .dropdown-toggle.btn-info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  background-image: none;
}
.btn-info.disabled:hover,
.btn-info[disabled]:hover,
fieldset[disabled] .btn-info:hover,
.btn-info.disabled:focus,
.btn-info[disabled]:focus,
fieldset[disabled] .btn-info:focus,
.btn-info.disabled.focus,
.btn-info[disabled].focus,
fieldset[disabled] .btn-info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.btn-warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning:focus,
.btn-warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.btn-warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active:hover,
.btn-warning.active:hover,
.open > .dropdown-toggle.btn-warning:hover,
.btn-warning:active:focus,
.btn-warning.active:focus,
.open > .dropdown-toggle.btn-warning:focus,
.btn-warning:active.focus,
.btn-warning.active.focus,
.open > .dropdown-toggle.btn-warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  background-image: none;
}
.btn-warning.disabled:hover,
.btn-warning[disabled]:hover,
fieldset[disabled] .btn-warning:hover,
.btn-warning.disabled:focus,
.btn-warning[disabled]:focus,
fieldset[disabled] .btn-warning:focus,
.btn-warning.disabled.focus,
.btn-warning[disabled].focus,
fieldset[disabled] .btn-warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger:focus,
.btn-danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.btn-danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active:hover,
.btn-danger.active:hover,
.open > .dropdown-toggle.btn-danger:hover,
.btn-danger:active:focus,
.btn-danger.active:focus,
.open > .dropdown-toggle.btn-danger:focus,
.btn-danger:active.focus,
.btn-danger.active.focus,
.open > .dropdown-toggle.btn-danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  background-image: none;
}
.btn-danger.disabled:hover,
.btn-danger[disabled]:hover,
fieldset[disabled] .btn-danger:hover,
.btn-danger.disabled:focus,
.btn-danger[disabled]:focus,
fieldset[disabled] .btn-danger:focus,
.btn-danger.disabled.focus,
.btn-danger[disabled].focus,
fieldset[disabled] .btn-danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger .badge {
  color: #d9534f;
  background-color: #fff;
}
.btn-link {
  color: #337ab7;
  font-weight: normal;
  border-radius: 0;
}
.btn-link,
.btn-link:active,
.btn-link.active,
.btn-link[disabled],
fieldset[disabled] .btn-link {
  background-color: transparent;
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn-link,
.btn-link:hover,
.btn-link:focus,
.btn-link:active {
  border-color: transparent;
}
.btn-link:hover,
.btn-link:focus {
  color: #23527c;
  text-decoration: underline;
  background-color: transparent;
}
.btn-link[disabled]:hover,
fieldset[disabled] .btn-link:hover,
.btn-link[disabled]:focus,
fieldset[disabled] .btn-link:focus {
  color: #777777;
  text-decoration: none;
}
.btn-lg,
.btn-group-lg > .btn {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.btn-sm,
.btn-group-sm > .btn {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-xs,
.btn-group-xs > .btn {
  padding: 1px 5px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}
.fade {
  opacity: 0;
  -webkit-transition: opacity 0.15s linear;
  -o-transition: opacity 0.15s linear;
  transition: opacity 0.15s linear;
}
.fade.in {
  opacity: 1;
}
.collapse {
  display: none;
}
.collapse.in {
  display: block;
}
tr.collapse.in {
  display: table-row;
}
tbody.collapse.in {
  display: table-row-group;
}
.collapsing {
  position: relative;
  height: 0;
  overflow: hidden;
  -webkit-transition-property: height, visibility;
  transition-property: height, visibility;
  -webkit-transition-duration: 0.35s;
  transition-duration: 0.35s;
  -webkit-transition-timing-function: ease;
  transition-timing-function: ease;
}
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
.dropup,
.dropdown {
  position: relative;
}
.dropdown-toggle:focus {
  outline: 0;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  display: none;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 13px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.15);
  border-radius: 2px;
  -webkit-box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu .divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.dropdown-menu > li > a {
  display: block;
  padding: 3px 20px;
  clear: both;
  font-weight: normal;
  line-height: 1.42857143;
  color: #333333;
  white-space: nowrap;
}
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  text-decoration: none;
  color: #262626;
  background-color: #f5f5f5;
}
.dropdown-menu > .active > a,
.dropdown-menu > .active > a:hover,
.dropdown-menu > .active > a:focus {
  color: #fff;
  text-decoration: none;
  outline: 0;
  background-color: #337ab7;
}
.dropdown-menu > .disabled > a,
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  color: #777777;
}
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  text-decoration: none;
  background-color: transparent;
  background-image: none;
  filter: progid:DXImageTransform.Microsoft.gradient(enabled = false);
  cursor: not-allowed;
}
.open > .dropdown-menu {
  display: block;
}
.open > a {
  outline: 0;
}
.dropdown-menu-right {
  left: auto;
  right: 0;
}
.dropdown-menu-left {
  left: 0;
  right: auto;
}
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #777777;
  white-space: nowrap;
}
.dropdown-backdrop {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  z-index: 990;
}
.pull-right > .dropdown-menu {
  right: 0;
  left: auto;
}
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  border-top: 0;
  border-bottom: 4px dashed;
  border-bottom: 4px solid \9;
  content: "";
}
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 2px;
}
@media (min-width: 541px) {
  .navbar-right .dropdown-menu {
    left: auto;
    right: 0;
  }
  .navbar-right .dropdown-menu-left {
    left: 0;
    right: auto;
  }
}
.btn-group,
.btn-group-vertical {
  position: relative;
  display: inline-block;
  vertical-align: middle;
}
.btn-group > .btn,
.btn-group-vertical > .btn {
  position: relative;
  float: left;
}
.btn-group > .btn:hover,
.btn-group-vertical > .btn:hover,
.btn-group > .btn:focus,
.btn-group-vertical > .btn:focus,
.btn-group > .btn:active,
.btn-group-vertical > .btn:active,
.btn-group > .btn.active,
.btn-group-vertical > .btn.active {
  z-index: 2;
}
.btn-group .btn + .btn,
.btn-group .btn + .btn-group,
.btn-group .btn-group + .btn,
.btn-group .btn-group + .btn-group {
  margin-left: -1px;
}
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn,
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
.btn-group > .btn:not(:first-child):not(:last-child):not(.dropdown-toggle) {
  border-radius: 0;
}
.btn-group > .btn:first-child {
  margin-left: 0;
}
.btn-group > .btn:first-child:not(:last-child):not(.dropdown-toggle) {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn:last-child:not(:first-child),
.btn-group > .dropdown-toggle:not(:first-child) {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group > .btn-group {
  float: left;
}
.btn-group > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-left: 8px;
  padding-right: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-left: 12px;
  padding-right: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
.btn-group-vertical > .btn,
.btn-group-vertical > .btn-group,
.btn-group-vertical > .btn-group > .btn {
  display: block;
  float: none;
  width: 100%;
  max-width: 100%;
}
.btn-group-vertical > .btn-group > .btn {
  float: none;
}
.btn-group-vertical > .btn + .btn,
.btn-group-vertical > .btn + .btn-group,
.btn-group-vertical > .btn-group + .btn,
.btn-group-vertical > .btn-group + .btn-group {
  margin-top: -1px;
  margin-left: 0;
}
.btn-group-vertical > .btn:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.btn-group-vertical > .btn:first-child:not(:last-child) {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn:last-child:not(:first-child) {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
.btn-group-vertical > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  float: none;
  display: table-cell;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
.btn-group-justified > .btn-group .dropdown-menu {
  left: auto;
}
[data-toggle="buttons"] > .btn input[type="radio"],
[data-toggle="buttons"] > .btn-group > .btn input[type="radio"],
[data-toggle="buttons"] > .btn input[type="checkbox"],
[data-toggle="buttons"] > .btn-group > .btn input[type="checkbox"] {
  position: absolute;
  clip: rect(0, 0, 0, 0);
  pointer-events: none;
}
.input-group {
  position: relative;
  display: table;
  border-collapse: separate;
}
.input-group[class*="col-"] {
  float: none;
  padding-left: 0;
  padding-right: 0;
}
.input-group .form-control {
  position: relative;
  z-index: 2;
  float: left;
  width: 100%;
  margin-bottom: 0;
}
.input-group .form-control:focus {
  z-index: 3;
}
.input-group-lg > .form-control,
.input-group-lg > .input-group-addon,
.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-group-lg > .form-control,
select.input-group-lg > .input-group-addon,
select.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  line-height: 45px;
}
textarea.input-group-lg > .form-control,
textarea.input-group-lg > .input-group-addon,
textarea.input-group-lg > .input-group-btn > .btn,
select[multiple].input-group-lg > .form-control,
select[multiple].input-group-lg > .input-group-addon,
select[multiple].input-group-lg > .input-group-btn > .btn {
  height: auto;
}
.input-group-sm > .form-control,
.input-group-sm > .input-group-addon,
.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-group-sm > .form-control,
select.input-group-sm > .input-group-addon,
select.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  line-height: 30px;
}
textarea.input-group-sm > .form-control,
textarea.input-group-sm > .input-group-addon,
textarea.input-group-sm > .input-group-btn > .btn,
select[multiple].input-group-sm > .form-control,
select[multiple].input-group-sm > .input-group-addon,
select[multiple].input-group-sm > .input-group-btn > .btn {
  height: auto;
}
.input-group-addon,
.input-group-btn,
.input-group .form-control {
  display: table-cell;
}
.input-group-addon:not(:first-child):not(:last-child),
.input-group-btn:not(:first-child):not(:last-child),
.input-group .form-control:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.input-group-addon,
.input-group-btn {
  width: 1%;
  white-space: nowrap;
  vertical-align: middle;
}
.input-group-addon {
  padding: 6px 12px;
  font-size: 13px;
  font-weight: normal;
  line-height: 1;
  color: #555555;
  text-align: center;
  background-color: #eeeeee;
  border: 1px solid #ccc;
  border-radius: 2px;
}
.input-group-addon.input-sm {
  padding: 5px 10px;
  font-size: 12px;
  border-radius: 1px;
}
.input-group-addon.input-lg {
  padding: 10px 16px;
  font-size: 17px;
  border-radius: 3px;
}
.input-group-addon input[type="radio"],
.input-group-addon input[type="checkbox"] {
  margin-top: 0;
}
.input-group .form-control:first-child,
.input-group-addon:first-child,
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group > .btn,
.input-group-btn:first-child > .dropdown-toggle,
.input-group-btn:last-child > .btn:not(:last-child):not(.dropdown-toggle),
.input-group-btn:last-child > .btn-group:not(:last-child) > .btn {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.input-group-addon:first-child {
  border-right: 0;
}
.input-group .form-control:last-child,
.input-group-addon:last-child,
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group > .btn,
.input-group-btn:last-child > .dropdown-toggle,
.input-group-btn:first-child > .btn:not(:first-child),
.input-group-btn:first-child > .btn-group:not(:first-child) > .btn {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.input-group-addon:last-child {
  border-left: 0;
}
.input-group-btn {
  position: relative;
  font-size: 0;
  white-space: nowrap;
}
.input-group-btn > .btn {
  position: relative;
}
.input-group-btn > .btn + .btn {
  margin-left: -1px;
}
.input-group-btn > .btn:hover,
.input-group-btn > .btn:focus,
.input-group-btn > .btn:active {
  z-index: 2;
}
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group {
  margin-right: -1px;
}
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group {
  z-index: 2;
  margin-left: -1px;
}
.nav {
  margin-bottom: 0;
  padding-left: 0;
  list-style: none;
}
.nav > li {
  position: relative;
  display: block;
}
.nav > li > a {
  position: relative;
  display: block;
  padding: 10px 15px;
}
.nav > li > a:hover,
.nav > li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.nav > li.disabled > a {
  color: #777777;
}
.nav > li.disabled > a:hover,
.nav > li.disabled > a:focus {
  color: #777777;
  text-decoration: none;
  background-color: transparent;
  cursor: not-allowed;
}
.nav .open > a,
.nav .open > a:hover,
.nav .open > a:focus {
  background-color: #eeeeee;
  border-color: #337ab7;
}
.nav .nav-divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.nav > li > a > img {
  max-width: none;
}
.nav-tabs {
  border-bottom: 1px solid #ddd;
}
.nav-tabs > li {
  float: left;
  margin-bottom: -1px;
}
.nav-tabs > li > a {
  margin-right: 2px;
  line-height: 1.42857143;
  border: 1px solid transparent;
  border-radius: 2px 2px 0 0;
}
.nav-tabs > li > a:hover {
  border-color: #eeeeee #eeeeee #ddd;
}
.nav-tabs > li.active > a,
.nav-tabs > li.active > a:hover,
.nav-tabs > li.active > a:focus {
  color: #555555;
  background-color: #fff;
  border: 1px solid #ddd;
  border-bottom-color: transparent;
  cursor: default;
}
.nav-tabs.nav-justified {
  width: 100%;
  border-bottom: 0;
}
.nav-tabs.nav-justified > li {
  float: none;
}
.nav-tabs.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-tabs.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-tabs.nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs.nav-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs.nav-justified > .active > a,
.nav-tabs.nav-justified > .active > a:hover,
.nav-tabs.nav-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs.nav-justified > .active > a,
  .nav-tabs.nav-justified > .active > a:hover,
  .nav-tabs.nav-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.nav-pills > li {
  float: left;
}
.nav-pills > li > a {
  border-radius: 2px;
}
.nav-pills > li + li {
  margin-left: 2px;
}
.nav-pills > li.active > a,
.nav-pills > li.active > a:hover,
.nav-pills > li.active > a:focus {
  color: #fff;
  background-color: #337ab7;
}
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs-justified {
  border-bottom: 0;
}
.nav-tabs-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs-justified > .active > a,
.nav-tabs-justified > .active > a:hover,
.nav-tabs-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs-justified > .active > a,
  .nav-tabs-justified > .active > a:hover,
  .nav-tabs-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.tab-content > .tab-pane {
  display: none;
}
.tab-content > .active {
  display: block;
}
.nav-tabs .dropdown-menu {
  margin-top: -1px;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar {
  position: relative;
  min-height: 30px;
  margin-bottom: 18px;
  border: 1px solid transparent;
}
@media (min-width: 541px) {
  .navbar {
    border-radius: 2px;
  }
}
@media (min-width: 541px) {
  .navbar-header {
    float: left;
  }
}
.navbar-collapse {
  overflow-x: visible;
  padding-right: 0px;
  padding-left: 0px;
  border-top: 1px solid transparent;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
  -webkit-overflow-scrolling: touch;
}
.navbar-collapse.in {
  overflow-y: auto;
}
@media (min-width: 541px) {
  .navbar-collapse {
    width: auto;
    border-top: 0;
    box-shadow: none;
  }
  .navbar-collapse.collapse {
    display: block !important;
    height: auto !important;
    padding-bottom: 0;
    overflow: visible !important;
  }
  .navbar-collapse.in {
    overflow-y: visible;
  }
  .navbar-fixed-top .navbar-collapse,
  .navbar-static-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    padding-left: 0;
    padding-right: 0;
  }
}
.navbar-fixed-top .navbar-collapse,
.navbar-fixed-bottom .navbar-collapse {
  max-height: 340px;
}
@media (max-device-width: 540px) and (orientation: landscape) {
  .navbar-fixed-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    max-height: 200px;
  }
}
.container > .navbar-header,
.container-fluid > .navbar-header,
.container > .navbar-collapse,
.container-fluid > .navbar-collapse {
  margin-right: 0px;
  margin-left: 0px;
}
@media (min-width: 541px) {
  .container > .navbar-header,
  .container-fluid > .navbar-header,
  .container > .navbar-collapse,
  .container-fluid > .navbar-collapse {
    margin-right: 0;
    margin-left: 0;
  }
}
.navbar-static-top {
  z-index: 1000;
  border-width: 0 0 1px;
}
@media (min-width: 541px) {
  .navbar-static-top {
    border-radius: 0;
  }
}
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 541px) {
  .navbar-fixed-top,
  .navbar-fixed-bottom {
    border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
.navbar-brand {
  float: left;
  padding: 6px 0px;
  font-size: 17px;
  line-height: 18px;
  height: 30px;
}
.navbar-brand:hover,
.navbar-brand:focus {
  text-decoration: none;
}
.navbar-brand > img {
  display: block;
}
@media (min-width: 541px) {
  .navbar > .container .navbar-brand,
  .navbar > .container-fluid .navbar-brand {
    margin-left: 0px;
  }
}
.navbar-toggle {
  position: relative;
  float: right;
  margin-right: 0px;
  padding: 9px 10px;
  margin-top: -2px;
  margin-bottom: -2px;
  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 2px;
}
.navbar-toggle:focus {
  outline: 0;
}
.navbar-toggle .icon-bar {
  display: block;
  width: 22px;
  height: 2px;
  border-radius: 1px;
}
.navbar-toggle .icon-bar + .icon-bar {
  margin-top: 4px;
}
@media (min-width: 541px) {
  .navbar-toggle {
    display: none;
  }
}
.navbar-nav {
  margin: 3px 0px;
}
.navbar-nav > li > a {
  padding-top: 10px;
  padding-bottom: 10px;
  line-height: 18px;
}
@media (max-width: 540px) {
  .navbar-nav .open .dropdown-menu {
    position: static;
    float: none;
    width: auto;
    margin-top: 0;
    background-color: transparent;
    border: 0;
    box-shadow: none;
  }
  .navbar-nav .open .dropdown-menu > li > a,
  .navbar-nav .open .dropdown-menu .dropdown-header {
    padding: 5px 15px 5px 25px;
  }
  .navbar-nav .open .dropdown-menu > li > a {
    line-height: 18px;
  }
  .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-nav .open .dropdown-menu > li > a:focus {
    background-image: none;
  }
}
@media (min-width: 541px) {
  .navbar-nav {
    float: left;
    margin: 0;
  }
  .navbar-nav > li {
    float: left;
  }
  .navbar-nav > li > a {
    padding-top: 6px;
    padding-bottom: 6px;
  }
}
.navbar-form {
  margin-left: 0px;
  margin-right: 0px;
  padding: 10px 0px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  margin-top: -1px;
  margin-bottom: -1px;
}
@media (min-width: 768px) {
  .navbar-form .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .navbar-form .form-control-static {
    display: inline-block;
  }
  .navbar-form .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .navbar-form .input-group .input-group-addon,
  .navbar-form .input-group .input-group-btn,
  .navbar-form .input-group .form-control {
    width: auto;
  }
  .navbar-form .input-group > .form-control {
    width: 100%;
  }
  .navbar-form .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio,
  .navbar-form .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio label,
  .navbar-form .checkbox label {
    padding-left: 0;
  }
  .navbar-form .radio input[type="radio"],
  .navbar-form .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .navbar-form .has-feedback .form-control-feedback {
    top: 0;
  }
}
@media (max-width: 540px) {
  .navbar-form .form-group {
    margin-bottom: 5px;
  }
  .navbar-form .form-group:last-child {
    margin-bottom: 0;
  }
}
@media (min-width: 541px) {
  .navbar-form {
    width: auto;
    border: 0;
    margin-left: 0;
    margin-right: 0;
    padding-top: 0;
    padding-bottom: 0;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
}
.navbar-nav > li > .dropdown-menu {
  margin-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar-fixed-bottom .navbar-nav > li > .dropdown-menu {
  margin-bottom: 0;
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.navbar-btn {
  margin-top: -1px;
  margin-bottom: -1px;
}
.navbar-btn.btn-sm {
  margin-top: 0px;
  margin-bottom: 0px;
}
.navbar-btn.btn-xs {
  margin-top: 4px;
  margin-bottom: 4px;
}
.navbar-text {
  margin-top: 6px;
  margin-bottom: 6px;
}
@media (min-width: 541px) {
  .navbar-text {
    float: left;
    margin-left: 0px;
    margin-right: 0px;
  }
}
@media (min-width: 541px) {
  .navbar-left {
    float: left !important;
    float: left;
  }
  .navbar-right {
    float: right !important;
    float: right;
    margin-right: 0px;
  }
  .navbar-right ~ .navbar-right {
    margin-right: 0;
  }
}
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
.navbar-default .navbar-brand {
  color: #777;
}
.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
  color: #5e5e5e;
  background-color: transparent;
}
.navbar-default .navbar-text {
  color: #777;
}
.navbar-default .navbar-nav > li > a {
  color: #777;
}
.navbar-default .navbar-nav > li > a:hover,
.navbar-default .navbar-nav > li > a:focus {
  color: #333;
  background-color: transparent;
}
.navbar-default .navbar-nav > .active > a,
.navbar-default .navbar-nav > .active > a:hover,
.navbar-default .navbar-nav > .active > a:focus {
  color: #555;
  background-color: #e7e7e7;
}
.navbar-default .navbar-nav > .disabled > a,
.navbar-default .navbar-nav > .disabled > a:hover,
.navbar-default .navbar-nav > .disabled > a:focus {
  color: #ccc;
  background-color: transparent;
}
.navbar-default .navbar-toggle {
  border-color: #ddd;
}
.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
  background-color: #ddd;
}
.navbar-default .navbar-toggle .icon-bar {
  background-color: #888;
}
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
  border-color: #e7e7e7;
}
.navbar-default .navbar-nav > .open > a,
.navbar-default .navbar-nav > .open > a:hover,
.navbar-default .navbar-nav > .open > a:focus {
  background-color: #e7e7e7;
  color: #555;
}
@media (max-width: 540px) {
  .navbar-default .navbar-nav .open .dropdown-menu > li > a {
    color: #777;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #333;
    background-color: transparent;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #555;
    background-color: #e7e7e7;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #ccc;
    background-color: transparent;
  }
}
.navbar-default .navbar-link {
  color: #777;
}
.navbar-default .navbar-link:hover {
  color: #333;
}
.navbar-default .btn-link {
  color: #777;
}
.navbar-default .btn-link:hover,
.navbar-default .btn-link:focus {
  color: #333;
}
.navbar-default .btn-link[disabled]:hover,
fieldset[disabled] .navbar-default .btn-link:hover,
.navbar-default .btn-link[disabled]:focus,
fieldset[disabled] .navbar-default .btn-link:focus {
  color: #ccc;
}
.navbar-inverse {
  background-color: #222;
  border-color: #080808;
}
.navbar-inverse .navbar-brand {
  color: #9d9d9d;
}
.navbar-inverse .navbar-brand:hover,
.navbar-inverse .navbar-brand:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-text {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a:hover,
.navbar-inverse .navbar-nav > li > a:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
  color: #fff;
  background-color: #080808;
}
.navbar-inverse .navbar-nav > .disabled > a,
.navbar-inverse .navbar-nav > .disabled > a:hover,
.navbar-inverse .navbar-nav > .disabled > a:focus {
  color: #444;
  background-color: transparent;
}
.navbar-inverse .navbar-toggle {
  border-color: #333;
}
.navbar-inverse .navbar-toggle:hover,
.navbar-inverse .navbar-toggle:focus {
  background-color: #333;
}
.navbar-inverse .navbar-toggle .icon-bar {
  background-color: #fff;
}
.navbar-inverse .navbar-collapse,
.navbar-inverse .navbar-form {
  border-color: #101010;
}
.navbar-inverse .navbar-nav > .open > a,
.navbar-inverse .navbar-nav > .open > a:hover,
.navbar-inverse .navbar-nav > .open > a:focus {
  background-color: #080808;
  color: #fff;
}
@media (max-width: 540px) {
  .navbar-inverse .navbar-nav .open .dropdown-menu > .dropdown-header {
    border-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu .divider {
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a {
    color: #9d9d9d;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #fff;
    background-color: transparent;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #fff;
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #444;
    background-color: transparent;
  }
}
.navbar-inverse .navbar-link {
  color: #9d9d9d;
}
.navbar-inverse .navbar-link:hover {
  color: #fff;
}
.navbar-inverse .btn-link {
  color: #9d9d9d;
}
.navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link:focus {
  color: #fff;
}
.navbar-inverse .btn-link[disabled]:hover,
fieldset[disabled] .navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link[disabled]:focus,
fieldset[disabled] .navbar-inverse .btn-link:focus {
  color: #444;
}
.breadcrumb {
  padding: 8px 15px;
  margin-bottom: 18px;
  list-style: none;
  background-color: #f5f5f5;
  border-radius: 2px;
}
.breadcrumb > li {
  display: inline-block;
}
.breadcrumb > li + li:before {
  content: "/\00a0";
  padding: 0 5px;
  color: #5e5e5e;
}
.breadcrumb > .active {
  color: #777777;
}
.pagination {
  display: inline-block;
  padding-left: 0;
  margin: 18px 0;
  border-radius: 2px;
}
.pagination > li {
  display: inline;
}
.pagination > li > a,
.pagination > li > span {
  position: relative;
  float: left;
  padding: 6px 12px;
  line-height: 1.42857143;
  text-decoration: none;
  color: #337ab7;
  background-color: #fff;
  border: 1px solid #ddd;
  margin-left: -1px;
}
.pagination > li:first-child > a,
.pagination > li:first-child > span {
  margin-left: 0;
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.pagination > li:last-child > a,
.pagination > li:last-child > span {
  border-bottom-right-radius: 2px;
  border-top-right-radius: 2px;
}
.pagination > li > a:hover,
.pagination > li > span:hover,
.pagination > li > a:focus,
.pagination > li > span:focus {
  z-index: 2;
  color: #23527c;
  background-color: #eeeeee;
  border-color: #ddd;
}
.pagination > .active > a,
.pagination > .active > span,
.pagination > .active > a:hover,
.pagination > .active > span:hover,
.pagination > .active > a:focus,
.pagination > .active > span:focus {
  z-index: 3;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
  cursor: default;
}
.pagination > .disabled > span,
.pagination > .disabled > span:hover,
.pagination > .disabled > span:focus,
.pagination > .disabled > a,
.pagination > .disabled > a:hover,
.pagination > .disabled > a:focus {
  color: #777777;
  background-color: #fff;
  border-color: #ddd;
  cursor: not-allowed;
}
.pagination-lg > li > a,
.pagination-lg > li > span {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.pagination-lg > li:first-child > a,
.pagination-lg > li:first-child > span {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}
.pagination-lg > li:last-child > a,
.pagination-lg > li:last-child > span {
  border-bottom-right-radius: 3px;
  border-top-right-radius: 3px;
}
.pagination-sm > li > a,
.pagination-sm > li > span {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.pagination-sm > li:first-child > a,
.pagination-sm > li:first-child > span {
  border-bottom-left-radius: 1px;
  border-top-left-radius: 1px;
}
.pagination-sm > li:last-child > a,
.pagination-sm > li:last-child > span {
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
.pager {
  padding-left: 0;
  margin: 18px 0;
  list-style: none;
  text-align: center;
}
.pager li {
  display: inline;
}
.pager li > a,
.pager li > span {
  display: inline-block;
  padding: 5px 14px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 15px;
}
.pager li > a:hover,
.pager li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.pager .next > a,
.pager .next > span {
  float: right;
}
.pager .previous > a,
.pager .previous > span {
  float: left;
}
.pager .disabled > a,
.pager .disabled > a:hover,
.pager .disabled > a:focus,
.pager .disabled > span {
  color: #777777;
  background-color: #fff;
  cursor: not-allowed;
}
.label {
  display: inline;
  padding: .2em .6em .3em;
  font-size: 75%;
  font-weight: bold;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: .25em;
}
a.label:hover,
a.label:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.label:empty {
  display: none;
}
.btn .label {
  position: relative;
  top: -1px;
}
.label-default {
  background-color: #777777;
}
.label-default[href]:hover,
.label-default[href]:focus {
  background-color: #5e5e5e;
}
.label-primary {
  background-color: #337ab7;
}
.label-primary[href]:hover,
.label-primary[href]:focus {
  background-color: #286090;
}
.label-success {
  background-color: #5cb85c;
}
.label-success[href]:hover,
.label-success[href]:focus {
  background-color: #449d44;
}
.label-info {
  background-color: #5bc0de;
}
.label-info[href]:hover,
.label-info[href]:focus {
  background-color: #31b0d5;
}
.label-warning {
  background-color: #f0ad4e;
}
.label-warning[href]:hover,
.label-warning[href]:focus {
  background-color: #ec971f;
}
.label-danger {
  background-color: #d9534f;
}
.label-danger[href]:hover,
.label-danger[href]:focus {
  background-color: #c9302c;
}
.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  line-height: 1;
  vertical-align: middle;
  white-space: nowrap;
  text-align: center;
  background-color: #777777;
  border-radius: 10px;
}
.badge:empty {
  display: none;
}
.btn .badge {
  position: relative;
  top: -1px;
}
.btn-xs .badge,
.btn-group-xs > .btn .badge {
  top: 0;
  padding: 1px 5px;
}
a.badge:hover,
a.badge:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.list-group-item.active > .badge,
.nav-pills > .active > a > .badge {
  color: #337ab7;
  background-color: #fff;
}
.list-group-item > .badge {
  float: right;
}
.list-group-item > .badge + .badge {
  margin-right: 5px;
}
.nav-pills > li > a > .badge {
  margin-left: 3px;
}
.jumbotron {
  padding-top: 30px;
  padding-bottom: 30px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eeeeee;
}
.jumbotron h1,
.jumbotron .h1 {
  color: inherit;
}
.jumbotron p {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: 200;
}
.jumbotron > hr {
  border-top-color: #d5d5d5;
}
.container .jumbotron,
.container-fluid .jumbotron {
  border-radius: 3px;
  padding-left: 0px;
  padding-right: 0px;
}
.jumbotron .container {
  max-width: 100%;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding-top: 48px;
    padding-bottom: 48px;
  }
  .container .jumbotron,
  .container-fluid .jumbotron {
    padding-left: 60px;
    padding-right: 60px;
  }
  .jumbotron h1,
  .jumbotron .h1 {
    font-size: 59px;
  }
}
.thumbnail {
  display: block;
  padding: 4px;
  margin-bottom: 18px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: border 0.2s ease-in-out;
  -o-transition: border 0.2s ease-in-out;
  transition: border 0.2s ease-in-out;
}
.thumbnail > img,
.thumbnail a > img {
  margin-left: auto;
  margin-right: auto;
}
a.thumbnail:hover,
a.thumbnail:focus,
a.thumbnail.active {
  border-color: #337ab7;
}
.thumbnail .caption {
  padding: 9px;
  color: #000;
}
.alert {
  padding: 15px;
  margin-bottom: 18px;
  border: 1px solid transparent;
  border-radius: 2px;
}
.alert h4 {
  margin-top: 0;
  color: inherit;
}
.alert .alert-link {
  font-weight: bold;
}
.alert > p,
.alert > ul {
  margin-bottom: 0;
}
.alert > p + p {
  margin-top: 5px;
}
.alert-dismissable,
.alert-dismissible {
  padding-right: 35px;
}
.alert-dismissable .close,
.alert-dismissible .close {
  position: relative;
  top: -2px;
  right: -21px;
  color: inherit;
}
.alert-success {
  background-color: #dff0d8;
  border-color: #d6e9c6;
  color: #3c763d;
}
.alert-success hr {
  border-top-color: #c9e2b3;
}
.alert-success .alert-link {
  color: #2b542c;
}
.alert-info {
  background-color: #d9edf7;
  border-color: #bce8f1;
  color: #31708f;
}
.alert-info hr {
  border-top-color: #a6e1ec;
}
.alert-info .alert-link {
  color: #245269;
}
.alert-warning {
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}
.alert-warning hr {
  border-top-color: #f7e1b5;
}
.alert-warning .alert-link {
  color: #66512c;
}
.alert-danger {
  background-color: #f2dede;
  border-color: #ebccd1;
  color: #a94442;
}
.alert-danger hr {
  border-top-color: #e4b9c0;
}
.alert-danger .alert-link {
  color: #843534;
}
@-webkit-keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
@keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
.progress {
  overflow: hidden;
  height: 18px;
  margin-bottom: 18px;
  background-color: #f5f5f5;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 18px;
  color: #fff;
  text-align: center;
  background-color: #337ab7;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  -o-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.progress-striped .progress-bar,
.progress-bar-striped {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 40px 40px;
}
.progress.active .progress-bar,
.progress-bar.active {
  -webkit-animation: progress-bar-stripes 2s linear infinite;
  -o-animation: progress-bar-stripes 2s linear infinite;
  animation: progress-bar-stripes 2s linear infinite;
}
.progress-bar-success {
  background-color: #5cb85c;
}
.progress-striped .progress-bar-success {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-info {
  background-color: #5bc0de;
}
.progress-striped .progress-bar-info {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-warning {
  background-color: #f0ad4e;
}
.progress-striped .progress-bar-warning {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-danger {
  background-color: #d9534f;
}
.progress-striped .progress-bar-danger {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.media {
  margin-top: 15px;
}
.media:first-child {
  margin-top: 0;
}
.media,
.media-body {
  zoom: 1;
  overflow: hidden;
}
.media-body {
  width: 10000px;
}
.media-object {
  display: block;
}
.media-object.img-thumbnail {
  max-width: none;
}
.media-right,
.media > .pull-right {
  padding-left: 10px;
}
.media-left,
.media > .pull-left {
  padding-right: 10px;
}
.media-left,
.media-right,
.media-body {
  display: table-cell;
  vertical-align: top;
}
.media-middle {
  vertical-align: middle;
}
.media-bottom {
  vertical-align: bottom;
}
.media-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.media-list {
  padding-left: 0;
  list-style: none;
}
.list-group {
  margin-bottom: 20px;
  padding-left: 0;
}
.list-group-item {
  position: relative;
  display: block;
  padding: 10px 15px;
  margin-bottom: -1px;
  background-color: #fff;
  border: 1px solid #ddd;
}
.list-group-item:first-child {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
}
.list-group-item:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
a.list-group-item,
button.list-group-item {
  color: #555;
}
a.list-group-item .list-group-item-heading,
button.list-group-item .list-group-item-heading {
  color: #333;
}
a.list-group-item:hover,
button.list-group-item:hover,
a.list-group-item:focus,
button.list-group-item:focus {
  text-decoration: none;
  color: #555;
  background-color: #f5f5f5;
}
button.list-group-item {
  width: 100%;
  text-align: left;
}
.list-group-item.disabled,
.list-group-item.disabled:hover,
.list-group-item.disabled:focus {
  background-color: #eeeeee;
  color: #777777;
  cursor: not-allowed;
}
.list-group-item.disabled .list-group-item-heading,
.list-group-item.disabled:hover .list-group-item-heading,
.list-group-item.disabled:focus .list-group-item-heading {
  color: inherit;
}
.list-group-item.disabled .list-group-item-text,
.list-group-item.disabled:hover .list-group-item-text,
.list-group-item.disabled:focus .list-group-item-text {
  color: #777777;
}
.list-group-item.active,
.list-group-item.active:hover,
.list-group-item.active:focus {
  z-index: 2;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.list-group-item.active .list-group-item-heading,
.list-group-item.active:hover .list-group-item-heading,
.list-group-item.active:focus .list-group-item-heading,
.list-group-item.active .list-group-item-heading > small,
.list-group-item.active:hover .list-group-item-heading > small,
.list-group-item.active:focus .list-group-item-heading > small,
.list-group-item.active .list-group-item-heading > .small,
.list-group-item.active:hover .list-group-item-heading > .small,
.list-group-item.active:focus .list-group-item-heading > .small {
  color: inherit;
}
.list-group-item.active .list-group-item-text,
.list-group-item.active:hover .list-group-item-text,
.list-group-item.active:focus .list-group-item-text {
  color: #c7ddef;
}
.list-group-item-success {
  color: #3c763d;
  background-color: #dff0d8;
}
a.list-group-item-success,
button.list-group-item-success {
  color: #3c763d;
}
a.list-group-item-success .list-group-item-heading,
button.list-group-item-success .list-group-item-heading {
  color: inherit;
}
a.list-group-item-success:hover,
button.list-group-item-success:hover,
a.list-group-item-success:focus,
button.list-group-item-success:focus {
  color: #3c763d;
  background-color: #d0e9c6;
}
a.list-group-item-success.active,
button.list-group-item-success.active,
a.list-group-item-success.active:hover,
button.list-group-item-success.active:hover,
a.list-group-item-success.active:focus,
button.list-group-item-success.active:focus {
  color: #fff;
  background-color: #3c763d;
  border-color: #3c763d;
}
.list-group-item-info {
  color: #31708f;
  background-color: #d9edf7;
}
a.list-group-item-info,
button.list-group-item-info {
  color: #31708f;
}
a.list-group-item-info .list-group-item-heading,
button.list-group-item-info .list-group-item-heading {
  color: inherit;
}
a.list-group-item-info:hover,
button.list-group-item-info:hover,
a.list-group-item-info:focus,
button.list-group-item-info:focus {
  color: #31708f;
  background-color: #c4e3f3;
}
a.list-group-item-info.active,
button.list-group-item-info.active,
a.list-group-item-info.active:hover,
button.list-group-item-info.active:hover,
a.list-group-item-info.active:focus,
button.list-group-item-info.active:focus {
  color: #fff;
  background-color: #31708f;
  border-color: #31708f;
}
.list-group-item-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
a.list-group-item-warning,
button.list-group-item-warning {
  color: #8a6d3b;
}
a.list-group-item-warning .list-group-item-heading,
button.list-group-item-warning .list-group-item-heading {
  color: inherit;
}
a.list-group-item-warning:hover,
button.list-group-item-warning:hover,
a.list-group-item-warning:focus,
button.list-group-item-warning:focus {
  color: #8a6d3b;
  background-color: #faf2cc;
}
a.list-group-item-warning.active,
button.list-group-item-warning.active,
a.list-group-item-warning.active:hover,
button.list-group-item-warning.active:hover,
a.list-group-item-warning.active:focus,
button.list-group-item-warning.active:focus {
  color: #fff;
  background-color: #8a6d3b;
  border-color: #8a6d3b;
}
.list-group-item-danger {
  color: #a94442;
  background-color: #f2dede;
}
a.list-group-item-danger,
button.list-group-item-danger {
  color: #a94442;
}
a.list-group-item-danger .list-group-item-heading,
button.list-group-item-danger .list-group-item-heading {
  color: inherit;
}
a.list-group-item-danger:hover,
button.list-group-item-danger:hover,
a.list-group-item-danger:focus,
button.list-group-item-danger:focus {
  color: #a94442;
  background-color: #ebcccc;
}
a.list-group-item-danger.active,
button.list-group-item-danger.active,
a.list-group-item-danger.active:hover,
button.list-group-item-danger.active:hover,
a.list-group-item-danger.active:focus,
button.list-group-item-danger.active:focus {
  color: #fff;
  background-color: #a94442;
  border-color: #a94442;
}
.list-group-item-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.list-group-item-text {
  margin-bottom: 0;
  line-height: 1.3;
}
.panel {
  margin-bottom: 18px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
.panel-body {
  padding: 15px;
}
.panel-heading {
  padding: 10px 15px;
  border-bottom: 1px solid transparent;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel-heading > .dropdown .dropdown-toggle {
  color: inherit;
}
.panel-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 15px;
  color: inherit;
}
.panel-title > a,
.panel-title > small,
.panel-title > .small,
.panel-title > small > a,
.panel-title > .small > a {
  color: inherit;
}
.panel-footer {
  padding: 10px 15px;
  background-color: #f5f5f5;
  border-top: 1px solid #ddd;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .list-group,
.panel > .panel-collapse > .list-group {
  margin-bottom: 0;
}
.panel > .list-group .list-group-item,
.panel > .panel-collapse > .list-group .list-group-item {
  border-width: 1px 0;
  border-radius: 0;
}
.panel > .list-group:first-child .list-group-item:first-child,
.panel > .panel-collapse > .list-group:first-child .list-group-item:first-child {
  border-top: 0;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .list-group:last-child .list-group-item:last-child,
.panel > .panel-collapse > .list-group:last-child .list-group-item:last-child {
  border-bottom: 0;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .panel-heading + .panel-collapse > .list-group .list-group-item:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.panel-heading + .list-group .list-group-item:first-child {
  border-top-width: 0;
}
.list-group + .panel-footer {
  border-top-width: 0;
}
.panel > .table,
.panel > .table-responsive > .table,
.panel > .panel-collapse > .table {
  margin-bottom: 0;
}
.panel > .table caption,
.panel > .table-responsive > .table caption,
.panel > .panel-collapse > .table caption {
  padding-left: 15px;
  padding-right: 15px;
}
.panel > .table:first-child,
.panel > .table-responsive:first-child > .table:first-child {
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child {
  border-top-left-radius: 1px;
  border-top-right-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:first-child {
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:last-child {
  border-top-right-radius: 1px;
}
.panel > .table:last-child,
.panel > .table-responsive:last-child > .table:last-child {
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child {
  border-bottom-left-radius: 1px;
  border-bottom-right-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:first-child {
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:last-child {
  border-bottom-right-radius: 1px;
}
.panel > .panel-body + .table,
.panel > .panel-body + .table-responsive,
.panel > .table + .panel-body,
.panel > .table-responsive + .panel-body {
  border-top: 1px solid #ddd;
}
.panel > .table > tbody:first-child > tr:first-child th,
.panel > .table > tbody:first-child > tr:first-child td {
  border-top: 0;
}
.panel > .table-bordered,
.panel > .table-responsive > .table-bordered {
  border: 0;
}
.panel > .table-bordered > thead > tr > th:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:first-child,
.panel > .table-bordered > tbody > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:first-child,
.panel > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-bordered > thead > tr > td:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:first-child,
.panel > .table-bordered > tbody > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:first-child,
.panel > .table-bordered > tfoot > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:first-child {
  border-left: 0;
}
.panel > .table-bordered > thead > tr > th:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:last-child,
.panel > .table-bordered > tbody > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:last-child,
.panel > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-bordered > thead > tr > td:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:last-child,
.panel > .table-bordered > tbody > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:last-child,
.panel > .table-bordered > tfoot > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:last-child {
  border-right: 0;
}
.panel > .table-bordered > thead > tr:first-child > td,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > td,
.panel > .table-bordered > tbody > tr:first-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > td,
.panel > .table-bordered > thead > tr:first-child > th,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > th,
.panel > .table-bordered > tbody > tr:first-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > th {
  border-bottom: 0;
}
.panel > .table-bordered > tbody > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > td,
.panel > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-bordered > tbody > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > th,
.panel > .table-bordered > tfoot > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > th {
  border-bottom: 0;
}
.panel > .table-responsive {
  border: 0;
  margin-bottom: 0;
}
.panel-group {
  margin-bottom: 18px;
}
.panel-group .panel {
  margin-bottom: 0;
  border-radius: 2px;
}
.panel-group .panel + .panel {
  margin-top: 5px;
}
.panel-group .panel-heading {
  border-bottom: 0;
}
.panel-group .panel-heading + .panel-collapse > .panel-body,
.panel-group .panel-heading + .panel-collapse > .list-group {
  border-top: 1px solid #ddd;
}
.panel-group .panel-footer {
  border-top: 0;
}
.panel-group .panel-footer + .panel-collapse .panel-body {
  border-bottom: 1px solid #ddd;
}
.panel-default {
  border-color: #ddd;
}
.panel-default > .panel-heading {
  color: #333333;
  background-color: #f5f5f5;
  border-color: #ddd;
}
.panel-default > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ddd;
}
.panel-default > .panel-heading .badge {
  color: #f5f5f5;
  background-color: #333333;
}
.panel-default > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ddd;
}
.panel-primary {
  border-color: #337ab7;
}
.panel-primary > .panel-heading {
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.panel-primary > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #337ab7;
}
.panel-primary > .panel-heading .badge {
  color: #337ab7;
  background-color: #fff;
}
.panel-primary > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #337ab7;
}
.panel-success {
  border-color: #d6e9c6;
}
.panel-success > .panel-heading {
  color: #3c763d;
  background-color: #dff0d8;
  border-color: #d6e9c6;
}
.panel-success > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #d6e9c6;
}
.panel-success > .panel-heading .badge {
  color: #dff0d8;
  background-color: #3c763d;
}
.panel-success > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #d6e9c6;
}
.panel-info {
  border-color: #bce8f1;
}
.panel-info > .panel-heading {
  color: #31708f;
  background-color: #d9edf7;
  border-color: #bce8f1;
}
.panel-info > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #bce8f1;
}
.panel-info > .panel-heading .badge {
  color: #d9edf7;
  background-color: #31708f;
}
.panel-info > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #bce8f1;
}
.panel-warning {
  border-color: #faebcc;
}
.panel-warning > .panel-heading {
  color: #8a6d3b;
  background-color: #fcf8e3;
  border-color: #faebcc;
}
.panel-warning > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #faebcc;
}
.panel-warning > .panel-heading .badge {
  color: #fcf8e3;
  background-color: #8a6d3b;
}
.panel-warning > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #faebcc;
}
.panel-danger {
  border-color: #ebccd1;
}
.panel-danger > .panel-heading {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.panel-danger > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ebccd1;
}
.panel-danger > .panel-heading .badge {
  color: #f2dede;
  background-color: #a94442;
}
.panel-danger > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ebccd1;
}
.embed-responsive {
  position: relative;
  display: block;
  height: 0;
  padding: 0;
  overflow: hidden;
}
.embed-responsive .embed-responsive-item,
.embed-responsive iframe,
.embed-responsive embed,
.embed-responsive object,
.embed-responsive video {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  border: 0;
}
.embed-responsive-16by9 {
  padding-bottom: 56.25%;
}
.embed-responsive-4by3 {
  padding-bottom: 75%;
}
.well {
  min-height: 20px;
  padding: 19px;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border: 1px solid #e3e3e3;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
}
.well blockquote {
  border-color: #ddd;
  border-color: rgba(0, 0, 0, 0.15);
}
.well-lg {
  padding: 24px;
  border-radius: 3px;
}
.well-sm {
  padding: 9px;
  border-radius: 1px;
}
.close {
  float: right;
  font-size: 19.5px;
  font-weight: bold;
  line-height: 1;
  color: #000;
  text-shadow: 0 1px 0 #fff;
  opacity: 0.2;
  filter: alpha(opacity=20);
}
.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.5;
  filter: alpha(opacity=50);
}
button.close {
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 0;
  -webkit-appearance: none;
}
.modal-open {
  overflow: hidden;
}
.modal {
  display: none;
  overflow: hidden;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, -25%);
  -ms-transform: translate(0, -25%);
  -o-transform: translate(0, -25%);
  transform: translate(0, -25%);
  -webkit-transition: -webkit-transform 0.3s ease-out;
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  transition: transform 0.3s ease-out;
}
.modal.in .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
.modal-open .modal {
  overflow-x: hidden;
  overflow-y: auto;
}
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
.modal-content {
  position: relative;
  background-color: #fff;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  outline: 0;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
.modal-backdrop.fade {
  opacity: 0;
  filter: alpha(opacity=0);
}
.modal-backdrop.in {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
.modal-header {
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
.modal-footer .btn + .btn {
  margin-left: 5px;
  margin-bottom: 0;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
.modal-scrollbar-measure {
  position: absolute;
  top: -9999px;
  width: 50px;
  height: 50px;
  overflow: scroll;
}
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }
  .modal-sm {
    width: 300px;
  }
}
@media (min-width: 992px) {
  .modal-lg {
    width: 900px;
  }
}
.tooltip {
  position: absolute;
  z-index: 1070;
  display: block;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 12px;
  opacity: 0;
  filter: alpha(opacity=0);
}
.tooltip.in {
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.tooltip.top {
  margin-top: -3px;
  padding: 5px 0;
}
.tooltip.right {
  margin-left: 3px;
  padding: 0 5px;
}
.tooltip.bottom {
  margin-top: 3px;
  padding: 5px 0;
}
.tooltip.left {
  margin-left: -3px;
  padding: 0 5px;
}
.tooltip-inner {
  max-width: 200px;
  padding: 3px 8px;
  color: #fff;
  text-align: center;
  background-color: #000;
  border-radius: 2px;
}
.tooltip-arrow {
  position: absolute;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.tooltip.top .tooltip-arrow {
  bottom: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-left .tooltip-arrow {
  bottom: 0;
  right: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-right .tooltip-arrow {
  bottom: 0;
  left: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.right .tooltip-arrow {
  top: 50%;
  left: 0;
  margin-top: -5px;
  border-width: 5px 5px 5px 0;
  border-right-color: #000;
}
.tooltip.left .tooltip-arrow {
  top: 50%;
  right: 0;
  margin-top: -5px;
  border-width: 5px 0 5px 5px;
  border-left-color: #000;
}
.tooltip.bottom .tooltip-arrow {
  top: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-left .tooltip-arrow {
  top: 0;
  right: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-right .tooltip-arrow {
  top: 0;
  left: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.popover {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1060;
  display: none;
  max-width: 276px;
  padding: 1px;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 13px;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
.popover.top {
  margin-top: -10px;
}
.popover.right {
  margin-left: 10px;
}
.popover.bottom {
  margin-top: 10px;
}
.popover.left {
  margin-left: -10px;
}
.popover-title {
  margin: 0;
  padding: 8px 14px;
  font-size: 13px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #ebebeb;
  border-radius: 2px 2px 0 0;
}
.popover-content {
  padding: 9px 14px;
}
.popover > .arrow,
.popover > .arrow:after {
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.popover > .arrow {
  border-width: 11px;
}
.popover > .arrow:after {
  border-width: 10px;
  content: "";
}
.popover.top > .arrow {
  left: 50%;
  margin-left: -11px;
  border-bottom-width: 0;
  border-top-color: #999999;
  border-top-color: rgba(0, 0, 0, 0.25);
  bottom: -11px;
}
.popover.top > .arrow:after {
  content: " ";
  bottom: 1px;
  margin-left: -10px;
  border-bottom-width: 0;
  border-top-color: #fff;
}
.popover.right > .arrow {
  top: 50%;
  left: -11px;
  margin-top: -11px;
  border-left-width: 0;
  border-right-color: #999999;
  border-right-color: rgba(0, 0, 0, 0.25);
}
.popover.right > .arrow:after {
  content: " ";
  left: 1px;
  bottom: -10px;
  border-left-width: 0;
  border-right-color: #fff;
}
.popover.bottom > .arrow {
  left: 50%;
  margin-left: -11px;
  border-top-width: 0;
  border-bottom-color: #999999;
  border-bottom-color: rgba(0, 0, 0, 0.25);
  top: -11px;
}
.popover.bottom > .arrow:after {
  content: " ";
  top: 1px;
  margin-left: -10px;
  border-top-width: 0;
  border-bottom-color: #fff;
}
.popover.left > .arrow {
  top: 50%;
  right: -11px;
  margin-top: -11px;
  border-right-width: 0;
  border-left-color: #999999;
  border-left-color: rgba(0, 0, 0, 0.25);
}
.popover.left > .arrow:after {
  content: " ";
  right: 1px;
  border-right-width: 0;
  border-left-color: #fff;
  bottom: -10px;
}
.carousel {
  position: relative;
}
.carousel-inner {
  position: relative;
  overflow: hidden;
  width: 100%;
}
.carousel-inner > .item {
  display: none;
  position: relative;
  -webkit-transition: 0.6s ease-in-out left;
  -o-transition: 0.6s ease-in-out left;
  transition: 0.6s ease-in-out left;
}
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  line-height: 1;
}
@media all and (transform-3d), (-webkit-transform-3d) {
  .carousel-inner > .item {
    -webkit-transition: -webkit-transform 0.6s ease-in-out;
    -moz-transition: -moz-transform 0.6s ease-in-out;
    -o-transition: -o-transform 0.6s ease-in-out;
    transition: transform 0.6s ease-in-out;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-perspective: 1000px;
    -moz-perspective: 1000px;
    perspective: 1000px;
  }
  .carousel-inner > .item.next,
  .carousel-inner > .item.active.right {
    -webkit-transform: translate3d(100%, 0, 0);
    transform: translate3d(100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.prev,
  .carousel-inner > .item.active.left {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.next.left,
  .carousel-inner > .item.prev.right,
  .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
.carousel-inner > .active,
.carousel-inner > .next,
.carousel-inner > .prev {
  display: block;
}
.carousel-inner > .active {
  left: 0;
}
.carousel-inner > .next,
.carousel-inner > .prev {
  position: absolute;
  top: 0;
  width: 100%;
}
.carousel-inner > .next {
  left: 100%;
}
.carousel-inner > .prev {
  left: -100%;
}
.carousel-inner > .next.left,
.carousel-inner > .prev.right {
  left: 0;
}
.carousel-inner > .active.left {
  left: -100%;
}
.carousel-inner > .active.right {
  left: 100%;
}
.carousel-control {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  width: 15%;
  opacity: 0.5;
  filter: alpha(opacity=50);
  font-size: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
  background-color: rgba(0, 0, 0, 0);
}
.carousel-control.left {
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#80000000', endColorstr='#00000000', GradientType=1);
}
.carousel-control.right {
  left: auto;
  right: 0;
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000', endColorstr='#80000000', GradientType=1);
}
.carousel-control:hover,
.carousel-control:focus {
  outline: 0;
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.carousel-control .icon-prev,
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-left,
.carousel-control .glyphicon-chevron-right {
  position: absolute;
  top: 50%;
  margin-top: -10px;
  z-index: 5;
  display: inline-block;
}
.carousel-control .icon-prev,
.carousel-control .glyphicon-chevron-left {
  left: 50%;
  margin-left: -10px;
}
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-right {
  right: 50%;
  margin-right: -10px;
}
.carousel-control .icon-prev,
.carousel-control .icon-next {
  width: 20px;
  height: 20px;
  line-height: 1;
  font-family: serif;
}
.carousel-control .icon-prev:before {
  content: '\2039';
}
.carousel-control .icon-next:before {
  content: '\203a';
}
.carousel-indicators {
  position: absolute;
  bottom: 10px;
  left: 50%;
  z-index: 15;
  width: 60%;
  margin-left: -30%;
  padding-left: 0;
  list-style: none;
  text-align: center;
}
.carousel-indicators li {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 1px;
  text-indent: -999px;
  border: 1px solid #fff;
  border-radius: 10px;
  cursor: pointer;
  background-color: #000 \9;
  background-color: rgba(0, 0, 0, 0);
}
.carousel-indicators .active {
  margin: 0;
  width: 12px;
  height: 12px;
  background-color: #fff;
}
.carousel-caption {
  position: absolute;
  left: 15%;
  right: 15%;
  bottom: 20px;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
}
.carousel-caption .btn {
  text-shadow: none;
}
@media screen and (min-width: 768px) {
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-prev,
  .carousel-control .icon-next {
    width: 30px;
    height: 30px;
    margin-top: -10px;
    font-size: 30px;
  }
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .icon-prev {
    margin-left: -10px;
  }
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-next {
    margin-right: -10px;
  }
  .carousel-caption {
    left: 20%;
    right: 20%;
    padding-bottom: 30px;
  }
  .carousel-indicators {
    bottom: 20px;
  }
}
.clearfix:before,
.clearfix:after,
.dl-horizontal dd:before,
.dl-horizontal dd:after,
.container:before,
.container:after,
.container-fluid:before,
.container-fluid:after,
.row:before,
.row:after,
.form-horizontal .form-group:before,
.form-horizontal .form-group:after,
.btn-toolbar:before,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:before,
.btn-group-vertical > .btn-group:after,
.nav:before,
.nav:after,
.navbar:before,
.navbar:after,
.navbar-header:before,
.navbar-header:after,
.navbar-collapse:before,
.navbar-collapse:after,
.pager:before,
.pager:after,
.panel-body:before,
.panel-body:after,
.modal-header:before,
.modal-header:after,
.modal-footer:before,
.modal-footer:after,
.item_buttons:before,
.item_buttons:after {
  content: " ";
  display: table;
}
.clearfix:after,
.dl-horizontal dd:after,
.container:after,
.container-fluid:after,
.row:after,
.form-horizontal .form-group:after,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:after,
.nav:after,
.navbar:after,
.navbar-header:after,
.navbar-collapse:after,
.pager:after,
.panel-body:after,
.modal-header:after,
.modal-footer:after,
.item_buttons:after {
  clear: both;
}
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.pull-right {
  float: right !important;
}
.pull-left {
  float: left !important;
}
.hide {
  display: none !important;
}
.show {
  display: block !important;
}
.invisible {
  visibility: hidden;
}
.text-hide {
  font: 0/0 a;
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
.hidden {
  display: none !important;
}
.affix {
  position: fixed;
}
@-ms-viewport {
  width: device-width;
}
.visible-xs,
.visible-sm,
.visible-md,
.visible-lg {
  display: none !important;
}
.visible-xs-block,
.visible-xs-inline,
.visible-xs-inline-block,
.visible-sm-block,
.visible-sm-inline,
.visible-sm-inline-block,
.visible-md-block,
.visible-md-inline,
.visible-md-inline-block,
.visible-lg-block,
.visible-lg-inline,
.visible-lg-inline-block {
  display: none !important;
}
@media (max-width: 767px) {
  .visible-xs {
    display: block !important;
  }
  table.visible-xs {
    display: table !important;
  }
  tr.visible-xs {
    display: table-row !important;
  }
  th.visible-xs,
  td.visible-xs {
    display: table-cell !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-block {
    display: block !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline {
    display: inline !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm {
    display: block !important;
  }
  table.visible-sm {
    display: table !important;
  }
  tr.visible-sm {
    display: table-row !important;
  }
  th.visible-sm,
  td.visible-sm {
    display: table-cell !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-block {
    display: block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline {
    display: inline !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md {
    display: block !important;
  }
  table.visible-md {
    display: table !important;
  }
  tr.visible-md {
    display: table-row !important;
  }
  th.visible-md,
  td.visible-md {
    display: table-cell !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-block {
    display: block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline {
    display: inline !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg {
    display: block !important;
  }
  table.visible-lg {
    display: table !important;
  }
  tr.visible-lg {
    display: table-row !important;
  }
  th.visible-lg,
  td.visible-lg {
    display: table-cell !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-block {
    display: block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline {
    display: inline !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline-block {
    display: inline-block !important;
  }
}
@media (max-width: 767px) {
  .hidden-xs {
    display: none !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .hidden-sm {
    display: none !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .hidden-md {
    display: none !important;
  }
}
@media (min-width: 1200px) {
  .hidden-lg {
    display: none !important;
  }
}
.visible-print {
  display: none !important;
}
@media print {
  .visible-print {
    display: block !important;
  }
  table.visible-print {
    display: table !important;
  }
  tr.visible-print {
    display: table-row !important;
  }
  th.visible-print,
  td.visible-print {
    display: table-cell !important;
  }
}
.visible-print-block {
  display: none !important;
}
@media print {
  .visible-print-block {
    display: block !important;
  }
}
.visible-print-inline {
  display: none !important;
}
@media print {
  .visible-print-inline {
    display: inline !important;
  }
}
.visible-print-inline-block {
  display: none !important;
}
@media print {
  .visible-print-inline-block {
    display: inline-block !important;
  }
}
@media print {
  .hidden-print {
    display: none !important;
  }
}
/*!
*
* Font Awesome
*
*/
/*!
 *  Font Awesome 4.7.0 by @davegandy - http://fontawesome.io - @fontawesome
 *  License - http://fontawesome.io/license (Font: SIL OFL 1.1, CSS: MIT License)
 */
/* FONT PATH
 * -------------------------- */
@font-face {
  font-family: 'FontAwesome';
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?v=4.7.0');
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?#iefix&v=4.7.0') format('embedded-opentype'), url('../components/font-awesome/fonts/fontawesome-webfont.woff2?v=4.7.0') format('woff2'), url('../components/font-awesome/fonts/fontawesome-webfont.woff?v=4.7.0') format('woff'), url('../components/font-awesome/fonts/fontawesome-webfont.ttf?v=4.7.0') format('truetype'), url('../components/font-awesome/fonts/fontawesome-webfont.svg?v=4.7.0#fontawesomeregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
.fa {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/* makes the font 33% larger relative to the icon container */
.fa-lg {
  font-size: 1.33333333em;
  line-height: 0.75em;
  vertical-align: -15%;
}
.fa-2x {
  font-size: 2em;
}
.fa-3x {
  font-size: 3em;
}
.fa-4x {
  font-size: 4em;
}
.fa-5x {
  font-size: 5em;
}
.fa-fw {
  width: 1.28571429em;
  text-align: center;
}
.fa-ul {
  padding-left: 0;
  margin-left: 2.14285714em;
  list-style-type: none;
}
.fa-ul > li {
  position: relative;
}
.fa-li {
  position: absolute;
  left: -2.14285714em;
  width: 2.14285714em;
  top: 0.14285714em;
  text-align: center;
}
.fa-li.fa-lg {
  left: -1.85714286em;
}
.fa-border {
  padding: .2em .25em .15em;
  border: solid 0.08em #eee;
  border-radius: .1em;
}
.fa-pull-left {
  float: left;
}
.fa-pull-right {
  float: right;
}
.fa.fa-pull-left {
  margin-right: .3em;
}
.fa.fa-pull-right {
  margin-left: .3em;
}
/* Deprecated as of 4.4.0 */
.pull-right {
  float: right;
}
.pull-left {
  float: left;
}
.fa.pull-left {
  margin-right: .3em;
}
.fa.pull-right {
  margin-left: .3em;
}
.fa-spin {
  -webkit-animation: fa-spin 2s infinite linear;
  animation: fa-spin 2s infinite linear;
}
.fa-pulse {
  -webkit-animation: fa-spin 1s infinite steps(8);
  animation: fa-spin 1s infinite steps(8);
}
@-webkit-keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
@keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
.fa-rotate-90 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=1)";
  -webkit-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  transform: rotate(90deg);
}
.fa-rotate-180 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2)";
  -webkit-transform: rotate(180deg);
  -ms-transform: rotate(180deg);
  transform: rotate(180deg);
}
.fa-rotate-270 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=3)";
  -webkit-transform: rotate(270deg);
  -ms-transform: rotate(270deg);
  transform: rotate(270deg);
}
.fa-flip-horizontal {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=0, mirror=1)";
  -webkit-transform: scale(-1, 1);
  -ms-transform: scale(-1, 1);
  transform: scale(-1, 1);
}
.fa-flip-vertical {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2, mirror=1)";
  -webkit-transform: scale(1, -1);
  -ms-transform: scale(1, -1);
  transform: scale(1, -1);
}
:root .fa-rotate-90,
:root .fa-rotate-180,
:root .fa-rotate-270,
:root .fa-flip-horizontal,
:root .fa-flip-vertical {
  filter: none;
}
.fa-stack {
  position: relative;
  display: inline-block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  vertical-align: middle;
}
.fa-stack-1x,
.fa-stack-2x {
  position: absolute;
  left: 0;
  width: 100%;
  text-align: center;
}
.fa-stack-1x {
  line-height: inherit;
}
.fa-stack-2x {
  font-size: 2em;
}
.fa-inverse {
  color: #fff;
}
/* Font Awesome uses the Unicode Private Use Area (PUA) to ensure screen
   readers do not read off random characters that represent icons */
.fa-glass:before {
  content: "\f000";
}
.fa-music:before {
  content: "\f001";
}
.fa-search:before {
  content: "\f002";
}
.fa-envelope-o:before {
  content: "\f003";
}
.fa-heart:before {
  content: "\f004";
}
.fa-star:before {
  content: "\f005";
}
.fa-star-o:before {
  content: "\f006";
}
.fa-user:before {
  content: "\f007";
}
.fa-film:before {
  content: "\f008";
}
.fa-th-large:before {
  content: "\f009";
}
.fa-th:before {
  content: "\f00a";
}
.fa-th-list:before {
  content: "\f00b";
}
.fa-check:before {
  content: "\f00c";
}
.fa-remove:before,
.fa-close:before,
.fa-times:before {
  content: "\f00d";
}
.fa-search-plus:before {
  content: "\f00e";
}
.fa-search-minus:before {
  content: "\f010";
}
.fa-power-off:before {
  content: "\f011";
}
.fa-signal:before {
  content: "\f012";
}
.fa-gear:before,
.fa-cog:before {
  content: "\f013";
}
.fa-trash-o:before {
  content: "\f014";
}
.fa-home:before {
  content: "\f015";
}
.fa-file-o:before {
  content: "\f016";
}
.fa-clock-o:before {
  content: "\f017";
}
.fa-road:before {
  content: "\f018";
}
.fa-download:before {
  content: "\f019";
}
.fa-arrow-circle-o-down:before {
  content: "\f01a";
}
.fa-arrow-circle-o-up:before {
  content: "\f01b";
}
.fa-inbox:before {
  content: "\f01c";
}
.fa-play-circle-o:before {
  content: "\f01d";
}
.fa-rotate-right:before,
.fa-repeat:before {
  content: "\f01e";
}
.fa-refresh:before {
  content: "\f021";
}
.fa-list-alt:before {
  content: "\f022";
}
.fa-lock:before {
  content: "\f023";
}
.fa-flag:before {
  content: "\f024";
}
.fa-headphones:before {
  content: "\f025";
}
.fa-volume-off:before {
  content: "\f026";
}
.fa-volume-down:before {
  content: "\f027";
}
.fa-volume-up:before {
  content: "\f028";
}
.fa-qrcode:before {
  content: "\f029";
}
.fa-barcode:before {
  content: "\f02a";
}
.fa-tag:before {
  content: "\f02b";
}
.fa-tags:before {
  content: "\f02c";
}
.fa-book:before {
  content: "\f02d";
}
.fa-bookmark:before {
  content: "\f02e";
}
.fa-print:before {
  content: "\f02f";
}
.fa-camera:before {
  content: "\f030";
}
.fa-font:before {
  content: "\f031";
}
.fa-bold:before {
  content: "\f032";
}
.fa-italic:before {
  content: "\f033";
}
.fa-text-height:before {
  content: "\f034";
}
.fa-text-width:before {
  content: "\f035";
}
.fa-align-left:before {
  content: "\f036";
}
.fa-align-center:before {
  content: "\f037";
}
.fa-align-right:before {
  content: "\f038";
}
.fa-align-justify:before {
  content: "\f039";
}
.fa-list:before {
  content: "\f03a";
}
.fa-dedent:before,
.fa-outdent:before {
  content: "\f03b";
}
.fa-indent:before {
  content: "\f03c";
}
.fa-video-camera:before {
  content: "\f03d";
}
.fa-photo:before,
.fa-image:before,
.fa-picture-o:before {
  content: "\f03e";
}
.fa-pencil:before {
  content: "\f040";
}
.fa-map-marker:before {
  content: "\f041";
}
.fa-adjust:before {
  content: "\f042";
}
.fa-tint:before {
  content: "\f043";
}
.fa-edit:before,
.fa-pencil-square-o:before {
  content: "\f044";
}
.fa-share-square-o:before {
  content: "\f045";
}
.fa-check-square-o:before {
  content: "\f046";
}
.fa-arrows:before {
  content: "\f047";
}
.fa-step-backward:before {
  content: "\f048";
}
.fa-fast-backward:before {
  content: "\f049";
}
.fa-backward:before {
  content: "\f04a";
}
.fa-play:before {
  content: "\f04b";
}
.fa-pause:before {
  content: "\f04c";
}
.fa-stop:before {
  content: "\f04d";
}
.fa-forward:before {
  content: "\f04e";
}
.fa-fast-forward:before {
  content: "\f050";
}
.fa-step-forward:before {
  content: "\f051";
}
.fa-eject:before {
  content: "\f052";
}
.fa-chevron-left:before {
  content: "\f053";
}
.fa-chevron-right:before {
  content: "\f054";
}
.fa-plus-circle:before {
  content: "\f055";
}
.fa-minus-circle:before {
  content: "\f056";
}
.fa-times-circle:before {
  content: "\f057";
}
.fa-check-circle:before {
  content: "\f058";
}
.fa-question-circle:before {
  content: "\f059";
}
.fa-info-circle:before {
  content: "\f05a";
}
.fa-crosshairs:before {
  content: "\f05b";
}
.fa-times-circle-o:before {
  content: "\f05c";
}
.fa-check-circle-o:before {
  content: "\f05d";
}
.fa-ban:before {
  content: "\f05e";
}
.fa-arrow-left:before {
  content: "\f060";
}
.fa-arrow-right:before {
  content: "\f061";
}
.fa-arrow-up:before {
  content: "\f062";
}
.fa-arrow-down:before {
  content: "\f063";
}
.fa-mail-forward:before,
.fa-share:before {
  content: "\f064";
}
.fa-expand:before {
  content: "\f065";
}
.fa-compress:before {
  content: "\f066";
}
.fa-plus:before {
  content: "\f067";
}
.fa-minus:before {
  content: "\f068";
}
.fa-asterisk:before {
  content: "\f069";
}
.fa-exclamation-circle:before {
  content: "\f06a";
}
.fa-gift:before {
  content: "\f06b";
}
.fa-leaf:before {
  content: "\f06c";
}
.fa-fire:before {
  content: "\f06d";
}
.fa-eye:before {
  content: "\f06e";
}
.fa-eye-slash:before {
  content: "\f070";
}
.fa-warning:before,
.fa-exclamation-triangle:before {
  content: "\f071";
}
.fa-plane:before {
  content: "\f072";
}
.fa-calendar:before {
  content: "\f073";
}
.fa-random:before {
  content: "\f074";
}
.fa-comment:before {
  content: "\f075";
}
.fa-magnet:before {
  content: "\f076";
}
.fa-chevron-up:before {
  content: "\f077";
}
.fa-chevron-down:before {
  content: "\f078";
}
.fa-retweet:before {
  content: "\f079";
}
.fa-shopping-cart:before {
  content: "\f07a";
}
.fa-folder:before {
  content: "\f07b";
}
.fa-folder-open:before {
  content: "\f07c";
}
.fa-arrows-v:before {
  content: "\f07d";
}
.fa-arrows-h:before {
  content: "\f07e";
}
.fa-bar-chart-o:before,
.fa-bar-chart:before {
  content: "\f080";
}
.fa-twitter-square:before {
  content: "\f081";
}
.fa-facebook-square:before {
  content: "\f082";
}
.fa-camera-retro:before {
  content: "\f083";
}
.fa-key:before {
  content: "\f084";
}
.fa-gears:before,
.fa-cogs:before {
  content: "\f085";
}
.fa-comments:before {
  content: "\f086";
}
.fa-thumbs-o-up:before {
  content: "\f087";
}
.fa-thumbs-o-down:before {
  content: "\f088";
}
.fa-star-half:before {
  content: "\f089";
}
.fa-heart-o:before {
  content: "\f08a";
}
.fa-sign-out:before {
  content: "\f08b";
}
.fa-linkedin-square:before {
  content: "\f08c";
}
.fa-thumb-tack:before {
  content: "\f08d";
}
.fa-external-link:before {
  content: "\f08e";
}
.fa-sign-in:before {
  content: "\f090";
}
.fa-trophy:before {
  content: "\f091";
}
.fa-github-square:before {
  content: "\f092";
}
.fa-upload:before {
  content: "\f093";
}
.fa-lemon-o:before {
  content: "\f094";
}
.fa-phone:before {
  content: "\f095";
}
.fa-square-o:before {
  content: "\f096";
}
.fa-bookmark-o:before {
  content: "\f097";
}
.fa-phone-square:before {
  content: "\f098";
}
.fa-twitter:before {
  content: "\f099";
}
.fa-facebook-f:before,
.fa-facebook:before {
  content: "\f09a";
}
.fa-github:before {
  content: "\f09b";
}
.fa-unlock:before {
  content: "\f09c";
}
.fa-credit-card:before {
  content: "\f09d";
}
.fa-feed:before,
.fa-rss:before {
  content: "\f09e";
}
.fa-hdd-o:before {
  content: "\f0a0";
}
.fa-bullhorn:before {
  content: "\f0a1";
}
.fa-bell:before {
  content: "\f0f3";
}
.fa-certificate:before {
  content: "\f0a3";
}
.fa-hand-o-right:before {
  content: "\f0a4";
}
.fa-hand-o-left:before {
  content: "\f0a5";
}
.fa-hand-o-up:before {
  content: "\f0a6";
}
.fa-hand-o-down:before {
  content: "\f0a7";
}
.fa-arrow-circle-left:before {
  content: "\f0a8";
}
.fa-arrow-circle-right:before {
  content: "\f0a9";
}
.fa-arrow-circle-up:before {
  content: "\f0aa";
}
.fa-arrow-circle-down:before {
  content: "\f0ab";
}
.fa-globe:before {
  content: "\f0ac";
}
.fa-wrench:before {
  content: "\f0ad";
}
.fa-tasks:before {
  content: "\f0ae";
}
.fa-filter:before {
  content: "\f0b0";
}
.fa-briefcase:before {
  content: "\f0b1";
}
.fa-arrows-alt:before {
  content: "\f0b2";
}
.fa-group:before,
.fa-users:before {
  content: "\f0c0";
}
.fa-chain:before,
.fa-link:before {
  content: "\f0c1";
}
.fa-cloud:before {
  content: "\f0c2";
}
.fa-flask:before {
  content: "\f0c3";
}
.fa-cut:before,
.fa-scissors:before {
  content: "\f0c4";
}
.fa-copy:before,
.fa-files-o:before {
  content: "\f0c5";
}
.fa-paperclip:before {
  content: "\f0c6";
}
.fa-save:before,
.fa-floppy-o:before {
  content: "\f0c7";
}
.fa-square:before {
  content: "\f0c8";
}
.fa-navicon:before,
.fa-reorder:before,
.fa-bars:before {
  content: "\f0c9";
}
.fa-list-ul:before {
  content: "\f0ca";
}
.fa-list-ol:before {
  content: "\f0cb";
}
.fa-strikethrough:before {
  content: "\f0cc";
}
.fa-underline:before {
  content: "\f0cd";
}
.fa-table:before {
  content: "\f0ce";
}
.fa-magic:before {
  content: "\f0d0";
}
.fa-truck:before {
  content: "\f0d1";
}
.fa-pinterest:before {
  content: "\f0d2";
}
.fa-pinterest-square:before {
  content: "\f0d3";
}
.fa-google-plus-square:before {
  content: "\f0d4";
}
.fa-google-plus:before {
  content: "\f0d5";
}
.fa-money:before {
  content: "\f0d6";
}
.fa-caret-down:before {
  content: "\f0d7";
}
.fa-caret-up:before {
  content: "\f0d8";
}
.fa-caret-left:before {
  content: "\f0d9";
}
.fa-caret-right:before {
  content: "\f0da";
}
.fa-columns:before {
  content: "\f0db";
}
.fa-unsorted:before,
.fa-sort:before {
  content: "\f0dc";
}
.fa-sort-down:before,
.fa-sort-desc:before {
  content: "\f0dd";
}
.fa-sort-up:before,
.fa-sort-asc:before {
  content: "\f0de";
}
.fa-envelope:before {
  content: "\f0e0";
}
.fa-linkedin:before {
  content: "\f0e1";
}
.fa-rotate-left:before,
.fa-undo:before {
  content: "\f0e2";
}
.fa-legal:before,
.fa-gavel:before {
  content: "\f0e3";
}
.fa-dashboard:before,
.fa-tachometer:before {
  content: "\f0e4";
}
.fa-comment-o:before {
  content: "\f0e5";
}
.fa-comments-o:before {
  content: "\f0e6";
}
.fa-flash:before,
.fa-bolt:before {
  content: "\f0e7";
}
.fa-sitemap:before {
  content: "\f0e8";
}
.fa-umbrella:before {
  content: "\f0e9";
}
.fa-paste:before,
.fa-clipboard:before {
  content: "\f0ea";
}
.fa-lightbulb-o:before {
  content: "\f0eb";
}
.fa-exchange:before {
  content: "\f0ec";
}
.fa-cloud-download:before {
  content: "\f0ed";
}
.fa-cloud-upload:before {
  content: "\f0ee";
}
.fa-user-md:before {
  content: "\f0f0";
}
.fa-stethoscope:before {
  content: "\f0f1";
}
.fa-suitcase:before {
  content: "\f0f2";
}
.fa-bell-o:before {
  content: "\f0a2";
}
.fa-coffee:before {
  content: "\f0f4";
}
.fa-cutlery:before {
  content: "\f0f5";
}
.fa-file-text-o:before {
  content: "\f0f6";
}
.fa-building-o:before {
  content: "\f0f7";
}
.fa-hospital-o:before {
  content: "\f0f8";
}
.fa-ambulance:before {
  content: "\f0f9";
}
.fa-medkit:before {
  content: "\f0fa";
}
.fa-fighter-jet:before {
  content: "\f0fb";
}
.fa-beer:before {
  content: "\f0fc";
}
.fa-h-square:before {
  content: "\f0fd";
}
.fa-plus-square:before {
  content: "\f0fe";
}
.fa-angle-double-left:before {
  content: "\f100";
}
.fa-angle-double-right:before {
  content: "\f101";
}
.fa-angle-double-up:before {
  content: "\f102";
}
.fa-angle-double-down:before {
  content: "\f103";
}
.fa-angle-left:before {
  content: "\f104";
}
.fa-angle-right:before {
  content: "\f105";
}
.fa-angle-up:before {
  content: "\f106";
}
.fa-angle-down:before {
  content: "\f107";
}
.fa-desktop:before {
  content: "\f108";
}
.fa-laptop:before {
  content: "\f109";
}
.fa-tablet:before {
  content: "\f10a";
}
.fa-mobile-phone:before,
.fa-mobile:before {
  content: "\f10b";
}
.fa-circle-o:before {
  content: "\f10c";
}
.fa-quote-left:before {
  content: "\f10d";
}
.fa-quote-right:before {
  content: "\f10e";
}
.fa-spinner:before {
  content: "\f110";
}
.fa-circle:before {
  content: "\f111";
}
.fa-mail-reply:before,
.fa-reply:before {
  content: "\f112";
}
.fa-github-alt:before {
  content: "\f113";
}
.fa-folder-o:before {
  content: "\f114";
}
.fa-folder-open-o:before {
  content: "\f115";
}
.fa-smile-o:before {
  content: "\f118";
}
.fa-frown-o:before {
  content: "\f119";
}
.fa-meh-o:before {
  content: "\f11a";
}
.fa-gamepad:before {
  content: "\f11b";
}
.fa-keyboard-o:before {
  content: "\f11c";
}
.fa-flag-o:before {
  content: "\f11d";
}
.fa-flag-checkered:before {
  content: "\f11e";
}
.fa-terminal:before {
  content: "\f120";
}
.fa-code:before {
  content: "\f121";
}
.fa-mail-reply-all:before,
.fa-reply-all:before {
  content: "\f122";
}
.fa-star-half-empty:before,
.fa-star-half-full:before,
.fa-star-half-o:before {
  content: "\f123";
}
.fa-location-arrow:before {
  content: "\f124";
}
.fa-crop:before {
  content: "\f125";
}
.fa-code-fork:before {
  content: "\f126";
}
.fa-unlink:before,
.fa-chain-broken:before {
  content: "\f127";
}
.fa-question:before {
  content: "\f128";
}
.fa-info:before {
  content: "\f129";
}
.fa-exclamation:before {
  content: "\f12a";
}
.fa-superscript:before {
  content: "\f12b";
}
.fa-subscript:before {
  content: "\f12c";
}
.fa-eraser:before {
  content: "\f12d";
}
.fa-puzzle-piece:before {
  content: "\f12e";
}
.fa-microphone:before {
  content: "\f130";
}
.fa-microphone-slash:before {
  content: "\f131";
}
.fa-shield:before {
  content: "\f132";
}
.fa-calendar-o:before {
  content: "\f133";
}
.fa-fire-extinguisher:before {
  content: "\f134";
}
.fa-rocket:before {
  content: "\f135";
}
.fa-maxcdn:before {
  content: "\f136";
}
.fa-chevron-circle-left:before {
  content: "\f137";
}
.fa-chevron-circle-right:before {
  content: "\f138";
}
.fa-chevron-circle-up:before {
  content: "\f139";
}
.fa-chevron-circle-down:before {
  content: "\f13a";
}
.fa-html5:before {
  content: "\f13b";
}
.fa-css3:before {
  content: "\f13c";
}
.fa-anchor:before {
  content: "\f13d";
}
.fa-unlock-alt:before {
  content: "\f13e";
}
.fa-bullseye:before {
  content: "\f140";
}
.fa-ellipsis-h:before {
  content: "\f141";
}
.fa-ellipsis-v:before {
  content: "\f142";
}
.fa-rss-square:before {
  content: "\f143";
}
.fa-play-circle:before {
  content: "\f144";
}
.fa-ticket:before {
  content: "\f145";
}
.fa-minus-square:before {
  content: "\f146";
}
.fa-minus-square-o:before {
  content: "\f147";
}
.fa-level-up:before {
  content: "\f148";
}
.fa-level-down:before {
  content: "\f149";
}
.fa-check-square:before {
  content: "\f14a";
}
.fa-pencil-square:before {
  content: "\f14b";
}
.fa-external-link-square:before {
  content: "\f14c";
}
.fa-share-square:before {
  content: "\f14d";
}
.fa-compass:before {
  content: "\f14e";
}
.fa-toggle-down:before,
.fa-caret-square-o-down:before {
  content: "\f150";
}
.fa-toggle-up:before,
.fa-caret-square-o-up:before {
  content: "\f151";
}
.fa-toggle-right:before,
.fa-caret-square-o-right:before {
  content: "\f152";
}
.fa-euro:before,
.fa-eur:before {
  content: "\f153";
}
.fa-gbp:before {
  content: "\f154";
}
.fa-dollar:before,
.fa-usd:before {
  content: "\f155";
}
.fa-rupee:before,
.fa-inr:before {
  content: "\f156";
}
.fa-cny:before,
.fa-rmb:before,
.fa-yen:before,
.fa-jpy:before {
  content: "\f157";
}
.fa-ruble:before,
.fa-rouble:before,
.fa-rub:before {
  content: "\f158";
}
.fa-won:before,
.fa-krw:before {
  content: "\f159";
}
.fa-bitcoin:before,
.fa-btc:before {
  content: "\f15a";
}
.fa-file:before {
  content: "\f15b";
}
.fa-file-text:before {
  content: "\f15c";
}
.fa-sort-alpha-asc:before {
  content: "\f15d";
}
.fa-sort-alpha-desc:before {
  content: "\f15e";
}
.fa-sort-amount-asc:before {
  content: "\f160";
}
.fa-sort-amount-desc:before {
  content: "\f161";
}
.fa-sort-numeric-asc:before {
  content: "\f162";
}
.fa-sort-numeric-desc:before {
  content: "\f163";
}
.fa-thumbs-up:before {
  content: "\f164";
}
.fa-thumbs-down:before {
  content: "\f165";
}
.fa-youtube-square:before {
  content: "\f166";
}
.fa-youtube:before {
  content: "\f167";
}
.fa-xing:before {
  content: "\f168";
}
.fa-xing-square:before {
  content: "\f169";
}
.fa-youtube-play:before {
  content: "\f16a";
}
.fa-dropbox:before {
  content: "\f16b";
}
.fa-stack-overflow:before {
  content: "\f16c";
}
.fa-instagram:before {
  content: "\f16d";
}
.fa-flickr:before {
  content: "\f16e";
}
.fa-adn:before {
  content: "\f170";
}
.fa-bitbucket:before {
  content: "\f171";
}
.fa-bitbucket-square:before {
  content: "\f172";
}
.fa-tumblr:before {
  content: "\f173";
}
.fa-tumblr-square:before {
  content: "\f174";
}
.fa-long-arrow-down:before {
  content: "\f175";
}
.fa-long-arrow-up:before {
  content: "\f176";
}
.fa-long-arrow-left:before {
  content: "\f177";
}
.fa-long-arrow-right:before {
  content: "\f178";
}
.fa-apple:before {
  content: "\f179";
}
.fa-windows:before {
  content: "\f17a";
}
.fa-android:before {
  content: "\f17b";
}
.fa-linux:before {
  content: "\f17c";
}
.fa-dribbble:before {
  content: "\f17d";
}
.fa-skype:before {
  content: "\f17e";
}
.fa-foursquare:before {
  content: "\f180";
}
.fa-trello:before {
  content: "\f181";
}
.fa-female:before {
  content: "\f182";
}
.fa-male:before {
  content: "\f183";
}
.fa-gittip:before,
.fa-gratipay:before {
  content: "\f184";
}
.fa-sun-o:before {
  content: "\f185";
}
.fa-moon-o:before {
  content: "\f186";
}
.fa-archive:before {
  content: "\f187";
}
.fa-bug:before {
  content: "\f188";
}
.fa-vk:before {
  content: "\f189";
}
.fa-weibo:before {
  content: "\f18a";
}
.fa-renren:before {
  content: "\f18b";
}
.fa-pagelines:before {
  content: "\f18c";
}
.fa-stack-exchange:before {
  content: "\f18d";
}
.fa-arrow-circle-o-right:before {
  content: "\f18e";
}
.fa-arrow-circle-o-left:before {
  content: "\f190";
}
.fa-toggle-left:before,
.fa-caret-square-o-left:before {
  content: "\f191";
}
.fa-dot-circle-o:before {
  content: "\f192";
}
.fa-wheelchair:before {
  content: "\f193";
}
.fa-vimeo-square:before {
  content: "\f194";
}
.fa-turkish-lira:before,
.fa-try:before {
  content: "\f195";
}
.fa-plus-square-o:before {
  content: "\f196";
}
.fa-space-shuttle:before {
  content: "\f197";
}
.fa-slack:before {
  content: "\f198";
}
.fa-envelope-square:before {
  content: "\f199";
}
.fa-wordpress:before {
  content: "\f19a";
}
.fa-openid:before {
  content: "\f19b";
}
.fa-institution:before,
.fa-bank:before,
.fa-university:before {
  content: "\f19c";
}
.fa-mortar-board:before,
.fa-graduation-cap:before {
  content: "\f19d";
}
.fa-yahoo:before {
  content: "\f19e";
}
.fa-google:before {
  content: "\f1a0";
}
.fa-reddit:before {
  content: "\f1a1";
}
.fa-reddit-square:before {
  content: "\f1a2";
}
.fa-stumbleupon-circle:before {
  content: "\f1a3";
}
.fa-stumbleupon:before {
  content: "\f1a4";
}
.fa-delicious:before {
  content: "\f1a5";
}
.fa-digg:before {
  content: "\f1a6";
}
.fa-pied-piper-pp:before {
  content: "\f1a7";
}
.fa-pied-piper-alt:before {
  content: "\f1a8";
}
.fa-drupal:before {
  content: "\f1a9";
}
.fa-joomla:before {
  content: "\f1aa";
}
.fa-language:before {
  content: "\f1ab";
}
.fa-fax:before {
  content: "\f1ac";
}
.fa-building:before {
  content: "\f1ad";
}
.fa-child:before {
  content: "\f1ae";
}
.fa-paw:before {
  content: "\f1b0";
}
.fa-spoon:before {
  content: "\f1b1";
}
.fa-cube:before {
  content: "\f1b2";
}
.fa-cubes:before {
  content: "\f1b3";
}
.fa-behance:before {
  content: "\f1b4";
}
.fa-behance-square:before {
  content: "\f1b5";
}
.fa-steam:before {
  content: "\f1b6";
}
.fa-steam-square:before {
  content: "\f1b7";
}
.fa-recycle:before {
  content: "\f1b8";
}
.fa-automobile:before,
.fa-car:before {
  content: "\f1b9";
}
.fa-cab:before,
.fa-taxi:before {
  content: "\f1ba";
}
.fa-tree:before {
  content: "\f1bb";
}
.fa-spotify:before {
  content: "\f1bc";
}
.fa-deviantart:before {
  content: "\f1bd";
}
.fa-soundcloud:before {
  content: "\f1be";
}
.fa-database:before {
  content: "\f1c0";
}
.fa-file-pdf-o:before {
  content: "\f1c1";
}
.fa-file-word-o:before {
  content: "\f1c2";
}
.fa-file-excel-o:before {
  content: "\f1c3";
}
.fa-file-powerpoint-o:before {
  content: "\f1c4";
}
.fa-file-photo-o:before,
.fa-file-picture-o:before,
.fa-file-image-o:before {
  content: "\f1c5";
}
.fa-file-zip-o:before,
.fa-file-archive-o:before {
  content: "\f1c6";
}
.fa-file-sound-o:before,
.fa-file-audio-o:before {
  content: "\f1c7";
}
.fa-file-movie-o:before,
.fa-file-video-o:before {
  content: "\f1c8";
}
.fa-file-code-o:before {
  content: "\f1c9";
}
.fa-vine:before {
  content: "\f1ca";
}
.fa-codepen:before {
  content: "\f1cb";
}
.fa-jsfiddle:before {
  content: "\f1cc";
}
.fa-life-bouy:before,
.fa-life-buoy:before,
.fa-life-saver:before,
.fa-support:before,
.fa-life-ring:before {
  content: "\f1cd";
}
.fa-circle-o-notch:before {
  content: "\f1ce";
}
.fa-ra:before,
.fa-resistance:before,
.fa-rebel:before {
  content: "\f1d0";
}
.fa-ge:before,
.fa-empire:before {
  content: "\f1d1";
}
.fa-git-square:before {
  content: "\f1d2";
}
.fa-git:before {
  content: "\f1d3";
}
.fa-y-combinator-square:before,
.fa-yc-square:before,
.fa-hacker-news:before {
  content: "\f1d4";
}
.fa-tencent-weibo:before {
  content: "\f1d5";
}
.fa-qq:before {
  content: "\f1d6";
}
.fa-wechat:before,
.fa-weixin:before {
  content: "\f1d7";
}
.fa-send:before,
.fa-paper-plane:before {
  content: "\f1d8";
}
.fa-send-o:before,
.fa-paper-plane-o:before {
  content: "\f1d9";
}
.fa-history:before {
  content: "\f1da";
}
.fa-circle-thin:before {
  content: "\f1db";
}
.fa-header:before {
  content: "\f1dc";
}
.fa-paragraph:before {
  content: "\f1dd";
}
.fa-sliders:before {
  content: "\f1de";
}
.fa-share-alt:before {
  content: "\f1e0";
}
.fa-share-alt-square:before {
  content: "\f1e1";
}
.fa-bomb:before {
  content: "\f1e2";
}
.fa-soccer-ball-o:before,
.fa-futbol-o:before {
  content: "\f1e3";
}
.fa-tty:before {
  content: "\f1e4";
}
.fa-binoculars:before {
  content: "\f1e5";
}
.fa-plug:before {
  content: "\f1e6";
}
.fa-slideshare:before {
  content: "\f1e7";
}
.fa-twitch:before {
  content: "\f1e8";
}
.fa-yelp:before {
  content: "\f1e9";
}
.fa-newspaper-o:before {
  content: "\f1ea";
}
.fa-wifi:before {
  content: "\f1eb";
}
.fa-calculator:before {
  content: "\f1ec";
}
.fa-paypal:before {
  content: "\f1ed";
}
.fa-google-wallet:before {
  content: "\f1ee";
}
.fa-cc-visa:before {
  content: "\f1f0";
}
.fa-cc-mastercard:before {
  content: "\f1f1";
}
.fa-cc-discover:before {
  content: "\f1f2";
}
.fa-cc-amex:before {
  content: "\f1f3";
}
.fa-cc-paypal:before {
  content: "\f1f4";
}
.fa-cc-stripe:before {
  content: "\f1f5";
}
.fa-bell-slash:before {
  content: "\f1f6";
}
.fa-bell-slash-o:before {
  content: "\f1f7";
}
.fa-trash:before {
  content: "\f1f8";
}
.fa-copyright:before {
  content: "\f1f9";
}
.fa-at:before {
  content: "\f1fa";
}
.fa-eyedropper:before {
  content: "\f1fb";
}
.fa-paint-brush:before {
  content: "\f1fc";
}
.fa-birthday-cake:before {
  content: "\f1fd";
}
.fa-area-chart:before {
  content: "\f1fe";
}
.fa-pie-chart:before {
  content: "\f200";
}
.fa-line-chart:before {
  content: "\f201";
}
.fa-lastfm:before {
  content: "\f202";
}
.fa-lastfm-square:before {
  content: "\f203";
}
.fa-toggle-off:before {
  content: "\f204";
}
.fa-toggle-on:before {
  content: "\f205";
}
.fa-bicycle:before {
  content: "\f206";
}
.fa-bus:before {
  content: "\f207";
}
.fa-ioxhost:before {
  content: "\f208";
}
.fa-angellist:before {
  content: "\f209";
}
.fa-cc:before {
  content: "\f20a";
}
.fa-shekel:before,
.fa-sheqel:before,
.fa-ils:before {
  content: "\f20b";
}
.fa-meanpath:before {
  content: "\f20c";
}
.fa-buysellads:before {
  content: "\f20d";
}
.fa-connectdevelop:before {
  content: "\f20e";
}
.fa-dashcube:before {
  content: "\f210";
}
.fa-forumbee:before {
  content: "\f211";
}
.fa-leanpub:before {
  content: "\f212";
}
.fa-sellsy:before {
  content: "\f213";
}
.fa-shirtsinbulk:before {
  content: "\f214";
}
.fa-simplybuilt:before {
  content: "\f215";
}
.fa-skyatlas:before {
  content: "\f216";
}
.fa-cart-plus:before {
  content: "\f217";
}
.fa-cart-arrow-down:before {
  content: "\f218";
}
.fa-diamond:before {
  content: "\f219";
}
.fa-ship:before {
  content: "\f21a";
}
.fa-user-secret:before {
  content: "\f21b";
}
.fa-motorcycle:before {
  content: "\f21c";
}
.fa-street-view:before {
  content: "\f21d";
}
.fa-heartbeat:before {
  content: "\f21e";
}
.fa-venus:before {
  content: "\f221";
}
.fa-mars:before {
  content: "\f222";
}
.fa-mercury:before {
  content: "\f223";
}
.fa-intersex:before,
.fa-transgender:before {
  content: "\f224";
}
.fa-transgender-alt:before {
  content: "\f225";
}
.fa-venus-double:before {
  content: "\f226";
}
.fa-mars-double:before {
  content: "\f227";
}
.fa-venus-mars:before {
  content: "\f228";
}
.fa-mars-stroke:before {
  content: "\f229";
}
.fa-mars-stroke-v:before {
  content: "\f22a";
}
.fa-mars-stroke-h:before {
  content: "\f22b";
}
.fa-neuter:before {
  content: "\f22c";
}
.fa-genderless:before {
  content: "\f22d";
}
.fa-facebook-official:before {
  content: "\f230";
}
.fa-pinterest-p:before {
  content: "\f231";
}
.fa-whatsapp:before {
  content: "\f232";
}
.fa-server:before {
  content: "\f233";
}
.fa-user-plus:before {
  content: "\f234";
}
.fa-user-times:before {
  content: "\f235";
}
.fa-hotel:before,
.fa-bed:before {
  content: "\f236";
}
.fa-viacoin:before {
  content: "\f237";
}
.fa-train:before {
  content: "\f238";
}
.fa-subway:before {
  content: "\f239";
}
.fa-medium:before {
  content: "\f23a";
}
.fa-yc:before,
.fa-y-combinator:before {
  content: "\f23b";
}
.fa-optin-monster:before {
  content: "\f23c";
}
.fa-opencart:before {
  content: "\f23d";
}
.fa-expeditedssl:before {
  content: "\f23e";
}
.fa-battery-4:before,
.fa-battery:before,
.fa-battery-full:before {
  content: "\f240";
}
.fa-battery-3:before,
.fa-battery-three-quarters:before {
  content: "\f241";
}
.fa-battery-2:before,
.fa-battery-half:before {
  content: "\f242";
}
.fa-battery-1:before,
.fa-battery-quarter:before {
  content: "\f243";
}
.fa-battery-0:before,
.fa-battery-empty:before {
  content: "\f244";
}
.fa-mouse-pointer:before {
  content: "\f245";
}
.fa-i-cursor:before {
  content: "\f246";
}
.fa-object-group:before {
  content: "\f247";
}
.fa-object-ungroup:before {
  content: "\f248";
}
.fa-sticky-note:before {
  content: "\f249";
}
.fa-sticky-note-o:before {
  content: "\f24a";
}
.fa-cc-jcb:before {
  content: "\f24b";
}
.fa-cc-diners-club:before {
  content: "\f24c";
}
.fa-clone:before {
  content: "\f24d";
}
.fa-balance-scale:before {
  content: "\f24e";
}
.fa-hourglass-o:before {
  content: "\f250";
}
.fa-hourglass-1:before,
.fa-hourglass-start:before {
  content: "\f251";
}
.fa-hourglass-2:before,
.fa-hourglass-half:before {
  content: "\f252";
}
.fa-hourglass-3:before,
.fa-hourglass-end:before {
  content: "\f253";
}
.fa-hourglass:before {
  content: "\f254";
}
.fa-hand-grab-o:before,
.fa-hand-rock-o:before {
  content: "\f255";
}
.fa-hand-stop-o:before,
.fa-hand-paper-o:before {
  content: "\f256";
}
.fa-hand-scissors-o:before {
  content: "\f257";
}
.fa-hand-lizard-o:before {
  content: "\f258";
}
.fa-hand-spock-o:before {
  content: "\f259";
}
.fa-hand-pointer-o:before {
  content: "\f25a";
}
.fa-hand-peace-o:before {
  content: "\f25b";
}
.fa-trademark:before {
  content: "\f25c";
}
.fa-registered:before {
  content: "\f25d";
}
.fa-creative-commons:before {
  content: "\f25e";
}
.fa-gg:before {
  content: "\f260";
}
.fa-gg-circle:before {
  content: "\f261";
}
.fa-tripadvisor:before {
  content: "\f262";
}
.fa-odnoklassniki:before {
  content: "\f263";
}
.fa-odnoklassniki-square:before {
  content: "\f264";
}
.fa-get-pocket:before {
  content: "\f265";
}
.fa-wikipedia-w:before {
  content: "\f266";
}
.fa-safari:before {
  content: "\f267";
}
.fa-chrome:before {
  content: "\f268";
}
.fa-firefox:before {
  content: "\f269";
}
.fa-opera:before {
  content: "\f26a";
}
.fa-internet-explorer:before {
  content: "\f26b";
}
.fa-tv:before,
.fa-television:before {
  content: "\f26c";
}
.fa-contao:before {
  content: "\f26d";
}
.fa-500px:before {
  content: "\f26e";
}
.fa-amazon:before {
  content: "\f270";
}
.fa-calendar-plus-o:before {
  content: "\f271";
}
.fa-calendar-minus-o:before {
  content: "\f272";
}
.fa-calendar-times-o:before {
  content: "\f273";
}
.fa-calendar-check-o:before {
  content: "\f274";
}
.fa-industry:before {
  content: "\f275";
}
.fa-map-pin:before {
  content: "\f276";
}
.fa-map-signs:before {
  content: "\f277";
}
.fa-map-o:before {
  content: "\f278";
}
.fa-map:before {
  content: "\f279";
}
.fa-commenting:before {
  content: "\f27a";
}
.fa-commenting-o:before {
  content: "\f27b";
}
.fa-houzz:before {
  content: "\f27c";
}
.fa-vimeo:before {
  content: "\f27d";
}
.fa-black-tie:before {
  content: "\f27e";
}
.fa-fonticons:before {
  content: "\f280";
}
.fa-reddit-alien:before {
  content: "\f281";
}
.fa-edge:before {
  content: "\f282";
}
.fa-credit-card-alt:before {
  content: "\f283";
}
.fa-codiepie:before {
  content: "\f284";
}
.fa-modx:before {
  content: "\f285";
}
.fa-fort-awesome:before {
  content: "\f286";
}
.fa-usb:before {
  content: "\f287";
}
.fa-product-hunt:before {
  content: "\f288";
}
.fa-mixcloud:before {
  content: "\f289";
}
.fa-scribd:before {
  content: "\f28a";
}
.fa-pause-circle:before {
  content: "\f28b";
}
.fa-pause-circle-o:before {
  content: "\f28c";
}
.fa-stop-circle:before {
  content: "\f28d";
}
.fa-stop-circle-o:before {
  content: "\f28e";
}
.fa-shopping-bag:before {
  content: "\f290";
}
.fa-shopping-basket:before {
  content: "\f291";
}
.fa-hashtag:before {
  content: "\f292";
}
.fa-bluetooth:before {
  content: "\f293";
}
.fa-bluetooth-b:before {
  content: "\f294";
}
.fa-percent:before {
  content: "\f295";
}
.fa-gitlab:before {
  content: "\f296";
}
.fa-wpbeginner:before {
  content: "\f297";
}
.fa-wpforms:before {
  content: "\f298";
}
.fa-envira:before {
  content: "\f299";
}
.fa-universal-access:before {
  content: "\f29a";
}
.fa-wheelchair-alt:before {
  content: "\f29b";
}
.fa-question-circle-o:before {
  content: "\f29c";
}
.fa-blind:before {
  content: "\f29d";
}
.fa-audio-description:before {
  content: "\f29e";
}
.fa-volume-control-phone:before {
  content: "\f2a0";
}
.fa-braille:before {
  content: "\f2a1";
}
.fa-assistive-listening-systems:before {
  content: "\f2a2";
}
.fa-asl-interpreting:before,
.fa-american-sign-language-interpreting:before {
  content: "\f2a3";
}
.fa-deafness:before,
.fa-hard-of-hearing:before,
.fa-deaf:before {
  content: "\f2a4";
}
.fa-glide:before {
  content: "\f2a5";
}
.fa-glide-g:before {
  content: "\f2a6";
}
.fa-signing:before,
.fa-sign-language:before {
  content: "\f2a7";
}
.fa-low-vision:before {
  content: "\f2a8";
}
.fa-viadeo:before {
  content: "\f2a9";
}
.fa-viadeo-square:before {
  content: "\f2aa";
}
.fa-snapchat:before {
  content: "\f2ab";
}
.fa-snapchat-ghost:before {
  content: "\f2ac";
}
.fa-snapchat-square:before {
  content: "\f2ad";
}
.fa-pied-piper:before {
  content: "\f2ae";
}
.fa-first-order:before {
  content: "\f2b0";
}
.fa-yoast:before {
  content: "\f2b1";
}
.fa-themeisle:before {
  content: "\f2b2";
}
.fa-google-plus-circle:before,
.fa-google-plus-official:before {
  content: "\f2b3";
}
.fa-fa:before,
.fa-font-awesome:before {
  content: "\f2b4";
}
.fa-handshake-o:before {
  content: "\f2b5";
}
.fa-envelope-open:before {
  content: "\f2b6";
}
.fa-envelope-open-o:before {
  content: "\f2b7";
}
.fa-linode:before {
  content: "\f2b8";
}
.fa-address-book:before {
  content: "\f2b9";
}
.fa-address-book-o:before {
  content: "\f2ba";
}
.fa-vcard:before,
.fa-address-card:before {
  content: "\f2bb";
}
.fa-vcard-o:before,
.fa-address-card-o:before {
  content: "\f2bc";
}
.fa-user-circle:before {
  content: "\f2bd";
}
.fa-user-circle-o:before {
  content: "\f2be";
}
.fa-user-o:before {
  content: "\f2c0";
}
.fa-id-badge:before {
  content: "\f2c1";
}
.fa-drivers-license:before,
.fa-id-card:before {
  content: "\f2c2";
}
.fa-drivers-license-o:before,
.fa-id-card-o:before {
  content: "\f2c3";
}
.fa-quora:before {
  content: "\f2c4";
}
.fa-free-code-camp:before {
  content: "\f2c5";
}
.fa-telegram:before {
  content: "\f2c6";
}
.fa-thermometer-4:before,
.fa-thermometer:before,
.fa-thermometer-full:before {
  content: "\f2c7";
}
.fa-thermometer-3:before,
.fa-thermometer-three-quarters:before {
  content: "\f2c8";
}
.fa-thermometer-2:before,
.fa-thermometer-half:before {
  content: "\f2c9";
}
.fa-thermometer-1:before,
.fa-thermometer-quarter:before {
  content: "\f2ca";
}
.fa-thermometer-0:before,
.fa-thermometer-empty:before {
  content: "\f2cb";
}
.fa-shower:before {
  content: "\f2cc";
}
.fa-bathtub:before,
.fa-s15:before,
.fa-bath:before {
  content: "\f2cd";
}
.fa-podcast:before {
  content: "\f2ce";
}
.fa-window-maximize:before {
  content: "\f2d0";
}
.fa-window-minimize:before {
  content: "\f2d1";
}
.fa-window-restore:before {
  content: "\f2d2";
}
.fa-times-rectangle:before,
.fa-window-close:before {
  content: "\f2d3";
}
.fa-times-rectangle-o:before,
.fa-window-close-o:before {
  content: "\f2d4";
}
.fa-bandcamp:before {
  content: "\f2d5";
}
.fa-grav:before {
  content: "\f2d6";
}
.fa-etsy:before {
  content: "\f2d7";
}
.fa-imdb:before {
  content: "\f2d8";
}
.fa-ravelry:before {
  content: "\f2d9";
}
.fa-eercast:before {
  content: "\f2da";
}
.fa-microchip:before {
  content: "\f2db";
}
.fa-snowflake-o:before {
  content: "\f2dc";
}
.fa-superpowers:before {
  content: "\f2dd";
}
.fa-wpexplorer:before {
  content: "\f2de";
}
.fa-meetup:before {
  content: "\f2e0";
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
/*!
*
* IPython base
*
*/
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
code {
  color: #000;
}
pre {
  font-size: inherit;
  line-height: inherit;
}
label {
  font-weight: normal;
}
/* Make the page background atleast 100% the height of the view port */
/* Make the page itself atleast 70% the height of the view port */
.border-box-sizing {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.corner-all {
  border-radius: 2px;
}
.no-padding {
  padding: 0px;
}
/* Flexible box model classes */
/* Taken from Alex Russell http://infrequently.org/2009/08/css-3-progress/ */
/* This file is a compatability layer.  It allows the usage of flexible box 
model layouts accross multiple browsers, including older browsers.  The newest,
universal implementation of the flexible box model is used when available (see
`Modern browsers` comments below).  Browsers that are known to implement this 
new spec completely include:

    Firefox 28.0+
    Chrome 29.0+
    Internet Explorer 11+ 
    Opera 17.0+

Browsers not listed, including Safari, are supported via the styling under the
`Old browsers` comments below.
*/
.hbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
.hbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.vbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
.vbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.hbox.reverse,
.vbox.reverse,
.reverse {
  /* Old browsers */
  -webkit-box-direction: reverse;
  -moz-box-direction: reverse;
  box-direction: reverse;
  /* Modern browsers */
  flex-direction: row-reverse;
}
.hbox.box-flex0,
.vbox.box-flex0,
.box-flex0 {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
  width: auto;
}
.hbox.box-flex1,
.vbox.box-flex1,
.box-flex1 {
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex,
.vbox.box-flex,
.box-flex {
  /* Old browsers */
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex2,
.vbox.box-flex2,
.box-flex2 {
  /* Old browsers */
  -webkit-box-flex: 2;
  -moz-box-flex: 2;
  box-flex: 2;
  /* Modern browsers */
  flex: 2;
}
.box-group1 {
  /*  Deprecated */
  -webkit-box-flex-group: 1;
  -moz-box-flex-group: 1;
  box-flex-group: 1;
}
.box-group2 {
  /* Deprecated */
  -webkit-box-flex-group: 2;
  -moz-box-flex-group: 2;
  box-flex-group: 2;
}
.hbox.start,
.vbox.start,
.start {
  /* Old browsers */
  -webkit-box-pack: start;
  -moz-box-pack: start;
  box-pack: start;
  /* Modern browsers */
  justify-content: flex-start;
}
.hbox.end,
.vbox.end,
.end {
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
}
.hbox.center,
.vbox.center,
.center {
  /* Old browsers */
  -webkit-box-pack: center;
  -moz-box-pack: center;
  box-pack: center;
  /* Modern browsers */
  justify-content: center;
}
.hbox.baseline,
.vbox.baseline,
.baseline {
  /* Old browsers */
  -webkit-box-pack: baseline;
  -moz-box-pack: baseline;
  box-pack: baseline;
  /* Modern browsers */
  justify-content: baseline;
}
.hbox.stretch,
.vbox.stretch,
.stretch {
  /* Old browsers */
  -webkit-box-pack: stretch;
  -moz-box-pack: stretch;
  box-pack: stretch;
  /* Modern browsers */
  justify-content: stretch;
}
.hbox.align-start,
.vbox.align-start,
.align-start {
  /* Old browsers */
  -webkit-box-align: start;
  -moz-box-align: start;
  box-align: start;
  /* Modern browsers */
  align-items: flex-start;
}
.hbox.align-end,
.vbox.align-end,
.align-end {
  /* Old browsers */
  -webkit-box-align: end;
  -moz-box-align: end;
  box-align: end;
  /* Modern browsers */
  align-items: flex-end;
}
.hbox.align-center,
.vbox.align-center,
.align-center {
  /* Old browsers */
  -webkit-box-align: center;
  -moz-box-align: center;
  box-align: center;
  /* Modern browsers */
  align-items: center;
}
.hbox.align-baseline,
.vbox.align-baseline,
.align-baseline {
  /* Old browsers */
  -webkit-box-align: baseline;
  -moz-box-align: baseline;
  box-align: baseline;
  /* Modern browsers */
  align-items: baseline;
}
.hbox.align-stretch,
.vbox.align-stretch,
.align-stretch {
  /* Old browsers */
  -webkit-box-align: stretch;
  -moz-box-align: stretch;
  box-align: stretch;
  /* Modern browsers */
  align-items: stretch;
}
div.error {
  margin: 2em;
  text-align: center;
}
div.error > h1 {
  font-size: 500%;
  line-height: normal;
}
div.error > p {
  font-size: 200%;
  line-height: normal;
}
div.traceback-wrapper {
  text-align: left;
  max-width: 800px;
  margin: auto;
}
div.traceback-wrapper pre.traceback {
  max-height: 600px;
  overflow: auto;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
body {
  background-color: #fff;
  /* This makes sure that the body covers the entire window and needs to
       be in a different element than the display: box in wrapper below */
  position: absolute;
  left: 0px;
  right: 0px;
  top: 0px;
  bottom: 0px;
  overflow: visible;
}
body > #header {
  /* Initially hidden to prevent FLOUC */
  display: none;
  background-color: #fff;
  /* Display over codemirror */
  position: relative;
  z-index: 100;
}
body > #header #header-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 5px;
  padding-bottom: 5px;
  padding-top: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body > #header .header-bar {
  width: 100%;
  height: 1px;
  background: #e7e7e7;
  margin-bottom: -1px;
}
@media print {
  body > #header {
    display: none !important;
  }
}
#header-spacer {
  width: 100%;
  visibility: hidden;
}
@media print {
  #header-spacer {
    display: none;
  }
}
#ipython_notebook {
  padding-left: 0px;
  padding-top: 1px;
  padding-bottom: 1px;
}
[dir="rtl"] #ipython_notebook {
  margin-right: 10px;
  margin-left: 0;
}
[dir="rtl"] #ipython_notebook.pull-left {
  float: right !important;
  float: right;
}
.flex-spacer {
  flex: 1;
}
#noscript {
  width: auto;
  padding-top: 16px;
  padding-bottom: 16px;
  text-align: center;
  font-size: 22px;
  color: red;
  font-weight: bold;
}
#ipython_notebook img {
  height: 28px;
}
#site {
  width: 100%;
  display: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  overflow: auto;
}
@media print {
  #site {
    height: auto !important;
  }
}
/* Smaller buttons */
.ui-button .ui-button-text {
  padding: 0.2em 0.8em;
  font-size: 77%;
}
input.ui-button {
  padding: 0.3em 0.9em;
}
span#kernel_logo_widget {
  margin: 0 10px;
}
span#login_widget {
  float: right;
}
[dir="rtl"] span#login_widget {
  float: left;
}
span#login_widget > .button,
#logout {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button:focus,
#logout:focus,
span#login_widget > .button.focus,
#logout.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
span#login_widget > .button:hover,
#logout:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active:hover,
#logout:active:hover,
span#login_widget > .button.active:hover,
#logout.active:hover,
.open > .dropdown-togglespan#login_widget > .button:hover,
.open > .dropdown-toggle#logout:hover,
span#login_widget > .button:active:focus,
#logout:active:focus,
span#login_widget > .button.active:focus,
#logout.active:focus,
.open > .dropdown-togglespan#login_widget > .button:focus,
.open > .dropdown-toggle#logout:focus,
span#login_widget > .button:active.focus,
#logout:active.focus,
span#login_widget > .button.active.focus,
#logout.active.focus,
.open > .dropdown-togglespan#login_widget > .button.focus,
.open > .dropdown-toggle#logout.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  background-image: none;
}
span#login_widget > .button.disabled:hover,
#logout.disabled:hover,
span#login_widget > .button[disabled]:hover,
#logout[disabled]:hover,
fieldset[disabled] span#login_widget > .button:hover,
fieldset[disabled] #logout:hover,
span#login_widget > .button.disabled:focus,
#logout.disabled:focus,
span#login_widget > .button[disabled]:focus,
#logout[disabled]:focus,
fieldset[disabled] span#login_widget > .button:focus,
fieldset[disabled] #logout:focus,
span#login_widget > .button.disabled.focus,
#logout.disabled.focus,
span#login_widget > .button[disabled].focus,
#logout[disabled].focus,
fieldset[disabled] span#login_widget > .button.focus,
fieldset[disabled] #logout.focus {
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button .badge,
#logout .badge {
  color: #fff;
  background-color: #333;
}
.nav-header {
  text-transform: none;
}
#header > span {
  margin-top: 10px;
}
.modal_stretch .modal-dialog {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-height: 80vh;
}
.modal_stretch .modal-dialog .modal-body {
  max-height: calc(100vh - 200px);
  overflow: auto;
  flex: 1;
}
.modal-header {
  cursor: move;
}
@media (min-width: 768px) {
  .modal .modal-dialog {
    width: 700px;
  }
}
@media (min-width: 768px) {
  select.form-control {
    margin-left: 12px;
    margin-right: 12px;
  }
}
/*!
*
* IPython auth
*
*/
.center-nav {
  display: inline-block;
  margin-bottom: -4px;
}
[dir="rtl"] .center-nav form.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] .center-nav .navbar-text {
  float: right;
}
[dir="rtl"] .navbar-inner {
  text-align: right;
}
[dir="rtl"] div.text-left {
  text-align: right;
}
/*!
*
* IPython tree view
*
*/
/* We need an invisible input field on top of the sentense*/
/* "Drag file onto the list ..." */
.alternate_upload {
  background-color: none;
  display: inline;
}
.alternate_upload.form {
  padding: 0;
  margin: 0;
}
.alternate_upload input.fileinput {
  position: absolute;
  display: block;
  width: 100%;
  height: 100%;
  overflow: hidden;
  cursor: pointer;
  opacity: 0;
  z-index: 2;
}
.alternate_upload .btn-xs > input.fileinput {
  margin: -1px -5px;
}
.alternate_upload .btn-upload {
  position: relative;
  height: 22px;
}
::-webkit-file-upload-button {
  cursor: pointer;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
ul#tabs {
  margin-bottom: 4px;
}
ul#tabs a {
  padding-top: 6px;
  padding-bottom: 4px;
}
[dir="rtl"] ul#tabs.nav-tabs > li {
  float: right;
}
[dir="rtl"] ul#tabs.nav.nav-tabs {
  padding-right: 0;
}
ul.breadcrumb a:focus,
ul.breadcrumb a:hover {
  text-decoration: none;
}
ul.breadcrumb i.icon-home {
  font-size: 16px;
  margin-right: 4px;
}
ul.breadcrumb span {
  color: #5e5e5e;
}
.list_toolbar {
  padding: 4px 0 4px 0;
  vertical-align: middle;
}
.list_toolbar .tree-buttons {
  padding-top: 1px;
}
[dir="rtl"] .list_toolbar .tree-buttons .pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .list_toolbar .col-sm-4,
[dir="rtl"] .list_toolbar .col-sm-8 {
  float: right;
}
.dynamic-buttons {
  padding-top: 3px;
  display: inline-block;
}
.list_toolbar [class*="span"] {
  min-height: 24px;
}
.list_header {
  font-weight: bold;
  background-color: #EEE;
}
.list_placeholder {
  font-weight: bold;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
}
.list_container {
  margin-top: 4px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 2px;
}
.list_container > div {
  border-bottom: 1px solid #ddd;
}
.list_container > div:hover .list-item {
  background-color: red;
}
.list_container > div:last-child {
  border: none;
}
.list_item:hover .list_item {
  background-color: #ddd;
}
.list_item a {
  text-decoration: none;
}
.list_item:hover {
  background-color: #fafafa;
}
.list_header > div,
.list_item > div {
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
.list_header > div input,
.list_item > div input {
  margin-right: 7px;
  margin-left: 14px;
  vertical-align: text-bottom;
  line-height: 22px;
  position: relative;
  top: -1px;
}
.list_header > div .item_link,
.list_item > div .item_link {
  margin-left: -1px;
  vertical-align: baseline;
  line-height: 22px;
}
[dir="rtl"] .list_item > div input {
  margin-right: 0;
}
.new-file input[type=checkbox] {
  visibility: hidden;
}
.item_name {
  line-height: 22px;
  height: 24px;
}
.item_icon {
  font-size: 14px;
  color: #5e5e5e;
  margin-right: 7px;
  margin-left: 7px;
  line-height: 22px;
  vertical-align: baseline;
}
.item_modified {
  margin-right: 7px;
  margin-left: 7px;
}
[dir="rtl"] .item_modified.pull-right {
  float: left !important;
  float: left;
}
.item_buttons {
  line-height: 1em;
  margin-left: -5px;
}
.item_buttons .btn,
.item_buttons .btn-group,
.item_buttons .input-group {
  float: left;
}
.item_buttons > .btn,
.item_buttons > .btn-group,
.item_buttons > .input-group {
  margin-left: 5px;
}
.item_buttons .btn {
  min-width: 13ex;
}
.item_buttons .running-indicator {
  padding-top: 4px;
  color: #5cb85c;
}
.item_buttons .kernel-name {
  padding-top: 4px;
  color: #5bc0de;
  margin-right: 7px;
  float: left;
}
[dir="rtl"] .item_buttons.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .item_buttons .kernel-name {
  margin-left: 7px;
  float: right;
}
.toolbar_info {
  height: 24px;
  line-height: 24px;
}
.list_item input:not([type=checkbox]) {
  padding-top: 3px;
  padding-bottom: 3px;
  height: 22px;
  line-height: 14px;
  margin: 0px;
}
.highlight_text {
  color: blue;
}
#project_name {
  display: inline-block;
  padding-left: 7px;
  margin-left: -2px;
}
#project_name > .breadcrumb {
  padding: 0px;
  margin-bottom: 0px;
  background-color: transparent;
  font-weight: bold;
}
.sort_button {
  display: inline-block;
  padding-left: 7px;
}
[dir="rtl"] .sort_button.pull-right {
  float: left !important;
  float: left;
}
#tree-selector {
  padding-right: 0px;
}
#button-select-all {
  min-width: 50px;
}
[dir="rtl"] #button-select-all.btn {
  float: right ;
}
#select-all {
  margin-left: 7px;
  margin-right: 2px;
  margin-top: 2px;
  height: 16px;
}
[dir="rtl"] #select-all.pull-left {
  float: right !important;
  float: right;
}
.menu_icon {
  margin-right: 2px;
}
.tab-content .row {
  margin-left: 0px;
  margin-right: 0px;
}
.folder_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f114";
}
.folder_icon:before.fa-pull-left {
  margin-right: .3em;
}
.folder_icon:before.fa-pull-right {
  margin-left: .3em;
}
.folder_icon:before.pull-left {
  margin-right: .3em;
}
.folder_icon:before.pull-right {
  margin-left: .3em;
}
.notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
}
.notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.notebook_icon:before.pull-left {
  margin-right: .3em;
}
.notebook_icon:before.pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
  color: #5cb85c;
}
.running_notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before.pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.pull-right {
  margin-left: .3em;
}
.file_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f016";
  position: relative;
  top: -2px;
}
.file_icon:before.fa-pull-left {
  margin-right: .3em;
}
.file_icon:before.fa-pull-right {
  margin-left: .3em;
}
.file_icon:before.pull-left {
  margin-right: .3em;
}
.file_icon:before.pull-right {
  margin-left: .3em;
}
#notebook_toolbar .pull-right {
  padding-top: 0px;
  margin-right: -1px;
}
ul#new-menu {
  left: auto;
  right: 0;
}
#new-menu .dropdown-header {
  font-size: 10px;
  border-bottom: 1px solid #e5e5e5;
  padding: 0 0 3px;
  margin: -3px 20px 0;
}
.kernel-menu-icon {
  padding-right: 12px;
  width: 24px;
  content: "\f096";
}
.kernel-menu-icon:before {
  content: "\f096";
}
.kernel-menu-icon-current:before {
  content: "\f00c";
}
#tab_content {
  padding-top: 20px;
}
#running .panel-group .panel {
  margin-top: 3px;
  margin-bottom: 1em;
}
#running .panel-group .panel .panel-heading {
  background-color: #EEE;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
#running .panel-group .panel .panel-heading a:focus,
#running .panel-group .panel .panel-heading a:hover {
  text-decoration: none;
}
#running .panel-group .panel .panel-body {
  padding: 0px;
}
#running .panel-group .panel .panel-body .list_container {
  margin-top: 0px;
  margin-bottom: 0px;
  border: 0px;
  border-radius: 0px;
}
#running .panel-group .panel .panel-body .list_container .list_item {
  border-bottom: 1px solid #ddd;
}
#running .panel-group .panel .panel-body .list_container .list_item:last-child {
  border-bottom: 0px;
}
.delete-button {
  display: none;
}
.duplicate-button {
  display: none;
}
.rename-button {
  display: none;
}
.move-button {
  display: none;
}
.download-button {
  display: none;
}
.shutdown-button {
  display: none;
}
.dynamic-instructions {
  display: inline-block;
  padding-top: 4px;
}
/*!
*
* IPython text editor webapp
*
*/
.selected-keymap i.fa {
  padding: 0px 5px;
}
.selected-keymap i.fa:before {
  content: "\f00c";
}
#mode-menu {
  overflow: auto;
  max-height: 20em;
}
.edit_app #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.edit_app #menubar .navbar {
  /* Use a negative 1 bottom margin, so the border overlaps the border of the
    header */
  margin-bottom: -1px;
}
.dirty-indicator {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator.pull-left {
  margin-right: .3em;
}
.dirty-indicator.pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-dirty.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty.pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-clean.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f00c";
}
.dirty-indicator-clean:before.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.pull-right {
  margin-left: .3em;
}
#filename {
  font-size: 16pt;
  display: table;
  padding: 0px 5px;
}
#current-mode {
  padding-left: 5px;
  padding-right: 5px;
}
#texteditor-backdrop {
  padding-top: 20px;
  padding-bottom: 20px;
}
@media not print {
  #texteditor-backdrop {
    background-color: #EEE;
  }
}
@media print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container {
    padding: 0px;
    background-color: #fff;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
.CodeMirror-dialog {
  background-color: #fff;
}
/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI escape sequences */
/* The color values are a mix of
   http://www.xcolors.net/dl/baskerville-ivorylight and
   http://www.xcolors.net/dl/euphrasia */
.ansi-black-fg {
  color: #3E424D;
}
.ansi-black-bg {
  background-color: #3E424D;
}
.ansi-black-intense-fg {
  color: #282C36;
}
.ansi-black-intense-bg {
  background-color: #282C36;
}
.ansi-red-fg {
  color: #E75C58;
}
.ansi-red-bg {
  background-color: #E75C58;
}
.ansi-red-intense-fg {
  color: #B22B31;
}
.ansi-red-intense-bg {
  background-color: #B22B31;
}
.ansi-green-fg {
  color: #00A250;
}
.ansi-green-bg {
  background-color: #00A250;
}
.ansi-green-intense-fg {
  color: #007427;
}
.ansi-green-intense-bg {
  background-color: #007427;
}
.ansi-yellow-fg {
  color: #DDB62B;
}
.ansi-yellow-bg {
  background-color: #DDB62B;
}
.ansi-yellow-intense-fg {
  color: #B27D12;
}
.ansi-yellow-intense-bg {
  background-color: #B27D12;
}
.ansi-blue-fg {
  color: #208FFB;
}
.ansi-blue-bg {
  background-color: #208FFB;
}
.ansi-blue-intense-fg {
  color: #0065CA;
}
.ansi-blue-intense-bg {
  background-color: #0065CA;
}
.ansi-magenta-fg {
  color: #D160C4;
}
.ansi-magenta-bg {
  background-color: #D160C4;
}
.ansi-magenta-intense-fg {
  color: #A03196;
}
.ansi-magenta-intense-bg {
  background-color: #A03196;
}
.ansi-cyan-fg {
  color: #60C6C8;
}
.ansi-cyan-bg {
  background-color: #60C6C8;
}
.ansi-cyan-intense-fg {
  color: #258F8F;
}
.ansi-cyan-intense-bg {
  background-color: #258F8F;
}
.ansi-white-fg {
  color: #C5C1B4;
}
.ansi-white-bg {
  background-color: #C5C1B4;
}
.ansi-white-intense-fg {
  color: #A1A6B2;
}
.ansi-white-intense-bg {
  background-color: #A1A6B2;
}
.ansi-default-inverse-fg {
  color: #FFFFFF;
}
.ansi-default-inverse-bg {
  background-color: #000000;
}
.ansi-bold {
  font-weight: bold;
}
.ansi-underline {
  text-decoration: underline;
}
/* The following styles are deprecated an will be removed in a future version */
.ansibold {
  font-weight: bold;
}
.ansi-inverse {
  outline: 0.5px dotted;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  position: relative;
  overflow: visible;
}
div.cell:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: transparent;
}
div.cell.jupyter-soft-selected {
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected,
div.cell.selected.jupyter-soft-selected {
  border-color: #ababab;
}
div.cell.selected:before,
div.cell.selected.jupyter-soft-selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #42A5F5;
}
@media print {
  div.cell.selected,
  div.cell.selected.jupyter-soft-selected {
    border-color: transparent;
  }
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
}
.edit_mode div.cell.selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #66BB6A;
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  min-width: 0;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  /* Note that this should set vertical padding only, since CodeMirror assumes
       that horizontal padding will be set on CodeMirror pre */
  padding: 0.4em 0;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. This sets horizontal padding only,
    use .CodeMirror-lines for vertical */
  padding: 0 0.4em;
  border: 0;
  border-radius: 0;
}
.CodeMirror-cursor {
  border-left: 1.4px solid black;
}
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .CodeMirror-cursor {
    border-left: 2px solid black;
  }
}
@media screen and (min-width: 4320px) {
  .CodeMirror-cursor {
    border-left: 4px solid black;
  }
}
/*

Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme

*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area .rendered_html table {
  margin-left: 0;
  margin-right: 0;
}
div.output_area .rendered_html img {
  margin-left: 0;
  margin-right: 0;
}
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
div.output_area .mglyph > img {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 1px 0 1px 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html em {
  font-style: italic;
}
.rendered_html strong {
  font-weight: bold;
}
.rendered_html u {
  text-decoration: underline;
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1 {
  font-size: 185.7%;
  margin: 1.08em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h2 {
  font-size: 157.1%;
  margin: 1.27em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h3 {
  font-size: 128.6%;
  margin: 1.55em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h4 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h5 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h6 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html ul:not(.list-inline),
.rendered_html ol:not(.list-inline) {
  padding-left: 2em;
}
.rendered_html ul {
  list-style: disc;
}
.rendered_html ul ul {
  list-style: square;
  margin-top: 0;
}
.rendered_html ul ul ul {
  list-style: circle;
}
.rendered_html ol {
  list-style: decimal;
}
.rendered_html ol ol {
  list-style: upper-alpha;
  margin-top: 0;
}
.rendered_html ol ol ol {
  list-style: lower-alpha;
}
.rendered_html ol ol ol ol {
  list-style: lower-roman;
}
.rendered_html ol ol ol ol ol {
  list-style: decimal;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html hr {
  color: black;
  background-color: black;
}
.rendered_html pre {
  margin: 1em 2em;
  padding: 0px;
  background-color: #fff;
}
.rendered_html code {
  background-color: #eff0f1;
}
.rendered_html p code {
  padding: 1px 5px;
}
.rendered_html pre code {
  background-color: #fff;
}
.rendered_html pre,
.rendered_html code {
  border: 0;
  color: #000;
  font-size: 100%;
}
.rendered_html blockquote {
  margin: 1em 2em;
}
.rendered_html table {
  margin-left: auto;
  margin-right: auto;
  border: none;
  border-collapse: collapse;
  border-spacing: 0;
  color: black;
  font-size: 12px;
  table-layout: fixed;
}
.rendered_html thead {
  border-bottom: 1px solid black;
  vertical-align: bottom;
}
.rendered_html tr,
.rendered_html th,
.rendered_html td {
  text-align: right;
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}
.rendered_html th {
  font-weight: bold;
}
.rendered_html tbody tr:nth-child(odd) {
  background: #f5f5f5;
}
.rendered_html tbody tr:hover {
  background: rgba(66, 165, 245, 0.2);
}
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html p {
  text-align: left;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html svg {
  max-width: 100%;
  height: auto;
}
.rendered_html img.unconfined,
.rendered_html svg.unconfined {
  max-width: none;
}
.rendered_html .alert {
  margin-bottom: initial;
}
.rendered_html * + .alert {
  margin-top: 1em;
}
[dir="rtl"] .rendered_html p {
  text-align: right;
}
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered .rendered_html {
  overflow-x: auto;
  overflow-y: hidden;
}
.text_cell.rendered .rendered_html tr,
.text_cell.rendered .rendered_html th,
.text_cell.rendered .rendered_html td {
  max-width: none;
}
.text_cell.unrendered .text_cell_render {
  display: none;
}
.text_cell .dropzone .input_area {
  border: 2px dashed #bababa;
  margin: -1px;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
/*!
*
* IPython notebook webapp
*
*/
@media (max-width: 767px) {
  .notebook_app {
    padding-left: 0px;
    padding-right: 0px;
  }
}
#ipython-main-app {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook_panel {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook {
  font-size: 14px;
  line-height: 20px;
  overflow-y: hidden;
  overflow-x: auto;
  width: 100%;
  /* This spaces the page away from the edge of the notebook area */
  padding-top: 20px;
  margin: 0px;
  outline: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  min-height: 100%;
}
@media not print {
  #notebook-container {
    padding: 15px;
    background-color: #fff;
    min-height: 0;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
@media print {
  #notebook-container {
    width: 100%;
  }
}
div.ui-widget-content {
  border: 1px solid #ababab;
  outline: none;
}
pre.dialog {
  background-color: #f7f7f7;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0.4em;
  padding-left: 2em;
}
p.dialog {
  padding: 0.2em;
}
/* Word-wrap output correctly.  This is the CSS3 spelling, though Firefox seems
   to not honor it correctly.  Webkit browsers (Chrome, rekonq, Safari) do.
 */
pre,
code,
kbd,
samp {
  white-space: pre-wrap;
}
#fonttest {
  font-family: monospace;
}
p {
  margin-bottom: 0;
}
.end_space {
  min-height: 100px;
  transition: height .2s ease;
}
.notebook_app > #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
@media not print {
  .notebook_app {
    background-color: #EEE;
  }
}
kbd {
  border-style: solid;
  border-width: 1px;
  box-shadow: none;
  margin: 2px;
  padding-left: 2px;
  padding-right: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
.jupyter-keybindings {
  padding: 1px;
  line-height: 24px;
  border-bottom: 1px solid gray;
}
.jupyter-keybindings input {
  margin: 0;
  padding: 0;
  border: none;
}
.jupyter-keybindings i {
  padding: 6px;
}
.well code {
  background-color: #ffffff;
  border-color: #ababab;
  border-width: 1px;
  border-style: solid;
  padding: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
/* CSS for the cell toolbar */
.celltoolbar {
  border: thin solid #CFCFCF;
  border-bottom: none;
  background: #EEE;
  border-radius: 2px 2px 0px 0px;
  width: 100%;
  height: 29px;
  padding-right: 4px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
  display: -webkit-flex;
}
@media print {
  .celltoolbar {
    display: none;
  }
}
.ctb_hideshow {
  display: none;
  vertical-align: bottom;
}
/* ctb_show is added to the ctb_hideshow div to show the cell toolbar.
   Cell toolbars are only shown when the ctb_global_show class is also set.
*/
.ctb_global_show .ctb_show.ctb_hideshow {
  display: block;
}
.ctb_global_show .ctb_show + .input_area,
.ctb_global_show .ctb_show + div.text_cell_input,
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border-top-right-radius: 0px;
  border-top-left-radius: 0px;
}
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border: 1px solid #cfcfcf;
}
.celltoolbar {
  font-size: 87%;
  padding-top: 3px;
}
.celltoolbar select {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  width: inherit;
  font-size: inherit;
  height: 22px;
  padding: 0px;
  display: inline-block;
}
.celltoolbar select:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.celltoolbar select::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.celltoolbar select:-ms-input-placeholder {
  color: #999;
}
.celltoolbar select::-webkit-input-placeholder {
  color: #999;
}
.celltoolbar select::-ms-expand {
  border: 0;
  background-color: transparent;
}
.celltoolbar select[disabled],
.celltoolbar select[readonly],
fieldset[disabled] .celltoolbar select {
  background-color: #eeeeee;
  opacity: 1;
}
.celltoolbar select[disabled],
fieldset[disabled] .celltoolbar select {
  cursor: not-allowed;
}
textarea.celltoolbar select {
  height: auto;
}
select.celltoolbar select {
  height: 30px;
  line-height: 30px;
}
textarea.celltoolbar select,
select[multiple].celltoolbar select {
  height: auto;
}
.celltoolbar label {
  margin-left: 5px;
  margin-right: 5px;
}
.tags_button_container {
  width: 100%;
  display: flex;
}
.tag-container {
  display: flex;
  flex-direction: row;
  flex-grow: 1;
  overflow: hidden;
  position: relative;
}
.tag-container > * {
  margin: 0 4px;
}
.remove-tag-btn {
  margin-left: 4px;
}
.tags-input {
  display: flex;
}
.cell-tag:last-child:after {
  content: "";
  position: absolute;
  right: 0;
  width: 40px;
  height: 100%;
  /* Fade to background color of cell toolbar */
  background: linear-gradient(to right, rgba(0, 0, 0, 0), #EEE);
}
.tags-input > * {
  margin-left: 4px;
}
.cell-tag,
.tags-input input,
.tags-input button {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  box-shadow: none;
  width: inherit;
  font-size: inherit;
  height: 22px;
  line-height: 22px;
  padding: 0px 4px;
  display: inline-block;
}
.cell-tag:focus,
.tags-input input:focus,
.tags-input button:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.cell-tag::-moz-placeholder,
.tags-input input::-moz-placeholder,
.tags-input button::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.cell-tag:-ms-input-placeholder,
.tags-input input:-ms-input-placeholder,
.tags-input button:-ms-input-placeholder {
  color: #999;
}
.cell-tag::-webkit-input-placeholder,
.tags-input input::-webkit-input-placeholder,
.tags-input button::-webkit-input-placeholder {
  color: #999;
}
.cell-tag::-ms-expand,
.tags-input input::-ms-expand,
.tags-input button::-ms-expand {
  border: 0;
  background-color: transparent;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
.cell-tag[readonly],
.tags-input input[readonly],
.tags-input button[readonly],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  background-color: #eeeeee;
  opacity: 1;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  cursor: not-allowed;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button {
  height: auto;
}
select.cell-tag,
select.tags-input input,
select.tags-input button {
  height: 30px;
  line-height: 30px;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button,
select[multiple].cell-tag,
select[multiple].tags-input input,
select[multiple].tags-input button {
  height: auto;
}
.cell-tag,
.tags-input button {
  padding: 0px 4px;
}
.cell-tag {
  background-color: #fff;
  white-space: nowrap;
}
.tags-input input[type=text]:focus {
  outline: none;
  box-shadow: none;
  border-color: #ccc;
}
.completions {
  position: absolute;
  z-index: 110;
  overflow: hidden;
  border: 1px solid #ababab;
  border-radius: 2px;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  line-height: 1;
}
.completions select {
  background: white;
  outline: none;
  border: none;
  padding: 0px;
  margin: 0px;
  overflow: auto;
  font-family: monospace;
  font-size: 110%;
  color: #000;
  width: auto;
}
.completions select option.context {
  color: #286090;
}
#kernel_logo_widget .current_kernel_logo {
  display: none;
  margin-top: -1px;
  margin-bottom: -1px;
  width: 32px;
  height: 32px;
}
[dir="rtl"] #kernel_logo_widget {
  float: left !important;
  float: left;
}
.modal .modal-body .move-path {
  display: flex;
  flex-direction: row;
  justify-content: space;
  align-items: center;
}
.modal .modal-body .move-path .server-root {
  padding-right: 20px;
}
.modal .modal-body .move-path .path-input {
  flex: 1;
}
#menubar {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  margin-top: 1px;
}
#menubar .navbar {
  border-top: 1px;
  border-radius: 0px 0px 2px 2px;
  margin-bottom: 0px;
}
#menubar .navbar-toggle {
  float: left;
  padding-top: 7px;
  padding-bottom: 7px;
  border: none;
}
#menubar .navbar-collapse {
  clear: left;
}
[dir="rtl"] #menubar .navbar-toggle {
  float: right;
}
[dir="rtl"] #menubar .navbar-collapse {
  clear: right;
}
[dir="rtl"] #menubar .navbar-nav {
  float: right;
}
[dir="rtl"] #menubar .nav {
  padding-right: 0px;
}
[dir="rtl"] #menubar .navbar-nav > li {
  float: right;
}
[dir="rtl"] #menubar .navbar-right {
  float: left !important;
}
[dir="rtl"] ul.dropdown-menu {
  text-align: right;
  left: auto;
}
[dir="rtl"] ul#new-menu.dropdown-menu {
  right: auto;
  left: 0;
}
.nav-wrapper {
  border-bottom: 1px solid #e7e7e7;
}
i.menu-icon {
  padding-top: 4px;
}
[dir="rtl"] i.menu-icon.pull-right {
  float: left !important;
  float: left;
}
ul#help_menu li a {
  overflow: hidden;
  padding-right: 2.2em;
}
ul#help_menu li a i {
  margin-right: -1.2em;
}
[dir="rtl"] ul#help_menu li a {
  padding-left: 2.2em;
}
[dir="rtl"] ul#help_menu li a i {
  margin-right: 0;
  margin-left: -1.2em;
}
[dir="rtl"] ul#help_menu li a i.pull-right {
  float: left !important;
  float: left;
}
.dropdown-submenu {
  position: relative;
}
.dropdown-submenu > .dropdown-menu {
  top: 0;
  left: 100%;
  margin-top: -6px;
  margin-left: -1px;
}
[dir="rtl"] .dropdown-submenu > .dropdown-menu {
  right: 100%;
  margin-right: -1px;
}
.dropdown-submenu:hover > .dropdown-menu {
  display: block;
}
.dropdown-submenu > a:after {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  content: "\f0da";
  float: right;
  color: #333333;
  margin-top: 2px;
  margin-right: -10px;
}
.dropdown-submenu > a:after.fa-pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.fa-pull-right {
  margin-left: .3em;
}
.dropdown-submenu > a:after.pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.pull-right {
  margin-left: .3em;
}
[dir="rtl"] .dropdown-submenu > a:after {
  float: left;
  content: "\f0d9";
  margin-right: 0;
  margin-left: -10px;
}
.dropdown-submenu:hover > a:after {
  color: #262626;
}
.dropdown-submenu.pull-left {
  float: none;
}
.dropdown-submenu.pull-left > .dropdown-menu {
  left: -100%;
  margin-left: 10px;
}
#notification_area {
  float: right !important;
  float: right;
  z-index: 10;
}
[dir="rtl"] #notification_area {
  float: left !important;
  float: left;
}
.indicator_area {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] .indicator_area {
  float: left !important;
  float: left;
}
#kernel_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  border-left: 1px solid;
}
#kernel_indicator .kernel_indicator_name {
  padding-left: 5px;
  padding-right: 5px;
}
[dir="rtl"] #kernel_indicator {
  float: left !important;
  float: left;
  border-left: 0;
  border-right: 1px solid;
}
#modal_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] #modal_indicator {
  float: left !important;
  float: left;
}
#readonly-indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  margin-top: 2px;
  margin-bottom: 0px;
  margin-left: 0px;
  margin-right: 0px;
  display: none;
}
.modal_indicator:before {
  width: 1.28571429em;
  text-align: center;
}
.edit_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f040";
}
.edit_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.edit_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: ' ';
}
.command_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f10c";
}
.kernel_idle_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f111";
}
.kernel_busy_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f1e2";
}
.kernel_dead_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f127";
}
.kernel_disconnected_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.pull-right {
  margin-left: .3em;
}
.notification_widget {
  color: #777;
  z-index: 10;
  background: rgba(240, 240, 240, 0.5);
  margin-right: 4px;
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget:focus,
.notification_widget.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.notification_widget:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active:hover,
.notification_widget.active:hover,
.open > .dropdown-toggle.notification_widget:hover,
.notification_widget:active:focus,
.notification_widget.active:focus,
.open > .dropdown-toggle.notification_widget:focus,
.notification_widget:active.focus,
.notification_widget.active.focus,
.open > .dropdown-toggle.notification_widget.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  background-image: none;
}
.notification_widget.disabled:hover,
.notification_widget[disabled]:hover,
fieldset[disabled] .notification_widget:hover,
.notification_widget.disabled:focus,
.notification_widget[disabled]:focus,
fieldset[disabled] .notification_widget:focus,
.notification_widget.disabled.focus,
.notification_widget[disabled].focus,
fieldset[disabled] .notification_widget.focus {
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget .badge {
  color: #fff;
  background-color: #333;
}
.notification_widget.warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning:focus,
.notification_widget.warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.notification_widget.warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active:hover,
.notification_widget.warning.active:hover,
.open > .dropdown-toggle.notification_widget.warning:hover,
.notification_widget.warning:active:focus,
.notification_widget.warning.active:focus,
.open > .dropdown-toggle.notification_widget.warning:focus,
.notification_widget.warning:active.focus,
.notification_widget.warning.active.focus,
.open > .dropdown-toggle.notification_widget.warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  background-image: none;
}
.notification_widget.warning.disabled:hover,
.notification_widget.warning[disabled]:hover,
fieldset[disabled] .notification_widget.warning:hover,
.notification_widget.warning.disabled:focus,
.notification_widget.warning[disabled]:focus,
fieldset[disabled] .notification_widget.warning:focus,
.notification_widget.warning.disabled.focus,
.notification_widget.warning[disabled].focus,
fieldset[disabled] .notification_widget.warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.notification_widget.success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success:focus,
.notification_widget.success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.notification_widget.success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active:hover,
.notification_widget.success.active:hover,
.open > .dropdown-toggle.notification_widget.success:hover,
.notification_widget.success:active:focus,
.notification_widget.success.active:focus,
.open > .dropdown-toggle.notification_widget.success:focus,
.notification_widget.success:active.focus,
.notification_widget.success.active.focus,
.open > .dropdown-toggle.notification_widget.success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  background-image: none;
}
.notification_widget.success.disabled:hover,
.notification_widget.success[disabled]:hover,
fieldset[disabled] .notification_widget.success:hover,
.notification_widget.success.disabled:focus,
.notification_widget.success[disabled]:focus,
fieldset[disabled] .notification_widget.success:focus,
.notification_widget.success.disabled.focus,
.notification_widget.success[disabled].focus,
fieldset[disabled] .notification_widget.success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.notification_widget.info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info:focus,
.notification_widget.info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.notification_widget.info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active:hover,
.notification_widget.info.active:hover,
.open > .dropdown-toggle.notification_widget.info:hover,
.notification_widget.info:active:focus,
.notification_widget.info.active:focus,
.open > .dropdown-toggle.notification_widget.info:focus,
.notification_widget.info:active.focus,
.notification_widget.info.active.focus,
.open > .dropdown-toggle.notification_widget.info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  background-image: none;
}
.notification_widget.info.disabled:hover,
.notification_widget.info[disabled]:hover,
fieldset[disabled] .notification_widget.info:hover,
.notification_widget.info.disabled:focus,
.notification_widget.info[disabled]:focus,
fieldset[disabled] .notification_widget.info:focus,
.notification_widget.info.disabled.focus,
.notification_widget.info[disabled].focus,
fieldset[disabled] .notification_widget.info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.notification_widget.danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger:focus,
.notification_widget.danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.notification_widget.danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active:hover,
.notification_widget.danger.active:hover,
.open > .dropdown-toggle.notification_widget.danger:hover,
.notification_widget.danger:active:focus,
.notification_widget.danger.active:focus,
.open > .dropdown-toggle.notification_widget.danger:focus,
.notification_widget.danger:active.focus,
.notification_widget.danger.active.focus,
.open > .dropdown-toggle.notification_widget.danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  background-image: none;
}
.notification_widget.danger.disabled:hover,
.notification_widget.danger[disabled]:hover,
fieldset[disabled] .notification_widget.danger:hover,
.notification_widget.danger.disabled:focus,
.notification_widget.danger[disabled]:focus,
fieldset[disabled] .notification_widget.danger:focus,
.notification_widget.danger.disabled.focus,
.notification_widget.danger[disabled].focus,
fieldset[disabled] .notification_widget.danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger .badge {
  color: #d9534f;
  background-color: #fff;
}
div#pager {
  background-color: #fff;
  font-size: 14px;
  line-height: 20px;
  overflow: hidden;
  display: none;
  position: fixed;
  bottom: 0px;
  width: 100%;
  max-height: 50%;
  padding-top: 8px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  /* Display over codemirror */
  z-index: 100;
  /* Hack which prevents jquery ui resizable from changing top. */
  top: auto !important;
}
div#pager pre {
  line-height: 1.21429em;
  color: #000;
  background-color: #f7f7f7;
  padding: 0.4em;
}
div#pager #pager-button-area {
  position: absolute;
  top: 8px;
  right: 20px;
}
div#pager #pager-contents {
  position: relative;
  overflow: auto;
  width: 100%;
  height: 100%;
}
div#pager #pager-contents #pager-container {
  position: relative;
  padding: 15px 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
div#pager .ui-resizable-handle {
  top: 0px;
  height: 8px;
  background: #f7f7f7;
  border-top: 1px solid #cfcfcf;
  border-bottom: 1px solid #cfcfcf;
  /* This injects handle bars (a short, wide = symbol) for 
        the resize handle. */
}
div#pager .ui-resizable-handle::after {
  content: '';
  top: 2px;
  left: 50%;
  height: 3px;
  width: 30px;
  margin-left: -15px;
  position: absolute;
  border-top: 1px solid #cfcfcf;
}
.quickhelp {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  line-height: 1.8em;
}
.shortcut_key {
  display: inline-block;
  width: 21ex;
  text-align: right;
  font-family: monospace;
}
.shortcut_descr {
  display: inline-block;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
span.save_widget {
  height: 30px;
  margin-top: 4px;
  display: flex;
  justify-content: flex-start;
  align-items: baseline;
  width: 50%;
  flex: 1;
}
span.save_widget span.filename {
  height: 100%;
  line-height: 1em;
  margin-left: 16px;
  border: none;
  font-size: 146.5%;
  text-overflow: ellipsis;
  overflow: hidden;
  white-space: nowrap;
  border-radius: 2px;
}
span.save_widget span.filename:hover {
  background-color: #e6e6e6;
}
[dir="rtl"] span.save_widget.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] span.save_widget span.filename {
  margin-left: 0;
  margin-right: 16px;
}
span.checkpoint_status,
span.autosave_status {
  font-size: small;
  white-space: nowrap;
  padding: 0 5px;
}
@media (max-width: 767px) {
  span.save_widget {
    font-size: small;
    padding: 0 0 0 5px;
  }
  span.checkpoint_status,
  span.autosave_status {
    display: none;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  span.checkpoint_status {
    display: none;
  }
  span.autosave_status {
    font-size: x-small;
  }
}
.toolbar {
  padding: 0px;
  margin-left: -5px;
  margin-top: 2px;
  margin-bottom: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.toolbar select,
.toolbar label {
  width: auto;
  vertical-align: middle;
  margin-right: 2px;
  margin-bottom: 0px;
  display: inline;
  font-size: 92%;
  margin-left: 0.3em;
  margin-right: 0.3em;
  padding: 0px;
  padding-top: 3px;
}
.toolbar .btn {
  padding: 2px 8px;
}
.toolbar .btn-group {
  margin-top: 0px;
  margin-left: 5px;
}
.toolbar-btn-label {
  margin-left: 6px;
}
#maintoolbar {
  margin-bottom: -3px;
  margin-top: -8px;
  border: 0px;
  min-height: 27px;
  margin-left: 0px;
  padding-top: 11px;
  padding-bottom: 3px;
}
#maintoolbar .navbar-text {
  float: none;
  vertical-align: middle;
  text-align: right;
  margin-left: 5px;
  margin-right: 0px;
  margin-top: 0px;
}
.select-xs {
  height: 24px;
}
[dir="rtl"] .btn-group > .btn,
.btn-group-vertical > .btn {
  float: right;
}
.pulse,
.dropdown-menu > li > a.pulse,
li.pulse > a.dropdown-toggle,
li.pulse.open > a.dropdown-toggle {
  background-color: #F37626;
  color: white;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
/** WARNING IF YOU ARE EDITTING THIS FILE, if this is a .css file, It has a lot
 * of chance of beeing generated from the ../less/[samename].less file, you can
 * try to get back the less file by reverting somme commit in history
 **/
/*
 * We'll try to get something pretty, so we
 * have some strange css to have the scroll bar on
 * the left with fix button on the top right of the tooltip
 */
@-moz-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-moz-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
/*properties of tooltip after "expand"*/
.bigtooltip {
  overflow: auto;
  height: 200px;
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
}
/*properties of tooltip before "expand"*/
.smalltooltip {
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
  text-overflow: ellipsis;
  overflow: hidden;
  height: 80px;
}
.tooltipbuttons {
  position: absolute;
  padding-right: 15px;
  top: 0px;
  right: 0px;
}
.tooltiptext {
  /*avoid the button to overlap on some docstring*/
  padding-right: 30px;
}
.ipython_tooltip {
  max-width: 700px;
  /*fade-in animation when inserted*/
  -webkit-animation: fadeOut 400ms;
  -moz-animation: fadeOut 400ms;
  animation: fadeOut 400ms;
  -webkit-animation: fadeIn 400ms;
  -moz-animation: fadeIn 400ms;
  animation: fadeIn 400ms;
  vertical-align: middle;
  background-color: #f7f7f7;
  overflow: visible;
  border: #ababab 1px solid;
  outline: none;
  padding: 3px;
  margin: 0px;
  padding-left: 7px;
  font-family: monospace;
  min-height: 50px;
  -moz-box-shadow: 0px 6px 10px -1px #adadad;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  border-radius: 2px;
  position: absolute;
  z-index: 1000;
}
.ipython_tooltip a {
  float: right;
}
.ipython_tooltip .tooltiptext pre {
  border: 0;
  border-radius: 0;
  font-size: 100%;
  background-color: #f7f7f7;
}
.pretooltiparrow {
  left: 0px;
  margin: 0px;
  top: -16px;
  width: 40px;
  height: 16px;
  overflow: hidden;
  position: absolute;
}
.pretooltiparrow:before {
  background-color: #f7f7f7;
  border: 1px #ababab solid;
  z-index: 11;
  content: "";
  position: absolute;
  left: 15px;
  top: 10px;
  width: 25px;
  height: 25px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
ul.typeahead-list i {
  margin-left: -10px;
  width: 18px;
}
[dir="rtl"] ul.typeahead-list i {
  margin-left: 0;
  margin-right: -10px;
}
ul.typeahead-list {
  max-height: 80vh;
  overflow: auto;
}
ul.typeahead-list > li > a {
  /** Firefox bug **/
  /* see https://github.com/jupyter/notebook/issues/559 */
  white-space: normal;
}
ul.typeahead-list  > li > a.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .typeahead-list {
  text-align: right;
}
.cmd-palette .modal-body {
  padding: 7px;
}
.cmd-palette form {
  background: white;
}
.cmd-palette input {
  outline: none;
}
.no-shortcut {
  min-width: 20px;
  color: transparent;
}
[dir="rtl"] .no-shortcut.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .command-shortcut.pull-right {
  float: left !important;
  float: left;
}
.command-shortcut:before {
  content: "(command mode)";
  padding-right: 3px;
  color: #777777;
}
.edit-shortcut:before {
  content: "(edit)";
  padding-right: 3px;
  color: #777777;
}
[dir="rtl"] .edit-shortcut.pull-right {
  float: left !important;
  float: left;
}
#find-and-replace #replace-preview .match,
#find-and-replace #replace-preview .insert {
  background-color: #BBDEFB;
  border-color: #90CAF9;
  border-style: solid;
  border-width: 1px;
  border-radius: 0px;
}
[dir="ltr"] #find-and-replace .input-group-btn + .form-control {
  border-left: none;
}
[dir="rtl"] #find-and-replace .input-group-btn + .form-control {
  border-right: none;
}
#find-and-replace #replace-preview .replace .match {
  background-color: #FFCDD2;
  border-color: #EF9A9A;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .insert {
  background-color: #C8E6C9;
  border-color: #A5D6A7;
  border-radius: 0px;
}
#find-and-replace #replace-preview {
  max-height: 60vh;
  overflow: auto;
}
#find-and-replace #replace-preview pre {
  padding: 5px 10px;
}
.terminal-app {
  background: #EEE;
}
.terminal-app #header {
  background: #fff;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.terminal-app .terminal {
  width: 100%;
  float: left;
  font-family: monospace;
  color: white;
  background: black;
  padding: 0.4em;
  border-radius: 2px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
}
.terminal-app .terminal,
.terminal-app .terminal dummy-screen {
  line-height: 1em;
  font-size: 14px;
}
.terminal-app .terminal .xterm-rows {
  padding: 10px;
}
.terminal-app .terminal-cursor {
  color: black;
  background: white;
}
.terminal-app #terminado-container {
  margin-top: 20px;
}
/*# sourceMappingURL=style.min.css.map */
    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sa { color: #BA2121 } /* Literal.String.Affix */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .dl { color: #BA2121 } /* Literal.String.Delimiter */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .fm { color: #0000FF } /* Name.Function.Magic */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .vm { color: #19177C } /* Name.Variable.Magic */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>
<style type="text/css">
    
/* Temporary definitions which will become obsolete with Notebook release 5.0 */
.ansi-black-fg { color: #3E424D; }
.ansi-black-bg { background-color: #3E424D; }
.ansi-black-intense-fg { color: #282C36; }
.ansi-black-intense-bg { background-color: #282C36; }
.ansi-red-fg { color: #E75C58; }
.ansi-red-bg { background-color: #E75C58; }
.ansi-red-intense-fg { color: #B22B31; }
.ansi-red-intense-bg { background-color: #B22B31; }
.ansi-green-fg { color: #00A250; }
.ansi-green-bg { background-color: #00A250; }
.ansi-green-intense-fg { color: #007427; }
.ansi-green-intense-bg { background-color: #007427; }
.ansi-yellow-fg { color: #DDB62B; }
.ansi-yellow-bg { background-color: #DDB62B; }
.ansi-yellow-intense-fg { color: #B27D12; }
.ansi-yellow-intense-bg { background-color: #B27D12; }
.ansi-blue-fg { color: #208FFB; }
.ansi-blue-bg { background-color: #208FFB; }
.ansi-blue-intense-fg { color: #0065CA; }
.ansi-blue-intense-bg { background-color: #0065CA; }
.ansi-magenta-fg { color: #D160C4; }
.ansi-magenta-bg { background-color: #D160C4; }
.ansi-magenta-intense-fg { color: #A03196; }
.ansi-magenta-intense-bg { background-color: #A03196; }
.ansi-cyan-fg { color: #60C6C8; }
.ansi-cyan-bg { background-color: #60C6C8; }
.ansi-cyan-intense-fg { color: #258F8F; }
.ansi-cyan-intense-bg { background-color: #258F8F; }
.ansi-white-fg { color: #C5C1B4; }
.ansi-white-bg { background-color: #C5C1B4; }
.ansi-white-intense-fg { color: #A1A6B2; }
.ansi-white-intense-bg { background-color: #A1A6B2; }

.ansi-bold { font-weight: bold; }

    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="./CNN_V6_MSDS_458_Image_Classification_NN_files/custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="./CNN_V6_MSDS_458_Image_Classification_NN_files/MathJax.js.download"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config;executed=true">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --><style type="text/css">.MathJax_Hover_Frame {border-radius: .25em; -webkit-border-radius: .25em; -moz-border-radius: .25em; -khtml-border-radius: .25em; box-shadow: 0px 0px 15px #83A; -webkit-box-shadow: 0px 0px 15px #83A; -moz-box-shadow: 0px 0px 15px #83A; -khtml-box-shadow: 0px 0px 15px #83A; border: 1px solid #A6D ! important; display: inline-block; position: absolute}
.MathJax_Menu_Button .MathJax_Hover_Arrow {position: absolute; cursor: pointer; display: inline-block; border: 2px solid #AAA; border-radius: 4px; -webkit-border-radius: 4px; -moz-border-radius: 4px; -khtml-border-radius: 4px; font-family: 'Courier New',Courier; font-size: 9px; color: #F0F0F0}
.MathJax_Menu_Button .MathJax_Hover_Arrow span {display: block; background-color: #AAA; border: 1px solid; border-radius: 3px; line-height: 0; padding: 4px}
.MathJax_Hover_Arrow:hover {color: white!important; border: 2px solid #CCC!important}
.MathJax_Hover_Arrow:hover span {background-color: #CCC!important}
</style><style type="text/css">#MathJax_About {position: fixed; left: 50%; width: auto; text-align: center; border: 3px outset; padding: 1em 2em; background-color: #DDDDDD; color: black; cursor: default; font-family: message-box; font-size: 120%; font-style: normal; text-indent: 0; text-transform: none; line-height: normal; letter-spacing: normal; word-spacing: normal; word-wrap: normal; white-space: nowrap; float: none; z-index: 201; border-radius: 15px; -webkit-border-radius: 15px; -moz-border-radius: 15px; -khtml-border-radius: 15px; box-shadow: 0px 10px 20px #808080; -webkit-box-shadow: 0px 10px 20px #808080; -moz-box-shadow: 0px 10px 20px #808080; -khtml-box-shadow: 0px 10px 20px #808080; filter: progid:DXImageTransform.Microsoft.dropshadow(OffX=2, OffY=2, Color='gray', Positive='true')}
#MathJax_About.MathJax_MousePost {outline: none}
.MathJax_Menu {position: absolute; background-color: white; color: black; width: auto; padding: 2px; border: 1px solid #CCCCCC; margin: 0; cursor: default; font: menu; text-align: left; text-indent: 0; text-transform: none; line-height: normal; letter-spacing: normal; word-spacing: normal; word-wrap: normal; white-space: nowrap; float: none; z-index: 201; box-shadow: 0px 10px 20px #808080; -webkit-box-shadow: 0px 10px 20px #808080; -moz-box-shadow: 0px 10px 20px #808080; -khtml-box-shadow: 0px 10px 20px #808080; filter: progid:DXImageTransform.Microsoft.dropshadow(OffX=2, OffY=2, Color='gray', Positive='true')}
.MathJax_MenuItem {padding: 2px 2em; background: transparent}
.MathJax_MenuArrow {position: absolute; right: .5em; padding-top: .25em; color: #666666; font-size: .75em}
.MathJax_MenuActive .MathJax_MenuArrow {color: white}
.MathJax_MenuArrow.RTL {left: .5em; right: auto}
.MathJax_MenuCheck {position: absolute; left: .7em}
.MathJax_MenuCheck.RTL {right: .7em; left: auto}
.MathJax_MenuRadioCheck {position: absolute; left: 1em}
.MathJax_MenuRadioCheck.RTL {right: 1em; left: auto}
.MathJax_MenuLabel {padding: 2px 2em 4px 1.33em; font-style: italic}
.MathJax_MenuRule {border-top: 1px solid #CCCCCC; margin: 4px 1px 0px}
.MathJax_MenuDisabled {color: GrayText}
.MathJax_MenuActive {background-color: Highlight; color: HighlightText}
.MathJax_MenuDisabled:focus, .MathJax_MenuLabel:focus {background-color: #E8E8E8}
.MathJax_ContextMenu:focus {outline: none}
.MathJax_ContextMenu .MathJax_MenuItem:focus {outline: none}
#MathJax_AboutClose {top: .2em; right: .2em}
.MathJax_Menu .MathJax_MenuClose {top: -10px; left: -10px}
.MathJax_MenuClose {position: absolute; cursor: pointer; display: inline-block; border: 2px solid #AAA; border-radius: 18px; -webkit-border-radius: 18px; -moz-border-radius: 18px; -khtml-border-radius: 18px; font-family: 'Courier New',Courier; font-size: 24px; color: #F0F0F0}
.MathJax_MenuClose span {display: block; background-color: #AAA; border: 1.5px solid; border-radius: 18px; -webkit-border-radius: 18px; -moz-border-radius: 18px; -khtml-border-radius: 18px; line-height: 0; padding: 8px 0 6px}
.MathJax_MenuClose:hover {color: white!important; border: 2px solid #CCC!important}
.MathJax_MenuClose:hover span {background-color: #CCC!important}
.MathJax_MenuClose:hover:focus {outline: none}
</style><style type="text/css">.MathJax_Preview .MJXf-math {color: inherit!important}
</style><style type="text/css">.MJX_Assistive_MathML {position: absolute!important; top: 0; left: 0; clip: rect(1px, 1px, 1px, 1px); padding: 1px 0 0 0!important; border: 0!important; height: 1px!important; width: 1px!important; overflow: hidden!important; display: block!important; -webkit-touch-callout: none; -webkit-user-select: none; -khtml-user-select: none; -moz-user-select: none; -ms-user-select: none; user-select: none}
.MJX_Assistive_MathML.MJX_Assistive_MathML_Block {width: 100%!important}
</style><style type="text/css">#MathJax_Zoom {position: absolute; background-color: #F0F0F0; overflow: auto; display: block; z-index: 301; padding: .5em; border: 1px solid black; margin: 0; font-weight: normal; font-style: normal; text-align: left; text-indent: 0; text-transform: none; line-height: normal; letter-spacing: normal; word-spacing: normal; word-wrap: normal; white-space: nowrap; float: none; -webkit-box-sizing: content-box; -moz-box-sizing: content-box; box-sizing: content-box; box-shadow: 5px 5px 15px #AAAAAA; -webkit-box-shadow: 5px 5px 15px #AAAAAA; -moz-box-shadow: 5px 5px 15px #AAAAAA; -khtml-box-shadow: 5px 5px 15px #AAAAAA; filter: progid:DXImageTransform.Microsoft.dropshadow(OffX=2, OffY=2, Color='gray', Positive='true')}
#MathJax_ZoomOverlay {position: absolute; left: 0; top: 0; z-index: 300; display: inline-block; width: 100%; height: 100%; border: 0; padding: 0; margin: 0; background-color: white; opacity: 0; filter: alpha(opacity=0)}
#MathJax_ZoomFrame {position: relative; display: inline-block; height: 0; width: 0}
#MathJax_ZoomEventTrap {position: absolute; left: 0; top: 0; z-index: 302; display: inline-block; border: 0; padding: 0; margin: 0; background-color: white; opacity: 0; filter: alpha(opacity=0)}
</style><style type="text/css">.MathJax_Preview {color: #888}
#MathJax_Message {position: fixed; left: 1em; bottom: 1.5em; background-color: #E6E6E6; border: 1px solid #959595; margin: 0px; padding: 2px 8px; z-index: 102; color: black; font-size: 80%; width: auto; white-space: nowrap}
#MathJax_MSIE_Frame {position: absolute; top: 0; left: 0; width: 0px; z-index: 101; border: 0px; margin: 0px; padding: 0px}
.MathJax_Error {color: #CC0000; font-style: italic}
</style><style type="text/css">.MJXp-script {font-size: .8em}
.MJXp-right {-webkit-transform-origin: right; -moz-transform-origin: right; -ms-transform-origin: right; -o-transform-origin: right; transform-origin: right}
.MJXp-bold {font-weight: bold}
.MJXp-italic {font-style: italic}
.MJXp-scr {font-family: MathJax_Script,'Times New Roman',Times,STIXGeneral,serif}
.MJXp-frak {font-family: MathJax_Fraktur,'Times New Roman',Times,STIXGeneral,serif}
.MJXp-sf {font-family: MathJax_SansSerif,'Times New Roman',Times,STIXGeneral,serif}
.MJXp-cal {font-family: MathJax_Caligraphic,'Times New Roman',Times,STIXGeneral,serif}
.MJXp-mono {font-family: MathJax_Typewriter,'Times New Roman',Times,STIXGeneral,serif}
.MJXp-largeop {font-size: 150%}
.MJXp-largeop.MJXp-int {vertical-align: -.2em}
.MJXp-math {display: inline-block; line-height: 1.2; text-indent: 0; font-family: 'Times New Roman',Times,STIXGeneral,serif; white-space: nowrap; border-collapse: collapse}
.MJXp-display {display: block; text-align: center; margin: 1em 0}
.MJXp-math span {display: inline-block}
.MJXp-box {display: block!important; text-align: center}
.MJXp-box:after {content: " "}
.MJXp-rule {display: block!important; margin-top: .1em}
.MJXp-char {display: block!important}
.MJXp-mo {margin: 0 .15em}
.MJXp-mfrac {margin: 0 .125em; vertical-align: .25em}
.MJXp-denom {display: inline-table!important; width: 100%}
.MJXp-denom > * {display: table-row!important}
.MJXp-surd {vertical-align: top}
.MJXp-surd > * {display: block!important}
.MJXp-script-box > *  {display: table!important; height: 50%}
.MJXp-script-box > * > * {display: table-cell!important; vertical-align: top}
.MJXp-script-box > *:last-child > * {vertical-align: bottom}
.MJXp-script-box > * > * > * {display: block!important}
.MJXp-mphantom {visibility: hidden}
.MJXp-munderover {display: inline-table!important}
.MJXp-over {display: inline-block!important; text-align: center}
.MJXp-over > * {display: block!important}
.MJXp-munderover > * {display: table-row!important}
.MJXp-mtable {vertical-align: .25em; margin: 0 .125em}
.MJXp-mtable > * {display: inline-table!important; vertical-align: middle}
.MJXp-mtr {display: table-row!important}
.MJXp-mtd {display: table-cell!important; text-align: center; padding: .5em 0 0 .5em}
.MJXp-mtr > .MJXp-mtd:first-child {padding-left: 0}
.MJXp-mtr:first-child > .MJXp-mtd {padding-top: 0}
.MJXp-mlabeledtr {display: table-row!important}
.MJXp-mlabeledtr > .MJXp-mtd:first-child {padding-left: 0}
.MJXp-mlabeledtr:first-child > .MJXp-mtd {padding-top: 0}
.MJXp-merror {background-color: #FFFF88; color: #CC0000; border: 1px solid #CC0000; padding: 1px 3px; font-style: normal; font-size: 90%}
.MJXp-scale0 {-webkit-transform: scaleX(.0); -moz-transform: scaleX(.0); -ms-transform: scaleX(.0); -o-transform: scaleX(.0); transform: scaleX(.0)}
.MJXp-scale1 {-webkit-transform: scaleX(.1); -moz-transform: scaleX(.1); -ms-transform: scaleX(.1); -o-transform: scaleX(.1); transform: scaleX(.1)}
.MJXp-scale2 {-webkit-transform: scaleX(.2); -moz-transform: scaleX(.2); -ms-transform: scaleX(.2); -o-transform: scaleX(.2); transform: scaleX(.2)}
.MJXp-scale3 {-webkit-transform: scaleX(.3); -moz-transform: scaleX(.3); -ms-transform: scaleX(.3); -o-transform: scaleX(.3); transform: scaleX(.3)}
.MJXp-scale4 {-webkit-transform: scaleX(.4); -moz-transform: scaleX(.4); -ms-transform: scaleX(.4); -o-transform: scaleX(.4); transform: scaleX(.4)}
.MJXp-scale5 {-webkit-transform: scaleX(.5); -moz-transform: scaleX(.5); -ms-transform: scaleX(.5); -o-transform: scaleX(.5); transform: scaleX(.5)}
.MJXp-scale6 {-webkit-transform: scaleX(.6); -moz-transform: scaleX(.6); -ms-transform: scaleX(.6); -o-transform: scaleX(.6); transform: scaleX(.6)}
.MJXp-scale7 {-webkit-transform: scaleX(.7); -moz-transform: scaleX(.7); -ms-transform: scaleX(.7); -o-transform: scaleX(.7); transform: scaleX(.7)}
.MJXp-scale8 {-webkit-transform: scaleX(.8); -moz-transform: scaleX(.8); -ms-transform: scaleX(.8); -o-transform: scaleX(.8); transform: scaleX(.8)}
.MJXp-scale9 {-webkit-transform: scaleX(.9); -moz-transform: scaleX(.9); -ms-transform: scaleX(.9); -o-transform: scaleX(.9); transform: scaleX(.9)}
.MathJax_PHTML .noError {vertical-align: ; font-size: 90%; text-align: left; color: black; padding: 1px 3px; border: 1px solid}
</style></head>
<body style=""><div id="MathJax_Message" style="display: none;"></div>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Kevin-Tong---Bird-Image-Classification">Kevin Tong - Bird Image Classification<a class="anchor-link" href="https://htmtopdf.herokuapp.com/ipynbviewer/temp/76b2494a59eaa356c37baa3190c2ff46/CNN_V6_MSDS_458_Image_Classification_NN.html?t=1692251437780#Kevin-Tong---Bird-Image-Classification">¶</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Packages">Packages<a class="anchor-link" href="https://htmtopdf.herokuapp.com/ipynbviewer/temp/76b2494a59eaa356c37baa3190c2ff46/CNN_V6_MSDS_458_Image_Classification_NN.html?t=1692251437780#Packages">¶</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[80]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="kn">import</span> <span class="nn">datetime</span>
<span class="kn">import</span> <span class="nn">time</span>
<span class="kn">from</span> <span class="nn">packaging</span> <span class="kn">import</span> <span class="n">version</span>
<span class="kn">from</span> <span class="nn">collections</span> <span class="kn">import</span> <span class="n">Counter</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="kn">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="kn">as</span> <span class="nn">pd</span>

<span class="kn">import</span> <span class="nn">matplotlib</span> <span class="kn">as</span> <span class="nn">mpl</span>  <span class="c1"># EA</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="kn">as</span> <span class="nn">plt</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="kn">as</span> <span class="nn">sns</span>

<span class="kn">from</span> <span class="nn">sklearn.metrics</span> <span class="kn">import</span> <span class="n">confusion_matrix</span><span class="p">,</span> <span class="n">classification_report</span>
<span class="kn">from</span> <span class="nn">sklearn.decomposition</span> <span class="kn">import</span> <span class="n">PCA</span>
<span class="kn">from</span> <span class="nn">sklearn.manifold</span> <span class="kn">import</span> <span class="n">TSNE</span>
<span class="kn">from</span> <span class="nn">sklearn.ensemble</span> <span class="kn">import</span> <span class="n">RandomForestClassifier</span>
<span class="kn">from</span> <span class="nn">sklearn.metrics</span> <span class="kn">import</span> <span class="n">mean_squared_error</span> <span class="k">as</span> <span class="n">MSE</span>
<span class="kn">from</span> <span class="nn">sklearn.metrics</span> <span class="kn">import</span> <span class="n">accuracy_score</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">train_test_split</span>

<span class="kn">import</span> <span class="nn">tensorflow</span> <span class="kn">as</span> <span class="nn">tf</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.utils</span> <span class="kn">import</span> <span class="n">to_categorical</span>
<span class="kn">from</span> <span class="nn">tensorflow</span> <span class="kn">import</span> <span class="n">keras</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras</span> <span class="kn">import</span> <span class="n">layers</span><span class="p">,</span> <span class="n">models</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.models</span> <span class="kn">import</span> <span class="n">Sequential</span>
<span class="kn">import</span> <span class="nn">tensorflow.keras.backend</span> <span class="kn">as</span> <span class="nn">z</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.utils</span> <span class="kn">import</span> <span class="n">plot_model</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.layers</span> <span class="kn">import</span> <span class="n">Conv2D</span><span class="p">,</span> <span class="n">MaxPool2D</span><span class="p">,</span> <span class="n">BatchNormalization</span><span class="p">,</span> <span class="n">Dropout</span><span class="p">,</span> <span class="n">Flatten</span><span class="p">,</span> <span class="n">Dense</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.callbacks</span> <span class="kn">import</span> <span class="n">ModelCheckpoint</span><span class="p">,</span> <span class="n">EarlyStopping</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.preprocessing</span> <span class="kn">import</span> <span class="n">image</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.utils</span> <span class="kn">import</span> <span class="n">to_categorical</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.layers</span> <span class="kn">import</span> <span class="n">Dropout</span>
<span class="kn">import</span> <span class="nn">os</span>
<span class="kn">import</span> <span class="nn">cv2</span>
<span class="kn">from</span> <span class="nn">PIL</span> <span class="kn">import</span> <span class="n">Image</span>
<span class="kn">from</span> <span class="nn">tensorflow.keras.regularizers</span> <span class="kn">import</span> <span class="n">l2</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[2]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="c1"># from google.colab import drive</span>
<span class="c1"># drive.mount('/content/drive')</span>
<span class="n">data_dir</span> <span class="o">=</span> <span class="s1">'/content/drive/MyDrive/Northwestern MSDS/MSDS 458/458_Final_Notebooks/spectrogram_output'</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Preprocessing">Preprocessing<a class="anchor-link" href="https://htmtopdf.herokuapp.com/ipynbviewer/temp/76b2494a59eaa356c37baa3190c2ff46/CNN_V6_MSDS_458_Image_Classification_NN.html?t=1692251437780#Preprocessing">¶</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="c1"># Initialize a set to store unique classes (bird species)</span>
<span class="n">unique_classes</span> <span class="o">=</span> <span class="nb">set</span><span class="p">()</span>

<span class="c1"># Define a function to load and preprocess images</span>
<span class="k">def</span> <span class="nf">load_and_preprocess_images</span><span class="p">(</span><span class="n">image_paths</span><span class="p">):</span>
    <span class="n">images</span> <span class="o">=</span> <span class="p">[]</span>
    <span class="k">for</span> <span class="n">path</span> <span class="ow">in</span> <span class="n">image_paths</span><span class="p">:</span>
        <span class="n">img</span> <span class="o">=</span> <span class="n">Image</span><span class="o">.</span><span class="n">open</span><span class="p">(</span><span class="n">path</span><span class="p">)</span>
        <span class="n">img</span> <span class="o">=</span> <span class="n">img</span><span class="o">.</span><span class="n">resize</span><span class="p">((</span><span class="mi">224</span><span class="p">,</span> <span class="mi">224</span><span class="p">))</span>  <span class="c1"># Resize to your desired dimensions</span>
        <span class="n">img</span> <span class="o">=</span> <span class="n">img</span><span class="o">.</span><span class="n">convert</span><span class="p">(</span><span class="s2">"RGB"</span><span class="p">)</span>  <span class="c1"># Convert to RGB (remove alpha channel if present)</span>
        <span class="n">img</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">img</span><span class="p">)</span> <span class="o">/</span> <span class="mf">255.0</span>   <span class="c1"># Normalize pixel values</span>
        <span class="n">images</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">img</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">images</span><span class="p">)</span>

<span class="c1"># Loop through directories and load images</span>
<span class="n">all_images</span> <span class="o">=</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">bird_folder</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">data_dir</span><span class="p">):</span>
    <span class="n">bird_folder_path</span> <span class="o">=</span> <span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">data_dir</span><span class="p">,</span> <span class="n">bird_folder</span><span class="p">)</span>
    <span class="k">if</span> <span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">isdir</span><span class="p">(</span><span class="n">bird_folder_path</span><span class="p">)</span> <span class="ow">and</span> <span class="nb">len</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">bird_folder_path</span><span class="p">))</span> <span class="o">&gt;</span> <span class="mi">1</span><span class="p">:</span>
        <span class="c1"># Add the current folder name to the set of unique classes</span>
        <span class="n">unique_classes</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">bird_folder</span><span class="p">)</span>

        <span class="n">image_paths</span> <span class="o">=</span> <span class="p">[</span><span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">bird_folder_path</span><span class="p">,</span> <span class="n">img</span><span class="p">)</span> <span class="k">for</span> <span class="n">img</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">bird_folder_path</span><span class="p">)]</span>
        <span class="n">images</span> <span class="o">=</span> <span class="n">load_and_preprocess_images</span><span class="p">(</span><span class="n">image_paths</span><span class="p">)</span>
        <span class="n">all_images</span><span class="o">.</span><span class="n">extend</span><span class="p">(</span><span class="n">images</span><span class="p">)</span>

<span class="n">all_images</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span><span class="n">all_images</span><span class="p">)</span>

<span class="c1"># Calculate the total number of classes</span>
<span class="n">num_classes</span> <span class="o">=</span> <span class="nb">len</span><span class="p">(</span><span class="n">unique_classes</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="s2">"Number of classes:"</span><span class="p">,</span> <span class="n">num_classes</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Number of classes: 110
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="c1"># Load and preprocess labels</span>
<span class="n">all_labels</span> <span class="o">=</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">bird_folder</span> <span class="ow">in</span> <span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">data_dir</span><span class="p">):</span>
    <span class="n">bird_folder_path</span> <span class="o">=</span> <span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">data_dir</span><span class="p">,</span> <span class="n">bird_folder</span><span class="p">)</span>
    <span class="k">if</span> <span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">isdir</span><span class="p">(</span><span class="n">bird_folder_path</span><span class="p">)</span> <span class="ow">and</span> <span class="nb">len</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">bird_folder_path</span><span class="p">))</span> <span class="o">&gt;</span> <span class="mi">1</span><span class="p">:</span>
        <span class="n">label</span> <span class="o">=</span> <span class="n">bird_folder</span>  <span class="c1"># Assuming folder name is the label</span>
        <span class="n">labels</span> <span class="o">=</span> <span class="p">[</span><span class="n">label</span><span class="p">]</span> <span class="o">*</span> <span class="nb">len</span><span class="p">(</span><span class="n">os</span><span class="o">.</span><span class="n">listdir</span><span class="p">(</span><span class="n">bird_folder_path</span><span class="p">))</span>
        <span class="n">all_labels</span><span class="o">.</span><span class="n">extend</span><span class="p">(</span><span class="n">labels</span><span class="p">)</span>

<span class="c1"># Convert labels to numerical format (e.g., one-hot encoding)</span>
<span class="kn">from</span> <span class="nn">sklearn.preprocessing</span> <span class="kn">import</span> <span class="n">LabelEncoder</span><span class="p">,</span> <span class="n">OneHotEncoder</span>

<span class="n">label_encoder</span> <span class="o">=</span> <span class="n">LabelEncoder</span><span class="p">()</span>
<span class="n">integer_encoded</span> <span class="o">=</span> <span class="n">label_encoder</span><span class="o">.</span><span class="n">fit_transform</span><span class="p">(</span><span class="n">all_labels</span><span class="p">)</span>
<span class="n">onehot_encoder</span> <span class="o">=</span> <span class="n">OneHotEncoder</span><span class="p">(</span><span class="n">sparse</span><span class="o">=</span><span class="bp">False</span><span class="p">)</span>
<span class="n">encoded_labels</span> <span class="o">=</span> <span class="n">onehot_encoder</span><span class="o">.</span><span class="n">fit_transform</span><span class="p">(</span><span class="n">integer_encoded</span><span class="o">.</span><span class="n">reshape</span><span class="p">(</span><span class="o">-</span><span class="mi">1</span><span class="p">,</span> <span class="mi">1</span><span class="p">))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stderr output_text">
<pre>/usr/local/lib/python3.10/dist-packages/sklearn/preprocessing/_encoders.py:868: FutureWarning: `sparse` was renamed to `sparse_output` in version 1.2 and will be removed in 1.4. `sparse_output` is ignored unless you leave `sparse` to its default value.
  warnings.warn(
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">train_test_split</span>

<span class="c1"># Split data into training and temporary set (which includes validation and test data)</span>
<span class="n">train_images</span><span class="p">,</span> <span class="n">temp_images</span><span class="p">,</span> <span class="n">train_labels</span><span class="p">,</span> <span class="n">temp_labels</span> <span class="o">=</span> <span class="n">train_test_split</span><span class="p">(</span><span class="n">all_images</span><span class="p">,</span> <span class="n">encoded_labels</span><span class="p">,</span> <span class="n">test_size</span><span class="o">=</span><span class="mf">0.2</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">42</span><span class="p">)</span>

<span class="c1"># Split temporary set into validation and test sets</span>
<span class="n">val_images</span><span class="p">,</span> <span class="n">test_images</span><span class="p">,</span> <span class="n">val_labels</span><span class="p">,</span> <span class="n">test_labels</span> <span class="o">=</span> <span class="n">train_test_split</span><span class="p">(</span><span class="n">temp_images</span><span class="p">,</span> <span class="n">temp_labels</span><span class="p">,</span> <span class="n">test_size</span><span class="o">=</span><span class="mf">0.5</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">42</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="k">print</span><span class="p">(</span><span class="s2">"Train images shape:"</span><span class="p">,</span> <span class="n">train_images</span><span class="o">.</span><span class="n">shape</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="s2">"Validation images shape:"</span><span class="p">,</span> <span class="n">val_images</span><span class="o">.</span><span class="n">shape</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="s2">"Test images shape:"</span><span class="p">,</span> <span class="n">test_images</span><span class="o">.</span><span class="n">shape</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Train images shape: (1725, 224, 224, 3)
Validation images shape: (216, 224, 224, 3)
Test images shape: (216, 224, 224, 3)
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Neural-Network">Neural Network<a class="anchor-link" href="https://htmtopdf.herokuapp.com/ipynbviewer/temp/76b2494a59eaa356c37baa3190c2ff46/CNN_V6_MSDS_458_Image_Classification_NN.html?t=1692251437780#Neural-Network">¶</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[89]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="n">start_time</span> <span class="o">=</span> <span class="n">time</span><span class="o">.</span><span class="n">time</span><span class="p">()</span>

<span class="c1"># Define your CNN model with Conv2D and Dropout layers</span>
<span class="n">model</span> <span class="o">=</span> <span class="n">models</span><span class="o">.</span><span class="n">Sequential</span><span class="p">([</span>
    <span class="n">layers</span><span class="o">.</span><span class="n">Conv2D</span><span class="p">(</span><span class="mi">32</span><span class="p">,</span> <span class="p">(</span><span class="mi">3</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span> <span class="n">activation</span><span class="o">=</span><span class="s1">'relu'</span><span class="p">,</span> <span class="n">input_shape</span><span class="o">=</span><span class="p">(</span><span class="mi">224</span><span class="p">,</span> <span class="mi">224</span><span class="p">,</span> <span class="mi">3</span><span class="p">)),</span>
    <span class="n">layers</span><span class="o">.</span><span class="n">MaxPooling2D</span><span class="p">((</span><span class="mi">2</span><span class="p">,</span> <span class="mi">2</span><span class="p">)),</span>

    <span class="n">layers</span><span class="o">.</span><span class="n">Conv2D</span><span class="p">(</span><span class="mi">32</span><span class="p">,</span> <span class="p">(</span><span class="mi">3</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span> <span class="n">activation</span><span class="o">=</span><span class="s1">'relu'</span><span class="p">),</span>
    <span class="n">layers</span><span class="o">.</span><span class="n">MaxPooling2D</span><span class="p">((</span><span class="mi">2</span><span class="p">,</span> <span class="mi">2</span><span class="p">)),</span>

    <span class="n">layers</span><span class="o">.</span><span class="n">Conv2D</span><span class="p">(</span><span class="mi">32</span><span class="p">,</span> <span class="p">(</span><span class="mi">3</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span> <span class="n">activation</span><span class="o">=</span><span class="s1">'relu'</span><span class="p">),</span>
    <span class="n">layers</span><span class="o">.</span><span class="n">MaxPooling2D</span><span class="p">((</span><span class="mi">2</span><span class="p">,</span> <span class="mi">2</span><span class="p">)),</span>

    <span class="n">layers</span><span class="o">.</span><span class="n">Conv2D</span><span class="p">(</span><span class="mi">32</span><span class="p">,</span> <span class="p">(</span><span class="mi">3</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span> <span class="n">activation</span><span class="o">=</span><span class="s1">'relu'</span><span class="p">),</span>
    <span class="n">layers</span><span class="o">.</span><span class="n">MaxPooling2D</span><span class="p">((</span><span class="mi">2</span><span class="p">,</span> <span class="mi">2</span><span class="p">)),</span>

    <span class="n">layers</span><span class="o">.</span><span class="n">Flatten</span><span class="p">(),</span>

    <span class="c1"># Add dropout layers</span>
    <span class="n">layers</span><span class="o">.</span><span class="n">Dropout</span><span class="p">(</span><span class="mf">0.5</span><span class="p">),</span>  <span class="c1"># Add dropout after flattening</span>
    <span class="n">layers</span><span class="o">.</span><span class="n">Dense</span><span class="p">(</span><span class="mi">128</span><span class="p">,</span> <span class="n">activation</span><span class="o">=</span><span class="s1">'relu'</span><span class="p">),</span>

    <span class="n">layers</span><span class="o">.</span><span class="n">Dropout</span><span class="p">(</span><span class="mf">0.5</span><span class="p">),</span>  <span class="c1"># Add dropout after the first dense layer</span>
    <span class="n">layers</span><span class="o">.</span><span class="n">Dense</span><span class="p">(</span><span class="n">num_classes</span><span class="p">,</span> <span class="n">activation</span><span class="o">=</span><span class="s1">'softmax'</span><span class="p">)</span>  <span class="c1"># num_classes is the number of bird species</span>
<span class="p">])</span>

<span class="c1"># Compile the model</span>
<span class="n">model</span><span class="o">.</span><span class="n">compile</span><span class="p">(</span><span class="n">optimizer</span><span class="o">=</span><span class="s1">'adam'</span><span class="p">,</span>
              <span class="n">loss</span><span class="o">=</span><span class="s1">'categorical_crossentropy'</span><span class="p">,</span>
              <span class="n">metrics</span><span class="o">=</span><span class="p">[</span><span class="s1">'accuracy'</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[90]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="c1"># Print the model summary</span>
<span class="n">model</span><span class="o">.</span><span class="n">summary</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Model: "sequential_14"
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 conv2d_29 (Conv2D)          (None, 222, 222, 32)      896       
                                                                 
 max_pooling2d_29 (MaxPoolin  (None, 111, 111, 32)     0         
 g2D)                                                            
                                                                 
 conv2d_30 (Conv2D)          (None, 109, 109, 32)      9248      
                                                                 
 max_pooling2d_30 (MaxPoolin  (None, 54, 54, 32)       0         
 g2D)                                                            
                                                                 
 conv2d_31 (Conv2D)          (None, 52, 52, 32)        9248      
                                                                 
 max_pooling2d_31 (MaxPoolin  (None, 26, 26, 32)       0         
 g2D)                                                            
                                                                 
 conv2d_32 (Conv2D)          (None, 24, 24, 32)        9248      
                                                                 
 max_pooling2d_32 (MaxPoolin  (None, 12, 12, 32)       0         
 g2D)                                                            
                                                                 
 flatten_14 (Flatten)        (None, 4608)              0         
                                                                 
 dropout_22 (Dropout)        (None, 4608)              0         
                                                                 
 dense_34 (Dense)            (None, 128)               589952    
                                                                 
 dropout_23 (Dropout)        (None, 128)               0         
                                                                 
 dense_35 (Dense)            (None, 110)               14190     
                                                                 
=================================================================
Total params: 632,782
Trainable params: 632,782
Non-trainable params: 0
_________________________________________________________________
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[91]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="c1"># Train the model</span>
<span class="n">history</span> <span class="o">=</span> <span class="n">model</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">train_images</span><span class="p">,</span> <span class="n">train_labels</span><span class="p">,</span> <span class="n">epochs</span><span class="o">=</span><span class="mi">200</span><span class="p">,</span> <span class="n">batch_size</span><span class="o">=</span><span class="mi">64</span><span class="p">,</span>
                    <span class="n">validation_data</span><span class="o">=</span><span class="p">(</span><span class="n">val_images</span><span class="p">,</span> <span class="n">val_labels</span><span class="p">),</span><span class="n">callbacks</span><span class="o">=</span><span class="p">[</span>
                     <span class="n">tf</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">callbacks</span><span class="o">.</span><span class="n">ModelCheckpoint</span><span class="p">(</span><span class="s2">"CNN_model.h5"</span><span class="p">,</span><span class="n">save_best_only</span><span class="o">=</span><span class="bp">True</span><span class="p">,</span><span class="n">save_weights_only</span><span class="o">=</span><span class="bp">False</span><span class="p">)</span>
                     <span class="p">,</span><span class="n">tf</span><span class="o">.</span><span class="n">keras</span><span class="o">.</span><span class="n">callbacks</span><span class="o">.</span><span class="n">EarlyStopping</span><span class="p">(</span><span class="n">monitor</span><span class="o">=</span><span class="s1">'val_accuracy'</span><span class="p">,</span> <span class="n">patience</span><span class="o">=</span><span class="mi">3</span><span class="p">),</span>
                    <span class="p">])</span>

<span class="c1"># Evaluate the model</span>
<span class="n">test_loss</span><span class="p">,</span> <span class="n">test_acc</span> <span class="o">=</span> <span class="n">model</span><span class="o">.</span><span class="n">evaluate</span><span class="p">(</span><span class="n">test_images</span><span class="p">,</span> <span class="n">test_labels</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="s1">'Test accuracy:'</span><span class="p">,</span> <span class="n">test_acc</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Epoch 1/200
27/27 [==============================] - 4s 52ms/step - loss: 4.6891 - accuracy: 0.0104 - val_loss: 4.6637 - val_accuracy: 0.0046
Epoch 2/200
27/27 [==============================] - 1s 25ms/step - loss: 4.6270 - accuracy: 0.0157 - val_loss: 4.6020 - val_accuracy: 0.0093
Epoch 3/200
27/27 [==============================] - 1s 25ms/step - loss: 4.5305 - accuracy: 0.0238 - val_loss: 4.4084 - val_accuracy: 0.0741
Epoch 4/200
27/27 [==============================] - 1s 24ms/step - loss: 4.2104 - accuracy: 0.1003 - val_loss: 4.0688 - val_accuracy: 0.1852
Epoch 5/200
27/27 [==============================] - 1s 25ms/step - loss: 3.7403 - accuracy: 0.1809 - val_loss: 3.2938 - val_accuracy: 0.2546
Epoch 6/200
27/27 [==============================] - 1s 25ms/step - loss: 3.2048 - accuracy: 0.2713 - val_loss: 2.8231 - val_accuracy: 0.3889
Epoch 7/200
27/27 [==============================] - 1s 25ms/step - loss: 2.7759 - accuracy: 0.3542 - val_loss: 2.5749 - val_accuracy: 0.4583
Epoch 8/200
27/27 [==============================] - 1s 27ms/step - loss: 2.3709 - accuracy: 0.4528 - val_loss: 2.2608 - val_accuracy: 0.5231
Epoch 9/200
27/27 [==============================] - 1s 25ms/step - loss: 2.0368 - accuracy: 0.5258 - val_loss: 2.0481 - val_accuracy: 0.5370
Epoch 10/200
27/27 [==============================] - 1s 25ms/step - loss: 1.8291 - accuracy: 0.5548 - val_loss: 1.9154 - val_accuracy: 0.5926
Epoch 11/200
27/27 [==============================] - 1s 24ms/step - loss: 1.5910 - accuracy: 0.5965 - val_loss: 1.7914 - val_accuracy: 0.6204
Epoch 12/200
27/27 [==============================] - 1s 25ms/step - loss: 1.4395 - accuracy: 0.6139 - val_loss: 1.7617 - val_accuracy: 0.6435
Epoch 13/200
27/27 [==============================] - 1s 25ms/step - loss: 1.3622 - accuracy: 0.6429 - val_loss: 1.6273 - val_accuracy: 0.6481
Epoch 14/200
27/27 [==============================] - 1s 23ms/step - loss: 1.1678 - accuracy: 0.6800 - val_loss: 1.6779 - val_accuracy: 0.6528
Epoch 15/200
27/27 [==============================] - 1s 23ms/step - loss: 1.1467 - accuracy: 0.7090 - val_loss: 1.7350 - val_accuracy: 0.6296
Epoch 16/200
27/27 [==============================] - 1s 23ms/step - loss: 1.0149 - accuracy: 0.7322 - val_loss: 1.6636 - val_accuracy: 0.6620
Epoch 17/200
27/27 [==============================] - 1s 23ms/step - loss: 0.9065 - accuracy: 0.7397 - val_loss: 1.6750 - val_accuracy: 0.6713
Epoch 18/200
27/27 [==============================] - 1s 23ms/step - loss: 0.8367 - accuracy: 0.7571 - val_loss: 1.7187 - val_accuracy: 0.6574
Epoch 19/200
27/27 [==============================] - 1s 23ms/step - loss: 0.8080 - accuracy: 0.7762 - val_loss: 1.7561 - val_accuracy: 0.6806
Epoch 20/200
27/27 [==============================] - 1s 23ms/step - loss: 0.7648 - accuracy: 0.7803 - val_loss: 1.7513 - val_accuracy: 0.6574
Epoch 21/200
27/27 [==============================] - 1s 23ms/step - loss: 0.7421 - accuracy: 0.7768 - val_loss: 1.7418 - val_accuracy: 0.6667
Epoch 22/200
27/27 [==============================] - 1s 23ms/step - loss: 0.6925 - accuracy: 0.8075 - val_loss: 1.7076 - val_accuracy: 0.6806
7/7 [==============================] - 0s 8ms/step - loss: 1.7739 - accuracy: 0.6852
Test accuracy: 0.6851851940155029
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[92]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="n">end_time</span> <span class="o">=</span> <span class="n">time</span><span class="o">.</span><span class="n">time</span><span class="p">()</span>
<span class="n">runtime</span> <span class="o">=</span> <span class="n">end_time</span> <span class="o">-</span> <span class="n">start_time</span>
<span class="k">print</span><span class="p">(</span><span class="s1">'Total runtime:'</span><span class="p">,</span> <span class="n">runtime</span><span class="p">,</span> <span class="s1">'seconds'</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Total runtime: 22.1960666179657 seconds
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[93]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="c1"># Plot training and validation accuracy</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">history</span><span class="o">.</span><span class="n">history</span><span class="p">[</span><span class="s1">'accuracy'</span><span class="p">],</span> <span class="n">label</span><span class="o">=</span><span class="s1">'Train Accuracy'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">history</span><span class="o">.</span><span class="n">history</span><span class="p">[</span><span class="s1">'val_accuracy'</span><span class="p">],</span> <span class="n">label</span><span class="o">=</span><span class="s1">'Validation Accuracy'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">'Epochs'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">'Accuracy'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">'Training and Validation Accuracy'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">legend</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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zOzZs3nxxRd58cUXmT17do7Hjx49Srdu3XBycsLR0ZHWrVtz9uxZw+Nz5syhfv36aDQavL29GT58OAAXLlxApVIZ1UolJCSgUqkMsxlv2bIFlUrF2rVrCQoKQqPRsG3bNs6ePcvTTz+Np6cnDg4ONGvWjI0bNxrFlZGRwXvvvYevry8ajYYaNWowe/ZsFEWhRo0aOVY1P3DgACqVijNnzjzyNRGivMjS6thyMo7/LTlI8483MmzBPjadiEOrU2hSpQIf92zAng9DmP5CE9rV9pDEppSSfxcfRVEgK80817ay0081+QiWlpb079+fefPm8eGHHxqGHy5ZsgStVkvfvn1JSUkhKCiI9957DycnJ1avXs1LL72Ev78/zZs3f+Q1dDodzzzzDJ6envz7778kJibm2hfH0dGRefPm4ePjw+HDhxkyZAiOjo68++679O7dmyNHjrBu3TrDF7ezc87RBampqYSGhtKiRQv27NlDXFwcr7zyCsOHDzdK4DZv3oy3tzebN2/mzJkz9O7dm8DAQIYMGfLA53H27Fl27tzJsmXLUBSFt99+m4sXL1K1alUArly5Qps2bWjXrh2bNm3CycmJ7du3k52dDcDMmTMJCwvj008/pXPnziQmJrJ9+/ZHvn73e//995k6dSrVq1fHxcWFS5cu0aVLFz7++GM0Gg0///wz3bt35+TJk1SpUgWA/v37s3PnTr755hsCAgI4f/488fHxqFQqXn75ZebOncuoUaMM15g7dy5t2rShRo0a+Y5PiLIkW6tj17kbrD4czbojMdxMu/tPkLezDc80qcQzTSrj7+5gxiiFKUly8yhZafCJj3mu/UE0WOetz8vLL7/MlClT+Pvvv2nXrh2g/3Lr1asXzs7OODs7G33xjRgxgvXr1/Pbb7/lKbnZuHEjJ06cYP369fj46F+PTz75hM6dOxsdN2bMGMO2n58fo0aNYtGiRbz77rvY2tri4OCApaXlQ5uhFixYQHp6Oj///LOhz8/06dPp3r07n332mWHVeBcXF6ZPn46FhQV16tSha9euREZGPjS5mTNnDp07dzb07wkNDWXu3LlMmDABgBkzZuDs7MyiRYuwsrICoFatWobzP/roI9555x1Gjhxp2NesWbNHvn73mzRpEh07djTcr1ixIgEBAYb7kydPZvny5axatYrhw4dz6tQpfvvtNzZs2EBISAgA1atXNxw/cOBAxo0bx+7du2nevDlZWVksWLAgR22OEOWFVqew58IN/jykT2junY/GzcGazg286dbIm2Z+FfO1DpMoHSS5KSPq1KlDy5YtmTNnDu3atePMmTNs3bqVSZMmAaDVavnkk0/47bffuHLlCpmZmWRkZGBnZ5en8o8fP46vr68hsQFo0aJFjuMWL17MN998w9mzZ0lJSSE7O/uRq7fmdq2AgACjzsytWrVCp9Nx8uRJQ3JTv359LCzuzujp7e3N4cOHH1iuVqvlp59+4uuvvzbse/HFFxk1ahTjxo1DrVZz4MABWrdubUhs7hUXF0d0dDQdOnTI1/PJTdOmTY3up6SkMGHCBFavXs3Vq1fJzs7m1q1bREVFAfomJgsLC9q2bZtreT4+PnTt2pU5c+bQvHlz/vjjDzIyMnjuuecKHasQpYVOp7Av6iZ/HrrKmsNXiUvOMDzmYmdFpwbedG/kTfNqFaW5qYyT5OZRrOz0NSjmunY+DB48mBEjRjBjxgzmzp2Lv7+/4ctwypQpfP3110RERNCwYUPs7e156623yMzMfESpebdz50769evHxIkTCQ0NNdSAfPHFFya7xr3uT0BUKhU6ne4BR8P69eu5cuVKjg7EWq2WyMhIOnbsiK2t7QPPf9hjAGq1/o+lotxdAO9BfYDuH4U2atQoNmzYwNSpU6lRowa2trY8++yzhvfnUdcGeOWVV3jppZf46quvmDt3Lr17985z8ipEaaUoCgcuJbD60FVWH77K1cR0w2NONpaE1veiW4APLf1dZT6ackSSm0dRqfLcNGRuzz//PCNHjmTBggX8/PPPDB061ND/Zvv27Tz99NO8+OKLgL4PzalTp6hXr16eyq5bty6XLl3i6tWreHt7A7Br1y6jY3bs2EHVqlX58MMPDfsuXrxodIy1tTVarfaR15o3bx6pqamGJGD79u2o1Wpq166dp3hzM3v2bPr06WMUH8DHH3/M7Nmz6dixI40aNeKnn34iKysrR/Lk6OiIn58fkZGRtG/fPkf5d0aXXb16lcaNGwPkGPL+INu3b2fgwIH07NkT0NfkXLhwwfB4w4YN0el0/P3334Zmqft16dIFe3t7Zs6cybp16/jnn3/ydG0hSps7c9H8cSia1YeucvnmLcNjDhpLnqznSbcAbx6v4V7qV7cWBSPJTRni4OBA7969GT16NElJSQwcONDwWM2aNVm6dCk7duzAxcWFL7/8ktjY2DwnNyEhIdSqVYsBAwYwZcoUkpKSciQJNWvWJCoqikWLFtGsWTNWr17N8uXLjY7x8/Pj/PnzHDhwgMqVK+Po6Jhjnpl+/foxfvx4BgwYwIQJE7h27RojRozgpZdeMjRJ5de1a9f4448/WLVqFQ0aNDB6rH///vTs2ZMbN24wfPhwpk2bRp8+fRg9ejTOzs7s2rWL5s2bU7t2bSZMmMDrr7+Oh4cHnTt3Jjk5me3btzNixAhsbW157LHH+PTTT6lWrRpxcXFGfZAepmbNmixbtozu3bujUqkYO3asUS2Un58fAwYM4OWXXzZ0KL548SJxcXE8//zzAFhYWDBw4EBGjx5NzZo1c202FKK0UhSFEzHJ/Hk7oblw/e5ADztrC0LqetK1kTdta7ljY1X4BShF6SYpbRkzePBgbt68SWhoqFH/mDFjxtCkSRNCQ0Np164dXl5e+ZoNWK1Ws3z5cm7dukXz5s155ZVX+Pjjj42Oeeqpp3j77bcZPnw4gYGB7Nixg7Fjxxod06tXLzp16kT79u1xd3fPdTi6nZ0d69ev58aNGzRr1oxnn32WDh06MH369Py9GPe40zk5t/4yHTp0wNbWlvnz5+Pq6sqmTZtISUmhbdu2BAUF8cMPPxhqcQYMGEBERATffvst9evXp1u3bpw+fdpQ1pw5c8jOziYoKIi33nqLjz76KE/xffnll7i4uNCyZUu6d+9OaGgoTZo0MTpm5syZPPvss7zxxhvUqVOHIUOGkJqaanTM4MGDyczMZNCgQfl9iYQoMW5lajl+NYk1h68yY/MZRi05SMiXf9P5663M2HyWC9fTsLFS06WhF9/2a8LeMR35pm9jQut7SWIjAFAp93YQKAeSkpJwdnYmMTExR0fX9PR0zp8/T7Vq1bCxKd8rqorSaevWrXTo0IFLly49tJZLPuvC3DKzdVy6mcb5a6lcuJ7KufhULsSncj4+1ajfzL2sLdW0q+VOtwAfOtTxwF4jjQ/lycO+v+8nnwwhyoCMjAyuXbvGhAkTeO655wrcfCeEKWl1CtEJt7hwXZ+0nLudyJyPT+XyzVuGGYFzU8HOimpu9lRztaeamz01PBx4vKYbjjY5RzIKcT9JboQoAxYuXMjgwYMJDAzk559/Nnc4opyKT8lg8Z5LHLyUwPn4VC7eSCMz+8EjGO2sLajmZo+fmz3V3ezxc7Wnmrs+oZGFKUVhSHIjRBkwcOBAow7kQhSnM3EpzN52jt/3XcmRzFhbqKniake1OwmMm74mppqbPR6OGsOITiFMSZIbIYQQ+aYoCv+ev8GPW8+x8XicYX+AbwV6BPpQ3d2B6m72+FSwxUJmABbFTJKbXJSzPtaiHJLPuCiobK2OtUdi+GHrOQ5dTgT004F1rOvJkDbVaVrVRWpjhNlJcnOPO8N909LS8jQjrBClVVqafo6Q3JaZECI3KRnZLN5ziTnbznMlQT9pnsZSzbNBlRn8eDWqy6KTogSR5OYeFhYWVKhQgbg4fRWrnZ2d/AciyhRFUUhLSyMuLo4KFSoYrc0lRG5iEtOZu+M8C/6NIjk9GwBXe2v6t/Djxceq4OqgeUQJQhQ/SW7uc2e16jsJjhBlUYUKFR66MrsQx68m8cPWc6w6EE327SHb1d3teeXx6jzTpJJMlidKNElu7qNSqfD29sbDw+OBix4KUZpZWVlJjY3IlaIobD0dzw9bz7H1dLxhf/NqFXm1dXWeqOOBWjoHi1JAkpsHsLCwkC8AIUS5kJmtY9XBaH7ceo4TMckAqFXQpaE3Q1pXJ8C3gnkDFCKfJLkRQohyKjEtiwW7o5i34zyxSRmAfmK93s18eblVNXwr2pk5QiEKRpIbIYQoZ1Izsvnu77P8uO08aZlaADwcNQxqVY0XmlfB2U5G0YnSrUSsCj5jxgz8/PywsbEhODiY3bt3P/DYdu3aoVKpcty6du1ajBELIUTpo9Up/PbfJdpP3cI3m86QlqmljpcjU58LYNt7TzC0nb8kNqJMMHvNzeLFiwkLC2PWrFkEBwcTERFBaGgoJ0+exMPDI8fxy5YtIzMz03D/+vXrBAQE8NxzzxVn2EIIUarsPHudyX8e49jVJACqVLRjdOc6dGrgJVNeiDJHpZh5qtLg4GCaNWvG9OnTAdDpdPj6+jJixAjef//9R54fERHBuHHjuHr1Kvb29o88Pj9LpgshRGl3Pj6V8DXH+etYLACONpa8+URN+resisZSBk2I0iM/399mrbnJzMxk7969jB492rBPrVYTEhLCzp0781TG7Nmz6dOnzwMTm4yMDDIyMgz3k5KSChe0EEKUAolpWXwdeZqfd14gW6dgoVbRL7gKIzvUlIn3RJln1uQmPj4erVaLp6en0X5PT09OnDjxyPN3797NkSNHmD179gOPCQ8PZ+LEiYWOVQghSoMsrY5fd10kIvI0CWn6ubra13bngy51qenpaObohCgeZu9zUxizZ8+mYcOGNG/e/IHHjB49mrCwMMP9pKQkfH19iyM8IYQoNoqisOlEHB+vOc65a6kA1PJ0YEzXerSp5W7m6IQoXmZNbtzc3LCwsCA2NtZof2xs7COnhk9NTWXRokVMmjTpocdpNBo0GqmCFUKUXcevJvHx6uNsO6OfVdjV3pqwJ2vRu6kvlhYlYlCsEMXKrMmNtbU1QUFBREZG0qNHD0DfoTgyMpLhw4c/9NwlS5aQkZHBiy++WAyRCiFEyROXnM5XG06xeM8ldApYW6h5+fFqvNHeHycbGdItyi+zN0uFhYUxYMAAmjZtSvPmzYmIiCA1NZVBgwYB0L9/fypVqkR4eLjRebNnz6ZHjx64urqaI2whhDCb9Cwts7ed59vNZ0i9PQlf10bevN+pjswqLAQlILnp3bs3165dY9y4ccTExBAYGMi6desMnYyjoqJQq42rVU+ePMm2bdv466+/zBGyEEKYhaIo/HHoKp+tPcGVhFsABFR2Zmy3ejT1q2jm6IQoOcw+z01xk3luhBCl0b6om0z+8xj7oxIA8Ha24b1OdXgqwEdW6hYlizYb0hPB3rQtK6VmnhshhBAPl5iWxcQ/jrJs/xUAbK0sGNrOnyGtq2NrLZPwlRiKAue2wM4ZcO0k1HsKgl+HCuVgdK6iwI1zcHYTnN0MF7ZCjRB4bq7ZQpLkRgghSqg9F27w1qIDXEm4hUoFzzapzKjQ2ng62Zg7NHFHdiYcXQY7pkPs4bv7d06HXTOhfk9oOQJ8As0WYpFIu6FP5s5thrNbIDHK+PGYQ/qkx0xLe0hyI4QQJUy2Vsf0zWf4JvI0OgWqutoR0TuQxlVczB2auONWAuydB/9+B8nR+n1W9tD4RajaAv6bC+f/hiNL9Te/1vokp0ZHUJfC4fnZGXBpt7525txmiD4A3NOrxcIafIPBvz1Ubw/eAWZLbECSGyGEKFGuJNzirUX72XPhJgDPNKnEpKcb4KApx3+udVrISAbbCuaOBG5ehH9nwb6fITNFv8/BC4JfhaBBYHe7Y3f9nnD1oL5G5+gyfVPNha3gVgtaDIdGvcGqBNfAKQpcO3G3qenidshKMz7Go54+kfFvD1VbgvWj13csLtKhWAghSog1h6/y/u+HSErPxkFjycc9G/B0YCVzh1W80m5A3DGIPQoxh/U/445D9i19YnDny9TvcdAU43ISV/bqE5VjK0HRD7/Ho54+UWn4LFg+ZLLYxMv6hGjvT5Bxe31De3do/io0HWzyjrcFlhx7t6np3BZIvmr8uL3H3ZqZ6u3AybtYw8vP97ckN0IIYWZpmdlM+uMYi/ZcAiDAtwLT+jSmimsZnrNGmw3Xz0DsEX0Cc+dn0pW8na+2hMrN737Z+jQGCxPXbul0cHo97Jimr7m4o3o7fROTf4f8Nb2kJ+lrfHbNhKTL+n2WthD4ArQYBq7+Jg0/T/Fc3nO7qWmL/j24l6UNVG119zX2rG/WpiZJbh5CkhshRElyNDqRNxfu5+y1VFQqGNrWn7c71sKqLC2bkBp/TxJzu0bm2knQZuR+fIUq4NlA/2XqWV+/becKF7bd7sC6CW5eMD7Hxhmqtblds/MEVKxW8HizbsHBhbDzW7h+Wr9PbQkNnoWWw8GrYcHLBtBm6WuAdnyjb7oCQAV1uuprgqo8ZtokQqeFG+dvvwf3JJMJUTmP9Wqkf/3824PvYyWq6UySm4eQ5EYIURIoisKc7Rf4bO0JMrU6PJ00fPV8IC1ruJk7tMK5eQGi/jX+Ek2Jzf1YK/t7EpjbSYxnPX2i8ig3zt9NdM7/o59X5V4ufnebsKq1Ads8dMZOjYfdP8CeHyDtun6fxhmaDoTmr4GziZsIFUWfsO2cDqfW3d1fqak+iarTPf+1UQ9r1suNsy9Ua3u7dqYd2Jfcz58kNw8hyY0QwtziUzL435KDbD55DYCQup58/mwjKtpbmzmyQshMhS2f6ud5udMn5V4u1cCrgXGNTAU/04wc0mkher++4+vZTXB5N+iy7z6uUoNPE/0XuP8TULkZWNyz9lb8aX2CcXARZKfr9zlXgceGQpOXiqdvz7WTt2NYfLdGq0IVeGyYfgSWxsH4+Pw261nagkfdu0mkVwN9nyG70jOztSQ3DyHJjRDCnP45dY2w3w4Sn5KBtaWasV3r8uJjVVGZsS9DoZ3eCKvfvtvMUampvg/MnS9Sj7o5v5yLUkYyXNh+d9hy/Cnjx60d9B2S/R7XH3dq7d3HfJroa03qPm36Pjx5kRJ3u/boR7h1Q7/Pxlk/EsvBA2JuNy3lq1mvob6ZTl26J32U5OYhJLkRQphDZraOqX+d5Pt/zgFQy9OBb/o2po5XKf47lBIH60br53EBcKoMXb+A2p3MG9f9Ei/ra3XujAK60+R0r9pd9P1dqrY0a6dZg8y02/1+ZsCNs7kfU5hmvVJIkpuHkORGCFHczsen8ubC/Ry+ou8X8uJjVRjTtR42Vg/4T1pR9HOopMRB6jX9zwpVSs4st4oC++fDX2MgPUHf7BM8FNp/ULw1NAWh0+lnEj67CS7u1C+PEPw6uNU0d2S502nh5Fr9621hWTTNeqWEJDcPIcmNEKK4KIrC0r2XGb/qKGmZ2VS2zSI81IvW3oq+k23KNUiNM05iUuP0+3PrAOr7mL7JpHYX8zUxxJ+GP9/WT0gH+pFD3b+BSk3ME48oNyS5eQhJboQQJqMo+pqLHElKLJmJMZw8ew5tcixuqiQ8VIlYk5W/8q3s9f0s7CrC1UOgu31+xer6eVECXgDrYpoLJzsTtkfAP1NAmwlWdtBuNDz2hnn6pohyR5Kbh5DkRgjxUIoCt27eU4tyT63K/ftSr+m/6PPD2hEc3PWzvTrcvtl7GO+zd9f/vHc6+6SrsPt7+G+OPqECsK0IzV6B5kP0xxeVqF3wx0j9dPygX/G56xf64dZCFBNJbh5CkhshBNosOP6HfgK12zUtRgnLvcOI80LjDA7uKPbunE2zY0esBXE6Z7R2bvRq04Qa1arfTVisbAsXe0YKHPhV39E04aJ+n4UGAnrrO8S61y5c+fe6lQAbJ8Deufr7dm7Q+TNo0KtkdLoV5YokNw8hyY0Q5Vh6on59n39nPXqaf5sKudSq3PnpeXfb3h2sbNhxJp7Jq49z/Kp+7aCnAnz4qGcDnGysHn6dgtJp9Qnajmlw5b+7+2uG6vvl+LUueAKiKHBsBax97+4EfI1fgo6TStW8KKJskeTmISS5EaIcSrh0d+HCzGT9PnsPqPe0fvG/+5uI7N3BMm8T6p27lsIna46z8XgcAE42lozrXp9eTSoVz9w1igKX/tUnOSdWA7f/pHsHQIsRUL+H8YR1j5JwCdaMujtjrmsN6P61fk4YIcxIkpuHkORGiHIker9+Jeejy+/Omute5/ZKzs8Vat2chLRMvo48zS87L5KtU7BQq3jpsaqM7FATF3PNNHz9LOz6Fvb/ene0lVNleOx1aDIAbB7yN0+n1ffpiZwMWamgtoLWYfB4WIlaX0iUX5LcPIQkN0KUcTodnP5LP5X9neHKoF9fqOWb+pWcCzE3SJZWxy87L/J15GkSb+lHL3Wo48HoLnWp4VFC5nhJva7veLz7O30fIgCNEzTpr19SwLmy8fFXD+o7DEfv19/3fUxfW+NRp3jjFuIhJLl5CEluhCijstLh0GJ9UnNnun21JdR/Rt8HxTugUMUrisLG43GErznOufhUAOp4OTKmaz0er1lCFxvMSofDv+lrr+JP6vepLaF+T33tlVtN4/WgNM7QcaK+lqccTQ4nSgdJbh5CkhshypjU6/p1ePb8YFxLETRAP/Ps/bUUBXA0OpGPVx9nx1n9tP1uDta882Rtnm/qi4W6FIwa0ungzEbY8Y1xbZaN893VtOv10I+EcvQyS4hCPEp+vr9l5iUhROkUfwZ2zYADC+/2L3H21Te7NH7p4f1L8iguKZ0v/jrFb3svoShgbanmlcerMbSdP45FNQqqKKjVUOtJ/S36gL5268gyfWJTUteDEqIQpOZGCFF6KIp+Qrkd0+DkGu6ODAqEliP0o5/yMzLoAdKztPy49RzfbjlLWqa+I3K3Rt6816kOvhWLaUbgopZwST/Kqlankr8elBBIzY0QoqzRZsOJO3O67L27v1YnfVJTtZVJJpVTFIVVB6P5bO0JohPTAQj0rcDYbvUIqupS6PJLlAq++psQZZAkN0KIkkunhYML4e/P75uNt49+bSUTzsa79+JNJv95jAOXEgDwcbbhvc516N7IB3Vp6FcjhDCQ5EYIUfIoCpxar5/6/9px/T47V/06Ss2G6GcHNpHLN9P4dO0J/jx0VX8ZawveaOfPK62rY2NlppW3hRCFIsmNEKJkufwfbBgHF7fr79tUgNbv6BMbE66AnZKRzbebz/DjtvNkZutQqeD5IF/eCa2Fh6NMWidEaSbJjRCiZIg/A5ET4fgq/X0LjX5m3cffBlvT9HfJyNay9VQ8fx6KZuPxOFIy9AtktvR3ZUzXetTzkUEGQpQFktwIIcwrORb+/lS/7pOiBZUaAl6A9qNNMkdNllbHtjPx/HnwKn8diyE5/e6K39Xd7RnduS4hdT2KZx0oIUSxMHtyM2PGDKZMmUJMTAwBAQFMmzaN5s2bP/D4hIQEPvzwQ5YtW8aNGzeoWrUqERERdOnSpRijFkIUWkayfvTTjun6tYxAP/qpw3jwrFeoorO1Onadu8Gfh6JZdzSGhLQsw2OeThq6NPSmWyMfGvtWkM7CQpRBZk1uFi9eTFhYGLNmzSI4OJiIiAhCQ0M5efIkHh4eOY7PzMykY8eOeHh4sHTpUipVqsTFixepUKFC8QcvhCiY7EzYOw/+/gzS4vX7KjXVT/tfiJWntTqF3edvJzRHYriemml4zM1BQ5eGXnRr5EPTqi6S0AhRxpl1Er/g4GCaNWvG9OnTAdDpdPj6+jJixAjef//9HMfPmjWLKVOmcOLECaysCjZRl0ziJ4SZ6HRwbLl+1emb5/X7KvpDyHio+1SB5qnR6RT2Rt3kz4PRrDkSw7XkDMNjFe2t6dTAi24NvQmu7lo6lkkQQjxQqZjELzMzk7179zJ69GjDPrVaTUhICDt37sz1nFWrVtGiRQuGDRvGypUrcXd354UXXuC9997DwkKGbApRYp37GzaOv7vqtL0HtHtPv0BjPmcUVhSFA5cS+PPQVdYcvsrV25PtATjbWhFa35NujXxo4e+KlYUs/ihEeWS25CY+Ph6tVounp6fRfk9PT06cOJHrOefOnWPTpk3069ePNWvWcObMGd544w2ysrIYP358rudkZGSQkXH3v7mkpCTTPQkhxMPFHNEnNWc26u9bO0DLN/UT8OVjyn9FUThyJYk/D0Xz56GrXEm4ZXjMUWNJx/qedG/kQ6sablhbSkIjRHln9g7F+aHT6fDw8OD777/HwsKCoKAgrly5wpQpUx6Y3ISHhzNx4sRijlSIci4hCjZ9DIcWAwqoLaHpy9Dm3XxPwLf5ZBwTVx3lwvU0wz57awtC6ulraFrXdJPJ9oQQRsyW3Li5uWFhYUFsbKzR/tjYWLy8vHI9x9vbGysrK6MmqLp16xITE0NmZibW1tY5zhk9ejRhYWGG+0lJSfj6ynoqQhSJtBuw9QvY/T1ob3forf8MPDEGXP3zVZSiKHz3zzk+W3cCRQEbKzUd6nrSraE37et4SEIjhHggsyU31tbWBAUFERkZSY8ePQB9zUxkZCTDhw/P9ZxWrVqxYMECdDodarW+6vnUqVN4e3vnmtgAaDQaNBpNkTwHIcQ9EqJgTmdIuqy/79daPwKqUlC+i0rP0vLe74dYeSAagD7NfBnbrR72mlJV2SyEMBOzNk6HhYXxww8/8NNPP3H8+HGGDh1KamoqgwYNAqB///5GHY6HDh3KjRs3GDlyJKdOnWL16tV88sknDBs2zFxPQQgBkHINfu6hT2xcqkG/32HAHwVKbKITbvHsrB2sPBCNpVrF5KfrE/5MQ0lshBB5Zta/Fr179+batWuMGzeOmJgYAgMDWbdunaGTcVRUlKGGBsDX15f169fz9ttv06hRIypVqsTIkSN57733zPUUhBDpSTD/GbhxFpx9YeBqcK5UoKL+u3CD1+fvJT4lk4r21sx4oQkt/F1NHLAQoqwz6zw35iDz3AhhQlnpML8XXNwGdm7w8npwq1GgohbujmLcyiNkaRXqeDnyQ/+m+FY03UKZQojSrVTMcyOEKOW02bB0kD6xsXaEF38vUGKTpdUx+c9j/LzzIgBdGnox9bkA7Kzlz5MQomDkr4cQIv90Olg1Ak6u0a/e/cIi8AnMdzHXUzIYtmAfu87dAGDUk7UY1r6GLGIphCgUSW6EEPmjKLBhLBxcACoLeG5egdaEOhadxJCf/+NKwi3srS2I6NOYjvU8H32iEEI8giQ3Qoj82fYl7NSvB8fT06FOl3wXsebwVd757SC3srRUdbXjh/5NqeXpaOJAhRDllSQ3Qoi8+28uRE7Sbz/5MQS+kK/TdTqFrzaeYtqmMwC0runGtL6NqWCX+zxVQghREJLcCCHy5uhy+PNt/Xbrd6Bl7pNtPkhyehZvLz7IxuP6Wclfebwa73eug6UsbimEMDFJboQQj3Z2E/w+BFAgaBA8MTZfp1+IT2XIz/9xOi4Fa0s14T0b0iuoctHEKoQo9yS5EUI83OX/YNGLoMuCej2g6xeQj9FM/5y6xvAF+0hKz8bTScN3LzUl0LdCkYUrhBCS3AghHizuOPz6LGSlQvX28Mz3oM7bgpWKojB723k+WXMcnQKNq1TguxeD8HCyKeKghRDlnSQ3Qojc3bwIv/SEWzehUlPoPR8s87YIbXqWlg+WH2bZvisAPBtUmY96NJCVvIUQxUKSGyFETilx8EsPSL4K7nWg3xLQOOTp1JjEdF6bv5eDlxKwUKsY07UuA1v6ycR8QohiI8mNEMJYeqJ+vagb58C5Cry0HOwq5unUvRdvMHT+PuKSM3C2teLbfk1oVcOtiAMWQghjktwIIe7KugUL+0LMIbB3h/4rwMnnkafFJqUzZf1Jft93GUWBWp4O/NC/KVVd7Ys+ZiGEuI8kN0IIPW02LBkEF7eDxkm/EKar/0NPuZWp5Yet55j191nSMrUAPNO4EpN6NMBBI39ehBDmIX99hBC3F8IcDqfWgqUN9F0E3gEPOVxh5cErfL7uJFcT0wFoUqUCY7rVo0kVl+KKWgghciXJjRDlnaLAXx/CwYX3LITZ6oGH/3fhBpP/PMbBy4kAVKpgy/ud69Ctkbd0GhZClAiS3AhR3m39AnZ9q99+egbU7pzrYZdupPHp2hOsPnwVAHtrC95oX4PBj1eTId5CiBJFkhshyrM9s2HTZP12aDgE9s1xSFJ6FjM2n2HutgtkanWoVdC7mS9hHWvj7pi3eW+EEKI4SXIjRHl1ZBmsfke/3eZ/0OINo4eztToW7bnEVxtOcT01E4BWNVwZ07Uedb2dijtaIYTIM0luhChPbl6Ec5vh7GY4sRpQoOnL0P5Do8P+OXWNj1Yf41RsCgDV3e35sEtdnqjjIf1qhBAlniQ3QpRl6YlwfuvdhObGWePHGzwLXaYaFsI8E5fMR6uPs+XkNQAq2FnxVoea9HusKlYW6uKOXgghCkSSGyHKEm02XPlPn8ic26xf0VvR3n1cZQGVm4F/e/B/Qr+tUnEjNZOIjaf49d8otDoFS7WKAS39ePOJmjjbWZnv+QghRAFIciNEaaYo+mUSzm7SJzQXtkJGkvExrjX0K3r7twe/x8HG2fBQRraWn3dc5JtNp0lOzwagYz1PPuhSl2puMruwEKJ0kuRGiNIm7Qac23K7qWkLJEYZP27rAtXb3U1oKlTJUYSiKKw/Gkv42uNcvJ4GQD1vJ8Z0q0tLf1kLSghRuklyI0RJp82CqJ13m5qiDwDK3cfVVlDlMX0iU729fmZh9cPnnZm97TwfrT4OgLujhv89WZteQZWxUEtnYSFE6SfJjRAlWWYqzOsK0fuN93vUu1szU7UlWOe9Cen41SQ+X3cSgMGPVyOsYy3sZR0oIUQZIn/RhCipFAVWDtcnNhon/czB1dvrm5ycvAtUZHqWlrcWHSBTqyOkrgdjutaVod1CiDJHkhshSqqd0+HoMlBbwgu/QdUWhS5yyvqTnIxNxs3Bmk97NZLERghRJsnEFUKUROf+hg3j9Nuh4SZJbLadjmf2tvMAfP5sI9wcZOkEIUTZJMmNECVNwiVYOggUHQT0heZDCl9kWibvLDkAwIuPVeGJOp6FLlMIIUoqSW6EKEmy0uG3lyDtOng1gm5fGWYPLihFUfhg+WFikzJuL6NQz0TBCiFEyVQikpsZM2bg5+eHjY0NwcHB7N69+4HHzps3D5VKZXSzsbEpxmiFKCKKol/IMno/2FaE3vPByrbQxS7bd4U1h2OwVKuI6B2IrfXDh4kLIURpZ/bkZvHixYSFhTF+/Hj27dtHQEAAoaGhxMXFPfAcJycnrl69arhdvHixGCMWooj8NwcOzAeVGp6dDS5VC13kpRtpjF91FIC3QmrSqHKFQpcphBAlndmTmy+//JIhQ4YwaNAg6tWrx6xZs7Czs2POnDkPPEelUuHl5WW4eXpK/wFRyl3aDWvf0293GKdf96mQtDqFsN8OkJKRTdOqLgxtV6PQZQohRGlg1uQmMzOTvXv3EhISYtinVqsJCQlh586dDzwvJSWFqlWr4uvry9NPP83Ro0eLI1whikZyLPzWH3RZUO9paPWWSYqd9fdZ9ly4iYPGkq96B8rsw0KIcsOsyU18fDxarTZHzYunpycxMTG5nlO7dm3mzJnDypUrmT9/PjqdjpYtW3L58uVcj8/IyCApKcnoJkSJkZ0JSwZA8lVwrwNPzyh0B2KAw5cT+WrDKQAmPFUf34p2hS5TCCFKC7M3S+VXixYt6N+/P4GBgbRt25Zly5bh7u7Od999l+vx4eHhODs7G26+vr7FHLEQD/HXGP26URon6P0raBwLXeStTC0jF+8nW6fQpaEXvZpUMkGgQghRepg1uXFzc8PCwoLY2Fij/bGxsXh5eeWpDCsrKxo3bsyZM2dyfXz06NEkJiYabpcuXSp03EKYxMFFsPt2Ut7zO3AzTZ+YT9Yc59y1VDwcNXzco6HMQiyEKHfMmtxYW1sTFBREZGSkYZ9OpyMyMpIWLfI2I6tWq+Xw4cN4e+e+1o5Go8HJycnoJoTZRR+AP0bqt9u+B3W6mKTYzSfi+GWXfvTg1OcCcLG3Nkm5QghRmph9bamwsDAGDBhA06ZNad68OREREaSmpjJo0CAA+vfvT6VKlQgPDwdg0qRJPPbYY9SoUYOEhASmTJnCxYsXeeWVV8z5NITIu7QbsPglyE6Hmk9C2/dNUuz1lAz+t/QQAINa+dGmlrtJyhVCiNLG7MlN7969uXbtGuPGjSMmJobAwEDWrVtn6GQcFRWFWn23gunmzZsMGTKEmJgYXFxcCAoKYseOHdSrJ7OuilJAp4WlL0NiFLhUg2e+B3XhK1AVReH9ZYeJT8mglqcD73WqY4JghRCidFIpiqKYO4jilJSUhLOzM4mJidJEJYrfhvGwPQKs7OCVSPA0TVK+aHcU7y87jLWFmhXDWlHPRz7bQoiyJT/f36VutJQQpdaxlfrEBuDp6SZLbM7HpzLxj2MAjAqtJYmNEKLck+RGiOIQdwJWvKHfbjEcGvQySbFZWh1vLT7ArSwtj1WvyCuPVzdJuUIIUZpJciNEUUtPhEUvQGYKVGsDIRNNVvT0TWc4eCkBRxtLvng+ELXMQiyEEJLcCFGkdDpY/jrcOAtOleHZuWBhmn78+6JuMn2zfn6nj3o0oFKFwq8gLoQQZUG+kxs/Pz8mTZpEVFRUUcQjRNmydSqcXAMWGuj9C9i7maTY1Ixs3l58AK1O4elAH54OlFmIhRDijnwnN2+99RbLli2jevXqdOzYkUWLFpGRkVEUsQlRup36CzZ/ot/u9iVUamKyoif/eYyL19PwcbZh0tMNTFauEEKUBQVKbg4cOMDu3bupW7cuI0aMwNvbm+HDh7Nv376iiFGI0uf6WVj2CqBA08HQ+EWTFb3+aAyL9lxCpYIvng/E2dbKZGULIURZUOA+N02aNOGbb74hOjqa8ePH8+OPP9KsWTMCAwOZM2cO5Wz6HCHuykzVz0CcngiVm0OnT01WdFxSOu//rp+F+NXW1Wnh72qysoUQoqwocM/GrKwsli9fzty5c9mwYQOPPfYYgwcP5vLly3zwwQds3LiRBQsWmDJWIUo+RYFVIyDuKDh4wvM/g6Vp1ndSFIV3fz/EzbQs6no7EfZkLZOUK4QQZU2+k5t9+/Yxd+5cFi5ciFqtpn///nz11VfUqXN3uveePXvSrFkzkwYqRKmwcwYc+R3UlvDcT+CU+4KuBTF/10W2nLyGtaWar/sEorG0MFnZQghRluQ7uWnWrBkdO3Zk5syZ9OjRAyurnO391apVo0+fPiYJUIhS48I22DBOvx0aDlXztrJ9XpyJS+aj1ccBGN25DrU8HU1WthBClDX5Tm7OnTtH1apVH3qMvb09c+fOLXBQQpQ6qfHw+yugaKFRH2g+xGRFZ2brZyHOyNbRuqYbA1r4maxsIYQoi/LdoTguLo5///03x/5///2X//77zyRBCVGq6HSwYigkXwW32vph3yrTzRT8deQpjlxJooKdFVOfC5BZiIUQ4hHyndwMGzaMS5cu5dh/5coVhg0bZpKghChVds2A03+BpQ08Nxes7U1WdNT1NL77+xwA4T0b4ulkY7KyhRCirMp3cnPs2DGaNMk5GVnjxo05duyYSYISotS4vBc2TtBvdwoHz/omLT4i8hTZOoXWNd3o3NB0nZOFEKIsy3dyo9FoiI2NzbH/6tWrWFqaZs0cIUqFWwmwdBDosqFeDwgaZNLiz8Qls2L/FQBGPVnbpGULIURZlu/k5sknn2T06NEkJiYa9iUkJPDBBx/QsWNHkwYnRImlKPDHm5BwESpUhae+MWk/G4AvN5xCp8CT9TwJ8K1g0rKFEKIsy3dVy9SpU2nTpg1Vq1alcePGABw4cABPT09++eUXkwcoRIn03xw4tlI/n82zc8HG2aTFH7mSyJrDMahU8I7U2gghRL7kO7mpVKkShw4d4tdff+XgwYPY2toyaNAg+vbtm+ucN0KUOTFHYN1o/XbIBKgcZPJLTP3rJABPB/hQ20vmtBFCiPwoUCcZe3t7Xn31VVPHIkTJl5mq72ejzYCaofCY6UcI/nfhBltOXsNCreKtEFliQQgh8qvAPYCPHTtGVFQUmZmZRvufeuqpQgclRIm15n8QfwocfaDHTFAXeO3ZXCmKwufr9bU2zzetjJ+b6YaVCyFEeVGgGYp79uzJ4cOHUalUhtW/Vbc7U2q1WtNGKERJcXAxHPgVVGro9SPYm35F7q2n49l9/gbWlmpGPFHT5OULIUR5kO9/O0eOHEm1atWIi4vDzs6Oo0eP8s8//9C0aVO2bNlSBCEKUQLEn4E/39Zvt30f/FqZ/BKKohj62rwYXBWfCrYmv4YQQpQH+a652blzJ5s2bcLNzQ21Wo1arebxxx8nPDycN998k/379xdFnEKYT1Y6LBkIWang1xrajCqSy/x1LJZDlxOxs7bgjfb+RXINIYQoD/Jdc6PVanF01I/ecHNzIzo6GoCqVaty8uRJ00YnREnw1xiIPQx2bvDMD6C2MPkltDqFL27X2rzcqhpuDhqTX0MIIcqLfNfcNGjQgIMHD1KtWjWCg4P5/PPPsba25vvvv6d69epFEaMQ5nNsFez5Qb/d8ztwKpolEP44GM2p2BScbCwZ0kZ+j4QQojDyndyMGTOG1NRUACZNmkS3bt1o3bo1rq6uLF682OQBCmE2Ny/CquH67ZZvQs2QIrlMllbHVxtPAfBaW3+cbWW+KCGEKIx8JzehoaGG7Ro1anDixAlu3LiBi4uLYcSUEKWeNgt+HwzpiVC5GXQYV2SXWrr3Mhevp+HmYM3Aln5Fdh0hhCgv8tXnJisrC0tLS44cOWK0v2LFipLYiLJl00dweY9+WYVes8GiaGpT0rO0fBN5GoA32tXAXiOLzwohRGHlK7mxsrKiSpUqMpeNKNvObITtEfrtp6aDS9Uiu9Sv/0ZxNTEdb2cbXgiuUmTXEUKI8iTfo6U+/PBDPvjgA27cuFEU8QhhXklXYdlr+u1mr0C9optxOzUjm283nwHgzQ41sbEy/SgsIYQoj/Kd3EyfPp1//vkHHx8fateuTZMmTYxuBTFjxgz8/PywsbEhODiY3bt35+m8RYsWoVKp6NGjR4GuK4QRnRaWDYG0ePBsCE9+XKSXm7fjAtdTM/FztePZoMpFei0hhChP8t3Ab+pEYvHixYSFhTFr1iyCg4OJiIggNDSUkydP4uHh8cDzLly4wKhRo2jdurVJ4xHl2NYv4MJWsLKH5+aClU2RXSoxLYtZf58F4O2OtbCyMO0aVUIIUZ6plDuLQ5lJcHAwzZo1Y/r06QDodDp8fX0ZMWIE77//fq7naLVa2rRpw8svv8zWrVtJSEhgxYoVebpeUlISzs7OJCYm4uTkZKqnIUq7C9vhp26g6KDHLAjsW6SXm7L+BDM2n6W2pyNrR7ZGrZYO+UII8TD5+f4267+LmZmZ7N27l5CQu/OHqNVqQkJC2Llz5wPPmzRpEh4eHgwePPiR18jIyCApKcnoJoSR1Ovw+yv6xCagb5EnNteSM5i7/QIA7zxZSxIbIYQwsXw3S6nV6ocO+87PSKr4+Hi0Wi2enp5G+z09PTlx4kSu52zbto3Zs2dz4MCBPF0jPDyciRMn5jkmUc4oCqx8A5KjwbUmdJla5Jf8dssZ0jK1BPhWoGM9z0efIIQQIl/yndwsX77c6H5WVhb79+/np59+KvIkIjk5mZdeeokffvgBNze3PJ0zevRowsLCDPeTkpLw9fUtqhBFabPrWzi1Diw08Nw80DgU6eWiE27x664oAEY9WUvmhxJCiCKQ7+Tm6aefzrHv2WefpX79+ixevDhPTUV3uLm5YWFhQWxsrNH+2NhYvLy8chx/9uxZLly4QPfu3Q37dDodAJaWlpw8eRJ/f+PVlDUaDRqNLEIocnFlL2wYr9/u9Al4NSjyS07bdJpMrY7Hqlfk8Rp5S9CFEELkj8n63Dz22GNERkbm6xxra2uCgoKMztPpdERGRtKiRYscx9epU4fDhw9z4MABw+2pp56iffv2HDhwQGpkRN6lJ8KSQaDLgrpPQdO8J+UFdSE+ld/+uwzA/0JrS62NEEIUEZPM9X7r1i2++eYbKlWqlO9zw8LCGDBgAE2bNqV58+ZERESQmprKoEGDAOjfvz+VKlUiPDwcGxsbGjQw/u+6QoUKADn2C/FQa9+DhItQoQo8NQ2KIdH4auMptDqF9rXdCapascivJ4QQ5VW+k5v7F8hUFIXk5GTs7OyYP39+vgPo3bs3165dY9y4ccTExBAYGMi6desMnYyjoqJQq2UOEGFCyTFw6Df9dq/ZYFuhyC95MiaZVQejAXjnydpFfj0hhCjP8j3Pzbx584ySG7Vajbu7O8HBwbi4uJg8QFOTeW4E2yJg43jwDYbBfxXLJV/9+T/+OhZL14bezOhXsJm8hRCiPMvP93e+a24GDhxY0LiEMD9Fgf23axgbv1gslzxwKYG/jsWiVulnIxZCCFG08t3eM3fuXJYsWZJj/5IlS/jpp59MEpQQRebSbrh+GqzsoH7PYrnkF3+dBKBn48rU8CjaoeZCCCEKkNyEh4fnOseMh4cHn3zyiUmCEqLI7P9F/7N+T9A4Fvnldp27ztbT8VhZqHgrpGaRX08IIUQBkpuoqCiqVauWY3/VqlWJiooySVBCFInMVDh6exLKYmiSUhSFqev1tTZ9mlXBt6JdkV9TCCFEAZIbDw8PDh06lGP/wYMHcXV1NUlQQhSJYyshMwUqVocqOedRMrUtJ6/x38WbaCzVDH+iRpFfTwghhF6+k5u+ffvy5ptvsnnzZrRaLVqtlk2bNjFy5Ej69OlTFDEKYRp3OhIH9ivyeW10OoWpt/vaDGzph6eTTZFeTwghxF35Hi01efJkLly4QIcOHbC01J+u0+no37+/9LkRJdf1s3BxO6jU+pW/i9i6ozEcjU7CQWPJ6239H32CEEIIk8l3cmNtbc3ixYv56KOPOHDgALa2tjRs2JCqVasWRXxCmMaBX/U//TuAc/5n0s4PrU4xjJAa/Hg1XOyti/R6QgghjBV4+YWaNWtSs6aM/hClgE4LBxbot4uhI/Hy/Vc4ey2VCnZWvNI6Z+d7IYQQRSvffW569erFZ599lmP/559/znPPPWeSoIQwqbObIPkq2FaE2p2L9FKZ2ToiNp4CYGhbfxxtrIr0ekIIIXLKd3Lzzz//0KVLlxz7O3fuzD///GOSoIQwqTsdiRv1BktNkV5q8X+XuHzzFu6OGvq38CvSawkhhMhdvpOblJQUrK1z9iGwsrIiKSnJJEEJYTKp1+HEav12435FeqlbmVqmRZ4GYMQTNbC1tijS6wkhhMhdvpObhg0bsnjx4hz7Fy1aRL169UwSlBAmc3gJ6LLAOwC8GhbppX7Yeo645Awqu9jSp1mVIr2WEEKIB8t3h+KxY8fyzDPPcPbsWZ544gkAIiMjWbBgAUuXLjV5gEIUmKLcXW6h8UtFeqnz8alM33wGgPc61cHaMt//NwghhDCRfCc33bt3Z8WKFXzyyScsXboUW1tbAgIC2LRpExUrViyKGIUomKsHIfYIWGigQa8iu4yiKIxbeYTMbB2ta7rRrZF3kV1LCCHEoxVoKHjXrl3p2rUrAElJSSxcuJBRo0axd+9etFqtSQMUosDudCSu2w3sii7xXnUwmq2n47G2VPNRjwaoinj2YyGEEA9X4Lrzf/75hwEDBuDj48MXX3zBE088wa5du0wZmxAFl5Wu728DRTq3TeKtLCb/eRyAEe1rUNXVvsiuJYQQIm/yVXMTExPDvHnzmD17NklJSTz//PNkZGSwYsUK6UwsSpaTqyE9AZwqQ7W2RXaZKetPEJ+Sgb+7Pa+2rV5k1xFCCJF3ea656d69O7Vr1+bQoUNEREQQHR3NtGnTijI2IQrOsEjmC6AumiHZ+6Nu8uu/UQB81KMhGksZ+i2EECVBnmtu1q5dy5tvvsnQoUNl2QVRsiVcgrOb9duBLxTJJbK1Oj5cfgRFgV5NKtPC37VIriOEECL/8lxzs23bNpKTkwkKCiI4OJjp06cTHx9flLEJUTAHFwIK+LWGikWzttO8HRc4djWJCnZWfNClTpFcQwghRMHkObl57LHH+OGHH7h69SqvvfYaixYtwsfHB51Ox4YNG0hOTi7KOIXIG53ubpNUEc1tE51wiy836NePGt25Dq4ORbukgxBCiPzJ92gpe3t7Xn75ZbZt28bhw4d55513+PTTT/Hw8OCpp54qihiFyLuL2yHhImicoG73IrnExD+OkpappWlVF54L8i2SawghhCi4Qk2jWrt2bT7//HMuX77MwoULTRWTEAV3p9amwTNgbWfy4jcei2X90Vgs1So+7tkQtVrmtBFCiJLGJHPEW1hY0KNHD1atWmWK4oQomPREOLZSv10ETVJpmdmMX3UUgFdaV6e2l6PJryGEEKLwZAEcUXYcWQbZt8C9DlQKMnnxX0ee5krCLSpVsOXNDjVMXr4QQgjTkORGlB2GjsQvgomXQDgRk8TsrecBmNyjPnbWBVq5RAghRDGQ5EaUDXHH4cp/oLaERr1NWrROp/Dh8iNk6xQ61ffiiTqeJi1fCCGEaUlyI8qGO7U2tTqBg4dJi1783yX2XryJvbUF45+SZUaEEKKkk+RGlH7aLDi0WL8d2M+kRcenZPDp2hMAhD1ZG29nW5OWL4QQwvQkuRGl3+m/IPUa2HtAzY4mLfqT1cdJvJVFPW8nBrSoatKyhRBCFI0SkdzMmDEDPz8/bGxsCA4OZvfu3Q88dtmyZTRt2pQKFSpgb29PYGAgv/zySzFGK0qcO01SAX3Awspkxe44G8+y/VdQqeCTZxpiaVEifl2EEEI8gtn/Wi9evJiwsDDGjx/Pvn37CAgIIDQ0lLi4uFyPr1ixIh9++CE7d+7k0KFDDBo0iEGDBrF+/fpijlyUCMmxcOr2e9/4RZMVm5GtZczyIwC8GFyVQN8KJitbCCFE0TJ7cvPll18yZMgQBg0aRL169Zg1axZ2dnbMmTMn1+PbtWtHz549qVu3Lv7+/owcOZJGjRqxbdu2Yo5clAiHFoGihcrNwb22yYr97u9znItPxd1Rw/86ma5cIYQQRc+syU1mZiZ79+4lJCTEsE+tVhMSEsLOnTsfeb6iKERGRnLy5EnatGmT6zEZGRkkJSUZ3UQZoSjGc9uYyPn4VKZvPgPA2G71cLIxXVOXEEKIomfW5CY+Ph6tVounp/G8IZ6ensTExDzwvMTERBwcHLC2tqZr165MmzaNjh1z70gaHh6Os7Oz4ebrKwsdlhmX/4P4U2BpC/V7mqRIRVEYt/IImdk6Wtd0o3sjb5OUK4QQoviYvVmqIBwdHTlw4AB79uzh448/JiwsjC1btuR67OjRo0lMTDTcLl26VLzBiqKz/3ZH8vo9wMbJJEWuOhjN1tPxWFuqmfx0A1QmnulYCCFE0TPrHPJubm5YWFgQGxtrtD82NhYvL68HnqdWq6lRQ7+2T2BgIMePHyc8PJx27drlOFaj0aDRaEwatygBMlP1a0mByZqkEm9lMfnP4wCMaF8DPzd7k5QrhBCieJm15sba2pqgoCAiIyMN+3Q6HZGRkbRo0SLP5eh0OjIyMooiRFFSHVsFmcngUg2qtjJJkVPWnyA+JYPq7va82ra6ScoUQghR/My++l9YWBgDBgygadOmNG/enIiICFJTUxk0aBAA/fv3p1KlSoSHhwP6PjRNmzbF39+fjIwM1qxZwy+//MLMmTPN+TREcTN0JO5nkkUy90fd5Nd/owD4qEcDNJYWhS5TCCGEeZg9uenduzfXrl1j3LhxxMTEEBgYyLp16wydjKOiolCr71Ywpaam8sYbb3D58mVsbW2pU6cO8+fPp3dv0y6WKEqwG+fg4jZABQEvFLq4bK2OD5cfQVHgmSaVaOnvVvgYhRBCmI1KURTF3EEUp6SkJJydnUlMTMTJyTSdUEUx2/QR/DMF/DvAS8sKXdyPW8/x0erjONtaEflOW9wcpI+WEEKUNPn5/i6Vo6VEOabTwoEF+m0TdCSOTrjFlxtOATC6cx1JbIQQogyQ5EaULuc2Q9IVsHWBOl0LXdzEP46SlqmlaVUXnm8qcyAJIURZIMmNKF3udCRu+DxYFq6WZeOxWNYfjcVSreKjng1Qq2VOGyGEKAskuRGlR9oNOLFav13IJqm0zGzGrzoKwODW1ajjJf2vhBCirJDkRpQeh5eANhO8GoF3o0IV9XXkaa4k3KJSBVtGdqhpogCFEEKUBJLciNLDRItkno9PZc628wBMfKo+dtZmnxFBCCGECUlyI0qHqwch5hBYWEPD5wpV1CdrjpOlVWhX252Qep6PPkEIIUSpIsmNKB32/6r/Wacr2FUscDE7zsaz4VgsFmoVY7rWNVFwQgghShJJbkTJl5UOhxbrtwvRJKXVKYaFMfsFV6GGh6MpohNCCFHCSHIjSr6TayA9AZwqQfX2BS5myX+XOH41CUcbS94KqWW6+IQQQpQoktyIku9OR+LAF0BdsAUtUzKymfqXfibikR1qUtHe2lTRCSGEKGEkuRElW0IUnN2k3w4s+CKZ324+Q3xKBtXc7Onfws80sQkhhCiRJLkRJZdOB6veBBTwaw0VqxeomEs30vjx9tDv0Z3rYG0pH3shhCjL5K+8KLm2f6VfS8rSFrpMLXAxn647QWa2jhbVXekoQ7+FEKLMk+RGlExRu2DTx/rtrlPBo06Bivnvwg1WH7qKSgVju9VDpZL1o4QQoqyT5EaUPGk3YOlgULT6BTID+xWoGJ1OYfKfxwDo3dSXej6yfpQQQpQHktyIkkVRYOVwSLoMFf2h25dQwNqWlQevcPByIvbWFoQ9KUO/hRCivJDkRpQs/34HJ1frl1l4bi5oCjbRXlpmNp+tPQnAG+1r4OFoY8oohRBClGCS3IiSI/oAbBir337yI/AOKHBR3/9zjpikdCpVsGXw49VME58QQohSQZIbUTJkJMPSQaDNhDrdoPmrBS4qJjGd7/4+B8DoLnWwsSrYxH9CCCFKJ0luhPkpCvz5Ntw4B86+8NS0AvezAfh8/QluZWlpWtWFrg29TRioEEKI0kCSG2F+++fD4SWgsoBeswu16vehywks23cFkKHfQghRXklyI8wr7gSs+Z9++4kPoUpwgYtSFIVJf+iHfvdsXIkA3womCFAIIURpI8mNMJ+sW/p+Ntm39Kt9t3q7UMWtORzDfxdvYmOl5t1OtU0UpBBCiNJGkhthPuveh7hj4OAJz3wP6oJ/HNOztISvPQ7Aa2388Xa2NVWUQgghShlJboR5HPkd9s4DVPrExsGjUMXN3X6Byzdv4emk4bW2BVtgUwghRNkgyY0ofjfOwaqR+u3W70D1doUq7lpyBjM2nwHg3dA62FlbFjJAIYQQpZkkN6J4ZWfC0pchMxmqtIB2owtd5JcbTpKSkU2jys70bFzJBEEKIYQozSS5EcVr4wSI3g+2LtDrR7AoXC3L8atJLN5zCdAP/VarZei3EEKUd5LciOJzch3smqHffvpbcK5cqOIUReGj1cfQKdC1oTfN/Ao+P44QQoiyQ5IbUTwSr8CK1/XbwUOhTpdCF7nxeBzbz1zH2kLN+53rFLo8IYQQZUOJSG5mzJiBn58fNjY2BAcHs3v37gce+8MPP9C6dWtcXFxwcXEhJCTkoceLEkCbDb+/ArdugncgdJxY6CIzs3V8skY/9Pvlx6vhW9Gu0GUKIYQoG8ye3CxevJiwsDDGjx/Pvn37CAgIIDQ0lLi4uFyP37JlC3379mXz5s3s3LkTX19fnnzySa5cuVLMkYs8+/sziNoB1o7w3Fyw1BS6yF92XeR8fCpuDtYMa+9vgiCFEEKUFSpFURRzBhAcHEyzZs2YPn06ADqdDl9fX0aMGMH777//yPO1Wi0uLi5Mnz6d/v37P/L4pKQknJ2dSUxMxMnJqdDxi0c4twV+7gEo+nWjGj5b6CJvpmbSdspmktKzCX+mIX2bVyl0mUIIIUq2/Hx/m7XmJjMzk7179xISEmLYp1arCQkJYefOnXkqIy0tjaysLCpWzL0zaUZGBklJSUY3UUxS4mDZq4ACTfqbJLEBiNh4iqT0bOp4OfJ8U1+TlCmEEKLsMGtyEx8fj1arxdPT02i/p6cnMTExeSrjvffew8fHxyhBuld4eDjOzs6Gm6+vfBkWC50Olr8GKbHgXhc6fWaSYs/EJTP/3yhAP/TbQoZ+CyGEuI/Z+9wUxqeffsqiRYtYvnw5NjY2uR4zevRoEhMTDbdLly4Vc5Tl1I6v4ewmsLTV97OxNk2H349XH0erUwip60GrGm4mKVMIIUTZYtZ56t3c3LCwsCA2NtZof2xsLF5eXg89d+rUqXz66ads3LiRRo0aPfA4jUaDRlP4DqwiHy7thsjJ+u3On4FHXZMU+/epa2w+eQ1LtYoPupimTCGEEGWPWWturK2tCQoKIjIy0rBPp9MRGRlJixYtHnje559/zuTJk1m3bh1NmzYtjlBFXt26qV9eQdFCg176vjYmkK3V8dGfxwDo38KP6u4OJilXCCFE2WP2FQbDwsIYMGAATZs2pXnz5kRERJCamsqgQYMA6N+/P5UqVSI8PByAzz77jHHjxrFgwQL8/PwMfXMcHBxwcJAvPLNSFFg5HBIvgUs16BYBKtP0iVm45xKn41KoYGfFyA41TVKmEEKIssnsyU3v3r25du0a48aNIyYmhsDAQNatW2foZBwVFYVafbeCaebMmWRmZvLss8Yjb8aPH8+ECROKM3Rxvz0/wok/QW2l72djY5qh9om3svhqwykA3upQE2c7K5OUK4QQomwy+zw3xU3muSkiGSnwVX1IT4DQcGjxhsmK/mTNcb7/5xz+7vase6sNVhaluh+8EEKIAig189yIMmTfz/rEpqI/BL9msmIvxKcyd/t5AMZ0rSeJjRBCiEeSbwpReNos2Hl7te+WI0BtYZJiFUXhwxWHydIqtKnlTrva7iYpVwghRNkmyY0ovCPLIOky2LtDQF+TFbt072W2n7mOxlLNpKfqozJR52QhhBBlmyQ3onAUBbZ/rd8Ofh2scp9MMb/iUzL4+Paq32+F1MLPzd4k5QohhCj7JLkRhXMmEuKOgrUDNBtssmIn/XGMhLQs6no78UrraiYrVwghRNknyY0onO0R+p9BA8HWxSRFbj4Zx6qD0ahV8FmvhtKJWAghRL7It4YouMt74cJWUFvCY0NNUmRqRjZjlh8BYFCrajSqXMEk5QohhCg/JLkRBbfjdl+bhs+Bc2WTFPnFX6e4knCLShVsCetYyyRlCiGEKF8kuREFc/0sHFul3275pkmKPHgpgXk79HPafNyzAfYas0+gLYQQohSS5EYUzM7pgAI1Q8GzXqGLy9LqeO/3Q+gU6BHoQ7vaHoWPUQghRLkkyY3Iv5Q42P+rfrvVSJMU+cPWc5yIScbFzoqx3QqfLAkhhCi/JLkR+ffvd6DNgEpNoWrLQhd3IT6VrzeeBvRLLLg6aApdphBCiPJLkhuRPxkpsOcH/XarkVDIWYMVReGD5YfJyNbRuqYbzzSpZIIghRBClGeS3Ij82fczpCeCaw2o07XQxS3Ze5kdZ69jY6Xm4x4NZYkFIYQQhSbJjcg7Ey+QeS05g49X65dYeDukFlVc7QoboRBCCCHJjciHI7/fXiDTAxr1KXRxk/48RuKtLOr7ODH4cVliQQghhGlIciPy5t4FMh8r/AKZm0/E8cftJRY+faYRlrLEghBCCBORbxSRN2c2Qtwx/QKZTQu3QGZqRjZjVuiXWBj8eDUaVnY2RYRCCCEEIMmNyKs7tTZBA8G2QqGKmvrXSa4k3KKyiy1vyxILQgghTEySG/FoRgtkvlGoog5cSmDejgsAfNKzIXbWssSCEEII05LkRjza9gj9z4bPg3PB56HJ0up4//dDKAr0bFyJNrXcTROfEEIIcQ9JbsTDXT8Lx//Qb7cq3AKZ3/9zd4mFMV3rmiA4IYQQIidJbsTD7ZgGKFCrE3gUPCE5H5/K15H6JRbGdpMlFoQQQhQdSW7Eg6XEwYEF+u1CLJCpKAofLDtM5u0lFno2liUWhBBCFB1JbsSD/TtLv0Bm5WZQpUWBi1ny32V2npMlFoQQQhQPSW5E7jKSYc+P+u1CLJB5LTmDj9fol1gI6yhLLAghhCh6ktyI3N27QGbtgi+QOfGPoyTeyqJBJSdebiVLLAghhCh6ktyInIwWyHwT1AX7mGw6Ecufh65ioVbJEgtCCCGKjXzbiJyO/A5JV8DBExr1LlARKRnZjFl+d4mFBpVkiQUhhBDFQ5IbYezeBTKDC75A5tT1J4lOTMe3oi1vh8gSC0IIIYqPJDfC2OkNtxfIdISmLxeoiP1RN/lp5wVAv8SCrbWFCQMUQgghHs7syc2MGTPw8/PDxsaG4OBgdu/e/cBjjx49Sq9evfDz80OlUhEREVF8gZYXd2ptmg4s0AKZWVodo5cdRlHgmcaVaF1TllgQQghRvMya3CxevJiwsDDGjx/Pvn37CAgIIDQ0lLi4uFyPT0tLo3r16nz66ad4eXkVc7TlwOX/4OI2UFtB8NACFXFniYWK9taM6VbPxAEKIYQQj2bW5ObLL79kyJAhDBo0iHr16jFr1izs7OyYM2dOrsc3a9aMKVOm0KdPHzQamb7f5O7U2jQq2AKZ566l3LPEQl0q2lubMjohhBAiT8yW3GRmZrJ3715CQkLuBqNWExISws6dO012nYyMDJKSkoxuIhfxZ+4ukNky/wtk6nQK799eYqFNLXd6BMoSC0IIIczDbMlNfHw8Wq0WT09Po/2enp7ExMSY7Drh4eE4Ozsbbr6+viYru0zZeWeBzM7gUSffp/+88wK7z9/AztqCj3s0kCUWhBBCmI3ZOxQXtdGjR5OYmGi4Xbp0ydwhlTzJsXBgoX67AAtkXohP5dN1JwAY3aUuvhVliQUhhBDmY2muC7u5uWFhYUFsbKzR/tjYWJN2FtZoNNI/51F2f3d7gczmUOWxfJ2q0yn8b+lB0rN0tPR3pV/zKkUUpBBCCJE3Zqu5sba2JigoiMjISMM+nU5HZGQkLVoUfAVqkU/3LpD5+Fv5XiBz7o4L7LlwE3trCz7r1Qi1WpqjhBBCmJfZam4AwsLCGDBgAE2bNqV58+ZERESQmprKoEGDAOjfvz+VKlUiPDwc0HdCPnbsmGH7ypUrHDhwAAcHB2rUqGG251Gq7f3p9gKZNfX9bfLh3LUUPr/dHPVh13rSHCWEEKJEMGty07t3b65du8a4ceOIiYkhMDCQdevWGToZR0VFob5n0cbo6GgaN25suD916lSmTp1K27Zt2bJlS3GHX/plZ8Kub/XbrfK3QKZWp/C/pYfIyNbRuqYbfZtLR20hhBAlg0pRFMXcQRSnpKQknJ2dSUxMxMnJydzhmNeBhbDidf0CmW8dBsu890364Z9zfLzmOA4aS9a/3YZKFWyLMFAhhBDlXX6+v8v8aCnxAPcukPnY0HwlNmfiUpjy10lAP1mfJDZCCCFKEkluyqvTG+Da8XwvkKnVKYxacpDMbB1ta7nzfFNpjhJCCFGySHJTXm2P0P9sOghsnPN82g9bz3HgUgKONpZ82quhTNYnhBCixJHkpjw6tR4ubtcvkPlY3hfIPB2bzJd/nQJgbLd6eDtLc5QQQoiSR5Kb8ubGOVg2RL/dfAg4+eTptGytTt8cpdXRvrY7zwVVLsIghRBCiIKT5KY8yUyFRS/q57Wp3BxCJub51O/+OcfBy4k42VgS/kwjaY4SQghRYklyU14oCqwaAXFHwd4Dnv8ZLK3zdOrJmGS+3ngagPHd6+PlbFOUkQohhBCFIslNebHrWzjyO6gt9YmNk3eeTsu6pzkqpK4HzzSpVMSBCiGEEIUjyU15cP4f+Gusfjs0HKrmfe2uWVvOcvhKIs62VnzSU0ZHCSGEKPkkuSnrEi/DkkGgaCGgr74TcR4dv5rEN5v0zVETn6qPh5M0RwkhhCj5JLkpy7LSYfFLkBYPXo2g21d5XvU7S6vjnd8OkqVVeLKeJ08H5m1UlRBCCGFuktyUVYoCa0ZB9D6wrQi954NV3uelmbH5DMeuJuFiZ8XH0hwlhBCiFJHkpqzaOxf2/wIqNTw7G1yq5vnUo9GJTN90BoCJTzfA3THv604JIYQQ5ibJTVl0aQ+seVe/3WEc+D+R51Mzs/XNUdk6hc4NvOjeKG+jqoQQQoiSQpKbsiY5Fn57CXRZUPcpaPVWvk6fvuk0J2KSqWhvzeQeDaQ5SgghRKkjyU1Zos2CJQMh+Sq414Ee3+a5AzHAkSuJzNhyFoDJTzfAzUGao4QQQpQ+ktyUJX+NgagdoHGC3r+CxjHPp2Zka3nnt4NodQpdG3nTVZqjhBBClFKS3JQVBxfDv7P02z2/A7ca+Tp9WuQZTsYm4+ZgzeSnGxRBgEIIIUTxkOSmLLh6EP54U7/d5l2o0yVfpx+8lMDMv/XNUR/1aEBF+7ytOSWEEEKURJLclHZpN2Dxi5CdDjWfhHaj83V6epaWUUv0zVFPBfjQqYE0RwkhhCjdJLkpzXRa+H0wJESBSzV45ntQ5+8t/TryNKfjUnBz0DDxqfpFFKgQQghRfCS5Kc02TYazm8DKDvr8CrYu+Tp9f9RNvrvdHPVJzwa4SHOUEEKIMkCSm9Lq2ErY9pV++6lp4Jm/Wpc7zVE6BXo2rsST9b2KIEghhBCi+ElyUxrFnYAVb+i3WwyHhs/m63RFUfhywynOXkvF3VHD+O71iiBIIYQQwjwszR2AyKf0RFjcDzJTwK81hEx84KHZWh0Xb6RxNi6FM9dSOBuXyplrKZyLSyE5IxuA8J4NqWAnzVFCCCHKDkluShOdDpYPhetnwKkyPDcPLCxJzcjm7LUUzl5L4Uzc3STm4vVUsrRKrkVZqFW83rY6IfU8i/c5CCGEEEVMkptSQlEUUjd+isPJ1WjV1sz2nsA/C89y9tpBriamP/A8WysL/D3sqeHugL+7AzU8HPD3cKCqqx0aS4tifAZCCCFE8ZDkpoRIzcgmNimd2KQM4pLTDduxSelcvnkL72tbmaF8Dip4P2MgSw7aAfGG890cNPi72+uTl3uSGG8nG9RqWfxSCCFE+SHJTRFLz9ISl5RB7D0JS1zSPclLcjpxSRmk3O4Dk5sqqlh+sv4atUphlWUoN/ye57XbSYy/hwM13B1wtrMqxmclhBBClFyS3JjIxeupLN5zKUfNS+KtrDyX4aCxxMNJg6ejDZ5OGjydbPCxV+i5dwJOSWnoKjXlqUG/8JSlrNYthBBCPIgkNyYSn5LBt1vO5vqYjZUaTycbPB1t8HDS4OVoRVXbW1S2SsFTnYSbKgFnXQKa9HhIuQapcXDzGlyOg9R4ULRg74G69y8giY0QQgjxUCUiuZkxYwZTpkwhJiaGgIAApk2bRvPmzR94/JIlSxg7diwXLlygZs2afPbZZ3Tpkr/FIk2tSgUNI5ra46tJwccyGQ91EhWVBBy1N7FOv44qNU6fuFyJg7TroOjyXridGzz/Mzj5FN0TEEIIIcoIsyc3ixcvJiwsjFmzZhEcHExERAShoaGcPHkSDw+PHMfv2LGDvn37Eh4eTrdu3ViwYAE9evRg3759NGjQwAzPQM89fjfvHOmRjzNUYOcKDh5g7377pwc4uN/+ee9+d7CQPjVCCCFEXqgURcl9IpRiEhwcTLNmzZg+fToAOp0OX19fRowYwfvvv5/j+N69e5Oamsqff/5p2PfYY48RGBjIrFmzHnm9pKQknJ2dSUxMxMnJyXRPJPYozHpcX8tyf2KSW+Ji5wYWZs8thRBCiFIhP9/fZv12zczMZO/evYwePdqwT61WExISws6dO3M9Z+fOnYSFhRntCw0NZcWKFbken5GRQUZGhuF+UlJS4QPPjXtdGBsPapk7RgghhDAns64tFR8fj1arxdPTeJZcT09PYmJicj0nJiYmX8eHh4fj7OxsuPn6+pom+Pup1ZLYCCGEECVAmV84c/To0SQmJhpuly5dMndIQgghhChCZm2WcnNzw8LCgtjYWKP9sbGxeHl55XqOl5dXvo7XaDRoNDJ8WgghhCgvzFpzY21tTVBQEJGRkYZ9Op2OyMhIWrRokes5LVq0MDoeYMOGDQ88XgghhBDli9mH64SFhTFgwACaNm1K8+bNiYiIIDU1lUGDBgHQv39/KlWqRHh4OAAjR46kbdu2fPHFF3Tt2pVFixbx33//8f3335vzaQghhBCihDB7ctO7d2+uXbvGuHHjiImJITAwkHXr1hk6DUdFRaFW361gatmyJQsWLGDMmDF88MEH1KxZkxUrVph1jhshhBBClBxmn+emuBXZPDdCCCGEKDL5+f4u86OlhBBCCFG+SHIjhBBCiDJFkhshhBBClCmS3AghhBCiTJHkRgghhBBliiQ3QgghhChTJLkRQgghRJli9kn8itudaX2SkpLMHIkQQggh8urO93Zepucrd8lNcnIyAL6+vmaORAghhBD5lZycjLOz80OPKXczFOt0OqKjo3F0dESlUpm07KSkJHx9fbl06ZLMflzCyXtVusj7VXrIe1V6lLb3SlEUkpOT8fHxMVqWKTflruZGrVZTuXLlIr2Gk5NTqfigCHmvSht5v0oPea9Kj9L0Xj2qxuYO6VAshBBCiDJFkhshhBBClCmS3JiQRqNh/PjxaDQac4ciHkHeq9JF3q/SQ96r0qMsv1flrkOxEEIIIco2qbkRQgghRJkiyY0QQgghyhRJboQQQghRpkhyI4QQQogyRZIbE5kxYwZ+fn7Y2NgQHBzM7t27zR2SyMWECRNQqVRGtzp16pg7LAH8888/dO/eHR8fH1QqFStWrDB6XFEUxo0bh7e3N7a2toSEhHD69GnzBCse+X4NHDgwx+9ap06dzBNsORceHk6zZs1wdHTEw8ODHj16cPLkSaNj0tPTGTZsGK6urjg4ONCrVy9iY2PNFHHhSXJjAosXLyYsLIzx48ezb98+AgICCA0NJS4uztyhiVzUr1+fq1evGm7btm0zd0gCSE1NJSAggBkzZuT6+Oeff84333zDrFmz+Pfff7G3tyc0NJT09PRijlTAo98vgE6dOhn9ri1cuLAYIxR3/P333wwbNoxdu3axYcMGsrKyePLJJ0lNTTUc8/bbb/PHH3+wZMkS/v77b6Kjo3nmmWfMGHUhKaLQmjdvrgwbNsxwX6vVKj4+Pkp4eLgZoxK5GT9+vBIQEGDuMMQjAMry5csN93U6neLl5aVMmTLFsC8hIUHRaDTKwoULzRChuNf975eiKMqAAQOUp59+2izxiIeLi4tTAOXvv/9WFEX/u2RlZaUsWbLEcMzx48cVQNm5c6e5wiwUqbkppMzMTPbu3UtISIhhn1qtJiQkhJ07d5oxMvEgp0+fxsfHh+rVq9OvXz+ioqLMHZJ4hPPnzxMTE2P0e+bs7ExwcLD8npVgW7ZswcPDg9q1azN06FCuX79u7pAEkJiYCEDFihUB2Lt3L1lZWUa/X3Xq1KFKlSql9vdLkptCio+PR6vV4unpabTf09OTmJgYM0UlHiQ4OJh58+axbt06Zs6cyfnz52ndujXJycnmDk08xJ3fJfk9Kz06derEzz//TGRkJJ999hl///03nTt3RqvVmju0ck2n0/HWW2/RqlUrGjRoAOh/v6ytralQoYLRsaX596vcrQouyrfOnTsbths1akRwcDBVq1blt99+Y/DgwWaMTIiypU+fPobthg0b0qhRI/z9/dmyZQsdOnQwY2Tl27Bhwzhy5EiZ72soNTeF5ObmhoWFRY5e5bGxsXh5eZkpKpFXFSpUoFatWpw5c8bcoYiHuPO7JL9npVf16tVxc3OT3zUzGj58OH/++SebN2+mcuXKhv1eXl5kZmaSkJBgdHxp/v2S5KaQrK2tCQoKIjIy0rBPp9MRGRlJixYtzBiZyIuUlBTOnj2Lt7e3uUMRD1GtWjW8vLyMfs+SkpL4999/5feslLh8+TLXr1+X3zUzUBSF4cOHs3z5cjZt2kS1atWMHg8KCsLKysro9+vkyZNERUWV2t8vaZYygbCwMAYMGEDTpk1p3rw5ERERpKamMmjQIHOHJu4zatQounfvTtWqVYmOjmb8+PFYWFjQt29fc4dW7qWkpBj9V3/+/HkOHDhAxYoVqVKlCm+99RYfffQRNWvWpFq1aowdOxYfHx969OhhvqDLsYe9XxUrVmTixIn06tULLy8vzp49y7vvvkuNGjUIDQ01Y9Tl07Bhw1iwYAErV67E0dHR0I/G2dkZW1tbnJ2dGTx4MGFhYVSsWBEnJydGjBhBixYteOyxx8wcfQGZe7hWWTFt2jSlSpUqirW1tdK8eXNl165d5g5J5KJ3796Kt7e3Ym1trVSqVEnp3bu3cubMGXOHJRRF2bx5swLkuA0YMEBRFP1w8LFjxyqenp6KRqNROnTooJw8edK8QZdjD3u/0tLSlCeffFJxd3dXrKyslKpVqypDhgxRYmJizB12uZTb+wQoc+fONRxz69Yt5Y033lBcXFwUOzs7pWfPnsrVq1fNF3QhqRRFUYo/pRJCCCGEKBrS50YIIYQQZYokN0IIIYQoUyS5EUIIIUSZIsmNEEIIIcoUSW6EEEIIUaZIciOEEEKIMkWSGyGEEEKUKZLcCCHKJZVKxYoVK8wdhhCiCEhyI4QodgMHDkSlUuW4derUydyhCSHKAFlbSghhFp06dWLu3LlG+zQajZmiEUKUJVJzI4QwC41Gg5eXl9HNxcUF0DcZzZw5k86dO2Nra0v16tVZunSp0fmHDx/miSeewNbWFldXV1599VVSUlKMjpkzZw7169dHo9Hg7e3N8OHDjR6Pj4+nZ8+e2NnZUbNmTVatWmV47ObNm/Tr1w93d3dsbW2pWbNmjmRMCFEySXIjhCiRxo4dS69evTh48CD9+vWjT58+HD9+HIDU1FRCQ0NxcXFhz549LFmyhI0bNxolLzNnzmTYsGG8+uqrHD58mFWrVlGjRg2ja0ycOJHnn3+eQ4cO0aVLF/r168eNGzcM1z927Bhr167l+PHjzJw5Ezc3t+J7AYQQBWfulTuFEOXPgAEDFAsLC8Xe3t7o9vHHHyuKol/F+PXXXzc6Jzg4WBk6dKiiKIry/fffKy4uLkpKSorh8dWrVytqtdqw8rSPj4/y4YcfPjAGQBkzZozhfkpKigIoa9euVRRFUbp3764MGjTINE9YCFGspM+NEMIs2rdvz8yZM432VaxY0bDdokULo8datGjBgQMHADh+/DgBAQHY29sbHm/VqhU6nY6TJ0+iUqmIjo6mQ4cOD42hUaNGhm17e3ucnJyIi4sDYOjQofTq1Yt9+/bx5JNP0qNHD1q2bFmg5yqEKF6S3AghzMLe3j5HM5Gp2Nra5uk4Kysro/sqlQqdTgdA586duXjxImvWrGHDhg106NCBYcOGMXXqVJPHK4QwLelzI4QokXbt2pXjft26dQGoW7cuBw8eJDU11fD49u3bUavV1K5dG0dHR/z8/IiMjCxUDO7u7gwYMID58+cTERHB999/X6jyhBDFQ2puhBBmkfH/9u1QVWEwjMP4fzAEl4eyKxA06ppegE3QJrIqwrCsWHRXoFdgFAcGi0EvwOIVGI2C0eLSTjggxyacI3o+nl/8wnjXHva9S1Odz+eHM9u270u7q9VKtVpN9Xpdi8VCh8NB8/lcktTtdjWZTBQEgeI41uVyURiG6vV6KhaLkqQ4jtXv91UoFNRsNnW9XrXf7xWG4VPzjcdjVatVVSoVpWmqzWZzjysAn424AfAW2+1Wnuc9nJVKJR2PR0nffzIlSaLBYCDP87RcLlUulyVJjuNot9tpOBzK9305jqN2u63pdHp/VhAEut1ums1miqJIruuq0+k8PV8ul9NoNNLpdFI+n1ej0VCSJH/w5gBezcqyLHv3EADwk2VZWq/XarVa7x4FwD/Ezg0AADAKcQMAAIzCzg2Aj8NtOYDf4MsNAAAwCnEDAACMQtwAAACjEDcAAMAoxA0AADAKcQMAAIxC3AAAAKMQNwAAwCjEDQAAMMoX8IC526Vu5/4AAAAASUVORK5CYII=">
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[94]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="c1"># Plot test accuracy</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">history</span><span class="o">.</span><span class="n">history</span><span class="p">[</span><span class="s1">'accuracy'</span><span class="p">],</span> <span class="n">label</span><span class="o">=</span><span class="s1">'Train Accuracy'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">history</span><span class="o">.</span><span class="n">history</span><span class="p">[</span><span class="s1">'val_accuracy'</span><span class="p">]),</span> <span class="n">test_acc</span><span class="p">,</span> <span class="s1">'ro'</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">'Test Accuracy'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">'Epochs'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">'Accuracy'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">'Test Accuracy'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">legend</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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">
</div>

</div>

</div>
</div>

</div>
    </div>
  </div>


 



</body></html>
