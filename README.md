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
