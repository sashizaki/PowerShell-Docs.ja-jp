---
title: "MSFT_DSCLocalConfigurationManager クラスの GetConfigurationResultOutput メソッド"
ms.date: 2016-05-16
keywords: PowerShell, DSC
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
ms.openlocfilehash: 8f13964dfbbe1cd827c58232a35d1cbacddeed1b
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
translationtype: HT
---
# <a name="getconfigurationresultoutput-method-of-the-msftdsclocalconfigurationmanager-class"></a>MSFT_DSCLocalConfigurationManager クラスの GetConfigurationResultOutput メソッド

特定のジョブに関連する構成エージェントの出力を取得します。

<a name="syntax"></a>構文
------

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

<a name="parameters"></a>パラメーター
----------

*jobId* \[in\]  
出力データを取得するジョブの ID です。

*resumeOutputBookmark* \[in\]  
出力が前のブックマークからの続きとなるように指定します。

*output* \[out\]  
指定されたジョブの出力です。

## <a name="return-value"></a>戻り値
------------

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>コメント

これは静的メソッドです。

## <a name="requirements"></a>要件
------------
>**MOF:** DscCore.mof

>**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration


## <a name="see-also"></a>関連項目


[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)

 

 



