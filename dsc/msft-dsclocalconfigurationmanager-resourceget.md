---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの ResourceGet メソッド"
ms.openlocfilehash: 7d8b185c49778253dcb4e983ad948775c4cb0842
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="resourceget-method-of-the-msftdsclocalconfigurationmanager-class"></a>MSFT_DSCLocalConfigurationManager クラスの ResourceGet メソッド

DSC リソースの **Get** メソッドを直接呼び出します。

<a name="syntax"></a>構文
------

```mof
uint32 ResourceGet(
  [in]  string           ResourceType,
  [in]  string           ModuleName,
  [in]  uint8            resourceProperty[],
  [out] OMI_BaseResource configurations
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

*configurations* \[out\]  
制御が戻ったとき、その構成の埋め込みインスタンスが含まれます。

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


 

 



