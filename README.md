# 专用量子计算

基本背景
---
量子计算有哪些实验路线？
### 1. 光量子
<div align=center>
<ima src="https://user-images.githubusercontent.com/118708553/210042795-0438dfcd-46dd-4a15-86bf-cc2656d43bf2.PNG"/>
</div>
光量子是将量子信息编码在光子的几率、相位等信息上，并通过单量子比特操控和测量过程实现 MBQC（Measurement Based Quantum Computing）来实现量子计算

### 2. 离子阱
<div align=center>
<ima src="https://user-images.githubusercontent.com/118708553/210042877-b40e177a-0af1-46df-bac7-3ba35fcfbed6.PNG"/>
</div>
将量子信息编码在原子的二能级上，并利用激光进行量子比特操操纵

### 3. 中性原子
<div align=center>
<ima src="https://user-images.githubusercontent.com/118708553/210042910-2efdb999-3269-43f6-9f09-d98283ce3965.PNG"/>
</div>

### 4. 超导
<div align=center>
<ima src="https://user-images.githubusercontent.com/118708553/210042957-000188ef-4746-4335-8b58-15cf3f4fbb87.PNG"/>
</div>

超导线路是将量子信息编码在一个非线性振荡电路中的电子振荡模式的量子化能级上，并利用微波来进行量子比特操纵。量子比特可以直接在芯片上加工。在实际操作中，量子芯片需要被置于极低温环境下（10 mK）

## 目前量子发展到了什么阶段？
<div align=center>
<ima src="https://user-images.githubusercontent.com/118708553/210043023-efbc7414-0d97-4e9b-b69c-159aed3eee36.PNG"/>
</div>

目前在试图提升物理量子比特等实验技术的同时，在尝试实际通过量子纠错来降低错误率，在朝向实现 逻辑量子比特的道路前进。

### 离子阱

公司：
IONQ（估值1b）
Honeywell
AQT
华翊量子（奇绩校友）

目前IonQ和Honeywell的装置已经可以实际跑量子纠错并减少误差
IonQ: Fault-tolerant control of an error-corrected qubit
Honeywell: Realization of real-time fault-tolerant quantum error correction

优势：保真度高、相干时间长、连通性好
劣势：量子比特扩张难度高，门速度慢

### 超导

公司：
Google
IBM
rigetti (YC校友，已上市，IPO市值 1b，现在跌到 200M了)
IQM
本源量子（上一轮融了10亿人民币）
...

目前Google的装置也可以实际跑量子纠错并减少误差

优势：扩展容易，门速度快（ns）
劣势：要求极低温环境，相干性差，连通性差

### 光量子

公司：
Psiquantum（估值 3b）
Xanadu（1个月前完成1亿美元的C轮融资，估值1b）
...

注意：
因为光子之间没有相互作用，所以没法编程光子之间的相互作用来做逻辑门，只能基于MBQC模型编程光子的路径来让量子态坍塌到最终结果上。基于MBQC也是通用量子计算。
目前只有Psiquantum在基于MBQC方式进行研发。
Psiquantum: Fusion-based quantum computation
国内王剑威教授和Psiquantum是相同路径

Xanadu是基于连续变量光+MBQC的方式去做，原理上也是通用量子计算，但是目前暂无明确文章出现。

### 中性原子
公司：
Coldqunta
Atom computing
QuEra
pasqal
中科酷原

目前哈佛团队(QuEra)可以实现基于中性原子的通用量子计算
QuEra: A quantum processor based on coherent transport of entangled atom arrays
技术为光晶格+光镊+里德堡原子

优点：扩展性好
缺点：控制较难，系统不稳定

## 通用与专用量子计算？
数理逻辑的视角来说，如果我们能够实现某个特定的逻辑操作，那么我们就可以实现所有的逻辑计算，也就是可以编程。这种我们叫做通用计算。
量子计算也是一样的，有一些特定的量子门组合，只要我们能实现这些组合的每一个量子门，我们就可以实现量子计算机的通用计算。

区别于通用量子计算，专用量子计算主要特点在于只能解决一部分特定问题，无法编程。

专用量子计算例子

### 九章，图灵量子，玻色量子
<div align=center>
<img src="https://user-images.githubusercontent.com/118708553/210043140-b77b278f-7cdf-405c-ad7b-63814327a228.png"/>
</div>

只能解决高斯玻色取样问题，或许可以应用在 计算分子谱，计算图论问题上，目前没有实际落地方向
陆朝阳教授团队应该也在同时进行可编程光量子路线的研究，但目前无具体公开研究结果
注意：目前结果为80量子比特左右

### 中性原子(QuEra)
<div align=center>
<img src="![7](https://user-images.githubusercontent.com/118708553/210043178-b861e777-711d-4e5e-92b6-bfcfce0f1e45.png"/>
</div>

目前只能解决 Maximum Independent Set problem问题 （图的优化问题，为经典NP问题），实验证明存在加速（并不是指数！NP问题量子计算机无法指数加速。实验装置为289 量子比特！）
QuEra：A quantum processor based on coherent transport of entangled atom arrays

### 量子退火(D-wave)
D-wave在1999年成立，于2022年8月上市
该公司技术路线为量子退火，基于绝热演化来解决最优化问题。
值得一提，该技术路线非常多学者持怀疑或者否认态度，认为这根本没有量子特性
但后来被证明该公司芯片还是有一定量子特性
D-wave: Quantum annealing with manufactured spins
D-wave是目前距离商业化最近的公司，已经有不少公司利用该公司产品来做一些优化问题，但实际具体效果如何理论上完全没有保证。

专用量子计算主要是量子计算发展路径中的一些特定路线，优势在于考虑的问题是最硬件友好地，相比于通用量子计算能实际去落地的早很多。但是问题在于考虑的问题往往过于局限，想找到合适的落地场景也十分有难度。
