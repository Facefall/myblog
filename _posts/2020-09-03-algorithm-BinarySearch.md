---
layout: single
title:  "Algorithm beginner - 2.BinarySearch"
categories: binary JavaScript algorithm search
---
### BinarySearch

{% highlight ruby linenos %}
const binarySearch = (SortedArray,target) =>{
   let startIndex = 0,endIndex = SortedArray.length-1;
   let midIndex = 0;
   while(startIndex <= endIndex){
       midIndex = startIndex + (Math.floor( (endIndex - startIndex)/2 ));
       if(SortedArray[midIndex] === target){
           return midIndex;
       }
       if(SortedArray[midIndex] < target){
           startIndex = midIndex + 1;
       }
       if(SortedArray[midIndex] > target){
           endIndex = midIndex - 1;
       }
   }

   return -1;
}
{% endhighlight %}
