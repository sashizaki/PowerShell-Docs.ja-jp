---
ms.date: 07/17/2020
ms.topic: reference
title: GetConfigurationResultOutput メソッド
description: GetConfigurationResultOutput メソッド
ms.openlocfilehash: 7c885109b3078189b7ac653733a5fb24db66312e
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644713"
---
# <a name="getconfigurationresultoutput-method"></a>GetConfigurationResultOutput メソッド

特定のジョブに関連する構成エージェントの出力を取得します。

## <a name="syntax"></a>構文

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

## <a name="parameters"></a>パラメーター

**jobId** \[in\] 出力データを取得するジョブの ID です。

**resumeOutputBookmark** \[in\] 出力が前のブックマークからの続きとなるように指定します。

**output** \[out\] 指定されたジョブの出力です。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>解説

これは静的メソッドです。

## <a name="requirements"></a>必要条件

**MOF:** DscCore.mof

**名前空間** :Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
