---
layout: post
title: "★★★☆☆ 「程序员修炼之道」——从小工到专家"
tagline: ""
description: ""
category: 读书
tags: [编程]
last_updated: 2018-03-25
---

本书作者 Andrew Hunt 和 David Thomas 从多个角度探讨了什么是好的编程习惯和如何搭建一支高效的编程团队。这本书值得再重读，我感觉这一次读有很多内容并不适用于我现在的工作环境，比如如何保持高效的团队协作。我同意一个说法是，这本书需要等到一定时候才需要去看或者说才可以看得懂。以下是我摘抄的部分：

## DRY原则 (Don't Repeat Yourself)
- 几种可能的重复：imposed duplication/ anadvertent duplication/ impatient duplication/ interdveloper duplication
- 把低级的知识放在代码里。注释留给高级说明。

## 正交性
- 保持代码改动局部化，隔离风险；同样的，小组成员的分工也要正交化。
    - 维持正交：保持你的代码解耦/避免全局数据/避免写相似的函数/尝试重构。

## 曳光代码
- 从开发最小可用产品开始。避免从复杂繁重的文档和大而全的设计开始。先实现一个可供操作和评估的东西，观察用户的反应。一旦命中，再对其进行修缮和完备，反复直到形成最终的产品。
- “曳光弹”是可交付代码的一部分，而“原型”的代码与交付的产品没有任何关系。

## 版本控制
- 永远保持所有东西都在版本控制之下，包括代码以外的东西。这样给我们在关键时刻使用时间机器的能力。

## Design by Contract (DBC原则)
- Write down the precondition, post condition and case invariant so that you can check them easily.

## Crash Yor Program Earliy
- 在出现错误的时候，让你的程序早点崩溃比让它继续跑下去并导致不可预料的后果更好。有以下一些方法去达到这个目标：
  - Catch runtime error
  - Use assert: *If it can't happen, use assertions to make sure it wont*

## Metaprogram Design
- Configure, don't integrate into the code.
  - 我的理解是用配置文件管理程序而不是把参数hard coded在里面。

##  不要依靠巧合编程
- 不要不顾一切地尝试把某种东西显示在屏幕上，这往往就是你在依靠巧合编程。
- 在极端情况下，你的例程甚至没有被设计成去做你想要他做的事情，但看起来他却工作的很好。

## 解决不可能解决的谜题
- 尝试着向鸭子玩具解释每一行代码，让代码里的错误自然地浮现出来。
- 问自己是不是一定要这么做去解决问题。
- 重新审视真正的需求。

## 营销技巧
- 创建一个团队的logo，可以用滑稽的名字，在各种展示的场合到处用，提升团队凝聚力，更容易被外界recognized。

## 自动化流程
- 编译，单元测试等都可以自动化。用Shell等编写脚本。

## 杂项
- 让你的用户参与权衡需求，在最后一刻为了满足时间压力而削减掉基本的工程内容是没有职业素养的行为。
- 投资知识资产和金融资产的要诀是一样的：定期投资／多元化／平衡风险和回报／低买高卖／周期性重新评估和平衡。
- 批判性的思考，警惕商业主义的力量。比如书店展示一本书是因为有人付了钱。
- 日常生活中应该总是对他人得邮件做出回应，即使内容是我稍后回复你。让他们原谅你偶然的疏失，你没有忘记他们。
- Gently exceed users expect。 增添自己的商誉。
- 名词学习： Hisenburg: 改变了被调试系统的调试过程
- 这本书翻译的真是太差了。我真的觉得看英文版的恐怕会好一些。这本书的中文翻译差到让我第一次看着中文书用英文记起了笔记。
