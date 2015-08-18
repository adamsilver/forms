# Validation design

## Overview

Designing forms is actually quite straightforward. There is only the following components to consider:

1. An error summary at the top
2. Contextual errors, also known as inline errors.
3. Accessibility additions
4. When to validate

## Behaviour

Form validation should only be triggered when the form is submitted. Obviously this note does not pertain to server-side validation as it can *only* be triggered in this way	.

It is advised that you don't attempt to validate controls when the user is typing or moving between controls i.e. `blur`.

This is because this causes a poor experience in terms of over-the-top hand holding, early interuption and visual glitches such as jumping when information is injected into the page via Javascript.

When a form is submitted with errors, the following points should be noted:

1. A group of error messages is displayed at the top of the form/page. The focus is put here.

2. Inline error messages are placed underneath the erroneous control.

3. Typically visual treatment will be red by convention.

4. Clicking on one of those errors in the error summary will put focus to the particular erroneous control.

4. Inline errors also display beneath the erroneous control for visual context as the user fixes the errors.

## Accessibility note

For screen readers error indicators are injected. For group controls (i.e. radios) we add the indicator to the legend, otherwise we add the indicator to the associated label.