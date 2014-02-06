# fractionalgrids-css

Current Version `v0.0.3`

*A Yahoo Pure CSS implementation of grids in Twitter's Bootstrap 3.*

## Demo

Check out an example over at our [blog](http://appdev-confluence.mesd.k12.or.us:8090/display/APPDEV/CSS+Fractional+Grid+Framework).

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

### 3. Edit Your `theme.less` File (PREFERRED)

In your `theme.less` file, add a new directory and override the grid reference, like so:

```javascript
@bootstrap-dir:  "../bower_components/bootstrap/less";
@fractionalgrid-dir: "../path/to/your/less";

// Core CSS
@import '@{fractionalgrid-dir}/grid.less';
```

And since **fractionalgrids-css** is a replacement library for Bootstrap's grids,
it can take any number of columns defined in the `variables.less` file.
Change it here like so:

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

## Known Bugs & Caveats

Bootstrap 3's grid system offers a plethora of flexibility: responsive widths, offsets, pushes & pulls, and nesting.
Because of these features, implementing relational and fractional grid systems uses considerably larger file sizes.
The 24-column css file is a whopping 150kB minified! Luckily, the 12-column file is only 37kB.
If you plan to use the distribution file, stick with the 12-column format unless you are absolutely sure
you will need the 24-column version. If worse comes to worse, you could alyways nest columns to produce a 24-column layout.

In order to make this less file compile into the smallest stylesheet possible, we had to use inline javascript anonymous functions.
This stylesheet is supported using only javascript less compilers.
It is **ABSOLUTELY NOT** supported using alternative less compilers, such as leafo's PHP Less script.
We encourage anyone who has any ideas on how to make this script work without anonymous functions,
feel free to drop a suggestion by or make a pull request. Thanks!

## Contributing

See the [CONTRIBUTING.md](CONTRIBUTING.md) file for more information.

## Changelog

See the [CHANGELOG.md](CHANGELOG.md) file for more information.

## License

See the [LICENSE.md](LICENSE.md) file for more information.