# Basic design principles

## Overview:

There are many ways you *could* display your forms, but 99% there is just one way in which you will want to design it. This section cuts through the options to provide the best way to design your form elements. If you're even 1% unsure this chapter is for you.

## Basic rules

1. Text controls should have labels. And these labels should be above the controls. The eye should move downwards only (not left to right).

2. Groups of checkboxes or radios should have a fieldset and legend (sometimes hidden) with labels to the *right* of each control.

3. There should be a primary submit button (styled as such) at the bottom of the form.

4. Each form field should be vertically linear.

5. If you *must* have optional fields, then mark them with an asterisk and denote this at the top of the form.

## Rules for pros

1. Don't try and customise the visual design of form controls, let other parts of the site cater to branding requirements. You're asking for trouble if you try to do this cross-browser.

2. Form submit buttons should not have a pointer cursor like links. They are not links. The hand does *not* denote "clickable" contrary to popular misguided belief.

3. Don't try and make every field look beautiful on screen by making them the same width. Make each form provide affordance to the content required by each control. i.e. a name field should be longer than a date of birth field requiring (6 numbers)

4. Avoid multi-select controls. Most people avoid them but just incase you thought about. Don't.

5. Use select menus when there are are lots of options. What does lots mean? Probably more than 5 or 6. Use judgement.

## Validation rules

1. Forms should be validated when the user submits. For one, for server-side validation, this is the only time it can be done. For two, you don't want to validate too early. Let the user decide when they are done and help them out when they need it. Attempting silly things on change or on blur is asking for trouble both technically and UX wise.

Form validation should only be triggered when the form is submitted. Obviously this note does not pertain to server-side validation as it can *only* be triggered in this way	.

It is advised that you don't attempt to validate controls when the user is typing or moving between controls i.e. `blur`.

This is because this causes a poor experience in terms of over-the-top hand holding, early interuption and visual glitches such as jumping when information is injected into the page via Javascript.

2. When a form contains errors a list of those errors should be shown at the top of the form. Why? Because the user needs to be clearly alerted to whatever has gone wrong in a nice focused summary without having to scroll through the form. Even when the form is one or two fields, this is highly advised.

3. Contexual (or inline) errors should be shown below each field. Why? So that when fixing individual fields the user doesn't have to remember what and how to fix said error.

4. Don't use AJAX for form validation unless there is a very good reason. The point of JS is to stop expensive server hits. AJAX introduces this back into the mix. May as well hit the server and forget the AJAX complexities that cause a degraded experience.

5. Errors should be a tint of red by convention. It's something users intuitively look for. Don't hide them in the name of design asthetics etc.

6. Clicking on one of the errors in the error summary will put focus to the particular erroneous control.

## Accessibility rules

1. For screen readers error indicators are injected. For group controls (i.e. radios) we add the indicator to the legend, otherwise we add the indicator to the associated label.
