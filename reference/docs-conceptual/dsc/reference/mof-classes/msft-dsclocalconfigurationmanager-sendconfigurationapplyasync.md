---
ms.date: 07/17/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: SendConfigurationApplyAsync メソッド
ms.openlocfilehash: 4cfac5edb5fed94ee69deb98d7aa6be56b51c5b3
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463739"
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

**ConfigurationData** \[in\] 構成用の環境データ。

**force** \[in\] **true** の場合、構成を強制的に中止します。

**jobId** \[in\] 構成を送信するジョブの ID です。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>解説

これは静的メソッドです。

## <a name="requirements"></a>必要条件

**MOF:** DscCore.mof

**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
