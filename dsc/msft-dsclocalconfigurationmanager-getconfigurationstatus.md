---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの GetConfigurationStatus メソッド"
ms.openlocfilehash: e02ed81a7b8436323bc68aaa2587a445e6a5adf9
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="getconfigurationstatus-method-of-the-msftdsclocalconfigurationmanager-class" class="xliff"></a>

# MSFT_DSCLocalConfigurationManager クラスの GetConfigurationStatus メソッド

構成状態の履歴を取得します。

<a id="syntax" class="xliff"></a>

構文
------

```mof
uint32 GetConfigurationStatus(
  [in]  boolean                     All,
  [out] MSFT_DSCConfigurationStatus configurationStatus[]
);
```

<a id="parameters" class="xliff"></a>

パラメーター
----------

*All* \[in\]  
**true** の場合、コンピューターで実行中のすべての構成 (構成の適用や整合性チェックも含む) についての情報が返されます

*configurationStatus* \[out\]  
制御が戻ったとき、設定を定義する **MSFT_DSCConfigurationStatus** クラスの埋め込みインスタンスが含まれます。

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


 

 



