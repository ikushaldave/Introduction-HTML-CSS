### Getting to Know More CSS

CSS is a powerful language that is used to style and layout the HTML document. Remember HTML is used to define the simple structure and semantics of the content. But with CSS you can describe how your HTML elements should be displayed on a page. For example, you can alter the font, color, size, spacing, etc. of your content. You can also split the layout into multiple columns, add animations, and other decorative features.

In the [introduction](https://github.com/AltCampus/AC-STYLE-introduction-to-web-and-html-css/blob/master/Ex1-explanation.md) chapter we have seen how to target any element using different selectors style it. In this chapter, we are gonna a bit deeper. We will see how exactly the styles are rendered. We are gonna discuss more different selectors and how selectors affect the style rendering. Then we will see some common property values that most often appear in CSS.

#### CSS Resets

We have several options when it comes to using a browser, such as Chrome, Safari, Opera, Firefox, etc. Every browser has its default styles for different elements. For example, the way a Chrome browser will display elements, in a similar way safari won't. Whatever margin and padding are having for different elements inside Firefox, it may be different in opera. To ensure cross-browser compatibility CSS reset is widely used.

CSS resets takes all the element and provides unified styles for all browser. It removes all the default sizing, margin, padding, and all the additional styles from the element.

One of the most popular CSS reset is [Eric Meyer’s reset](https://meyerweb.com/eric/tools/css/reset/), which targets all the common elements and resets the styles.

```
  /* http://meyerweb.com/eric/tools/css/reset/
   v2.0 | 20110126
   License: none (public domain)
  */

  html, body, div, span, applet, object, iframe,
  h1, h2, h3, h4, h5, h6, p, blockquote, pre,
  a, abbr, acronym, address, big, cite, code,
  del, dfn, em, img, ins, kbd, q, s, samp,
  small, strike, strong, sub, sup, tt, var,
  b, u, i, center,
  dl, dt, dd, ol, ul, li,
  fieldset, form, label, legend,
  table, caption, tbody, tfoot, thead, tr, th, td,
  article, aside, canvas, details, embed,
  figure, figcaption, footer, header, hgroup,
  menu, nav, output, ruby, section, summary,
  time, mark, audio, video {
    margin: 0;
    padding: 0;
    border: 0;
    font-size: 100%;
    font: inherit;
    vertical-align: baseline;
  }
  /* HTML5 display-role reset for older browsers */
  article, aside, details, figcaption, figure,
  footer, header, hgroup, menu, nav, section {
    display: block;
  }
  body {
    line-height: 1;
  }
  ol, ul {
    list-style: none;
  }
  blockquote, q {
    quotes: none;
  }
  blockquote:before, blockquote:after,
  q:before, q:after {
    content: '';
    content: none;
  }
  table {
    border-collapse: collapse;
    border-spacing: 0;
  }
```

After applying [Eric Meyer’s reset](https://meyerweb.com/eric/tools/css/reset/) you'll notice all the default styles from the elements are removed, everything looks similar. Now you can target the elements and define your own style. All the browsers will render the styles that you will define. That's how we ensure cross-browser compatibility.

"Always apply CSS reset on top of your stylesheet and then add your style after the reset". Because CSS follows the cascading rule, it means styles can be added and overwritten as the style sheet progress.

#### The Cascading Rule

CSS is a "Cascading Style Sheet" where styles cascade from top to bottom. Cascading allows to add different styles and overwrite the previous styles. In cascading whatever styles come at the bottom will have more precedence than the earlier one. For example,

```
p {
  background-color: orange;
  font-size: 24px;
}
p {
  background-color: green;
}
```

Here, we have selected the paragraph element change it's `background-color and font-size`. And again at the bottom, we selected paragraph element and change its background-color to green. When we will see the paragraph in the browser will find that the paragraph is having background `green`. Because the "green" comes after the orange for the paragraph, so it will take precedence. And there won't be any changes in `font-size`, it will remain `24px` because we haven't made any change in the font-size.

That's how the cascading style sheet works. However, sometimes this cascading may fail when we use the different selectors to target elements in a style sheet. The specificity weight of different selectors breaks the cascading rule.

#### Specificity weight of selectors.

In the [introduction](https://github.com/AltCampus/AC-STYLE-introduction-to-web-and-html-css/blob/master/Ex1-explanation.md) chapter we have seen three types of selectors, type, class, and ID. Each selector has a specific weight in the specificity table. Let's have a look at the table and the point of how much each selector hold.

```
  Type: 0-0-1
  Class: 0-1-0
  ID: 1-0-0
```

The ID selector has higher specificity weight than the class selector and the class selector has higher specificity weight than the type selector. It means that if an element is selected and styled in a stylesheet using these selectors, then the selector holding a more specific point in the table will always get the priority. The higher the specific weight more superiority is given in the stylesheet. Let's understand this with examples.

```
  <p class="food">...</p>

  .food {
    background: green;
  }
  p {
    background: orange;
  }
```

Here, the paragraph is selected using two selectors, type as well as the `class` selector. Although the orange background comes after the green background in the cascading. But the green background will take precedence because it has been applied using the class selector and the class selector has a higher specific weight in the table than the type selector. Let's see one more example of using all three selectors.

```
  <p class="food" id="bread">...</p>

  #bread {
    background: red;
  }
  .food {
    background: green;
  }
  p {
    background: orange;
  }
```

Similarly, although the class selector and type selector are coming after the ID selector, the background of the paragraph will be red. Because the ID selector has a higher specific weight than the class and type selector.

> A browser identifies how styles will be rendered for a selector, depends upon the selector's specificity weight along with its placement at cascade.

Sometimes, selectors are combined to be more specific. Its time to dig out more about the selectors and let's see how more than one selectors are combined to style an element.

#### Combining Selectors

We have seen how all the three selectors work individually. It's time to check out how they work together. Let's see a few examples,

```
  <div class="awesome">
    <p class="child">.....</p>
    <p class="child">.....</p>
  </div>
  <section>
    <p>.....</p>
    <p>.....</p>
  </section>
```

Now, if we select the paragraph element using just type selector, it will select every paragraph element in the document. So to become more specific we can combine the selector.

```
  .awesome .child {
    font-size: 32px;
    color: red;
  }
```

Now, the above selector will only select the paragraph element, which will be having an `awesome` class as a parent.

When selectors are combined, the rightmost selector is known as the key selector which always sits right before the opening curly braces. The key selector identifies which element will get all the styles inside the curly braces. And the selectors left to the key selector works as references. One more important point to note here, if you look at the above code closely will observe that there is a space between the key selector and the reference selector. There is a purpose of the space. For example,

```
  <div class="awesome child">
    <p>.....</p>
    <p>.....</p>
  </div>
  <section>
    <p>.....</p>
    <p>.....</p>
  </section>

  .awesome.child {
    font-size: 32px;
    color: red;
  }
```

It makes a large difference between `.awesome .child` and `awesome.child`. Since there is no space it means it will select the only element which will be having both the classes `awesome` as well as `child`. But if there is a space, means the key selector(**_here .child_**) is inside the reference selector(**_here .awesome_**).

We can combine different types of selectors to target elements and to be specific on a page. We will see their power as we write different combined selectors.

#### Styling Elements With Multiple Classes

In an html document, it is possible that an element can have multiple class attribute values with space-separated. At the same time, we can also provide the same class attribute value to multiple elements. Let's have a look.

```
  <button class="btn btn-error">.....</button>
  <button  class="btn btn-success">.....</button>
```

Yes, we can do that. Here, `btn` class is provided for the similar properties which both the element is sharing i.e. `font-size: 16px`. And both the element is also having a different class for different properties.

```
  .btn {
    font-size: 16px;
  }
  .btn-error {
    background: red;
  }
  .btn-success {
    background: green;
  }
```

This is one of the best practices of being as modular as possible. It helps in not to repeat yourself again and again for similar properties. It also helps in keeping the specificity weight of the selectors low.

In the beginning, it may feel confusing and it will take time to fully understand it, but with the time and practice, it will get easier and better.

#### Common CSS Property & Values

We have been using different properties and values in CSS from the beginning. For applying color we say the color name like `red, blue, green`, etc. Also for applying length, we say values in `pixel(px)`.

In this section mostly we will discuss what are the different values for color and length measurements can be applied.

##### Colors

Primarily there are four ways to apply color within CSS: `Keywords, hexadecimal, RGB and HSL` values. Probably we all know that all the colors are a combination of `RGB(red, green, blue)`. So all four ways are just the representation of RGB colors. By mixing different shades of RGB colors we can create millions of colors.

Let's discuss all these four ways one by one.\

##### Keyword Values

We have been taking this approach from the beginning. Keyword values are just to say the name of color which you want to set within CSS. For example, `red, blue, green, black, gray`, etc there are a lot more keyword values that we can apply.

```
  .pending {
    background: orange;
  }
  .success {
    background: green;
  }
```

Although it seems simple to use keyword values, it may get difficult to remember the name of all the colors. That's why we have other options also like hexadecimal, RGB, and HSL.

##### Hexadecimal Values

The hexadecimal values are represented in three or six characters and the value always consist `pound or hash (#)` at the beginning. For example,

```
  .pending {
    background: #FF6600;
  }
  .success {
    background: #008000;
  }
```

The first two characters represent red, the third and fourth characters represent green color and the last two characters represent blue color. The character can be numbered, 0 through 9 and letters a through f, upper or lower cases. With this combination, we have millions of hexadecimal colors.

Here, we can do one more thing that if the first two characters are matching, third and four are matching and the last two characters are matching then instead of six we can represent the color in three characters. Let's say for #FF6600:

```
.pending {
  background: #F60;
}
```

##### RGB & RGBa values

##### RGB

The RGB colors and are represented with function `rgb()` which stands for red, green, and blue colors.

```
.pending {
  background: rgb(255,102,0);
}
.success {
  background: rgb(0, 128, 0);
}
```

It accepts three values in integer with comma-separated. The first value represents the red, second green and last value represents the blue color. And value can be anything from 0 to 255.

##### RGBa

The RGBa values are represented with function `rgba()`. It's just we are adding an alpha value to RGB colors. In RGBa color the last value is alpha values, which must be a number between 0 to 1, it can be decimal. Mostly RGBa colors are defined to provide some transparency to the colors.

If the alpha value is 0 it means the color will be fully transparent means invisible or if the value is 1 then the color will be fully opaque. And if the value is between 0 to 1 then the color will have some transparency depending upon the value.

For example, suppose we want to provide 50% transparency to the background for the pending class.

```
  pending {
    background: rgba(255,102,0, 0.5);
  }
  .success {
    background: rgba(0, 128, 0, 1);
  }
```

##### HSL and HSLa value:

##### HSL

HSL colors are represented by `hsl()` function which stands for hue, saturation, and lightness.

```
  pending {
    background: hsl(24,100%,50%);
  }
  .success {
    background: hsl(120, 100%, 25.1%);
  }
```

The first value accepts the number between 0 to 360 which identifies the degree of color on the color wheel. The number 0 through 360 represents the color wheel.

The second and third values accept the value in percentage between 0 to 100%. The second value is for saturation of the color, where 0 is the grayscale and 100% means fully saturated. And the last value is for the lightness of the color, where 0 means fully black and 100% means fully white.

#### HSLa

As in RGBa value, 'a' represents alpha values which decide the transparency of the color. Similarly, we can also add an alpha value in HSL color, which is represented by function `hsla()`. The alpha value accepts the number between 0 to 1, where 0 means fully transparent and 1 means fully opaque.

```
  pending {
    background: hsla(24,100%,50%, 0.5);
  }
  .success {
    background: hsla(120, 100, 25.1, 1);
  }
```

We have seen all the ways to apply the value of the color. The most widely and accepted value is the hexadecimal and RGB values. It gives us a wide range of options and supported by almost every browser. The HSL values also give a wide range but as it is the newest way of defining color in CSS so it is not widely used and accepted by every browser.

##### Lengths

Now its time to discuss the what are the ways to define length values in CSS. We have seen `pixel(px)` values, which is one of the ways to define length. But there are other ways also to define the length values.

The length values are categorized into two categories. One is Absolute length and another is Relative length.

##### Absolute Lengths

One of the simplest length values used in CSS is the Absolute length. Few absolute lengths are pixel, centimeters, inches, etc. The absolute lengths are always fixed. Whatever the value is defined, it will always remain fixed, unlike relative lengths. It won't respond as the size of the screen increases or decreases.

One of the most common and widely used absolute lengths is pixel(px).

```
  p {
    font-size: 16px;
  }
```

The pixel is equal to 1/96th of an inch. The pixel unit is being used for quite a long time. But nowadays, as a responsive web design concept has come, the pixel unit has lost some of its popularity. Pixel does not provide flexibility, so mostly relative units are preferred. But for beginner, the pixel unit has always been trustworthy and it will remain.

##### Relative Lengths

The relative lengths are a bit complicated and different from the absolute lengths as they are not the fixed unit. It relies on other units of measurement. The most common relative units are `percentages, EM, REM`.

```
  .col {
    width: 100%;
  }
  .heading {
    font-size: 2em;
  }
  p {
    font-size: 1rem;
  }
```

We are not going in detail with relative lengths here, just an introduction to all types of relative units. But yeah, we will discuss all these relative units in detail once we reach to "Responsive Web Design" chapter.
