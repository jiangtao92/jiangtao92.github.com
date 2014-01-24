---
layout: post
title: "Markdown解析器redcarpet"
description: ""
category: jekyll 博客构建笔记
tags: [jekyll]
---
{% include JB/setup %}

# redcarpet and extensions

> [传送门](https://github.com/vmg/redcarpet)

## 安装

`gem install redcarpet` 

> 如果是 Linux 需要 root 权限. ` sudo gem install redcarpet `

## 使用

修改`_config.yml` 中的 `markdown` 属性为 `redcarpet`.

## 属性

需要打开 `redcarpet `中的插件以支持其特殊 `markdown` 语法


- `no_intra_emphasis` : 不处理出现在字符串中的下划线. 例如: foo_bar_baz 不会变成 foo *bar* baz 如果需要斜体加空格

- `tables` : 支持表格语法,表格语法非原生`markdown` 语法,参考 `GFM` 语法

| Tables | Are | Cool |
| ------------- |:-------------:| -----:|
| col 3 is | right-aligned | $1600 |
| col 2 is | centered | $12 |
| zebra stripes | are neat | $1 |

- `autolink` : 网址自动转换成链接 不需要再加上 `<>`,需要以 `http://` or `www` 开头

- `fenced_code_blocks` : 三个` 环绕定义代码 默认开启

- `disable_indented_code_blocks` : 关闭原生`markdown` 中顶格四个空格定义代码语法

- `strikethrough` : 删除线 例如 ~~快乐的删除线~~ 使用两个`~`

- `underline` : `This is _underlined_ but this is still *italic*` --> This is _underlined_ but this is still *italic*

- `space_after_headers` : `#` 之后需要增加一个空格才可以表示为标题 `#this is my header` 不会是标题

- `superscript` : 上标, 例如 : `this is the 2^(nd) time` --> this is the 2^(nd) time

- `footnotes` 和 `highlight`  需要等到 `jekyll 3.0` 之后才会支持

## 配置

在`_config.yml` 中增加`redcarpet`的 `extensions`选项:

```
# extensions of redcarpet
redcarpet:
  extensions: ["no_intra_emphasis", "fenced_code_blocks", "autolink", "tables","with_toc_data","strikethrough","underline","superscript"]
# more(http://chaoskeh.com/blog/markdown-and-redcarpet.html)
# more(https://github.com/vmg/redcarpet)
```

## warning

- 加粗 和 斜体 之后不要增加空格,不然会不转换
	- `* 斜体 *` -> * 斜体 *

	- `** 粗体 **` -> ** 粗体 **

	- `_ 斜体 _` -> _ 斜体 _

	- `__ 粗体 __` -> __ 粗体 __
	
> 坑死爹了,找了半天才明白

- `underline` 下划线 开启之后 `_下划线_ 不是 *斜体*` -> _下划线_ 不是 *斜体* 

---
### 其他 `markdown` 解析器

- [par](https://github.com/limodou/par)
- [rdiscount](https://github.com/davidfstr/rdiscount)