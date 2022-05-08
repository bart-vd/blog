---
title: "Bem"
date: 2022-05-04T22:26:21+02:00
draft: false
tags: ["CSS", "BEM"]
---
One of the things I struggle with when styling a website in css or Sass is naming things. This sounds pretty mundaine, but without a good naming scheme, one quickly ends up using the same class names for different things.

> “If names be not correct, language is not in accordance with the truth of things.”
> ― Confucius, The Analects of Confucius

In my search for a solution, I stumbled upon the [BEM methodology](https://getbem.com). BEM stands for Block, Element and Modifier. It's a simple naming convention designed to make front end code easier to read and understand, but also easier to scale.

In essence, using BEM means naming your classes something like this:

```scss
.block__element--modifier
```

In HTML, any DOM node within a block can be an element. Within a given block, all elements are semantically equal.

```html
<div class="block">
  <span class="block__element"></span>
</div>
```

In CSS, BEM insists on using class name selectors only. Also, no tag names or ids are used, and there is no dependency on other blocks/elements on a page.

```scss
.block__elem { color: #000 }
```

Modifiers in BEM then, are flags on blocks or elements, used to change appearance, behavior or state. In HTML, it's an extra class name which you add to a block/element DOM node. Add modifier classes only to blocks/elements they modify, and keep the original class:

```html
<div class="block block--mod">...</div>
<div class="block block--size-big block--shadow-yes">...</div>
```

Since I'm a sucker for this sort of methodologies, I immediately took to BEM, and implemented it in this site.

One of the problems I encountered, and which prevented me from fully implementing BEM, is the fact that static site generator [Hugo](https://gohugo.io) does not have a way of adding classes to the Markdown files that are the basis for the final posts on the site.

This means that, contrary to what BEM suggests, I _do_ have to use HTML elements as selectors, so that I can add some styling to things like bold text, headers, etc. But other then that, using BEM suits me just fine.

To finish up, here are some great articles on BEM to get you started:

- [Scaling Down The BEM Methodology For Small Projects](https://www.smashingmagazine.com/2014/07/bem-methodology-for-small-projects/)
- [MindBEMding – getting your head ’round BEM syntax](https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
- [Objects in Space - A style-guide for modular SASS using SMACSS and BEM](https://medium.com/objects-in-space/objects-in-space-f6f404727)
- [How to Scale and Maintain Legacy CSS with Sass and SMACSS](https://webuild.envato.com/blog/how-to-scale-and-maintain-legacy-css-with-sass-and-smacss/)
- [BEM Cheat Sheet](https://9elements.com/bem-cheat-sheet/)
- [Understanding CSS BEM](https://codeburst.io/understanding-css-bem-naming-convention-a8cca116d252)
- [BEMIT: Taking the BEM Naming Convention a Step Further](https://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/)
