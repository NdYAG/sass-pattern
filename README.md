# sass-pattern

A list of mixins and placeholders to ease you from of the pain of repeating same code and help you focus on necessary styling.

* [Install](#install)
* Styling
    * [Arrange](#arrange)
    * [Button](#button)
    * [Typography](#typography)
    * [Retina](#retina)
    * [Shape](#shape)
    * [Reset](#reset)

## Install

`bower install sass-pattern`

`npm install sass-pattern`

```scss
@import "sass-pattern";
```


## Arrange

These three objects helps you achieve the most common design layouts.

```scss
// API:
@mixin Media($left, $right, $gutter: 0, $atRoot: true)

@mixin Flag($left, $right, $align: middle, $gutter: 0, $atRoot: true)

@mixin Balance($left, $right, $height: 0, $atRoot: true)
```

### Media Object

> The media object is an image to the left, with descriptive content to the right.

via http://www.stubbornella.org/content/2010/06/25/the-media-object-saves-hundreds-of-lines-of-code/

Douban Community:

![media.png](https://qiita-image-store.s3.amazonaws.com/0/19886/22b0477f-79b4-a02e-0adc-1d1b2eab5ffa.png "media.png")

```html
<div class="status">
    <div class="status-author"></div>
    <div class="status-content"></div>
</div>
```

```scss
.status {
    @include Media(
        $left: '.status-author',
        $right: '.status-content',
        $gutter: 10px
    );
}
```

### Flag Object

> ... Where the flag object differs, however, is its ability to vertically align the image and text to the tops, middles or bottoms of each other.

via http://csswizardry.com/2013/05/the-flag-object/

Part of user's profile in Douban:

![flag.png](https://qiita-image-store.s3.amazonaws.com/0/19886/6df4e728-2a60-20b7-fab3-0a7692a5778d.png "flag.png")

```html
<div class="collection">
    <span class="collection-status"></span>
    <ul class="collection-items"></div>
</div>
```

```sass
.collection {
    @include Flag(
        $left: '.collection-status',
        $right: '.collection-items',
        $gutter: 5px
    );
}
```

### Balance Object

This time, the two elements being arranged are 'floated', one left, one right. But you still have the control of their vertical alignment.

The header of a story in Douban Music:

![balance.png](https://qiita-image-store.s3.amazonaws.com/0/19886/337e09a3-8a47-d979-927f-d02b9c390d7f.png "balance.png")

```html
<header class="event-hd">
    <h1 class="event-title"></h1>
    <div class="event-share"></div>
</header>
```

```scss
.event-hd {
    @include Balance(
        $left: '.event-title',
        $right: '.event-share'
    );
}
```

## Button

```scss
// API
@mixin Button {
    @content;
}
%Button
```

Create a button:

```scss
.button-primary {
    @include Button {
        border: 1px solid #ccc;
        background: #fff;
        padding: 1rem;
        font-size: 1.5rem;
    };
}
```

Style a button without worrying about cross-device style differences.

```html
<button class="button-login">Login</button>
<a class="button-login">Login</a>
<span class="button-login">Login</span>
```

```scss
.button-login {
    @extend %Button;
    
    border: 1px solid darken($blue, 6%);
    background: linear-gradient(top, lighten($blue, 6%) 0%, $blue 100%);
    &:hover {
        background: linear-gradient(top, lighten($blue, 6%) 10%, $blue 100%);
    }
    &:active {
        background: $blue;
    }
}
```

### Typography

```scss
// API
@mixin SansSerif
%SansSerif

@mixin Smoothing
%Smoothing

@mixin Kerning
%Kerning

// One-line truncating, with ellipsis behind
@mixin Ellipsis
%Ellipsis

// Multiline truncating, with ellipsis behind
@mixin Clamp($lines)
```

### Retina
```scss
@mixin Retina($img, $img2x, $bgSize: cover)

@mixin HalfPixelBorder($color, $dir)
```

```scss
.sprite {
    @include Retina('img.png', 'img@2x.png', 100px 50px);
}
```

### Shape
```scss
@mixin Rect($width, $height, $radius: 0)

@mixin Square($length, $radius: 0)

@mixin Circle($diameter)

// auto scaling
@mixin Ratio($ratio)
```

### Reset
```scss
@mixin ResetElement

@mixin ResetMobile

// arguments $h1 ~ $h6 are all optional
@mixin ResetTitle($h1, $h2, $h3, $h4, $h5, $h6) {
    @content;
}

@mixin Reset {
    @content;
}
```


```scss
@include Reset {
    body {
        @include SansSerif;
        @include Smoothing;
    }
    a {
        text-decoration: none;
    }
};
```

Documentation:

* [English](https://github.com/NdYAG/sass-pattern/wiki/Documentation)
* [简体中文](https://github.com/NdYAG/sass-pattern/wiki/%E6%96%87%E6%A1%A3)
