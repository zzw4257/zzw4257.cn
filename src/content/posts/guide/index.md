---
title: Fuwari 实用向指南
published: 2025-09-28
description: 大概是给我自己看的一些东西：关于这个网站采用的架构
image: "./cover.jpeg"
tags: [note,links]
category: Unconcerned
draft: false
---

# Fuwari 实用向指南

## 前置属性

```yaml
---
title: My First Blog Post
published: 2023-09-09
description: This is the first post of my new Astro blog.
image: ./cover.jpg
tags: [Foo, Bar]
category: Front-end
draft: false
---
```

| Attribute     | Description                                                  |
| ------------- | ------------------------------------------------------------ |
| `title`       | The title of the post.                                       |
| `published`   | The date the post was published.                             |
| `description` | A short description of the post. Displayed on index page.    |
| `image`       | The cover image path of the post.<br/>1. Start with `http://` or `https://`: Use web image<br/>2. Start with `/`: For image in `public` dir<br/>3. With none of the prefixes: Relative to the markdown file |
| `tags`        | The tags of the post.                                        |
| `category`    | The category of the post.                                    |
| `draft`       | If this post is still a draft, which won't be displayed.     |



## 扩展语法

::github{repo="/zzw4257"}

:::note
高亮内容，突出信息
:::

:::tip
提示性
:::

:::important

重点突出
:::

:::warning

警示性内容

:::

:::caution

警告性内容

:::

:::note[我的笔记]

我的内容

:::