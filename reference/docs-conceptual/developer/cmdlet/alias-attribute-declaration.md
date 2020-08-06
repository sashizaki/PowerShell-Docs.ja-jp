---
title: Alias 属性宣言 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- Alias attribute
- attributes, Alias
- Alias attribute, described
ms.openlocfilehash: 4c1ff34a244611173ca919a44d6598189b19dc98
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782414"
---
# <a name="alias-attribute-declaration"></a>エイリアス属性の宣言

Alias 属性を使用すると、ユーザーはコマンドレットパラメーターに別の名前を指定できます。 エイリアスを使用してパラメーター名のショートカットを指定することも、さまざまなシナリオに適した異なる名前を指定することもできます。

## <a name="syntax"></a>構文

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a>パラメーター

`aliasName`(文字列 [])必須。 コマンドレットパラメーターのコンマ区切りのエイリアス名のセットを指定します。

## <a name="remarks"></a>解説

- Alias 属性は、コマンドレットパラメーターを指定するときに、Parameter 属性と共に使用されます。 これらの属性を宣言する方法の詳細については、「[コマンドレットのパラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)」を参照してください。

- 各エイリアス名は、コマンドレット内で一意である必要があります。 Windows PowerShell では、重複するエイリアス名は確認されません。

- Alias 属性は、コマンドレットのパラメーターごとに1回使用されます。

- Alias 属性は、system.servicemodel[属性](/dotnet/api/System.Management.Automation.AliasAttribute)クラスによって定義されます。

## <a name="see-also"></a>参照

[パラメーターのエイリアス](./parameter-aliases.md)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
