---
layout: single
title:  "linklist - reverse 逆转"
categories: LinkList JavaScript algorithm
---

### LinkList structure

{% highlight ruby linenos %}

export default class LinkList {
    constructor(){
        this.head = null;
        this.tail = null;
    }
}
{% endhighlight %}

### 链表逆转
完成链表逆转总共需要三个指针.

核心思想：

prev -> currentNode -> nextNode

在逆转之前，先将

<code>nextNode = currentNode.next;</code>

确保能拿到链表的下一个节点。

之后将节点指向逆转：

<code>currentNode.next = prev;</code>

于是：
<pre>
node1 <- node2        node3  -> node4 -> node5 -> node6
prev  <- currentNode  nextNode
</pre>


然后三个节点依次向后移动，重复上述过程，

①：current赋值nextNode，

②：current指向改为prev。

<pre>
node1 <- node2 <- node3       node4 -> node5 -> node6
         prev  <- currentNode nextNode
</pre>

直到currentNode.next为空，就不给nextNode赋值了，直接跳出循环。

---

将节点指向逆转之后需要注意
链表自身属性也要调整。

逆转后尾节点：是逆转前的头节点

<code>this.tail = this.head;</code>

逆转后的头节点：当前的currentNode

<code>this.head = currentNode;</code>

完整代码
{% highlight ruby linenos %}
reverse_(){
        let currentNode = this.head;
        let prevNode = null,nextNode = null;
        while(currentNode){
            nextNode = currentNode.next;
            currentNode.next = prevNode;
            prevNode = currentNode;
            currentNode = nextNode;
        }
        this.tail = this.head;
        this.head = preNode;
    }
{% endhighlight %}