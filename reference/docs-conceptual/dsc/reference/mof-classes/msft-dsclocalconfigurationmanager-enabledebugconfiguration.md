---
ms.date: 07/17/2020
ms.topic: reference
title: EnableDebugConfiguration メソッド
description: EnableDebugConfiguration メソッド
ms.openlocfilehash: 536366e6e1627a249f3bc2dc19bfd8ff3de42117
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644776"
---
# <a name="enabledebugconfiguration-method"></a>EnableDebugConfiguration メソッド

DSC リソースのデバッグを有効にします。

## <a name="syntax"></a>構文

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a>パラメーター

**BreakAll** \[in\] リソース スクリプトのすべての行にブレークポイントを設定します。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>解説

これは静的メソッドです。

## <a name="requirements"></a>必要条件

**MOF:** DscCore.mof

**名前空間** :Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
