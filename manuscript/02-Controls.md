# Controls

## Overview

This chapter covers the different types of inputs you will want to useform controls that you will typically use in any web application. There are subtle differences worth noting, that enable the technical build adhering to visual design, accessibility standards and usability requirements.

## Simple control e.g. a username

What I am referring to as a *simple* control, is one that is made up of a label and a text control (or select menu). Anything other than a button, a checkbox or a radio.

In HTML this looks like:

	<div class="standardControl">
		<label for="username">Username</label>
		<input id="username" name="username">
	</div>

## Checkbox control e.g. agreeing to terms and conditions

This control pertains specifically to *one* checkbox. A group of checkboxes should not use this mark-up. The checkbox should appear first in the mark-up, with labels to the right, for accessibility and readability.

	<div class="checkboxControl">
		<input type="checkbox" name="terms" id="terms">
		<label for="terms">Terms</label>
	</div>

## Group control

Useful for a group of checkboxes or radios. A group requires a fieldset and legend at least for accessibility. Notice that each radio (or checkbox) is wrapped in a `div` with a class attribute value `control` because just like the checkbox control above, the group must conform in the same way. That is inputs to the left, labels to the right.

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

I> ## Important
I>
I> The `id` attribute value of the first control in the group, matches the `name` attribute value. This is essential for the client-side validation as we will see later.

## Action buttons

You must provide a submit button for everyform. No exceptions. This is expected, intuitive and required to work in all browsers without issue. It's standard and good practice.

This HTML allows you to place any primary (and secondary) call to actions. Typically this is placed at the end of the form.

	<div class="actions">
		<input type="submit" value="Checkout" name="checkout">
	</div>