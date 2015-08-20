# Control extras

## Select options

Dependening on the situation, grouping parts of a select menu's options is advisable. Take the following example. It is a list of cuisines. The most popular are grouped at the top for quick selection. Providing benefit to the user, by indicating how this large list is organised and how they can go about using it. Much better than a long list of ungrouped options.

	<div class="standardControl">
		<label for="cuisine">Cuisine</label>
		<select id="cuisine" name="cuisine">
		    <option value="">Show everything</option>
		    <optgroup label="Most popular cuisines">
	            <option value="indian">Indian</option>
	            <option value="pizza">Pizza</option>
	            <option value="chinese">Chinese</option>
	            <option value="kebabs">Kebabs</option>
		    </optgroup>
		    <optgroup label="Other cuisines">
	            <option value="bangladeshi">Bangladeshi</option>
	            <option value="thai">Thai</option>
	            <option value="english">English</option>
		    </optgroup>
		</select>
	</div>

## Placeholders

I> ## Summary
I>
I> Placeholder text within a form field makes it difficult for people to remember what information belongs in a field, and to check for and fix errors. It also poses additional burdens for users with visual and cognitive impairments.

In-context descriptions or hints can help clarify what goes inside each form field, and therefore improve completion and conversion rates. There are many ways to provide hints. A common implementation is by inserting instructions within form fields. Unfortunately, user testing continually shows that placeholders in form fields often hurt usability more than help it.

Labels tell users what information belongs in a given form field and are positioned outside the form field. Placeholder text, located inside a form field, is an additional hint, description, or example of the information required for a particular field. These hints typically disappear when the user types in the field.

Some forms replace field labels with in-field placeholder text to reduce clutter on the page, or to shorten the length of the form. While this approach is based on good intentions, our research shows that it has many negative consequences.

Below are 7 main reasons why placeholders should not be used as replacements for field labels.

1. Disappearing placeholder text strains users’ short-term memory.
If the user forgets the hint, which people often do while filling out long forms, he has to delete what he wrote and, in some cases, click away from the field to reveal the placeholder text again. In an ideal world, users would be entirely focused when filling out a form. But in reality, users multitask. They have different tabs open, or they might be pulled away by an email or phone call. For complex tasks, they might have to stop and go retrieve a document or order number. From our research on mobile usability, we know that mobile users are also frequently distracted and interrupted while using their devices. So, it’s important to help users pick up where they left off.

On simple, frequently used forms with one or two fields, such as a search box or login form, the strain on memory is less of an issue than with complex or rarely used forms. That is because with simple, familiar forms, users can guess what they are supposed to enter. Although, on even a simple login form without labels, users may not remember if they have the option to type Username or Email or just Username.

2. Without labels, users cannot check their work before submitting a form.
The lack of labels makes it impossible for customers to glance through the form and make sure that their responses are correct. Similarly, browsers that autocomplete form fields may fill in information incorrectly. If there are no labels, or if special instructions are no longer visible, customers must reveal the placeholder text by deleting the text in each field one by one in order verify that it matches the description. Realistically though, many won’t even realize that potential for error, and they won’t make the effort to double check.

3. When error messages occur, people don’t know how to fix the problem.
If the form has been filled out, but there are no labels or instructions visible outside the form fields, then users have to go back to each field to reveal the description in order to fix the error.

4. Placeholder text that disappears when the cursor is placed in a form field is irritating for users navigating with the keyboard.
People using the Tab key move quickly from field to field, and they don’t stop to study the next field before tabbing to it.

5. Fields with stuff in them are less noticeable.
Eyetracking studies show that users’ eyes are drawn to empty fields. At the minimum, users will spend more time locating a non-empty field — a nuisance. At the worst, they will overlook the field completely—a potential business-killing disaster.

6. Users may mistake a placeholder for data that was automatically filled in.
When there is already text in the field, people are less likely to realize that they can type there. Some users assume the placeholder text is a default value and skip the field completely.

7. Occasionally users have to delete placeholder text manually.
Sometimes placeholders do not disappear when users move their input focus into the field. If the placeholder remains in the field as editable text, users are forced to manually select and delete it. This creates an unnecessary burden on users and increases the interaction cost of filling in the form.

Sometimes the placeholder dims when the cursor is placed in a text field. Unfortunately, this interaction pattern is rare and users are not familiar with it: some still think they have to delete the text manually. It often takes a few failed attempts and lots of clicking to realize that they can start typing over the dimmed text.

Placeholder Text in Addition to Labels

Using placeholder text in combination with form labels is a step in the right direction. Labels outside the form fields make the essential information visible at all times, while placeholder text inside form fields is reserved for supplementary information. However, even when using labels, placing important hints or instructions within a form field can still cause the 7 issues mentioned above, albeit with less severity. If some of the fields require an extra description that is essential to completing the form correctly, it’s best to place that text outside the field so that it is always visible.

### Placeholders and Accessibility
One last issue to consider is that placeholder text is generally bad for accessibility. Certainly, accessibility software and modern browsers are improving, but they still have a long way to go. Three of the biggest problems for accessibility are as follows:

The default light-grey color of placeholder text has poor color contrast against most backgrounds. For users with a visual impairment, poor color contrast makes it difficult to read the text. Because not all browsers allow placeholder text to be styled using CSS, this is a difficult issue to mitigate.

Users with cognitive or motor impairments are more heavily burdened. As we saw, placeholders can be problematic for all users: disappearing placeholders increase the memory load; persistent dimmable placeholders cause confusion when they look clickable but aren’t, and placeholders that do not disappear require more keyboard or mouse interaction to be deleted. These difficulties are magnified for people with cognitive or motor impairments.

Not all screen readers read placeholder text aloud. Blind or visually impaired users may miss the hint completely if their software does not speak the placeholder content.

### Conclusion

Rather than risk having users stumble while filling out forms or waste valuable time figuring out how they work, the best solution is to have clear, visible labels that are placed outside empty form fields.

## Email

## Number

## Date

## Range

## Etc