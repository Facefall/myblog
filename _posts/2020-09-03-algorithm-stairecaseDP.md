---
layout: single
title:  "Algorithm beginner - 3.DP 楼梯问题"
categories: DP stairecase JavaScript algorithm
---
### DP 楼梯问题

每次可以上1个台阶，或者2个台阶

给一个N，问到达N阶台阶有几种方法。

{% highlight ruby linenos %}
const StaireCaseDP = N =>{
    const method_A = () => return 1;
    const method_B = () => return 2;
    let DP = new Array(N.length+1);
    DP[0] = 0;
    DP[1] = 1;// method_A()
    DP[2] = 2;// method_B or method_A + method_A

    for(let i = 3; i <= N ; i++){
        DP[i] = DP[i-1] + DP[i-2];
    }

    return DP[N];
}
{% endhighlight %}
