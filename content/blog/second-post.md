---
title: 'hello, again'
description: 'this is a description'
date: 2024-05-14
---

here's a brand new blog post, buried inside the `blog/` folder server-side,
so i can test the slug routing.

i have [the first post](./first-post.md) in a directory above, so
when you go to `averywald.github.io/blog/first-post`, you should get it.

BUT, if you try `averywald.github.io/blog/second-post`, it *miiiiiight* not work.
Technically, it's at `averywald.github.io/blog/blog/second-post`

console.log('hello');