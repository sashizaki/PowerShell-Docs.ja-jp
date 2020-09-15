---
ms.date: 07/14/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DisableDebugConfiguration メソッド
ms.openlocfilehash: 52d55ff6b1fd126482bbaa9480efc131ab2f100c
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463756"
---
# <a name="disabledebugconfiguration-method"></a>DisableDebugConfiguration メソッド

DSC リソースのデバッグを無効にします。

## <a name="syntax"></a>構文

```mof
uint32 DisableDebugConfiguration();
```

## <a name="parameters"></a>パラメーター

このメソッドにはパラメーターはありません。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>解説

これは静的メソッドです。

## <a name="requirements"></a>必要条件

**MOF:** DscCore.mof

**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>参照

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
