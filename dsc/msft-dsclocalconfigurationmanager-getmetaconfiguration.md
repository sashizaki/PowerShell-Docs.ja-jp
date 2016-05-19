---
DCS.appliesToProduct: 'WindowsServer\_Dev'
Description: '構成エージェントを制御するために使用するローカル構成マネージャーの設定を取得します。'
MS-HAID: 'cimwin32a.MSFT_DSCLocalConfigurationManager\_getmetaconfiguration'
MSHAttr: 'PreferredLib:/library'
title: 'MSFT_DSCLocalConfigurationManager クラスの GetMetaConfiguration メソッド'
---

# MSFT_DSCLocalConfigurationManager クラスの GetMetaConfiguration メソッド

構成エージェントを制御するために使用するローカル構成マネージャーの設定を取得します。

構文
------

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

パラメーター
----------

*MetaConfiguration* \[out\]  
制御が戻ったとき、設定を定義する **MSFT_DSCMetaConfiguration** クラスの埋め込みインスタンスが含まれます。

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


