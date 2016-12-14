---
title: "MSFT_DSCLocalConfigurationManager クラスの RemoveConfiguration メソッド"
ms.date: 2016-05-16
keywords: PowerShell, DSC
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
ms.openlocfilehash: 4f3d74949d98e3ab3f5136303e229c23ed903c5d
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
translationtype: HT
---
# <a name="removeconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a>MSFT_DSCLocalConfigurationManager クラスの RemoveConfiguration メソッド

構成ファイルを削除します。

<a name="syntax"></a>構文
------

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

<a name="parameters"></a>パラメーター
----------

*Stage* \[in\]  
削除する構成ドキュメントを指定します。 次の値が有効です。

|値 |説明 |
|:--- |:---|
|**1** | **現在**の構成ドキュメント (current.mof)。 |
|**2** | **保留中**の構成ドキュメント (pending.mof)。  |
|**4** | **以前**の構成ドキュメント (previous.mof)。 |

*Force* \[in\]  
**true** の場合、構成を強制的に削除します。

## <a name="return-value"></a>戻り値
------------

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>コメント

これは静的メソッドです。

## <a name="requirements"></a>要件
------------
>**MOF:** DscCore.mof

>**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration


## <a name="see-also"></a>関連項目


[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)


 

 



