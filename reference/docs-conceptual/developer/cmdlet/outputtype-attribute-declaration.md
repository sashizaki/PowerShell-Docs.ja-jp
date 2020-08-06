---
title: OutputType 属性の宣言 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a4cc874031bba092cfef6041bef0e19e6af3f09c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786545"
---
# <a name="outputtype-attribute-declaration"></a>OutputType 属性の宣言

属性は、 `OutputType` コマンドレット、関数、またはスクリプトによって返される .NET Framework 型を識別します。

## <a name="syntax"></a>構文

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a>パラメーター

型 ( `string[]` または `Type[]` ) が必要です。 コマンドレット関数またはスクリプトによって返される型を指定します。

ParameterSetName (string []) 省略可能。 パラメーターで指定した型を返すパラメーターセットを指定し `type` ます。

providerCmdlet オプション。 パラメーターで指定した型を返すプロバイダーコマンドレットを指定し `type` ます。

## <a name="see-also"></a>参照

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
