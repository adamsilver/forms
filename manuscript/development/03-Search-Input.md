# Search input

I> ## Important
I>
I> The search control, where unsupported degrades down to a text input.

When we talk about search, we’re not just talking about Google, Bing, or Yahoo. We’re talking about the search field on that e-commerce site you just made a purchase from, on Wikipedia, and even on your personal blog. It’s probably the most common action performed on the Web every day, yet it’s not marked up very semantically, is it? We all tend to write something like this:

	<input type="text" name="search">

Well, what if we could write something like …

	<input type="search" name="search">

With HTML5 we can. Feels much better, doesn’t it? Desktop browsers will render this in a similar way to a standard text field—until you start typing, that is. At this point, a small cross appears on the right side of the field. Notice the x in Figure 1. This lets you quickly clear the field, just like Safari’s built-in search field.

![Search IOS](images/search-ios.png)

On a mobile device, however, things start to get interesting. Take the example iPhone shown in Figure 2; when you focus on an input using type="search", notice the keyboard, specifically the action button on the keyboard (bottom right). Did you spot that it says “Search” rather than the regular “Go”? It’s a subtle difference that most users won’t even notice, but those who do will afford themselves a wry smile.

![Search Safari](images/search-safari.png)

As you’ve seen with the new attributes, browsers that don’t understand them will simply degrade gracefully. The same applies to all of the new input types discussed here. If a browser doesn’t understand type="search", it will default to type="text". This means you’re not losing anything. In fact, you’re using progressive enhancement and helping users to have a better experience. Let’s face it: filling out web forms isn’t very fun, so anything you can add to ensure a smoother experience, the better.