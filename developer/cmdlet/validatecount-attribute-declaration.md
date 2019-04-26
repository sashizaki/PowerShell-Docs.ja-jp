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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067180"
---
# <a name="validatecount-attribute-declaration"></a>ValidateCount 属性の宣言

ValidateCount 属性には、コマンドレット パラメーターの許可されている引数の最小値と最大数を指定します。

## <a name="syntax"></a>構文

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a>パラメーター

`MinLength` ([System.Int32][]) が必要です。 引数の最小数を指定します。

`MaxLength`([System.Int32][]) が必要です。 引数の最大数を指定します。

## <a name="remarks"></a>コメント

- この属性を宣言する方法の詳細については、次を参照してください。[引数の数を検証する方法][]します。

- この属性がない呼び出されると、コマンドレットの対応するパラメーターに任意の数の引数のことができます。

- Windows PowerShell ランタイムには、次の条件下でエラーがスローされます。

    - `MinLength`と`MaxLength`型の属性のパラメーターがない[System.Int32][]します。

    - 値、`MaxLength`属性パラメーターは、の値より小さい、`MinLength`属性パラメーター。

- ValidateCount 属性を定義した、 [System.Management.Automation.ValidateCountAttribute][]クラス。

## <a name="see-also"></a>参照

[System.Management.Automation.ValidateCountAttribute][]

[引数の数を検証する方法][]

[Windows PowerShell コマンドレットの記述][]

[引数の数を検証する方法]: how-to-validate-an-argument-count.md
[Windows PowerShell コマンドレットの記述]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
