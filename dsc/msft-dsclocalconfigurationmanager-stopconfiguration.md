---
DCS.appliesToProduct: 'WindowsServer\_Dev'
Description: '進行中の構成を停止しています。'
MS-HAID: 'cimwin32a.MSFT_DSCLocalConfigurationManager\_stopconfiguration'
MSHAttr: 'PreferredLib:/library'
title: 'MSFT_DSCLocalConfigurationManager クラスの StopConfiguration メソッド'
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


 

 





<!--HONumber=Apr16_HO2-->


