---
ms.date: 07/17/2020
ms.topic: reference
title: RemoveConfiguration メソッド
description: RemoveConfiguration メソッド
ms.openlocfilehash: d5988ac014c457407c56a097c9a376427376eb3f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650727"
---
# <a name="removeconfiguration-method"></a>RemoveConfiguration メソッド

構成ファイルを削除します。

## <a name="syntax"></a>構文

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a>パラメーター

**Stage** \[in\] 削除する構成ドキュメントを指定します。 有効な値は、

|値 |説明 |
|:--- |:---|
|**1** | **現在** の構成ドキュメント (current.mof)。 |
|**2** | **保留中** の構成ドキュメント (pending.mof)。  |
|**4** | **以前** の構成ドキュメント (previous.mof)。 |

*Force* \[in\] **true** の場合、構成を強制的に削除します。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>解説

これは静的メソッドです。

## <a name="requirements"></a>必要条件

**MOF:** DscCore.mof

**名前空間** :Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
