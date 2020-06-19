### Getting to Know More About HTML

So far we have been introduced with the basic knowledge of HTML & CSS. Now it's time to dig a little bit more about the language.

We already know about the HTML elements. There are a large number of HTML elements available to display content on a page. But to start building a website we need to know more about the elements, like which element is best to display different types of content on a page. It's not only that we have to display our content on a page but it is also important to understand how elements are visually displayed and what's the semantic difference between the elements.

In HTML document element provides semantic meaning to raw content. Using proper elements for appropriate content plays an important role in HTML coding.

#### What is Semantic Code?

In HTML semantics means using a proper element for appropriate content. Semantic code provides perfect meaning to raw content on a page. Which element has how much value on a page, that is well described by semantic code.

In HTML semantic code plays a really important role. For a beginner, semantics doesn't matter much because most of the time they focus on the appearance of the content. But let me tell you it is good to have practice on semantic code from the beginning only. There are several benefits of writing semantic code.

- It provides the ability to machine to understand the content in a more appropriate way.

- Semantic code helps screen readers to explain your content to visually impaired people.

- The search engine also needs to understand your content properly, then only it can rank a page. Therefore semantic also helps in Search Engine Optimization.

However semantic code has others benefits too if you are more interested u go through the [article](https://boagworld.com/dev/semantic-code-what-why-how/) written by `Paul Boag`.

#### How to Write Semantic Code?

Semantic code is nothing but consists of semantic tags. As you are already familiar with tags and how do we use it to wrap our content in the HTML document.

What's the difference between a semantic tag and a normal tag? If you look at the semantic tags you can easily derive the meaning from its name only and for what purpose it can be used. For example: `<section>, <header>, <nav>, <footer>, <article>` etc are some of the semantic tags. Later in this chapter, we will learn to create a simple structure using these semantic tags.

There are few non-semantic tags also. For example: `<div>, <span>`. The non-semantic tags are mainly used for styling purpose, they do not hold any semantic meaning. You can not derive any meaning from its name also you won't get any idea how and where these tags should be used.

#### What are `<div>`s and `<span>`s?

Division or `<div>`s and `<span>`s are the two-element which are most often used in the HTML document. Although these element does not hold any semantic meaning they are extremely useful for styling a page.

It is not obvious that which content will be wrapped inside these tags, therefore they are mainly used to style the content within a page.

A `<div>` is a `block-level` element which is commonly used to group a large number of contents. To create a container or a wrapper or a division in a webpage we use `<div>` element.

On the other hand `<span>` is an `inline-level` element which is commonly used for smaller grouping of texts within a block-level element.

Further, in this lesson, we will learn to create a simple structure using both semantic tags as well as non-semantic tags.

#### Block vs Inline

Earlier in the above section, I have mentioned two levels of elements: block and inline. I mentioned `div` is a block and `span` is an inline-level element. In HTML document all the elements either falls within block-level or inline-level elements. So what's exactly a block-level and inline-level element?

A block-level element always begins from a new line and stack on top of each other. It occupies all the available width. A block-level element can nest a block or inline-level element inside itself. Commonly a block-level element is used to wrap a large piece of content. Few block-elements are `paragraph, div section, article, nav` etc.

An inline-level element does not begin from a new line. They come one after one in a line and takes the width according to the content it wraps inside it. An inline-level can only nest inline-level elements only inside it. A block-level element cannot inside an inline-level element. Commonly inline-level element is used to wrap a small piece of content such as a few words. Few inline-level elements are `span, anchor, strong, italics, bold` etc.

#### Forms of Media and Content

There are different forms of media and content available online. The most popular content which you can see usually on any page are texts, links, images, etc. In this lesson, we are going to discuss just the basics of this type of content. Later to have a closer look at all these types of content we have individual chapters.

#### Text Based Elements

On a page, you can have different forms of media and content but among them, texts are more predominant. The core content of a page is texts. And there are several elements to display texts on a web page. We have a heading, paragraph, bold and italics elements.

##### Headings

Headings are the block level elements that differentiate content and establish hierachy on a page. There are six different level of headings, `<h1>, <h2>, <h3>, <h4>, <h5>, <h6>`.

```
  <h1>Heading One</h1>
  <h2>Heading Two</h2>
  <h3>Heading Three</h3>
  <h4>Heading Four</h4>
  <h5>Heading Five</h5>
  <h6>Heading Six</h6>
```

Heading elements are used to apply a heading of any section or any article so that users can easily identify the content. As you see there are six levels of heading elements, so each level should be used accordingly where it is relevant on a page. The primary heading of a page should always come in `<h1>` tag and subsequently other levels. Each level should be used on a page where it is semantically correct.

The primary heading `h1` should always be used once per page. Avoid `<h1>` tag more than once. Using more than once won't show any error but that's the best practice.

Heading elements not only help users to identify content or establish but it also helps in `Search Engine Optimization(SEO)`. If the heading elements have been used semantically correct on a page then it has a better chance to get indexed on Search Engines.

##### Paragraphs

The paragraph element in HTML document is defined using `<p>`. It's a block-level element that is used whenever we need to add any information or paragraph on a page. Usually, Headings are followed by supporting paragraphs.

```
  <p>AltCampus offers a 6-month program that helps you become a software developer.</p>
```

##### Strong Vs Bold

There are two elements in the HTML document that makes the text appear bold, `<strong>` and `<b>`. Both of these are inline-level elements and are semantically different from each other.

To make a text bold and give strong importance we use `<strong>` tag and is the most popular way for bolding a text. Whereas the `<b>` tag is used only for styling purposes.

Choosing between `<strong>` and `<b>` you have extra careful. Chose one which is more semantically correct.

##### Em Vs I

Similar to `<strong>` and `<b>` tag there are two tags that italicize the texts, `<em>` and `<i>`. These two are also inline-level elements and are semantically different from each other.

The `<em>` tag is used to provide stress emphasis on text and a popular choice to italicize text. While `<i>` tag is only styling purposes such as an alternative to such as for any foreign word, or any fictional characters' thoughts.

Similarly, choosing between `<em>` and `<i>` you have to be extra careful. Chose the one which is more semantically correct.

#### Creating Hyperlinks

Hyperlinks are one of the most important parts of the web, that makes the web a web. Obviously, on the web, you can go from one page to another page, one document to another document or from one website to another website. Going from one resource to another required hyperlinks. In HTML document hyperlinks are created using anchor `<a>` tag.

The anchor tag is an inline-level element that comes with a `href` attribute, known as `hyperlink reference`. The `href` attribute value determines the destination of the link.

```
  <a href="https://altcampus.io/">AltCampus</a>
```

In the above example if you click on "AltCampus", which wrapped inside the anchor tag, will take you to "AltCampus" websites.

> The anchor tag not only can wrap texts, but you can also make an image working as a link.
> You can make any block or any division working as a link.
>
> As you know anchor tag is an inline-level element and by nature inline-level element cannot wrap a block-level element.
> But anchor tag is the only inline-level element that can any level of element inside, whether it's a block or inline.

It is most common to see that few links on a page connect to the other page of the same website as well as few links connect to a other website. For example,

```
  <a href="about.html">About</a>
  <a href="https://www.google.com/">Google</a>
```

Based on the value inside the href attribute of an anchor link, a link can have two types of path `Relative path` and `Absolute path`.

##### Relative Path:

If the link connects to the other pages of the same website then it is considered as a relative path that does not include any domain like `.com, .io, .org` etc. A relative path will have the name of the file in the href attribute value. For example:

```
  <a href="about.html">About</a>
```

##### Absolute Path:

If the link connects to another website which is entirely different from the current one, then it is considered to have an absolute path. An absolute path will always have a domain name like `.com, .org, .io` etc.

For example:

```
  <a href="https://www.google.com/">Google</a>
```

##### Opening Tag in New Tab

Usually, when you click on any link it opens on the same window on which they are clicked. That's the default behavior of a link. However, you can make the link to open in a new window. To apply such action you need to define another attribute, `target` with value `_blank` inside the anchor tag.

```
  <a href="https://www.google.com/" target"_blank">Google</a>
```

Now if you click on Google, the `google.com` will open in a new window. Normally you will find the absolute paths are defined with target attribute with `_blank` value.

##### Linking to Email Address

Sometimes you might have encountered the link "Mail Me". If such hyperlink is clicked user's default email client opens, populating email address to which the email will be sent.

To create such type of hyperlink `href` attribute value includes `mailto:` followed by the email address. For example:

```
  <a href="mailto:xyz@example.com">Mail me</a>
```

Additionally, we can also add subject and body text of the email. For example,

```
  <a href="mailto:xyz@example.com?subject=Reaching%20Out&body=How%20are%20you?">Mail Me</a>
```

Here `Reaching out` is the subject and `How are you?` is the body text of the email. To provide space we say `%20` between words and to break line we say `%0A`.

##### Linking to other parts of the same page.

Sometimes we can also find the links are connected to other sections of the same page. Generally, you can find such hyperlinks on the single-page website. When you click any link in the main navigation, it scrolls to other sections of the page.

Another best example for that type of link is, most of the time you may find a `back to top` button when clicked it directly take to the top of the page.

To create such link we use `id` attribute and the value of the id attribute is provided in the href attribute of the anchor link. For example:

```
  <body id="top">
    ................
    <a href="#top">Back to top</a>
    .................
  </body>
```

#### Images

Images are the core media element of a page, which you more often find on any website. To add an image on a page `<img>` tag is used which is an inline-level element. The `img` tag is a self-closing tag that generally comes with two attributes, `src` and `alt`.

The `src` attribute accepts the value of the URL from to specify the source of an image. And the `alt` attribute is defined to provide alternative text for the image, in a case for some reason the image is not displayed. The `alt` attribute value must describe the content of the image.

```
  <img src="cat.jpg" alt="Cat">
```

> Note: Never miss the `alt` attribute, because it helps in `Search Engine Optimization` also.

To define a certain width and height of the image you can add `width` and `height` attribute also inside the `<img>` tag.

```
  <img src="cat.jpg" alt="Cat" width="300" height="180">
```

Or you can specify the width and height in CSS.

```
  img {
    width: 300px;
    height: 180px;
  }
```

This is just the basic introduction of the image element. We can also display an image on a page, using `background-image` property, which we will learn in "Media Chapter". In the "Media" Chapter we will have a closer look at images. We will also learn other forms of media, apart from images, such as audio, video, inline frames, etc.

#### Structure Based Elements

In the previous section, we have seen different forms of media and content that bring our content to life on a page. But the content on a page is grouped based on the structure of a page. So apart from text-based elements, links, images, etc, there are some structure-based elements, `<header>, <nav>, <section>, <article>, <aside>, and <footer>`.

All of these structure-based elements are the block-level elements. The text-based elements, different forms of media, links are grouped inside these elements, to organize our page and provide semantic structure.

---

![alt text](https://raw.githubusercontent.com/suraj122/AC-STYLE-images/master/html-css/Structure.png)

---

Let's have a closer look at these elements individually.

##### Header

Header elements usually come on top of a page, article, section, or any other division of a page. Generally, heading, introductory text, and even navigations are wrapped inside the `<header>` elements.

```
  <header>.....</header>
```

##### Navigation

The purpose of the `<nav>` element is to group all the navigation links. For example menus, table of contents, and indexes.

The `<nav>` element is intended only for the major block of navigation, not necessary for all the links. Most commonly it wraps the links that take other pages within the same website or other parts of the web page.

```
  <nav>......</nav>
```

##### The Main Tag

The `<main>` tag specifies all the main content of the body inside a document. All the content coming inside the `<main>` tag should be unique. The repeated content such as main navigation links, site logos, sidebars, copyright information, should not be included in the `<main>` tag. However, the search forms should not also be included unless the form is the main function of the page.

Usually, it wraps the elements like a different section of the document, articles, divs, etc. And one more important point is that, there must not be more than one `<main>` tag in a document.

```
  <main>
    <section>
      .....
    </section>
    <section>
      .....
    </section>
  </main>
```

##### Section

The `<section>` element in HTML document is used to define different section on a page. Typically it includes a heading element but not always.

The `<section>` element break up and build hierarchy on a page so that it becomes easier for users to identify the group of content. Do not use `<section>` element as a generic container to style the layout, for that purpose we have `<div>` element. Logically it should only define the outline of different sections in a document.

```
  <main>
    <section>
      .....
    </section>
    <section>
      .....
    </section>
  </main>
```

##### Article

The `<article>` tag specifies the self-contained content, which is intended to distributable or reusable independently in a document. More often we mark up the content like blog posts, newspaper articles, user-submitted content, etc. inside the `<article>`.

```
  <article>
    .......
  </article>
```

##### Aside

The `<aside>` HTML element defines a section that is indirectly related to the main content in a document, such as sidebars. Most commonly the sidebars come on the left or right side of the page.

```
  <aside>
    ........
  </aside>
```

The `<aside>` tag is a block-level element, therefore it will appear on a new line occupying whole available width. So do not confuse that `<aside>` tag will appear as a sidebar on a page. To position it as left sidebar or right sidebar we will learn "positioning element" using CSS.

##### Footer

The `<footer>` element is a structural element that identifies the content which comes at the bottom of the page, document, section, or an article. Typically a `<footer>` element wraps the content related to copyright and author information. It also holds contact information, sitemap, and the extra links related to documents.

```
  <footer>
    .......
  </footer>
```

So far we are doing better with the basics of HTML. With the introduction to forms of media and content and structure base elements, now is a good time to put the things together. Let's see how and where all these elements are being used in a document practically.
