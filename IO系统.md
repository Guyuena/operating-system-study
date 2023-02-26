







![image-20230223201700762](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223201700762.png)

# 输入输出系统   IO

![image-20230223202603351](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223202603351.png)

![image-20230223202709075](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223202709075.png)

![image-20230223203140075](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223203140075.png)



![image-20230223210717703](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223210717703.png)

![image-20230223211327657](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223211327657.png)

![image-20230223211953144](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223211953144.png)









IO指令
IO指令是机器指令的一类，其指令格式可以与其他指令类似，但是也应该反映CPU与IO系统交换信息的特点

![在这里插入图片描述](https://img-blog.csdnimg.cn/20191215101438484.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjE2NzkxMQ==,size_16,color_FFFFFF,t_70)

- 通道指令
  通道指令是对具有通道的IO系统专门设置的指令，由通道控制字 Channel Control Word组成。







## I/O通道控制方式

通道控制方式是一种以内存为中心，**实现设备和内存间直接交换数据的控制方式**。 也是传输速率比较高的IO控制方式。

通道是一个独立于 CPU的专管输入/输出控制的处理机，它控制设备与[内存](https://so.csdn.net/so/search?q=内存&spm=1001.2101.3001.7020)直接进行数据交换。它有自己的通道指令，这些通道指令受CPU启动，并在操作结束时向CPU发中断信号。



**引入IO通道的目的是减少IO操作对CPU的占用，使得CPU更专注做非IO工作，因为IO操作比较耗时**

![image-20230223212111161](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223212111161.png)



![img](https://img-blog.csdnimg.cn/20210809230010736.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzMxNjA4NjQx,size_16,color_FFFFFF,t_70)

I/O通道(I/O Channel)设备的引入实际上，**I/O通道是一种特殊的处理机**。它具有执行I/O指令的能力，并通过执行通道(I/O)程序来控制I/O操作







**通道的运算控制部件**

- 通道地址字（CAW）：记录下一条通道指令的地址，其功能类似于中央处理机的指令计数器。
- 通道命令字（CCW）：记录正在执行的通道指令，其作用相当于中央处理机的指令寄存器。
- 通道状态字（CSW）：记录通道、控制器、设备的状态，包括I/O传输完成信息、出错信息、重复执行次数等。当IO操作完成后，CPU通过读取通道状态字的值来了解IO操作的执行情况。

**通道程序：保存在主存中**

通道通过执行一个通道程序来完成IO控制的。通道虽然是一种处理机，但是它本身没有内存，是与主机CPU共享系统的主存。所以通道程序是存放在主存中的。一个通道程序由一系列通道指令构成。 通道指令内容如下：

- 操作码：规定指令所执行的操作。
- 内存地址：内存缓冲区首址。
- 计数：本条指令要读写的字节数。
- 通道程序结束位P：P=1表示本条指令是通道程序最后一条指令。
- 记录结束标志R：R=0表示本条指令与下一条指令所处理的数据属同一条记录。

![img](https://pic4.zhimg.com/v2-b6eedbf539bc38165b3a054821c360f3_r.jpg)

































# 总线

![image-20230223203316766](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223203316766.png)

![image-20230223203330441](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223203330441.png)



![image-20230223203343016](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223203343016.png)

![image-20230223203423542](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223203423542.png)



![image-20230223203435507](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223203435507.png)

![image-20230223203520510](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223203520510.png)

![image-20230223203613204](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223203613204.png)

![image-20230223203646691](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223203646691.png)

![image-20230223203654722](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223203654722.png)



![image-20230223203812340](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223203812340.png)

![image-20230223203900954](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223203900954.png)

![image-20230223204001356](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223204001356.png)

![image-20230223204019292](C:\Users\jc\AppData\Roaming\Typora\typora-user-images\image-20230223204019292.png)



PCI（外设组件互连标准）         PCI   ： Peripheral Component Interconnect



PCI-Express(peripheral component interconnect express)是一种高速串行计算机扩展总线标准