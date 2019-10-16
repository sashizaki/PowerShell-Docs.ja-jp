---
title: パラメーターとしてのプロパティの宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f71ea35d-cff5-4e44-a5c6-3a747ed4c4d9
caps.latest.revision: 9
ms.openlocfilehash: 6f6640afb15b3608669538f9b5f53d7a8a5c380d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365751"
---
# <a name="declaring-properties-as-parameters"></a>パラメーターとしてプロパティを宣言する

このトピックでは、コマンドレットのパラメーターを宣言する前に理解しておく必要がある基本的な情報について説明します。

コマンドレットクラス内のコマンドレットのパラメーターを宣言するには、各パラメーターを表すパブリックプロパティを定義し、1つまたは複数のパラメーター属性を各プロパティに追加します。 Windows PowerShell ランタイムは、パラメーター属性を使用して、コマンドレットパラメーターとしてプロパティを識別します。 パラメーター属性を宣言するための基本構文は、`[Parameter()]` です。

必須パラメーターとして定義されたプロパティの例を次に示します。

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

ここでは、パラメーターについて覚えておくべきことをいくつか紹介します。

- パラメーターは、明示的にパブリックとしてマークする必要があります。 既定でパブリックに設定されていないパラメーターは、Windows PowerShell ランタイムによって検出されません。

- パラメーターの検証を強化するには、パラメーターを Microsoft .NET Framework 型として定義する必要があります。 たとえば、値のセットから1つの値に制限されているパラメーターは、列挙型として定義する必要があります。 Uniform Resource Identifier (URI) 値を受け取るパラメーターは、system.string 型にする必要が[あります。](/dotnet/api/System.Uri)

- 自由形式のテキストプロパティ以外のすべてに対して、基本的な文字列パラメーターを使用しないようにします。

- 任意の数のパラメーターセットにパラメーターを追加できます。 パラメーターセットの詳細については、「[コマンドレットパラメーターセット](./cmdlet-parameter-sets.md)」を参照してください。

Windows PowerShell には、すべてのコマンドレットで自動的に使用できる一連の共通パラメーターも用意されています。 これらのパラメーターとそのエイリアスの詳細については、「[コマンドレットの共通パラメーター](./common-parameter-names.md)」を参照してください。

## <a name="see-also"></a>参照

[コマンドレットの共通パラメーター](./common-parameter-names.md)

[コマンドレットパラメーターの型](./types-of-cmdlet-parameters.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
