# Outlayer

_Layout class_

Outlayer is a base layout class for layout libraries like [Packery](http://packery.metafizzy.co) and [Masonry](http://masonry.desandro.com)

Outlayer layouts work with a container element and children item elements.

``` html
<div class="container">
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  ...
</div>
```

## Outlayer.create()

Create a layout class with `Outlayer.create()`

``` js
var Layout = Outlayer.create( namespace );
// for example
var Masonry = Outlayer.create('masonry');
```

+ `namespace` _{String}_
+ returns `LayoutClass` _{Function}_

Create a new layout class. `namespace` is used for jQuery plugin, and for declarative initialization.

The `Layout` inherits from [`Outlayer.prototype`](docs/outlayer.md).

```
var elem = document.querySelector('#selector');
var msnry = new Masonry( elem, {
  // set options...
  columnWidth: 200
});
```

## Item

Layouts work with Items, accessible as `Layout.Item`. See [Item API](docs/item.md).

## Declarative

An Outlayer layout class can be initialized via HTML, by setting a class of `.js-namespace` on the element. Options can be set via a `data-namespace-options` attribution. For example:

``` html
<!-- var Masonry = Outlayer.create('masonry') -->
<div id="container" class="js-masonry" data-masonry-options='{ "itemSelector": ".item", "columnWidth": 200 }'>
  ...
</div>
```

## .data()

Get a layout instance from an element.

```
var myMasonry = Masonry.data( document.querySelector('#container') );
```

## jQuery plugin

The layout class also works as jQuery plugin.

``` js
// create Masonry layout class, namespace will be the jQuery method
var Masonry = Outlayer.create('masonry');
// rock some jQuery
$( function() {
  // .masonry() to initialize
  var $container = $('#container').masonry({
    // options...
  });
  // methods are available by passing a string as first parameter
  $container.masonry( 'reveal', elems );
});
```
