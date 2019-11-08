# Container

## at 与 [] 的区别

1. 在某些容器中 [] 可以用于添加元素，at则不行，比如：map
2. at会检查下标的有效性，无效会抛出std::out_of_range异常，[] 则不会检查。*例外，在 array 中，两种操作都不会进行下标有效性检查*。

## 数组

int *pbeg = begin(ia);

int *pend = end(ia);  // p106

## 1. Vector

[C++ vector的内部实现原理及基本用法](https://blog.csdn.net/lmhlmh_/article/details/80545046)

**如果你的元素是结构或是类,那么移动的同时还会进行构造和析构操作，所以性能不高 （最好将结构或类的指针放入vector中，而不是结构或类本身，这样可以避免移动时的构造与析构)。**

**增长速度**

Vector每次增长都要重新分配全部内存，而不是在原有内存尾部申请需要增加的内存。

STL使用的增长速度是1.5，理论上讲最优的增长速度是1.618（黄金分割比）。

如果使用增长速度为2，那么每一次的分配都会大于前几次分配之和，导致无法重复利用之前的内存，使用1.5可以重复利用之前的内存，~~防止了内存的浪费~~（还要具体看一下，每一都是重新分配，为什么会防止浪费？）。

> [C++ STL中vector内存用尽后，为啥每次是两倍的增长，而不是3倍或其他数值？](https://www.zhihu.com/question/36538542)
> [C++ Made Easier: How Vectors Grow](http://www.drdobbs.com/c-made-easier-how-vectors-grow/184401375)
> [What is the ideal growth rate for a dynamically allocated array?](https://stackoverflow.com/questions/1100311/what-is-the-ideal-growth-rate-for-a-dynamically-allocated-array)

### 删除容器中指定内容的元素

```
for (auto it = v.begin(); it != v.end();) {
	if (*it == /* */) {
		it = v.erase(it);
	} else {
		it++;
	}
}
```

### .front() 与 .back()

.front(): 返回第一个元素

.back(): 返回最后一个元素



## 2. Stack 栈

* ***top()才能查看元素，pop()不行***
* s.empty(); //如果栈为空则返回true, 否则返回false
* s.size(); //返回栈中元素的个数
* s.top(); //返回栈顶元素, 但不删除该元素
* s.pop(); //弹出栈顶元素, 但不返回其值
* s.push(); //将元素压入栈顶
* [151. 翻转字符串里的单词](https://leetcode-cn.com/problems/reverse-words-in-a-string/)



## 3. Map

通过**红黑树**存储查找

**遍历**

```
for(auto iter=maps.begin(); iter!=maps.end(); iter++)
{
	int i = iter->first;
	string s = iter->second;
}
// 也可以通过下标遍历 string s = maps[i];
```



## 4. Hash_Map

通过hash表存储

需要实现hash函数、比较函数（等与函数）



## 5. Set





## 6. deque队列

[950. 按递增顺序显示卡牌](https://leetcode-cn.com/problems/reveal-cards-in-increasing-order/)
