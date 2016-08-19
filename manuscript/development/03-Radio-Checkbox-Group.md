# Group control

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
