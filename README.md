# Spacing

Generate any number of padding and margin classes based on a list of sizes.

## Usage

```scss
@include Spacing($sizes: 10px 20px 40px);
```

The mixin `Spacing` has three parameters

`$sizes`: The base size to use to generate the classes
`$prefix`: Prefix all classes, default is `u-`
`$suffix`: Add a suffix to every class. Default is empty.

You can then use these in your HTML

```html
<div class="u-py1">
  Foo
</div>
```

In this case it will add 10px padding to the top and bottom of the element.

It generates these classes:

* p = Padding
* py = Padding top and bottom
* pz = Padding on the left and right
* pt = Padding top
* pb = Padding bottom
* pl = Padding left
* pr = Padding right

It will also generate the same margin classes for each size, but uses `m` instead of `p`.

## Responsive Spacing Classes

Wrap the mixin in a media query and add a suffix:

```scss
@media (min-width: 480px) {
  @include Spacing($sizes: 10px 20px 40px, $suffix: '-mobile');
}
```

Results in classes like:

```scss
.u-py1-mobile
```

Which will only work within that media query.
