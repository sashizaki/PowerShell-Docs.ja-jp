---
title: "MSFT_DSCLocalConfigurationManager クラスの GetConfiguration メソッド"
ms.date: 2016-05-16
keywords: powershell,DSC
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
translationtype: Human Translation
ms.sourcegitcommit: 919438862ca9786447b690d2db10e905da0a7c42
ms.openlocfilehash: 19d4790f22491e0bb11de1e315d1ee3b07929d55

---

# MSFT_DSCLocalConfigurationManager クラスの GetConfiguration メソッド

構成ドキュメントを管理ノードに送信し、構成エージェントの **Get** メソッドを使用して構成を適用します。

構文
------

```mof
uint32 GetConfiguration(
  [in]  uint8            configurationData[],
  [out] OMI_BaseResource configurations[]
);
```

パラメーター
----------

*configurationData* \[in\]  
送信する構成データを指定します。

*configurations* \[out\]  
制御が戻ったとき、その構成の埋め込みインスタンスが含まれます。

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


