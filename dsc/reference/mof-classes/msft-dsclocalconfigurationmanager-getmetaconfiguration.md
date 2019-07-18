---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: GetMetaConfiguration メソッド
ms.openlocfilehash: bd280cb8ebd7b0522e4e01cbd24bd9bdcfddf4c2
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734436"
---
# <a name="getmetaconfiguration-method"></a>GetMetaConfiguration メソッド

構成エージェントを制御するために使用するローカル構成マネージャーの設定を取得します。

## <a name="syntax"></a>構文

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

## <a name="parameters"></a>パラメーター

*MetaConfiguration* \[out\] 制御が戻ったとき、設定を定義する **MSFT_DSCMetaConfiguration** クラスの埋め込みインスタンスが含まれます。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>コメント

これは静的メソッドです。

## <a name="requirements"></a>要件

**MOF:** DscCore.mof

**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
