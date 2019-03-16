---
title: コマンドレット属性 |Microsoft Docs
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
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055174"
---
# <a name="cmdlet-attributes"></a>コマンドレットの属性

Windows PowerShell では、独自のコード内でその機能を実装することがなく、コマンドレットに共通の機能を追加するのに使用できるいくつかの属性を定義します。 これには、コマンドレット クラスでコマンドレットとしてパブリック プロパティを識別するパラメーターの属性がコマンドレットによって返される .NET Framework 型を指定する OutputType 属性として Microsoft .NET Framework クラスを識別するコマンドレットの属性が含まれますパラメーター、および詳細。

## <a name="in-this-section"></a>このセクションの内容

[コマンドレット コード内の属性](./attributes-in-cmdlet-code.md)コマンドレットのコードで属性を使用する利点について説明します。

[属性型](./attribute-types.md)装飾できるは、コマンドレット クラスを別の属性について説明します。

[属性の宣言にエイリアス](./alias-attribute-declaration.md)コマンドレットのパラメーター名のエイリアスを定義する方法について説明します。

[コマンドレット属性宣言](./cmdlet-attribute-declaration.md)コマンドレットとして .NET Framework クラスを定義する方法について説明します。

[資格情報の属性宣言](./credential-attribute-declaration.md)への入力を文字列に変換するためのサポートを追加する方法について説明します、 [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)オブジェクト。

[OutputType 属性宣言](./outputtype-attribute-declaration.md)コマンドレットによって返される .NET Framework 型を指定する方法について説明します。

[パラメーター属性宣言](./parameter-attribute-declaration.md)コマンドレットのパラメーターを定義する方法について説明します。

[属性の宣言は ValidateCount](./validatecount-attribute-declaration.md)パラメーターの引数の数が許可されているかを定義する方法について説明します。

[属性の宣言は ValidateLength](./validatelength-attribute-declaration.md) (文字) でパラメーターの引数の長さを定義する方法について説明します。

[ValidatePattern 属性宣言](./validatepattern-attribute-declaration.md)パラメーターの引数の有効なパターンを定義する方法について説明します。

[属性の宣言は ValidateRange](./validaterange-attribute-declaration.md)パラメーターの引数の有効な範囲を定義する方法について説明します。

[属性の宣言は ValidateSet](./validateset-attribute-declaration.md)パラメーターの引数の値を定義する方法について説明します。

## <a name="reference"></a>参照先

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
