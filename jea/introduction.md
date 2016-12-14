---
description: 
manager: dongill
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット, JEA"
ms.date: 2016-06-22
title: "はじめに"
ms.technology: powershell
ms.openlocfilehash: 71264d1001228249d9f2bb0f72473e9761170bf0
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
translationtype: HT
---
# <a name="introduction"></a>はじめに

##  <a name="motivation"></a>**動機**  
システムに対する特権アクセスを誰かに付与することは、信頼の境界をその人物まで拡張することを意味します。
これにはリスクが伴います。なぜなら、管理者は、システムを攻撃する者になる可能性があるためです。
内部の関係者による攻撃と資格情報の盗難は、どちらも実際によくあることです。

##  <a name="not-a-new-problem"></a>**新しい問題ではありません。**  
最小権限の原則を熟知し、ロール ベースのアクセス制御 (RBAC) を何らかの形で使用してアプリケーションの管理を行っているかもしれません。
ただし、このソリューションの有効性と管理容易性は、多くの場合、その適用範囲の幅広さと不正確さによる限界があります。
さらに、RBAC には、その適用範囲にずれがあります。
たとえば、Windows では、特権アクセスの大部分はバイナリ スイッチであり、ユーザーを Administrators グループに追加するときに、不要なアクセス許可が強制的に付与されることになります。

##  <a name="just-enough-administration-jea"></a>**Just Enough Administration (JEA)** 
PowerShell リモート処理によるロール ベースのアクセス制御 (RBAC) プラットフォームを提供します。
*また、特定のユーザーに管理者権限を与えることなく、そのユーザーが特定のサーバーで特定の管理タスクを実行できるようにします。*
これにより、既存の RBAC ソリューションのずれを補い、設定を容易に管理できるようにします。

