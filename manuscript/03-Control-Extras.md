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

## Search input

Search seems like an appropriate place to start our foray into HTML5 input types. When we talk about search, we’re not just talking about Google, Bing, or Yahoo. We’re talking about the search field on that e-commerce site you just made a purchase from, on Wikipedia, and even on your personal blog. It’s probably the most common action performed on the Web every day, yet it’s not marked up very semantically, is it? We all tend to write something like this:

	<input type="text" name="search">

Well, what if we could write something like …

	<input type="search" name="search">

With HTML5 we can. Feels much better, doesn’t it? Desktop browsers will render this in a similar way to a standard text field—until you start typing, that is. At this point, a small cross appears on the right side of the field. Notice the x in Figure 1. This lets you quickly clear the field, just like Safari’s built-in search field.

![](images/search-ios.png)

On a mobile device, however, things start to get interesting. Take the example iPhone shown in Figure 2; when you focus on an input using type="search", notice the keyboard, specifically the action button on the keyboard (bottom right). Did you spot that it says “Search” rather than the regular “Go”? It’s a subtle difference that most users won’t even notice, but those who do will afford themselves a wry smile.

![](images/search-safari.png)

As you’ve seen with the new attributes, browsers that don’t understand them will simply degrade gracefully. The same applies to all of the new input types discussed here. If a browser doesn’t understand type="search", it will default to type="text". This means you’re not losing anything. In fact, you’re using progressive enhancement and helping users to have a better experience. Let’s face it: filling out web forms isn’t very fun, so anything you can add to ensure a smoother experience, the better.

## Email control

![](images/email-ios.png)

Did you notice it this time? No? Look at the keyboard again. That’s right, the keyboard is different. There are dedicated keys for the @ and . characters to help you complete the field more efficiently. As we discussed with type="search", there is no downside to using type="email" right now. If a browser doesn’t support it, it will degrade to type="text". And in some browsers, users will get a helping hand.

## Number

## Date

## Range

## Etc

http://html5doctor.com/html5-forms-input-types/