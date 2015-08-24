# The basic building blocks

In the main forms are rather simple to build. There are just a few basic building blocks you need to be aware of in order to design and build user-friendly froms. Some of these components are vital for the user experience, so being aware of them before designing a form will help to keep them looking beautiful. There are just a few components&hellip;

## 1. The form component

This is the outermost element and is invisible. Designers do not need to be aware of this component in great detail.

Implementing the form component is as follows:

	<form method="post" action="/">
	</form>

**The method attribute** takes *get* or *post* as values. The idea being that if you're doing any modification you must use post. If you're retrieving information you must use *get*.

Some examples of when to use *get*:

1. Sorting a particular set of products by rating.

2. Searching for a product with a particular keyword.

Some examples of when to use *post*:

1. Signing up for a new account.

2. Updating your email address.

**The action attribute** is a url where the form information is sent to for processing.

## 2. Controls

Controls are the meat and potatos of forms. They allow people to enter content and send that information off to be processed.

Not all controls allow input. Some trigger submission.

There are 4 main elements that are considered to be controls: `input`, `select`, `textarea`, `button`. Controls are discussed in more detail in a chapter of their own.

## 3. Labels

Labels provide information about each control. For example if the control expects a pasword, then the label might say "Password".

Visual users will see the label and visually impaired users may use a screen reader which will read out the label. Labels are only needed for controls that provide a vessel for input e.g. submit buttons are fine without.

Additionally, browsers may provide the ability to click a label which will either move focus to the control or mark the control as checked in the case of a checkbox or radio control.

Associating a control with a label as follows:

	<label for="username">Username</label>
	<input id="username">

## 4. Fieldsets and legends

Fieldsets provide information about a group of related controls. Typically this is useful for controls with a type attribute `radio` or `checkbox`.
