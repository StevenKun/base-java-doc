redis 复习手册

C语言

数据结构类型

string key-value类型

method: set   get     
		mset  mget
		expire  设置过期时间  
		ttl     查看过期时间
		exists  查看key是否存在

list  链表类型
env:
method: lpush rpush   向链表中添加元素
		lpop   rpop	  从链表中取出元素
		lrange  @start  @end   查看列表中下标从start到end的列表值
		llen          查看链表长度
		简单队列  rpush/ lpop  右进左出   FIFO   
		简单栈	 rpush/ rpop  右进右出   FILO

hash 数组+链表（hashmap）
env :系统中对象数据的存储
method: hmset  新建一个hashmap 
		hkeys  获取对象所有的key值
		hvals  获取对象所有的value值
		hgetall  展示所有的key-value值
		hset   修改或者新加hashmap中某个key的值
		hget   获取key的value值

example:
		hmset studentkey name 'likun' age '12' sex '0'


set  hashset(无序)
env: 数据不重复，以及需要多个数据源交集和并集等场景

method: sadd  添加元素进去key
		smembers   查看set中的所有元素
		scard 查看set的长度
		sismember 检查某个元素是否在set之中
		sinterstore 

		
sorted set
env: 需要对数据根据某个权重进行排序的场景
method: zadd  添加一个或者多个元素
        zcard myset 查看数量
        zrange   0 -1  查看所有  0 2  查看下标0到2范围内的

eg: zadd sortsetkey 3.0 value



bitmap
env: 适合需要保存状态信息，并对这些信息进行进一步分析的场景
		1.用户在线状态
		2.统计活跃用户
		3.用户行为分析

method: setbit
		getbit
		bitcount  统计key的bit为1的数量
		bitop



文件事件处理模型 
Redis 基于 Reactor 模式开发了自己的网络事件处理器：这个处理器被称为文件事件处理器（file event handler）。文件事件处理器使用 I/O 多路复用（multiplexing）程序来同时监听多个套接字，并根据 套接字目前执行的任务来为套接字关联不同的事件处理器。


redis单线程理由：

1.单线程编程容易并且更容易维护；
2、Redis 的性能瓶颈不再 CPU ，主要在内存和网络；
3.多线程就会存在死锁、线程上下文切换等问题，甚至会影响性能。


redis6.0 引入多线程的理由：	
为了提高网络I/O读写能力 ，只有网络读写操作上使用了多线程，不需担心线程安全问题



redis 过期时间的作用
1.redis给数据设置过期时间 ，是为了防止内存溢出 ；
2.可以满足部分场景需求，如验证码等；


redis 过期数据删除策略
1.惰性删除
	只有取出数据才对数据进行过期检查，对cpu友好，对内存不友好
2.定期删除
	每隔一段时间抽取一批key执行删除  对内存友好

Redis 内存淘汰机制
volatile-lru（least recently used）：从已设置过期时间的数据集（server.db[i].expires）中挑选最近最少使用的数据淘汰
volatile-ttl：从已设置过期时间的数据集（server.db[i].expires）中挑选将要过期的数据淘汰
volatile-random：从已设置过期时间的数据集（server.db[i].expires）中任意选择数据淘汰
allkeys-lru（least recently used）：当内存不足以容纳新写入数据时，在键空间中，移除最近最少使用的 key（这个是最常用的）
allkeys-random：从数据集（server.db[i].dict）中任意选择数据淘汰
no-eviction：禁止驱逐数据，也就是说当内存不足以容纳新写入数据时，新写入操作会报错。这个应该没人使用吧！

4.0 版本后增加以下两种：

1.volatile-lfu（least frequently used）：从已设置过期时间的数据集(server.db[i].expires)中挑选最不经常使用的数据淘汰
2.allkeys-lfu（least frequently used）：当内存不足以容纳新写入数据时，在键空间中，移除最不经常使用的 key




















