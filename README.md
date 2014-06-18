# Snake's blog
This blog is powered by Github Pages/[Jekyll](http://jekyllrb.com), and using a modified theme of [Lanyon](https://github.com/poole/lanyon) from [mdo](https://github.com/mdo).

If you wanna functions that not support in Lanyon, as these:
- Display a brief but not all content of post;
- Discuss from [Disqus](http://disqus.com/);
- Add a [CC License](http://creativecommons.org/) icon easily by using by-nc-nd, by-nc-sa, by-nc, by-nd, by-sa and by in Front-Matter;
- Use category, tag and topic index page,

Please fork and modify this project to your own repo.


## How to

### Use Topics
The topic is a new designed feature to make a series of posts in a common subject, which is like a book.

For using this feature, you should do the following two steps:
- Add a new topic metadata to the _data/topics.md file.
- Add some custom field to your post's front matter.

Metadatas of a topic is like this:

``` topics.yml

- topic: A
  is_serializing: true
  desc: This is a topic test.

- topic: B
  is_serializing: false
  desc: This is another topic test.

```
You can specify the name and description of a topic, and also specify if this topic is under working.

Post's front matter should add two fields:
``` post.md
topic: B
topic-sort: 2
```
While topic field is to figure out the topic's name, topic-sort will be used to determining the sort of posts of this topic.

After doing this, your new topic should appear in your topic index page.

### Add CC License
Only add a field with the field's name between by-nc-nd, by-nc-sa, by-nc, by-nd, by-sa, by and set its value as true.

A strict license will cover the loose ones.

## Note
The root repo of this blog is the built pages of this blog; the sources are in the 'workspace' dir. Please build the blog in your own jekyll environment first, this is to avoid the problems caused by the different versions of Github Pages and your own jekyll, and avoid the bugs in Github Pages' jekyll 1.5.1.
Since [elecelf](http://snakealpha.github.io) is a Chinese blog, some words are in chinese. Please change them to your own language yourself.


## License

Open sourced under the [MIT license](LICENSE.md).
