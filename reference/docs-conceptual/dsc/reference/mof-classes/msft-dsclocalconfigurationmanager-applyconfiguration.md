---
ms.date: 07/14/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: ApplyConfiguration メソッド
ms.openlocfilehash: bec74ccd6f75448484adfd26bf8a4af4e224eb3f
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463841"
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

### <a name="force"></a>force

**true** の場合、保留中の構成があっても、現在の構成が再適用されます。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>解説

これは静的メソッドです。

## <a name="requirements"></a>必要条件

**MOF:** DscCore.mof

**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
