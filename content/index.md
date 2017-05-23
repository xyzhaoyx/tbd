---
date: 2017-05-23T16:08:33+08:00
title: Introduction
type: index
weight: 0
---

<!-- print <h1 style="color: white; padding: 32px 20px 72px; background-image:url(/images/LogoSlim.png); background-repeat: no-repeat; background-size: 100% auto"><span style="background-color: #5677fc">Introduction</span></h1> print -->


## 一句话总结

有这么一种分支模型，所有的开发人员都在一条被称为'trunk' * 的分支上进行编码协作，通过采用记录技术来避免创建额外的长期分支，防止了合并灾难的发生，不会破坏构建的稳定，从此过上了幸福的生活。

![](trunk1.png)
([图例](/key/))

*在Git中称之为'master'

基于主干开发（Trunk-Based Development）是实施[持续集成](/continuous-integration/)以至于扩展到[持续交付](/continuous-delivery/)的关键推动因素。当团队中的每个人每天都向主干多次提交他们的改动时，这就很容易满足持续集成的核心要求，即团队所有成员在24小时内至少向主干提交一次。这就确保基线代码始终保持可按需发布的状态，并使得持续交付成为可能。

## 注意事项

- 根据团队规模和提交频率，[短期特性分支](/short-lived-feature-branches/)用于代码提交进入主干被其他开发人员引用之前，进行代码审查和构建检查(CI)。

- 这些分支帮助开发人员在对他们所贡献的代码合并入主干前，进行[积极和持续的代码审查](/continuous-review/)。小团队可能会[直接提交至主干](/committing-straight-to-the-trunk/)。

- 根据预期的发布节奏，可能会基于主线正好赶上发布的提交，拉出一些[发布分支](/branch-for-release/)，并且在发布（可能没有具体的团队活动）之前被“固化”，在发布后的一段时间里，**这些分支会被删掉**。另一种可能是，如果团队选择“下个版本修复（fix forward）”的修复缺陷策略，他们则会基于主干直接发布，而没有发布分支。基于主干发布也是为快速交付团队（high-throughput teams）准备的。

- 面对难以一次性实现的复杂修改，团队应该精通使用[抽象模拟分支](/branch-by-abstraction/)的相关技术，并在日常开发中使用[特性开关](/feature-flags/)来屏蔽它们对发布的影响（另一个好办法 - 参考 [串行发布中的并行开发](/concurrent-development-of-consecutive-releases/)）

- 如果你的团队有超过2名的开发人员，那么你需要一个和代码服务挂接的[构建服务器](/continuous-integration/)来验证他们的提交进入主干后**没有破坏构建稳定**，同时也用于将短期特性分支合并回主干时的验证。

- 开发团队可以任意调整团队大小，而不影响交付节奏和质量。

  证据？[Google 基于主干开发](/game-changers/index.html#google-revealing-their-monorepo-trunk-2016)在单条[monorepo](/monorepo/)主干拥有**25000个开发和自动化测试人员**的情况下，进行团队的[扩展或缩小](/expanding-contracting-monorepos/)以适应开发人员数量。

- 正在实践 [GitHub-flow 分支模型](/alternative-branching-models/index.html#modern-claimed-high-throughput-branching-models)的人会觉得这两种分支模型十分相似，但是从哪进行发布，它们之间还是有着一点小小的不同。

- 正在实践 Gitflow 分支模型的人会发现，这和过去开发人员所熟悉的 ClearCase, Subversion, Perforce, StarTeam, VCS 的[传统分支模型](/alternative-branching-models/index.html#legacy-branching-models)非常不同。

- [很多出版物](/publications/)提倡过我们所描述的这个基于主干开发（Trunk-Based Development）模式，其中包括非常畅销的《Continuous Delivery》和《DevOps Handbook》。这个话题甚至不应该在存有争议！

## 历史

基于主干开发（Trunk-Based Development）不是一个新的分支模型。'主干'（trunk）一词的概念源于生长中的树，其中最粗最长的是主干，而那些基于主干延伸出来的长度有限的是分支。

自八十年代被提出，截止九十年代中期一直作为一种不太知名的分支模型被使用。最大的开发组织，像 Google（上文提到过的）和 Facebook 正在规模化的实践这种分支模型。

30多年来，不同的[源码管理技术和相关工具／技术的进步](/game-changers/)使得基于主干开发（Trunk-Based Development）越来越流行，但是它始终是许多人多年来一直坚持使用的分支模型。

## 关于本站

本站试图将基于主干开发（Trunk-Based Development）相关的事实，理论基础和技术收集在一个地方，并附有25张图示来帮助解释。所有没有用 TBD 作为缩写的有~~一次~~两次。