---
title:  MSFT_DSCLocalConfigurationManager クラスの EnableDebugConfiguration メソッド
ms.date:  2016-05-16
keywords:  powershell,DSC
description:  
ms.topic:  article
author:  eslesar
manager:  dongill
ms.prod:  powershell
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
 

 





<!--HONumber=May16_HO3-->


