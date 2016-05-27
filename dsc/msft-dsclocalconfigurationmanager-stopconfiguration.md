---
title:  MSFT_DSCLocalConfigurationManager クラスの StopConfiguration メソッド
ms.date:  2016-05-16
keywords:  powershell,DSC
description:  
ms.topic:  article
author:  eslesar
manager:  dongill
ms.prod:  powershell
---

# MSFT_DSCLocalConfigurationManager クラスの StopConfiguration メソッド

進行中の構成の変更を停止します。

構文
------

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

パラメーター
----------

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


 

 





<!--HONumber=May16_HO3-->


