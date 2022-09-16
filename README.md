# Java 算法题常用工具总结
## 输入输出
### Scanner
```java
import java.util.Scanner;

Scanner in = new Scanner(System.in);
int a = in.nextInt();
double b = in.nextDouble();
/* WARNING:
    nextInt() nextDouble() 读取到数字后会留下换行符或者空格
    接着使用 nextLine() 就会出错
    要么都用 nextInt() 要么都用 nextLine()
    或者 nextInt() + next() 的组合
*/
String c = in.nextLine();
String d = in.next();
```

## 数据结构
### ArrayList
常用指数 *****
- list.add(E e)
- list.addAll(Collection<? extends E> c)
- list.get(int index)
- list.size()
- list.contains(Object o)
- list.remove(int index)
- list.set(int index, E element)
- list.sort(Comparator<? super E> c) 或者 Collections.sort(list, Comparator<? super E> c)

常用指数 **
- list.indexOf(Object o)
- list.isEmpty()
- list.clear()
- list.clone()

### LinkedList
用作单队列
- queue.offer(E e) 
- queue.poll()
- queue.peek()
- queue.size()
- queue.isEmpty()

用作双端队列
- deque.addFirst(E e)
- deque.addLast(E e)
- deque.removeFirst()
- deque.removeLast() // 有时很有用
- deque.peekFirst()
- deque.peekLast()

用作栈
- stack.push(E e)
- stack.pop()
- stack.peek()

### HashMap
常规
- map.put(K key, V value)
- map.get(Object key)
- map.getOrDefault(Object key, V defaultValue) // 当没有时返回 defaultValue
- map.isEmpty()
- map.size()
- map.containsKey(Object key)
- map.containsValue(Object value)

迭代访问
```java
for (Map.Entry<key, value> entry : map.entrySet()) {
    key = entry.getKey();
    value = entry.getValue();
}

//iterating over keys only
for (Integer key : map.keySet()) {
	key;
}
 
//iterating over values only
for (Integer value : map.values()) {
	value;
}

// 非常低效，不建议使用
Map<Integer, Integer> map = new HashMap<Integer, Integer>();
for (Integer key : map.keySet()) {
	Integer value = map.get(key);
	System.out.println("Key = " + key + ", Value = " + value);
}
```
