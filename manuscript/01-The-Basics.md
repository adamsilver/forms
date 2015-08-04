# The basics

## Forms

Forms are made up of several component elements. The first element being the `form` itself. Let's look at the basic construct:

	<form method="post" action="/" name="loginForm">
	</form>

### The `method` attribute

In the main the value will be either *post* or *get*.

You should use *post* when you're modifying or creating content. Examples include:

1. Signing up for a new account (creating new content)

2. Editing your name in your profile (editing an existing piece of content)

Otherwise you should use *get* whereby you want a slightly different view of an ever present resource. Examples include:

1. You want to sort a particular set of products by rating.

2. You want to filter results by keyword.

## Controls

Controls allow people to input content and send off to be processed by the web application in order to process an intended action. Without controls, forms would be useless.

Not all controls allow user input. Some just trigger submission.

There are 4 main elements that are considered to be controls:

`input`, `select`, `textarea`, `button`.

Controls will be explored in more detail in *Chapter 2: Controls*

## Labels

Labels provide information about each control. Visual users will see the label and visually impaired users may use a screen reader which will read out the label. Labels are only needed for controls that provide a vessel for input e.g. submit buttons are fine without.

Additionally, browsers may provide the ability to click a label which will either move focus to the control or even mark the control as checked in the case of a checkbox or radio control.

Associating a control with a label as follows:

	<label for="username">Username</label>
	<input id="username">

## Fieldsets and legends

Fieldsets provide information about a group of related controls. Typically this is useful for controls with a type attribute `radio` or `checkbox`.
