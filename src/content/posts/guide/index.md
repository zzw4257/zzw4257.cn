---
title: Fuwari 实用向指南
published: 2015-09-28
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

| Attribute       | Description                                                                                                                                                                                                                     |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `title`       | The title of the post.                                                                                                                                                                                                          |
| `published`   | The date the post was published.                                                                                                                                                                                                |
| `description` | A short description of the post. Displayed on index page.                                                                                                                                                                       |
| `image`       | The cover image path of the post.``1. Start with `http://` or `https://`: Use web image``2. Start with `/`: For image in `public` dir``3. With none of the prefixes: Relative to the markdown file |
| `tags`        | The tags of the post.                                                                                                                                                                                                           |
| `category`    | The category of the post.                                                                                                                                                                                                       |
| `draft`       | If this post is still a draft, which won't be displayed.                                                                                                                                                                        |

## 扩展语法

我之前一直好奇为什么markdown写的文章会有很多fancy的范式，比如炫酷方框包裹的文字，比如隐去的效果...

难道我们真的要返璞归真在web语言层面实现这些效果吗？

### 【背景知识与前置技术栈】remark.js

remark 实际上是 unified.js 的一个插件

从markdown的解析过程入手

![remark流程](/pic/remark-pro.png)

remark会生成一个名为MDAST的语法树，然后我们就需要remark-rehype插件将这个语法书转化为HAST，进而转化为html文件

remark的地层使用micromark解析语法，然后用mdast-util-from-markdown插件辅助转化MDAST语法树

书写一个remark扩展实质上需要

- 编写一个 micromark 扩展；词法分析
- 编写一个 mdast-util-from-markdown 扩展；语法分析
- 编写一个 remark 扩展；


### micromark 扩展——NFA

我们需要设计函数式的状态机

状态转换关系是隐式的（implicit），表现在函数的调用过程中。

```python
state = initial_state;
while (!end_state) {
    state = state(code);
}
```

在 micromark 中，状态的[typescript 类型定义](https://github.com/micromark/micromark/blob/4346e010d537b05f622e636d001bd25c1140f6a1/packages/micromark-util-types/index.d.ts#L353)如下：

```typescript
/**
 * A character code.
 *
 * This is often the same as what `String#charCodeAt()` yields but micromark
 * adds meaning to certain other values.
 *
 * `null` represents the end of the input stream (called eof).
 * Negative integers are used instead of certain sequences of characters (such
 * as line endings and tabs).
 */
export type Code = number | null
/**
 * The main unit in the state machine: a function that gets a character code
 * and has certain effects.
 *
 * A state function should return another function: the next
 * state-as-a-function to go to.
 *
 * But there is one case where they return void: for the eof character code
 * (at the end of a value).
 * The reason being: well, there isn’t any state that makes sense, so void
 * works well.
 * Practically that has also helped: if for some reason it was a mistake, then
 * an exception is throw because there is no next function, meaning it
 * surfaces early.
 */
export type State = (code: Code) => State | void
```

:::note

下面的内容因为暂时看不懂咕咕咕了

:::

## [local]A

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
