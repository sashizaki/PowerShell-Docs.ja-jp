---
description: 
manager: dongill
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: powershell,cmdlet,jea
ms.date: 2016-06-22
title: "はじめに"
ms.technology: powershell
translationtype: Human Translation
ms.sourcegitcommit: e6b5107b7222708dcceff14bc26f0e12ef98d728
ms.openlocfilehash: 00d568234b1453b9161b60d20117374ee4111ab3

---

# はじめに

##  **動機**  
システムに対する特権アクセスを誰かに付与することは、信頼の境界をその人物まで拡張することを意味します。
これにはリスクが伴います。なぜなら、管理者は、システムを攻撃する者になる可能性があるためです。
内部の関係者による攻撃と資格情報の盗難は、どちらも実際によくあることです。

##  **新しい問題ではありません。**  
最小権限の原則を熟知し、ロール ベースのアクセス制御 (RBAC) を何らかの形で使用してアプリケーションの管理を行っているかもしれません。
ただし、このソリューションの有効性と管理容易性は、多くの場合、その適用範囲の幅広さと不正確さによる限界があります。
さらに、RBAC には、その適用範囲にずれがあります。
たとえば、Windows では、特権アクセスの大部分はバイナリ スイッチであり、ユーザーを Administrators グループに追加するときに、不要なアクセス許可が強制的に付与されることになります。

##  **Just Enough Administration (JEA)** 
PowerShell リモート処理によるロール ベースのアクセス制御 (RBAC) プラットフォームを提供します。
*それは、特定のユーザーに管理者権限を与えることなく、そのユーザーが特定のサーバーで特定の管理タスクを実行できるようにします。*
これにより、既存の RBAC ソリューションのずれを補い、設定を容易に管理できるようにします。




<!--HONumber=Jul16_HO1-->


