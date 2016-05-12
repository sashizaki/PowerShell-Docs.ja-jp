---
DCS.appliesToProduct: 'WindowsServer\_Dev'
Description: '構成ドキュメントを管理ノードに送信し、Get メソッドを使って構成エージェントを使用し、構成を適用します。'
MS-HAID: 'cimwin32a.MSFT_DSCLocalConfigurationManager\_getconfiguration'
MSHAttr: 'PreferredLib:/library'
title: 'MSFT_DSCLocalConfigurationManager クラスの GetConfiguration メソッド'
---

# MSFT_DSCLocalConfigurationManager クラスの GetConfiguration メソッド

構成ドキュメントを管理ノードに送信し、構成エージェントの **Get** メソッドを使用して構成を適用します。

構文
------

```mof
uint32 GetConfiguration(
  [in]  uint8            configurationData[],
  [out] OMI_BaseResource configurations[]
);
```

パラメーター
----------

*configurationData* \[in\]  
送信する構成データを指定します。

*configurations* \[out\]  
制御が戻ったとき、その構成の埋め込みインスタンスが含まれます。

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


