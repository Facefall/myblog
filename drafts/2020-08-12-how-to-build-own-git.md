---
layout: single
title:  "How to Build Own GIT?"
date:   2020-08-12
categories: git JavaScript
---

#### Try to Better Understand GIT

*from [article][article-url]*

### Repository

{% highlight linenos %}
function Git(name){
    this.name = name;//Repo name
}
{% endhighlight %}

{% highlight javaScript linenos %}
var repo = new Git("我的仓库");
// 实际上的指令:
// > git init
{% endhighlight %}


{% highlight javaScript linenos %}
function Commit(id, message) {
  this.id = id;
  this.message = message;
}

Git.prototype.Commit = function(message){
    var commit = new Commit();
    return commit;
}
{% endhighlight %}




[article-url]:https://kushagra.dev/blog/build-git-learn-git