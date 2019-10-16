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
ms.openlocfilehash: ffc45f6b80a2b7ed22f27d083d042b1de7f353f6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369231"
---
# <a name="validatecount-attribute-declaration"></a>ValidateCount 属性の宣言

ValidateCount 属性では、コマンドレットパラメーターに許可される引数の最小数と最大数を指定します。

## <a name="syntax"></a>構文

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a>パラメーター

`MinLength` ([System.string][]) が必要です。 引数の最小数を指定します。

`MaxLength` ([System.string][]) が必要です。 引数の最大数を指定します。

## <a name="remarks"></a>コメント

- この属性を宣言する方法の詳細については、「[引数カウントを検証する方法][]」を参照してください。

- この属性が呼び出されない場合、対応するコマンドレットパラメーターには任意の数の引数を指定できます。

- Windows PowerShell ランタイムは、次の状況でエラーをスローします。

    - @No__t-0 および `MaxLength` 属性パラメーター[System.string][]system.string ではありません。

    - @No__t-0 属性パラメーターの値が、`MinLength` 属性パラメーターの値未満です。

- ValidateCount 属性は、 [System. Automation. ValidateCountAttribute][]よって定義されています。

## <a name="see-also"></a>参照

[System. Automation. ValidateCountAttribute][]

[引数カウントを検証する方法][]

[Windows PowerShell コマンドレットの記述][]

[引数カウントを検証する方法]: how-to-validate-an-argument-count.md
[Windows PowerShell コマンドレットの記述]: writing-a-windows-powershell-cmdlet.md

[System.string]: /dotnet/api/System.Int32
[System. Automation. ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
