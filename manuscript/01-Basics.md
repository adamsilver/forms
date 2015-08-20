# Basics

## Overview

Forms are made up of only a few components. Whilst this introduction gets a little techy, this should still be more than useful for a designer in that these constraints and components should help drive the User Experience and Visual Design.

Forms are made up of the following 5 components:

1. Form
2. Control
3. Label
4. Fieldset
5. Legend

## Forms

Forms are made up of several component elements. The first element being the `form` itself. Let's look at the basic construct:

	<form method="post" action="/" name="loginForm">
	</form>

### The `method` attribute

In the main the value will be either *post* or *get*. Technically, *put* and *delete* requests should also be used when appropriate, but there is a lack of support for this.

With that in-mind, you should use *post* when modifying (or creating) e.g.

1. Registering for a new account.

2. Updating your email address.

Otherwise, you should use *get* whereby no modification happens e.g.

1. Sorting a particular set of products by rating.

2. Searching for a product with a particular keyword.

## Controls

Controls allow people to input content and send it off to be processed by the web application in order to process an intended action.

Not all controls allow user input. Some just trigger submission.

There are 4 main elements that are considered to be controls: `input`, `select`, `textarea`, `button`.

## Labels

Labels provide information about each control. Visual users will see the label and visually impaired users may use a screen reader which will read out the label. Labels are only needed for controls that provide a vessel for input e.g. submit buttons are fine without.

Additionally, browsers may provide the ability to click a label which will either move focus to the control or even mark the control as checked in the case of a checkbox or radio control.

Associating a control with a label as follows:

	<label for="username">Username</label>
	<input id="username">

## Fieldsets and legends

Fieldsets provide information about a group of related controls. Typically this is useful for controls with a type attribute `radio` or `checkbox`.
