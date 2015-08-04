# How to guide

## Simple form control

This can be used with:

* input[type=text/password]
* textarea
* select

As an example:

	<div class="standardControl">
		<label for="username">Field label</label>
		<input id="username" name="username">
	</div>

## Grouping select options

By example:

	<div class="standardControl">
		<label for="cuisine">Cuisine</label>
		<select id="cuisine" name="cuisine">
		    <option value="">Show everything</option>
		    <optgroup label="Most popular cuisines">
	            <option value="indian">Indian</option>
	            <option value="pizza">Pizza</option>
	            <option value="chinese">Chinese</option>
	            <option value="kebabs">Kebabs</option>
		    </optgroup>
		    <optgroup label="Other cuisines">
	            <option value="bangladeshi">Bangladeshi</option>
	            <option value="thai">Thai</option>
	            <option value="english">English</option>
		    </optgroup>
		</select>
	</div>

## Single checkbox

e.g. terms and conditions or save as billing

	<div class="checkboxControl">
		<input type="checkbox" name="terms" id="terms">
		<label for="terms">Terms</label>
	</div>

## Group of checkboxess

Useful for a group of checkboxes or radios.

Note: fieldset and legend used for accessibility but might be useful visually. read more in accessibility guidelines.

	<div class="groupControl">
		<fieldset>
			<legend>Delivery or collection</legend>
			<div class="control">
				<input type="radio" name="delivery" id="delivery">
				<label for="delivery">Delivery</label>
			</div>
			<div class="control">
				<input type="radio" name="delivery" id="collection">
				<label for="collection">Collection</label>
			</div>
		</fieldset>
	</div>

## Action buttons

	<div class="actions">
		<input type="submit" value="Checkout" name="checkout">
	</div>

## Validation

### Functionality:

1. Form validation should only take place on submission. Not on blur, not on focus, not on key type. There are various UX reasons behind

a) Don't hold hand to early
b) Don't interupt me until I require
c) Can be annoying when page jumps injecting errors on key type
d) Intuitive and matches server side behaviour
e) Many more

2. When there are errors a summary of those error messages appear as a group in a red box above the form.

3. Clicking on one of those errors int he error summary group will put focus to the particular erroneous control.

4. Inline errors also display beneath the erroneous control for visual context as the user fixes the errors.

5. For screen readers we add error indicators to aid in fixing errors. For group controls (i.e. radios) we add the indicator to the legend, otherwise we add the indicator to the label.

### Code:

Let's say you want to create a form validator for the login page...

1. Define a controller (like for any other feature we build). i.e. je.controllers.LoginFormController.js

2. Define a view i.e. je.views.LoginFormValidatorView.js

3. je.views.LoginFormValidatorView should inherit from je.views.FormValidatorView.

Example in isolation:

	var validator = new je.views.FormValidatorView(document.forms.formName);
	validator.addValidator("username", [{
        message: "You must enter your username",
        method: je.validators.notEmpty
    }]);

Example in real world with a controller and inherited view:

	// controller
	je.controllers.LoginFormController = function() {
		this.loginFormValidatorView = new je.views.LoginFormValidatorView(document.forms.loginForm);
	}

	// view
	je.views.LoginFormValidator = function(form) {
	    je.views.LoginFormValidator.superConstructor.apply(this, arguments);
	    this.setupValidators();
	};
	je.utilities.inherit(je.views.LoginFormValidator, je.views.FormValidatorView);

	je.views.LoginFormValidator.prototype.setupValidators = function() {
		/*
			Arg1: name of field
			Arg2: Array of Rule objects with 3 properties (1 optional)

			Rule: {
				method: fn,
				message: "the error message to display",
				params: {} // optional
			}
			the second param is an array of rules consisting of 2 mandatory props: message and method and optional prop: params
		*/
	    this.addValidator("username", [{
	        message: "You must enter your username",
	        method: je.validators.notEmpty
	    }]);
	    this.addValidator("password", [{
	        message: "You must enter your password",
	        method: je.validators.notEmpty
	    }]);
	};

A rule is a function that takes an argument of control and returns true or false based on any criteria you wish. You could even check to see if a monkey exists and is dancing on the page if you wanted. But in real terms this could be cross-field validation.

	je.validators = {
		// first param is a reference to the form control
	    notEmpty: function (control) {
	    	// check that the value of the control is not an empty string
	        return control.value.length > 0;
	    },
	    /* second argument is the params which can contain anything you want.
	     it makes a rule reusable. So in this case different fields can use this rule but passing in a varying max length for each differ validator.
	    */
	    maxLength: function(control, params) {
	        return control.value.length <= params.maxLength;
	    }
	};