---
title: "WMF 5.1 (プレビュー) の既知の問題"
ms.date: 2016-07-13
keywords: PowerShell, DSC, WMF
description: 
ms.topic: article
author: krishna
manager: dongill
ms.prod: powershell
ms.technology: WMF
translationtype: Human Translation
ms.sourcegitcommit: 57049ff138604b0e13c8fd949ae14da05cb03a4b
ms.openlocfilehash: 387ebc0467b9f154444292f391af0f4b77123639

---

#WMF 5.1 (プレビュー) の既知の問題 #

> 注意: この情報は暫定版であり、変更することがあります。

##Pester 問題
このリリースでは、Nano Server で Pester を利用するとき、2 つの問題に注意する必要があります。

* Pester 自体にテストを実行すると、FULL CLR と CORE CLR の違いに起因し、エラーが発生します。 具体的には、Validate メソッドが XmlDocument 型で利用できません。 nunit 出力ログのスキーマの検証を試行するテストが 6 つあり、これでエラーが発生します。 
* 現在、コード カバレッジの 1 つでエラーが発生します。*WindowsFeature* DSC リソースが Nano Server にないためです。 しかしながら、以上のエラーは一般的に無害であり、無視しても問題ありません。


<!--HONumber=Jul16_HO3-->


