---
layout: page
title: Hello World!
tagline: Supporting tagline
---
{% include JB/setup %}
<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

----------

# Done:

1. 修改`jekyll`中的`Markdown`解析器为[redcarpet](https://github.com/vmg/redcarpet)
	- `Maruku` 默认选项,但不支持中文，不推荐使用
	- `rdiscount` 速度快，推荐!语法增加.[详细](http://rdoc.info/github/davidfstr/rdiscount/master/RDiscount)
	- `redcarpet` github page 使用,需要修改`_config.yml`开启插件

	``` 
	# extensions of redcarpet
		redcarpet:
				extensions: ["no_intra_emphasis", "fenced_code_blocks", "autolink", "tables","with_toc_data","strikethrough"]
	```
2. 评论系统修改为国内的[多说](http://duoshuo.com)
3. 代码高亮使用`google-code-prettify` [详细](https://code.google.com/p/google-code-prettify/)
4. 更换主题 [Tom](http://tom.preston-werner.com/)
5. 修改主题 css,美化图片布局

-----------

# TO_DO:

1. 暗色系的代码高亮主题不起作用
2. 增加搜索功能



