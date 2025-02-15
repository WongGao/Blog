# 行为型模式总结

创建型模式：对对象的实例化过程进行抽象，这使得一个系统可以不用关心这些对象是如何创建，组合，呈现的，对于类创建模式来说通过使用继承改变实例化的类，对于对象创建模式来说通过使用代理来实例化所需要的对象

结构型模式：通过对多个类和对象进行组合得到复杂结构的类，一般使用继承或者成员变量引用形式来实现。

行为型模式：行为模式不仅表达了对象和类，还表达了他们之间的交互，涉及到了对象和算法的分配。

--------------------------------------------------------------------------------
行为型： 观察者模式 模板方法模式 命令模式 状态模式 职责链模式 解释器模式 中介者模式 访问者模式 策略模式 备忘录模式 迭代器模式

--------------------------------------------------------------------------------
观察者模式

设计原则：遵循迪米特、开闭原则

常用场景：需要将观察者与被观察者解耦或者是观察者的种类不确定

使用概率：40%

复杂度：中

变化点：观察者的种类与个数

选择关键点：观察者与被观察者是否是多对一的关系

逆鳞：观察者之间有过多的细节依赖

模板方法模式

设计原则：破坏里氏替换，体现功能复用

常用场景：一批子类的功能有可提取的公共算法骨架

使用概率：80%

复杂度：中低

变化点：算法骨架内各个步骤的具体实现

选择关键点：算法骨架是否牢固

逆鳞：无

命令模式

设计原则：遵循迪米特、开闭原则

常用场景：行为的请求者与行为的处理者耦合度过高

使用概率：20%

复杂度：中高

变化点：命令的种类

选择关键点：请求者是否不需要关心命令的执行只知道接受者

逆鳞：命令的种类无限制增长

相关设计模式


职责链模式：容易将二者关联在一起的原因是，二者都是为了处理请求或者命令而存在的，而且二者都是为了将请求者与响应者解耦，不同的是命令模式中，客户端需要知道一个命令的接受者，在创建命令的时候就把接受者与命令绑定在一起发送给调用者，而职责链模式中，客户端并不关心最终处理请求的对象是谁，客户端只是封装一个请求对象，随后交给职责链的头部而已，也正因为这样，二者的实现方式，有着很大的区别

状态模式

设计原则：遵循单一职责、依赖倒置、开闭原则

常用场景：一个对象在多个状态下行为不同，且这些状态可互相转换

使用概率：20%

复杂度：中

变化点：状态的种类

选择关键点：这些状态是否经常在运行时需要在不同的动态之间相互转换

逆鳞：无

相关设计模式

策略模式：二者的实现方式非常相似，策略接口与状态接口，具体的策略与具体的状态以及二者都拥有的上下文，如果看它们的类图，会发现几乎一模一样，而二者不同的地方就在于，状态模式经常会在处理请求的过程中更改上下文的状态，而策略模式只是按照不同的算法处理算法逻辑，而且从实际场景来讲，顾名思义，状态模式改变的是状态，策略模式改变的是策略

职责链模式

设计原则：遵循迪米特

常用场景：一个请求的处理需要多个对象当中的一个或几个协作处理

使用概率：15%


复杂度：中


变化点：处理链的长度与次序

选择关键点：对于每一次请求是否每个处理的对象都需要一次处理机会

逆鳞：无

解释器模式

设计原则：遵循单一职责

常用场景：有一种语言被频繁的使用

使用概率：0.00009%

复杂度：中高

变化点：语言的规则

选择关键点：被频繁使用的语言是否可用文法表示

逆鳞：语言的规则无限制增长或规则十分不稳定

中介者模式

设计原则：遵循迪米特，破坏单一职责

常用场景：一个系列的对象交互关系十分复杂

使用概率：10%

复杂度：中

变化点：对象之间的交互

选择关键点：复杂的交互关系是否有共性可被中介者承担

逆鳞：中介者无法工作

访问者模式

设计原则：遵循倾斜的开闭原则

常用场景：作用于一个数据结构之上的操作经常变化

使用概率：5%

复杂度：高

变化点：数据结构之上的操作

选择关键点：数据结构是否稳定以及操作是否经常变化

逆鳞：数据结构的不稳定

策略模式

设计原则：遵循单一职责、依赖倒置、迪米特、开闭原则

常用场景：算法或者策略需要经常替换

使用概率：60%

复杂度：中

变化点：策略的种类

选择关键点：客户端是否依赖于某一个或若干个具体的策略

逆鳞：无

备忘录模式

设计原则：遵循迪米特、开闭原则

常用场景：需要在对象的外部保存该对象的内部状态

使用概率：5%


复杂度：中

变化点：无

选择关键点：是否可以在必要的时候捕捉到对象的内部状态

逆鳞：大对象的备份

迭代器模式

设计原则：遵循迪米特

常用场景：需要迭代访问一个聚合对象中的各个元素，且不暴露该聚合对象内部的表示

使用概率：99.99999%

复杂度：中

变化点：聚合对象的种类

选择关键点：客户端是否关心遍历的次序

逆鳞：无

相关设计模式

访问者模式：二者都是迭代的访问一个聚合对象中的各个元素，不同的是，访问者模式中，扩展开放的部分在作用于对象的操作上，而迭代器模式中，扩展开放的部分在聚合对象的种类上，而且二者的实现方式也有着很大的区别。

![image](assets/231055f0f53b677242792b0744033525.jpeg)
