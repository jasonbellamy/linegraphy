# Deprecated
This project is deprecated and only remains for historical reasons.

---

# Linegraphy
A typographic SASS extension to help you easily maintain vertical-rhythm in your projects. 

## Installation
* Copy sass/_linegraphy.sass into your project's SASS directory
* Import the file into your project `@import linegraphy`

## Mixins

### font-size(*$font-size*)
 Converts a static font-size to relative units

* **$font-size:** size of the elements font in px

Example:

```sass
p
  @include font-size(16px)
```

Generates:

```css
p {
  font-size: 1em;
}
```
***********************************************************************************

### line-height(*$font-size*, *$custom-line-height*)
 Calculates the elements line-height

* **$font-size:** size of the elements font in px
* **$custom-line-height:** (optional)

Example:

```sass
h1
  @include line-height(48px, 48px)
p
  @include line-height(16px)
```

Generates:

```css
h1 {
  line-height: 1em;
}
p {
  font-size: 1.5em;
}
```
***********************************************************************************

### line-before(*$font-size*, *$property*, *$lines*)
 Creates rhythmed whitepace before an element

* **$font-size:** size of the elements font in px
* **$property:** padding or margin
* **$lines:** integer (optional) multiplies the whitespace by nth

Example:

```sass
p
  @include line-before(16px, margin)
```

Generates:

```css
p {
  margin-top: 1.5em;
}
```
***********************************************************************************

### line-after(*$font-size*, *$property*, *$lines*)
 Creates rhythmed whitepace after an element

* **$font-size:** size of the elements font in px
* **$property:** padding or margin
* **$lines:** integer (optional) multiplies the whitespace by nth

Example:

```sass
p
  @include line-after(16px, margin, 2)
```

Generates:

```css
p {
  margin-bottom: 3em;
}
```
***********************************************************************************

### line-both(*$font-size*, *$property*, *$lines*)
 Calculates the rhythmed whitepace for an element and divides it up before AND after an element

* **$font-size:** size of the elements font in px
* **$property:** padding or margin
* **$lines:** integer (optional) multiplies the whitespace by nth

Example:

```sass
p
  @include line-both(16px, margin)
```

Generates:

```css
p {
  margin-top: 0.75em;
  margin-bottom: 0.75em;
}
```
***********************************************************************************

### line-border-before(*$font-size*, *$property*, *$border-size*, *$border-style*, *$border-color*)
 Creates rhythmed whitespace before an element and adds a "border-top" to it

* **$font-size:** size of the elements font in px
* **$property:** padding or margin
* **$border-size:** border size in px
* **$border-style:** solid, dashed, dotted, etc
* **$border-color:** hex, rgb, rgba, hsla

Example:

```sass
p
  @include line-border-before(16px, padding, 1px, solid, #000)
```

Generates:

```css
p {
  border-top: 1px solid #000
  padding-top: 1.5em;
}
```
***********************************************************************************

### line-border-after(*$font-size*, *$property*, *$border-size*, *$border-style*, *$border-color*)
 Creates rhythmed whitespace after an element and adds a "border-bottom" to it

* **$font-size:** size of the elements font in px
* **$property:** padding or margin
* **$border-size:** border size in px
* **$border-style:** solid, dashed, dotted, etc
* **$border-color:** hex, rgb, rgba, hsla

Example:

```sass
p
  @include line-border-after(16px, padding, 1px, solid, #000)
```

Generates:

```css
p {
  border-bottom: 1px solid #000
  padding-bottom: 1.5em;
}
```
***********************************************************************************

### line-fixed-before(*$height*, *$property*, *$lines*)
 Creates rhythmed whitespace before a fixed height element

* **$height:** height of the element in px
* **$property:** padding or margin
* **$lines:** integer (optional) multiplies the whitespace by nth

Example:

```sass
img
  @include line-fixed-before(16px, padding, 1) 
  display: block
  height: 100px
  width: 100px
```

Generates:

```css
img {
  padding-top: 1.25em;
  display: block;
  height: 100px;
  width: 100px;
}
```
***********************************************************************************

### line-fixed-after(*$height*, *$property*, *$lines*)
 Creates rhythmed whitespace after a fixed height element

* **$height:** height of the element in px
* **$property:** padding or margin
* **$lines:** integer (optional) multiplies the whitespace by nth

Example:

```sass
img
  @include line-fixed-after(16px, padding, 1) 
  display: block
  height: 100px
  width: 100px
```

Generates:

```css
img {
  padding-bottom: 1.25em;
  display: block;
  height: 100px;
  width: 100px;
}
```
***********************************************************************************

### line-fixed-both(*$height*, *$property*, *$lines*)
 Calculates the rhythmed whitepace for a fixed height element and divides it up before AND after an element

* **$height:** height of the element in px
* **$property:** padding or margin
* **$lines:** integer (optional) multiplies the whitespace by nth

Example:

```sass
img
  @include line-fixed-both(16px, padding, 1) 
  display: block
  height: 100px
  width: 100px
```

Generates:

```css
img {
  padding-top: 0.625em;
  padding-bottom: 0.625em;
  display: block;
  height: 100px;
  width: 100px;
}
```
***********************************************************************************


## Functions

### static-to-relative(*$target*, *$context*)
 Converts a static unit to a relative unit

* *$target:* px  the static unit you want a relative unit from
* *$context:* px the targets parent unit

Example:

```sass
p
 font-size: static-to-relative(16px)
```

Generates:

```css
p {
  font-size: 1em;
}
```
***********************************************************************************

### relative-to-static(*$context*)
 Converts a static unit to a relative unit

* *context:* em  the relative unit you want a static unit from

Example:

```sass
p
 font-size: relative-to-static(1em)
```

Generates:

```css
p {
  font-size: 16px;
}
```
***********************************************************************************

### remainder(*$height*)
 Takes an elements height and returns the difference between it and the next multiple of the baseline

* *context:* em  the relative unit you want a static unit from

Example:

```sass
img
 height: 100px
 margin-bottom: remainder(100px)
```

Generates:

```css
img {
  height: 100px;
  /* 24px (line-height) * 5 = 120px - 100px (img height) = 20px */
  margin-bottom: 20px;
}
```
***********************************************************************************

### License

Copyright (c) 2011 [Jason Bellamy](http://www.jasonbellamy.com/)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
