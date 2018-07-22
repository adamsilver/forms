# Group control


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

The `id` attribute value of the first control in the group, matches the `name` attribute value. This is essential for the client-side and server-side validation because the server only knows about the name (not the id). And because the error summary links to to the first input in the group.
