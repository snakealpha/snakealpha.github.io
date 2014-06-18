---
layout: page
title: 专题

sort-id: 3
---

<script type="text/javascript">
	$(document).ready(function(){
		$(".item-title").click(function(){
			$(".item-content#" + this.id).slideToggle("fast");
		})
	})
</script>

<small class="masthead-title">点击专题名称展开或收起专题目录</small>

{% if site.data.topics == false %}
<p class="message">当前还没有专题</p>
{% endif %}

{% assign post_list = site.posts | sort: 'topic-sort' %}
{% for topic in site.data.topics %}
<div class="item-title" id="{{ topic.topic }}">
	<h2>{{ topic.topic }}      <small>{% if topic.is_serializing == true %}连载中...{% else %}已完结{% endif %}</small></h2>
	<p class="topic-desc">
		{{ topic.desc }}
	</p>
</div>
<div class="item-content" id="{{ topic.topic }}">
	<ul>
    	{% for post in post_list %}
    	{% if post.topic == topic.topic %}
        	<li><a href="{{ post.topic-sort }}.   {{ post.url }}">{{ post.title }}</a>      <small>{{ post.date | date:"%d/%m/%Y" }}</small></li>
        {% endif %}
    	{% endfor %}
	</ul>
</div>
<hr width="70%" />
{% endfor %}
