# fractionalgrids-css

Current Version `v0.0.1`

*A Yahoo Pure CSS implementation of grids in Twitter's Bootstrap 3.*

## Demo

Check out an example over at our [blog](http://appdev-confluence.mesd.k12.or.us:8090/display/APPDEV/Yahoo+Pure+Grids+with+Twitter+Bootstrap).

## Usage

**fractionalgrids-css** is used just like Bootstrap's [grid system](http://getbootstrap.com/css/#grid) with one minor exception:
the column size is now a fractional number.

Depending on how many columns you chose, usage is any valid fraction following the proper prefix convention.

For example, to make four 1/4 width columns:

```html
<div class="row">
    <div class="col-md-1-4">.col-md-1-4</div>
    <div class="col-md-1-4">.col-md-1-4</div>
    <div class="col-md-1-4">.col-md-1-4</div>
    <div class="col-md-1-4">.col-md-1-4</div>
</div>
```

That's it! You can even go wild with offsets, media queries, and column ordering:

```html
<div class="row">
    <div class="col-md-4-16">.col-md-4-16</div>
    <div class="col-md-4-16 col-md-offset-8-16">.col-md-4-16 .col-md-offset-8-16</div>
</div>
<div class="row">
    <div class="col-md-2-3 col-md-push-1-3">.col-md-2-3 .col-md-push-1-3</div>
    <div class="col-md-1-3 col-md-pull-2-3">.col-md-1-3 .col-md-pull-2-3</div>
</div>
<div class="row">
    <div class="col-md-9-11">
        Level 1: .col-md-9-11
        <div class="row">
            <div class="col-md-1-2">Level 2: .col-md-1-2</div>
            <div class="col-md-1-2">Level 2: .col-md-1-2</div>
        </div>
    </div>
</div>
```

## Installation

**fractionalgrids-css** can be installed any of three ways:

### 1. Add `fractionalgrids-12col.min.css` File Below Bootstrap's CSS File (EASIEST)

Simply add either `../fractionalgrids-css/dist/fractionalgrids-12col.min.css` or `../fractionalgrids-css/dist/fractionalgrids-24col.min.css`
to your web css directory and reference it in your header:

```html
<link type="text/css" rel="stylesheet" media="all" href="../bootstrap/dist/css/bootstrap.min.css">
<link type="text/css" rel="stylesheet" media="all" href="../fractionalgrids-css/dist/fractionalgrids-12col.min.css">
```

### 2. Cut and Paste (NOT RECOMMENDED)

Cut and Paste all of the `.col-` css classes over the ones found in your `bootstrap.css` file.
This is not recommended.

### 3. Edit Your `theme.less` File

In your `theme.less` file, add a new directory and override the grid reference, like so:

```javascript
@bootstrap-dir:  "../bower_components/bootstrap/less";
@fractionalgrid-dir: "../path/to/your/less";

// Core CSS
@import '@{fractionalgrid-dir}/grid.less';
```

And since **fractionalgrids-css** is a replacement library for Bootstrap's grids, it can take any number of columns defined in the `variables.less` file.
Change it here like so:

`../variables.less`

```javascript
// Grid system
// --------------------------------------------------

// Number of columns in the grid system
@grid-columns:                      12;
// Padding, to be divided by two and applied to the left and right of all columns
@grid-gutter-width:               30px;
// Point at which the navbar stops collapsing
@grid-float-breakpoint: @screen-sm-min;
```

## Contributing

See the [CONTRIBUTING.md] file for more information.

## Changelog

See the [CHANGELOG.md] file for more information.

## License

See the [LICENSE.md] file for more information.