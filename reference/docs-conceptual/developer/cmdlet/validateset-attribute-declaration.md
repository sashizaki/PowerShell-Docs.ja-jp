---
title: ValidateSet 属性宣言 |Microsoft Docs
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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364281"
---
# <a name="validateset-attribute-declaration"></a>ValidateSet 属性の宣言

ValidateSetAttribute 属性は、コマンドレットパラメーターの引数として使用可能な値のセットを指定します。 この属性は、Windows PowerShell の関数でも使用できます。

この属性を指定すると、Windows PowerShell ランタイムは、コマンドレットパラメーターの指定された引数が、指定された要素セット内の要素と一致するかどうかを判断します。 コマンドレットは、パラメーター引数が set 内の要素と一致する場合にのみ実行されます。 一致するものが見つからない場合は、Windows PowerShell ランタイムによってエラーがスローされます。

## <a name="syntax"></a>構文

```csharp
[ValidateSetAttribute(params string[] validValues)]
[ValidateSetAttribute(params string[] validValues, Named Parameters)]
```

#### <a name="parameters"></a>パラメーター

`ValidValues` ([system.string](/dotnet/api/System.String)) が必要です。 有効なパラメーター要素の値を指定します。 次のサンプルは、1つまたは複数の要素を指定する方法を示しています。

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

`IgnoreCase` ([system.string](/dotnet/api/System.Boolean)) 省略可能な名前付きパラメーター。 `true` の既定値は、大文字小文字を区別しないことを示します。 `false` の値を指定すると、コマンドレットで大文字と小文字が区別されます。

## <a name="remarks"></a>コメント

- この属性は、パラメーターごとに1回だけ使用できます。

- パラメーター値が配列の場合は、配列のすべての要素が属性セットの要素と一致している必要があります。

- ValidateSetAttribute 属性は、 [ValidateSetAttribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)クラスによって定義されます。

## <a name="see-also"></a>関連項目

[Validatesetattribute (システム管理)](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
