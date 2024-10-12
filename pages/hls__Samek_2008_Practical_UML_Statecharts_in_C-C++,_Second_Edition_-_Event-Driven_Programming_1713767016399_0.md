file:: [Samek_2008_Practical_UML_Statecharts_in_C-C++,_Second_Edition_-_Event-Driven_Programming_1713767016399_0.pdf](../assets/Samek_2008_Practical_UML_Statecharts_in_C-C++,_Second_Edition_-_Event-Driven_Programming_1713767016399_0.pdf)
file-path:: ../assets/Samek_2008_Practical_UML_Statecharts_in_C-C++,_Second_Edition_-_Event-Driven_Programming_1713767016399_0.pdf

- 嵌入式软件架构师
  ls-type:: annotation
  hl-page:: 4
  hl-color:: red
  id:: 66304339-cd35-4b10-90ed-cf0b543cfc97
- 软件跟踪工具 QS 本身是一个强大的调试工具，如果读者想了解如何实现一个复杂高效的通讯协议，它也是一个经典的学习范例
  ls-type:: annotation
  hl-page:: 5
  hl-color:: yellow
  id:: 66304391-1e31-45dd-a71f-caa9208b5a0b
- ## **目录**
  hl-page:: 8
  ls-type:: annotation
  id:: 6638a9ff-a44d-4f71-9698-44f225b45fac
  hl-color:: yellow
- [[$red]]==第一部分 UML 状态机==
  ls-type:: annotation
  hl-page:: 8
  hl-color:: red
  id:: 6638ad31-6149-495a-aff7-186363cd939b
  hl-stamp:: 1714990481961
- 第 1 章 UML 状态机和事件驱动型编程技术初探
  ls-type:: annotation
  hl-page:: 8
  hl-color:: yellow
  id:: 6638ad3b-f671-41f5-a57b-19bea8986f8f
- 第 2 章 UML 状态机速成
  hl-page:: 9
  ls-type:: annotation
  id:: 6638ad45-ff37-4d76-9302-f63c07da32f5
  hl-color:: yellow
- 第 3 章  标准状态机的实现方法
  hl-page:: 10
  ls-type:: annotation
  id:: 6638ad5b-4eb2-4d12-b2ca-3a2874863339
  hl-color:: yellow
	- {{embed ((667043e4-2c70-487d-808c-5954b9c91b9b))}}
- 第 4 章 层次式事件处理器的实现
  hl-page:: 10
  ls-type:: annotation
  id:: 6638ad6b-9095-411c-9856-d3aed14d7f92
  hl-color:: yellow
- 第 5 章 状态模式
  hl-page:: 11
  ls-type:: annotation
  id:: 6638ad79-afc7-4622-b751-2743a696e40e
  hl-color:: yellow
- [[$red]]==第二部分 实时框架==
  hl-page:: 12
  ls-type:: annotation
  id:: 6638ad89-5554-42b7-98cb-aadf28504688
  hl-color:: red
- 第 6 章 实时框架的概念
  hl-page:: 12
  ls-type:: annotation
  id:: 6638adb6-c0b9-4a83-9b9e-14da2ae7b87e
  hl-color:: yellow
- 第 7 章 实时框架的实现
  hl-page:: 13
  ls-type:: annotation
  id:: 6638adcb-4c3c-4d51-8d68-b68cbc90c1b7
  hl-color:: yellow
- 第 8 章 ==移植和配置QF==
  hl-page:: 14
  ls-type:: annotation
  id:: 6638ade0-dfc8-4165-9150-c5f0f629266e
  hl-color:: yellow
- 第 9 章 开发 QP 应用程序
  hl-page:: 15
  ls-type:: annotation
  id:: 6638adf6-1269-4f64-b5b0-f0c50a782645
  hl-color:: yellow
- 第 10 章 可抢占式‘运行 - 到 - 完成’内核
  hl-page:: 16
  ls-type:: annotation
  id:: 6638ae08-4355-4c0c-af3b-aca561e9841e
  hl-color:: yellow
- 第 11 章 事件驱动型系统的软件追踪
  hl-page:: 16
  ls-type:: annotation
  id:: 6638ae1e-1759-4781-8da7-dbfe863523d2
  hl-color:: yellow
- 第 12 章 QP-nano ：你能变多小？
  hl-page:: 17
  ls-type:: annotation
  id:: 6638ae31-d5bc-401f-8090-5ba10ddf42db
  hl-color:: yellow
- 第二部分 实时框架
  ls-type:: annotation
  hl-page:: 201
  hl-color:: red
  id:: 6638ae9d-89e8-400e-aec9-fcf72f4c2f51
- 当你开始把多个 UML 状态机结合成系统时，你将很快认识到问题不是如何编码状态机—本书第一部分说明了这实际上不是一个问题
  ls-type:: annotation
  hl-page:: 202
  hl-color:: yellow
  id:: 6638af00-dc08-4bdc-bb23-92a430c63d88
- 后面主要的挑战是生成事件，对事件进行排队，围绕状态机编写全部代码让它们运行，并用一种及时的方式互相通讯而且不会产生并发性危机。
  ls-type:: annotation
  hl-page:: 202
  hl-color:: red
  id:: 6638af07-bafd-424c-9a47-92568ae20d74
- 当一个顺序程序需要一些输入事件时，它原地等待直到事件到达。程序在所有时间都保持控制权，并且因为这个原因，在等待某类事件时，顺序性程序不能（最起码立刻）响应其他事件。
  ls-type:: annotation
  hl-page:: 202
  hl-color:: yellow
  id:: 6638af4f-1501-401b-961a-fa6fd8435723
- 一个事件驱动型应用程序在等待一个事件时没有控制权，事实上，它甚至没有活动。仅当这个事件到达了，这个事件驱动型应用程序被调用去处理这个事件，然后它很快的又放弃控制权。
  ls-type:: annotation
  hl-page:: 202
  hl-color:: yellow
  id:: 6638af6c-6ec7-4de4-9379-8234165692d0
- 事件驱动型方案对 CPU 的使用更加有效率，并趋向消耗更少的堆栈空间，这些对嵌入式系统来说都是非常需要的特性。
  ls-type:: annotation
  hl-page:: 208
  hl-color:: yellow
  id:: 6638b0e9-3829-48c2-a230-ae84c818017b
- 术语“活动对象 (active object)” 从 UML 而来，意思是“一个对象，它有自己的控制的线程”
  ls-type:: annotation
  hl-page:: 209
  hl-color:: red
  id:: 6638b104-8920-4754-a57c-6050aafcf682
- 这个模型的本质概念是在一个多任务环境里使用多个事件驱动型系统。
  ls-type:: annotation
  hl-page:: 209
  hl-color:: blue
  id:: 6638b110-660d-41e4-8561-92a5000b319f
- [:span]
  ls-type:: annotation
  hl-page:: 218
  hl-color:: blue
  id:: 6638b1d6-34ca-4402-af3b-88f941124920
  hl-type:: area
  hl-stamp:: 1714991573232
- QF 可以管理多达 ==63个==并发执行的活动对象，它们封装了任务（每个都嵌入了一个状态机和一个事件队列），任务之间通过发送和接收事件进行异步通讯
  hl-page:: 235
  ls-type:: annotation
  id:: 6638ba08-973d-43e2-a7e7-511f2bcf2b7f
  hl-color:: red
- QF 实时框架支持使用 FIFO和 LIFO 策略对特点活动对象进行直接事件发送。
  ls-type:: annotation
  hl-page:: 237
  hl-color:: yellow
  id:: 6638bbea-e7c7-42ff-b744-4f82415b21e1
- 高效“零复制”事件内存管理
  ls-type:: annotation
  hl-page:: 237
  hl-color:: yellow
  id:: 6638bbff-00ca-49dd-b3b6-c9bf3b1cf27b
- QF 提供了核心基本类 QActive ，用于活动对象类的派生。 QActive 类是抽象的，意味着它不是打算用于被直接实例化，而是为了派生具体43 的活动对象类，比如图 7.3 内的 Ship ， Missile 和 Tunnel 。
  ls-type:: annotation
  hl-page:: 238
  hl-color:: yellow
  id:: 6638bc4e-873d-494f-99d0-1e931e54f6d4
- [:span]
  ls-type:: annotation
  hl-page:: 239
  hl-color:: blue
  id:: 6638bd3f-ed91-4109-9480-38cca4dcb9ed
  hl-type:: area
  hl-stamp:: 1714994494008
- 作为一个规则，软件系统只有当它们在实际应用中被使用过并经过了多次失败以后，才会正常工作。
  ls-type:: annotation
  hl-page:: 290
  hl-color:: yellow
  id:: 6638c75f-974e-4b80-bd88-0043cfc9dbcc
- 状态机在高级编程语言比如 C 或 C++ 里典型的实现方法包括：
  hl-page:: 90
  ls-type:: annotation
  id:: 667043e4-2c70-487d-808c-5954b9c91b9b
  hl-color:: green
	- 嵌套的 switch 语句
	- 状态表
	- 面向对象的状态设计模式，以及
	- 综合以上方法的其他技术