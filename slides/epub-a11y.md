- What’s a11y?
- How to make it happen?
- All your guidelines
- Behold: accessible EPUB <!-- .element: class="selected" -->
- Automatic for the people
- Manual checking

<!-- .element: class="toc no-bullets" -->

---

## Behold: accessible EPUB

---

### A tale of two reading experiences

This is a video of a user navigating the headings of a book with a screenreader.

---

<video src="assets/lean-bad-headings-screencast.mov"/>

---

Seemed ok, right? I mean, the contrast is awful, but there were a few headings and some text? So it looks like it's working?

---

But then again, how would we know what we were missing if the AT didn't pick up on it?

---

<video src="assets/lean-bad-headings-screencast.mov"/>

---

I notice a lot of pages between headings. That would be a lot of skimming. I wish there headings more often than every 30 pages.

---

Oh wait, there are more headings! But they were marked up incorrectly, so the screenreader never found them.

---

Magic fixes ..

..<!-- .element: class="fragment" -->

..<!-- .element: class="fragment" -->

---

<video src="assets/lean-fixed-screencast.mov"/>

---

### Let's take a moment

To acknowledge the importance of hiring accessibility testers.

Testing with AT is not easy if you're not an expert user.

E.g. making those 10 second screenreader videos took me forever.

---

### EPUB and the Web

EPUB 3 is built on web languages (HTML, CSS) <!-- .element: class="fragment" -->

And the web has extensive accessibility support (WAI, WCAG, ARIA, A11y Tree) <!-- .element: class="fragment" -->

This is great! So all the accessibility stuff that works on the web should work in my EPUB? Yes but... <!-- .element: class="fragment" -->

---

### Differences between EPUB and the Web when it comes to a11y

  - Reading order: Unlike websites, books have a linear progression 	
  - There's always a table of contents                                <!-- .element: class="fragment" -->
  - Discovery metadata                                                <!-- .element: class="fragment" -->    

---

The ecosystem is complicated

![Publishing supply chain](assets/ebookflow.jpg)

(from [JISC](https://accessibility.jiscinvolve.org/wp/))

---

### Devils and details

😈

Specific ways you can optimize your usage of EPUB accessibility features.

---

### (table of) Content(s) is king

Enables users to choose where to go in the content.

This is a very important mechanism for non-visual readers. <!-- .element: class="fragment" -->

---

### Putting yourself out there

Show off your accessibility features

with discovery metadata in the package document. <!-- .element: class="fragment" -->
```
<meta property="schema:accessMode">textual</meta>
<meta property="schema:accessibilityHazard">flashing</meta>
<meta property="schema:accessibilityFeature">alternativeText</meta>
```
<!-- .element: class="fragment" style="width: 100%" -->

---

### So like, what's your type?

And why it might not impact what you think it does. <!-- .element: class="fragment" -->

---

### `epub:type`

The `epub:type` attribute was introduced in EPUB 3 as a way to extend semantics.

Values come from EPUB 3's extensive structural semantics vocabulary. <!-- .element: class="fragment" -->

---

The promise of `epub:type` was to extend a generic XHTML element with publishing-specific refinements.

```
<div epub:type="prologue">"Lorem ipsum dolor," he thought.</div>
```
  <!-- .element: class="fragment" -->

---

And then, reading systems could expose this information to users, which would really enhance accessibility.

---

### Reality check

You can very thoroughly add `epub:type` everywhere, but you'll notice that the reading experience doesn't change.

Why? <!-- .element: class="fragment" -->

It was never really adopted by reading systems 🤷‍♀️ <!-- .element: class="fragment" -->

---

### The exception: footnotes and endnotes

A reading system might pop up a little box to show the footnote inline:

```
<p>lorum ipsum.<a epub:type="noteref" href="#fn01">1</a></p>
<aside epub:type="footnote">
…
</aside>
```
<!-- .element: class="fragment" -->

---

Beyond this, though, there are no known implementations that provide an enhanced user experience via `epub:type`.

Don't rely on it alone. <!-- .element: class="fragment" -->

---

### ARIA

Remember how we talked about EPUB leveraging web accessibility?

---

The W3C created ARIA specifically for making content more accessible.

ARIA consists of roles, features, and properties. <!-- .element: class="fragment" -->

And, of course, rules for how to use it. <!-- .element: class="fragment" -->

```
<div role="checkbox"
     aria-checked="false"
     tabindex="0">
  ...
</div>
```
<!-- .element: class="fragment" -->

---

Let's see how `epub:type` and ARIA are related.

---

### Roleplay

There's a set of digital publishing roles for ARIA (ARIA DPUB).

E.g. <!-- .element: class="fragment" -->

```
<section role="chapter" aria-label="chapter 1">
  <p>Once upon a time …</p>
  …
</section>
```
<!-- .element: class="fragment" -->

---

But, be careful -- don't assume a 1-1 mapping between `epub:type` and ARIA

```
<body epub:type="cover">
  <h1>Sports!</h1>
  <img src="cover.jpg" alt="An olympic athlete in mid-pole vault"/>
</body>
```
<!-- .element: class="fragment" -->

vs <!-- .element: class="fragment" -->

```
<body epub:type="cover">
  <h1>Sports!</h1>
  <img role="doc-cover" src="cover.jpg" alt="An olympic athlete in mid-pole vault"/>
</body>
```
<!-- .element: class="fragment" -->

---

Handy reference: [EPUB ARIA Authoring](https://idpf.github.io/epub-guides/epub-aria-authoring/)

---

### Tell us about yourselves

What are some accessibility issues you're facing?

What solutions have you tried that have[n't] helped?
