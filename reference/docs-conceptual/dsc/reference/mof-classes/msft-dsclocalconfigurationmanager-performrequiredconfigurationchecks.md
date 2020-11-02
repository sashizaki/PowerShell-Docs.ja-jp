---
ms.date: 07/17/2020
ms.topic: reference
title: PerformRequiredConfigurationChecks メソッド
description: PerformRequiredConfigurationChecks メソッド
ms.openlocfilehash: c5e847cda6376f4266cc771dc947032a279e25f4
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650820"
---
# <a name="performrequiredconfigurationchecks-method"></a>PerformRequiredConfigurationChecks メソッド

タスク スケジューラを使用して、整合性チェックを開始します。

## <a name="syntax"></a>構文

```mof
uint32 PerformRequiredConfigurationChecks(
  [in] uint32 Flags
);
```

## <a name="parameters"></a>パラメーター

**Flags** \[in\] 実行する整合性チェックの種類を指定するビットマスク。 次の値が有効です。これらの値はビット単位の **OR** 演算で組み合わせることもできます。

|値 |説明 |
|:--- |:---|
|**1** | 通常の整合性チェックです。 |
|**2** | 再起動後に、整合性チェックを続行します。 この値は、他の値と組み合わせないでください。 |
|**4** | 構成は、ノード用のメタ構成で指定されたプル サーバーからプルされる必要があります。 値を **5** にするには、常に **1** と組み合わせる必要があります。 |
|**8** | レポート サーバーにステータスを送信します。 |

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>解説

これは静的メソッドです。

## <a name="requirements"></a>必要条件

**MOF:** DscCore.mof

**名前空間** :Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
