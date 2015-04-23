### SWABATs

+ CSS - understand how to use descendant, children, sibling and precedent selectors
+ CSS - understand universal, attribute and pseudo selectors
+ CSS - understand authority and inheritance rules
+ CSS - utilize text declarations
+ CSS - How to create their own image sprites and render different versions based on hover state.
+ CSS - understand how to use scaling elements - px, em, % - and min and max
+ CSS - Understand what a sprite it
+ CSS - understand how to use Z index property for layering
+ CSS - include comments
+ HTML - understand how to use HTML5 audio and video tags
+ CSS - understand how to use gradient and how to make it cross-browser friendly
+ CSS - Use background properties for box styling
+ CSS - understand how to use opacity and how to make it cross-browser friendly
+ CSS - understand and utilize border property for box styling, including border radius and box shadow

###Motivation
We’re starting to make some complex HTML pages and sometimes you need to get really specific about the element you are styling. Today we are going to go into more depth about how to use selectors to be very specific about styling elements on the page and keep our CSS stylesheets nice and clean.

We’re also going to help you pimp out your site with box styles, audio and video tags, and sprites! 

###Lesson Plan
<b>CSS SELECTORS</b>

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
+ The descendent selector is targeting this second selector listed (li in the example above). What this css is saying is - target only those li’s that are nested within #nav. This means any and all li elements. So if there is a list within a list like this:
	+ `<ul id="nav”>`
	  +  `<li>child`
	    +  `<ul><li>grandchild</li></ul>`
	   + `</li>`
	+ `</ul>`
+ It will target not only the child in li it will also affect the grandchild
+ If you want to be more specific and only target direct descendants (just the child) in the example above you can use the child selector `#list > li {…}`. If you do this the grandchildren will not be affected by any CSS you specify here.
+ The sibling selector is very specific - like the child selector - but it does not depend on nested elements. It targets the next element that comes after. In this example h3 + p {…} only the p element directly following the h3 element will be styled
	+ `<h3>An h3 Element</h3>`
	+ `<p>I'm a p directly after an h3 element.</p>`
	+ `<p>Not selected</p>`
+ The more general sibling selector is called the precedent selector. It will target all the siblings following an indicated selector - not just the one immediately following the selector. It does NOT affect siblings that are nested within another element though. Here is an example of how 
	+ .pre ~ h2 { 
	+ color:red;
	+ }
+ Would affect this text:
	+ `<p class="pre">I’m the pre div.</p>`
	+ `<h2>I'm an h2 positioned after the pre div</h2>`
	+ `<h2>Me too!</h2>`
	+ `<div>`
	`<h2>I’m nested within another element so I won’t be affected by the precedent style</h2>`
	+ `</div>`
+ There are a few other helpful selectors that we can use: Universal * {…}, Attribute img[alt="Cat"] {…} and Pseudo selectors li:first-child {…}, a:link {…}
+ The universal selector will do exactly what you think it will. It will affect every element on the page. 
+ The attribute selector will look for tags that have a certain attribute. Like this:
	+ img[alt="Cat"] { 
    	+ border: 1px solid black;
	+ }
+ `<img src="myimage.jpg" alt="Cat">` <!-- this will have a solid black border -->
The attribute selector can really help you target elements in unique ways. Examples:
<img src="https://s3.amazonaws.com/after-school-assets/css-selector1.png">
+ Pseudo class selectors are especially helpful in styling links. For example:
<img src= "https://s3.amazonaws.com/after-school-assets/css-selector2.png">
+ Cleaning up and streamlining your CSS stylesheet is another way to make it easier to keep track of which elements you are styling and make sure you are targeting the right elements. If there are several things on the page that you want styled in a similar fashion you can use compound selectors. For example, if I want all my h2 and h3 tags to be purple I can indicate that like this:
	+ h2, h3 {
		color: purple;
	+ }
+ One last important bit of CSS are the rules around authority and inheritance.
+ If you use conflicting styles on the same element, ID over rules class which overrules type which over rules * (universal). 
	+ Generally the more specific a selector the more authority it has. If a more specific selector is not defined for an element it will inherit styles from a previously defined general selector statement.
+ If multiple Classes are applied to the same element the Class listed furthest to the right overrules its neighbors to the left.
+ Uses “last man” rule. When conflicts with equal authority arise, CSS will listen to the last style it was told to apply. 
+ Now you know everything about CSS! <b>Go practice with the Graffiti lab and try using your new skills on your personal page.</b>

<b>Adding box styles</b>
+ We’ve covered changing the background color and adding a background image but here is a list of properties that you can give it:
	
	+ background-color: black | #fff | rgba(0,0,0,1);
	+ background-image: url(myimage.jpg);
	+ background-position: top left;
	+ background-repeat: repeat | repeat-x | repeat-y | no-repeat;
	+ background-scroll: fixed | scroll;
	+ background-size: 100% | 1px | 1em | contain | cover;
	+ background: white url(myimage.jpg) no-repeat;
+ A few cool properties to point out:
	+ background-scroll - if you set it to fixed you’ll have a fixed image background which can be nice
	+ background-size: cover can be used to resize your image to cover the page
	+ background - you can use this to apply the top 4 properties at once
+ We’ve mentioned borders but here is a review of how it works:
	+ border-size: 1% | 1px | 1em;
	+ border-color: blue | #00f | rgba(0,0,255,1);
	+ border-style: solid | dashed | dotted | double | groove | ridge | inset | outset;
	+ border: 1px solid #000;
+ Notice there are lots of options for border-style and that there is a border property that can be used to set all properties at once.
+ We can also set how our corners look and round out their edges a bit with border-radius property.
+ Here are some examples of how you can modify the look of your divs with the border radius property:
<img src= "https://s3.amazonaws.com/after-school-assets/css-selector3.png">
+ Not all browsers support border radius so we use something called browser prefixes to make sure that out CSS is compatible across browsers:
	+ -webkit-border-radius: 20px;
	+ -moz-border-radius: 20px;
	+ border-radius: 20px;
+ We can also set box shadows on our divs like this:
<img src="https://s3.amazonaws.com/after-school-assets/css-selector4.png">
+ Explain each of the properties and emphasize the prefixes.
+ We can also set the opacity of our div for effects like this:
<img src="https://s3.amazonaws.com/after-school-assets/css-selector5.png">
+ Here are the ways that you can do that for different browsers:
	+ filter: alpha(opacity=50); /* IE*/
	+ -moz-opacity: 0.5; /* Older than Firefox 0.9 */
	+ -khtml-opacity: 0.5; /* Safari 1.x (pre WebKit!) */
	+ opacity: 0.5; /* Modern! */
+ One last thing that we can do is set a gradient to the background of our divs. 
+ Here are some examples of how we would do that:
	+ background-color: #F47A20;
	+ background-image: -moz-linear-gradient( #FAA51A, #F47A20);
	+ background-image: -webkit-gradient( linear, 0 0, 0 100%,
	+ color-stop( 0, #FAA51A), color-stop( 1, #F47A20) );
+ It’s way easier to just use a gradient generator like this: http://www.colorzilla.com/gradient-editor/ 
+ Get Grover’s jsfiddle to use as examples for all these things.

<b>Embedding Audio and Video</b>
+ HTML5 makes it super easy to embed video and audio into your website with these tags:

+ Audio:
 
 		<audio>
     		<source src="audio.mp3" type="audio/mp3">
     		<source src="audio.ogg" type="audio/ogg”> 
     		<!-– fallback content here -->
	 	</audio>

+ Video

		<video>
	    	<source src="movie.mp4" type="video/mp4">
	   	 	<source src="movie.ogv" type="video/ogg">
	    	<source src="movie.webm" type="video/webm”>
	   		<!-– fall back content here -->
	   	</video>
	   
+ The fallback content is important because there are still old browsers out there that are not good at handling HTML5 audio and video elements.
+ A great resource for checking out HTML5 compatibility across browsers is http://caniuse.com/
+ <b>Try adding an audio or video to your personal website.</b>

<b>Design Principles - typography</b>
+ What is typography? Typography can simply be described as the art of type. It's everything you can think of – like fonts, sizes, and readability.
+ The basics

<img src="https://s3.amazonaws.com/after-school-assets/css-selector6.png">

+ <b>Sizing</b>
	+ The Type Size, also called the Cap Height, is the overall height of capital letters in the formation of words.
	+ The Ascender is the upward tail on letters like h, l, t, b, d, and k.
	+ The Descender is the downward tail for letters like g, q, and y.
	+ The Counter is the white space located inside letters like o and p.
	+ The X Height is the height of the letter, and does not include ascenders or descenders.
	+ Baselines are the boundary that the lowest part of the letter rests on. Take a look at the y, p, g, p and y letters in the illustration above. The solid line they are resting on is the baseline.
+ <b>Kerning</b>
+ Have you ever seen a paragraph or advertisement that made the letters appear either s p a c e d w a y out or scrunched all up so it was hard to read? The effective use of kerning and leading will fix that problem. Kerning is the space located between individual letters of a word. If you can remember the kernels on an ear of corn, it’s easy. When the kernels of corn line up, it makes a nice neat row.
+ If the kerning is off, so will the appearance of the word or line of text you are working with and it will be harder to read.
<img src ="https://s3.amazonaws.com/after-school-assets/css-selector7.png">
	+ Leading is the space between the lines of text. If you look at the illustration above, you will quickly notice the space between line one and two is too close, giving the impression of not enough space. By adjusting the amount of leading between lines, the text becomes much more readable and less pinched.
	+ How do you want your text to line up? Is this a standard body of text, a headline or are you in need of a more professional finish? Depending on the type alignment, you may inadvertently create the wrong impact based solely on the placement of your message.
+ <b>Type Alignment</b>
	+ Default writing techniques will use left alignment to create easy to read text for the reader. Casual letters, unpublished manuscripts, and basic paragraph styles tend to fall into this category.
	+ Center alignment is used to draw attention and is used a majority of the time for Headlines or Titles. Newspaper headers, book titles, and report titles are excellent examples of center alignment.
	+ Right Alignment is a clean crisp professional look and is used quite a bit for corporate business letters, return address labels, business cards and a variety of other applications where a formal style of alignment is needed.
	+ Justified alignment is usually reserved for newspaper print and body text for textbooks, and is more difficult to work with. This type of alignment creates perfect alignment on both the left and right margins without regard for the actual characters. This can lead to a condition called tracking, or the creation of “rivers” of white space throughout the text body. If this happens, reduce the tracking gradually to correct the illusion.
+ <b>Font</b>
+ Now that we know how to identify the parts, make sure the spacing is correct and we’ve decided on the image we want to portray, selecting what your message will look like is paramount to leaving the gravy off the mashed potatoes at dinner. You’re still going to have a nice dinner, but if you want to get saucy, pick a type category that fits.
	+ <b>Serif</b> type has extensions or strokes on the ends of the letters. Times New Roman is a perfect example of this. This type of font is easy to read for longer pieces and tends to be a little more conservative. If you do not deliberately choose another font, most programs default to the Times New Roman style.
	+ <b>San-Serif</b> does not have extensions or strokes on the ends of the letters and are used heavily for labeling, headlines and titles. This is also easy to read with a more contemporary feel to it. Children’s books use this because it is more easily identifiable as children are learning the alphabet.
	+ <b>Script,</b> symbols and decorative type are all styles of type categories to create a specific image or message. Weddings might lean more toward the fluid motion of a script type while a child’s birthday might be more inclined to like a decorative font from a favorite movie.
+ Whatever font family you choose bears careful consideration in the design of any piece. Here are a few suggestions to get you started:
+ The font you decide on should not dominate the piece. Fonts are like exquisite jewelry to be placed in just the right context to insure maximum results.
+ <b>Tips</b>
	+ Use care when mixing fonts. It’s kind of like mixing stripes and plaids. When in doubt, stay with something a little more conservative then add one splash of notice me.
	+ Use consistency in your layouts. If you start out using an Arial font for the headers, stay with the same font throughout the piece.
	+ Newsletters with columns will look better if you use the Justified Alignment. Make sure you don’t create rivers of white space though.
	+ Use an 11 or 12 point font size and a serif type for maximum readability.
	+ Use Italics and Bold to point out areas of interest or draw quick reference to information.
	+ Use color for emphasis. Remember, reds draw the most attention if used correctly. It is amazing what one spot of red can do for an ordinary ad.
+ Next time while reading your favorite blog or newspaper, observe the fonts, line heights (the distance between each line), line lengths (how many letters per line), and font weights (bold, normal, light). CSS3 gives you great control over fonts and text, so an understanding of the basic rules of typography will come in handy as you design and build websites.
+ <b>Steve Jobs calligraphy story</b>

<b>Sprites and Rollovers</b>

+ Another way to spice up  your website is with sprite rollovers.
+ The most common place that you’ll see this is with buttons or links that will change when you hover over them.
+ The best way to do this is to upload one file with multiple images. This jpeg will by default be positioned as a background image then you can add a pseudo class like a:hover that changes the position of the image to display the other sprite. 
+ Here is some sample code:
	+ a {
	+ display: block;
	+ width: 30px;
	+ height: 30px;
	+ background: url(sprite.png) no-repeat;
	+ }
	+ a:hover {
	    + background-position: 0 -30px;
	+ }
+ Give it a shot with the sprite lab on Learn.co.
