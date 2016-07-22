---
title: "DSC リソースのデバッグの機能強化"
author: jaimeo
contributor: amitsara
translationtype: Human Translation
ms.sourcegitcommit: e39aa2e5cbda0c83e24e21c4459d957d8baaff25
ms.openlocfilehash: 33c3fcffdeb281b205ecc48f7cdd470b79e9e068

---


## DSC リソースのデバッグの機能強化

WMF 5.0 では、PowerShell デバッガーは、クラス リソース メソッド (Get/Set/Test) で直接停止しませんでした。
この問題は解消されました。デバッガーは、mof ベースのリソース メソッドと同様に、クラス リソース メソッドで停止します。



<!--HONumber=Jul16_HO3-->


