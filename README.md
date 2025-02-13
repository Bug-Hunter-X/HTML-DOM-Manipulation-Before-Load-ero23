# Uncommon HTML Bug: DOM Manipulation Before Load

This repository demonstrates a subtle bug related to manipulating the DOM (Document Object Model) before the HTML document is fully loaded.  The bug occurs when JavaScript attempts to interact with an element that hasn't yet been parsed and added to the DOM tree by the browser.

**The Problem:**

The `bug.html` file contains a simple HTML page with a div element. A JavaScript script attempts to hide this div by changing its display style. However, this script runs before the browser has fully loaded the div element.  This can lead to unexpected behavior:

- **Error:** In some browsers, a JavaScript error (like `TypeError: Cannot read properties of null (reading 'style')`) might occur.
- **No Visible Effect:** In other browsers, the script might simply fail silently, leaving the div element visible.

**The Solution:**

The `bugSolution.html` demonstrates the correct approach.  It uses the `DOMContentLoaded` event listener to ensure that the script runs only after the HTML document is completely parsed and ready.

This approach is more robust and prevents errors caused by trying to manipulate elements that don't yet exist in the DOM.

This example highlights the importance of understanding the timing of JavaScript execution in relation to the browser's DOM loading process.