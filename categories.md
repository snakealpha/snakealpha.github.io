---
layout: page
title: 分类
---

<script type="text/javascript">
	$(document).ready(function(){
		$(".item-title").click(function(){
			$(".item-content#" + this.id).slideToggle("fast");
		})
	})
</script>

<small class="masthead-title">点击分类名称展开或收起文章列表</small>

{% for category in site.categories %}
<div class="item-title" id="{{ category | first }}">
	<h2>{{ category | first }}      <small>共{{ category | last | size }}篇文章</small></h2>	
</div>
<div class="item-content" id="{{ category | first }}">
	<ul>
    	{% for post in category.last %}
        	<li><a href="{{ post.url }}">{{ post.title }}</a>      <small>{{ post.date | date:"%d/%m/%Y"}}</small></li>
    	{% endfor %}
	</ul>
</div>
<hr width="70%" />
{% endfor %}
