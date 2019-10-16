---
title: コマンドレットの属性 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes [PowerShell SDK]
- attributes [PowerShell SDK], described
ms.assetid: d3f4f652-d929-4c27-9358-9baa390a094c
caps.latest.revision: 14
ms.openlocfilehash: 326cd408e86402974569fc76d5e473be5a56f0b6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369961"
---
# <a name="cmdlet-attributes"></a>コマンドレットの属性

Windows PowerShell では、コマンドレットに共通機能を追加するために使用できるいくつかの属性が定義されています。独自のコード内でその機能を実装する必要はありません。 これには、コマンドレットクラスとして Microsoft .NET Framework クラスを識別するコマンドレット属性、コマンドレットによって返される .NET Framework 型を指定する OutputType 属性、パブリックプロパティをコマンドレットとして識別するパラメーター属性が含まれます。パラメーターなど。

## <a name="in-this-section"></a>このセクションの内容

[コマンドレットコードの属性](./attributes-in-cmdlet-code.md)コマンドレットコードで属性を使用する利点について説明します。

[属性の型](./attribute-types.md)コマンドレットクラスを修飾できるさまざまな属性について説明します。

[エイリアス属性の宣言](./alias-attribute-declaration.md)コマンドレットパラメーター名のエイリアスを定義する方法について説明します。

[コマンドレットの属性宣言](./cmdlet-attribute-declaration.md).NET Framework クラスをコマンドレットとして定義する方法について説明します。

[Credential 属性の宣言](./credential-attribute-declaration.md)文字列入力を system.string オブジェクトに変換するためのサポートを追加する方法について説明[します。](/dotnet/api/System.Management.Automation.PSCredential)

[OutputType 属性の宣言](./outputtype-attribute-declaration.md)コマンドレットによって返される .NET Framework 型を指定する方法について説明します。

[パラメーター属性の宣言](./parameter-attribute-declaration.md)コマンドレットのパラメーターを定義する方法について説明します。

[Validatecount 属性の宣言](./validatecount-attribute-declaration.md)パラメーターで許容される引数の数を定義する方法について説明します。

[ValidateLength 属性の宣言](./validatelength-attribute-declaration.md)パラメーター引数の長さ (文字数) を定義する方法について説明します。

[Validatepattern 属性の宣言](./validatepattern-attribute-declaration.md)パラメーター引数の有効なパターンを定義する方法について説明します。

[ValidateRange 属性の宣言](./validaterange-attribute-declaration.md)パラメーター引数の有効な範囲を定義する方法について説明します。

[Validateset 属性の宣言](./validateset-attribute-declaration.md)パラメーター引数に使用できる値を定義する方法について説明します。

## <a name="reference"></a>参照先

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
