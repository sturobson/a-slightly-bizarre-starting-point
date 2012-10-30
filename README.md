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

#### Indent any CSS changes for quick error finding. 

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

####Write all CSS rules alphabetically. 

This will aid quick error finding. 

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

####Compiling

Keep ALL THE COMMENTS for development but minimize the heck out of this for production

#### CSS Class/ID Naming conventions

Use hypens only

	.large-class-name == good
	.large_class_name == bad
	.largeClassName   == bad
	.largeclassname   == bad


#### CSS Commenting

Comment your code with these helpers - 

	/* ===== Major Section ===== */
	
	/*== Minor Section ==*/
 
	/* Explanation */
 
	/* !Flag For Attention! */   

	// Sass/SCSS ONLY comments to be written like this
	
#### CSS3, The Bleeding Edge

If you're 'hand coding' your CSS3 and not using pre-written @mixins or Compass/Bourborn then declare the CSS.

For Example

	-webkit-transform: rotate(45deg);
	   -moz-transform: rotate(45deg);
	    -ms-transform: rotate(45deg);
	     -o-transform: rotate(45deg);
	        transform: rotate(45deg);

note: make sure you are using the correct prefixes for the selector. Use [Can I Use](http://caniuse.com/) and the [Mozilla Developer's Network](https://developer.mozilla.org/en-US/)Mozilla Developer's Network to check

#### Internet Explorer

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
	

### Credits

Now where have I borrowed, stolen or rewritten this boilerplate from?

* [HTML5 Boilerplate](https://github.com/h5bp/html5-boilerplate)