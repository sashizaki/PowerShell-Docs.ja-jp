---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの PerformRequiredConfigurationChecks メソッド
ms.openlocfilehash: b92eefb7fbea6d96afa31f6b802ba10fe20d4103
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078438"
---
# <a name="performrequiredconfigurationchecks-method-of-the-msftdsclocalconfigurationmanager-class"></a>MSFT_DSCLocalConfigurationManager クラスの PerformRequiredConfigurationChecks メソッド

タスク スケジューラを使用して、整合性チェックを開始します。

## <a name="syntax"></a>構文

```mof
uint32 PerformRequiredConfigurationChecks(
  [in] uint32 Flags
);
```

## <a name="parameters"></a>パラメーター

*Flags* \[in\] 実行する整合性チェックの種類を指定するビットマスク。 次の値が有効です。これらの値はビット単位の **OR** 演算で組み合わせることもできます。

|値 |説明 |
|:--- |:---|
|**1** | 通常の整合性チェックです。 |
|**2** | 再起動後に、整合性チェックを続行します。 この値は、他の値と組み合わせないでください。 |
|**4** | 構成は、ノード用のメタ構成で指定されたプル サーバーからプルされる必要があります。 値を **5** にするには、常に **1** と組み合わせる必要があります。 |
|**8** | レポート サーバーにステータスを送信します。 |

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>コメント

これは静的メソッドです。

## <a name="requirements"></a>要件

**MOF:** DscCore.mof

**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)