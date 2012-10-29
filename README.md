# Slightly Bizarre Boilerplate

## A continual work in progress

Okay, so this is just a 'forever in progress' little framework/boilerplate for my own personal consumption.

It fits how I develop 'le web' and because of this I may do things differently to how you do. 

* I like my SCSS/CSS set up a little differently. 
* I like my HTML <head> set up a particular way.
* I like tabs over spaces
* I like indenting my HTML how I like to do it.

This is not to say don't pull this apart. In fact this 'framework' is the amalgamation of many other boilerplates and frameworks of which (when I've time) I'll list and link here.

## CSS (LESS/Sass/SCSS) Styleguide

#### Write the CSS using tab indentation. 

Like this -

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

#### Indent any CSS changes for quick error finding. 

Like this - 

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

####Write all CSS rules alphabetically. 

This will aid quick error finding. Like this - 

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

Compiling
-----------------------------------------------------

Keep ALL THE COMMENTS for development but minimize the heck out of this for production

CSS Class/ID Naming conventions
-----------------------------------------------------

Use hypens only

	.large-class-name == good
	.large_class_name == bad
	.largeClassName   == bad
		.largeclassname   == bad


CSS Commenting
-----------------------------------------------------

Comment your code with these helpers - 

	/* ===== Major Section ===== */
	
	/*== Minor Section ==*/
 
	/* Explanation */
 
	/* !Flag For Attention! */   

	// Sass/SCSS ONLY comments to be written like this