# A Slightly Bizarre Starting Point

## A continual work in progress

Okay, so this is just a 'forever in progress' little framework/boilerplate for my own personal consumption.

It fits how I develop 'le web' and because of this I may do things differently to how you do.

* I like my SCSS/CSS set up a little differently.
* I like my HTML <head> set up a particular way.
* I like tabs over spaces
* I like indenting my HTML how I like to do it.

This is not to say don't pull this apart. In fact this 'framework' is the amalgamation of many other boilerplates and frameworks.



## HTML

### Closing HTML tags

At the end of an HTML tag to ease the pain of what div is doing what for example we must 'close' the tag with an HTML comment, like this

	<div class="test">
	
	</di> <!-- /.test -->
	
#### Multiple Classes in use

If you end up have multiple classes for an HTML element then you must separate the classes logically with a forward slash. You must 'close' all the classes in an HTML comment too, like this

	<div class="list / sub-content / comp">
	
	</div> <!-- /.list /.sub-content /.comp -->

## CSS (Sass/SCSS) Styleguide

### CSS Class/ID Naming conventions

Use hypens only

	.large-class-name == good
	.large_class_name == bad
	.largeClassName   == bad
	.largeclassname   == bad

### CSS Commenting

Comment your code with these helpers -
#### OOCSS Module commenting

To aid in writing your CSS without referring to your HTML add the code snippet within this CSS Comment for ease and clarity.

	/*
	 * @description:	/
	 *
	 * @author:	    	/	Stuart Robson
	 * @version:	    /	0.1
	 * @date:	    	/	dd/mm/yyyy
	 *
	 *
	 * @example:		/
	 *
	 *
	 * @type:			/
	 * @notes:			/
	 * @tags:			/	^	^	^	^	^
	 */


#### For Sections

	/*------------------------------------*\
	
	\*------------------------------------*/

and edit it like this

	/*------------------------------------*\
		Typography
	\*------------------------------------*/

##### Section Spacing

For spaces between Major sections allow 3 blank lines -


	/*------------------------------------*\
		headings
	\*------------------------------------*/

		header {
			background: red;
			border: 1px solid white;
			height: 3em;
			position: relative;
		}



	/*------------------------------------*\
		footer
	\*------------------------------------*/

#### For individual Rules

	/* Explanation */

	/* !Flag For Attention! */

#### For completely uncompiled Sass comments

	// Sass/SCSS ONLY comments to be written like this

### Write the CSS using tab indentation.

For Example -

	.example {
		color: #fff;
		font-family: Georgia, "Times New Roman", serif;
		font-weight: bold;
		height: 300px;
		left: 50px;
		line-height: 20px;
		position: relative;
		top: 20px;
		width: 300px;
		z-index: 9;
	}

### Indent any CSS changes for quick error finding.

For Example -

	.example {
		color: #fff;
		font-family: Georgia, "Times New Roman", serif;
		font-weight: bold;
		height: 300px;
	left: 45px;
		line-height: 20px;
		position: relative;
		top: 20px;
		width: 300px;
		z-index: 9;
	}

### Write all CSS rules alphabetically.

This will aid quick error finding (notice the 2 left declarations).

For Example -

	.example {
		color: #fff;
		font-family: Georgia, "Times New Roman", serif;
		font-weight: bold;
		height: 300px;
		left: 50px;
		left: 30px;
		line-height: 20px;
		position: relative;
		top: 20px;
		width: 300px;
		z-index: 9;
	}

### Always a space after a property's colon

	display: block;

not

	display:block;
	
### CSS3, The Bleeding Edge

If you're 'hand coding' your CSS3 and not using pre-written @mixins or Compass/Bourborn then declare the CSS. Also put all CSS3 prefixed code at the end of the alphabetised stack.

For Example

	-webkit-transform: rotate(45deg);
	   -moz-transform: rotate(45deg);
	    -ms-transform: rotate(45deg);
	     -o-transform: rotate(45deg);
	        transform: rotate(45deg);

note: make sure you are using the correct prefixes for the selector. Use [Can I Use](http://caniuse.com/) and the [Mozilla Developer's Network](https://developer.mozilla.org/en-US/)Mozilla Developer's Network to check.

	
## Sass

This starting point is sticking with Sass (currently SCSS) so there's things that need to be addressed, outlined and adhered to whilst using this language also.

### Ordering things

For clarity, it is best to stick to a strict order of 'things' in a block of Sass. These 'things' are to be separated by one line.  

#### Ordering $variables, @extends and @includes

To start with you would call any variables specific to the element, followed by any @extends or @includes, like this

	.element {
		$bg-color: #D90000;
		
		@extend .rounded-border;
		
		@include data-module;
	}

#### Element properties

After we've got that bit of Sass lovliness out of the way we will add the element properties that are required. So our block could look like this 

	.element {
		$bg-color: #D90000;
		
		@extend .rounded-border;
		
		@include data-module;
		
		cursor: pointer;
		height: 300px;
		margin: 0 auto;
		padding: 0;
		width: 400px;
	}
	
#### Pseudo & Combinator Selectors

After this we place the Pseudo selectors followed by the combinator selectors, like this 

	.element {
		$bg-color: #D90000;
		
		@extend .rounded-border;
		
		@include data-module;
		
		cursor: pointer;
		height: 300px;
		margin: 0 auto;
		padding: 0;
		width: 400px;
		
		&:hover {
        	text-decoration:underline;
    	}
    	
        & > li {
	        margin:10px;
        }
        
        & + ul {
    	    margin-left:10px;
        }
	}

### Nesting Elements

There will also be a time where you would want to naturally nest things. Like adding a heading that's knowingly going to be specific to it's parent and maybe another div the same. 

To do this we would make sure our nested elements are in order of nesting anything super specific like a h1, p, a or #id'd element followed by anything that's a .class like this 

	.element {
		background: blue;
		display: block;
		margin: 0 auto;
		width: 44.15467%;
		h1 {
			color: green;
			font-size: 32px;
			font-size: 2rem;
		}
		.box {
			width: 80%;
			margin: 0 auto;
		}		
	}

### Nesting Media Queries

It will come to a point in the development when you'd need to add some media queries to your code. 
These are to be nested inline with the elements themselves rather than at the bottom of the (S)CSS document.
Like this -

	.element {
		background: red;
		@media (min-width: 700px) {
			background: blue;
		}
	}
	
### Nesting Media Queries with Nested Elements

It's therefore only progression to suggest where you would have elements nested within elements that also require media queries. For consistency rather than writing media queries after 'every' element in a nested group of elements. Group the media queries at the end of the element. Like this - 

	.element {
		background: blue;
		display: block;
		margin: 0 auto;
		width: 44.15467%;
		h1 {
			color: green;
			font-size: 32px;
			font-size: 2rem;
		}
		.box {
			width: 80%;
			margin: 0 auto;
		}
		@media (min-width: 700px) {
			width: 100%;
			h1 {
				font-size: 48px;
				font-size: 3rem;
			}
			.box {
				width: 95%;
			}
		}
		@media (min-width: 900px) {
			h1 {
				font-size: 32px;
				font-size: 2rem;
			}
		}
	}

## Internet Explorer

For targeting IE8 and below use a class of lte-ie8, then add specific hacks for IE7 and IE6.

For Example (using Sass) -

    {
		// put the IE9 and 'other' browser CSS declarations here

    	.lt-ie8 & {

    	// put the IE8 and below CSS declarations here
	 	/* IE8 and below */

    	// if you need IE7 as well then prefix the CSS with a *
     	/* IE7 and below */

		// if you need IE6 as well then prefix the CSS with a /
		/* IE6 */
	    }
	}

####Compiling

Keep ALL THE COMMENTS for development but minimize the heck out of this for production
