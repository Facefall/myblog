---
layout: single
title:  "Algorithm beginner - 1.fibonacci"
categories: fibonacci JavaScript algorithm
---
### Fibonacci

{% highlight ruby linenos %}
const fibonacci = N =>{
    if(N === 1){
        return 1;
    }
    if(N === 0){
        return 0;
    }
    return fibonacci(N-1) + fibonacci(N-2);
}
{% endhighlight %}
