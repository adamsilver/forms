# Controls

## Simple form control

This can be used with the following

* Inputs of type `text`, `password`, `email`, `number`
* Free flow text control i.e. `textarea`
* Drop down i.e. `select`

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

