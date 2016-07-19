---
title: "MSFT_DSCLocalConfigurationManager クラスの EnableDebugConfiguration メソッド"
ms.date: 2016-05-16
keywords: powershell,DSC
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
translationtype: Human Translation
ms.sourcegitcommit: 919438862ca9786447b690d2db10e905da0a7c42
ms.openlocfilehash: f74e9941180c00a1aae1bd1d7b48fa4de0c8790d

---


# MSFT_DSCLocalConfigurationManager クラスの EnableDebugConfiguration メソッド

DSC リソースのデバッグを有効にします。

構文
------

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

パラメーター
----------

*BreakAll* \[in\]  
リソース スクリプトのすべての行にブレークポイントを設定します。

## 戻り値
------------

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## コメント

これは静的メソッドです。

## 要件
------------
>**MOF:** DscCore.mof

>**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration


## 関連項目


[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
 

 






<!--HONumber=Jun16_HO4-->


