
- Doctype: used for rendering the HTML version
- Head: holds metadata
- body: page content


**Shortcuts**:
- ! - generate simple html starter code
- Lookup Emmet shortcuts


**SVG Image format**

**HTML Tables**
- `<table></table>` tags

**Forms**
- User inputs data to our backend
- `form` element
- `action` and `method` attributes:
- `<form action="example.com/patch" method="POST"></form>`
	- Input element w/ text type data: `<input type="text">`
		- `placeholder` attribute
		- `name` attribute - variable name for the input, required, otherwise input is ignored
	- Labels - inform user what type of data they are expected to enter.
		- `<label for="first_name">First Name:</label>`
	-  Other inputs:
		- `email` 
		- `password`
		- `number`
		- `date`
- Selection elements
	- Let the users select value from predefined list
	- renders dropdown list
	- `<select name=""> ... </select>`
- Radio buttons
	- Instead of select dropdowns, if you have few items, display them. Better user experience
	- Only 1 option can be selected at a time
- Checkboxes
	- Can select multiple items
- Buttons
	- Set the types to the following. By default, type is `submit`
	- `submit`
	- `reset`
- Fieldset element
	- container element that groups related form inputs into one logical unit
- Legend

**Validations**
- Required
- Minimum, maximum length validations
- Number range validation
	- min, max values
- Pattern validations
	- regular expressions as value
	- `pattern="(\d{5}([\-]\d{4})?)`
- Styling validations
	- `:valid` `:invalid` pseudo-classes
	- in CSS, can mark invalid input as red borders, or green
- Built-in validations ensure user input correct data but they have limitations. Thus, can make custom validations using CSS and javascript
- Not only do we need client side validations but also server side validations to ensure integrity of data