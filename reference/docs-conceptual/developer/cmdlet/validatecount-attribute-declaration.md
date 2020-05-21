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
ms.openlocfilehash: 3cae95fab30a4abe4e544ed5cb7dadc9f4debf02
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692373"
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
