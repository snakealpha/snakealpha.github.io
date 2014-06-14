---
layout: post
title: Introducing Lanyon

tag: [test, jekyll]
categories: [html, jekyll]

by-nc: true
---

中文测试
本Post用于博客补充功能的测试。

Jekyll的原本文章内容依然保留在本文章中。

[Jekyll](http://jekyllrb.com) theme that places content first by tucking away navigation in a hidden drawer. It's based on [Poole](http://getpoole.com), the Jekyll butler.

### Built on Poole

Poole is the Jekyll Butler, serving as an upstanding and effective foundation for Jekyll themes by [@mdo](https://twitter.com/mdo). Poole, and every theme built on it (like Lanyon here) includes the following:

* Complete Jekyll setup included (layouts, config, [404](/404), [RSS feed](/atom.xml), posts, and [example page](/about))
* Mobile friendly design and development
* Easily scalable text and component sizing with `rem` units in the CSS
* Support for a wide gamut of HTML elements
* Related posts (time-based, because Jekyll) below each post
* Syntax highlighting, courtesy Pygments (the Python-based code snippet highlighter)

### Lanyon features

In addition to the features of Poole, Lanyon adds the following:

* Toggleable sliding sidebar (built with only CSS) via **☰** link in top corner
* Sidebar includes support for textual modules and a dynamically generated navigation with active link support
* Two orientations for content and sidebar, default (left sidebar) and [reverse](https://github.com/poole/lanyon#reverse-layout) (right sidebar), available via `<body>` classes
* [Eight optional color schemes](https://github.com/poole/lanyon#themes), available via `<body>` classes

[Head to the readme](https://github.com/poole/lanyon#readme) to learn more.

### Browser support

Lanyon is by preference a forward-thinking project. In addition to the latest versions of Chrome, Safari (mobile and desktop), and Firefox, it is only compatible with Internet Explorer 9 and above.

### Download

Lanyon is developed on and hosted with GitHub. Head to the <a href="https://github.com/poole/lanyon">GitHub repository</a> for downloads, bug reports, and features requests.

Thanks!

Code Test:


```csharp
using System;
using System.Collections.Generic;

namespace Elecelf.MultiThreadUtils
{
    /// <summary>
    /// This class is used to keep a producer-custom queue to fit the query that some operations must be excuted in the main thread, but raised in a child thread.
    /// 
    /// Author: elecelf, Snake Liu
    /// Log:    Apr.2 2014  Create.
    /// </summary>
    class AsyncMessageQueue<T>
    {
        protected Dictionary<string, Queue<T>> queue = new Dictionary<string, Queue<T>>();

        public Dictionary<string, Queue<T>> Queue
        {
            get
            {
                return queue;
            }
        }

        public void Enqueue(T message, string channel = "default")
        {
            Queue<T> channelQueue;
            if (!queue.TryGetValue(channel, out channelQueue))
            {
                queue[channel] = new Queue<T>();
                channelQueue = queue[channel];
            }
            channelQueue.Enqueue(message);
        }

        public T Dequeue(string channel = "default")
        {
            Queue<T> channelQueue;
            if(queue.TryGetValue(channel, out channelQueue))
            {
                if(channelQueue.Count > 0)
                {
                    return channelQueue.Dequeue();
                }
            }

            return default(T);
        }
    }
}

```