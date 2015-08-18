# Client-side validation

## Overview

Client-side validation is almost identical to the server-side except for the following:

1. When there are errors, the user is scrolled up to the error summary.
3. Clicking on an error message in the summary, will focus the control - some browers will do this without Javascript.
4. Not all validation messages will/can be handled on the client.

	// define new validator
	var validator = new project.FormValidator(document.forms.formName);

	// add a validator that checks the username is not empty
	validator.addValidator("username", [{
        message: "You must enter your username",
        method: project.validators.notEmpty
    }]);

Note:

1. The first argument is the `name` of the control

2. The second argument is an array of rules

3. Each rule is an object with two or three properties (one is optional).

4. The `message` property is the the error message to be displayed when there is an error pertaining to the control.

5. The `method` is the function that executes to determine whether the control is valid or not.

## Defining a rule method

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
