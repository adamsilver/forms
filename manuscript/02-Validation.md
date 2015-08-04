# Validation

## Overview:

1. Form validation should only take place on submission. Not on blur, not on focus, not on key type. There are various UX reasons behind

* Don't hold hand to early
* Don't interupt me until I require
* Can be annoying when page jumps injecting errors on key type
* Intuitive and matches server side behaviour
* Many more

2. When there are errors a summary of those error messages appear as a group in a red box above the form.

3. Clicking on one of those errors int he error summary group will put focus to the particular erroneous control.

4. Inline errors also display beneath the erroneous control for visual context as the user fixes the errors.

5. For screen readers we add error indicators to aid in fixing errors. For group controls (i.e. radios) we add the indicator to the legend, otherwise we add the indicator to the label.

## Validation summary

The HTML needs to look like:

	<!-- When there are no errors class equals hide -->
	<div id="errorMessagePanel" class="hide">
		<!-- if there is a generic error -->
			<p>@Model.errorMessage.standardError.text</p>
		<!-- endif -->

		<!-- if there are form errors -->
		<h2>There are some errors in the form</h2>
		<ul>
			<!-- for each error relating to form control -->
				<li>
					<a href="#{{nameOfField}}">
						{{errorMessageForField}}
					</a>
				</li>
			<!-- end for each -->
		</ul>
	</div>

## Server side error state for individual control types

### Standard control

HTML:

	<div class="standardControl error">
		<label for="username">Field label <span class="errorIndicator">error</span></label>
		<input id="username" name="username" value="">
		<div class="errorMessage">Please enter a username.</div>
	</div>

View model segment:

	{
		controls: {
			username: {
				value: "Whatever",
				error: {
					message: "Please enter a username"
				}
			}
		}
	}

Notes:

1. An error `class` is added onto the container
2. A `span` is injected into the `label`
3. A visual message is injected underneath the `input`

### Single checkbox

HTML:

	<div class="checkboxControl error">
		<input type="checkbox" name="terms" id="terms">
		<label for="terms">Terms <span class="errorIndicator">error</span></label>
		<div class="errorMessage">Please confirm you have read the T&Cs.</div>
	</div>

View model segment:

	{
		controls: {
			terms: {
				error: {
					message: "Please confirm you have read the T&Cs"
				}
			}
		}
	}

Notes:

1. An error `class` is added onto the container
2. A `span` is injected into the `label`
3. A visual message is injected underneath the `input`

### Group control

HTML:

	<div class="groupControl error">
		<fieldset>
			<legend>Delivery or collection <span class="errorIndicator">error</span></legend>
			<div class="control">
				<input type="radio" name="delivery" id="delivery">
				<label for="delivery">Delivery</label>
			</div>
			<div class="control">
				<input type="radio" name="delivery" id="collection">
				<label for="collection">Collection</label>
			</div>
			<div class="errorMessage">Please confirm you have read the T&Cs.</div>
		</fieldset>
	</div>

View model segment:

	{
		controls: {
			delivery: {
				error: {
					message: "Please select a delivery option."
				}
			}
		}
	}

Notes:

1. An error `class` is added onto the container
2. A `span` is injected into the `legend`
3. A visual message is injected at the end of the `fieldset`

## Client-side validation

Client-side validation is almost identical to the server-side except for the following:

1. It happens instantaneously.
2. The user is scrolled up to validaiton summary messages
3. Clicking on an error message in the summary will focus the field (in all browsers). Some browers do this for free.
4. Not all validation messages will/can be handled on the client.

Let's say you want to create a form validator for the login page...

1. Define a controller (like for any other feature we build). i.e. project.controllers.LoginFormController.js

2. Define a view i.e. project.views.LoginFormValidatorView.js

3. project.views.LoginFormValidatorView should inherit from project.views.FormValidatorView.

Example in isolation:

	var validator = new project.views.FormValidatorView(document.forms.formName);
	validator.addValidator("username", [{
        message: "You must enter your username",
        method: project.validators.notEmpty
    }]);

Example in real world with a controller and inherited view:

	// controller
	project.controllers.LoginFormController = function() {
		this.loginFormValidatorView = new project.views.LoginFormValidatorView(document.forms.loginForm);
	}

	// view
	project.views.LoginFormValidator = function(form) {
	    project.views.LoginFormValidator.superConstructor.apply(this, arguments);
	    this.setupValidators();
	};
	project.utilities.inherit(project.views.LoginFormValidator, project.views.FormValidatorView);

	project.views.LoginFormValidator.prototype.setupValidators = function() {
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
	        method: project.validators.notEmpty
	    }]);
	    this.addValidator("password", [{
	        message: "You must enter your password",
	        method: project.validators.notEmpty
	    }]);
	};

A rule is a function that takes an argument of control and returns true or false based on any criteria you wish. You could even check to see if a monkey exists and is dancing on the page if you wanted. But in real terms this could be cross-field validation.

	project.validators = {
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