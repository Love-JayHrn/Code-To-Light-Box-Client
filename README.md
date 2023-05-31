# 软件体系结构课程设计
## 游戏描述

本项目名称为Code To Light Box，中文翻译为“编码点亮小盒子”，也可以被解读为将代码转换为控制光效。“Code”的原本的意思是“代码”，在这里译为“编码”。“To Light Box”表示“为了点亮盒子”。本游戏的目标是通过点击不同类型的方块（对应不同的行走策略）告诉机器人如何行走，实现将地图上所有的小盒子点亮，即可获得成功。

## 设计模式使用（重点）

结合上述体系结构的设计方案，结合本游戏特色，最终采用如下13种设计模式方案，包括了创建型模式，结构型模式，行为型模式三种。

1.  单例模式：该模式用于创建全局单个对象，包括游戏对象，每局游戏都只有一个实例；同时包括系统语言、系统音量、背景音乐、排行榜，这些都是确保只有一个实例。

2. 工厂模式：该模式可以用于业务逻辑层或者表示层的实现，通过工厂类来创建不同类型的对象，从而实现更好的封装性和灵活性，在这里通过工厂方式来创建主函数和子函中的程序。

3. 抽象工厂模式：可以通过抽象工厂来创建不同类型的关卡，这里我们设计了三种关卡。

4. 建造者模式：可以使用建造者模式来构建游戏对象，游戏中包括了机器人、程序、地图，不同的关卡的地图不一样，采用建造者模式创建不同的游戏关卡。

5. 适配器模式：这里游戏可能会采用多种登录方式，通过采用适配器模式适配第三方登录用户的信息。

6. 组合模式：这里程序呈现出部分——整体的关系，这里有多种函数，主函数可以有多个子函数，这里采用组合模式进行设计，简化类的创建。

7.  装饰器模式：可以使用装饰器模式来为机器人对象添加一些额外的行为。例如，可以用于表示层中对游戏界面的装饰处理。比如增加游戏音效、操作提示等，同时不同的类型排行榜使用装饰器模式。

8. 外观模式：可以使用外观模式来简化地图对象的接口。将地图类和方块工厂类封装在一个外观类中，提供了统一的接口。

9. 享元模式：实现方块的共享，避免创建相同的方块，减少系统中方块对象的数量，降低内存的占用，同时简化了系统的设计。

10. 命令模式：该模式是游戏中的机器人控制，通过命令对象来封装机器人的操作，实现游戏的逻辑。命令模式可以将机器人的操作和具体的命令对象解耦，使得代码更加灵活、可扩展和可维护。

11. 观察者模式：使用观察者模式来实现语言设置的功能。当语言设置发生变化时，所有注册的语言观察者会收到通知并更新对应的语言显示。该模式适用于当一个对象的状态变化需要通知其他多个对象，并且这些对象需要根据状态变化做出相应的处理时，可以使用观察者模式，游戏中用于实现切换语言，语言变化，通知观察者改变语言，排行榜进行观察，更新排行榜。

12.  策略模式：可以使用策略模式来封装不同的移动策略，包括上、下、左、右四个方向移动，并且可以在运行时动态地切换这些策略。

13. 模板方法模式：该模式可以用于业务逻辑层中相似操作的代码重复问题，将相同的部分提取出来形成一个模板方法，在不同的子类中实现具体的差异部分，这里用于实现游戏对象的初始化加载，所有的关卡都需要加载这些对象



## 包结构
com.nchu.software下的包结构解释
- common: 游戏实现需要的公共类
- controller: 业务逻辑控制，调用network包中的类
- controller.network: 所有网络交互的类，用于增删改查
- dto: 用于数据传输的对象，用于在前后端之间传递数据
- model: 游戏中的实体类对象
- pattern: 游戏设计模式所需要的类（自己根据模式创建包）
- view: 游戏界面

## 资源
main.resource
- css: 界面的css
- img: 界面图片

## 登录
用户名：
1. 开心的洋白菜 
2. 欢乐豆 
3. 小辣椒
密码：统一 123456

## 功能
1. 总排行榜（解锁关卡数目）
2. 关卡排行榜（闯关用时）
3. 切换语言（中英文）
4. 三种关卡