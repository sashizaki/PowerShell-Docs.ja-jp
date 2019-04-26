---
title: ValidateSet 属性の宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidateSet
- ValidateSet attribute, described
- ValidateSet attribute
ms.assetid: 4a6f97ab-45b2-4f3d-84d4-30acf8e074d0
caps.latest.revision: 12
ms.openlocfilehash: b036f39cd01ffe4b4ce7db9627cb6da0d5327190
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067071"
---
# <a name="validateset-attribute-declaration"></a>ValidateSet 属性の宣言

ValidateSetAttribute 属性には、一連のコマンドレット パラメーターの引数に指定できる値を指定します。 この属性は、Windows PowerShell 関数でも使用できます。

この属性を指定すると、Windows PowerShell ランタイムがコマンドレット パラメーターに指定された引数が指定された要素セット内の要素と一致するかどうかを決定します。 コマンドレットは、パラメーターの引数には、set 内の要素が一致する場合にのみ実行されます。 一致が検出されない場合は、Windows PowerShell ランタイムによってエラーがスローされます。

## <a name="syntax"></a>構文

```csharp
[ValidateSetAttribute(params string[] validValues)]
[ValidateSetAttribute(params string[] validValues, Named Parameters)]
```

#### <a name="parameters"></a>パラメーター

`ValidValues` ([System.String](/dotnet/api/System.String)) が必要です。 有効なパラメーターの要素の値を指定します。 次の例では、要素を 1 つまたは複数の要素を指定する方法を示します。

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

`IgnoreCase` ([System.Boolean](/dotnet/api/System.Boolean)) という名前のパラメーター (省略可能)。 既定値`true`ケースが無視されることを示します。 値`false`コマンドレットは、大文字小文字を区別します。

## <a name="remarks"></a>コメント

- この属性は、パラメーターごと 1 回だけ使用できます。

- パラメーターの値が配列の場合、配列の各要素は属性のセットの要素と一致する必要があります。

- ValidateSetAttribute 属性を定義した、 [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)クラス。

## <a name="see-also"></a>参照

[System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
