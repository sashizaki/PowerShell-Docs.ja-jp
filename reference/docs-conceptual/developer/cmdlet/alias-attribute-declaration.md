---
title: Alias 属性宣言 |Microsoft Docs
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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72370021"
---
# <a name="alias-attribute-declaration"></a>エイリアス属性の宣言

Alias 属性を使用すると、ユーザーはコマンドレットパラメーターに別の名前を指定できます。 エイリアスを使用してパラメーター名のショートカットを指定することも、さまざまなシナリオに適した異なる名前を指定することもできます。

## <a name="syntax"></a>構文

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a>パラメーター

`aliasName` (String []) が必要です。 コマンドレットパラメーターのコンマ区切りのエイリアス名のセットを指定します。

## <a name="remarks"></a>コメント

- Alias 属性は、コマンドレットパラメーターを指定するときに、Parameter 属性と共に使用されます。 これらの属性を宣言する方法の詳細については、「[コマンドレットのパラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)」を参照してください。

- 各エイリアス名は、コマンドレット内で一意である必要があります。 Windows PowerShell では、重複するエイリアス名は確認されません。

- Alias 属性は、コマンドレットのパラメーターごとに1回使用されます。

- Alias 属性は、system.servicemodel[属性](/dotnet/api/System.Management.Automation.AliasAttribute)クラスによって定義されます。

## <a name="see-also"></a>参照

[パラメーターの別名](./parameter-aliases.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
