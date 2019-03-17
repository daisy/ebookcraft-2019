## Behold: accessible EPUB

---

### A tale of two reading experiences

DEMO accessible vs inaccessible reading experiences

---

### Takeaway


#### Yes ✅

- Appropriate semantics
- Accurate image descriptions
- Contrast laws obeyed

#### No 🚫

- Lack of semantics or used incorrectly
- Bad or nonexistent image descriptions
- Poor contrast

---

### EPUB and the Web

EPUB 3 is built on web languages (HTML, CSS)

And the web has extensive accessibility support (WAI, WCAG, ARIA, A11y Tree)

This is great! So all the accessibility stuff that works on the web should work in my EPUB? Yes but...

---

### Differences between EPUB and the Web when it comes to a11y

Just to make sure we state the obvious: the ecosystem is complicated!

And, conceptually, the material isn't quite the same.

  - Reading order: Unlike websites, books have a linear progression
  - Explicit TOC
  - Discovery metadata

---

### Devils and details

Let's dig in to some of the specifics regarding what you can do to optimize your usage of EPUB accessibility features.

---

### (table of) Content(s) is king

Enables users to choose where to go in the content.

This is a very important mechanism for non-visual readers.

---

### Putting yourself out there

Show off your accessibility features!

.. with discovery metadata in the package document.

    <meta property="schema:accessMode">textual</meta>
    <meta property="schema:accessibilityHazard">flashing</meta>
    <meta property="schema:accessibilityFeature">alternativeText</meta>
    <meta property="schema:accessibilitySummary">
       The publication is missing alternative text for complex diagrams.
       The publication otherwise meets WCAG 2.0 Level A.
    </meta>


---

### So what's your type?

And why it might not impact what you think it does.

---

### `epub:type`

The `epub:type` attribute was introduced in EPUB 3 as a way to extend semantics.

Values come from EPUB 3's extensive structural semantics vocabulary.

---

### Reality check

You can very thoroughly add `epub:type` everywhere, but you'll notice that the reading experience doesn't change.

Why?

It was never really adopted by reading systems 🤷‍♀️

---

### The exception: footnotes and endnotes

A reading system might pop up a little box to show the footnote inline:

    <p>lorum ipsum.<a epub:type="noteref" href="#fn01">1</a></p>
    <aside epub:type="footnote">
    …
    </aside>

Beyond this, though, there are no known implementations that provide an enhanced user experience via `epub:type`.

---

### ARIA

Remember how we talked about EPUB leveraging web accessibility?

The web has a feature called `ARIA`, designed specifically for making content more accessible.

`ARIA` consists of roles, features, and properties. And, of course, rules for how to use it.

Let's see how `epub:type` and `ARIA` are related.

---

### Roleplay

ARIA roles and labels:

    <section role="chapter" aria-label="chapter 1">
      <p>Once upon a time …</p>
      …
    </section>

But, it's not a 1-1 mapping!

    <body epub:type="cover">
      <h1>Sports!</h1>
      <img src="cover.jpg" alt="An olympic athlete in mid-pole vault"/>
    </body>

vs

    <body epub:type="cover">
      <h1>Sports!</h1>
      <img role="doc-cover" src="cover.jpg" alt="An olympic athlete in mid-pole vault"/>
    </body>


Handy reference: [EPUB ARIA Authoring](https://idpf.github.io/epub-guides/epub-aria-authoring/)

---

### Tell us about yourselves

What are some accessibility issues you're facing?

What solutions have you tried that have helped?
