---
ms.date: 07/17/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: RollBack メソッド
ms.openlocfilehash: 301b8926d2ebf1ebe524f52a67928d34e26d860e
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464334"
---
# <a name="rollback-method"></a>RollBack メソッド

構成を以前のバージョンにロールバックします。

## <a name="syntax"></a>構文

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a>パラメーター

**configurationNumber** \[in\] 要求された構成を指定します。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>解説

これは静的メソッドです。

## <a name="requirements"></a>必要条件

**MOF:** DscCore.mof

**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
