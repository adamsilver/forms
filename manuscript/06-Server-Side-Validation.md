# Server-side validation

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