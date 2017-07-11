---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド"
ms.openlocfilehash: d8ddc9d99f0d74ad907a6e39ae0e8ac14159be16
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="sendmetaconfigurationapply-method-of-the-msftdsclocalconfigurationmanager-class" class="xliff"></a>

# MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド

構成エージェントを制御するために使用するローカル構成マネージャーの設定を設定します。

<a id="syntax" class="xliff"></a>

構文
------

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

<a id="parameters" class="xliff"></a>

パラメーター
----------

*ConfigurationData* \[in\]  
構成用の環境データ。

*force* \[in\]  
**true** の場合、構成を強制的に中止します。

<a id="return-value" class="xliff"></a>

## 戻り値
------------

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

<a id="remarks" class="xliff"></a>

## コメント

これは静的メソッドです。

<a id="requirements" class="xliff"></a>

## 要件
------------
>**MOF:** DscCore.mof

>**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration


<a id="see-also" class="xliff"></a>

## 関連項目


[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)


 

 



