# Empathetic Web Accessibility
A checklist of human-centered accessibility tests for web development

## The Checklist
1. [The content flows in a linear, meaningful order no matter how I view it](#1-the-content-flows-in-a-linear-meaningful-order-no-matter-how-i-view-it)
2. [The page responds to my viewport dimensions and zoom level](#2-the-page-responds-to-my-viewport-dimensions-and-zoom-level)
3. [The document is semantically structured to help assistive technologies interpret the content](#3-the-document-is-semantically-structured-to-help-assistive-technologies-interpret-the-content)
4. [Meaning is preserved when I cannot perceive differences between colors](#4-meaning-is-preserved-when-i-cannot-perceive-differences-between-colors)
5. [It's always easy to interact with dynamic content](#5-its-always-easy-to-interact-with-dynamic-content)

### How to use this checklist
At every step in the process, consider what barriers people might encounter when using your product and eliminate them when possible.  Use this checklist as part of a final check, especially when reviewing code.

### Why isn't automated testing enough?
Creating a web experience accessible to everyone requires an understanding of the challenges people face when using digital products.  Automated accessibility tools are a useful tool to identify possible problems, but cannot prove accessibility.

### Why is accessibility important?
You might find yourself required by law or contract to be accessible via WCAG compliance.  However, designing for everyone is also the right thing to do.  In many cases, accessible development also enforces good programming practices.

Our products aren't always used in ideal environments.  At some point you are likely to find yourself benefiting from accessible design practices (if you haven't already).

Have you used your computer or phone in a high glare environment?
Used a website while distracted?
Tried to navigate a website on your phone with gloves on?


### 1. The content flows in a meaningful order no matter how I view it
There are many ways people view content on the web. Whether using a screen reader, keyboard-based navigation, or as a developer viewing source, the fundamental linear document flow should match the visual flow.

Layout and style can be used to enhance the page structure, but should not change the way it's interpreted.

Example Violation
```html
<body>
	<div class="sidebar">
		<!-- Secondary Content -->
	</div>
	<div>
		<!-- Primary Content -->
	</div>
</body>
```

Also see:
https://www.w3.org/WAI/test-evaluate/preliminary/#structure

### 2. The page responds to my viewport dimensions and zoom level
Also called "page reflow," responsive design is critical to accessibility.  Make all features and content available to reasonable viewport configurations, including zoom level.

Additionally, consider that many people do not have regular access to computers and may use their phones as their primary access to your content or service.

To test, increase the level of zoom to ensure all content can be easily viewed at a larger size.

Also see:
https://www.w3.org/WAI/WCAG21/Understanding/reflow.html
https://www.w3.org/WAI/test-evaluate/preliminary/#resize

### 3. The document is semantically structured to help assistive technologies interpret the content
As much as possible, the structure of the document should describe the meaning of the content.  Use semantically appropriate HTML elements that can be understood by browsers and assistive technologies, which provides built-in accessibility features.

For example, all browsers and screen readers know how to understand and interpret the `<a>`  and `<button>` elements.  When native elements are not available, use the appropriate aria tags.

To test, review the generated HTML markup. Evaluate each element to determine if a more appropriate tag exists.

Also see:
https://reactjs.org/docs/accessibility.html#semantic-html
https://developer.mozilla.org/en-US/docs/Web/HTML/Element


### 4. Meaning is preserved when I cannot perceive differences between colors
Color should be supplemental, and not used alone to convey meaning.

There are many reasons people may have trouble distinguishing between colors including various forms of colorblindness, low-vision (including environmental causes such as high glare), or low quality displays.  Keep in mind that not all colorblindness is the same, so it's safest to simply avoid relying on color alone.

Also see:
https://www.smashingmagazine.com/2014/10/color-contrast-tips-and-tools-for-accessibility/

### 5. It's always easy to interact with dynamic content
When interacting with dynamic content, focus is visible and flows appropriately. If the document contains interactive elements, focus should be correctly directed between active elements.

Interactive elements are large enough to be easily targeted via an imprecise click or tap, and a missed target has minimal consequences.

To test, navigate all flows with the keyboard.  For example, a button that opens a modal should move the focus to the new content.

Also see:
https://reactjs.org/docs/accessibility.html#programmatically-managing-focus
https://www.w3.org/WAI/test-evaluate/preliminary/#interaction
