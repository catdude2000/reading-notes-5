# reading-notes-5
Notes for ch 5 reading


CSS (Cascading StyleSheets)
  Browser sometimes called "user agent" (program that represents a person inside a computer system
also other agents available

Syntax
  CSS is a rule-based language — you define rules specifying groups of styles that should be applied
to particular elements or groups of elements on your web page.
ex: Red header with large text
h1 {
    color: red;
    font-size: 5em;
}
-starts with selector "< h1>"
then curly braces {}
inside braces are declarations in form of "property" and "value" pairs
property: value
The individual property pages on MDN give you a quick way to look up properties and their values
use CSS reference page and get used to searching for "mdn css-feature-name"

Modules
  You'll see reference to these modules as you explore MDN and many of the documentation pages are
organized around a particular module.

Specs
  all web stsndard tech are defined in giant documents called "specifications"
published by standards organizations
CSS is developed by a group within the W3C called the CSS Working Group
invited experts act as independent voices; they are not linked to a member organization
New CSS features are developed, or specified, by the CSS Working Group.

Browser Support Info
Browsers must implement CSS code after it's specified
check implementation status
The browser support status is shown on every MDN property page in a section named "Browser compatibility"



How to add style sheet (CSS)
3 ways:
1. External CSS
2. Internal CSS
3. Inline CSS

External
With an external style sheet, you can change the look of an entire website by changing just one file
  Each HTML page must include a reference to the external style sheet file inside the < link> element, 
inside the head section.
EX:
< !DOCTYPE html>
< html>
< head>
< link rel="stylesheet" href="mystyle.css">
< /head>
< body>

< h1>This is a heading</ h1>
< p>This is a paragraph.< /p>

< /body>
< /html>
  external style sheet can be written with any text editor, needs .css extension
should not contain any HTML tags
EX:"mystyle.css"
body {
  background-color: lightblue;
}

h1 {
  color: navy;
  margin-left: 20px;
}
no space between property value and unit

Internal CSS
internal used if one single html page has unique style
defined inside < style> element in < head> section
Ex:
< !DOCTYPE html>
< html>
< head>
< style>
body {
  background-color: linen;
}
h1 {
  color: maroon;
  margin-left: 40px;
}
</ style>
< /head>
< body>
< h1>This is a heading</ h1>
< p>This is a paragraph.< /p>
</ body>
</ html>

Inline CSS
used to apply unique style for a single element
Ex:
<! DOCTYPE html>
< html>
< body>
< h1 style="color:blue;text-align:center;">This is a heading< /h1>
< p style="color:red;">This is a paragraph.< /p>
< /body>
< /html>

Multple Style sheets
  If some properties have been defined for the same selector (element)in different
style sheets, the value from the last read style sheet will be used. 
  If the internal style is defined after the link to the external style sheet then
the internal is used
Ex:
< head>
< link rel="stylesheet" type="text/css" href="mystyle.css">
< style>
h1 {
  color: orange;
}
< /style>
< /head>

Cascading Order
  When more than one style specified for an html element they'll cascade into
a new "virtual" style sheet by these rules:
1. Inline style (inside an HTML element)
2. External and internal style sheets (in the head section)
3. Browser default


CSS Color
The color property specifies the color of text.

CSS Syntax
color: color|initial|inherit;
Property Values
Value:	Description	
color:	Specifies the text color. 	
initial:	Sets this property to its default value.	
inherit:	Inherits this property from its parent element.
Different value types include HEX, RGB, RGBA, HSL, HSLA

  CSS rule definitions are entirely (ASCII) text-based, 
whereas DOM-CSS / CSSOM (the rule management system) is object-based

Selectors
 allow styles to be conditional based on various features of elements within the DOM.
Basic selectors:
Universal selector *, ns|*, *|*, |*
Type selector elementname
Class selector .classname
ID selector #idname
Attribute selector [ attr=value]

Grouping selectors
Selector list A, B
Specifies that both A and B elements are selected. This is a grouping method to select several matching elements.

Combinators
Combinators are selectors that establish a relationship between two or more simple selectors, such as "A is a child of B" or "A is adjacent to B."

Adjacent sibling combinator A + B
Specifies that the elements selected by both A and B have the same parent and that the element selected by B immediately follows the element selected by A horizontally.
General sibling combinator A ~ B
Specifies that the elements selected by both A and B share the same parent and that the element selected by A comes before—but not necessarily immediately before—the element selected by B.
Child combinator A > B
Specifies that the element selected by B is the direct child of the element selected by A.
Descendant combinator A B
Specifies that the element selected by B is a descendant of the element selected by A, but is not necessarily a direct child.
Column combinator A || B 
Specifies that the element selected by B is located within the table column specified by A. Elements which span multiple columns are considered to be a member of all of those columns.

Pseudo classes :
Specifies a special state of the selected element(s).
Pseudo elements ::
Represents entities that are not included in HTML.

Reset CSS
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