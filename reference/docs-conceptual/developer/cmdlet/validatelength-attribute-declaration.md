---
title: ValidateLength Attribute 宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateLength attribute, described
- attributes, ValidateLength
- ValidateLength attribute
ms.assetid: 82fe3a35-a94b-4bc1-ad9e-dfc5f1e788b3
caps.latest.revision: 13
ms.openlocfilehash: a25fa2410fcc6803563573596af1bc99052c3ffa
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369181"
---
# <a name="validatelength-attribute-declaration"></a>ValidateLength 属性の宣言

ValidateLength 属性は、コマンドレットパラメーター引数の文字数の最小値と最大値を指定します。 この属性は、Windows PowerShell の関数でも使用できます。

## <a name="syntax"></a>構文

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a>パラメーター

`MinLength` ([Int32](/dotnet/api/System.Int32)) が必要です。 許容される最小文字数を指定します。

`MaxLength` ([Int32](/dotnet/api/System.Int32)) が必要です。 許容される最大文字数を指定します。

## <a name="remarks"></a>コメント

- この属性を宣言する方法の詳細については、「[入力検証規則を宣言する方法](./how-to-validate-parameter-input.md)」を参照してください。

- この属性が使用されていない場合、対応するパラメーター引数は任意の長さにすることができます。

- Windows PowerShell ランタイムは、次の状況でエラーをスローします。

    - `MaxLength` 属性パラメーターの値が `MinLength` 属性パラメーターの値より小さい場合。

    - `MaxLength` 属性パラメーターが0に設定されている場合。

    - 引数が文字列でない場合。

- ValidateLength 属性は、 [Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)クラスによって定義されます。

## <a name="see-also"></a>参照

[Validatelengthattribute (システム管理)](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
