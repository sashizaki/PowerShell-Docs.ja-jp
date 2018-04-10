---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの DisableDebugConfiguration メソッド
ms.openlocfilehash: 9392a721a542c89be8794882a800b374f11ca5fd
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="disabledebugconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a>MSFT_DSCLocalConfigurationManager クラスの DisableDebugConfiguration メソッド

DSC リソースのデバッグを無効にします。

<a name="syntax"></a>構文
------

```mof
uint32 DisableDebugConfiguration();
```

<a name="parameters"></a>パラメーター
----------

このメソッドにはパラメーターはありません。

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