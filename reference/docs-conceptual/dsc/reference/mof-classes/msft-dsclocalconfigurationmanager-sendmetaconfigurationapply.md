---
ms.date: 07/17/2020
ms.topic: reference
title: SendMetaConfigurationApply メソッド
description: SendMetaConfigurationApply メソッド
ms.openlocfilehash: 27c58819c0249ace011c475e500e565e5daed9bb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648960"
---
# <a name="sendmetaconfigurationapply-method"></a>SendMetaConfigurationApply メソッド

構成エージェントを制御するために使用するローカル構成マネージャーの設定を設定します。

## <a name="syntax"></a>構文

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a>パラメーター

**ConfigurationData** \[in\] 構成用の環境データ。

**force** \[in\] **true** の場合、構成を強制的に中止します。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>解説

これは静的メソッドです。

## <a name="requirements"></a>必要条件

**MOF:** DscCore.mof

**名前空間** :Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
