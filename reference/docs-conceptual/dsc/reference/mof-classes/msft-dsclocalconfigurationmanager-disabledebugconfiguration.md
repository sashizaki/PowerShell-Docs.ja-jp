---
ms.date: 07/14/2020
ms.topic: reference
title: DisableDebugConfiguration メソッド
description: DisableDebugConfiguration メソッド
ms.openlocfilehash: 6894f86d9626ca03f93477477f573f45a5de4c49
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648993"
---
# <a name="disabledebugconfiguration-method"></a>DisableDebugConfiguration メソッド

DSC リソースのデバッグを無効にします。

## <a name="syntax"></a>構文

```mof
uint32 DisableDebugConfiguration();
```

## <a name="parameters"></a>パラメーター

このメソッドにはパラメーターはありません。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>解説

これは静的メソッドです。

## <a name="requirements"></a>必要条件

**MOF:** DscCore.mof

**名前空間** : Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>参照

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
