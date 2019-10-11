---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: ApplyConfiguration メソッド
ms.openlocfilehash: 0425b9a7db37e421830ba37da8f5c0a4877a1b72
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953459"
---
# <a name="applyconfiguration-method"></a>ApplyConfiguration メソッド

構成エージェントを使用して、保留中の構成を適用します。

保留中の構成がない場合は、現在の構成を再適用します。

## <a name="syntax"></a>構文

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a>パラメーター

*force* \[in\] **true** の場合、保留中の構成があっても、現在の構成が再適用されます。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>コメント

これは静的メソッドです。

## <a name="requirements"></a>要件

**MOF:** DscCore.mof

**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
