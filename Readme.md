WMD: The Wysiwym Markdown Editor
================================

Introduction
------------

WMD is a JavaScript based code editor for the [Markdown](http://daringfireball.net/projects/markdown/) formatting language.  It includes a Markdown interpreter – Showdown – for live preview and output of the Markdown generated HTML.

The goal of this project is to add support for simple input elements and forms to Markdown. This code is forked from [Jim Brikman's fork](https://github.com/brikis98/wmd) of WMD, which, in turn, was forked from a number of other sources. All credit goes to the respective authors.

I (maleldil) forked this from brikis98 to play around and see how difficult it would be to add the functionality he has defined here.  All the documentation provided is his, and all credit for the ideas are his as well.

Major Changes from ChiperSoft Library Revision
-------------

### Text fields

    name = ___

```html
<label for="name">Name:</label> 
<input type="text" id="name" name="name" size="20"/>
```

Or:

    name = ___[50]
	
```html
<label for="name">Name:</label> 
<input type="text" id="name" name="name" size="50"/>
```

Exactly 3 underscores will be matched.  Any more will be handled as standard underline directives.  Default input size is 20.


### Radio buttons

    sex = (x) male () female

```html
<label>Sex:</label> 
<input type="radio" name="sex" id="male" value="male" checked="checked"/><label for="male">Male</label>
<input type="radio" name="sex" id="female" value="female"/><label for="female">Female</label>  
```

### Check boxes

    phones = [] Android [x] iPhone [x] Blackberry

```html
<label>Phones:</label> 
<input type="checkbox" name="phones" id="Android" value="Android"/><label for="Android">Android</label>
<input type="checkbox" name="phones" id="iPhone" value="iPhone" checked="checked"/><label for="iPhone">iPhone</label>
<input type="checkbox" name="phones" id="Blackberry" value="Blackberry" checked="checked"/><label for="Blackberry">Blackberry</label>
```

### Drop down

    city = {BOS, SFO, (NYC)}

```html
<label for="city">City:</label>
<select id="city" name="city">
  <option value="BOS">BOS</option>
  <option value="SFO">SFO</option>
  <option value="NYC" selected="selected">NYC</option>
</select>
```

Or with user-friendly labels:

    city = {BOS -> Boston, SFO -> San Francisco, (NYC -> New York City)}

```html
<label for="city">City:</label>
<select id="city" name="city">
  <option value="BOS">Boston</option>
  <option value="SFO">San Francisco</option>
  <option value="NYC" selected="selected">New York City</option>
</select>
```

Or both:

    city = {BOS, SFO, (NYC -> New York City)}
	
```html
<label for="city">City:</label>
<select id="city" name="city">
  <option value="BOS">BOS</option>
  <option value="SFO">SFO</option>
  <option value="NYC" selected="selected">New York City</option>
</select>
```

### Required fields

    zip code* = ___

```html
<label for="zip-code" class="required-label">Zip code*:</label>
<input type="text" name="zip-code" id="zip-code" size="20" class="required-input"/>
```

    zip code* = ___[50]

```html
<label for="zip-code" class="required-label">Zip code*:</label>
<input type="text" name="zip-code" id="zip-code" size="50" class="required-input"/>
```


How to use
----------

```html
<html>
  <head>
    <title>WMD Example</title>        
    <link rel="stylesheet" type="text/css" href="wmd.css"/>
    <script type="text/javascript" src="wmd.js"></script>
    <script type="text/javascript" src="showdown.js"></script>
  </head>
  <body>
    <h1>WMD Example</h1>
    <div>
      <div id="notes-button-bar"></div>
      <textarea id="notes" name="copy"></textarea>
      <div id="notes-preview"></div>
      <input type="text" name="copy_html" value="" id="copy_html"/>
    </div>
    <script type="text/javascript">
      setup_wmd({
        input: "notes",
        button_bar: "notes-button-bar",
        preview: "notes-preview",
        output: "copy_html"
      });
    </script>
  </body>
</html>
```

Status
-------

All documented features have been implemented and tested with basic use cases.  It could use more thorough testing, though.

License
-------

WMD Editor is licensed under [MIT License](http://github.com/chipersoft/wmd/raw/master/License.txt).


