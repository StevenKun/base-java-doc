Lambda  (浪木妲)

why use? 减少代码冗余,解放程序员

when use? 只要是函数式接口,都可以直接使用   @FunctionalInterface注释的接口

这位浪木妲姐姐还有很多其他糖果哦! 内置的java.utils.function包里有很多内置的接口,可以直接拿来使用

常用的如:

| function          | 作用                               |      |
| ----------------- | ---------------------------------- | ---- |
| Predicate<T>      | 接收参数T,返回一个boolean值        |      |
| Consumer<T>       | 接收参数T,无返回值                 |      |
| Function<T, R>    | 接收参数T,返回一个R结果对象        |      |
| Suplier<T>        | 不接收参数,返回一个T对象的创建对象 |      |
| UnaryOperator<T>  | 接收参数对象T,返回结果对象T        |      |
| BinaryOperator<T> | 接收两个T对象,返回一个T对象        |      |

![1584607300361](C:\Users\smc7050u01\AppData\Roaming\Typora\typora-user-images\1584607300361.png)







Stream 

1. 聚合操作

2. stream 的处理流程

   数据源

   数据转换

   获取结果

3. 获取Steam对象

   

   1. 从集合或者数组中获取

      ```java
      collection.stream()
      collection.paralleStream()
      arrays.stream(T t)
      ```

   2. BufferReader

      ```java
      BufferReader.lines -> stream	
      ```

   3. 静态工厂

      ```java
      Java.util.stream.IntStream.range()...
      java.nio.file.files.wark()...
      ```

   4. 自定构建

      ```
      java.util.Spliterator
      ```

      

   5. 更多的方式

      ```
      Random.ins()
      pottern.splitAsStream()...
      ```

4. 中间操作api{intermediate}

   操作结果是一个Stream,中间操作可以有一个或者多个连续的中间操作,需要注意的是,中间操作只记录操作方式,不做具体执行,直到结束操作发生时,才做数据的最终执行.

   中间操作:就是业务逻辑处理

   中间操作过程:

   - 无状态,数据处理时,不收前置中间操作的影响

     ```java
     map/filter/peek/parallel/sequential/unordered
     ```

     

   - 有状态:数据处理时,受到前置中间操作的影响

     ```java
     distinct/sorted/limit/skip
     ```

   ​	

5. 终结操作|结束操作(Terminal)

   需要注意:一个Stream对象,只能有一个Terminal操作,这个操作一旦发生,就会真实处理数据,生成对应的

   终结操作:

   - 非短路操作:当前的Stream队形必须处理完集合中所有数据,才能得到结果

   ​		foreach,forEachOrdered/toArray/reduce/collection/min/max/count/iterator

   - 短路操作:当前的stream对象在处理过程中,一旦满足某个条件,就能得到结果

   ​		anyMatch/allMatch/noneMatch/findFirst/findAny等

   ​		short-circuiting,无限大的Stream->有限大的Stream

   ​	