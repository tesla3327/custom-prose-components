---
description: The first page of the blog.
---

# Test Page

This is just a page to test some things out.

It's filled with nonsense, and yes-sense (is that a thing?).

Yes, it's a thing.

Here's a link to the [second page](/second).

## Custom P Component

I made a custom `p` tag that lets you highlight a tag.

Try clicking on any of the paragraphs here, you'll see that they're highlighted.

You may also notice that the route hash changes — we're able to deep-link to a specifically highlighted section of the article.

Hello there _friend_!

We can use all sorts of markdown **styles** to make things happen.

Here's a link to [my website](https://michaelnthiessen.com).

## Some Random Images

Here is a picture of something nature like. Maybe it will be a mountain or a forest.
![](https://source.unsplash.com/random/1600x1200/?nature)

The next picture is going to be a car. It's random, so hopefully we get a good one.
![](https://source.unsplash.com/random/1600x1200/?car)

This last picture is of a city.

Why a city?

I don't know. I'm really just putting in random words here so it feels more like an actual blog post, but I don't really want to use lorem ipsum because that's lame.

I could have also used ChatGPT, but no one would like that — not even my mother who watches my talks on Vue and has no clue what I'm going on about.

So, here's a city picture.

![](https://source.unsplash.com/random/1600x1200/?city)

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
