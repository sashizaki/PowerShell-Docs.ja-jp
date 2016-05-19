---
DCS.appliesToProduct: 'WindowsServer\_Dev'
Description: '構成状態の履歴を取得します。'
MS-HAID: 'cimwin32a.MSFT_DSCLocalConfigurationManager\_getconfigurationstatus'
MSHAttr: 'PreferredLib:/library'
title: 'MSFT_DSCLocalConfigurationManager クラスの GetConfigurationStatus メソッド'
---

# MSFT_DSCLocalConfigurationManager クラスの GetConfigurationStatus メソッド

構成状態の履歴を取得します。

構文
------

```mof
uint32 GetConfigurationStatus(
  [in]  boolean                     All,
  [out] MSFT_DSCConfigurationStatus configurationStatus[]
);
```

パラメーター
----------

*All* \[in\]  
**true** の場合、コンピューターで実行中のすべての構成についての情報が返されます
(構成の適用や整合性チェックも含む)。

*configurationStatus* \[out\]  
制御が戻ったとき、設定を定義する **MSFT_DSCConfigurationStatus** クラスの埋め込みインスタンスが含まれます。

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


