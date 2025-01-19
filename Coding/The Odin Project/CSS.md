**Borders, margins, padding**
**Hover effect**
**Flexbox**

**Default Styles**
- Google has its own default CSS for tags. Like, list items have spacing, headers are bold and bigger and etc. Default styles determine a default margin, padding, colors, and etc.
- Can use a reset CSS style for ensuring your styles look the same across different web browsers

**CSS Units**
- Relative vs Absolute units
	- Absolute Units
		- `px` is an absolute unit, pixel size doesn't change relative to anything else
	- Relative Units
		- `em` and `rem` refer to font size
			- `1em` is `font-size` of an element
			- If setting element's `font-size` to `16px` and setting width to `4em`, then width would be `64px (16*4)`
		- Use `rem` to define font size (recommended)
- Viewport units
	- `vh` and `vw` relate to size of viewport. `1vh` is equal to `1%` of viewport width.
	- Useful when you want size relative to viewport like for full screen app like interfaces

**CSS Properties**
- Background
	- `background` property is shorthand for 8 different background-related properties
- Borders
	- `border`
	- `border-radiu`
	- 
- box-shadow
	- `box-shadow` adds shadow effects around element's frame
- Overflow
	- `overflow` defines what happens to element when content is too big to fit. Most common usage is adding scrollbars to element inside webpage
- Opacity
	- `opacity` sets opactiy of an element

**Advanced CSS Selectors**
- Child and Sibling Combinators
	- selectors:
		- `>` - child combinator
		- `+` - adjacent sibling combinator
		- `~` - general sibling combinator
		- 
```css
main div {
}

%% This rule will only select divs w/ class of child %%
main > div {

}

main > div > div {

}

.group1 + div {

}

.group1 ~ div {

}
```

- Pseudo-selectors
	- pseudo-classes
		- different way to target elements in HTML
		- User action pseudo-classes
			- `:focus` - element currently selected by user via cursor or keyboard
			- `:hover` - user's mouse pointer hover; buttons, links, drop-down menu
			- `:active` - elements that are being clicked, useful for giving user feedback that their action had an effect. "tactile" feedback
```css
  /* This rule will apply to all links */
  a {
    text-decoration: underline;
  }

  /* This will apply to unvisited links */
  a:link {
    color: blue;
  }

  /* And you guessed it, this applies to all links the user has clicked on */
  a:visited {
    color: purple;
  }

```
```css
  .myList:nth-child(5) {/* Selects the 5th element with class myList */}

  .myList:nth-child(3n) { /* Selects every 3rd element with class myList */}

  .myList:nth-child(3n + 3) { /* Selects every 3rd element with class myList, beginning with the 3rd */}

  .myList:nth-child(even) {/* Selects every even element with class myList */}

```

	- pseudo-elements
	
```html
<style>
  .emojify::before {
    content: '😎 🥸 🤓';
}

  .emojify::after {
    content: '🤓 🥸 😎';
}
</style>

<body>
  <div> Let's <span class="emojify">emojify</span>this span!</div>
</body>

%% Result: Let’s 😎 🥸 🤓 emojify 🤓 🥸 😎 this span! %%
```

- Attribute Selectors
	- Attributes are anything in the opening tag of HTML element such as `src=''` and `href=''`
	- Basic usage
		- `[attribute]`
		- `selector[attribute]`
		- `[attribute="value"]`
	- Regular expressions selectors
		- - `[attribute^="value"]` - `^=` Will match strings from the start.
		- `[attribute$="value"]` - `$=` Will match strings from the end.
		- `[attribute*="value"]` - `*=` The wildcard selector will match anywhere inside the string.

**Positioning**
- moving elements around the screen using margin, padding, and flexbox rely on CSS's default "positioning-mode". 
- Default positioning mode is `position:static`. 
	- Static vs Relative
		- In relative, properties like `top, right, bottom, left` displace the element reltaive to its normal position
- Absolute Positioning
	- `position: absolute` - allows you to position something at exacct point on the screen w/o disturbing other elements around it
	- Examples:
		- modals
		- image w/ caption on it
		- icons on top of other elements
- Fixed positioning
	- Position relative to the `viewport`
- Sticky Positioning
	- Sticky elements act as normal elements until you scroll past them, then they start behaving like fixed elements
	- Useful for section headings
- Syntax:
```css
position: static;
position: relative;
position: absolute;
position: fixed;
position: sticky;	
```

**Functions**
- Similar to programming languages, functions in CSS are reusable pieces of code, passed in arguments between parentheses
- `color: rgb(0, 0, 255);`
- CSS functions can't be created, only a list of premade functions
	- `calc()`
	- `min()` 
	- `max()`
	- `clamp()` - (smallest val, ideal val, largest val)

**Variables (Custom Properties)**
- Allows you to reference CSS value, however many times. Instead of updating 1 instance of a value, can update all of them. Helps you keep values like colors consistent
- Syntax
	- declaring: `--name: red;`
	- using: `color: var(--name, <optional fallback value>);`
	- Kebab case
- Scope
	- Scope of custom property (variable) is determined by selector
	- Scope includes the selector AND descendents
	- Add custom property to `:root` selector to be available to all descendents. Like global variables. `:root` selects all the html but has higher specificity than `html`
- Can also set custom properties that can be used later. Like for Dark and Light themes, set root to a custom property when the class is dark or light
	- This is user click system, when an application uses operating system theme, this is `Media queries`
- `@property` at-rule - lets you associate type with the property, set default values, control inheritance 
	- can set `inherits: false` as a property to prevent inheriting from parents

**Frameworks and Preprocessors**
- Tools to make CSS more streamlined and less tedious
- Frameworks
	- Bootstrap
		- packages lots of CSS code
	- Tailwind
		- Changes how we apply CSS thru different syntax by supplying pre-named classes that typically apply to only a single line of CSS
	- Bulma
	- Foundation
	- many more
	- Using a framework can hamstring your CSS knowledge
- Preprocessors
	- aka precompilers
	- Help you write CSS more easily, reduce code reptition, provide time/code saving features (loops, conditionals, join multiple stylesheets)
	- 
**Grid**
- 2d version of flexbox
- `display: grid`
- 