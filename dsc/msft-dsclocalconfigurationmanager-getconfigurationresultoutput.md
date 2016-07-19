---
title: "MSFT_DSCLocalConfigurationManager クラスの GetConfigurationResultOutput メソッド"
ms.date: 2016-05-16
keywords: powershell,DSC
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
translationtype: Human Translation
ms.sourcegitcommit: c915ebd021ed20209bc491505d45cff2ac89f21d
ms.openlocfilehash: 8f13964dfbbe1cd827c58232a35d1cbacddeed1b

---

# MSFT_DSCLocalConfigurationManager クラスの GetConfigurationResultOutput メソッド

特定のジョブに関連する構成エージェントの出力を取得します。

構文
------

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

パラメーター
----------

*jobId* \[in\]  
出力データを取得するジョブの ID です。

*resumeOutputBookmark* \[in\]  
出力が前のブックマークからの続きとなるように指定します。

*output* \[out\]  
指定されたジョブの出力です。

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


