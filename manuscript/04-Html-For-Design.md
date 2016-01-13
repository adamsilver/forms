## Abstraction for design

### Simple control e.g. a username

What I am referring to as a *simple* control, is one that is made up of a label and a text control (or select menu). Anything other than a button, a checkbox or a radio.

In HTML this looks like:

	<div class="standardControl">
		<label for="username">Username</label>
		<input id="username" name="username">
	</div>
