---
title: CSS Basics - The Box Model
date: 2014-10-20 21:54 UTC
tags: Learning, DBC, CSS
---

Everything that goes into a webpage is treated as a rectangular box - even if an object or element itself is not a rectangle. This concept, referred to as The Box Model, is what forms the basis of CSS. CSS, or cascading style sheets, are used to format the presentation details of a webpage such as layout, colors, fonts. Separating CSS from content makes it easier and faster to make formatting changes.

The Box Model illustrates that each element is a rectangle with padding, borders, and margins.

![Box Model](/images/boxmodel.jpg)

Elements have:

<li> **Padding**: (transparent) Like an internal margin or frame, separating the element from its border.</li>

<li> **Border**: (visible) A border is visible frame around an element and can be customized by different thicknesses, colors and styles.</li>

<li>**Margin**: (transparent) The outside border of an element, generally used for placing elements on the screen, or creating spacing between elements.</li>

This means that the actual width and height of an element are a calculation:

<li>**ACTUAL WIDTH**= margin-left + border-left + padding-left + WIDTH + padding-right + border-right + margin-right</li>
<li>**ACTUAL HEIGHT**= margin-top + border-top + padding-top + HEIGHT + padding-bottom + border-bottom + margin-bottom</li>