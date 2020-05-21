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
ms.openlocfilehash: 560fa105ac3f93ae6334df0112f5290dfa20576c
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692009"
---
# <a name="validaterange-attribute-declaration"></a>ValidateRange 属性の宣言

ValidateRange 属性は、コマンドレットパラメーター引数の最小値と最大値 (範囲) を指定します。 この属性は、Windows PowerShell の関数でも使用できます。

## <a name="syntax"></a>構文

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a>パラメーター

`MinRange`([System.object](/dotnet/api/system.object)) が必要です。 許容される最小値を指定します。

`MaxRange`([System.object](/dotnet/api/system.object)) が必要です。 許容される最大値を指定します。

## <a name="remarks"></a>解説

- パラメーターの値 `MinRange` がパラメーターの値よりも大きい場合、Windows PowerShell ランタイムは構築エラーをスローし `MaxRange` ます。

- Windows PowerShell ランタイムは、次の条件下で検証エラーをスローします。

  - 引数の値が制限よりも小さいか、または制限を超えている場合 `MinRange` `MaxRange` 。

  - 引数がおよびパラメーターと同じ型ではない場合 `MinRange` `MaxRange` 。

- ValidateRange 属性は、system.servicemodel[属性](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)クラスによって定義されます。

## <a name="see-also"></a>参照

[System. Automation. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
