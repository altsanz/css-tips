# css-tips
Those tips that I find useful to keep bookmarked


## Equal column heights

*Disclaimer: Better use Flexbox if possible*

CSS tools for Bootstrap 3.

Extracted from http://www.minimit.com/articles/solutions-tutorials/bootstrap-3-responsive-columns-of-same-height


### Markup

#### The very basic

The content must be inside a container, we call it with the class .inside, it's inside each column.
You have to add a div with the class .row-height inside the row, and also add .col-height to the columns.

#### Restricting by media query

Just use the responsive .row-height and .col-height classes: for example .row-sm-height with .col-sm-height

#### Choose vertical alignment inside each column

Use the classes .col-top or .col-middle or .col-bottom, or theirs respective responsive classes.

### Demo

http://www.minimit.com/demos/bootstrap-3-responsive-columns-of-same-height


### Toolkit

CSS to be added in order to use these magic features:

```css

/* USAGE
<div class="row">
  <div class="row-height">
    <div class="col-xs-2 col-xs-height col-xs-middle">
      <div class="inside"></div>
    </div>
    <div class="col-xs-4 col-lg-5 col-xs-height col-xs-middle">
      <div class="inside"></div>
    </div>
  </div>
</div>
*/

/* content styles */

.inside {
  margin-top: 20px;
  margin-bottom: 20px;
  background: #ededed;
  background: -webkit-gradient(linear, left top, left bottom,color-stop(0%, #f4f4f4), color-stop(100%, #ededed));
  background: -moz-linear-gradient(top, #f4f4f4 0%, #ededed 100%);
  background: -ms-linear-gradient(top, #f4f4f4 0%, #ededed 100%);
}
.inside-full-height {
  /*
  // if you want to give content full height give him height: 100%;
  // with content full height you can't apply margins to the content
  // content full height does not work in ie http://stackoverflow.com/questions/27384433/ie-display-table-cell-child-ignores-height-100
  */
  height: 100%;
  margin-top: 0;
  margin-bottom: 0;
}

/* columns of same height styles */

.row-height {
  display: table;
  table-layout: fixed;
  height: 100%;
  width: 100%;
}
.col-height {
  display: table-cell;
  float: none;
  height: 100%;
}
.col-top {
  vertical-align: top;
}
.col-middle {
  vertical-align: middle;
}
.col-bottom {
  vertical-align: bottom;
}

@media (min-width: 480px) {
  .row-xs-height {
    display: table;
    table-layout: fixed;
    height: 100%;
    width: 100%;
  }
  .col-xs-height {
    display: table-cell;
    float: none;
    height: 100%;
  }
  .col-xs-top {
    vertical-align: top;
  }
  .col-xs-middle {
    vertical-align: middle;
  }
  .col-xs-bottom {
    vertical-align: bottom;
  }
}

@media (min-width: 768px) {
  .row-sm-height {
    display: table;
    table-layout: fixed;
    height: 100%;
    width: 100%;
  }
  .col-sm-height {
    display: table-cell;
    float: none;
    height: 100%;
  }
  .col-sm-top {
    vertical-align: top;
  }
  .col-sm-middle {
    vertical-align: middle;
  }
  .col-sm-bottom {
    vertical-align: bottom;
  }
}

@media (min-width: 992px) {
  .row-md-height {
    display: table;
    table-layout: fixed;
    height: 100%;
    width: 100%;
  }
  .col-md-height {
    display: table-cell;
    float: none;
    height: 100%;
  }
  .col-md-top {
    vertical-align: top;
  }
  .col-md-middle {
    vertical-align: middle;
  }
  .col-md-bottom {
    vertical-align: bottom;
  }
}

@media (min-width: 1200px) {
  .row-lg-height {
    display: table;
    table-layout: fixed;
    height: 100%;
    width: 100%;
  }
  .col-lg-height {
    display: table-cell;
    float: none;
    height: 100%;
  }
  .col-lg-top {
    vertical-align: top;
  }
  .col-lg-middle {
    vertical-align: middle;
  }
  .col-lg-bottom {
    vertical-align: bottom;
  }
}

```

### Improving animating performance

There are very few CSS properties that can be animated without constantly triggering repaints for every frame, namely **opacity** and **transform**. We minimize the amount of repaints (and work that your browser has to do) by sticking to only changing these two properties during the animation.
- Source: http://tobiasahlin.com/blog/how-to-animate-box-shadow/

Hint: Try using pseudo-elements and opacity.

