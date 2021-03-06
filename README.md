### SWABATs

+ CSS - understand how to use descendant, children, sibling and precedent selectors
+ CSS - understand universal, attribute and pseudo selectors
+ CSS - understand authority and inheritance rules

###Motivation
We’re starting to make some complex HTML pages and sometimes you need to get really specific about the element you are styling. Today we are going to go into more depth about how to use selectors to be very specific about styling elements on the page and keep our CSS stylesheets nice and clean.

###Lesson Plan
+ We’ve already learned how to use selectors. What are selectors? html tags `<p>`,`<h1>`, etc. and classes and IDs.
+ We can target elements on our page by specifying where one selector is in relation to another with a few different selectors:
	+ Descendent
		+ `#nav li {…}`
	+ Child 
		+ `#list > li {…}`
	+ Sibling
		+ `h3 + p {…}`
	+ Preceded
		+ `.styleafter ~ h2 {…}`
+ The descendent selector is targeting this second selector listed (li in the example above). What this css is saying is - target only those li’s that are nested within `#nav`. This means any and all `li` elements. So if there is a list within a list like this:
```html
	<ul id="nav”>
	  <li>child
	   <ul><li>grandchild</li></ul>
	   </li>
	</ul>
```
+ It will target not only the child in li it will also affect the grandchild
+ If you want to be more specific and only target direct descendants (just the child) in the example above you can use the child selector `#list > li {…}`. If you do this the grandchildren will not be affected by any CSS you specify here.
+ The sibling selector is very specific - like the child selector - but it does not depend on nested elements. It targets the next element that comes after. In this example h3 + p {…} only the p element directly following the h3 element will be styled
	```html
	<h3>An h3 Element</h3>
	<p>I'm a p directly after an h3 element.</p>
	<p>Not selected</p>
	```
+ The more general sibling selector is called the precedent selector. It will target all the siblings following an indicated selector - not just the one immediately following the selector. It does NOT affect siblings that are nested within another element though. Here is an example of how 
	```css
	.pre ~ h2 { 
		color:red;
	}
	```
+ Would affect this text:
	```html
	<p class="pre">I’m the pre div.</p>
	<h2>I'm an h2 positioned after the pre div</h2>
	<h2>Me too!</h2>
	<div>`
		<h2>I’m nested within another element so I won’t be affected by the precedent style</h2>
	</div>
```
+ There are a few other helpful selectors that we can use: Universal `* {…}`, Attribute `img[alt="Cat"] {…}` and Pseudo selectors `li:first-child {…}`, `a:link {…}`
+ The universal selector will do exactly what you think it will. It will affect every element on the page. 
+ The attribute selector will look for tags that have a certain attribute. Like this:
CSS:
	```css
	img[alt="Cat"] { 
    border: 1px solid black;
	 }
	```
	HTML:
	```html
	<img src="myimage.jpg" alt="Cat">` <!-- this will have a solid black border -->
	```
The attribute selector can really help you target elements in unique ways. Examples:

<img src="https://s3.amazonaws.com/after-school-assets/css-selector1.png">

+ Pseudo class selectors are especially helpful in styling links. For example:

<img src= "https://s3.amazonaws.com/after-school-assets/css-selector2.png">

+ Cleaning up and streamlining your CSS stylesheet is another way to make it easier to keep track of which elements you are styling and make sure you are targeting the right elements. If there are several things on the page that you want styled in a similar fashion you can use compound selectors. For example, if I want all my h2 and h3 tags to be purple I can indicate that like this:
```css
	h2, h3 {
		color: purple;
	}
	```
+ One last important bit of CSS are the rules around authority and inheritance.
+ If you use conflicting styles on the same element, ID over rules class which overrules type which over rules * (universal). 
	+ Generally the more specific a selector the more authority it has. If a more specific selector is not defined for an element it will inherit styles from a previously defined general selector statement.
+ If multiple Classes are applied to the same element the Class listed furthest to the right overrules its neighbors to the left.
+ Uses “last man” rule. When conflicts with equal authority arise, CSS will listen to the last style it was told to apply. 
+ Now you know everything about CSS! *Go practice with the Graffiti lab and try using your new skills on your personal page.*

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/hs-intro-web-design-teachers-guide-css-selectors' title='SWABATs'>SWABATs</a> on Learn.co and start learning to code for free.</p>
