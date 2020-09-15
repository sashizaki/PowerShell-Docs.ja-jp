---
ms.date: 07/17/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: SendConfigurationApply メソッド
ms.openlocfilehash: 9b684790e5a7d6c7bdf074caca6040e13807f1ca
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464317"
---
# <a name="sendconfigurationapply-method"></a>SendConfigurationApply メソッド

構成ドキュメントを管理ノードに送信し、構成エージェントを使用して構成を適用します。

## <a name="syntax"></a>構文

```mof
uint32 SendConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
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

**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
