# CPU,GPU,TPU,NPU等异同来源解析



## 什么是CPU?

​		中央处理器(CPU，Central Processing Unit)，是电子计算机的主要设备之一，电脑中的核心配件。其功能主要是解释计算机指令以及处理计算机软件中的数据。电脑中所有操作都由CPU负责读取指令，对指令译码并执行指令的核心部件。

​		CPU的结构主要包括运算器(ALU, Arithmetic and Logic Unit)、控制单元(CU, Control Unit)、寄存器(Register)、高速缓存器(Cache)和它们之间通讯的数据、控制及状态的总线。

​		CPU遵循的是冯诺依曼架构，其核心就是:存储程序，顺序执行。

​		另外，因为遵循冯诺依曼架构(存储程序，顺序执行)，CPU就像是个一板一眼的管家，人们吩咐的事情它总是一步一步来做。但是随着人们对更大规模与更快处理速度的需求的增加，这位管家渐渐变得有些力不从心。

​		于是，大家就想，**能不能把多个处理器放在同一块芯片上，让它们一起来做事，这样效率不就提高了吗?**

​		没错，GPU便由此诞生了。

## 什么是GPU?

​		在正式讲解GPU之前，我们先来讲讲上文中提到的一个概念：并行计算。

​		并行计算(Parallel Computing)是指同时使用多种计算资源解决计算问题的过程，是提高计算机系统计算速度和处理能力的一种有效手段。它的基本思想是用多个处理器来共同求解同一问题，即将被求解的问题分解成若干个部分，各部分均由一个独立的处理机来并行计算。

​		并行计算可分为时间上的并行和空间上的并行。

​		时间上的并行是指流水线技术，比如说工厂生产食品的时候分为四步:清洗-消毒-切割-包装。

​		如果不采用流水线，一个食品完成上述四个步骤后，下一个食品才进行处理，耗时且影响效率。但是采用流水线技术，就可以同时处理四个食品。这就是并行算法中的时间并行，在同一时间启动两个或两个以上的操作，大大提高计算性能。

​		空间上的并行是指多个处理机并发的执行计算，即通过网络将两个以上的处理机连接起来，达到同时计算同一个任务的不同部分，或者单个处理机无法解决的大型问题。

​		比如小李准备在植树节种三棵树，如果小李1个人需要6个小时才能完成任务，植树节当天他叫来了好朋友小红、小王，三个人同时开始挖坑植树，2个小时后每个人都完成了一颗植树任务，这就是并行算法中的空间并行，将一个大任务分割成多个相同的子任务，来加快问题解决速度。

​		所以说，如果让CPU来执行这个种树任务的话，它就会一棵一棵的种，花上6个小时的时间，但是让GPU来种树，就相当于好几个人同时在种。

​		GPU全称为Graphics Processing Unit，中文为图形处理器，就如它的名字一样，GPU最初是用在个人电脑、工作站、游戏机和一些移动设备(如平板电脑、智能手机等)上运行绘图运算工作的微处理器。

​		为什么GPU特别擅长处理图像数据呢?这是因为图像上的每一个像素点都有被处理的需要，而且每个像素点处理的过程和方式都十分相似，也就成了GPU的天然温床。

​		**但GPU无法单独工作，必须由CPU进行控制调用才能工作**。CPU可单独作用，处理复杂的逻辑运算和不同的数据类型，但当需要大量的处理类型统一的数据时，则可调用GPU进行并行计算。

​		GPU的工作大部分都计算量大，但没什么技术含量，而且要重复很多很多次。

​		借用知乎上某大神的说法，就像你有个工作需要计算几亿次一百以内加减乘除一样，最好的办法就是雇上几十个小学生一起算，一人算一部分，反正这些计算也没什么技术含量，纯粹体力活而已;而CPU就像老教授，积分微分都会算，就是工资高，一个老教授资顶二十个小学生，你要是富士康你雇哪个?

​		但有一点需要强调，虽然GPU是为了图像处理而生的，但是我们通过前面的介绍可以发现，它在结构上并没有专门为图像服务的部件，只是对CPU的结构进行了优化与调整，所以现在GPU不仅可以在图像处理领域大显身手，它还被用来科学计算、密码破解、数值分析，海量数据处理(排序，Map-Reduce等)，金融分析等需要大规模并行计算的领域。

## 什么是TPU?

​		张量处理单元(TPU)是一种**定制化的 ASIC 芯片**，它由谷歌从头设计，并专门用于机器学习工作负载。TPU 为谷歌的主要产品提供了计算支持，包括翻译、照片、搜索助理和 Gmail 等。Cloud TPU 将 TPU 作为可扩展的云计算资源，并为所有在 Google Cloud 上运行尖端 ML 模型的开发者与数据科学家提供计算资源。

​		按照上文所述，CPU和GPU都是较为通用的芯片，但是有句老话说得好:**万能工具的效率永远比不上专用工具**。

​		随着人们的计算需求越来越专业化，人们希望有芯片可以更加符合自己的专业需求，这时，便产生了**ASIC(专用集成电路)的概念**。

​		ASIC是指**依产品需求不同而定制化的特殊规格集成电路，由特定使用者要求和特定电子系统的需要而设计、制造**。

​		而TPU(Tensor Processing Unit, 张量处理器)就是谷歌专门为**加速深层神经网络运算能力**而研发的一款芯片，其实也是一款ASIC。

​		据称，TPU与同期的CPU和GPU相比，可以提供15-30倍的性能提升，以及30-80倍的效率(性能/瓦特)提升。初代的TPU只能做推理，要依靠Google云来实时收集数据并产生结果，而训练过程还需要额外的资源;而第二代TPU既可以用于训练神经网络，又可以用于推理。





## 什么是NPU?

​		所谓**NPU(Neural network Processing Unit)， 即神经网络处理器。用电路模拟人类的神经元和突触结构**。

神经网络中存储和处理是一体化的，都是通过突触权重来体现。而冯·诺伊曼结构中，存储和处理是分离的，分别由存储器和运算器来实现，二者之间存在巨大的差异。当用现有的基于冯·诺伊曼结构的经典计算机(如X86处理器和英伟达GPU)来跑神经网络应用时，就不可避免地受到存储和处理分离式结构的制约，因而影响效率。这也就是专门针对人工智能的专业芯片能够对传统芯片有一定先天优势的原因之一。

​		NPU的典型代表有国内的寒武纪芯片和IBM的TrueNorth。以中国的寒武纪为例，DianNaoYu指令直接面对大规模神经元和突触的处理，一条指令即可完成一组神经元的处理，并对神经元和突触数据在芯片上的传输提供了一系列专门的支持。

​		用数字来说话，CPU、GPU与NPU相比，会有百倍以上的性能或能耗比差距–以寒武纪团队过去和Inria联合发表的DianNao论文为例–DianNao为单核处理器，主频为0.98GHz，峰值性能达每秒4520亿次神经网络基本运算，65nm工艺下功耗为0.485W，面积3.02平方毫米mm。



## 什么是BPU?

​		BPU(Brain Processing Unit，大脑处理器)是由地平线科技提出的嵌入式人工智能处理器架构。第一代是高斯架构，第二代是伯努利架构，第三代是贝叶斯架构。目前地平线已经设计出了第一代高斯架构，并与英特尔在2017年CES展会上联合推出了ADAS系统(高级驾驶辅助系统)。



## 什么是DPU?

DPU(Deep learning Processing Unit, 即深度学习处理器)最早由国内深鉴科技提出，基于Xilinx可重构特性的FPGA芯片，设计专用的深度学习处理单元(可基于已有的逻辑单元，设计并行高效的乘法器及逻辑电路，属于IP范畴)，且抽象出定制化的指令集和编译器(而非使用OpenCL)，从而实现快速的开发与产品迭代。事实上，深鉴提出的DPU属于半定制化的FPGA。



## 总结

- APU – Accelerated Processing Unit, 加速处理器，AMD公司推出加速图像处理芯片产品。
- BPU – Brain Processing Unit,地平线公司主导的嵌入式处理器架构。
- CPU – Central Processing Unit 中央处理器， 目前PC core的主流产品。
- DPU – Deep learning Processing Unit, 深度学习处理器，最早由国内深鉴科技提出;另说有Dataflow Processing Unit 数据流处理器， Wave Computing 公司提出的AI架构;Data storage Processing Unit，深圳大普微的智能固态硬盘处理器。
- FPU – Floating Processing Unit 浮点计算单元，通用处理器中的浮点运算模块。
- GPU – Graphics Processing Unit, 图形处理器，采用多线程SIMD架构，为图形处理而生。
- HPU – Holographics Processing Unit 全息图像处理器， 微软出品的全息计算芯片与设备。
- IPU – Intelligence Processing Unit， Deep Mind投资的Graphcore公司出品的AI处理器产品。
- MPU/MCU – Microprocessor/Micro controller Unit， 微处理器/微控制器，一般用于低计算应用的RISC计算机体系架构产品，如ARM-M系列处理器。
- NPU – Neural Network Processing Unit，神经网络处理器，是基于神经网络算法与加速的新型处理器总称，如中科院计算所/寒武纪公司出品的diannao系列。
- RPU – Radio Processing Unit, 无线电处理器， Imagination Technologies 公司推出的集合集Wifi/蓝牙/FM/处理器为单片的处理器。
- TPU – Tensor Processing Unit 张量处理器， Google 公司推出的加速人工智能算法的专用处理器。目前一代TPU面向Inference，二代面向训练。
- VPU – Vector Processing Unit 矢量处理器，Intel收购的Movidius公司推出的图像处理与人工智能的专用芯片的加速计算核心。
- WPU – Wearable Processing Unit， 可穿戴处理器，Ineda Systems公司推出的可穿戴片上系统产品，包含GPU/MIPS CPU等IP。
- XPU – 百度与Xilinx公司在2017年Hotchips大会上发布的FPGA智能云加速，含256核。
- ZPU – Zylin Processing Unit,由挪威Zylin 公司推出的一款32位开源处理器。
