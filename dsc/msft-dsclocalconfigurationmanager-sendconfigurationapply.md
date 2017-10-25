---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApply メソッド"
ms.openlocfilehash: 9552fd5b5feb862fbe8ef95a7746776e7fe2f5c8
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="sendconfigurationapply-method-of-the-msftdsclocalconfigurationmanager-class"></a>MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApply メソッド

構成ドキュメントを管理ノードに送信し、構成エージェントを使用して構成を適用します。

<a name="syntax"></a>構文
------

```mof
uint32 SendConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

<a name="parameters"></a>パラメーター
----------

*ConfigurationData* \[in\]  
構成用の環境データ。

*force* \[in\]  
**true** の場合、構成を強制的に中止します。

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


 

 



