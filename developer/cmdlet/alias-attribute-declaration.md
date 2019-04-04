---
title: エイリアス属性の宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Alias attribute
- attributes, Alias
- Alias attribute, described
ms.assetid: d0df3a46-b1cc-42b9-beb1-e16bce254007
caps.latest.revision: 10
ms.openlocfilehash: 4d20672c5181c994c1b53624f6c42a301db11f26
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855048"
---
# <a name="alias-attribute-declaration"></a>エイリアス属性の宣言

Alias 属性は、コマンドレット パラメーターに異なる名前を指定できます。 エイリアスは、パラメーター名のショートカットを提供するために使用できますか、さまざまなシナリオに適した別の名を指定することができます。

## <a name="syntax"></a>構文

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a>パラメーター

`aliasName` (String[] など必須。 一連のコマンドレット パラメーターのコンマ区切りのエイリアス名を指定します。

## <a name="remarks"></a>コメント

- Alias 属性は、コマンドレット パラメーターを指定すると、パラメーターの属性で使用されます。 これらの属性を宣言する方法の詳細については、[コマンドレット パラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)を参照してください。

- 各エイリアス名をコマンドレット内で一意である必要があります。 Windows PowerShell は、重複するエイリアス名にはチェックされません。

- Alias 属性は、コマンドレットの各パラメーターの 1 回使用されます。

- Alias 属性は、 [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute)クラス。

## <a name="see-also"></a>参照

[パラメーターのエイリアス](./parameter-aliases.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
