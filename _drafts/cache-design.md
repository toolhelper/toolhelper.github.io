---
layout: post
title: 组策略处理
categories: Windows
description: 组策略处理
keywords: windows，Group Policy
---

# 组策略处理

当计算机启动且用户登录时，将按以下顺序应用计算机策略和用户策略：

### 1、网络启动。 远程过程调用系统服务 (RPCSS) 和多个通用命名约定提供程序 (MUP) 启动。

### 2、为设备获取组策略对象的有序列表。 该列表可能取决于以下因素：

* 设备是否是域的一部分，因此，取决于通过 Active Directory 组策略。
* 设备在 Active Directory 中的位置。
* 组策略 对象的列表是否已更改。 如果组策略对象列表未更改，则不执行任何处理。

### 3、应用计算机策略。 这些设置位于已收集列表中的“计算机配置”下。 此过程默认为同步过程，按以下顺序进行：本地、站点、域、组织单位、子组织单位等。 处理计算机策略时不显示任何用户界面。

### 4、启动脚本运行。 默认情况下，这些脚本是隐藏和同步的;每个脚本必须在下一个脚本开始之前完成或超时。 默认超时为 600 秒。 可以使用多个策略设置来修改此行为。

### 5、用户按 Ctrl+Alt+DEL 登录。

### 6、验证用户后，将加载用户配置文件;它受有效的策略设置控制。

### 7、为用户获取组策略对象的有序列表。 该列表可能取决于以下因素：

* 用户是否是域的一部分，因此，取决于通过 Active Directory 组策略。
* 是否启用了环回策略处理，如果是，则状态 (环回策略设置的“合并”或“替换) ”。
* 用户在 Active Directory 中的位置。
* 组策略 对象的列表是否已更改。 如果组策略对象列表未更改，则不执行任何处理。

### 8、应用用户策略。 这些设置是收集列表中的“用户配置”下的设置。 默认情况下，这些设置是同步的，按以下顺序进行：本地、站点、域、组织单位、子组织单位等。 处理用户策略时，不显示任何用户界面。

### 9、登录脚本运行。 默认情况下，基于 组策略 的登录脚本是隐藏和异步的。 用户对象脚本最后运行。

### 10 、将显示由组策略规定的操作系统用户界面。