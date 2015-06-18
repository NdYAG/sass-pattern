sass-pattern

A list of mixins to ease you from of the pain of repeating same code, and help you focusing on styling.

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

Create a Media Object:

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

* [in English](https://github.com/NdYAG/sass-pattern/wiki/Documentation)
* [中文版](https://github.com/NdYAG/sass-pattern/wiki/%E6%96%87%E6%A1%A3)
