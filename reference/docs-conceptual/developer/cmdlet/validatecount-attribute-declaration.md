---
title: ValidateCount 属性の宣言 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.openlocfilehash: c013a354ee339bd14508fe30549673bc79d5c616
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786324"
---
# <a name="validatecount-attribute-declaration"></a>ValidateCount 属性の宣言

ValidateCount 属性では、コマンドレットパラメーターに許可される引数の最小数と最大数を指定します。

## <a name="syntax"></a>構文

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a>パラメーター

`MinLength`([System.string][]) が必要です。 引数の最小数を指定します。

`MaxLength`([System.string][]) が必要です。 引数の最大数を指定します。

## <a name="remarks"></a>解説

- この属性を宣言する方法の詳細については、「[引数カウントを検証する方法][]」を参照してください。

- この属性が呼び出されない場合、対応するコマンドレットパラメーターには任意の数の引数を指定できます。

- Windows PowerShell ランタイムは、次の状況でエラーをスローします。

  - `MinLength`属性と `MaxLength` 属性のパラメーターが、system.string [System.Int32][]型ではありません。

  - 属性パラメーターの値 `MaxLength` が、属性パラメーターの値未満です `MinLength` 。

- ValidateCount 属性は、 [system.string クラスに][]よって定義されています。

## <a name="see-also"></a>参照

[System. Automation. ValidateCountAttribute][]

[引数カウントを検証する方法][]

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)][]

[引数カウントを検証する方法]: how-to-validate-an-argument-count.md
[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System. Automation. ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
