---
title: "MSFT_DSCLocalConfigurationManager クラスの ResourceTest メソッド"
ms.date: 2016-05-16
keywords: PowerShell, DSC
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
ms.openlocfilehash: 4129c83dd0b72159cbf1d47c037b9d462ca45f0e
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
translationtype: HT
---
# <a name="resourcetest-method-of-the-msftdsclocalconfigurationmanager-class"></a>MSFT_DSCLocalConfigurationManager クラスの ResourceTest メソッド

DSC リソースの **Test** メソッドを直接呼び出します。

<a name="syntax"></a>構文
------

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

<a name="parameters"></a>パラメーター
----------

*ResourceType* \[in\]  
呼び出すリソースの名前。

*ModuleName* \[in\]  
呼び出すリソースを含むモジュールの名前。

*resourceProperty* \[in\]  
ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。 リソースのプロパティと種類を検出するには、[Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx) コマンドレットを使用します。

*InDesiredState* \[out\]  
ターゲット ノードが目的の状態にある場合、制御が戻るときに、このプロパティは **true** に設定されます。

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


 

 



