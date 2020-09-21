---
ms.date: 07/17/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: TestConfiguration メソッド
ms.openlocfilehash: 0611c4d5543c49b879bef9b60cafdd0b055c9b86
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464300"
---
# <a name="testconfiguration-method"></a>TestConfiguration メソッド

構成ドキュメントを管理ノードに送信し、そのドキュメントに対して現在の構成を検証します。

## <a name="syntax"></a>構文

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

## <a name="parameters"></a>パラメーター

**configurationData** \[in\] 構成のための環境データです。

**InDesiredState** \[out\] 制御が戻ったとき、マネージド ノードが構成ドキュメントで指定された状態であるかどうかを示します。

**ResourcesInDesiredState** \[out\] 制御が戻ったとき、目的の状態にあるリソースを指定する、**MSFT_ResourceInDesiredState** クラスの埋め込みインスタンスが含まれます。

**ResourcesNotInDesiredState** \[out\] 制御が戻ったとき、目的の状態ではないリソースを指定する、**MSFT_ResourceNotInDesiredState** クラスの埋め込みインスタンスが含まれます。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>解説

これは静的メソッドです。

## <a name="requirements"></a>必要条件

**MOF:** DscCore.mof

**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
