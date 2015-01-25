Form Validation
===============

This is a simple form validation. All you have to do is:

* give your form tag an attribute of 'data-form' with unique value
    - ex. data-form="mainForm"
* for every field (input, select, and/or textarea) you want validation the give it the attribute; data-validate="required"
* if you are using radio buttons or checkboxes then surround your group of radio buttons or checkboxes with a '&lt;div data-validate="inGroup"&gt;'
* attached the js file (you just need to include the jquery file).
* that's it!

### Options
You can also have special validation for each field rather than just a regular required validation. You can add as many options to your fields as desired but all fields to be validated must have a 'required' value. Your options are: 

* min
    - minimum character length.
	- ex. data-validate="required,min" data-min="5"
	- data-min is the amount of minimum characters for your field
* email
	- validates email
	- ex data-validate="required,email"
* numeric
	- Numbers only
	- ex data-validate="required,numeric"
* alpha
	- letters only
	- ex data-validate="required,alpha"
* alphanumeric
	- letters and numbers only (no special characters)
	- ex data-validate="required,alphanumeric"
* date
    - checks date at mm/dd/yyyy format
    - ex data-validate="required,date"
* phone
    - checks phone at (xxx) xxx-xxxx format
    - ex data-validate="required,phone"
* equal
    - checks if field is equal to another field
    - both fields need the data-eq attribute with field name's id you want to match
    - ex &lt;input id="password" data-validate="required,equal" data-eq="confirm-password" &gt; &lt;input id="confirm-password" data-validate="required,equal" data-eq="password" &gt;
* inGroup
    - validates the radio buttons or checkboxes within the inGroup div
    - ex data-validate="inGroup"

### Extras
By default, the error messages will display in red text and the fields will turn red. If you wish to change how the errors are displayed then target your CSS to the 'error' class. 

You can also change the way to display the errors. By adding data-error to the form tag and passing in an option, you can change the way the errors are displayed:

* empty
	- if you don't pass in a value in the data-error then the error fields will just be red; no error text. This will not work on radios and checkboxes.
* body
	- will prepend all errors to the body tag
* form
	- will prepend all errors to the form tag





For instance,

input.error {
	background: white;
}

span.error {
	color: red;
}