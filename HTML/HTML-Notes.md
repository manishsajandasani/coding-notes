# HTML Notes

## What is HTML?

- HTML stands for Hyper Text Markup Language.
- HTML is the standard markup language for creating Web pages.
- HTML describes the structure of a Web page.
- HTML consists of a series of elements.
- HTML elements tell the browser how to display the content.
- HTML elements label pieces of content such as "this is a heading", "this is a paragraph", "this is a link", etc.

## A simple HTML document

```html
<!DOCTYPE html>
<html>
	<head>
		<title>Page Title</title>
	</head>
	<body>
		<h1>My First Heading</h1>
		<p>My first paragraph.</p>
	</body>
</html>
```

## Explanation of above

- The `<!DOCTYPE html>` declaration defines that this document is an HTML5 document.
- The `<html>` element is the root element of an HTML page.
- The `<head>` element contains meta information about the HTML page.
- The `<title>` element specifies a title for the HTML page (which is shown in the browser's title bar or in the page's tab).
- The `<body>` element defines the document's body, and is a container for all the visible contents, such as headings, paragraphs, images, hyperlinks, tables, lists, etc.
- The `<h1>` element defines a large heading.
- The `<p>` element defines a paragraph.

## What is a Web Browser?

- The purpose of a web browser (Chrome, Edge, Firefox, Safari) is to read HTML documents and display them correctly.
- A browser does not display the HTML tags, but uses them to determine how to display the document.

## HTML Page Structure

- The content inside the `<body>` section will be displayed in a browser.
- The content inside the `<title>` element will be shown in the browser's title bar or in the page's tab.

## Write first HTML file

- Open Notepad in windows.
- Write or copy the HTML code into Notepad.
- Save the file on your computer with .html or .html extension. You can use either .htm or .html as file extension. There is no difference; it is up to you.
- Open the saved HTML file in your favorite browser (double click on the file).

## HTML Documents

- All HTML documents must start with a document type declaration: `<!DOCTYPE html>`.
- The HTML document itself begins with `<html>` and ends with `</html>`.
- The visible part of the HTML document is between `<body>` and `</body>`.

## The <!DOCTYPE> Declaration

- The `<!DOCTYPE>` declaration represents the document type, and helps browsers to display web pages correctly.
- It must only appear once, at the top of the page (before any HTML tags).
- The `<!DOCTYPE>` declaration is not case sensitive.
- The `<!DOCTYPE>` declaration for HTML5 is `<!DOCTYPE html>`

## How to view HTML source

- View HTML Source Code
  - Right-click in an HTML page and select "View Page Source" (in Chrome) or "View Source" (in Edge), or similar in other browsers. This will open a window containing the HTML source code of the page.
- Inspect an HTML Element
  - Right-click on an element (or a blank area), and choose "Inspect" or "Inspect Element" to see what elements are made up of (you will see both the HTML and the CSS). You can also edit the HTML or CSS on-the-fly in the Elements or Styles panel that opens.

## What is an HTML element?

- An HTML element is defined by a start tag, some content, and an end tag:
  `<tagname> Content goes here... </tagname>`
- The HTML element is everything from the start tag to the end tag:
  `<h1>My First Heading</h1>`
  `<p>My first paragraph.</p>`
- Some HTML elements have no content (like the `<br>` element). These elements are called empty elements. Empty elements do not have an end tag!

## Nested HTML Elements

- HTML elements can be nested (this means that elements can contain other elements).
- All HTML documents consist of nested HTML elements.
- The following example contains four HTML elements (`<html>`, `<body>`, `<h1>` and `<p>`):
  ```html
  <!DOCTYPE html>
  <html>
    <body>
      <h1>My First Heading</h1>
      <p>My first paragraph.</p>
    </body>
  </html>
  ```

- Example expalined:
  - The `<html>` element is the root element and it defines the whole HTML document.
  - It has a start tag `<html>` and an end tag `</html>`.
  - Then, inside the `<html>` element there is a `<body>` element.
  - The `<body>` element defines the document's body.
  - It has a start tag `<body>` and an end tag `</body>`.
  - Then, inside the `<body>` element there are two other elements: `<h1>` and `<p>`.
  - The `<h1>` element defines a heading.
  - It has a start tag `<h1>` and an end tag `</h1>`.
  - The `<p>` element defines a paragraph.
  - It has a start tag `<p>` and an end tag `</p>`.
- Never skip the end tag.

## Empty or Void HTML Elements

- HTML elements with no content are called empty elements.
- The `<br>` tag defines a line break, and is an empty element without a closing tag.

## HTML is Not Case Sensitive

- HTML tags are not case sensitive: `<p>` means the same as `<p>`.
- The HTML standard does not require lowercase tags, but W3C recommends lowercase in HTML, and demands lowercase for stricter document types like XHTML.

## HTML Attributes

- All HTML elements can have attributes
- Attributes provide additional information about elements
- Attributes are always specified in the start tag
- Attributes usually come in name/value pairs like: name="value"
- The `<a>` tag defines a hyperlink. The **href** attribute specifies the URL of the page the link goes to:
  ```html 
  <a href="https://www.w3schools.com">Visit W3Schools</a>
  ```
- The `<img>` tag is used to embed an image in an HTML page. The **src** attribute specifies the path to the image to be displayed:
  ```html
  <img src="img_girl.jpg">
  ```
- There are two ways to specify the URL in the src attribute:
  - **Absolute URL** - Links to an external image that is hosted on another website. Example: src="https://www.w3schools.com/images/img_girl.jpg".
  - **Relative URL** - Links to an image that is hosted within the website. Here, the URL does not include the domain name. If  the URL begins without a slash, it will be relative to the current page. Example: src="img_girl.jpg". If the URL begins with a slash, it will be relative to the domain. Example: src="/images/img_girl.jpg".
- **Notes:** External images might be under copyright. If you do not get permission to use it, you may be in violation of copyright laws. In addition, you cannot control external images; it can suddenly be removed or changed.
- **Tip:** It is almost always best to use relative URLs. They will not break if you change domain.
- The `<img>` tag should also contain the **width** and **height** attributes, which specify the width and height of the image (in pixels):
  ```html
  <img src="img_girl.jpg" width="500" height="600">
  ```
- Other attributes are **alt, style, lang, title,** etc.
- Always Use Lowercase Attributes.
- Always Quote Attribute Values.
- Double quotes around attribute values are the most common in HTML, but single quotes can also be used.
- In some situations, when the attribute value itself contains double quotes, it is necessary to use single quotes.

## Headings

- HTML headings are titles or subtitles that you want to display on a webpage.
- HTML headings are defined with the `<h1>` to `<h6>` tags.
- `<h1>` defines the most important heading. `<h6>` defines the least important heading.
  ```html
  <h1>Heading 1</h1>
  <h2>Heading 2</h2>
  <h3>Heading 3</h3>
  <h4>Heading 4</h4>
  <h5>Heading 5</h5>
  <h6>Heading 6</h6>
  ```
- Browsers automatically add some white space (a margin) before and after a heading.
- Headings are important:
  - Search engines use the headings to index the structure and content of your web pages.
  - Users often skim a page by its headings. It is important to use headings to show the document structure.
  - `<h1>` headings should be used for main headings, followed by `<h2>` headings, then the less important `<h3>`, and so on.
- Use HTML headings for headings only. Don't use headings to make text BIG or bold.
- Each HTML heading has a default size. However, you can specify the size for any heading with the CSS font-size property. 

## Paragraphs

  - The HTML `<p>` element defines a paragraph.
  - A paragraph always starts on a new line, and is usually a block of text. Browsers automatically add some white space (a margin) before and after a paragraph.
    ```html
    <p>This is a paragraph.</p>
    <p>This is another paragraph.</p>
    ```
  - You cannot be sure how HTML will be displayed.
  - Large or small screens, and resized windows will create different results.
  - With HTML, you cannot change the display by adding extra spaces or extra lines in your HTML code.
  - The browser will automatically remove any extra spaces and lines when the page is displayed:
    ```html
    <p>
      This paragraph
      contains a lot of lines
      in the source code,
      but the browser
      ignores it.
    </p>

    <p>
      This paragraph
      contains         a lot of spaces
      in the source         code,
      but the        browser
      ignores it.
    </p>    
    ```  

## Horizontal Rules

- The `<hr>` tag defines a thematic break in an HTML page, and is most often displayed as a horizontal rule.
- The `<hr>` tag is an empty tag, which means that it has no end tag.
- The `<hr>` element is used to separate content (or define a change) in an HTML page:
  ```html
  <h1>This is heading 1</h1>
  <p>This is some text.</p>
  <hr>
  <h2>This is heading 2</h2>
  <p>This is some other text.</p>
  <hr>
  ```

## Line Breaks

- The HTML `<br>` element defines a line break.
- The `<br>` tag is an empty tag, which means that it has no end tag.
- Use `<br>` if you want a line break (a new line) without starting a new paragraph:
  ```html
  <p>This is<br>a paragraph<br>with line breaks.</p>
  ```

## The Poem Problem

- The HTML `<pre>` element defines preformatted text.
- The text inside a `<pre>` element is displayed in a fixed-width font (usually Courier), and it preserves both spaces and line breaks:
  ```html
  <pre>
    My Bonnie lies over the ocean.
    My Bonnie lies over the sea.
    My Bonnie lies over the ocean.
    Oh, bring back my Bonnie to me.
  </pre>
  ```

## Style Attribute

- The HTML style attribute is used to add styles to an element, such as color, font, size, and more.
- Setting the style of an HTML element, can be done with the style attribute.
- The HTML style attribute has the following syntax:
  ```html
  <tagname style="property:value;">
  ```
- The property is a CSS property. The value is a CSS value.
  ```html
  <body style="background-color:powderblue;">

  <h1 style="background-color:powderblue;">This is a heading</h1>
  <p style="background-color:tomato;">This is a paragraph.</p>

  <h1 style="color:blue;">This is a heading</h1>
  <p style="color:red;">This is a paragraph.</p>

  <h1 style="font-family:verdana;">This is a heading</h1>
  <p style="font-family:courier;">This is a paragraph.</p>  

  <h1 style="font-size:300%;">This is a heading</h1>
  <p style="font-size:160%;">This is a paragraph.</p>  

  <h1 style="text-align:center;">Centered Heading</h1>
  <p style="text-align:center;">Centered paragraph.</p>  

  </body>
  ```

## Formatting

- HTML contains several elements for defining text with a special meaning.
- Formatting elements were designed to display special types of text:
  - `<b>` - Bold text
  - `<strong>` - Important text
  - `<i>` - Italic text
  - `<em>` - Emphasized text
  - `<mark>` - Marked text
  - `<small>` - Smaller text
  - `<del>` - Deleted text
  - `<ins>` - Inserted text
  - `<sub>` - Subscript text
  - `<sup>` - Superscript text
- The HTML `<b>` element defines bold text, without any extra importance.
  ```html
  <b>This text is bold</b>
  ```
- The HTML `<strong>` element defines text with strong importance. The content inside is typically displayed in bold.
  ```html
  <strong>This text is important!</strong>
  ```
- The HTML `<i>` element defines a part of text in an alternate voice or mood. The content inside is typically displayed in italic.
- Tip: The `<i>` tag is often used to indicate a technical term, a phrase from another language, a thought, a ship name, etc.
  ```html
  <i>This text is italic</i>
  ```
- The HTML `<em>` element defines emphasized text. The content inside is typically displayed in italic.
- Tip: A screen reader will pronounce the words in `<em>` with an emphasis, using verbal stress.
  ```html
  <em>This text is emphasized</em>
  ```
- The HTML `<small>` element defines smaller text:
  ```html
  <small>This is some smaller text.</small>
  ```
- The HTML `<mark>` element defines text that should be marked or highlighted:
  ```html
  <p>Do not forget to buy <mark>milk</mark> today.</p>
  ```
- The HTML `<del>` element defines text that has been deleted from a document. Browsers will usually strike a line through deleted text:
  ```html
  <p>My favorite color is <del>blue</del> red.</p>
  ```
- The HTML `<ins>` element defines a text that has been inserted into a document. Browsers will usually underline inserted text:
  ```html
  <p>My favorite color is <ins>red</ins>.</p>
  ```
- The HTML `<sub>` element defines subscript text. Subscript text appears half a character below the normal line, and is sometimes rendered in a smaller font. Subscript text can be used for chemical formulas:
  ```html
  <p>This is <sub>subscripted</sub> text.</p>
  ```
- The HTML `<sup>` element defines superscript text. Superscript text appears half a character above the normal line, and is sometimes rendered in a smaller font. Superscript text can be used for footnotes:
  ```html
  <p>This is <sup>superscripted</sup> text.</p>
  ```

## Comments

- HTML comments are not displayed in the browser, but they can help to document your HTML source code.
- Notice that there is an exclamation point (!) in the start tag, but not in the end tag.
- With comments you can place notifications and reminders in your HTML code.
- Comments can be helpful if you wish to hide html content temporarily. 
- You can also hide more than one line. Everything between the <!-- and the --> will be hidden from the display.
- Comments are also great for debugging HTML, because you can comment out HTML lines of code, one at a time, to search for errors.
- Comments can be used to hide parts in the middle of the HTML code.
- You can add comments to your HTML source by using the following syntax:
  ```html
  <!-- Write your comments here -->

  <!-- This is a comment -->
  <p>This is a paragraph.</p>
  <!-- Remember to add more information here -->

  <p>This is a paragraph.</p>
  <!-- <p>This is another paragraph </p> -->
  <p>This is a paragraph too.</p>

  <p>This is a paragraph.</p>
  <!--
    <p>Look at this cool image:</p>
    <img border="0" src="salman.jpg" alt="salman">
  -->
  <p>This is a paragraph too.</p>
  ```

## CSS

- CSS stands for Cascading Style Sheets.
- CSS saves a lot of work. It can control the layout of multiple web pages all at once.
- Cascading Style Sheets (CSS) is used to format the layout of a webpage.
- With CSS, you can control the color, font, the size of text, the spacing between elements, how elements are positioned and laid out, what background images or background colors are to be used, different displays for different devices and screen sizes, and much more!
- Tip: The word cascading means that a style applied to a parent element will also apply to all children elements within the parent. So, if you set the color of the body text to "blue", all headings, paragraphs, and other text elements within the body will also get the same color (unless you specify something else)!
- CSS can be added to HTML documents in 3 ways:
  - Inline - by using the style attribute inside HTML elements
  - Internal - by using a `<style>` element in the `<head>` section
  - External - by using a `<link>` element to link to an external CSS file
- The most common way to add CSS, is to keep the styles in external CSS files. However, in this tutorial we will use inline and internal styles, because this is easier to demonstrate, and easier for you to try it yourself.
- An inline CSS is used to apply a unique style to a single HTML element.
- An inline CSS uses the style attribute of an HTML element.
- The following example sets the text color of the `<h1>` element to blue, and the text color of the `<p>` element to red:
  ```html
  <h1 style="color:blue;">A Blue Heading</h1>
  <p style="color:red;">A red paragraph.</p>
  ```
- An internal CSS is used to define a style for a single HTML page.
- An internal CSS is defined in the `<head>` section of an HTML page, within a `<style>` element.
- The following example sets the text color of ALL the `<h1>` elements (on that page) to blue, and the text color of ALL the `<p>` elements to red. In addition, the page will be displayed with a "powderblue" background color: 
  ```html
  <!DOCTYPE html>
  <html>
    <head>
      <style>
        body {background-color: powderblue;}
        h1   {color: blue;}
        p    {color: red;}
      </style>
    </head>

    <body>
      <h1>This is a heading</h1>
      <p>This is a paragraph.</p>
    </body>
  </html>
  ```
- An external style sheet is used to define the style for many HTML pages.
- To use an external style sheet, add a link to it in the `<head>` section of each HTML page:
  ```html
  <!DOCTYPE html>
  <html>
    <head>
      <link rel="stylesheet" href="styles.css">
    </head>
    <body>
      <h1>This is a heading</h1>
      <p>This is a paragraph.</p>
    </body>
  </html>
  ```
- The external style sheet can be written in any text editor. The file must not contain any HTML code, and must be saved with a .css extension.
- Here is what the "styles.css" file looks like:
  ```css
  body {
    background-color: powderblue;
  }
  h1 {
    color: blue;
  }
  p {
    color: red;
  }
  ```
- Tip: With an external style sheet, you can change the look of an entire web site, by changing one file!
- External style sheets can be referenced with a full URL or with a path relative to the current web page.
  ```html
  <link rel="stylesheet" href="https://www.spssn.com/css/style.css">
  <link rel="stylesheet" href="/css/styles.css">
  ```

## Links

- Links are found in nearly all web pages. Links allow users to click their way from page to page.
- HTML links are hyperlinks.
- You can click on a link and jump to another document.
- When you move the mouse over a link, the mouse arrow will turn into a little hand.
- Note: A link does not have to be text. A link can be an image or any other HTML element!
- The HTML `<a>` tag defines a hyperlink. It has the following syntax:
  ```html
  <a href="url">link text</a>
  ```
- The most important attribute of the `<a>` element is the href attribute, which indicates the link's destination.
- The link text is the part that will be visible to the reader.
- Clicking on the link text, will send the reader to the specified URL address.
- Links can of course be styled with CSS, to get another look!
- By default, the linked page will be displayed in the current browser window. To change this, you must specify another target for the link.
- The target attribute specifies where to open the linked document.
- The target attribute can have one of the following values:
  - _self - Default. Opens the document in the same window/tab as it was clicked
  - _blank - Opens the document in a new window or tab
  - _parent - Opens the document in the parent frame
  - _top - Opens the document in the full body of the window
  ```html
  <a href="https://www.w3schools.com/" target="_blank">Visit W3Schools!</a>
  ```
- We can give absolute URL (a full web address) and relative URL (without the "https://www" part) in the href attribute.
  ```html
  <h2>Absolute URLs</h2>
  <p><a href="https://www.w3.org/">W3C</a></p>
  <p><a href="https://www.google.com/">Google</a></p>

  <h2>Relative URLs</h2>
  <p><a href="html_images.asp">HTML Images</a></p>
  <p><a href="/css/default.asp">CSS Tutorial</a></p>
  ```
- To use an image as a link, just put the `<img>` tag inside the `<a>` tag:
  ```html
  <a href="default.asp">
    <img src="smiley.gif" alt="HTML tutorial" style="width:42px;height:42px;">
  </a>
  ```
- Link to an Email Address : Use **mailto:** inside the `href` attribute to create a link that opens the user's email program (to let them send a new email):
  ```html
  <a href="mailto:someone@example.com">Send email</a>
  ```
- Button as a Link : To use an HTML button as a link, you have to add some JavaScript code.
- JavaScript allows you to specify what happens at certain events, such as a click of a button:
  ```html
  <button onclick="document.location='default.asp'">HTML Tutorial</button>
  ```
- The title attribute specifies extra information about an element. The information is most often shown as a tooltip text when the mouse moves over the element.
  ```html
  <a href="https://www.w3schools.com/html/" title="Go to W3Schools HTML section">Visit our HTML Tutorial</a>
  ```
- An HTML link is displayed in a different color depending on whether it has been visited, is unvisited, or is active.
- By default, a link will appear like this (in all browsers):
  - An unvisited link is underlined and blue
  - A visited link is underlined and purple
  - An active link is underlined and red
- You can change the link state colors, by using CSS:
  ```css
  <style>
    a:link {
      color: green;
      background-color: transparent;
      text-decoration: none;
    }

    a:visited {
      color: pink;
      background-color: transparent;
      text-decoration: none;
    }

    a:hover {
      color: red;
      background-color: transparent;
      text-decoration: underline;
    }

    a:active {
      color: yellow;
      background-color: transparent;
      text-decoration: underline;
    }
  </style>
  ```
- HTML links can be used to create bookmarks, so that readers can jump to specific parts of a web page.
- Bookmarks can be useful if a web page is very long.
- To create a bookmark - first create the bookmark, then add a link to it.
- When the link is clicked, the page will scroll down or up to the location with the bookmark.
- First, use the id attribute to create a bookmark.
- Then, add a link to the bookmark ("Jump to Chapter 4"), from within the same page.
- You can also add a link to a bookmark on another page.
  ```html
  <h2 id="C4">Chapter 4</h2>
  <a href="#C4">Jump to Chapter 4</a>

  <a href="html_demo.html#C4">Jump to Chapter 4</a>
  ```
- Use the id attribute (id="value") to define bookmarks in a page.
- Use the href attribute (href="#value") to link to the bookmark.

## Images

- Images can improve the design and the appearance of a web page.
- The HTML `<img>` tag is used to embed an image in a web page.
- Images are not technically inserted into a web page; images are linked to web pages. The `<img>` tag creates a holding space for the referenced image.
- The `<img>` tag is empty, it contains attributes only, and does not have a closing tag.
- The `<img>` tag has two required attributes:
  ```html
  <img src="url" alt="alternatetext">
  ```
  - src - Specifies the path to the image
  - alt - Specifies an alternate text for the image
- The required src attribute specifies the path (URL) to the image.
- Note: When a web page loads, it is the browser, at that moment, that gets the image from a web server and inserts it into the page. Therefore, make sure that the image actually stays in the same spot in relation to the web page, otherwise your visitors will get a broken link icon. The broken link icon and the alt text are shown if the browser cannot find the image.
- The required alt attribute provides an alternate text for an image, if the user for some reason cannot view it (because of slow connection, an error in the src attribute, or if the user uses a screen reader).
- The value of the alt attribute should describe the image.
- If a browser cannot find an image, it will display the value of the alt attribute.
- You can use the style attribute to specify the width and height of an image.
- Alternatively, you can use the width and height attributes.
- The width and height attributes always define the width and height of the image in pixels.
  ```html
  <img src="img_girl.jpg" alt="Girl in a jacket" style="width:500px;height:600px;">
  <img src="img_girl.jpg" alt="Girl in a jacket" width="500" height="600">
  ```
- The width, height, and style attributes are all valid in HTML.
- However, we suggest using the style attribute. It prevents styles sheets from changing the size of images.
- If you have your images in a sub-folder, you must include the folder name in the src attribute.
- Some web sites point to an image on another server.
- To point to an image on another server, you must specify an absolute (full) URL in the src attribute.
- External images might be under copyright. If you do not get permission to use it, you may be in violation of copyright laws. In addition, you cannot control external images; they can suddenly be removed or changed.
  ```html
  <img src="/images/html5.gif" alt="HTML5 Icon" style="width:128px;height:128px;">
  <img src="https://www.w3schools.com/images/w3schools_green.jpg" alt="W3Schools.com">
  <img src="programming.gif" alt="Computer Man" style="width:48px;height:48px;">
  ```
- To use an image as a link, put the `<img>` tag inside the `<a>` tag.
  ```html
  <a href="default.asp">
    <img src="smiley.gif" alt="HTML tutorial" style="width:42px;height:42px;">
  </a>
  ```
- Use the CSS float property to let the image float to the right or to the left of a text.
  ```html
  <p><img src="smiley.gif" alt="Smiley face" style="float:right;width:42px;height:42px;">
  The image will float to the right of the text.</p>

  <p><img src="smiley.gif" alt="Smiley face" style="float:left;width:42px;height:42px;">
  The image will float to the left of the text.</p>
  ```

## Picture Element

- The HTML `<picture>` element allows you to display different pictures for different devices or screen sizes.
- The HTML `<picture>` element gives web developers more flexibility in specifying image resources.
- The `<picture>` element contains one or more `<source>` elements, each referring to different images through the srcset attribute. This way the browser can choose the image that best fits the current view and/or device.
- Each `<source>` element has a media attribute that defines when the image is the most suitable.
- Always specify an `<img>` element as the last child element of the `<picture>` element. The `<img>` element is used by browsers that do not support the `<picture>` element, or if none of the `<source>` tags match.
- There are two main purposes for the `<picture>` element:
  - Bandwidth : If you have a small screen or device, it is not necessary to load a large image file. The browser will use the first `<source>` element with matching attribute values, and ignore any of the following elements.
  - Format Support : Some browsers or devices may not support all image formats. By using the `<picture>` element, you can add images of all formats, and the browser will use the first format it recognizes, and ignore any of the following elements.
  ```html
  <picture>
    <source srcset="img_avatar.png">
    <source srcset="img_girl.jpg">
    <img src="img_beatles.gif" alt="Beatles" style="width:auto;">
  </picture>
  ```
- The browser will use the first `<source>` element with matching attribute values, and ignore any following `<source>` elements.

## Favicon

- A favicon is a small image displayed next to the page title in the browser tab.
- You can use any image you like as your favicon. You can also create your own favicon on sites like https://www.favicon.cc.
- A favicon is a small image, so it should be a simple image with high contrast.
- To add a favicon to your website, either save your favicon image to the root directory of your webserver, or create a folder in the root directory called images, and save your favicon image in this folder. A common name for a favicon image is "favicon.ico".
- Next, add a `<link>` element to your "index.html" file, after the `<title>` element, like this:
  ```html
  <head>
    <title>My Page Title</title>
    <link rel="icon" type="image/x-icon" href="/images/favicon.ico">
  </head>
  ```
- Now, save the "index.html" file and reload it in your browser. Your browser tab should now display your favicon image to the left of the page title.

## Page Title

- Every web page should have a page title to describe the meaning of the page.
- The title should describe the content and the meaning of the page.
- The page title is very important for search engine optimization (SEO). The text is used by search engine algorithms to decide the order when listing pages in search results.
- The `<title>` element:
  - defines a title in the browser toolbar
  - provides a title for the page when it is added to favorites
  - displays a title for the page in search engine-results
  - So, try to make the title as accurate and meaningful as possible!
  ```html
  <head>
    <title>HTML Tutorial</title>
  </head>
  ```

## Tables

- HTML tables allow web developers to arrange data into rows and columns.
- A table in HTML consists of table cells inside rows and columns.
- Each table cell is defined by a `<td>` and a `</td>` tag.
- Everything between `<td>` and `</td>` are the content of the table cell.
- A table cell can contain all sorts of HTML elements: text, images, lists, links, other tables, etc.
- Each table row starts with a `<tr>` and ends with a `</tr>` tag.
- tr stands for table row.
- You can have as many rows as you like in a table; just make sure that the number of cells are the same in each row.
- Sometimes you want your cells to be table header cells. In those cases use the `<th>` tag instead of the `<td>` tag.
- th stands for table header.
- By default, the text in `<th>` elements are bold and centered, but you can change that with CSS.
  ```html
  <table>
    <tr>
      <th>Company</th>
      <th>Contact</th>
      <th>Country</th>
    </tr>
    <tr>
      <td>Alfreds Futterkiste</td>
      <td>Maria Anders</td>
      <td>Germany</td>
    </tr>
    <tr>
      <td>Centro comercial Moctezuma</td>
      <td>Francisco Chang</td>
      <td>Mexico</td>
    </tr>
  </table>
  ```
- HTML tables can have borders of different styles and shapes.
- When you add a border to a table, you also add borders around each table cell.
- To add a border, use the CSS border property on table, th, and td elements.
  ```css
  table, th, td {
    border: 1px solid black;
  }
  ```
- To avoid having double borders like in the example above, set the CSS border-collapse property to collapse.
- This will make the borders collapse into a single border.
  ```css
  table, th, td {
    border: 1px solid black;
    border-collapse: collapse;
  }
  ```
- If you set a background color of each cell, and give the border a white color (the same as the document background), you get the impression of an invisible border.
  ```css
  table, th, td {
  border: 1px solid white;
  border-collapse: collapse;
  }
  th, td {
    background-color: #96D4D4;
  }
  ```
- With the border-radius property, the borders get rounded corners.
  ```css
  table, th, td {
    border: 1px solid black;
    border-radius: 10px;
  }
  ```
- With the border-style property, you can set the appearance of the border.
  ```css
  th, td {
    border-style: dotted;
  }
  ```
- With the border-color property, you can set the color of the border.
  ```css
  th, td {
    border-color: #96D4D4;
  }
  ```
- HTML tables can have different sizes for each column, row or the entire table.
- Use the style attribute with the width or height properties to specify the size of a table, row or column.
- To set the width of a table, add the style attribute to the `<table>` element. 
- To set the size of a specific column, add the style attribute on a `<th>` or `<td>` element.
- To set the height of a specific row, add the style attribute on a table row element.
  ```html
  <table style="width:100%">
    <tr>
      <th style="width:70%">Firstname</th>
      <th>Lastname</th>
      <th>Age</th>
    </tr>
    <tr style="height:200px">
      <td>Jill</td>
      <td>Smith</td>
      <td>50</td>
    </tr>
    <tr>
      <td>Eve</td>
      <td>Jackson</td>
      <td>94</td>
    </tr>
  </table>
  ```
- Table headers are defined with th elements. Each th element represents a table cell.
- By default, table headers are bold and centered.
- To left-align the table headers, use the CSS text-align property.
  ```css
  th {
    text-align: left;
  }
  ```
- You can have a header that spans over two or more columns.
- To do this, use the colspan attribute on the `<th>` element.
- You can add a caption that serves as a heading for the entire table.
- The `<caption>` tag should be inserted immediately after the `<table>` tag.
  ```html
  <table style="width:100%">
    <caption>Monthly savings</caption>
    <tr>
      <th>Month</th>
      <th>Savings</th>
    </tr>
  </table>
  ```
- Cell padding is the space between the cell edges and the cell content.
- By default the padding is set to 0.
- To add padding on table cells, use the CSS padding property.
- To add padding only above the content, use the padding-top property.
- And the others sides with the padding-bottom, padding-left, and padding-right properties.
- Cell spacing is the space between each cell.
- By default the space is set to 2 pixels.
- To change the space between table cells, use the CSS border-spacing property on the table element.
  ```css
  th, td {
    padding: 15px;
  }
  th, td {
    padding-top: 10px;
    padding-bottom: 20px;
    padding-left: 30px;
    padding-right: 40px;
  }
  table {
    border-spacing: 30px;
  }
  ```
- To make a cell span over multiple columns, use the colspan attribute.
- The value of the colspan attribute represents the number of columns to span.
- To make a cell span over multiple rows, use the rowspan attribute.
- The value of the rowspan attribute represents the number of rows to span.
  ```html
  <table>
    <tr>
      <th colspan="2">Name</th>
      <th>Age</th>
    </tr>
    <tr>
      <th rowspan="2">Phone</th>
      <td>555-1234</td>
    </tr>
    <tr>
      <td>555-8745</td>
    </tr>
  </table>
  ```
- If you add a background color on every other table row, you will get a nice zebra stripes effect.
- To style every other table row element, use the :nth-child(even) selector.
- To make vertical zebra stripes, style every other column, instead of every other row.
- Put the :nth-child() selector on both th and td elements if you want to have the styling on both headers and regular table cells.
- Add the border-bottom property to all tr elements to get horizontal dividers.
- Use the :hover selector on tr to highlight table rows on mouse over.
  ```css
  tr:nth-child(even) {
    background-color: rgba(150, 212, 212, 0.4);
  }

  th:nth-child(even),td:nth-child(even) {
    background-color: rgba(150, 212, 212, 0.4);
  }

  tr {
    border-bottom: 1px solid #ddd;
  }
  
  tr:hover {background-color: #D6EEEE;}
  ```