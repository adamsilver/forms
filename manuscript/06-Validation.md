# Validation

## Overview:

Most web applications require form validation on both the server and the client. This chapter discuses the recommended functionality adhering to accessibility and usability standards.

## Behaviour

Form validation should only be triggered when the form is submitted. Obviously this note does not pertain to server-side validation as it can *only* be triggered in this way	.

It is advised that you don't attempt to validate controls when the user is typing or moving between controls i.e. `blur`.

This is because this causes a poor experience in terms of over-the-top hand holding, early interuption and visual glitches such as jumping when information is injected into the page via Javascript.

When a form is submitted with errors, the following points should be noted:

1. A group of error messages is displayed at the top of the form/page. The focus is put here.

2. Inline error messages are placed underneath the erroneous control.

3. Typically visual treatment will be red by convention.

4. Clicking on one of those errors in the error summary will put focus to the particular erroneous control.

4. Inline errors also display beneath the erroneous control for visual context as the user fixes the errors.

## Accessibility note

For screen readers error indicators are injected. For group controls (i.e. radios) we add the indicator to the legend, otherwise we add the indicator to the associated label.

## Validation summary

Template/partial/View/etc:

	<!-- When there are no errors class equals hide -->
	<div id="errorMessagePanel" class="hide">
		<!-- if there is a generic error -->
			<p>{{genericError.text}}</p>
		<!-- endif -->

		<!-- if there are form errors -->
		<h2>There are some errors in the form</h2>
		<ul>
			<!-- for each error relating to form control -->
				<li>
					<a href="#{{error.controlName}}">
						{{error.message}}
					</a>
				</li>
			<!-- end for each -->
		</ul>
	</div>

Note:

1. Syntax changes based on templating engine.

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

1. When there are errors, the user is scrolled up to the error summary.
3. Clicking on an error message in the summary, will focus the control - some browers will do this without Javascript.
4. Not all validation messages will/can be handled on the client.