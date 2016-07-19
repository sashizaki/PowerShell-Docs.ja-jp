---
title: "MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド"
ms.date: 2016-05-16
keywords: powershell,DSC
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
translationtype: Human Translation
ms.sourcegitcommit: c915ebd021ed20209bc491505d45cff2ac89f21d
ms.openlocfilehash: a81b41f66883b3cf0931905d24c8ff92ef55b6c7

---

# MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド

構成エージェントを制御するために使用するローカル構成マネージャーの設定を設定します。

構文
------

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

パラメーター
----------

*ConfigurationData* \[in\]  
構成用の環境データ。

*force* \[in\]  
**true** の場合、構成を強制的に中止します。

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


