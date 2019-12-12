---
title: ValidateRange Attribute 宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateRange, described
- ValidateRange attribute
- attributes, ValidateRange
ms.assetid: 1f8066e6-e5d3-4f4e-8948-a90af5dace82
caps.latest.revision: 11
ms.openlocfilehash: 155a406b9855c435041fe175ac7d983a4b4eb8b7
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369131"
---
# <a name="validaterange-attribute-declaration"></a>ValidateRange 属性の宣言

ValidateRange 属性は、コマンドレットパラメーター引数の最小値と最大値 (範囲) を指定します。 この属性は、Windows PowerShell の関数でも使用できます。

## <a name="syntax"></a>構文

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a>パラメーター

`MinRange` ([system.object](/dotnet/api/system.object)) が必要です。 許容される最小値を指定します。

`MaxRange` ([system.object](/dotnet/api/system.object)) が必要です。 許容される最大値を指定します。

## <a name="remarks"></a>コメント

- `MinRange` パラメーターの値が `MaxRange` パラメーターの値よりも大きい場合、Windows PowerShell ランタイムは構築エラーをスローします。

- Windows PowerShell ランタイムは、次の条件下で検証エラーをスローします。

    - 引数の値が `MinRange` 制限より小さい場合、または `MaxRange` 制限を超える場合。

    - 引数が `MinRange` と `MaxRange` パラメーターと同じ型ではない場合。

- ValidateRange 属性は、system.servicemodel[属性](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)クラスによって定義されます。

## <a name="see-also"></a>参照

[System. Automation. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
