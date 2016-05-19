---
DCS.appliesToProduct: 'WindowsServer\_Dev'
Description: '構成ドキュメントを管理ノードに送信し、構成エージェントの使用を開始して構成を適用します。 GetConfigurationResultOutput を使用して、結果の出力を取得します。'
MS-HAID: 'cimwin32a.MSFT_DSCLocalConfigurationManager\_sendconfigurationapplyasync'
MSHAttr: 'PreferredLib:/library'
title: 'MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApplyAsync メソッド'
---

# MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApplyAsync メソッド

構成ドキュメントを管理ノードに非同期的に送信し、構成エージェントを使用して構成を適用します。

構文
------

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

パラメーター
----------

*ConfigurationData* \[in\]  
構成用の環境データ。

*force* \[in\]  
**true** の場合、構成を強制的に中止します。

*jobId* \[in\]  
構成を送信するジョブの ID です。

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


