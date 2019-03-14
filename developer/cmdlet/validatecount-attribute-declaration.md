---
title: ValidateCount 属性の宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.assetid: 516af1ef-2c2e-408d-84bc-865f5bccf761
caps.latest.revision: 11
ms.openlocfilehash: 4e0be34b6f7a56dcf02a4381de4d2a5d08db14df
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794445"
---
# <a name="validatecount-attribute-declaration"></a>ValidateCount 属性の宣言

ValidateCount 属性には、コマンドレット パラメーターの許可されている引数の最小値と最大数を指定します。

## <a name="syntax"></a>構文

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a>パラメーター

`MinLength` ([System.Int32](/dotnet/api/System.Int32)) が必要です。 引数の最小数を指定します。

`MaxLength`([System.Int32](/dotnet/api/System.Int32)) が必要です。 引数の最大数を指定します。

## <a name="remarks"></a>コメント

- この属性を宣言する方法の詳細については、次を参照してください。[入力検証規則の宣言方法](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b)します。

- この属性がない呼び出されると、コマンドレットの対応するパラメーターに任意の数の引数のことができます。

- Windows PowerShell ランタイムには、次の条件下でエラーがスローされます。

    - `MinLength`と`MaxLength`型の属性のパラメーターがない[System.Int32](/dotnet/api/System.Int32)します。

    - 値、`MaxLength`属性パラメーターは、の値より小さい、`MinLength`属性パラメーター。

- ValidateCount 属性を定義した、 [System.Management.Automation.Validatecount](/dotnet/api/System.Management.Automation.ValidateCount)クラス。

## <a name="see-also"></a>参照

[System.Management.Automation.Validatecount](/dotnet/api/System.Management.Automation.ValidateCount)

[入力の検証規則を宣言する方法](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
