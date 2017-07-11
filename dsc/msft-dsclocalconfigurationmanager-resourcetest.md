---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの ResourceTest メソッド"
ms.openlocfilehash: 73d7d543505a3768a0660084345d3858e055514f
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="resourcetest-method-of-the-msftdsclocalconfigurationmanager-class" class="xliff"></a>

# MSFT_DSCLocalConfigurationManager クラスの ResourceTest メソッド

DSC リソースの **Test** メソッドを直接呼び出します。

<a id="syntax" class="xliff"></a>

構文
------

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

<a id="parameters" class="xliff"></a>

パラメーター
----------

*ResourceType* \[in\]  
呼び出すリソースの名前。

*ModuleName* \[in\]  
呼び出すリソースを含むモジュールの名前。

*resourceProperty* \[in\]  
ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。 リソースのプロパティと種類を検出するには、[Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx) コマンドレットを使用します。

*InDesiredState* \[out\]  
ターゲット ノードが目的の状態にある場合、制御が戻るときに、このプロパティは **true** に設定されます。

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


 

 



