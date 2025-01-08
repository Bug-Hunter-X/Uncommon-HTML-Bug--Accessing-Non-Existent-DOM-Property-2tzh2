# Uncommon HTML Bug: Accessing Non-Existent DOM Property

This repository demonstrates a subtle bug that can occur in HTML when attempting to access properties of DOM elements before they are fully loaded or properly initialized.  The bug manifests as a runtime error.

## The Bug

The `bug.html` file contains a script that attempts to access the `nonExistentProperty` of the `myDiv` element immediately after the element is defined. However, the script executes before the browser has fully parsed and rendered the HTML, resulting in the property being undefined, and thus generating an error.

## The Solution

The `solution.html` file provides a corrected approach. It uses `document.getElementById` to retrieve a reference to `myDiv`. Then, an event listener is attached to the `DOMContentLoaded` event.  This ensures that the script executes only after the complete HTML document has been loaded and parsed, thereby guaranteeing that `myDiv` is fully initialized and ready for interaction.  This is a best practice for interacting with DOM elements.