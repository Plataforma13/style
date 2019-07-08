# CSS writing patterns for plataforma13 Frontend

The new architeture of our css projects is based on the BEM metodology naming rules as following:

```css
	.awesome-block__amazing-item--marvelous-modifier {
		/*Some super css here*/
	}
	
	.awesome-block__amazing-item--marvelous-modifier:hover {
		/*Some super css  hovering by here*/
	}
```
## Before creating new css rules:

 * Look by the code and check if any already written rule solves your necesity
 * Then create an unique and objective name for the new css blocks and elements
 * Finaly code your new baby block!

### OOCSS and BEM [(By Airbnb)](https://github.com/airbnb/css/blob/master/README.md)

We encourage some combination of OOCSS and BEM for these reasons:

  * It helps create clear, strict relationships between CSS and HTML
  * It helps us create reusable, composable components
  * It allows for less nesting and lower specificity
  * It helps in building scalable stylesheets

**OOCSS**, or “Object Oriented CSS”, is an approach for writing CSS that encourages you to think about your stylesheets as a collection of “objects”: reusable, repeatable snippets that can be used independently throughout a website.

  * Nicole Sullivan's [OOCSS wiki](https://github.com/stubbornella/oocss/wiki)
  * Smashing Magazine's [Introduction to OOCSS](http://www.smashingmagazine.com/2011/12/12/an-introduction-to-object-oriented-css-oocss/)

**BEM**, or “Block-Element-Modifier”, is a _naming convention_ for classes in HTML and CSS. It was originally developed by Yandex with large codebases and scalability in mind, and can serve as a solid set of guidelines for implementing OOCSS.

  * CSS Trick's [BEM 101](https://css-tricks.com/bem-101/)
  * Harry Roberts' [introduction to BEM](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)

We recommend a variant of BEM with kebab-cased “blocks”, which works particularly well when combined with angular js components.

**Example**

```html
// passenger-number-input.html
<input type="number" class="input input__number  input__number--big input__number--passenger   input__number--passenger">
```

```css
/* input.css*/
.input {} /* especifity : (0, 1, 0)*/
.input:invalid {} /* especifity : (0, 1, 0)*/
```

```css
/* input.css*/
.input__number { } /* especifity : (0, 1, 0)*/
.input__number--big { } /* especifity : (0, 1, 0)*/
.input__number--passenger { } /* especifity : (0, 1, 0)*/
.input__number--passenger { } /* especifity : (0, 1, 0)*/
```

## Code style and Spacing

All idents are 4 spaces. Spaces are the only way to guarantee code renders the same in any person’s environment.

### Property and values

Put spaces after `:` in property declarations

```css
	/*Bad*/
	.card {
		border-radius:4px;  /*Please give space to the values they need to breathe*/
	}

	/*Good*/
	.card {
		border-radius: 4px;
	}
```
Use hex color codes `#000` unless using `rgba()` in raw CSS (the SCSS `rgba()` function is overloaded to accept hex colors, as in `rgba(#000, .5)`).

```css
	/*Bad*/
	background-color: white;
	color: rgba(0, 0, 0, .4);

	/*Good*/
	background-color: #ffffff;
	color: rgba(#ffffff, .4);
```
Avoid specifying units for zero values, e.g., `margin: 0;` instead of `margin: 0px;`.

```css
	/*Bad*/
	margin-top: 1px;
	margin-right: 2px;
	margin-bottom: 3px;
	margin-left: 4px;

	/*Good*/
	margin: 1px 2px 3px 4px;  // Ahhh clean !

```

### Rules and brackets

Rule opening brackets stil in the same line. After rule names add one space before braces.

```css
	.rule 
	{ /* Never do that */
	}

	.rule{ /*Bad*/
		
	}

	.rule { /*Good! Now we have an space before that*/
	
	}
```

### Line breaks

Dont leave line breaks between css properties

```css
	/* Bad: */
	.rule {
		display: flex;
		flex-flow: row-reverse wrap;
										/*  Please dont leave this void in me :(    */
		background-color: #aff;
	}

	/* Good: */
	.rule {
		display: flex;
		flex-flow: row-reverse wrap;
		background-color: #aff;
	}
```

You shoudnt add whitespaces between nested blocks

```css
	/*Bad*/
	@supports (me) {
		                               /*Unnecessary whitespace*/
		rule {
			/*code*/
		}
	}

	/*Bad*/
	@supports (me) {
		rule {
			/*code*/
		}
		                             /*Unnecessary whitespace*/
	}

	
	/*Good*/
	@supports (me) {
		rule {
			/*code*/
		}
	}

```


## Important note:
All css writen in plataforma13 projects  after the first publishing of this gude should follow the following rules and guides.

