---
title: "Designing a pixel-perfect design system"
description: "The challenges of bridging beautiful UIs from Figma to code."
date: 1695252037
---

2023 seems to be the year of the design system, with every other developer working on a "revolutionary" new way of building interfaces.

While a lot of these developers have produced great results, each with a coherent look and feel (e.g. see: [shadcn/ui](https://ui.shadcn.com/) and [reshaped](https://reshaped.so/)), many struggle with achieving similar pixel-perfection.

I have recently been working on a project, and in doing so, have had to implement some UI components myself— let's walk through a few of the things I've learned.

# The Figma trap

I'm a big advocate of Figma— a great piece of software, with a small learning curve, that allows almost anyone to quickly get started on designing things.

As great as it is for conceptualising, however, moving away from Figma and trying to translate designs into code can often be tricky. Things that feel natural in Figma may take hundreds of lines of code to recreate.

## Premature optimisation

"Premature optimisation" is a term often used in backend development talk to refer to systems which take performance optimisations into account from a very early stage.

This is commonly considered a naïve approach, as it can easily lead to getting stuck or creating a system that is overly rigid and not very extensible. The same can happen with design.

Design tokens have gained immense popularity in the design systems world over the last couple of years, and can now be easily implemented with Figma Variables. When used right, design tokens can lay the foundations for a consistent design language. But when used wrong, they can lead many into the trap of premature optimisation and excessive abstractions with tokens like `colors.button.primary.500.hover.bg` and `spacing.text.paragraph.leading.2xl`.

## Rendering differences

Take iOS Corner Smoothing as an example— Figma's implementation of Apple's "squircle" rounding of corners. Albeit subtle, a smoothing of 60% can really uplift a design, making it look far more fluid and easy on the eyes.

And while this takes less than 3 seconds in Figma, trying to recrete this effect in CSS doesn't fall short from tortorous.

Impossible? By no means. Just as long as you're okay with importing a [js library](https://github.com/PavelLaptev/css-houdini-squircle) onto the page, [limited browser support](https://ishoudinireadyyet.com/) and several hundred LOCs for a few pixels' difference.

Let's not forget text either, which looks vastly different in Figma, than it does on the web. Unless, of course, you turn on antialiasing... or [should you](https://usabilitypost.com/2012/11/05/stop-fixing-font-smoothing/)?

Achieving some of the visual results that Figma offers can sometimes come with tradeoffs, be that development time, accessibility or just painfully unnecessary complexity.

## Context matters

Figma is a blank slate that lets creativity flow. It's very easy, however, to forget about what exists beyond the blank slate. In reality, your design won't be the only thing present in the user's window. You will be fighting for screen space with a URL bar, tab bar, bookmarks bar, maybe a notch, notifications and many other visual distractions. This is easy to forget when designing in Figma, and putting a design into context can change its look entirely.

# Less is WAY more. Do less. Please do less.

You have created a beautiful skeumorphic button that implements iOS Corner Smoothing using CSS and JS, has 8 gradients, with different blend modes and 10 layers of shadows? Congratulations! You have created a button that nobody will use. Please stop.

To see that less is more, it helps to turn to some very successful design systems, used by public agencies and authorities— for instance, the [GOV.UK Design System](https://design-system.service.gov.uk/). Notice how their buttons don't even have rounded corners, but instead bold colors and use of typography? Beauty is often hiding in simplicity— trying to force it using tens of subtle visual tweaks detracts from the function of a component, and usually results in a design that you will hate in two weeks anyway.

# Inter is a beautiful font

This is the last point, this time about fonts.

You don't need to spend hours browsing Google Fonts in a quest to find the **PERFECT** fontface for your project. Honestly, Inter will do. Not to mention that Inter is an open-source typeface, maintained by people who have the time to discuss [cyrillic letterforms at length](https://github.com/rsms/inter/issues/567) (**NB:** if you're one of those people— I love you).

However, I'm well aware that you won't listen to my advice.

So, here's a better aproach to at least save you some time— pick out a few core fonts, ones along the lines of Inter, Public Sans and Libre Franklin; try those fonts for your project first; if you do feel the need to resort to another typeface, only **Sort by: Newest** when browsing, to save yourself from scrolling through hundres of fonts you are already well acquainted with.

