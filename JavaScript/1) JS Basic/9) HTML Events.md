- HTML events are things, triggered by actions, that occur to HTML elements.
	- When JS is used, JS can REACT to an event occurring to a HTML element.

## 1) HTML Events
- SOME examples of HTML events:
1) HTML webpage finished loading.
2) HTML input field was changed.
3) HTML button was clicked.

- event property will be the name of the desired event to react to.
- the value of this property will be some JS code that REACTS to the event.

```
<p eventName = "js code"> ahhhh </p>
```

EXAMPLE:

```
<p onload = "document.getElementById('demo').innerHTML = Date()">hello</p>
```

## COMMON HTML EVENTS:

1) onchange -> when HTML element has changed.
2) onclick -> when HTML element has been clicked.
3) onmouseover -> when a cursor moves over the HTML element.
4) onmouseout -> when a cursor is moved AWAY from the HTML element.
5) onkeydown -> user pushes a keyboard key.
6) onload -> when webpage has finished loading