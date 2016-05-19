---
DCS.appliesToProduct: 'WindowsServer\_Dev'
Description: 'デバッグ DSC 構成を有効にします。'
MS-HAID: 'cimwin32a.msft\_dsclocalconfigurationmanager\_enabledebugconfiguration'
MSHAttr: 'PreferredLib:/library'
title: 'MSFT_DSCLocalConfigurationManager クラスの EnableDebugConfiguration メソッド'
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
 

 





<!--HONumber=Apr16_HO2-->


