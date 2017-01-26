# Basic design principles

1. Text controls should have labels. And these labels should be above the controls. The eye should move downwards only (not left to right).

2. Don't try and customise the visual design of form controls, let other parts of the site cater to branding requirements. You're asking for trouble if you try to do this cross-browser.

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
