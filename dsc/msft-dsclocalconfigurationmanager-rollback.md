---
DCS.appliesToProduct: 'WindowsServer\_Dev'
Description: '以前の構成にロールバックします。'
MS-HAID: 'cimwin32a.MSFT_DSCLocalConfigurationManager\_rollback'
MSHAttr: 'PreferredLib:/library'
title: 'MSFT_DSCLocalConfigurationManager クラスの RollBack メソッド'
---

# MSFT_DSCLocalConfigurationManager クラスの RollBack メソッド

構成を以前のバージョンにロールバックします。

構文
------

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

パラメーター
----------

*configurationNumber* \[in\]  
要求された構成を指定します。 

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


