---
title: OutputType 属性の宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a97a98ee-ffc0-42f0-a9a6-b0717b39c798
caps.latest.revision: 5
ms.openlocfilehash: 7aa6fa407e509a31c4066c4f73ae01b02b2f338c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365341"
---
# <a name="outputtype-attribute-declaration"></a>OutputType 属性の宣言

`OutputType` 属性は、コマンドレット、関数、またはスクリプトによって返される .NET Framework 型を識別します。

## <a name="syntax"></a>構文

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a>パラメーター

型 (`string[]` または `Type[]`) が必要です。 コマンドレット関数またはスクリプトによって返される型を指定します。

ParameterSetName (string []) 省略可能。 `type` パラメーターで指定された型を返すパラメーターセットを指定します。

providerCmdlet オプション。 `type` パラメーターで指定された型を返すプロバイダーコマンドレットを指定します。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
