---
title: "MSFT_DSCLocalConfigurationManager クラスの ApplyConfiguration メソッド"
ms.date: 2016-05-16
keywords: powershell,DSC
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
translationtype: Human Translation
ms.sourcegitcommit: 919438862ca9786447b690d2db10e905da0a7c42
ms.openlocfilehash: 6f9c6a8851732574ac72bc4f3a3db1a73fbbecf2

---

# MSFT_DSCLocalConfigurationManager クラスの ApplyConfiguration メソッド

構成エージェントを使用して、保留中の構成を適用します。 

保留中の構成がない場合は、現在の構成を再適用します。


## 構文
------

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## パラメーター
----------

*force* \[in\]  
**true** の場合、保留中の構成があっても、現在の構成が再適用されます。

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


