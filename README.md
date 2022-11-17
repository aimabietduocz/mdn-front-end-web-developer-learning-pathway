# This is a repository where I store the codes and notes while taking MDN Web Docs's [front-end web developer learning pathway](https://developer.mozilla.org/en-US/docs/Learn/Front-end_web_developer).

# HTML - Structuring the Web

## Introduction to HTML

-   Tags in HTML are not case-sensitive. This means they can be written in uppercase or lowercase. However, it is best practice to write all tags in lowercase for consistency and readability.
-   The `title` attribute specifies extra information about the link, such as a description of the page that is being linked to. For example, `title="The Mozilla homepage"`. This appears as a tooltip when a cursor hovers over the element.
-   adding author, description, etc.
    -   [facebook](https://ogp.me/)
    -   [twitter](https://developer.twitter.com/en/docs/twitter-for-websites/cards/overview/abouts-cards)
-   Search engines indexing your page consider the contents of headings as important keywords for influencing the page's search rankings.
-   `span` is using to wrap content when you want to apply CSS to it (or do something to it with JavaScript) without giving it any extra meaning.
-   HTML text fundamentals
    -   In HTML we use the `<em>` (emphasis), `<strong>` (strong importance) element to mark up such instances. As well as making the document more interesting to read, these are recognized by _screen readers_, which can be configured to speak them in a different tone of voice.
    -   `<i>` is used to convey a meaning traditionally conveyed by italic: foreign words, taxonomic designation, technical terms, a thought…
    -   `<b>` is used to convey a meaning traditionally conveyed by bold: keywords, product names, lead sentence…
    -   `<u>` is used to convey a meaning traditionally conveyed by underline: proper name, misspelling…
-   Link best practices
    -   Search engines use link text to index target files, so it is a good idea to include keywords in your link text to effectively describe what is being linked to.
    -   Keep your link text as short as possible. - Linking to non-HTML resources — leave clear signposts, e.g. "Download FireFox" (.exe, 200MB)
    -   Use the download attribute when linking to a download to provide a default save filename.
-   Description lists use a different wrapper than the other list types — `<dl>`; in addition each term is wrapped in a `<dt>` (description term) element, and each description is wrapped in a `<dd>` (description definition) element.
-   Another fairly common element you'll meet when looking around the Web is `<abbr>` — this is used to wrap around an abbreviation or acronym, remember to add title attribute.
-   `<sup>` is use for superscript, `<sub>` is use to represent subscript.
-   `<main>` is for content unique to this page. Use `<main>` only once per page, and put it directly inside `<body>`. Ideally this shouldn't be nested within other elements.
-   `<article>` encloses a block of related content that makes sense on its own without the rest of the page (e.g., a single blog post).
-   `<section>` is similar to `<article>`, but it is more for grouping together a single part of the page that constitutes one single piece of functionality (e.g., a mini map, or a set of article headlines and summaries), or a theme. It's considered best practice to begin each sect `<article>`s up into different `<section>`s, or `<section>`s up into different `<article>`s, depending on the context.
-   `<aside>` contains content that is not directly related to the main content but can provide additional information indirectly related to it (glossary entries, author biography, related links, etc.).
-   `<header>` represents a group of introductory content. If it is a child of `<body>` it defines the global header of a webpage, but if it's a child of an `<article> `or` <section>` it defines a specific header for that section (try not to confuse this with titles and headings).
-   `<nav> `contains the main navigation functionality for the page. Secondary links, etc., would not go in the navigation.
-   `<footer>` represents a group of end content for a page.

## Multimedia and embedding

-   HTML `<figure>` and `<figcaption>` elements are created for exactly this purpose: to provide a semantic container for figures, The `<figcaption>` element tells browsers, and assistive technology that the caption describes the other content of the `<figure>` element.
    -   > Note: From an accessibility viewpoint, captions and alt text have distinct roles. Captions benefit even people who can see the image, whereas alt text provides the same functionality as an absent image. Therefore, captions and alt text shouldn't just say the same thing, because they both appear when the image is gone.
-   There are two types of images on the web:
    -   **Raster images** are defined using a grid of pixels — a raster image file contains information showing exactly where each pixel is to be placed, and exactly what color it should be. Popular web raster formats include Bitmap (`.bmp`), PNG (`.png`), JPEG (`.jpg`), and GIF (`.gif`).
    -   **Vector images** are defined using algorithms — a vector image file contains shape and path definitions that the computer can use to work out what the image should look like when rendered on the screen.

## HTML tables

We can style table with `<col>`, for example:

```html
<colgroup>
    <col />
    <col style="background-color: yellow" span="2" />
</colgroup>
```

# CSS - Styling the Web

## CSS first steps

Syntax

-   `li.special { css }`

This syntax means "target any li element that has a class of special".

-   `li em { css }`

This selector will select any `<em>` element that is inside (a descendant of) an `<li>`

-   `h1 + p { css }`

Something else you might like to try is styling a paragraph when it comes directly after a heading at the same hierarchy level in the HTML. To do so, place a + (**an adjacent sibling combinator**) between the selectors.

-   What happens if a browser encounters CSS it doesn't understand?

The answer is that it does nothing, and just moves on to the next bit of CSS!

## CSS building blocks

### Cascade and inheritance, CSS selectors

-   `article > p { css }`

selects paragraphs that are direct children of <`article`> elements using the child combinator (`>`):

-   `p::first-line { }`

`::first-line` always selects the first line of text inside an element (a <`p`> in the above case)

#### Outer display type

If a box has an outer display type of `block`, then:

-   The box will break onto a new line.
-   The width and height properties are respected.
-   Padding, margin and border will cause other elements to be pushed away from the box.
-   The box will extend in the inline direction to fill the space available in its container. In most cases, the box will become as wide as its container, filling up 100% of the space available.

Some HTML elements, such as <`h1`> and <`p`>, use block as their outer display type by default.

If a box has an outer display type of `inline`, then:

-   The box will not break onto a new line.
-   The width and height properties will not apply.
-   Vertical padding, margins, and borders will apply but will not cause other inline boxes to move away from the box.
-   Horizontal padding, margins, and borders will apply and will cause other inline boxes to move away from the box.

Some HTML elements, such as <`a`>, <`span`>, <`em`> and <`strong`> use inline as their outer display type by default.

#### Inner display type

You can change the inner display type for example by setting `display: flex;`. The element will still use the outer display type `block` but this changes the inner display type to `flex`. Any direct children of this box will become flex items and behave according to the Flexbox specification.

[Detail](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)

### The box model

#### Parts of a box

-   `Content box`: The area where your content is displayed; size it using properties like _inline-size_ and _block-size_ or _width_ and _height_.
-   `Padding box`: The padding sits around the content as white space; size it using _padding_ and related properties.
-   `Border box`: The border box wraps the content and any padding; size it using _border_ and related properties.
-   `Margin box`: The margin is the outermost layer, wrapping the content, padding, and border as whitespace between this box and other elements; size it using _margin_ and related properties.

The below diagram shows these layers:

![](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model/box-model.png)

If we assume that a box has the following CSS:

```css
.box {
    width: 350px;
    height: 150px;
    margin: 10px;
    padding: 25px;
    border: 5px solid black;
}
```

The _actual_ space taken up by the box will be 410px wide (350 + 25 + 25 + 5 + 5) and 210px high (150 + 25 + 25 + 5 + 5).
![](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model/standard-box-model.png)

> **Note**: The margin is not counted towards the actual size of the box — sure, it affects the total space that the box will take up on the page, but only the space outside the box. The box's area stops at the border — it does not extend into the margin.

#### The alternative CSS box model

In the alternative box model, any width is the width of the visible box on the page. The content area width is that width minus the width for the padding and border (see image below). No need to add up the border and padding to get the real size of the box.

To turn on the alternative model for an element, set `box-sizing: border-box` on it. With the code above, the `actual` space taken up by the box will be 350px in the inline direction and 150px in the block direction.
![](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model/alternate-box-model.png)

To use the alternative box model for all of your elements (which is a common choice among developers), set the `box-sizing` property on the <`html`> element and set all other elements to inherit that value:

```css
html {
    box-sizing: border-box;
}
*,
*::before,
*::after {
    box-sizing: inherit;
}
```

### Margins, padding, and borders

#### Margin

The margin is an invisible space around your box. It pushes other elements away from the box.

#### Borders

The border is drawn between the margin and the padding of a box.

#### Padding

The padding sits between the border and the content area and is used to push the content away from the border. Unlike margins, you cannot have a negative padding.

### Using display: inline-block

`display: inline-block` is a special value of `display`, which provides a middle ground between `inline` and `block`. Use it if you do not want an item to break onto a new line, but do want it to respect `width` and `height` and avoid the **overlapping**.

### Backgrounds

#### Controlling background-repeat

-   no-repeat — stop the background from repeating altogether.
-   repeat-x — repeat horizontally.
-   repeat-y — repeat vertically.
-   repeat — the default; repeat in both directions.

#### Sizing the background image

In this case we could use the `background-size` property, which can take `length` or `percentage` values, to size the image to fit inside the background.
You can also use keywords:

-   `cover` — the browser will make the image just large enough so that it completely covers the box area while still retaining its aspect ratio. In this case, part of the image is likely to end up outside the box.
-   `contain` — the browser will make the image the right size to fit inside the box. In this case, you may end up with gaps on either side or on the top and bottom of the image, if the aspect ratio of the image is different from that of the box.

#### Positioning the background image

We could use `top`, `center`,`bottom`, `left`, `right` to position the image, also:

```css
background-position: top 20px right 10px;
```

### Overflowing content

Everything in CSS is a box. You can constrain the size of these boxes by assigning values of `width` and `height`. **Overflow happens when there is too much content to fit in a box.**

See [the examples](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Overflowing_content)

### The overflow property

It is the way you instruct the browser how it should behave.
The default value of overflow is `visible`. With this default, we can see content when it overflows.

To crop content when it overflows, you can set `overflow: hidden`. This does exactly what it says: it hides overflow. Beware that this can make some content invisible. You should only do this if hiding content won't cause problems.

Instead, perhaps you would like to add scrollbars when content overflows? Using `overflow: scroll`, browsers with visible scrollbars will always display them—even if there is not enough content to overflow.

If you only want scrollbars to appear when there is more content than can fit in the box, use `overflow: auto`. This allows the browser to determine if it should display scrollbars.

### CSS Values and units

#### Relative length units

`em`: Font size of the parent, in the case of typographical properties like `font-size`, and font size of the element itself, in the case of other properties like `width`.

`rem`: Font size of the root element.

`vw`: 1% of the viewport's width.

`vh`: 1% of the viewport's height.

### Sizing items in CSS

#### min- and max- sizes

If you have a box that might contain a variable amount of content, and you always want it to be at least a certain height, you could set the `min-height` property on it. The box will always be at least this height, but will then grow taller if there is more content than the box has space for at its minimum height.

A common use of `max-width` is to cause images to scale down if there is not enough space to display them at their intrinsic width while making sure they don't become larger than that width.

#### Viewport units

The viewport — which is the visible area of your page in the browser you are using to view a site — also has a size. In CSS we have units which relate to the size of the viewport — the `vw` unit for viewport width, and `vh` for viewport height. Using these units you can size something relative to the viewport of the user.

**If you change the vh and vw values this will change the size of the box or font; changing the viewport size will also change their sizes because they are sized relative to the viewport.**

### Images, media, and form elements

Assume we have a box 200 pixels and the image inside of it is larger than 200 pixels and overflows the box. We can add `max-width: 100%` to the image css.

We also have `object-fit` property, `object-fit: cover` will size the image down, maintaining the aspect ratio so that it neatly fills the box. As the aspect ratio is maintained, some parts of the image will be cropped by the box.

If we use `contain` as a value, the image will be scaled down until it is small enough to fit inside the box. This will result in "letterboxing" if it is not the same aspect ratio as the box.

## Styling text

#### Font style, font weight, text transform, and text decoration

-   `text-transform`: Allows you to set your font to be transformed. Values include:
    -   none: Prevents any transformation.
    -   uppercase: Transforms all text to capitals.
    -   lowercase: Transforms all text to lower case.
    -   capitalize: Transforms all words to have the first letter capitalized.
    -   full-width: Transforms all glyphs to be written inside a fixed-width square, similar to a monospace font, allowing aligning of, e.g., Latin characters along with Asian language glyphs (like Chinese, Japanese, Korean).

beside that, we have:

-   `text-decoration` : none/ underline/ overline/ line-through
-   `font-weight`: normal/ bold/ lighter/ bolder/ 100-900
-   `font-style`: normal/ italic/ oblique (_Sets the text to use a simulated version of an italic font, created by slanting the normal version._)

### Text layout

#### Text alignment

-   `text-align`

    -   left: Left-justifies the text.
    -   right: Right-justifies the text.
    -   center: Centers the text.
    -   justify: Makes the text spread out, varying the gaps in between the words so that all lines of text are the same width. You need to use this carefully — it can look terrible, especially when applied to a paragraph with lots of long words in it. If you are going to use this, you should also think about using something else along with it, such as hyphens, to break some of the longer words across lines.

-   The `line-height` property sets the height of each line of text.
-   The `letter-spacing` and `word-spacing` properties allow you to set the spacing between letters and words in your text.

### List-specific styles

-   `list-style-type`: Sets the type of bullets to use for the list, for example, square or circle bullets for an unordered list, or numbers, letters, or roman numerals for an ordered list.
-   `list-style-position`: Sets whether the bullets, at the start of each item, appear inside or outside the lists.
-   `list-style-image`: Allows you to use a custom image for the bullet, rather than a simple square or circle.

## CSS layout
