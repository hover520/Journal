# Volatile

## [Volatile的官方专业解释][1]

 * Volatile Loads 等价 MonitorEnter
 * Volatile Stores 等价 MonitorExit
 
 
# Volatile Happen-Before
 对一个volatile变量的写操作happen-before对此变量的任意操作(当然也包括写操作了)
 
 * Thread A 写一个volatile变量v，Thread B 读写这个volatile v，则 Thread B 被保证可以看到 <u>**Thread A 写v之前所有的改变**</u>，包括Thread A对no-volatile变量的改变。
 * Thread C 如果没有读写这个volatile v，则Thread C仍有可能看到Thread A操作过的no-volatile变量的过期数据，直到Thread C也对v进行操作。
  
 * ReentrantLock 基于volatile变量state的实现，保证了同一个lock的可见性。
 
# 参考资料 
 * [Volatile read and non-volatile fields][2]
 * [Java volatile variables affecting memory consistency of other non-volatile variables][3]

[1]: http://gee.cs.oswego.edu/dl/jmm/cookbook.html
[2]: https://stackoverflow.com/questions/45602130/volatile-read-and-non-volatile-fields
[3]: https://stackoverflow.com/questions/43712673/java-volatile-variables-affecting-memory-consistency-of-other-non-volatile-varia