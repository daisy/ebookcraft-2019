- What’s a11y?
- How to make it happen?
- All your guidelines
- Behold: accessible EPUB
- Automatic for the people
- Manual checking <!-- .element: class="selected" -->

<!-- .element: class="toc no-bullets" -->

---

## Manual checking: blood, sweat, and .. oh that wasn't so bad

---

We just finished talking about how wonderful automated accessibility checking is!

---

But there are things that robots don't do well.

![Robot pouring milk over cereal and missing by a lot](assets/milkbot.gif)

---

| Example | Passes auto? | Actually accessible? |
|---------|--------------|----------------------|
|`<img alt="Picture" .../>`|✅|🚫|


---

<table>
  <thead>
    <tr>
      <th>Example</th>
      <th>Passes auto?</th>
      <th>Actually accessible?</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
<code>
<pre>
&lt;spine&gt;
  &lt;itemref idref="thirdChapter"/&gt;
  &lt;itemref idref="firstChapter"/&gt;
  &lt;itemref idref="secondChapter"/&gt;
&lt;/spine&gt;
</pre>
</code>
        </td>
        <td>✅</td>
        <td>😱</td>
  </tbody>
</table>

---

| Example | Passes auto? | Actually accessible? |
|---------|--------------|----------------------|
|`<img alt="An entire page of words" .../>`|🤠|🤬|

---

### So what does manual testing entail?

The EPUB Accessibility spec describes WCAG usage for EPUB

as well as EPUB-specific requirements.

---

So, just read all the documents:

- EPUB Accessibility 1.0 <!-- .element: class="fragment" -->
- EPUB 3 <!-- .element: class="fragment" -->
- WCAG <!-- .element: class="fragment" -->
- ARIA <!-- .element: class="fragment" -->
- DPUB-ARIA <!-- .element: class="fragment" -->
- DIAGRAM (image descriptions) <!-- .element: class="fragment" -->

---

And then cross-reference that with what's in your EPUB.

<p>
<style>
span.extra {
  color: yellow;
}
span.extraa {
  color: orange;
  font-size: larger;
}
</style>
<span class="fragment">Video?</span> <span class="fragment">Audio?</span> <span class="fragment">Text?</span> <span class="fragment">Images?</span> <span class="fragment extra">Captions?</span> <span class="fragment extra">Tables?</span> <span class="fragment extra">Stylish but illegible fonts?</span> <span class="fragment extra extraa">Print page equivalents?</span> <span class="fragment extra extraa">Media overlays?</span>
</p>

Just to name a few. <!-- .element: class="fragment" -->

---

And 5 hours later, you've got 25 browser tabs, 2 text editors, and 3 reading systems open; and you're not sure if this was really a good idea.

---

### Do you feel overwhelmed?

All you wanted to do was make your book accessible! It'll be easy, they said...

![Infomercial: a person opening a cupboard and having tons of clutter fall on them.](assets/infomercial.gif)<!-- .element: class="fragment" -->

---

### Truth

Manual testing takes time and patience and resources.

---

### SMART

SMART is a tool from DAISY. <!-- .element: class="fragment" -->

It walks you through checkpoints based on features in your publication. <!-- .element: class="fragment" -->

It asks you some questions and then generates a report. <!-- .element: class="fragment" -->

It works in conjunction with Ace. <!-- .element: class="fragment" -->

---

### SMART Demo

![Dancing bird](https://media0.giphy.com/media/ZKzYiPVnIh0c0/giphy.gif?cid=3640f6095c8f20d96d2f574c63312997)

---

### Try SMART

[smart.daisy.org](https://smart.daisy.org) ➡ sign up
