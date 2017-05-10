# sass-pattern

A list of mixins to ease you from of the pain of repeating same code and help you focus on necessary styling.

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

Reset style:

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

Create a [Media Object](http://www.stubbornella.org/content/2010/06/25/the-media-object-saves-hundreds-of-lines-of-code):

```scss
.status {
    @include Media(
        $left: '.status-avatar',
        $right: '.status-content',
        $gutter: '20px'
    );
}
```

More examples:

* [English](https://github.com/NdYAG/sass-pattern/wiki/Documentation)
* [简体中文](https://github.com/NdYAG/sass-pattern/wiki/%E6%96%87%E6%A1%A3)
