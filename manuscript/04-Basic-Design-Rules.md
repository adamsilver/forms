# Basic design principles

## Overview:

There are many ways you *could* display your forms, but 99% there is just one way in which you will want to design it. This section cuts through the options to provide the best way to design your form elements. If you're even 1% unsure this chapter is for you.

## The rules

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