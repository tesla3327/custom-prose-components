---
description: The first page of the blog.
---

# Test Page

This is just a page to test some things out.

It's filled with nonsense, and yes-sense (is that a thing?).

Yes, it's a thing.

Here's a link to the [second page](/second).

A link to the [second page](/second#Cotc) with a highlighted paragraph.

## Custom P Component

I made a custom `p` tag that lets you highlight a tag.

Try clicking on any of the paragraphs here, you'll see that they're highlighted.

You may also notice that the route hash changes — we're able to deep-link to a specifically highlighted section of the article.

Hello there _friend_!

We can use all sorts of markdown **styles** to make things happen.

Here's a link to [my website](https://michaelnthiessen.com).

This one [links to the Vue website](https://vuejs.org), and this one [links to the Nuxt website](https://nuxt.com).

## Some Random Images

Here's a picture of the Scottish Highlands:
![](https://source.unsplash.com/green-field-under-white-cloudy-sky-UiE-kcDnIGs/6000x4000)

The next picture is of a car:
![](https://source.unsplash.com/blue-volkswagen-beetle-on-grass-field-7HNftpNvqho/6000x4000)

This last picture is of a city.

Why a city?

I don't know. I'm really just putting in random words here so it feels more like an actual blog post, but I don't really want to use lorem ipsum because that's lame.

I could have also used ChatGPT, but no one would like that — not even my mother who watches my talks on Vue and has no clue what I'm going on about.

So, here's a city picture.

![](https://source.unsplash.com/aerial-photograph-of-cityscape-ErccHKWjG18/6000x4000)

## What is happening?

This is a new section.

Check out this code:

```html
<template>
  <div class="prose">{{ prop }}</div>
</template>

<script setup>
  defineProps({
    prop: String,
  });
</script>
```

Some more code, this time it's TypeScript. And this time we can see what the file is called:

```ts [types.ts]
type Wallet = {
  money: Number;
  idCard: UserIdCard;
  giftCards: GiftCard[];
};
```

You can see there's a `GiftCard` type but we haven't added that yet.

### Nothing much

Here we have yet another section.
