# MotaAction
项目[mota-js](https://github.com/ckcz123/mota-js)的事件编辑器子模块

同时用来尝试用[antlr](https://github.com/antlr/antlr4)来完成自动的.g4转[blockly](https://github.com/google/blockly)的过程

[转化思路](./convert.md)

motaAction和blockly运行机制的[简单介绍](./talk.md)

目前进度
+ 能够用BlocklyGrammer.g4解析MotaAction.g4
+ SymbolVisitor能够解析所有符号

- - -

blockly中mutators太过麻烦不适宜自动化,放弃

> blockly中`numeric imput`的机制待研究.

可以借助ChangeListener实现
```
b.getFieldValue()
b.setFieldValue('NUM',123)
b.getInputTargetBlock('statements')

b=demoWorkspace.getBlockById(event.blockId)
event.type == Blockly.Events.CHANGE && b.type == 'xxxx'
```
blockly.xml需要仔细研究一下

函数声明和变量声明也要再看一看