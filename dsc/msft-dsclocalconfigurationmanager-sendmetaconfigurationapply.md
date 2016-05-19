---
DCS.appliesToProduct: 'WindowsServer\_Dev'
Description: '構成エージェントを制御するために使用するローカル構成マネージャーの設定を設定します。'
MS-HAID: 'cimwin32a.MSFT_DSCLocalConfigurationManager\_sendmetaconfigurationapply'
MSHAttr: 'PreferredLib:/library'
title: 'MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド'
---

# MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド

構成エージェントを制御するために使用するローカル構成マネージャーの設定を設定します。

構文
------

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

パラメーター
----------

*ConfigurationData* \[in\]  
構成用の環境データ。

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


