﻿# 直接运行Flappy_bird.html文件


> 1. 设计模式的使用：
所有的模块都使用了沙箱模式和工厂模式，小鸟使用了单利模式，
独立了一个观察者模块，然后在游戏场景模块中进行了使用。
> 2. 继承的使用：
所有的模块要么使用了原型覆写的继承方式，
要么使用了混入的继承方式，
另外游戏计时模块还使用了构造器借用的继承方式。
> 3. 模块之间的依赖：
一共12个模块，几乎所有的模块都依赖util模块，所以需要最先引入；
flappyBird模块依赖所有的scene模块 ==> loaddingScene、overScene、gameScene；
loaddingScene模块依赖 ==> text；
overScene模块依赖 ==> text、observer；
gameScene模块依赖的最多 ==> bird、land、sky、pipe、timer；
timer模块依赖 ==> text。

## 设计模式的使用
- 所有的模块都使用了沙箱模式和工厂模式
- 小鸟使用了单利模式（所有的场景也可以改为单利模式）
- 独立了一个观察者模块，然后在游戏场景模块中进行了使用

## 继承的使用
- 所有的模块要么使用了原型覆写的继承方式，要么使用了混入的继承方式
- 游戏计时模块使用了构造器借用的继承方式。

## 模块之间的依赖关系
- 一共12个模块，几乎所有的模块都依赖util模块
- flappyBird模块依赖所有的scene模块 ==> loaddingScene、overScene、gameScene
- loaddingScene模块依赖 ==> text
- overScene模块依赖 ==> text、observer
- gameScene模块依赖的最多 ==> bird、land、sky、pipe、timer
- timer模块依赖 ==> text

## util模块方法
- angleToRadian：角度转弧度
- extend：混入继承
- getCanvasContext：创建2d绘图环境
- getImage：图片加载器

## flappyBird模块方法
- start: 开始游戏
- pause: 暂停游戏
- end: 结束游戏

## loadingScene模块方法
- draw: 绘制loading提示

## overScene模块方法
- draw: 绘制结束内容

## gameScene模块方法
- isBirdDie：判断小鸟是否死亡
- addListener：添加小鸟死亡听众
- draw：绘制游戏画面
- update：计算游戏下一帧的数据

## text模块方法
- draw：绘制文本

## bird模块方法
- draw：绘制小鸟
- update：计算小鸟下一帧的数据

## land模块方法
- draw：绘制大地
- update：计算大地下一帧的数据

## sky模块方法
- draw：绘制天空
- update：计算天空下一帧的数据

## pipe模块方法
- draw：绘制管道
- update：计算管道下一帧的数据

## timer模块方法
- draw：绘制游戏时长
- update：重新计算游戏时长
