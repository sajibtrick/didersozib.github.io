@charset "UTF-8";
/*
Theme Name: Twenty Nineteen
Theme URI: https://github.com/WordPress/twentynineteen
Author: the WordPress team
Author URI: https://wordpress.org/
Description: Our 2019 default theme is designed to show off the power of the block editor. It features custom styles for all the default blocks, and is built so that what you see in the editor looks like what you'll see on your website. Twenty Nineteen is designed to be adaptable to a wide range of websites, whether you’re running a photo blog, launching a new business, or supporting a non-profit. Featuring ample whitespace and modern sans-serif headlines paired with classic serif body text, it's built to be beautiful on all screen sizes.
Requires at least: WordPress 4.9.6
Version: 1.2
License: GNU General Public License v2 or later
License URI: LICENSE
Text Domain: twentynineteen
Tags: one-column, flexible-header, accessibility-ready, custom-colors, custom-menu, custom-logo, editor-style, featured-images, footer-widgets, rtl-language-support, sticky-post, threaded-comments, translation-ready

This theme, like WordPress, is licensed under the GPL.
Use it to make something cool, have fun, and share what you've learned with others.

Twenty Nineteen is based on Underscores https://underscores.me/, (C) 2012-2018 Automattic, Inc.
Underscores is distributed under the terms of the GNU GPL v2 or later.

Normalizing styles have been helped along thanks to the fine work of
Nicolas Gallagher and Jonathan Neal https://necolas.github.io/normalize.css/
*/
/*--------------------------------------------------------------
>>> TABLE OF CONTENTS:
----------------------------------------------------------------
# Variables
# Normalize
# Typography
	## Headings
	## Copy
# Elements
	## Lists
	## Tables
# Forms
	## Buttons
	## Fields
# Navigation
	## Links
	## Menus
	## Next & Previous
# Accessibility
# Alignments
# Clearings
# Layout
# Widgets
# Content
	## Archives
	## Posts and pages
	## Comments
# Blocks
# Media
	## Captions
	## Galleries
--------------------------------------------------------------*/
/*
 * Chrome renders extra-wide &nbsp; characters for the Hoefler Text font.
 * This results in a jumping cursor when typing in both the Classic and block
 * editors. The following font-face override fixes the issue by manually inserting
 * a custom font that includes just a Hoefler Text space replacement for that
 * character instead.
 */
@font-face {
  font-family: 'NonBreakingSpaceOverride';
  src: url(data:application/font-woff2;charset=utf-8;base64,d09GMgABAAAAAAMoAA0AAAAACDQAAALTAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAP0ZGVE0cGh4GYACCahEICjx3CywAATYCJANUBCAFhiEHgWwbXQfILgpsY+rQRRARwyAs6uL7pxzYhxEE+32b3aeHmifR6tklkS9hiZA0ewkqGRJE+H7/+6378ASViK/PGeavqJyOzsceKi1s3BCiQsiOdn1r/RBgIJYEgCUhbm/8/8/h4saPssnTNkkiWUBrTRtjmQSajw3Ui3pZ3LYDPD+XG2C3JA/yKAS8/rU5eNfuGqRf4eNNgV4YAlIIgxglEkWe6FYpq10+wi3g+/nUgvgPFczNrz/RsTgVm/zfbPuHZlsuQECxuyqBcQwKFBjFgKO8AqP4bAN9tFJtnM9xPcbNjeXS/x1wY/xU52f5W/X1+9cnH4YwKIaoRRAkUkj/YlAAeF/624foiIDBgBmgQBeGAyhBljUPZUm/l2dTvmpqcBDUOHdbPZWd8JsBAsGr4w8/EDn82/bUPx4eh0YNrQTBuHO2FjQEAGBwK0DeI37DpQVqdERS4gZBhpeUhWCfLFz7J99aEBgsJCHvUGAdAPp4IADDCAPCEFMGpMZ9AQpTfQtQGhLbGVBZFV8BaqNyP68oTZgHNj3M8kBPfXTTC9t90UuzYhy9ciH0grVlOcqyCytisvbsERsEYztiznR0WCrmTksJwbSNK6fd1Rvr25I9oLvctUoEbNOmXJbqgYgPXEHJ82IUsrCnpkxh23F1rfZ2zcRnJYoXtauB3VTFkFXQg3uoZYD5qE0kdjDtoDoF1h2bulGmev5HbYhbrjtohQSRI4aNOkffIcT+d3v6atpaYh3JvPoQsztCcqvaBkppDSPcQ3bw3KaCBo1f5CJWTZEgW3LjLofYg51MaVezrx8xZitYbQ9KYeoRaqQdVLwSEfrKXLK1otCWOKNdR/YwYAfon5Yk8O2MJfSD10dPGA5PIJJQMkah0ugMJiv6x4Dm7LEa8xnrRGGGLAg4sAlbsA07sAt76DOsXKO3hIjtIlpnnFrt1qW4kh6NhS83P/6HB/fl1SMAAA==) format("woff2"), url(data:application/font-woff;charset=utf-8;base64,d09GRgABAAAAAAUQAA0AAAAACDQAAQAAAAAAAAAAAAAAAAAAAAAAAAAAAABGRlRNAAAE9AAAABwAAAAchf5yU0dERUYAAATYAAAAHAAAAB4AJwAbT1MvMgAAAaAAAABJAAAAYJAcgU5jbWFwAAACIAAAAF4AAAFqUUxBZ2dhc3AAAATQAAAACAAAAAgAAAAQZ2x5ZgAAApAAAAAyAAAAPL0n8y9oZWFkAAABMAAAADAAAAA2Fi93Z2hoZWEAAAFgAAAAHQAAACQOSgWaaG10eAAAAewAAAAzAAAAVC7TAQBsb2NhAAACgAAAABAAAAAsAOQBAm1heHAAAAGAAAAAHQAAACAAWQALbmFtZQAAAsQAAAF6AAADIYvD/Adwb3N0AAAEQAAAAI4AAADsapk2o3jaY2BkYGAA4ov5mwzj+W2+MnCzXwCKMNzgCBSB0LfbQDQ7AxuI4mBgAlEAFKQIRHjaY2BkYGD3+NvCwMDBAALsDAyMDKhAFAA3+wH3AAAAeNpjYGRgYBBl4GBgYgABEMnIABJzAPMZAAVmAGUAAAB42mNgZlJhnMDAysDCKsKygYGBYRqEZtrDYMT4D8gHSmEHjgUFOQwODAqqf9g9/rYwMLB7MNUAhRlBcsxBrMlASoGBEQAj8QtyAAAAeNrjYGBkAAGmWQwMjO8gmBnIZ2NA0ExAzNjAAFYJVn0ASBsD6VAIDZb7AtELAgANIgb9AHjaY2BgYGaAYBkGRgYQSAHyGMF8FgYPIM3HwMHAxMDGoMCwQIFLQV8hXvXP//9AcRCfAcb///h/ygPW+w/vb7olBjUHCTCyMcAFGZmABBO6AogThgZgIUsXAEDcEzcAAHjaY2BgECMCyoEgACZaAed42mNgYmRgYGBnYGNgYAZSDJqMgorCgoqCjECRXwwNrCAKSP5mAAFGBiRgyAAAi/YFBQAAeNqtkc1OwkAUhU/5M25cEhcsZick0AwlBJq6MWwgJkAgYV/KAA2lJeUn+hY+gktXvpKv4dLTMqKycGHsTZNv7px7z50ZAFd4hYHjdw1Ls4EiHjVncIFnzVnc4F1zDkWjrzmPW+NNcwGlzIRKI3fJlUyrEjZQxb3mDH2fNGfRx4vmHKqG0JzHg6E0F9DOlFBGBxUI1GEzLNT4S0aLuTtsGAEUuYcQHkyg3KmIum1bNUvKlrjbbAIleqHHnS4iSudpQcySMYtdFiXlAxzSbAwfMxK6kZoHKhbjjespMTioOPZnzI+4ucCeTVyKMVKLfeAS6vSWaTinuZwzyy/Dc7vaed+6KaV0kukdPUk6yOcctZPvvxxqksq2lEW8RvHjMEO2FCl/zy6p3NEm0R9OFSafJdldc4QVeyaaObMBO0/5cCaa6d9Ggyubxire+lEojscdjoWUR1xGOy8KD8mG2ZLO2l2paDc3A39qmU2z2W5YNv5+u79e6QfGJY/hAAB42m3NywrCMBQE0DupWp/1AYI7/6DEaLQu66Mrd35BKUWKJSlFv1+rue4cGM7shgR981qSon+ZNwUJ8iDgoYU2OvDRRQ99DDDECAHGmGCKmf80hZSx/Kik/LliFbtmN6xmt+yOjdg9GztV4tROnRwX/Bsaaw51nt4Lc7tWaZYHp/MlzKx51LZs5htNri+2AAAAAQAB//8AD3jaY2BkYGDgAWIxIGZiYARCESBmAfMYAAR6AEMAAAABAAAAANXtRbgAAAAA2AhRFAAAAADYCNuG) format("woff");
}

/* If we add the border using a regular CSS border, it won't look good on non-retina devices,
 * since its edges can look jagged due to lack of antialiasing. In this case, we are several
 * layers of box-shadow to add the border visually, which will render the border smoother. */
/* Fallback for non-latin fonts */
/* Calculates maximum width for post content */
/* Nested sub-menu padding: 10 levels deep */
/* Normalize */
/*! normalize.css v8.0.0 | MIT License | github.com/necolas/normalize.css */
/* Document
	 ========================================================================== */
/**
 * 1. Correct the line height in all browsers.
 * 2. Prevent adjustments of font size after orientation changes in iOS.
 */
html {
  line-height: 1.15;
  /* 1 */
  -webkit-text-size-adjust: 100%;
  /* 2 */
}

/* Sections
	 ========================================================================== */
/**
 * Remove the margin in all browsers.
 */
body {
  margin: 0;
}

/**
 * Correct the font size and margin on `h1` elements within `section` and
 * `article` contexts in Chrome, Firefox, and Safari.
 */
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}

/* Grouping content
	 ========================================================================== */
/**
 * 1. Add the correct box sizing in Firefox.
 * 2. Show the overflow in Edge and IE.
 */
hr {
  box-sizing: content-box;
  /* 1 */
  height: 0;
  /* 1 */
  overflow: visible;
  /* 2 */
}

/**
 * 1. Correct the inheritance and scaling of font size in all browsers.
 * 2. Correct the odd `em` font sizing in all browsers.
 */
pre {
  font-family: monospace, monospace;
  /* 1 */
  font-size: 1em;
  /* 2 */
}

/* Text-level semantics
	 ========================================================================== */
/**
 * Remove the gray background on active links in IE 10.
 */
a {
  background-color: transparent;
}

/**
 * 1. Remove the bottom border in Chrome 57-
 * 2. Add the correct text decoration in Chrome, Edge, IE, Opera, and Safari.
 */
abbr[title] {
  border-bottom: none;
  /* 1 */
  text-decoration: underline;
  /* 2 */
  text-decoration: underline dotted;
  /* 2 */
}

/**
 * Add the correct font weight in Chrome, Edge, and Safari.
 */
b,
strong {
  font-weight: bolder;
}

/**
 * 1. Correct the inheritance and scaling of font size in all browsers.
 * 2. Correct the odd `em` font sizing in all browsers.
 */
code,
kbd,
samp {
  font-family: monospace, monospace;
  /* 1 */
  font-size: 1em;
  /* 2 */
}

/**
 * Add the correct font size in all browsers.
 */
small {
  font-size: 80%;
}

/**
 * Prevent `sub` and `sup` elements from affecting the line height in
 * all browsers.
 */
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}

sub {
  bottom: -0.25em;
}

sup {
  top: -0.5em;
}

/* Embedded content
	 ========================================================================== */
/**
 * Remove the border on images inside links in IE 10.
 */
img {
  border-style: none;
}

/* Forms
	 ========================================================================== */
/**
 * 1. Change the font styles in all browsers.
 * 2. Remove the margin in Firefox and Safari.
 */
button,
input,
optgroup,
select,
textarea {
  font-family: inherit;
  /* 1 */
  font-size: 100%;
  /* 1 */
  line-height: 1.15;
  /* 1 */
  margin: 0;
  /* 2 */
}

/**
 * Show the overflow in IE.
 * 1. Show the overflow in Edge.
 */
button,
input {
  /* 1 */
  overflow: visible;
}

/**
 * Remove the inheritance of text transform in Edge, Firefox, and IE.
 * 1. Remove the inheritance of text transform in Firefox.
 */
button,
select {
  /* 1 */
  text-transform: none;
}

/**
 * Correct the inability to style clickable types in iOS and Safari.
 */
button,
[type="button"],
[type="reset"],
[type="submit"] {
  -webkit-appearance: button;
}

/**
 * Remove the inner border and padding in Firefox.
 */
button::-moz-focus-inner,
[type="button"]::-moz-focus-inner,
[type="reset"]::-moz-focus-inner,
[type="submit"]::-moz-focus-inner {
  border-style: none;
  padding: 0;
}

/**
 * Restore the focus styles unset by the previous rule.
 */
button:-moz-focusring,
[type="button"]:-moz-focusring,
[type="reset"]:-moz-focusring,
[type="submit"]:-moz-focusring {
  outline: 1px dotted ButtonText;
}

/**
 * Correct the padding in Firefox.
 */
fieldset {
  padding: 0.35em 0.75em 0.625em;
}

/**
 * 1. Correct the text wrapping in Edge and IE.
 * 2. Correct the color inheritance from `fieldset` elements in IE.
 * 3. Remove the padding so developers are not caught out when they zero out
 *		`fieldset` elements in all browsers.
 */
legend {
  box-sizing: border-box;
  /* 1 */
  color: inherit;
  /* 2 */
  display: table;
  /* 1 */
  max-width: 100%;
  /* 1 */
  padding: 0;
  /* 3 */
  white-space: normal;
  /* 1 */
}

/**
 * Add the correct vertical alignment in Chrome, Firefox, and Opera.
 */
progress {
  vertical-align: baseline;
}

/**
 * Remove the default vertical scrollbar in IE 10+.
 */
textarea {
  overflow: auto;
}

/**
 * 1. Add the correct box sizing in IE 10.
 * 2. Remove the padding in IE 10.
 */
[type="checkbox"],
[type="radio"] {
  box-sizing: border-box;
  /* 1 */
  padding: 0;
  /* 2 */
}

/**
 * Correct the cursor style of increment and decrement buttons in Chrome.
 */
[type="number"]::-webkit-inner-spin-button,
[type="number"]::-webkit-outer-spin-button {
  height: auto;
}

/**
 * 1. Correct the odd appearance in Chrome and Safari.
 * 2. Correct the outline style in Safari.
 */
[type="search"] {
  -webkit-appearance: textfield;
  /* 1 */
  outline-offset: -2px;
  /* 2 */
}

/**
 * Remove the inner padding in Chrome and Safari on macOS.
 */
[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}

/**
 * 1. Correct the inability to style clickable types in iOS and Safari.
 * 2. Change font properties to `inherit` in Safari.
 */
::-webkit-file-upload-button {
  -webkit-appearance: button;
  /* 1 */
  font: inherit;
  /* 2 */
}

/* Interactive
	 ========================================================================== */
/*
 * Add the correct display in Edge, IE 10+, and Firefox.
 */
details {
  display: block;
}

/*
 * Add the correct display in all browsers.
 */
summary {
  display: list-item;
}

/* Misc
	 ========================================================================== */
/**
 * Add the correct display in IE 10+.
 */
template {
  display: none;
}

/**
 * Add the correct display in IE 10.
 */
[hidden] {
  display: none;
}

/* Typography */
html {
  font-size: 22px;
}

body {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #111;
  font-family: "NonBreakingSpaceOverride", "Hoefler Text", "Baskerville Old Face", Garamond, "Times New Roman", serif;
  font-weight: 400;
  font-size: 1em;
  line-height: 1.8;
  margin: 0;
  text-rendering: optimizeLegibility;
}

button,
input,
select,
optgroup,
textarea {
  color: #111;
  font-family: "NonBreakingSpaceOverride", "Hoefler Text", "Baskerville Old Face", Garamond, "Times New Roman", serif;
  font-weight: 400;
  line-height: 1.8;
  text-rendering: optimizeLegibility;
}

.author-description .author-link,
.comment-metadata,
.comment-reply-link,
.comments-title,
.comment-author .fn,
.discussion-meta-info,
.entry-meta,
.entry-footer,
.main-navigation,
.no-comments,
.not-found .page-title,
.error-404 .page-title,
.post-navigation .post-title,
.page-links,
.page-description,
.pagination .nav-links,
.sticky-post,
.site-title,
.site-info,
#cancel-comment-reply-link,
img:after,
h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
}

.main-navigation,
.page-description,
.author-description .author-link,
.not-found .page-title,
.error-404 .page-title,
.post-navigation .post-title,
.pagination .nav-links,
.comments-title,
.comment-author .fn,
.no-comments,
.site-title,
h1,
h2,
h3,
h4,
h5,
h6 {
  font-weight: 700;
  letter-spacing: -0.02em;
  line-height: 1.2;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.page-title {
  font-family: "NonBreakingSpaceOverride", "Hoefler Text", "Baskerville Old Face", Garamond, "Times New Roman", serif;
}

.site-branding,
.main-navigation ul.main-menu > li,
.social-navigation,
.author-description .author-bio,
.nav-links {
  line-height: 1.25;
}

h1 {
  font-size: 2.25em;
}

@media only screen and (min-width: 768px) {
  h1 {
    font-size: 2.8125em;
  }
}

.entry-title,
.not-found .page-title,
.error-404 .page-title,
.has-larger-font-size,
h2 {
  font-size: 1.6875em;
}

@media only screen and (min-width: 768px) {
  .entry-title,
  .not-found .page-title,
  .error-404 .page-title,
  .has-larger-font-size,
  h2 {
    font-size: 2.25em;
  }
}

.has-regular-font-size,
.has-large-font-size,
.comments-title,
h3 {
  font-size: 1.6875em;
}

.site-title,
.site-description,
.main-navigation,
.nav-links,
.page-title,
.page-description,
.comment-author .fn,
.no-comments,
h2.author-title,
p.author-bio,
h4 {
  font-size: 1.125em;
}

.pagination .nav-links,
.comment-content,
h5 {
  font-size: 0.88889em;
}

.entry-meta,
.entry-footer,
.discussion-meta-info,
.site-info,
.has-small-font-size,
.comment-reply-link,
.comment-metadata,
.comment-notes,
.sticky-post,
#cancel-comment-reply-link,
img:after,
h6 {
  font-size: 0.71111em;
}

.site-title,
.page-title {
  font-weight: normal;
}

.page-description,
.page-links a {
  font-weight: bold;
}

.site-description {
  letter-spacing: -0.01em;
}

.post-navigation .post-title,
.entry-title,
.not-found .page-title,
.error-404 .page-title,
.comments-title,
blockquote {
  hyphens: auto;
  word-break: break-word;
}

/* Do not hyphenate entry title on tablet view and bigger. */
@media only screen and (min-width: 768px) {
  .entry-title {
    hyphens: none;
  }
}

p {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

dfn,
cite,
em,
i {
  font-style: italic;
}

blockquote cite {
  font-size: 0.71111em;
  font-style: normal;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
}

pre {
  font-size: 0.88889em;
  font-family: "Courier 10 Pitch", Courier, monospace;
  line-height: 1.8;
  overflow: auto;
}

code,
kbd,
tt,
var {
  font-size: 0.88889em;
  font-family: Menlo, monaco, Consolas, Lucida Console, monospace;
}

abbr, acronym {
  border-bottom: 1px dotted #666;
  cursor: help;
}

mark,
ins {
  background: #fff9c0;
  text-decoration: none;
}

big {
  font-size: 125%;
}

a {
  text-decoration: none;
}

a:hover {
  text-decoration: none;
}

a:focus {
  text-decoration: underline;
}

/* Arabic */
html[lang="ar"] .site *,
html[lang="ary"] .site *,
html[lang="azb"] .site *,
html[lang="ckb"] .site *,
html[lang="fa-IR"] .site *,
html[lang="haz"] .site *,
html[lang="ps"] .site * {
  font-family: Tahoma, Arial, sans-serif !important;
}

/* Cyrillic */
html[lang="be"] .site *,
html[lang="bg-BG"] .site *,
html[lang="kk"] .site *,
html[lang="mk-MK"] .site *,
html[lang="mn"] .site *,
html[lang="ru-RU"] .site *,
html[lang="sah"] .site *,
html[lang="sr-RS"] .site *,
html[lang="tt-RU"] .site *,
html[lang="uk"] .site * {
  font-family: 'Helvetica Neue', Helvetica, 'Segoe UI', Arial, sans-serif !important;
}

/* Chinese (Hong Kong) */
html[lang="zh-HK"] .site * {
  font-family: -apple-system, BlinkMacSystemFont, 'PingFang HK', 'Helvetica Neue', "Microsoft YaHei New", STHeiti Light, sans-serif !important;
}

/* Chinese (Taiwan) */
html[lang="zh-TW"] .site * {
  font-family: -apple-system, BlinkMacSystemFont, 'PingFang TC', 'Helvetica Neue', "Microsoft YaHei New", STHeiti Light, sans-serif !important;
}

/* Chinese (China) */
html[lang="zh-CN"] .site * {
  font-family: -apple-system, BlinkMacSystemFont, 'PingFang SC', 'Helvetica Neue', "Microsoft YaHei New", STHeiti Light, sans-serif !important;
}

/* Devanagari */
html[lang="bn-BD"] .site *,
html[lang="hi-IN"] .site *,
html[lang="mr"] .site *,
html[lang="ne-NP"] .site * {
  font-family: Arial, sans-serif !important;
}

/* Greek */
html[lang="el"] .site * {
  font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif !important;
}

/* Gujarati */
html[lang="gu"] .site * {
  font-family: Arial, sans-serif !important;
}

/* Hebrew */
html[lang="he-IL"] .site * {
  font-family: 'Arial Hebrew', Arial, sans-serif !important;
}

/* Japanese */
html[lang="ja"] .site * {
  font-family: -apple-system, BlinkMacSystemFont, "Hiragino Sans", Meiryo, "Helvetica Neue", sans-serif !important;
}

/* Korean */
html[lang="ko-KR"] .site * {
  font-family: 'Apple SD Gothic Neo', 'Malgun Gothic', 'Nanum Gothic', Dotum, sans-serif !important;
}

/* Thai */
html[lang="th"] .site * {
  font-family: 'Sukhumvit Set', 'Helvetica Neue', helvetica, arial, sans-serif !important;
}

/* Vietnamese */
html[lang="vi"] .site * {
  font-family: 'Libre Franklin', sans-serif !important;
}

/* Elements */
html {
  box-sizing: border-box;
}

::-moz-selection {
  background-color: #bfdcea;
}

::selection {
  background-color: #bfdcea;
}

*,
*:before,
*:after {
  box-sizing: inherit;
}

body {
  background-color: #fff;
}

a {
  transition: color 110ms ease-in-out;
  color: #0073aa;
}

a:hover,
a:active {
  color: #005177;
  outline: 0;
  text-decoration: none;
}

a:focus {
  outline: thin;
  outline-style: dotted;
  text-decoration: underline;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  clear: both;
  margin: 1rem 0;
}

h1:not(.site-title):before,
h2:before {
  background: #767676;
  content: "\020";
  display: block;
  height: 2px;
  margin: 1rem 0;
  width: 1em;
}

hr {
  background-color: #767676;
  border: 0;
  height: 2px;
}

ul,
ol {
  padding-left: 1rem;
}

ul {
  list-style: disc;
}

ul ul {
  list-style-type: circle;
}

ol {
  list-style: decimal;
}

li {
  line-height: 1.8;
}

li > ul,
li > ol {
  padding-left: 2rem;
}

dt {
  font-weight: bold;
}

dd {
  margin: 0 1rem 1rem;
}

img {
  height: auto;
  max-width: 100%;
  position: relative;
}

figure {
  margin: 0;
}

blockquote {
  border-left: 2px solid #0073aa;
  margin-left: 0;
  padding: 0 0 0 1rem;
}

blockquote > p {
  margin: 0 0 1rem;
}

blockquote cite {
  color: #767676;
}

table {
  margin: 0 0 1rem;
  border-collapse: collapse;
  width: 100%;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
}

table td,
table th {
  padding: 0.5em;
  border: 1px solid #767676;
  word-break: break-all;
}

/* Forms */
.button,
button,
input[type="button"],
input[type="reset"],
input[type="submit"] {
  transition: background 150ms ease-in-out;
  background: #0073aa;
  border: none;
  border-radius: 5px;
  box-sizing: border-box;
  color: #fff;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  font-size: 0.88889em;
  font-weight: 700;
  line-height: 1.2;
  outline: none;
  padding: 0.76rem 1rem;
  text-decoration: none;
  vertical-align: bottom;
}

.button:hover,
button:hover,
input[type="button"]:hover,
input[type="reset"]:hover,
input[type="submit"]:hover {
  background: #111;
  cursor: pointer;
}

.button:visited,
button:visited,
input[type="button"]:visited,
input[type="reset"]:visited,
input[type="submit"]:visited {
  color: #fff;
  text-decoration: none;
}

.button:focus,
button:focus,
input[type="button"]:focus,
input[type="reset"]:focus,
input[type="submit"]:focus {
  background: #111;
  outline: thin dotted;
  outline-offset: -4px;
}

input[type="text"],
input[type="email"],
input[type="url"],
input[type="password"],
input[type="search"],
input[type="number"],
input[type="tel"],
input[type="range"],
input[type="date"],
input[type="month"],
input[type="week"],
input[type="time"],
input[type="datetime"],
input[type="datetime-local"],
input[type="color"],
textarea {
  -webkit-backface-visibility: hidden;
  background: #fff;
  border: solid 1px #ccc;
  box-sizing: border-box;
  outline: none;
  padding: 0.36rem 0.66rem;
  -webkit-appearance: none;
  outline-offset: 0;
  border-radius: 0;
}

input[type="text"]:focus,
input[type="email"]:focus,
input[type="url"]:focus,
input[type="password"]:focus,
input[type="search"]:focus,
input[type="number"]:focus,
input[type="tel"]:focus,
input[type="range"]:focus,
input[type="date"]:focus,
input[type="month"]:focus,
input[type="week"]:focus,
input[type="time"]:focus,
input[type="datetime"]:focus,
input[type="datetime-local"]:focus,
input[type="color"]:focus,
textarea:focus {
  border-color: #0073aa;
  outline: thin solid rgba(0, 115, 170, 0.15);
  outline-offset: -4px;
}

input[type="search"]::-webkit-search-decoration {
  display: none;
}

textarea {
  box-sizing: border-box;
  display: block;
  width: 100%;
  max-width: 100%;
  resize: vertical;
}

form p {
  margin: 1rem 0;
}

/* Navigation */
/*--------------------------------------------------------------
## Links
--------------------------------------------------------------*/
a {
  transition: color 110ms ease-in-out;
  color: #0073aa;
}

a:visited {
  color: #0073aa;
}

a:hover, a:active {
  color: #005177;
  outline: 0;
  text-decoration: none;
}

a:focus {
  outline: thin dotted;
  text-decoration: underline;
}

/*--------------------------------------------------------------
## Menus
--------------------------------------------------------------*/
/** === Main menu === */
.main-navigation {
  display: block;
  margin-top: 0.25rem;
  /* Un-style buttons */
  /*
	 * Sub-menu styles
	 *
	 * :focus-within needs its own selector so other similar
	 * selectors don’t get ignored if a browser doesn’t recognize it
	 */
  /**
	 * Fade-in animation for top-level submenus
	 */
  /**
	 * Off-canvas touch device styles
	 */
}

body.page .main-navigation {
  display: block;
}

.main-navigation > div {
  display: inline;
}

.main-navigation button {
  display: inline-block;
  border: none;
  padding: 0;
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  font-weight: 700;
  line-height: 1.2;
  text-decoration: none;
  background: transparent;
  color: inherit;
  cursor: pointer;
  transition: background 250ms ease-in-out, transform 150ms ease;
  -webkit-appearance: none;
  -moz-appearance: none;
}

.main-navigation button:hover, .main-navigation button:focus {
  background: transparent;
}

.main-navigation button:focus {
  outline: 1px solid transparent;
  outline-offset: -4px;
}

.main-navigation button:active {
  transform: scale(0.99);
}

.main-navigation .main-menu {
  display: inline-block;
  margin: 0;
  padding: 0;
}

.main-navigation .main-menu > li {
  color: #0073aa;
  display: inline;
  position: relative;
}

.main-navigation .main-menu > li > a {
  font-weight: 700;
  color: #0073aa;
  margin-right: 0.5rem;
}

.main-navigation .main-menu > li > a + svg {
  margin-right: 0.5rem;
}

.main-navigation .main-menu > li > a:hover,
.main-navigation .main-menu > li > a:hover + svg {
  color: #005177;
}

.main-navigation .main-menu > li.menu-item-has-children {
  display: inline-block;
  position: inherit;
}

@media only screen and (min-width: 768px) {
  .main-navigation .main-menu > li.menu-item-has-children {
    position: relative;
  }
}

.main-navigation .main-menu > li.menu-item-has-children > a {
  margin-right: 0.125rem;
}

.main-navigation .main-menu > li.menu-item-has-children > a:after,
.main-navigation .main-menu > li.menu-item-has-children .menu-item-has-children > a:after {
  content: "";
  display: none;
}

.main-navigation .main-menu > li.menu-item-has-children .submenu-expand {
  display: inline-block;
  margin-right: 0.25rem;
  /* Priority+ Menu */
}

.main-navigation .main-menu > li.menu-item-has-children .submenu-expand.main-menu-more-toggle {
  position: relative;
  height: 24px;
  line-height: 1.2;
  width: 24px;
  padding: 0;
  margin-left: 0.5rem;
}

.main-navigation .main-menu > li.menu-item-has-children .submenu-expand.main-menu-more-toggle svg {
  height: 24px;
  width: 24px;
  top: -0.125rem;
  vertical-align: text-bottom;
}

.wp-customizer-unloading .main-navigation .main-menu > li.menu-item-has-children .submenu-expand, .main-navigation .main-menu > li.menu-item-has-children .submenu-expand.is-empty {
  display: none;
}

.main-navigation .main-menu > li.menu-item-has-children .submenu-expand svg {
  position: relative;
  top: 0.2rem;
}

.main-navigation .main-menu > li:last-child > a,
.main-navigation .main-menu > li:last-child.menu-item-has-children .submenu-expand {
  margin-right: 0;
}

.main-navigation .sub-menu {
  background-color: #0073aa;
  color: #fff;
  list-style: none;
  padding-left: 0;
  position: absolute;
  opacity: 0;
  left: -9999px;
  z-index: 99999;
}

@media only screen and (min-width: 768px) {
  .main-navigation .sub-menu {
    width: auto;
    min-width: -moz-max-content;
    min-width: -webkit-max-content;
    min-width: max-content;
  }
}

.main-navigation .sub-menu > li {
  display: block;
  float: none;
  position: relative;
}

.main-navigation .sub-menu > li.menu-item-has-children .submenu-expand {
  display: inline-block;
  position: absolute;
  width: calc( 24px + 1rem);
  right: 0;
  top: calc( .125 * 1rem);
  bottom: 0;
  color: white;
  line-height: 1;
  padding: calc( .5 * 1rem);
}

.main-navigation .sub-menu > li.menu-item-has-children .submenu-expand svg {
  top: 0;
}

.main-navigation .sub-menu > li.menu-item-has-children .submenu-expand {
  margin-right: 0;
}

@media only screen and (min-width: 768px) {
  .main-navigation .sub-menu > li.menu-item-has-children .menu-item-has-children > a:after {
    content: "\203a";
  }
}

.main-navigation .sub-menu > li > a,
.main-navigation .sub-menu > li > .menu-item-link-return {
  color: #fff;
  display: block;
  line-height: 1.2;
  text-shadow: none;
  padding: calc( .5 * 1rem) calc( 24px + 1rem) calc( .5 * 1rem) 1rem;
  white-space: nowrap;
}

.main-navigation .sub-menu > li > a:hover, .main-navigation .sub-menu > li > a:focus,
.main-navigation .sub-menu > li > .menu-item-link-return:hover,
.main-navigation .sub-menu > li > .menu-item-link-return:focus {
  background: #005177;
}

.main-navigation .sub-menu > li > a:hover:after, .main-navigation .sub-menu > li > a:focus:after,
.main-navigation .sub-menu > li > .menu-item-link-return:hover:after,
.main-navigation .sub-menu > li > .menu-item-link-return:focus:after {
  background: #005177;
}

.main-navigation .sub-menu > li > .menu-item-link-return {
  width: 100%;
  font-size: 22px;
  font-weight: normal;
  text-align: left;
}

.main-navigation .sub-menu > li > a:empty {
  display: none;
}

.main-navigation .sub-menu > li.mobile-parent-nav-menu-item {
  display: none;
  font-size: 0.88889em;
  font-weight: normal;
}

.main-navigation .sub-menu > li.mobile-parent-nav-menu-item svg {
  position: relative;
  top: 0.2rem;
  margin-right: calc( .25 * 1rem);
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas)[focus-within] > .sub-menu {
  display: block;
  left: 0;
  margin-top: 0;
  opacity: 1;
  width: auto;
  min-width: 100%;
  /* Non-mobile position */
  /* Nested sub-menu dashes */
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus-within > .sub-menu {
  display: block;
  left: 0;
  margin-top: 0;
  opacity: 1;
  width: auto;
  min-width: 100%;
  /* Non-mobile position */
  /* Nested sub-menu dashes */
}

@media only screen and (min-width: 768px) {
  .main-navigation .main-menu .menu-item-has-children:not(.off-canvas)[focus-within] > .sub-menu {
    display: block;
    margin-top: 0;
    opacity: 1;
    position: absolute;
    left: 0;
    right: auto;
    top: auto;
    bottom: auto;
    height: auto;
    min-width: -moz-max-content;
    min-width: -webkit-max-content;
    min-width: max-content;
    transform: none;
  }
  .main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus-within > .sub-menu {
    display: block;
    margin-top: 0;
    opacity: 1;
    position: absolute;
    left: 0;
    right: auto;
    top: auto;
    bottom: auto;
    height: auto;
    min-width: -moz-max-content;
    min-width: -webkit-max-content;
    min-width: max-content;
    transform: none;
  }
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas)[focus-within] > .sub-menu.hidden-links {
  left: 0;
  width: 100%;
  display: table;
  position: absolute;
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus-within > .sub-menu.hidden-links {
  left: 0;
  width: 100%;
  display: table;
  position: absolute;
}

@media only screen and (min-width: 768px) {
  .main-navigation .main-menu .menu-item-has-children:not(.off-canvas)[focus-within] > .sub-menu.hidden-links {
    right: 0;
    left: auto;
    display: block;
    width: max-content;
  }
  .main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus-within > .sub-menu.hidden-links {
    right: 0;
    left: auto;
    display: block;
    width: max-content;
  }
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas)[focus-within] > .sub-menu .submenu-expand {
  display: none;
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus-within > .sub-menu .submenu-expand {
  display: none;
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas)[focus-within] > .sub-menu .sub-menu {
  display: block;
  margin-top: inherit;
  position: relative;
  width: 100%;
  left: 0;
  opacity: 1;
  /* Non-mobile position */
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus-within > .sub-menu .sub-menu {
  display: block;
  margin-top: inherit;
  position: relative;
  width: 100%;
  left: 0;
  opacity: 1;
  /* Non-mobile position */
}

@media only screen and (min-width: 768px) {
  .main-navigation .main-menu .menu-item-has-children:not(.off-canvas)[focus-within] > .sub-menu .sub-menu {
    float: none;
    max-width: 100%;
  }
  .main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus-within > .sub-menu .sub-menu {
    float: none;
    max-width: 100%;
  }
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas)[focus-within] > .sub-menu .sub-menu {
  counter-reset: submenu;
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus-within > .sub-menu .sub-menu {
  counter-reset: submenu;
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas)[focus-within] > .sub-menu .sub-menu > li > a::before {
  font-family: "NonBreakingSpaceOverride", "Hoefler Text", "Baskerville Old Face", Garamond, "Times New Roman", serif;
  font-weight: normal;
  content: "– " counters(submenu, "– ", none);
  counter-increment: submenu;
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus-within > .sub-menu .sub-menu > li > a::before {
  font-family: "NonBreakingSpaceOverride", "Hoefler Text", "Baskerville Old Face", Garamond, "Times New Roman", serif;
  font-weight: normal;
  content: "– " counters(submenu, "– ", none);
  counter-increment: submenu;
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):hover > .sub-menu,
.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus > .sub-menu,
.main-navigation .main-menu .menu-item-has-children.is-focused:not(.off-canvas) > .sub-menu {
  display: block;
  left: 0;
  margin-top: 0;
  opacity: 1;
  width: auto;
  min-width: 100%;
  /* Non-mobile position */
  /* Nested sub-menu dashes */
}

@media only screen and (min-width: 768px) {
  .main-navigation .main-menu .menu-item-has-children:not(.off-canvas):hover > .sub-menu,
  .main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus > .sub-menu,
  .main-navigation .main-menu .menu-item-has-children.is-focused:not(.off-canvas) > .sub-menu {
    display: block;
    float: none;
    margin-top: 0;
    opacity: 1;
    position: absolute;
    left: 0;
    right: auto;
    top: auto;
    bottom: auto;
    height: auto;
    min-width: -moz-max-content;
    min-width: -webkit-max-content;
    min-width: max-content;
    transform: none;
  }
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):hover > .sub-menu.hidden-links,
.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus > .sub-menu.hidden-links,
.main-navigation .main-menu .menu-item-has-children.is-focused:not(.off-canvas) > .sub-menu.hidden-links {
  left: 0;
  width: 100%;
  display: table;
  position: absolute;
}

@media only screen and (min-width: 768px) {
  .main-navigation .main-menu .menu-item-has-children:not(.off-canvas):hover > .sub-menu.hidden-links,
  .main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus > .sub-menu.hidden-links,
  .main-navigation .main-menu .menu-item-has-children.is-focused:not(.off-canvas) > .sub-menu.hidden-links {
    right: 0;
    left: auto;
    display: table;
    width: max-content;
  }
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):hover > .sub-menu .submenu-expand,
.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus > .sub-menu .submenu-expand,
.main-navigation .main-menu .menu-item-has-children.is-focused:not(.off-canvas) > .sub-menu .submenu-expand {
  display: none;
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):hover > .sub-menu .sub-menu,
.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus > .sub-menu .sub-menu,
.main-navigation .main-menu .menu-item-has-children.is-focused:not(.off-canvas) > .sub-menu .sub-menu {
  display: block;
  margin-top: inherit;
  position: relative;
  width: 100%;
  left: 0;
  opacity: 1;
  /* Non-mobile position */
}

@media only screen and (min-width: 768px) {
  .main-navigation .main-menu .menu-item-has-children:not(.off-canvas):hover > .sub-menu .sub-menu,
  .main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus > .sub-menu .sub-menu,
  .main-navigation .main-menu .menu-item-has-children.is-focused:not(.off-canvas) > .sub-menu .sub-menu {
    float: none;
    max-width: 100%;
  }
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):hover > .sub-menu .sub-menu,
.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus > .sub-menu .sub-menu,
.main-navigation .main-menu .menu-item-has-children.is-focused:not(.off-canvas) > .sub-menu .sub-menu {
  counter-reset: submenu;
}

.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):hover > .sub-menu .sub-menu > li > a::before,
.main-navigation .main-menu .menu-item-has-children:not(.off-canvas):focus > .sub-menu .sub-menu > li > a::before,
.main-navigation .main-menu .menu-item-has-children.is-focused:not(.off-canvas) > .sub-menu .sub-menu > li > a::before {
  font-family: "NonBreakingSpaceOverride", "Hoefler Text", "Baskerville Old Face", Garamond, "Times New Roman", serif;
  font-weight: normal;
  content: "– " counters(submenu, "– ", none);
  counter-increment: submenu;
}

.main-navigation .main-menu > .menu-item-has-children:not(.off-canvas):hover > .sub-menu {
  animation: fade_in 0.1s forwards;
}

.main-navigation .main-menu .menu-item-has-children.off-canvas .sub-menu .submenu-expand .svg-icon {
  transform: rotate(270deg);
}

.main-navigation .main-menu .menu-item-has-children.off-canvas .sub-menu .sub-menu {
  opacity: 0;
  position: absolute;
  z-index: 0;
  transform: translateX(-100%);
}

.main-navigation .main-menu .menu-item-has-children.off-canvas .sub-menu li:hover,
.main-navigation .main-menu .menu-item-has-children.off-canvas .sub-menu li:focus,
.main-navigation .main-menu .menu-item-has-children.off-canvas .sub-menu li > a:hover,
.main-navigation .main-menu .menu-item-has-children.off-canvas .sub-menu li > a:focus {
  background-color: transparent;
}

.main-navigation .main-menu .menu-item-has-children.off-canvas .sub-menu > li > a,
.main-navigation .main-menu .menu-item-has-children.off-canvas .sub-menu > li > .menu-item-link-return {
  white-space: inherit;
}

.main-navigation .main-menu .menu-item-has-children.off-canvas .sub-menu.expanded-true {
  display: table;
  margin-top: 0;
  opacity: 1;
  padding-left: 0;
  /* Mobile position */
  left: 0;
  top: 0;
  right: 0;
  bottom: 0;
  position: fixed;
  z-index: 100000;
  /* Make sure appears above mobile admin bar */
  width: 100vw;
  height: 100vh;
  max-width: 100vw;
  transform: translateX(100%);
  animation: slide_in_right 0.3s forwards;
  /* Prevent menu from being blocked by admin bar */
}

.main-navigation .main-menu .menu-item-has-children.off-canvas .sub-menu.expanded-true > .mobile-parent-nav-menu-item {
  display: block;
}

.admin-bar .main-navigation .main-menu .menu-item-has-children.off-canvas .sub-menu.expanded-true {
  top: 46px;
  height: calc( 100vh - 46px);
  /* WP core breakpoint */
}

.admin-bar .main-navigation .main-menu .menu-item-has-children.off-canvas .sub-menu.expanded-true .sub-menu.expanded-true {
  top: 0;
}

@media only screen and (min-width: 782px) {
  .admin-bar .main-navigation .main-menu .menu-item-has-children.off-canvas .sub-menu.expanded-true {
    top: 32px;
    height: calc( 100vh - 32px);
  }
  .admin-bar .main-navigation .main-menu .menu-item-has-children.off-canvas .sub-menu.expanded-true .sub-menu.expanded-true {
    top: 0;
  }
}

.main-navigation .main-menu-more:nth-child(n+3) {
  display: none;
}

/* Menu animation */
@keyframes slide_in_right {
  100% {
    transform: translateX(0%);
  }
}

@keyframes fade_in {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

/* Social menu */
.social-navigation {
  margin-top: calc(1rem / 2);
  text-align: left;
}

.social-navigation ul.social-links-menu {
  content: "";
  display: table;
  table-layout: fixed;
  display: inline-block;
  margin: 0;
  padding: 0;
}

.social-navigation ul.social-links-menu li {
  display: inline-block;
  vertical-align: bottom;
  vertical-align: -webkit-baseline-middle;
  list-style: none;
}

.social-navigation ul.social-links-menu li:nth-child(n+2) {
  margin-left: 0.1em;
}

.social-navigation ul.social-links-menu li a {
  border-bottom: 1px solid transparent;
  display: block;
  color: #111;
  margin-bottom: -1px;
  transition: opacity 110ms ease-in-out;
}

.social-navigation ul.social-links-menu li a:hover, .social-navigation ul.social-links-menu li a:active {
  color: #111;
  opacity: 0.6;
}

.social-navigation ul.social-links-menu li a:focus {
  color: #111;
  opacity: 1;
  border-bottom: 1px solid #111;
}

.social-navigation ul.social-links-menu li a svg {
  display: block;
  width: 32px;
  height: 32px;
  transform: translateZ(0);
}

.social-navigation ul.social-links-menu li a svg#ui-icon-link {
  transform: rotate(-45deg);
}

@media only screen and (min-width: 768px) {
  .site-title + .social-navigation,
  .site-description + .social-navigation {
    margin-top: calc(1rem / 5);
  }
}

/** === Footer menu === */
.footer-navigation {
  display: inline;
}

.footer-navigation > div {
  display: inline;
}

.footer-navigation .footer-menu {
  display: inline;
  padding-left: 0;
}

.footer-navigation .footer-menu li {
  display: inline;
  margin-right: 1rem;
}

/*--------------------------------------------------------------
## Next / Previous
--------------------------------------------------------------*/
/* Next/Previous navigation */
.post-navigation {
  margin: calc(3 * 1rem) 0;
}

@media only screen and (min-width: 768px) {
  .post-navigation {
    margin: calc(3 * 1rem) calc(10% + 60px);
    max-width: calc(6 * (100vw / 12));
  }
}

@media only screen and (min-width: 1168px) {
  .post-navigation {
    margin: calc(3 * 1rem) 0;
    max-width: 100%;
  }
}

.post-navigation .nav-links {
  margin: 0 1rem;
  max-width: 100%;
  display: flex;
  flex-direction: column;
}

@media only screen and (min-width: 768px) {
  .post-navigation .nav-links {
    margin: 0;
  }
}

@media only screen and (min-width: 1168px) {
  .post-navigation .nav-links {
    flex-direction: row;
    margin: 0 calc(10% + 60px);
    max-width: calc(6 * (100vw / 12) - 28px);
  }
}

.post-navigation .nav-links a .meta-nav {
  color: #767676;
  user-select: none;
}

.post-navigation .nav-links a .meta-nav:before, .post-navigation .nav-links a .meta-nav:after {
  display: none;
  content: "—";
  width: 2em;
  color: #767676;
  height: 1em;
}

.post-navigation .nav-links a .post-title {
  hyphens: auto;
}

.post-navigation .nav-links a:hover {
  color: #005177;
}

@media only screen and (min-width: 1168px) {
  .post-navigation .nav-links .nav-previous,
  .post-navigation .nav-links .nav-next {
    min-width: calc(50% - 2 * 1rem);
  }
}

.post-navigation .nav-links .nav-previous {
  order: 2;
}

@media only screen and (min-width: 1168px) {
  .post-navigation .nav-links .nav-previous {
    order: 1;
  }
}

.post-navigation .nav-links .nav-previous + .nav-next {
  margin-bottom: 1rem;
}

.post-navigation .nav-links .nav-previous .meta-nav:before {
  display: inline;
}

.post-navigation .nav-links .nav-next {
  order: 1;
}

@media only screen and (min-width: 1168px) {
  .post-navigation .nav-links .nav-next {
    order: 2;
    padding-left: 1rem;
  }
}

.post-navigation .nav-links .nav-next .meta-nav:after {
  display: inline;
}

.pagination .nav-links {
  display: flex;
  flex-wrap: wrap;
  padding: 0 calc(.5 * 1rem);
}

.pagination .nav-links > * {
  padding: calc(.5 * 1rem);
}

.pagination .nav-links > *.dots, .pagination .nav-links > *.prev {
  padding-left: 0;
}

.pagination .nav-links > *.dots, .pagination .nav-links > *.next {
  padding-right: 0;
}

.pagination .nav-links a:focus {
  text-decoration: underline;
  outline-offset: -1px;
}

.pagination .nav-links a:focus.prev, .pagination .nav-links a:focus.next {
  text-decoration: none;
}

.pagination .nav-links a:focus.prev .nav-prev-text,
.pagination .nav-links a:focus.prev .nav-next-text, .pagination .nav-links a:focus.next .nav-prev-text,
.pagination .nav-links a:focus.next .nav-next-text {
  text-decoration: underline;
}

.pagination .nav-links .nav-next-text,
.pagination .nav-links .nav-prev-text {
  display: none;
}

@media only screen and (min-width: 768px) {
  .pagination .nav-links {
    margin-left: calc(10% + 60px);
    padding: 0;
  }
  .pagination .nav-links .prev > *,
  .pagination .nav-links .next > * {
    display: inline-block;
    vertical-align: text-bottom;
  }
  .pagination .nav-links > * {
    padding: 1rem;
  }
}

.comment-navigation .nav-links {
  display: flex;
  flex-direction: row;
}

.comment-navigation .nav-previous,
.comment-navigation .nav-next {
  min-width: 50%;
  width: 100%;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  font-weight: bold;
}

.comment-navigation .nav-previous .secondary-text,
.comment-navigation .nav-next .secondary-text {
  display: none;
}

@media only screen and (min-width: 768px) {
  .comment-navigation .nav-previous .secondary-text,
  .comment-navigation .nav-next .secondary-text {
    display: inline;
  }
}

.comment-navigation .nav-previous svg,
.comment-navigation .nav-next svg {
  vertical-align: middle;
  position: relative;
  margin: 0 -0.35em;
  top: -1px;
}

.comment-navigation .nav-next {
  text-align: right;
}

/* Accessibility */
/* Text meant only for screen readers. */
.screen-reader-text {
  border: 0;
  clip: rect(1px, 1px, 1px, 1px);
  clip-path: inset(50%);
  height: 1px;
  margin: -1px;
  overflow: hidden;
  padding: 0;
  position: absolute !important;
  width: 1px;
  word-wrap: normal !important;
  /* Many screen reader and browser combinations announce broken words as they would appear visually. */
}

.screen-reader-text:focus {
  background-color: #f1f1f1;
  border-radius: 3px;
  box-shadow: 0 0 2px 2px rgba(0, 0, 0, 0.6);
  clip: auto !important;
  clip-path: none;
  color: #21759b;
  display: block;
  font-size: 14px;
  font-size: 0.875rem;
  font-weight: bold;
  height: auto;
  left: 5px;
  line-height: normal;
  padding: 15px 23px 14px;
  text-decoration: none;
  top: 5px;
  width: auto;
  z-index: 100000;
  /* Above WP toolbar. */
}

/* Do not show the outline on the skip link target. */
#content[tabindex="-1"]:focus {
  outline: 0;
}

/* Alignments */
.alignleft {
  /*rtl:ignore*/
  float: left;
  /*rtl:ignore*/
  margin-right: 1rem;
}

@media only screen and (min-width: 768px) {
  .alignleft {
    /*rtl:ignore*/
    margin-right: calc(2 * 1rem);
  }
}

.alignright {
  /*rtl:ignore*/
  float: right;
  /*rtl:ignore*/
  margin-left: 1rem;
}

@media only screen and (min-width: 768px) {
  .alignright {
    /*rtl:ignore*/
    margin-left: calc(2 * 1rem);
  }
}

.aligncenter {
  clear: both;
  display: block;
  margin-left: auto;
  margin-right: auto;
}

/* Clearings */
.clear:before,
.clear:after,
.entry-content:before,
.entry-content:after,
.comment-content:before,
.comment-content:after,
.site-header:before,
.site-header:after,
.site-content:before,
.site-content:after,
.site-footer:before,
.site-footer:after {
  content: "";
  display: table;
  table-layout: fixed;
}

.clear:after,
.entry-content:after,
.comment-content:after,
.site-header:after,
.site-content:after,
.site-footer:after {
  clear: both;
}

/* Layout */
/** === Layout === */
#page {
  width: 100%;
}

.site-content {
  overflow: hidden;
}

/* Content */
/*--------------------------------------------------------------
## Header
--------------------------------------------------------------*/
.site-header {
  padding: 1em;
}

.site-header.featured-image {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  min-height: 90vh;
}

.site-header.featured-image .site-branding-container {
  margin-bottom: auto;
}

@media only screen and (min-width: 768px) {
  .site-header {
    margin: 0;
    padding: 3rem 0;
  }
  .site-header.featured-image {
    min-height: 100vh;
    margin-bottom: 3rem;
  }
}

.site-branding {
  color: #767676;
  position: relative;
}

@media only screen and (min-width: 768px) {
  .site-branding {
    margin: 0 calc(10% + 60px);
  }
}

.site-logo {
  position: relative;
  z-index: 999;
  margin-bottom: calc(.66 * 1rem);
}

@media only screen and (min-width: 768px) {
  .site-logo {
    margin-bottom: 0;
    position: absolute;
    right: calc(100% + (1.25 * 1rem));
    top: 4px;
    z-index: 999;
  }
}

.site-logo .custom-logo-link {
  border-radius: 100%;
  box-sizing: content-box;
  box-shadow: 0 0 0 0 rgba(0, 0, 0, 0);
  display: block;
  width: 50px;
  height: 50px;
  overflow: hidden;
  transition: box-shadow 200ms ease-in-out;
}

.site-logo .custom-logo-link .custom-logo {
  min-height: inherit;
}

.site-logo .custom-logo-link:hover, .site-logo .custom-logo-link:active, .site-logo .custom-logo-link:focus {
  box-shadow: 0 0 0 2px black;
}

@media only screen and (min-width: 768px) {
  .site-logo .custom-logo-link {
    width: 64px;
    height: 64px;
  }
}

.site-title {
  margin: auto;
  display: inline;
  color: #111;
  /* When there is no description set, make sure navigation appears below title. */
}

.site-title a {
  color: #111;
}

.site-title a:link, .site-title a:visited {
  color: #111;
}

.site-title a:hover {
  color: #4a4a4a;
}

.featured-image .site-title {
  margin: 0;
}

@media only screen and (min-width: 768px) {
  .featured-image .site-title {
    display: inline-block;
  }
}

.site-title + .main-navigation {
  display: block;
}

@media only screen and (min-width: 768px) {
  .site-title {
    display: inline;
  }
}

.site-title:not(:empty) + .site-description:not(:empty):before {
  content: "\2014";
  margin: 0 .2em;
}

.site-description {
  display: inline;
  color: #767676;
  font-weight: normal;
  margin: 0;
}

.site-header.featured-image {
  /* Hide overflow for overflowing featured image */
  overflow: hidden;
  /* Need relative positioning to properly align layers. */
  position: relative;
  /* Add text shadow to text, to increase readability. */
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.35);
  /* Set white text color when featured image is set. */
  /* add focus state to social media icons */
  /* Entry header */
  /* Custom Logo Link */
  /* Make sure important elements are above pseudo elements used for effects. */
  /* Set up image filter layer positioning */
  /* Background & Effects */
  /* Shared background settings between pseudo elements. */
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  /* The intensity of each blend mode is controlled via layer opacity. */
  /* Second layer: screen. */
  /* Third layer: multiply. */
  /* When image filters are inactive, a black overlay is added. */
  /* Fourth layer: overlay. */
  /* Fifth layer: readability overlay */
}

.site-header.featured-image .site-branding .site-title,
.site-header.featured-image .site-branding .site-description,
.site-header.featured-image .main-navigation a:after,
.site-header.featured-image .main-navigation .main-menu > li.menu-item-has-children:after,
.site-header.featured-image .main-navigation li,
.site-header.featured-image .social-navigation li,
.site-header.featured-image .entry-meta,
.site-header.featured-image .entry-title {
  color: #fff;
}

.site-header.featured-image .main-navigation a,
.site-header.featured-image .main-navigation a + svg,
.site-header.featured-image .social-navigation a,
.site-header.featured-image .site-title a,
.site-header.featured-image .site-featured-image a {
  color: #fff;
  transition: opacity 110ms ease-in-out;
}

.site-header.featured-image .main-navigation a:hover, .site-header.featured-image .main-navigation a:active,
.site-header.featured-image .main-navigation a:hover + svg,
.site-header.featured-image .main-navigation a:active + svg,
.site-header.featured-image .main-navigation a + svg:hover,
.site-header.featured-image .main-navigation a + svg:active,
.site-header.featured-image .main-navigation a + svg:hover + svg,
.site-header.featured-image .main-navigation a + svg:active + svg,
.site-header.featured-image .social-navigation a:hover,
.site-header.featured-image .social-navigation a:active,
.site-header.featured-image .social-navigation a:hover + svg,
.site-header.featured-image .social-navigation a:active + svg,
.site-header.featured-image .site-title a:hover,
.site-header.featured-image .site-title a:active,
.site-header.featured-image .site-title a:hover + svg,
.site-header.featured-image .site-title a:active + svg,
.site-header.featured-image .site-featured-image a:hover,
.site-header.featured-image .site-featured-image a:active,
.site-header.featured-image .site-featured-image a:hover + svg,
.site-header.featured-image .site-featured-image a:active + svg {
  color: #fff;
  opacity: 0.6;
}

.site-header.featured-image .main-navigation a:focus,
.site-header.featured-image .main-navigation a:focus + svg,
.site-header.featured-image .main-navigation a + svg:focus,
.site-header.featured-image .main-navigation a + svg:focus + svg,
.site-header.featured-image .social-navigation a:focus,
.site-header.featured-image .social-navigation a:focus + svg,
.site-header.featured-image .site-title a:focus,
.site-header.featured-image .site-title a:focus + svg,
.site-header.featured-image .site-featured-image a:focus,
.site-header.featured-image .site-featured-image a:focus + svg {
  color: #fff;
}

.site-header.featured-image .main-navigation .sub-menu a {
  opacity: inherit;
}

.site-header.featured-image .social-navigation a:focus {
  color: #fff;
  opacity: 1;
  border-bottom: 1px solid #fff;
}

.site-header.featured-image .social-navigation svg,
.site-header.featured-image .site-featured-image svg {
  /* Use -webkit- only if supporting: Chrome < 54, iOS < 9.3, Android < 4.4.4 */
  -webkit-filter: drop-shadow(0 1px 2px rgba(0, 0, 0, 0.35));
  filter: drop-shadow(0 1px 2px rgba(0, 0, 0, 0.35));
}

.site-header.featured-image .site-featured-image {
  /* First layer: grayscale. */
}

.site-header.featured-image .site-featured-image .post-thumbnail img {
  height: auto;
  left: 50%;
  max-width: 1000%;
  min-height: 100%;
  min-width: 100vw;
  position: absolute;
  top: 50%;
  transform: translateX(-50%) translateY(-50%);
  width: auto;
  z-index: 1;
  /* When image filters are active, make it grayscale to colorize it blue. */
}

@supports (object-fit: cover) {
  .site-header.featured-image .site-featured-image .post-thumbnail img {
    height: 100%;
    left: 0;
    object-fit: cover;
    top: 0;
    transform: none;
    width: 100%;
  }
}

.image-filters-enabled .site-header.featured-image .site-featured-image .post-thumbnail img {
  filter: grayscale(100%);
}

.site-header.featured-image .site-featured-image .entry-header {
  margin-top: calc( 4 * 1rem);
  margin-bottom: 0;
  margin-left: 0;
  margin-right: 0;
  /* Entry meta */
}

@media only screen and (min-width: 768px) {
  .site-header.featured-image .site-featured-image .entry-header {
    margin-left: calc(10% + 60px);
    margin-right: calc(10% + 60px);
  }
}

.site-header.featured-image .site-featured-image .entry-header .entry-title:before {
  background: #fff;
}

.site-header.featured-image .site-featured-image .entry-header .entry-meta {
  font-weight: 500;
}

.site-header.featured-image .site-featured-image .entry-header .entry-meta > span {
  margin-right: 1rem;
  display: inline-block;
}

.site-header.featured-image .site-featured-image .entry-header .entry-meta > span:last-child {
  margin-right: 0;
}

.site-header.featured-image .site-featured-image .entry-header .entry-meta a {
  transition: color 110ms ease-in-out;
  color: currentColor;
}

.site-header.featured-image .site-featured-image .entry-header .entry-meta a:hover {
  text-decoration: none;
}

.site-header.featured-image .site-featured-image .entry-header .entry-meta .svg-icon {
  position: relative;
  display: inline-block;
  vertical-align: middle;
  margin-right: 0.5em;
}

.site-header.featured-image .site-featured-image .entry-header .entry-meta .discussion-avatar-list {
  display: none;
}

@media only screen and (min-width: 768px) {
  .site-header.featured-image .site-featured-image .entry-header.has-discussion .entry-meta {
    display: flex;
    position: relative;
  }
  .site-header.featured-image .site-featured-image .entry-header.has-discussion .entry-title {
    padding-right: calc(1 * (100vw / 12) + 1rem);
  }
  .site-header.featured-image .site-featured-image .entry-header.has-discussion .entry-meta .comment-count {
    position: absolute;
    right: 0;
  }
  .site-header.featured-image .site-featured-image .entry-header.has-discussion .entry-meta .discussion-avatar-list {
    display: block;
    position: absolute;
    bottom: 100%;
  }
}

.site-header.featured-image .custom-logo-link {
  background: #fff;
  box-shadow: 0 0 0 0 rgba(255, 255, 255, 0);
}

.site-header.featured-image .custom-logo-link:hover, .site-header.featured-image .custom-logo-link:active, .site-header.featured-image .custom-logo-link:focus {
  box-shadow: 0 0 0 2px white;
}

.site-header.featured-image .site-branding {
  position: relative;
  z-index: 10;
}

.site-header.featured-image .site-featured-image .entry-header {
  position: relative;
  z-index: 9;
}

.site-header.featured-image .site-branding-container:after,
.site-header.featured-image .site-featured-image:before,
.site-header.featured-image .site-featured-image:after, .site-header.featured-image:after {
  display: block;
  position: absolute;
  top: 0;
  left: 0;
  content: "\020";
  width: 100%;
  height: 100%;
}

.image-filters-enabled .site-header.featured-image .site-featured-image:before {
  background: #0073aa;
  mix-blend-mode: screen;
  opacity: 0.1;
}

.site-header.featured-image .site-featured-image:after {
  background: #000;
  mix-blend-mode: multiply;
  opacity: .7;
  /* When image filters are active, a blue overlay is added. */
}

.image-filters-enabled .site-header.featured-image .site-featured-image:after {
  background: #0073aa;
  opacity: .8;
  z-index: 3;
  /* Browsers supporting mix-blend-mode don't need opacity < 1 */
}

@supports (mix-blend-mode: multiply) {
  .image-filters-enabled .site-header.featured-image .site-featured-image:after {
    opacity: 1;
  }
}

.image-filters-enabled .site-header.featured-image .site-branding-container:after {
  background: rgba(0, 0, 0, 0.35);
  mix-blend-mode: overlay;
  opacity: 0.5;
  z-index: 4;
  /* Browsers supporting mix-blend-mode can have a light overlay */
}

@supports (mix-blend-mode: overlay) {
  .image-filters-enabled .site-header.featured-image .site-branding-container:after {
    background: rgba(255, 255, 255, 0.35);
  }
}

.site-header.featured-image:after {
  background: #000;
  /**
		 * Add a transition to the readability overlay, to add a subtle
		 * but smooth effect when resizing the screen.
		 */
  transition: opacity 1200ms ease-in-out;
  opacity: 0.7;
  z-index: 5;
  /* When image filters are active, a blue overlay is added. */
}

.image-filters-enabled .site-header.featured-image:after {
  background: #000e14;
  opacity: 0.38;
}

@media only screen and (min-width: 768px) {
  .image-filters-enabled .site-header.featured-image:after {
    opacity: 0.18;
  }
}

.site-header.featured-image ::-moz-selection {
  background: rgba(255, 255, 255, 0.17);
}

.site-header.featured-image ::selection {
  background: rgba(255, 255, 255, 0.17);
}

/*--------------------------------------------------------------
## Posts and pages
--------------------------------------------------------------*/
.sticky {
  display: block;
}

.sticky-post {
  background: #0073aa;
  color: #fff;
  display: inline-block;
  font-weight: bold;
  line-height: 1;
  padding: .25rem;
  position: absolute;
  text-transform: uppercase;
  top: -1rem;
  z-index: 1;
}

.updated:not(.published) {
  display: none;
}

.page-links {
  clear: both;
  margin: 0 0 calc(1.5 * 1rem);
}

.entry {
  margin-top: calc(6 * 1rem);
}

.entry:first-of-type {
  margin-top: 0;
}

.entry .entry-header {
  margin: calc(3 * 1rem) 1rem 1rem;
  position: relative;
}

@media only screen and (min-width: 768px) {
  .entry .entry-header {
    margin: calc(3 * 1rem) calc(10% + 60px) 1rem;
  }
}

.entry .entry-title {
  margin: 0;
}

.entry .entry-title:before {
  background: #767676;
  content: "\020";
  display: block;
  height: 2px;
  margin: 1rem 0;
  width: 1em;
}

.entry .entry-title a {
  color: inherit;
}

.entry .entry-title a:hover {
  color: #4a4a4a;
}

.entry .entry-meta,
.entry .entry-footer {
  color: #767676;
  font-weight: 500;
}

.entry .entry-meta > span,
.entry .entry-footer > span {
  margin-right: 1rem;
  display: inline-block;
}

.entry .entry-meta > span:last-child,
.entry .entry-footer > span:last-child {
  margin-right: 0;
}

.entry .entry-meta a,
.entry .entry-footer a {
  transition: color 110ms ease-in-out;
  color: currentColor;
}

.entry .entry-meta a:hover,
.entry .entry-footer a:hover {
  text-decoration: none;
  color: #0073aa;
}

.entry .entry-meta .svg-icon,
.entry .entry-footer .svg-icon {
  position: relative;
  display: inline-block;
  vertical-align: middle;
  margin-right: 0.5em;
}

.entry .entry-meta {
  margin: 1rem 0;
}

.entry .entry-footer {
  margin: calc(2 * 1rem) 1rem 1rem;
}

@media only screen and (min-width: 768px) {
  .entry .entry-footer {
    margin: 1rem calc(10% + 60px) calc(3 * 1rem);
    max-width: calc(8 * (100vw / 12) - 28px);
  }
}

@media only screen and (min-width: 768px) {
  .entry .entry-footer {
    max-width: calc(6 * (100vw / 12) - 28px);
  }
}

.entry .post-thumbnail {
  margin: 1rem;
}

@media only screen and (min-width: 768px) {
  .entry .post-thumbnail {
    margin: 1rem calc(10% + 60px);
  }
}

.entry .post-thumbnail:focus {
  outline: none;
}

.entry .post-thumbnail .post-thumbnail-inner {
  display: block;
}

.entry .post-thumbnail .post-thumbnail-inner img {
  position: relative;
  display: block;
  width: 100%;
}

.image-filters-enabled .entry .post-thumbnail {
  position: relative;
  display: block;
}

.image-filters-enabled .entry .post-thumbnail .post-thumbnail-inner {
  filter: grayscale(100%);
}

.image-filters-enabled .entry .post-thumbnail .post-thumbnail-inner:after {
  background: rgba(0, 0, 0, 0.35);
  content: "";
  display: block;
  height: 100%;
  opacity: .5;
  pointer-events: none;
  position: absolute;
  top: 0;
  width: 100%;
  z-index: 4;
}

@supports (mix-blend-mode: multiply) {
  .image-filters-enabled .entry .post-thumbnail .post-thumbnail-inner:after {
    display: none;
  }
}

.image-filters-enabled .entry .post-thumbnail:before, .image-filters-enabled .entry .post-thumbnail:after {
  position: absolute;
  display: block;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  content: "\020";
  pointer-events: none;
}

.image-filters-enabled .entry .post-thumbnail:before {
  background: #0073aa;
  mix-blend-mode: screen;
  opacity: 0.1;
  z-index: 2;
}

.image-filters-enabled .entry .post-thumbnail:after {
  background: #0073aa;
  mix-blend-mode: multiply;
  opacity: .8;
  z-index: 3;
  /* Browsers supporting mix-blend-mode don't need opacity < 1 */
}

@supports (mix-blend-mode: multiply) {
  .image-filters-enabled .entry .post-thumbnail:after {
    opacity: 1;
  }
}

.entry .entry-content,
.entry .entry-summary {
  max-width: calc(100% - (2 * 1rem));
  margin: 0 1rem;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content,
  .entry .entry-summary {
    max-width: 80%;
    margin: 0 10%;
    padding: 0 60px;
  }
}

.entry .entry-content p {
  word-wrap: break-word;
}

.entry .entry-content .more-link {
  transition: color 110ms ease-in-out;
  display: inline;
  color: inherit;
}

.entry .entry-content .more-link:after {
  content: "\02192";
  display: inline-block;
  margin-left: 0.5em;
}

.entry .entry-content .more-link:hover {
  color: #0073aa;
  text-decoration: none;
}

.entry .entry-content a {
  text-decoration: underline;
}

.entry .entry-content a.button, .entry .entry-content a:hover {
  text-decoration: none;
}

.entry .entry-content a.button {
  display: inline-block;
}

.entry .entry-content a.button:hover {
  background: #111;
  color: #fff;
  cursor: pointer;
}

.entry .entry-content > iframe[style] {
  margin: 32px 0 !important;
  max-width: 100% !important;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content > iframe[style] {
    max-width: calc(8 * (100vw / 12) - 28px) !important;
  }
}

@media only screen and (min-width: 1168px) {
  .entry .entry-content > iframe[style] {
    max-width: calc(6 * (100vw / 12) - 28px) !important;
  }
}

.entry .entry-content .page-links a {
  margin: calc(0.5 * 1rem);
  text-decoration: none;
}

.entry .entry-content .wp-audio-shortcode {
  max-width: calc(100vw - (2 * 1rem));
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-audio-shortcode {
    max-width: calc(8 * (100vw / 12) - 28px);
  }
}

@media only screen and (min-width: 1168px) {
  .entry .entry-content .wp-audio-shortcode {
    max-width: calc(6 * (100vw / 12) - 28px);
  }
}

/* Author description */
.author-bio {
  margin: calc(2 * 1rem) 1rem 1rem;
}

@media only screen and (min-width: 768px) {
  .author-bio {
    max-width: calc(8 * (100vw / 12) - 28px);
  }
}

@media only screen and (min-width: 1168px) {
  .author-bio {
    max-width: calc(6 * (100vw / 12) - 28px);
  }
}

@media only screen and (min-width: 768px) {
  .author-bio {
    margin: calc(3 * 1rem) calc(10% + 60px);
  }
}

@media only screen and (min-width: 1168px) {
  .author-bio {
    margin: calc(3 * 1rem) calc(10% + 60px);
  }
}

.author-bio .author-title {
  display: inline;
}

.author-bio .author-title:before {
  background: #767676;
  content: "\020";
  display: block;
  height: 2px;
  margin: 1rem 0;
  width: 1em;
}

.author-bio .author-description {
  display: inline;
  color: #767676;
  font-size: 1.125em;
  line-height: 1.2;
}

.author-bio .author-description .author-link {
  display: inline-block;
}

.author-bio .author-description .author-link:hover {
  color: #005177;
  text-decoration: none;
}

/*--------------------------------------------------------------
## Comments
--------------------------------------------------------------*/
.comment-content a {
  word-wrap: break-word;
}

.bypostauthor {
  display: block;
}

.comments-area {
  margin: calc(2 * 1rem) 1rem;
  /* Add extra margin when the comments section is located immediately after the
	 * post itself (this happens on pages).
	 */
}

@media only screen and (min-width: 768px) {
  .comments-area {
    max-width: calc(8 * (100vw / 12) - 28px);
  }
}

@media only screen and (min-width: 1168px) {
  .comments-area {
    max-width: calc(6 * (100vw / 12) - 28px);
  }
}

@media only screen and (min-width: 768px) {
  .comments-area {
    margin: calc(3 * 1rem) calc(10% + 60px);
  }
}

.comments-area > * {
  margin-top: calc(2 * 1rem);
  margin-bottom: calc(2 * 1rem);
}

@media only screen and (min-width: 768px) {
  .comments-area > * {
    margin-top: calc(3 * 1rem);
    margin-bottom: calc(3 * 1rem);
  }
}

.entry + .comments-area {
  margin-top: calc(3 * 1rem);
}

@media only screen and (min-width: 768px) {
  .comments-area .comments-title-wrap {
    align-items: baseline;
    display: flex;
    justify-content: space-between;
  }
}

.comments-area .comments-title-wrap .comments-title {
  margin: 0;
}

.comments-area .comments-title-wrap .comments-title:before {
  background: #767676;
  content: "\020";
  display: block;
  height: 2px;
  margin: 1rem 0;
  width: 1em;
}

@media only screen and (min-width: 768px) {
  .comments-area .comments-title-wrap .comments-title {
    flex: 1 0 calc(3 * (100vw / 12));
  }
}

@media only screen and (min-width: 768px) {
  .comments-area .comments-title-wrap .discussion-meta {
    flex: 0 0 calc(2 * (100vw / 12));
    margin-left: 1rem;
  }
}

#comment {
  max-width: 100%;
  box-sizing: border-box;
}

#respond {
  position: relative;
}

#respond .comment-user-avatar {
  margin: 1rem 0 -1rem;
}

#respond .comment .comment-form {
  padding-left: 0;
}

#respond > small {
  display: block;
  font-size: 22px;
  position: absolute;
  left: calc(1rem + 100%);
  top: calc(-3.5 * 1rem);
  width: calc(100vw / 12);
}

#comments > .comments-title:last-child {
  display: none;
}

.comment-form-flex {
  display: flex;
  flex-direction: column;
}

.comment-form-flex .comments-title {
  display: none;
  margin: 0;
  order: 1;
}

.comment-form-flex #respond {
  order: 2;
}

.comment-form-flex #respond + .comments-title {
  display: block;
}

.comment-list {
  list-style: none;
  padding: 0;
}

.comment-list .children {
  margin: 0;
  padding: 0 0 0 1rem;
}

.comment-list > .comment:first-child {
  margin-top: 0;
}

.comment-list .pingback .comment-body,
.comment-list .trackback .comment-body {
  color: #767676;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  font-size: 0.71111em;
  font-weight: 500;
  margin-top: 1rem;
  margin-bottom: 1rem;
}

.comment-list .pingback .comment-body a:not(.comment-edit-link),
.comment-list .trackback .comment-body a:not(.comment-edit-link) {
  font-weight: bold;
  font-size: 19.55556px;
  line-height: 1.5;
  padding-right: 0.5rem;
  display: block;
}

.comment-list .pingback .comment-body .comment-edit-link,
.comment-list .trackback .comment-body .comment-edit-link {
  color: #767676;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  font-weight: 500;
}

#respond + .comment-reply {
  display: none;
}

.comment-reply .comment-reply-link {
  display: inline-block;
}

.comment {
  list-style: none;
  position: relative;
}

@media only screen and (min-width: 768px) {
  .comment {
    padding-left: calc(.5 * (1rem + calc(100vw / 12 )));
  }
  .comment.depth-1,
  .comment .children {
    padding-left: 0;
  }
  .comment.depth-1 {
    margin-left: calc(3.25 * 1rem);
  }
}

.comment .comment-body {
  margin: calc(2 * 1rem) 0 0;
}

.comment .comment-meta {
  position: relative;
}

.comment .comment-author .avatar {
  float: left;
  margin-right: 1rem;
  position: relative;
}

@media only screen and (min-width: 768px) {
  .comment .comment-author .avatar {
    float: inherit;
    margin-right: inherit;
    position: absolute;
    top: 0;
    right: calc(100% + 1rem);
  }
}

.comment .comment-author .fn {
  position: relative;
  display: block;
}

.comment .comment-author .fn a {
  color: inherit;
}

.comment .comment-author .fn a:hover {
  color: #005177;
}

.comment .comment-author .post-author-badge {
  border-radius: 100%;
  display: block;
  height: 18px;
  position: absolute;
  background: #008fd3;
  right: calc(100% - 2.5rem);
  top: -3px;
  width: 18px;
}

@media only screen and (min-width: 768px) {
  .comment .comment-author .post-author-badge {
    right: calc(100% + 0.75rem);
  }
}

.comment .comment-author .post-author-badge svg {
  width: inherit;
  height: inherit;
  display: block;
  fill: white;
  transform: scale(0.875);
}

.comment .comment-metadata > a,
.comment .comment-metadata .comment-edit-link {
  display: inline;
  font-weight: 500;
  color: #767676;
  vertical-align: baseline;
}

.comment .comment-metadata > a time,
.comment .comment-metadata .comment-edit-link time {
  vertical-align: baseline;
}

.comment .comment-metadata > a:hover,
.comment .comment-metadata .comment-edit-link:hover {
  color: #005177;
  text-decoration: none;
}

.comment .comment-metadata > * {
  display: inline-block;
}

.comment .comment-metadata .edit-link-sep {
  color: #767676;
  margin: 0 0.2em;
  vertical-align: baseline;
}

.comment .comment-metadata .edit-link {
  color: #767676;
}

.comment .comment-metadata .edit-link svg {
  transform: scale(0.8);
  vertical-align: baseline;
  margin-right: 0.1em;
}

.comment .comment-metadata .comment-edit-link {
  position: relative;
  padding-left: 1rem;
  margin-left: -1rem;
  z-index: 1;
}

.comment .comment-metadata .comment-edit-link:hover {
  color: #0073aa;
}

.comment .comment-content {
  margin: 1rem 0;
}

@media only screen and (min-width: 1168px) {
  .comment .comment-content {
    padding-right: 1rem;
  }
}

.comment .comment-content > *:first-child {
  margin-top: 0;
}

.comment .comment-content > *:last-child {
  margin-bottom: 0;
}

.comment .comment-content blockquote {
  margin-left: 0;
}

.comment .comment-content a {
  text-decoration: underline;
}

.comment .comment-content a:hover {
  text-decoration: none;
}

.comment-reply-link,
#cancel-comment-reply-link {
  font-weight: 500;
}

.comment-reply-link:hover,
#cancel-comment-reply-link:hover {
  color: #005177;
}

.discussion-avatar-list {
  content: "";
  display: table;
  table-layout: fixed;
  margin: 0;
  padding: 0;
}

.discussion-avatar-list li {
  position: relative;
  list-style: none;
  margin: 0 -8px 0 0;
  padding: 0;
  float: left;
}

.discussion-avatar-list .comment-user-avatar img {
  height: calc(1.5 * 1rem);
  width: calc(1.5 * 1rem);
}

.discussion-meta .discussion-meta-info {
  margin: 0;
}

.discussion-meta .discussion-meta-info .svg-icon {
  vertical-align: middle;
  fill: currentColor;
  transform: scale(0.6) scaleX(-1) translateY(-0.1em);
  margin-left: -0.25rem;
}

.comment-form .comment-notes,
.comment-form label {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  font-size: 0.71111em;
  color: #767676;
}

@media only screen and (min-width: 768px) {
  .comment-form .comment-form-author,
  .comment-form .comment-form-email {
    width: calc(50% - 0.5rem);
    float: left;
  }
}

@media only screen and (min-width: 768px) {
  .comment-form .comment-form-email {
    margin-left: 1rem;
  }
}

.comment-form input[name="author"],
.comment-form input[name="email"],
.comment-form input[name="url"] {
  display: block;
  width: 100%;
}

/*--------------------------------------------------------------
## Archives
--------------------------------------------------------------*/
.archive .page-header,
.search .page-header,
.error404 .page-header {
  margin: 1rem 1rem calc(3 * 1rem);
}

@media only screen and (min-width: 768px) {
  .archive .page-header,
  .search .page-header,
  .error404 .page-header {
    margin: 0 calc(10% + 60px) calc(10% + 60px);
  }
}

.archive .page-header .page-title,
.search .page-header .page-title,
.error404 .page-header .page-title {
  color: #767676;
  display: inline;
  letter-spacing: normal;
}

.archive .page-header .page-title:before,
.search .page-header .page-title:before,
.error404 .page-header .page-title:before {
  display: none;
}

.archive .page-header .search-term,
.archive .page-header .page-description,
.search .page-header .search-term,
.search .page-header .page-description,
.error404 .page-header .search-term,
.error404 .page-header .page-description {
  display: inherit;
  clear: both;
}

.archive .page-header .search-term:after,
.archive .page-header .page-description:after,
.search .page-header .search-term:after,
.search .page-header .page-description:after,
.error404 .page-header .search-term:after,
.error404 .page-header .page-description:after {
  content: ".";
  font-weight: bold;
  color: #767676;
}

.archive .page-header .page-description {
  display: block;
  color: #111;
  font-size: 1em;
}

@media only screen and (min-width: 768px) {
  .hfeed .entry .entry-header {
    margin: calc(3 * 1rem) calc(10% + 60px) calc(1rem / 2);
  }
}

/* 404 & Not found */
.error-404.not-found .page-content,
.no-results.not-found .page-content {
  margin: calc(3 * 1rem) 1rem;
}

@media only screen and (min-width: 768px) {
  .error-404.not-found .page-content,
  .no-results.not-found .page-content {
    margin: calc(3 * 1rem) calc(10% + 60px) calc(1rem / 2);
  }
}

.error-404.not-found .search-submit,
.no-results.not-found .search-submit {
  vertical-align: middle;
  margin: 1rem 0;
}

.error-404.not-found .search-field,
.no-results.not-found .search-field {
  width: 100%;
}

/*--------------------------------------------------------------
## Footer
--------------------------------------------------------------*/
/* Site footer */
#colophon .widget-area,
#colophon .site-info {
  margin: calc(2 * 1rem) 1rem;
}

@media only screen and (min-width: 768px) {
  #colophon .widget-area,
  #colophon .site-info {
    margin: calc(3 * 1rem) calc(10% + 60px);
  }
}

#colophon .widget-column {
  display: flex;
  flex-wrap: wrap;
}

#colophon .widget-column .widget {
  width: 100%;
}

@media only screen and (min-width: 1168px) {
  #colophon .widget-column .widget {
    margin-right: calc(3 * 1rem);
    width: calc(50% - (3 * 1rem));
  }
}

#colophon .site-info {
  color: #767676;
}

#colophon .site-info a {
  color: inherit;
}

#colophon .site-info a:hover {
  text-decoration: none;
  color: #0073aa;
}

#colophon .site-info .imprint,
#colophon .site-info .privacy-policy-link {
  margin-right: 1rem;
}

/* Widgets */
.widget {
  margin: 0 0 1rem;
  /* Make sure select elements fit in widgets. */
}

.widget select {
  max-width: 100%;
}

.widget a {
  color: #0073aa;
}

.widget a:hover {
  color: #005177;
}

.widget_archive ul,
.widget_categories ul,
.widget_meta ul,
.widget_nav_menu ul,
.widget_pages ul,
.widget_recent_comments ul,
.widget_recent_entries ul,
.widget_rss ul {
  padding: 0;
  list-style: none;
}

.widget_archive ul li,
.widget_categories ul li,
.widget_meta ul li,
.widget_nav_menu ul li,
.widget_pages ul li,
.widget_recent_comments ul li,
.widget_recent_entries ul li,
.widget_rss ul li {
  color: #767676;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  font-size: calc(22px * 1.125);
  font-weight: 700;
  line-height: 1.2;
  margin-top: 0.5rem;
  margin-bottom: 0.5rem;
}

.widget_archive ul ul,
.widget_categories ul ul,
.widget_meta ul ul,
.widget_nav_menu ul ul,
.widget_pages ul ul,
.widget_recent_comments ul ul,
.widget_recent_entries ul ul,
.widget_rss ul ul {
  counter-reset: submenu;
}

.widget_archive ul ul > li > a::before,
.widget_categories ul ul > li > a::before,
.widget_meta ul ul > li > a::before,
.widget_nav_menu ul ul > li > a::before,
.widget_pages ul ul > li > a::before,
.widget_recent_comments ul ul > li > a::before,
.widget_recent_entries ul ul > li > a::before,
.widget_rss ul ul > li > a::before {
  font-family: "NonBreakingSpaceOverride", "Hoefler Text", "Baskerville Old Face", Garamond, "Times New Roman", serif;
  font-weight: normal;
  content: "– " counters(submenu, "– ", none);
  counter-increment: submenu;
}

.widget_tag_cloud .tagcloud {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  font-weight: 700;
}

.widget_search .search-field {
  width: 100%;
}

@media only screen and (min-width: 600px) {
  .widget_search .search-field {
    width: auto;
  }
}

.widget_search .search-submit {
  display: block;
  margin-top: 1rem;
}

.widget_calendar .calendar_wrap {
  text-align: center;
}

.widget_calendar .calendar_wrap table td,
.widget_calendar .calendar_wrap table th {
  border: none;
}

.widget_calendar .calendar_wrap a {
  text-decoration: underline;
}

/* Blocks */
/* !Block styles */
.entry .entry-content > *,
.entry .entry-summary > * {
  margin: 32px 0;
  max-width: 100%;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content > *,
  .entry .entry-summary > * {
    max-width: calc(8 * (100vw / 12) - 28px);
  }
}

@media only screen and (min-width: 1168px) {
  .entry .entry-content > *,
  .entry .entry-summary > * {
    max-width: calc(6 * (100vw / 12) - 28px);
  }
}

@media only screen and (min-width: 768px) {
  .entry .entry-content > *,
  .entry .entry-summary > * {
    margin: 32px 0;
  }
}

.entry .entry-content > * > *:first-child,
.entry .entry-summary > * > *:first-child {
  margin-top: 0;
}

.entry .entry-content > * > *:last-child,
.entry .entry-summary > * > *:last-child {
  margin-bottom: 0;
}

.entry .entry-content > *.alignwide,
.entry .entry-summary > *.alignwide {
  margin-left: auto;
  margin-right: auto;
  clear: both;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content > *.alignwide,
  .entry .entry-summary > *.alignwide {
    width: 100%;
    max-width: 100%;
  }
}

.entry .entry-content > *.alignfull,
.entry .entry-summary > *.alignfull {
  position: relative;
  left: -1rem;
  width: calc( 100% + (2 * 1rem));
  max-width: calc( 100% + (2 * 1rem));
  clear: both;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content > *.alignfull,
  .entry .entry-summary > *.alignfull {
    margin-top: calc(2 * 1rem);
    margin-bottom: calc(2 * 1rem);
    left: calc( -12.5% - 75px);
    width: calc( 125% + 150px);
    max-width: calc( 125% + 150px);
  }
}

.entry .entry-content > *.alignleft,
.entry .entry-summary > *.alignleft {
  /*rtl:ignore*/
  float: left;
  max-width: calc(5 * (100vw / 12));
  margin-top: 0;
  margin-left: 0;
  /*rtl:ignore*/
  margin-right: 1rem;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content > *.alignleft,
  .entry .entry-summary > *.alignleft {
    max-width: calc(4 * (100vw / 12));
    /*rtl:ignore*/
    margin-right: calc(2 * 1rem);
  }
}

.entry .entry-content > *.alignright,
.entry .entry-summary > *.alignright {
  /*rtl:ignore*/
  float: right;
  max-width: calc(5 * (100vw / 12));
  margin-top: 0;
  margin-right: 0;
  /*rtl:ignore*/
  margin-left: 1rem;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content > *.alignright,
  .entry .entry-summary > *.alignright {
    max-width: calc(4 * (100vw / 12));
    margin-right: 0;
    /*rtl:ignore*/
    margin-left: calc(2 * 1rem);
  }
}

.entry .entry-content > *.aligncenter,
.entry .entry-summary > *.aligncenter {
  margin-left: auto;
  margin-right: auto;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content > *.aligncenter,
  .entry .entry-summary > *.aligncenter {
    max-width: calc(8 * (100vw / 12) - 28px);
  }
}

@media only screen and (min-width: 1168px) {
  .entry .entry-content > *.aligncenter,
  .entry .entry-summary > *.aligncenter {
    max-width: calc(6 * (100vw / 12) - 28px);
  }
}

@media only screen and (min-width: 768px) {
  .entry .entry-content > *.aligncenter,
  .entry .entry-summary > *.aligncenter {
    margin-left: 0;
    margin-right: 0;
  }
}

/*
 * Unset nested content selector styles
 * - Prevents layout styles from cascading too deeply
 * - helps with plugin compatibility
 */
.entry .entry-content .entry-content,
.entry .entry-content .entry-summary,
.entry .entry-content .entry,
.entry .entry-summary .entry-content,
.entry .entry-summary .entry-summary,
.entry .entry-summary .entry {
  margin: inherit;
  max-width: inherit;
  padding: inherit;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .entry-content,
  .entry .entry-content .entry-summary,
  .entry .entry-content .entry,
  .entry .entry-summary .entry-content,
  .entry .entry-summary .entry-summary,
  .entry .entry-summary .entry {
    margin: inherit;
    max-width: inherit;
    padding: inherit;
  }
}

.entry .entry-content p.has-background {
  padding: 20px 30px;
}

.entry .entry-content .wp-block-audio {
  width: 100%;
}

.entry .entry-content .wp-block-audio audio {
  width: 100%;
}

.entry .entry-content .wp-block-audio.alignleft audio,
.entry .entry-content .wp-block-audio.alignright audio {
  max-width: 198px;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-audio.alignleft audio,
  .entry .entry-content .wp-block-audio.alignright audio {
    max-width: 384px;
  }
}

@media only screen and (min-width: 1379px) {
  .entry .entry-content .wp-block-audio.alignleft audio,
  .entry .entry-content .wp-block-audio.alignright audio {
    max-width: 385.44px;
  }
}

.entry .entry-content .wp-block-video video {
  width: 100%;
}

.entry .entry-content .wp-block-button .wp-block-button__link {
  transition: background 150ms ease-in-out;
  border: none;
  font-size: 0.88889em;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  line-height: 1.2;
  box-sizing: border-box;
  font-weight: bold;
  text-decoration: none;
  padding: 0.76rem 1rem;
  outline: none;
  outline: none;
}

.entry .entry-content .wp-block-button .wp-block-button__link:not(.has-background) {
  background-color: #0073aa;
}

.entry .entry-content .wp-block-button .wp-block-button__link:not(.has-text-color) {
  color: white;
}

.entry .entry-content .wp-block-button .wp-block-button__link:hover {
  color: white;
  background: #111;
  cursor: pointer;
}

.entry .entry-content .wp-block-button .wp-block-button__link:focus {
  color: white;
  background: #111;
  outline: thin dotted;
  outline-offset: -4px;
}

.entry .entry-content .wp-block-button:not(.is-style-squared) .wp-block-button__link {
  border-radius: 5px;
}

.entry .entry-content .wp-block-button.is-style-outline .wp-block-button__link,
.entry .entry-content .wp-block-button.is-style-outline .wp-block-button__link:focus,
.entry .entry-content .wp-block-button.is-style-outline .wp-block-button__link:active {
  transition: all 150ms ease-in-out;
  border-width: 2px;
  border-style: solid;
}

.entry .entry-content .wp-block-button.is-style-outline .wp-block-button__link:not(.has-background),
.entry .entry-content .wp-block-button.is-style-outline .wp-block-button__link:focus:not(.has-background),
.entry .entry-content .wp-block-button.is-style-outline .wp-block-button__link:active:not(.has-background) {
  background: transparent;
}

.entry .entry-content .wp-block-button.is-style-outline .wp-block-button__link:not(.has-text-color),
.entry .entry-content .wp-block-button.is-style-outline .wp-block-button__link:focus:not(.has-text-color),
.entry .entry-content .wp-block-button.is-style-outline .wp-block-button__link:active:not(.has-text-color) {
  color: #0073aa;
  border-color: currentColor;
}

.entry .entry-content .wp-block-button.is-style-outline .wp-block-button__link:hover {
  color: white;
  border-color: #111;
}

.entry .entry-content .wp-block-button.is-style-outline .wp-block-button__link:hover:not(.has-background) {
  color: #111;
}

.entry .entry-content .wp-block-archives,
.entry .entry-content .wp-block-categories,
.entry .entry-content .wp-block-latest-posts {
  padding: 0;
  list-style: none;
}

.entry .entry-content .wp-block-archives li,
.entry .entry-content .wp-block-categories li,
.entry .entry-content .wp-block-latest-posts li {
  color: #767676;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  font-size: calc(22px * 1.125);
  font-weight: bold;
  line-height: 1.2;
  padding-bottom: 0.75rem;
}

.entry .entry-content .wp-block-archives li.menu-item-has-children, .entry .entry-content .wp-block-archives li:last-child,
.entry .entry-content .wp-block-categories li.menu-item-has-children,
.entry .entry-content .wp-block-categories li:last-child,
.entry .entry-content .wp-block-latest-posts li.menu-item-has-children,
.entry .entry-content .wp-block-latest-posts li:last-child {
  padding-bottom: 0;
}

.entry .entry-content .wp-block-archives li a,
.entry .entry-content .wp-block-categories li a,
.entry .entry-content .wp-block-latest-posts li a {
  text-decoration: none;
}

.entry .entry-content .wp-block-archives.aligncenter,
.entry .entry-content .wp-block-categories.aligncenter {
  text-align: center;
}

.entry .entry-content .wp-block-categories ul {
  padding-top: 0.75rem;
}

.entry .entry-content .wp-block-categories li ul {
  list-style: none;
  padding-left: 0;
}

.entry .entry-content .wp-block-categories ul {
  counter-reset: submenu;
}

.entry .entry-content .wp-block-categories ul > li > a::before {
  font-family: "NonBreakingSpaceOverride", "Hoefler Text", "Baskerville Old Face", Garamond, "Times New Roman", serif;
  font-weight: normal;
  content: "– " counters(submenu, "– ", none);
  counter-increment: submenu;
}

.entry .entry-content .wp-block-latest-posts.is-grid li {
  border-top: 2px solid #ccc;
  padding-top: 1rem;
  margin-bottom: 2rem;
}

.entry .entry-content .wp-block-latest-posts.is-grid li a:after {
  content: '';
}

.entry .entry-content .wp-block-latest-posts.is-grid li:last-child {
  margin-bottom: auto;
}

.entry .entry-content .wp-block-latest-posts.is-grid li:last-child a:after {
  content: '';
}

.entry .entry-content .wp-block-preformatted {
  font-size: 0.71111em;
  line-height: 1.8;
  padding: 1rem;
}

.entry .entry-content .wp-block-verse {
  font-family: "NonBreakingSpaceOverride", "Hoefler Text", "Baskerville Old Face", Garamond, "Times New Roman", serif;
  font-size: 22px;
  line-height: 1.8;
}

.entry .entry-content .has-drop-cap:not(:focus):first-letter {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  font-size: 3.375em;
  line-height: 1;
  font-weight: bold;
  margin: 0 0.25em 0 0;
}

.entry .entry-content .wp-block-pullquote {
  border-color: transparent;
  border-width: 2px;
  padding: 1rem;
}

.entry .entry-content .wp-block-pullquote blockquote {
  color: #111;
  border: none;
  margin-top: calc(4 * 1rem);
  margin-bottom: calc(4.33 * 1rem);
  margin-right: 0;
  padding-left: 0;
}

.entry .entry-content .wp-block-pullquote p {
  font-size: 1.6875em;
  font-style: italic;
  line-height: 1.3;
  margin-bottom: 0.5em;
  margin-top: 0.5em;
}

.entry .entry-content .wp-block-pullquote p em {
  font-style: normal;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-pullquote p {
    font-size: 2.25em;
  }
}

.entry .entry-content .wp-block-pullquote cite {
  display: inline-block;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  line-height: 1.6;
  text-transform: none;
  color: #767676;
  /*
			 * This requires a rem-based font size calculation instead of our normal em-based one,
			 * because the cite tag sometimes gets wrapped in a p tag. This is equivalent to $font-size_xs.
			 */
  font-size: calc(1rem / (1.25 * 1.125));
}

.entry .entry-content .wp-block-pullquote.alignleft, .entry .entry-content .wp-block-pullquote.alignright {
  width: 100%;
  padding: 0;
}

.entry .entry-content .wp-block-pullquote.alignleft blockquote, .entry .entry-content .wp-block-pullquote.alignright blockquote {
  margin: 1rem 0;
  padding: 0;
  text-align: left;
  max-width: 100%;
}

.entry .entry-content .wp-block-pullquote.alignleft blockquote p:first-child, .entry .entry-content .wp-block-pullquote.alignright blockquote p:first-child {
  margin-top: 0;
}

.entry .entry-content .wp-block-pullquote.is-style-solid-color {
  background-color: #0073aa;
  padding-left: 0;
  padding-right: 0;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-pullquote.is-style-solid-color {
    padding-left: 10%;
    padding-right: 10%;
  }
}

.entry .entry-content .wp-block-pullquote.is-style-solid-color p {
  font-size: 1.6875em;
  line-height: 1.3;
  margin-bottom: 0.5em;
  margin-top: 0.5em;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-pullquote.is-style-solid-color p {
    font-size: 2.25em;
  }
}

.entry .entry-content .wp-block-pullquote.is-style-solid-color a {
  color: #fff;
}

.entry .entry-content .wp-block-pullquote.is-style-solid-color cite {
  color: inherit;
}

.entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote {
  max-width: 100%;
  color: #fff;
  padding-left: 0;
  margin-left: 1rem;
  margin-right: 1rem;
}

.entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote.has-text-color p,
.entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote.has-text-color a, .entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote.has-primary-color, .entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote.has-secondary-color, .entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote.has-dark-gray-color, .entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote.has-light-gray-color, .entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote.has-white-color {
  color: inherit;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote {
    margin-left: 0;
    margin-right: 0;
  }
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-pullquote.is-style-solid-color.alignright, .entry .entry-content .wp-block-pullquote.is-style-solid-color.alignleft {
    padding: 1rem calc(2 * 1rem);
  }
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-pullquote.is-style-solid-color.alignfull {
    padding-left: calc(10% + 58px + (2 * 1rem));
    padding-right: calc(10% + 58px + (2 * 1rem));
  }
}

.entry .entry-content .wp-block-quote:not(.is-large), .entry .entry-content .wp-block-quote:not(.is-style-large) {
  border-left: 2px solid #0073aa;
  padding-top: 0;
  padding-bottom: 0;
}

.entry .entry-content .wp-block-quote p {
  font-size: 1em;
  font-style: normal;
  line-height: 1.8;
}

.entry .entry-content .wp-block-quote cite {
  /*
			 * This requires a rem-based font size calculation instead of our normal em-based one,
			 * because the cite tag sometimes gets wrapped in a p tag. This is equivalent to $font-size_xs.
			 */
  font-size: calc(1rem / (1.25 * 1.125));
}

.entry .entry-content .wp-block-quote.is-large, .entry .entry-content .wp-block-quote.is-style-large {
  margin: 1rem 0;
  padding: 0;
  border-left: none;
}

.entry .entry-content .wp-block-quote.is-large p, .entry .entry-content .wp-block-quote.is-style-large p {
  font-size: 1.6875em;
  line-height: 1.4;
  font-style: italic;
}

.entry .entry-content .wp-block-quote.is-large cite,
.entry .entry-content .wp-block-quote.is-large footer, .entry .entry-content .wp-block-quote.is-style-large cite,
.entry .entry-content .wp-block-quote.is-style-large footer {
  /*
				 * This requires a rem-based font size calculation instead of our normal em-based one,
				 * because the cite tag sometimes gets wrapped in a p tag. This is equivalent to $font-size_xs.
				 */
  font-size: calc(1rem / (1.25 * 1.125));
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-quote.is-large, .entry .entry-content .wp-block-quote.is-style-large {
    margin: 1rem 0;
    padding: 1rem 0;
  }
  .entry .entry-content .wp-block-quote.is-large p, .entry .entry-content .wp-block-quote.is-style-large p {
    font-size: 1.6875em;
  }
}

.entry .entry-content .wp-block-image {
  max-width: 100%;
}

.entry .entry-content .wp-block-image img {
  display: block;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-image .aligncenter {
    max-width: calc(8 * (100vw / 12) - 28px);
  }
}

@media only screen and (min-width: 1168px) {
  .entry .entry-content .wp-block-image .aligncenter {
    max-width: calc(6 * (100vw / 12) - 28px);
  }
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-image .aligncenter {
    margin: 0;
    width: calc(8 * (100vw / 12) - 28px);
  }
  .entry .entry-content .wp-block-image .aligncenter img {
    margin: 0 auto;
  }
}

@media only screen and (min-width: 1168px) {
  .entry .entry-content .wp-block-image .aligncenter {
    width: calc(6 * (100vw / 12) - 28px);
  }
  .entry .entry-content .wp-block-image .aligncenter img {
    margin: 0 auto;
  }
}

.entry .entry-content .wp-block-image.alignfull img {
  width: 100vw;
  max-width: calc( 100% + (2 * 1rem));
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-image.alignfull img {
    max-width: calc( 125% + 150px);
    margin-left: auto;
    margin-right: auto;
  }
}

.entry .entry-content .wp-block-cover-image,
.entry .entry-content .wp-block-cover {
  position: relative;
  min-height: 430px;
  padding: 1rem;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-cover-image,
  .entry .entry-content .wp-block-cover {
    padding: 1rem 10%;
  }
}

.entry .entry-content .wp-block-cover-image .wp-block-cover-image-text,
.entry .entry-content .wp-block-cover-image .wp-block-cover-text,
.entry .entry-content .wp-block-cover-image h2,
.entry .entry-content .wp-block-cover .wp-block-cover-image-text,
.entry .entry-content .wp-block-cover .wp-block-cover-text,
.entry .entry-content .wp-block-cover h2 {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  font-size: 1.6875em;
  font-weight: bold;
  line-height: 1.25;
  padding: 0;
  color: #fff;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-cover-image .wp-block-cover-image-text,
  .entry .entry-content .wp-block-cover-image .wp-block-cover-text,
  .entry .entry-content .wp-block-cover-image h2,
  .entry .entry-content .wp-block-cover .wp-block-cover-image-text,
  .entry .entry-content .wp-block-cover .wp-block-cover-text,
  .entry .entry-content .wp-block-cover h2 {
    font-size: 2.25em;
    max-width: 100%;
  }
}

.entry .entry-content .wp-block-cover-image.alignleft, .entry .entry-content .wp-block-cover-image.alignright,
.entry .entry-content .wp-block-cover.alignleft,
.entry .entry-content .wp-block-cover.alignright {
  width: 100%;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-cover-image.alignleft, .entry .entry-content .wp-block-cover-image.alignright,
  .entry .entry-content .wp-block-cover.alignleft,
  .entry .entry-content .wp-block-cover.alignright {
    padding: 1rem calc(2 * 1rem);
  }
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-cover-image.alignfull .wp-block-cover-image-text,
  .entry .entry-content .wp-block-cover-image.alignfull .wp-block-cover-text,
  .entry .entry-content .wp-block-cover-image.alignfull h2,
  .entry .entry-content .wp-block-cover.alignfull .wp-block-cover-image-text,
  .entry .entry-content .wp-block-cover.alignfull .wp-block-cover-text,
  .entry .entry-content .wp-block-cover.alignfull h2 {
    max-width: calc(8 * (100vw / 12) - 28px);
  }
}

@media only screen and (min-width: 1168px) {
  .entry .entry-content .wp-block-cover-image.alignfull .wp-block-cover-image-text,
  .entry .entry-content .wp-block-cover-image.alignfull .wp-block-cover-text,
  .entry .entry-content .wp-block-cover-image.alignfull h2,
  .entry .entry-content .wp-block-cover.alignfull .wp-block-cover-image-text,
  .entry .entry-content .wp-block-cover.alignfull .wp-block-cover-text,
  .entry .entry-content .wp-block-cover.alignfull h2 {
    max-width: calc(6 * (100vw / 12) - 28px);
  }
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-cover-image.alignfull,
  .entry .entry-content .wp-block-cover.alignfull {
    padding-left: calc(10% + 58px + (2 * 1rem));
    padding-right: calc(10% + 58px + (2 * 1rem));
  }
  .entry .entry-content .wp-block-cover-image.alignfull .wp-block-cover-image-text,
  .entry .entry-content .wp-block-cover-image.alignfull .wp-block-cover-text,
  .entry .entry-content .wp-block-cover-image.alignfull h2,
  .entry .entry-content .wp-block-cover.alignfull .wp-block-cover-image-text,
  .entry .entry-content .wp-block-cover.alignfull .wp-block-cover-text,
  .entry .entry-content .wp-block-cover.alignfull h2 {
    padding: 0;
  }
}

.entry .entry-content .wp-block-gallery {
  list-style-type: none;
  padding-left: 0;
}

.entry .entry-content .wp-block-gallery .blocks-gallery-image:last-child,
.entry .entry-content .wp-block-gallery .blocks-gallery-item:last-child {
  margin-bottom: 16px;
}

.entry .entry-content .wp-block-gallery figcaption a {
  color: #fff;
}

.entry .entry-content .wp-block-audio figcaption,
.entry .entry-content .wp-block-video figcaption,
.entry .entry-content .wp-block-image figcaption,
.entry .entry-content .wp-block-gallery .blocks-gallery-image figcaption,
.entry .entry-content .wp-block-gallery .blocks-gallery-item figcaption {
  font-size: 0.71111em;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  line-height: 1.6;
  margin: 0;
  padding: 0.5rem;
  text-align: center;
}

.entry .entry-content .wp-block-separator,
.entry .entry-content hr {
  background-color: #767676;
  border: 0;
  height: 2px;
  margin-bottom: 2rem;
  margin-top: 2rem;
  max-width: 2.25em;
  text-align: left;
  /* Remove duplicate rule-line when a separator
		 * is followed by an H1, or H2 */
}

.entry .entry-content .wp-block-separator.is-style-wide,
.entry .entry-content hr.is-style-wide {
  max-width: 100%;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-separator.is-style-wide,
  .entry .entry-content hr.is-style-wide {
    max-width: calc(8 * (100vw / 12) - 28px);
  }
}

@media only screen and (min-width: 1168px) {
  .entry .entry-content .wp-block-separator.is-style-wide,
  .entry .entry-content hr.is-style-wide {
    max-width: calc(6 * (100vw / 12) - 28px);
  }
}

.entry .entry-content .wp-block-separator.is-style-dots,
.entry .entry-content hr.is-style-dots {
  max-width: 100%;
  background-color: inherit;
  border: inherit;
  height: inherit;
  text-align: center;
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-separator.is-style-dots,
  .entry .entry-content hr.is-style-dots {
    max-width: calc(8 * (100vw / 12) - 28px);
  }
}

@media only screen and (min-width: 1168px) {
  .entry .entry-content .wp-block-separator.is-style-dots,
  .entry .entry-content hr.is-style-dots {
    max-width: calc(6 * (100vw / 12) - 28px);
  }
}

.entry .entry-content .wp-block-separator.is-style-dots:before,
.entry .entry-content hr.is-style-dots:before {
  color: #767676;
  font-size: 1.6875em;
  letter-spacing: 0.88889em;
  padding-left: 0.88889em;
}

.entry .entry-content .wp-block-separator + h1:before,
.entry .entry-content .wp-block-separator + h2:before,
.entry .entry-content hr + h1:before,
.entry .entry-content hr + h2:before {
  display: none;
}

.entry .entry-content .wp-block-embed-twitter {
  word-break: break-word;
}

.entry .entry-content .wp-block-table th,
.entry .entry-content .wp-block-table td {
  border-color: #767676;
}

.entry .entry-content .wp-block-file {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
}

.entry .entry-content .wp-block-file .wp-block-file__button {
  display: table;
  transition: background 150ms ease-in-out;
  border: none;
  border-radius: 5px;
  background: #0073aa;
  font-size: 22px;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  line-height: 1.2;
  text-decoration: none;
  font-weight: bold;
  padding: 0.75rem 1rem;
  color: #fff;
  margin-left: 0;
  margin-top: calc(0.75 * 1rem);
}

@media only screen and (min-width: 1168px) {
  .entry .entry-content .wp-block-file .wp-block-file__button {
    font-size: 22px;
    padding: 0.875rem 1.5rem;
  }
}

.entry .entry-content .wp-block-file .wp-block-file__button:hover {
  background: #111;
  cursor: pointer;
}

.entry .entry-content .wp-block-file .wp-block-file__button:focus {
  background: #111;
  outline: thin dotted;
  outline-offset: -4px;
}

.entry .entry-content .wp-block-code {
  border-radius: 0;
}

.entry .entry-content .wp-block-code code {
  font-size: 1.125em;
  white-space: pre-wrap;
  word-break: break-word;
}

.entry .entry-content .wp-block-columns.alignfull {
  padding-left: 1rem;
  padding-right: 1rem;
}

@media only screen and (min-width: 600px) {
  .entry .entry-content .wp-block-columns {
    flex-wrap: nowrap;
  }
}

@media only screen and (min-width: 768px) {
  .entry .entry-content .wp-block-columns .wp-block-column > *:first-child {
    margin-top: 0;
  }
  .entry .entry-content .wp-block-columns .wp-block-column > *:last-child {
    margin-bottom: 0;
  }
  .entry .entry-content .wp-block-columns[class*='has-'] > * {
    margin-right: 1rem;
  }
  .entry .entry-content .wp-block-columns[class*='has-'] > *:last-child {
    margin-right: 0;
  }
  .entry .entry-content .wp-block-columns.alignfull,
  .entry .entry-content .wp-block-columns.alignfull .wp-block-column {
    padding-left: calc(2 * 1rem);
    padding-right: calc(2 * 1rem);
  }
}

.entry .entry-content .wp-block-latest-comments .wp-block-latest-comments__comment-meta {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  font-weight: bold;
}

.entry .entry-content .wp-block-latest-comments .wp-block-latest-comments__comment-meta .wp-block-latest-comments__comment-date {
  font-weight: normal;
}

.entry .entry-content .wp-block-latest-comments .wp-block-latest-comments__comment,
.entry .entry-content .wp-block-latest-comments .wp-block-latest-comments__comment-date,
.entry .entry-content .wp-block-latest-comments .wp-block-latest-comments__comment-excerpt p {
  font-size: inherit;
}

.entry .entry-content .wp-block-latest-comments.has-dates .wp-block-latest-comments__comment-date {
  font-size: 0.71111em;
}

.entry .entry-content .has-small-font-size {
  font-size: 0.88889em;
}

.entry .entry-content .has-normal-font-size {
  font-size: 1.125em;
}

.entry .entry-content .has-large-font-size {
  font-size: 1.6875em;
}

.entry .entry-content .has-huge-font-size {
  font-size: 2.25em;
}

.entry .entry-content .has-primary-background-color,
.entry .entry-content .has-secondary-background-color,
.entry .entry-content .has-dark-gray-background-color,
.entry .entry-content .has-light-gray-background-color {
  color: #fff;
}

.entry .entry-content .has-primary-background-color p,
.entry .entry-content .has-primary-background-color h1,
.entry .entry-content .has-primary-background-color h2,
.entry .entry-content .has-primary-background-color h3,
.entry .entry-content .has-primary-background-color h4,
.entry .entry-content .has-primary-background-color h5,
.entry .entry-content .has-primary-background-color h6,
.entry .entry-content .has-primary-background-color a,
.entry .entry-content .has-secondary-background-color p,
.entry .entry-content .has-secondary-background-color h1,
.entry .entry-content .has-secondary-background-color h2,
.entry .entry-content .has-secondary-background-color h3,
.entry .entry-content .has-secondary-background-color h4,
.entry .entry-content .has-secondary-background-color h5,
.entry .entry-content .has-secondary-background-color h6,
.entry .entry-content .has-secondary-background-color a,
.entry .entry-content .has-dark-gray-background-color p,
.entry .entry-content .has-dark-gray-background-color h1,
.entry .entry-content .has-dark-gray-background-color h2,
.entry .entry-content .has-dark-gray-background-color h3,
.entry .entry-content .has-dark-gray-background-color h4,
.entry .entry-content .has-dark-gray-background-color h5,
.entry .entry-content .has-dark-gray-background-color h6,
.entry .entry-content .has-dark-gray-background-color a,
.entry .entry-content .has-light-gray-background-color p,
.entry .entry-content .has-light-gray-background-color h1,
.entry .entry-content .has-light-gray-background-color h2,
.entry .entry-content .has-light-gray-background-color h3,
.entry .entry-content .has-light-gray-background-color h4,
.entry .entry-content .has-light-gray-background-color h5,
.entry .entry-content .has-light-gray-background-color h6,
.entry .entry-content .has-light-gray-background-color a {
  color: #fff;
}

.entry .entry-content .has-white-background-color {
  color: #111;
}

.entry .entry-content .has-white-background-color p,
.entry .entry-content .has-white-background-color h1,
.entry .entry-content .has-white-background-color h2,
.entry .entry-content .has-white-background-color h3,
.entry .entry-content .has-white-background-color h4,
.entry .entry-content .has-white-background-color h5,
.entry .entry-content .has-white-background-color h6,
.entry .entry-content .has-white-background-color a {
  color: #111;
}

.entry .entry-content .has-primary-background-color,
.entry .entry-content .wp-block-pullquote.is-style-solid-color.has-primary-background-color {
  background-color: #0073aa;
}

.entry .entry-content .has-secondary-background-color,
.entry .entry-content .wp-block-pullquote.is-style-solid-color.has-secondary-background-color {
  background-color: #005177;
}

.entry .entry-content .has-dark-gray-background-color,
.entry .entry-content .wp-block-pullquote.is-style-solid-color.has-dark-gray-background-color {
  background-color: #111;
}

.entry .entry-content .has-light-gray-background-color,
.entry .entry-content .wp-block-pullquote.is-style-solid-color.has-light-gray-background-color {
  background-color: #767676;
}

.entry .entry-content .has-white-background-color,
.entry .entry-content .wp-block-pullquote.is-style-solid-color.has-white-background-color {
  background-color: #FFF;
}

.entry .entry-content .has-primary-color,
.entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote.has-primary-color,
.entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote.has-primary-color p {
  color: #0073aa;
}

.entry .entry-content .has-secondary-color,
.entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote.has-secondary-color,
.entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote.has-secondary-color p {
  color: #005177;
}

.entry .entry-content .has-dark-gray-color,
.entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote.has-dark-gray-color,
.entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote.has-dark-gray-color p {
  color: #111;
}

.entry .entry-content .has-light-gray-color,
.entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote.has-light-gray-color,
.entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote.has-light-gray-color p {
  color: #767676;
}

.entry .entry-content .has-white-color,
.entry .entry-content .wp-block-pullquote.is-style-solid-color blockquote.has-white-color {
  color: #FFF;
}

/* Media */
.page-content .wp-smiley,
.entry-content .wp-smiley,
.comment-content .wp-smiley {
  border: none;
  margin-bottom: 0;
  margin-top: 0;
  padding: 0;
}

embed,
iframe,
object {
  max-width: 100%;
}

.custom-logo-link {
  display: inline-block;
}

.avatar {
  border-radius: 100%;
  display: block;
  height: calc(2.25 * 1rem);
  min-height: inherit;
  width: calc(2.25 * 1rem);
}

svg {
  transition: fill 120ms ease-in-out;
  fill: currentColor;
}

/*--------------------------------------------------------------
## Captions
--------------------------------------------------------------*/
.wp-caption {
  margin-bottom: calc(1.5 * 1rem);
}

@media only screen and (min-width: 768px) {
  .wp-caption.aligncenter {
    position: relative;
    left: calc( calc(8 * (100vw / 12) - 28px) / 2);
    transform: translateX(-50%);
  }
}

@media only screen and (min-width: 1168px) {
  .wp-caption.aligncenter {
    left: calc( calc(6 * (100vw / 12) - 28px) / 2);
  }
}

.wp-caption img[class*="wp-image-"] {
  display: block;
  margin-left: auto;
  margin-right: auto;
}

.wp-caption-text {
  color: #767676;
  font-size: 0.71111em;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  line-height: 1.6;
  margin: 0;
  padding: 0.5rem;
  text-align: center;
}

/*--------------------------------------------------------------
## Galleries
--------------------------------------------------------------*/
.gallery {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  margin-bottom: calc(1.5 * 1rem);
}

.gallery-item {
  display: inline-block;
  margin-right: 16px;
  margin-bottom: 16px;
  text-align: center;
  vertical-align: top;
  width: 100%;
}

.gallery-columns-2 .gallery-item {
  max-width: calc((100% - 16px * 1) / 2);
}

.gallery-columns-2 .gallery-item:nth-of-type(2n+2) {
  margin-right: 0;
}

.gallery-columns-3 .gallery-item {
  max-width: calc((100% - 16px * 2) / 3);
}

.gallery-columns-3 .gallery-item:nth-of-type(3n+3) {
  margin-right: 0;
}

.gallery-columns-4 .gallery-item {
  max-width: calc((100% - 16px * 3) / 4);
}

.gallery-columns-4 .gallery-item:nth-of-type(4n+4) {
  margin-right: 0;
}

.gallery-columns-5 .gallery-item {
  max-width: calc((100% - 16px * 4) / 5);
}

.gallery-columns-5 .gallery-item:nth-of-type(5n+5) {
  margin-right: 0;
}

.gallery-columns-6 .gallery-item {
  max-width: calc((100% - 16px * 5) / 6);
}

.gallery-columns-6 .gallery-item:nth-of-type(6n+6) {
  margin-right: 0;
}

.gallery-columns-7 .gallery-item {
  max-width: calc((100% - 16px * 6) / 7);
}

.gallery-columns-7 .gallery-item:nth-of-type(7n+7) {
  margin-right: 0;
}

.gallery-columns-8 .gallery-item {
  max-width: calc((100% - 16px * 7) / 8);
}

.gallery-columns-8 .gallery-item:nth-of-type(8n+8) {
  margin-right: 0;
}

.gallery-columns-9 .gallery-item {
  max-width: calc((100% - 16px * 8) / 9);
}

.gallery-columns-9 .gallery-item:nth-of-type(9n+9) {
  margin-right: 0;
}

.gallery-item:last-of-type {
  padding-right: 0;
}

.gallery-caption {
  display: block;
  font-size: 0.71111em;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  line-height: 1.6;
  margin: 0;
  padding: 0.5rem;
}

.gallery-item > div > a {
  display: block;
  line-height: 0;
  box-shadow: 0 0 0 0 transparent;
}

.gallery-item > div > a:focus {
  box-shadow: 0 0 0 2px #0073aa;
}
