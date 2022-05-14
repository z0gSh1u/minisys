# *minisys*

这是我们小组对本科大四上学期的《计算机系统综合设计》课程的设计的集合。

*（因为代码在团队账号下，归不到自己的 repo list 就写了个集合 repo）*

在这门课中，我们合作造了：

- **一个 Verilog 写的片上系统 [ [minisys-1a-cpu](https://github.com/seu-cs-class2/minisys-1a-cpu) ]**
  - 五级流水、单发射、哈佛结构、可中断的 CPU，支持 57 条 MIPS 指令
  - 总线下挂式外设：拨码开关、矩阵键盘、八位七段数码管、蜂鸣器、LED 灯…
- **一个 C 语言（缩水版）编译器 [ [minisys-minicc-ts](https://github.com/seu-cs-class2/minisys-minicc-ts) ]**
  - 使用 TypeScript 语言
  - 从类 C 编译到类 MIPS 汇编（支持函数、递归、include、循环、作用域、内联汇编、地址访问）
  - 完全从 0 手工实现的
    - 基于 DFA 的词法分析（正则 → NFA → DFA，源码 → Token 流）
    - 基于 LALR 的语法分析（结合律、优先级、冲突处理）
    - 语法树生成（可视化）
    - 中间代码（IR）生成（四元式）
    - 中间代码优化（代数优化、死代码消除、常量传播和常量折叠）
    - 目标代码生成（寄存器分配，汇编语句选择）
    - 目标代码优化（Peephole）
  - 词法分析和语法分析借助另一门课的产品 [ [seu-lex-yacc](https://github.com/z0gSh1u/seu-lex-yacc) ]（学习《编译原理》的好帮手，可帮你画 DFA 和 LR1 语法分析表）
- **一个类 MIPS 汇编的汇编器 [ [minisys-asm](https://github.com/seu-cs-class2/minisys-asm) ]**
  - 使用 TypeScript 语言
  - 从类 MIPS 汇编到可上板的二进制机器码
  - 顺便帮你链接了基于中断向量表的中断处理程序和 BIOS，并布局了内存
  - 可以在线使用
- **一个全能的 IDE [ [minisys-ide](https://github.com/seu-cs-class2/minisys-ide) ]**
  - 使用 Electron 技术栈
  - 可配置相关工具链一键编译汇编加烧录
- **一系列能在板上运行的程序 [ [minisys-app](https://github.com/seu-cs-class2/minisys-app) ]**
  - 用前面的缩水 C 写的
  - 给了一套 “标准库”

