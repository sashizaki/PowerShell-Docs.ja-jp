---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの TestConfiguration メソッド
ms.openlocfilehash: 7815d458a9a67639a31c917510097212d104eb8a
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="testconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a>MSFT_DSCLocalConfigurationManager クラスの TestConfiguration メソッド

構成ドキュメントを管理ノードに送信し、そのドキュメントに対して現在の構成を検証します。

<a name="syntax"></a>構文
------

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

<a name="parameters"></a>パラメーター
----------

*configurationData* \[in\] 構成のための環境データ。

*InDesiredState* \[out\] 制御が戻ったとき、管理ノードが構成ドキュメントで指定された状態であるかどうかを示します。

*ResourcesInDesiredState* \[out\] 制御が戻ったとき、目的の状態にあるリソースを指定する、**MSFT_ResourceInDesiredState** クラスの埋め込みインスタンスが含まれます。

*ResourcesNotInDesiredState* \[out\] 制御が戻ったとき、目的の状態ではないリソースを指定する、**MSFT_ResourceNotInDesiredState** クラスの埋め込みインスタンスが含まれます。

## <a name="return-value"></a>戻り値
------------

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>コメント

これは静的メソッドです。

## <a name="requirements"></a>要件
------------
>**MOF:** DscCore.mof

>**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration


## <a name="see-also"></a>関連項目


[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)