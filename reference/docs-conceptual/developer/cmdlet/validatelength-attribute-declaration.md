---
title: ValidateLength Attribute 宣言 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateLength attribute, described
- attributes, ValidateLength
- ValidateLength attribute
ms.openlocfilehash: 7145dde55e79eeea6e3ceb91dfc1c93043a8857c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786307"
---
# <a name="validatelength-attribute-declaration"></a>ValidateLength 属性の宣言

ValidateLength 属性は、コマンドレットパラメーター引数の文字数の最小値と最大値を指定します。 この属性は、Windows PowerShell の関数でも使用できます。

## <a name="syntax"></a>構文

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a>パラメーター

`MinLength`([System.string](/dotnet/api/System.Int32)) が必要です。 許容される最小文字数を指定します。

`MaxLength`([System.string](/dotnet/api/System.Int32)) が必要です。 許容される最大文字数を指定します。

## <a name="remarks"></a>解説

- この属性を宣言する方法の詳細については、「[入力検証規則を宣言する方法](./how-to-validate-parameter-input.md)」を参照してください。

- この属性が使用されていない場合、対応するパラメーター引数は任意の長さにすることができます。

- Windows PowerShell ランタイムは、次の状況でエラーをスローします。

  - `MaxLength`属性パラメーターの値が属性パラメーターの値より小さい場合 `MinLength` 。

  - `MaxLength`属性パラメーターが0に設定されている場合。

  - 引数が文字列でない場合。

- ValidateLength 属性は、 [Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)クラスによって定義されます。

## <a name="see-also"></a>参照

[Validatelengthattribute (システム管理)](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
