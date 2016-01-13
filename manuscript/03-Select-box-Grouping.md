### Grouping options

Dependening on the situation, grouping parts of a select menu's options is advisable. Take the following example. It is a list of cuisines. The most popular are grouped at the top for quick selection. Providing benefit to the user, by indicating how this large list is organised and how they can go about using it. Much better than a long list of ungrouped options.

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