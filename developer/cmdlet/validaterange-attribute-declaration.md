---
title: ValidateRange 属性の宣言 |Microsoft Docs
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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067112"
---
# <a name="validaterange-attribute-declaration"></a>ValidateRange 属性の宣言

ValidateRange 属性には、コマンドレット パラメーターの引数の最小値と最大値 (範囲) を指定します。 この属性は、Windows PowerShell 関数でも使用できます。

## <a name="syntax"></a>構文

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a>パラメーター

`MinRange` ([System.Object](/dotnet/api/system.object)) が必要です。 許容される最小値を指定します。

`MaxRange` ([System.Object](/dotnet/api/system.object)) が必要です。 許容される最大値を指定します。

## <a name="remarks"></a>コメント

- Windows PowerShell ランタイム構築エラーをスローするときの値、`MinRange`パラメーターがの値より大きい、`MaxRange`パラメーター。

- Windows PowerShell ランタイムには、次の条件で検証エラーがスローされます。

    - 引数の値がより小さい`MinRange`制限より大きいか、`MaxRange`制限します。

    - 同じ型の引数がありませんが、`MinRange`と`MaxRange`パラメーター。

- ValidateRange 属性を定義した、 [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)クラス。

## <a name="see-also"></a>参照

[System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
