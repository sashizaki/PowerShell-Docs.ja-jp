---
title: ValidateLength 属性の宣言 |Microsoft Docs
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
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67735098"
---
# <a name="validatelength-attribute-declaration"></a>ValidateLength 属性の宣言

ValidateLength 属性には、コマンドレット パラメーターの引数の文字の最小値と最大数を指定します。 この属性は、Windows PowerShell 関数でも使用できます。

## <a name="syntax"></a>構文

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a>パラメーター

`MinLength` ([System.Int32](/dotnet/api/System.Int32)) が必要です。 許可される文字の最小数を指定します。

`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) が必要です。 許可される文字の最大数を指定します。

## <a name="remarks"></a>コメント

- この属性を宣言する方法の詳細については、次を参照してください。[入力検証規則の宣言方法](./how-to-validate-parameter-input.md)します。

- この属性を使用しない場合、任意の長さの対応するパラメーターの引数を引き起こすことができます。

- Windows PowerShell ランタイムには、次の条件下でエラーがスローされます。

    - ときの値、`MaxLength`属性パラメーターは、の値より小さい、`MinLength`属性パラメーター。

    - ときに、`MaxLength`属性のパラメーターが 0 に設定します。

    - ときに、引数は文字列ではありません。

- ValidateLength 属性を定義した、 [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)クラス。

## <a name="see-also"></a>参照

[System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
