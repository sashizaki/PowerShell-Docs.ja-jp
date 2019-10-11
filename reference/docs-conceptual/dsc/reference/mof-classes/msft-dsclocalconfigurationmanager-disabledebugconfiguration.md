---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DisableDebugConfiguration メソッド
ms.openlocfilehash: e3eab98c734b3fd1593ceb2b5d4b40fa69a3bf97
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71955059"
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

## <a name="remarks"></a>コメント

これは静的メソッドです。

## <a name="requirements"></a>要件

**MOF:** DscCore.mof

**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
