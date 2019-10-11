---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: SendConfigurationApplyAsync メソッド
ms.openlocfilehash: c0e6dc9418757ee719e848fa8e7006dd73d91ad8
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953379"
---
# <a name="sendconfigurationapplyasync-method"></a>SendConfigurationApplyAsync メソッド

構成ドキュメントを管理ノードに非同期的に送信し、構成エージェントを使用して構成を適用します。

## <a name="syntax"></a>構文

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

## <a name="parameters"></a>パラメーター

*ConfigurationData* \[in\] 構成用の環境データ。

*force* \[in\] **true** の場合、構成を強制的に中止します。

*jobId* \[in\] 構成を送信するジョブの ID です。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>コメント

これは静的メソッドです。

## <a name="requirements"></a>要件

**MOF:** DscCore.mof

**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
