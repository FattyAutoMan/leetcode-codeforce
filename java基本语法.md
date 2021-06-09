## java中值比较用equal，地址==

队列相关的数据结构有offer和poll

## 基本数据和封装类

char--Character

int--Integer



## Integer

valof()装箱 intval()卸

```java
  Integer integer = 10;
  int a=Integer.parseInt("123");
  System.out.println("" + integer.intValue());
   List<Integer> ans = new ArrayList<>();
   ans.add(3);
     ans.sort((t1, t2) -> {
      return t1 - t2;
   });
```

## 数组长度

除了基本数组，长度为length，其它都是size（）

```java
int[] nums={};
int len=nums.length;
```

数组排序，只能默认升序

```java
java.util.Arrays 
int[] a={1,4,-1,5,0};
Arrays.sort(a);
```

自定义排序

int数组转string数组

## ArrayList

```java
List<Integer> list=new ArrayList<>();
```

## 栈

```java
Stack<Integer> stack=new Stack<Integer> ();
stack.peek();
stack.pop();
stack.push();
stack.size();
```

## 堆(collection)

没有pop()和push()

```java
Queue<Integer> queue = new LinkedList<Integer>();
queue.offer(i)/ queue.poll();
queue.add()/queue.remove()
queue.contains();
queue.contains();
queue.peek(); queue.element();
queue.size();
```

## 双边队列(collection)

```java
deque.offer(1);deque.offerFirst();deque.offerLast()
deque.poll();deque.pollFirst();deque.pollLast();
deque.add();deque.addFirst();deque.addLast();
deque.isEmpty();
deque.size();
deque.addAll(queue);
```

## 优先队列priorityqueue

没有first和last

```java
PriorityQueue<Integer> priorityqueue = new PriorityQueue<>((t1, t2) -> {
      return t2 - t1;
});//最大优先队列
priorityqueue.size();
priorityqueue.isEmpty();
priorityqueue.add(1);
priorityqueue.remove(1);
priorityqueue.offer(1);
priorityqueue.poll();   // 无参数，弹出头顶
priorityqueue.peek();priorityqueue.element();
priority.toArray();//转成数组 object[]
priority.iterator()//迭代器
```

## 双向链表

```java
LinkedList<Integer> list = new LinkedList<>();
list.add(1);list.remove();//First,last
list.offer();list.poll();//First,last
list.get();//First,Last
list.peek();//First,last
list.element(); 
list.size();
list.contains();
list.isEmpty();
Iterator<Integer> it9 = list.descendingIterator();
while (it9.hasNext()) {
       System.out.println(it9.next());
 }
```

## pair

```
Pair<Integer, Integer> pair = new Pair<Integer,Integer>(1, 1);
pair.getKey();
pair.getValue();
```

## String

StringBuffer是线性安全的；stringbuider是线性不安全的；String对象在方法区中的常量池，不能更改内容，只能变更指向

```java
StringBuilder string = new StringBuilder("abc");
string.charAt(1);
string.insert(2, ch);//基本数据类型以及char[]
string.append("123456789");//同上
string.delete(2, 3);
string.indexof("s");//返回字符串所在位置；不存在返回-1
```

int和String直接转换

```java
Integer t = Integer.parseInt(str);
Integer.toString(2);
```

char[]和string之间转换

```java
char[] ch = new char[10];
string.getChars(0, string.length() , ch, 0);
string.delete(0, string.length()).append(ch);
```

## set

没有poll和offer；add/remove;按顺序排；求交并补

Set和hashSet没办法得到first和last；但是TreeSet有first()和last(); pollFirst(); pollLast();

treeset还能用来搜索[a,b]内数是否存在，先找到第一个**大于等于**a的数（ceil=set.ceeling(a)）

```java
Set<Integer> set = new TreeSet<>();
Set<Integer> set1 = new TreeSet<>();
set.contains(1);
set.size();
set.isEmpty();
set.remove(9);//不会抛出异常
set.add(1);
set1.add(1);
set.add(8);
set.add(3);
set1.add(3);
set.add(5);
set.add(2);
set.add(3);
set1.add(10);
set.removeAll(set1);//set移除交集部分
set.retainAll(set1); //set保留set和set2交集
//set容器按升序遍历
//移除set最后一个元素，只能用treeSet
pollLast();
pollFirst();
```

```java
TreeSet<Integer> set=new TreeSet<>();
set.ceiling(Integer e); //第一个>=e
set.floor(Integer e); //第一个 <=e
set.higher(Integer e);//第一个>e的数
set.lower(Integer e);//第一个<e
```



## Map(collection)

```java
Map<Integer, Integer> map2 = new LinkedHashMap<>();
map2.put(1, 1);
map2.put(2, 2);
map2.put(8, 2);
map2.put(3, 2);
map2.put(5, 2);
map2.put(1, 3);  map2.remove(map2.entrySet().iterator().next().getKey());
Iterator<Integer> it = map2.keySet().iterator();

map.containsKey('C');
map.remove(key);
Collection<Integer> collection = map.values();
for (Integer i : collection)
System.out.println(i);
```

## 排序算法(9种)

|          算法          | 最好时间                        | 最差时间     | 平均时间 | 最差空间                                                    |
| :--------------------: | ------------------------------- | ------------ | -------- | ----------------------------------------------------------- |
|        归并排序        | nlogn                           | nlogn        | nlogn    | nlogn(需要开辟n空间进行有序数组合并)，面试会问**O（logn）** |
|        快速排序        | nlgn                            | n2(树一边倒) | nlgn     | 完全二叉logn，一边倒n                                       |
|         堆排序         | 建堆nlogn，弹出logn，完全二叉树 | nlogn        | nlogn    | logn（递归压栈空间）                                        |
|        冒泡排序        | n2 但**n（改进后的算法）**      | n2           | n2       | 1                                                           |
|        插入排序        | n                               | n2           | n2       | 1                                                           |
|        选择排序        | n2                              | n2           | n2       | 1                                                           |
|         桶排序         | n+k                             | n+k          | n2       | 1                                                           |
| 希尔排序（shell sort） | n                               | (logn)2      | (logn)2  | 1                                                           |
| 基数排序（radix sort)  | nk                              | nk           | nk       | n+k                                                         |

### 归并算法空间的改进

![](C:\Users\llh\AppData\Roaming\Typora\typora-user-images\image-20210528150212245.png

![img](https://pic2.zhimg.com/80/v2-d6f818db4ff639c151242bc97ca30115_720w.jpg)

递归O（logn）不开辟新空间将其排好，让一个位置保留两个信息，余数（当前指向值）和商（结果）就能实现O（1）空间复杂度

### 冒泡排序改进后最好时间复杂度O(n)

在原有基础上增加标志位didswap

```java
public void bubbleSort(int arr[]) {
    boolean didSwap;
    for(int i = 0, len = arr.length; i < len - 1; i++) {
        didSwap = false;
        for(int j = 0; j < len - i - 1; j++) {
            if(arr[j + 1] < arr[j]) {
                swap(arr, j, j + 1);
                didSwap = true;
            }
        }
        if(didSwap == false)
            return;
    }    
```

### 插入排序

当前nums[i]和nums[i-1]比较交换位置。直到不交换说明当前数找到自己的位置

### 选择排序

依次找出第1大，第2大，第3大。。。

所以任何条件都是O(n2)

### 基数排序

### 桶排序

### 希尔排序

### 编码

https://www.cnblogs.com/liujinhong/p/5995946.html

assci就128个字符，一个字节就能解决

unicode不包括辅助平面就16位，包括就24位，1-3字节不等；是字符集，不是编码方式

**为什么不同一使用3字节表示一个字符？浪费资源**

所以unicode字符在1-3字节不定

**计算机如何知道该读多少个字节？需要使用相应编码方式utf8，gbk**

**utf8是实现正确解读unicode的一种方法**

具体如下：

三个模板：0xxxxxxx ║110xxxxx 10xxxxxx║1110xxxx 10xxxxxx 10xxx10x║11110xxx 10xxxxxx 10xxxxxx 10xxxxxx

单字节开头一定是0，128个asci用7位足够表示了

通过读取开头就知道模板类别，从而正确解读unicode

**iso8859-1编码**

  属于**单字节编码**，最多能表示的字符范围是0-255，应用于英文系列。比如，字母a的编码为0×61=97.很明显，iso8859-1编码表示的字符范围很窄，无法表示中文字符。但是，由于是单字节编码，和计算机最基础的表示单位一致，所以很多时候，仍旧使用iso8859-1编码来表示。而且在很多协议上，默认使用该编码。

**GBK**

统一2个字节编码（16位）

**java对字符的处理**

1. **getBytes（charset）**

  这是java字符串处理的一个标准函数，其作用是将字符串所表示的字符按照**charset编码**（编码方式），并以**字节**方式表示。注意字符串在java内存中总是按**unicode**编码存储的。比如"中文"，正常情况下（即没有错误的时候）存储为"4e2d 6587"，如果charset为"gbk"，则被编码为"d6d0 cec4"，然后返回字节"d6 d0 ce c4".如果charset为"utf8"则最后是"e4 b8 ad e6 96 87".如果是"iso8859-1"，则由于无法编码，最后返回 "3f 3f"（两个问号）。

java文件在内存存储的是unicode，打开文件到程序员看到是通过编辑平台charset解读的。

**.class类的编码为：unicode;**

*windows 默认的编码为：中文：gb2312; 英文：iso8859;*

String str = "张三" ;//unicode

byte[] jiema= str.**getBytes**("gb2312") ; //gb解码

String  bianma = new String(jiema,"UTF-8");//编码 如果上面的解码不对 可能出现问题，这回存储的是UTF8的码

？？？**String.charAt(i)适合实现正确解码unicode？**

String str = "张三hi" ;//unicode 2 2 1 1 

length信息但有可能 2 1 1 2啊，如何正确读到“三”？

## 简便函数

### 累加，字符判断

```java
accumulate(stk.begin(), stk.end(), 0);
Character.isDigit(s.charAt(i));
```

### Arrays.sort()对Integer[]实现逆排序

```java
        // 倒序排列
         Integer[] array2 = {2, 5, -2, 6, -3, 8, 0, -7, -9, 4};
         Arrays.sort(array2, new Comparator() {
            @Override
            public int compare(Object o1, Object o2) {
                 Integer e1 = (Integer)o1;
                 Integer e2 = (Integer)o2;
                return e1 > e2?-1:1;
            }             
        });
```

### 对于int[]的数据进行逆排序

使用数组的流运算

```java
nums = Arrays.stream(nums).boxed().sorted((a, b) -> b - a).mapToInt(p -> p).toArray();
```

### List<Integer>,  int[]，Integer[]之间的转换

总结转涉及到,int[] 中间需要intstream或者stream<Integer>

Arrays.stream(int[])返回IntStream,放入Intger[]返回Stream<Integer>

List-->Integer[]: list.toArray(new Integer[0]);

[]-->List: asList

stream<Integer>转换成List： collect(Collectors.toList())

Intstream-->stream<Integer>:  boxed();

stream<Integer> -->Intstream:  mapToInt(Integer::Valueof)

Intstream-->int[] : toArray(int[]::new)

**int[] --> List<Integer>, 中间Instream做转接**

```java
int[] data = {4, 5, 3, 6, 2, 5, 1};
// int[] 转 List<Integer>
List<Integer> list1 = Arrays.stream(data).boxed().collect(Collectors.toList());
// Arrays.stream(arr) 可以替换成IntStream.of(arr)。
// 1.使用Arrays.stream将int[]转换成IntStream。
// 2.使用IntStream中的boxed()装箱。将IntStream转换成Stream<Integer>。
// 3.使用Stream的collect()，将Stream<T>转换成List<T>，因此正是List<Integer>。
```

**int[]-->Integer[]**

```
Integer[] Integers1=Arrays.stream(data).boxed().toArray(Integer[]::new);
// 前两步同上，此时是Stream<Integer>。
// 然后使用Stream的toArray，传入IntFunction<A[]> generator。
// 这样就可以返回Integer数组。
// 不然默认是Object[]。
```

**List<Integer> -->Integer[]**

```java
Integer[] integer2=list1.toArray(new Integer[0]);
```

**List<Integer> -->int[]**

```
int[] arr1 = list1.stream().mapToInt(Integer::valueOf).toArray();
// 想要转换成int[]类型，就得先转成IntStream。
// 这里就通过mapToInt()把Stream<Integer>调用Integer::valueOf来转成IntStream
// 而IntStream中默认toArray()转成int[]。
```

**Integer[]--> int[]**

```java
int[] arr2 = Arrays.stream(integers1).mapToInt(Integer::valueOf).toArray();
```

**Integer[] --> List<Integer>**

```
  List<Integer> list2 = Arrays.asList(integers1);
```



### queue,stack,PriorityQueue转数组

