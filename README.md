# OS-by-Java
## 计算机操作系统实验课 Java编写

### 实验一 —— 按照优先数进行处理器调度
  * 一共分了3个包，code包是主要代码，main包是主函数，test包用于测试.
  * code包下Process类属性即进程的基本属性，如name,runninTime,priorty.
  * CPU类是此项目的重点类，它有一个链表用于存放所有的进程，addProcess用于添加进程，但要根据优先度进行排序，接着就是调度schedule方法，基本操作就是将就绪队列最前面的进程运行时间和优先度分别递减，如果运行结束就抽出队列.
  * Mian包下主函数主要通过获得键盘输入作为进程的参数创建所需进程，接着while循环进行调度，直到队列为空位置。中间使用线程进行时间等待，以不至于一开始就打印出所有结果
  * Utiles类是一个静态工具类，其中有获取键盘参数创建进程的方法.
******************************************************
### 实验二 —— 首次适应算法分区管理
  * 本实验一共分为3个包，分别是code,main,test
  * code包
      * Memory类 重要属性有**分区块列表**，用于保存分区块；方法有**排序方法**，把分区块列表按照首地址排序
      * MemoryBlock类 重要属性有**start,end,length,task,isUsed**,其中**task**属性用于保存此分区块属于那个任务，**isUsed**标记是否是空分区块
    重要方法是实现Comparable接口的方法，按照**start**属性排序
      * MemoryOperator类 无重要属性，重要方法有**添加任务申请分区，撤销任务擦除分区，合并邻近分区**，其中**撤销任务擦除分区**会涉及**调用合并邻近分区**。另外方法是**打印内存的分区情况**
      * Task类 重要属性只有**分区大小**
   * main包 只有主类和主函数，通过键盘获取**整数输入**，使用**while死循环，swich**实现题目要求逻辑
   * test包 用Junit来测试编写中的类


