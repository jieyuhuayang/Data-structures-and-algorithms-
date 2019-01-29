## 1. what is queue
queue（队列）是一种FIFO的线性表
  
## 2. STL之deque介绍  
deque连续存储结构,即其元素在内存上也是连续的。  
我们知道连续内存的容器不能随意扩充,因为很容易会越界。但是deque却可以,它创造了内存连续的假象：  
其实deque由一段一段构成 ,它是分段连续,而不是内存连续 当走向段的尾端时候自动跳到下一段。  
  
deque除具有vector的所有功能外，**还具有高效的首/尾端的插入/删除操作**。  
缺点：占用内存较多  
```c++
//默认构造函数 创建一个空的deque
    deque<int> c;
    
    //拷贝构造
    deque<int> c1(c);
    
    //赋值拷贝
    deque<int> c2 = c1;
    
    //指定元素个数创建
    deque<int> c3 (5,6);
    for (auto i : c3) {
        cout<< i << ",";
    }
    cout << "deque(个数, 元素)"<<endl;
    
    //指定区间创建
    deque<int> c4(c3.begin()+2, c3.begin()+3);
    for (auto i : c4) {
        cout<< i << ",";
    }
    cout << "deque(区间, 区间)"<<endl;
    
    //指定初始化列表创建
    deque<int> c5({2,3,4,5});
    for (auto i : c5) {
        cout<< i << ",";
    }
    cout << "deque({})"<<endl;
    
    //指定初始化列表创建
    deque<int> c6 = {2,3,4,5};
    for (auto i : c6) {
        cout<< i << ",";
    }
    cout << "deque = {}" <<endl;
```

## 3.Heapsort（堆排序）  
### 3.1 heap 堆   
回顾一下堆的概念，堆是一棵顺序存储的近似完全二叉树结构，并同时满足堆积的性质：即子结点的键值或索引总是小于（或者大于）它的父节点。  
### 3.2 heap的性质：  
设当前元素在数组中以R[i]表示：
-  Ri <= R2i+1 且 Ri <= R2i+2  
- 它的左孩子结点是：R[2*i+1];   
- 它的右孩子结点是：R[2*i+2];  
- 它的父结点是：R[(i-1)/2];  
### 3.3 堆排序  
由上面的介绍我们可以看出堆的第一个元素要么是最大值（大顶堆），要么是最小值（小顶堆），这样在排序的时候（假设共n个节点），直接将第一个元素和最后一个元素进行交换，然后从第一个元素开始进行向下调整至第n-1个元素。所以，如果需要升序，就建一个大堆，需要降序，就建一个小堆。 
堆排序的步骤分为三步:   
1、建堆（升序建大堆，降序建小堆）；   
2、交换数据；   
3、向下调整。   

## 4. 239. Sliding Window Maximum（239 滑动窗口最大值问题）