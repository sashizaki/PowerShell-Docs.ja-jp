---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: StopConfiguration メソッド
ms.openlocfilehash: e1de175032a3bddf11af218bc4a15bdbe554a9d5
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953359"
---
# <a name="stopconfiguration-method"></a>StopConfiguration メソッド

進行中の構成の変更を停止します。

## <a name="syntax"></a>構文

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a>パラメーター

*force* \[in\] **true** の場合、構成を強制的に中止します。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>コメント

これは静的メソッドです。

## <a name="requirements"></a>要件

**MOF:** DscCore.mof

**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
