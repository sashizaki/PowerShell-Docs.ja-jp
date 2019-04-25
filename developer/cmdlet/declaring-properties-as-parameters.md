---
title: パラメーターとしてプロパティの宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f71ea35d-cff5-4e44-a5c6-3a747ed4c4d9
caps.latest.revision: 9
ms.openlocfilehash: 6f6640afb15b3608669538f9b5f53d7a8a5c380d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068268"
---
# <a name="declaring-properties-as-parameters"></a>パラメーターとしてプロパティを宣言する

このトピックでは、コマンドレットのパラメーターを宣言する前に理解する必要があります、基本的な情報を提供します。

コマンドレット クラス内でのコマンドレットのパラメーターを宣言するには、各パラメーターを表すパブリック プロパティを定義し、各プロパティに 1 つまたは複数のパラメーター属性を追加します。 Windows PowerShell ランタイムでは、パラメーターの属性を使用して、コマンドレット パラメーターとしてプロパティを識別します。 パラメーター属性を宣言するための基本構文は`[Parameter()]`します。

必要なパラメーターとして定義されているプロパティの例を次に示します。

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

パラメーターに関する注意事項があります。

- パラメーターをする必要があります明示的にパブリックと指定します。 内部にパブリックの既定としてマークされていないと、Windows PowerShell ランタイムでは見つからないされるパラメーター。

- パラメーターより優れたパラメーターの検証を提供する Microsoft .NET Framework 型として定義する必要があります。 たとえば、値の中から 1 つの値に制限されているパラメーターは、列挙型として定義する必要があります。 型の Uniform Resource Identifier (URI) の値を受け取るパラメーターは必ず[System.Uri](/dotnet/api/System.Uri)します。

- 以外のすべての自由形式テキストのプロパティの基本的な文字列パラメーターを回避します。

- パラメーターは、任意の数のパラメーター セットを追加できます。 パラメーター セットの詳細については、次を参照してください。[コマンドレット パラメーター設定](./cmdlet-parameter-sets.md)します。

Windows PowerShell には、すべてのコマンドレットを自動的に利用できる共通のパラメーターのセットも提供します。 これらのパラメーターと、エイリアスの詳細については、次を参照してください。[コマンドレットに共通のパラメーター](./common-parameter-names.md)します。

## <a name="see-also"></a>参照

[コマンドレットの一般的なパラメーター](./common-parameter-names.md)

[コマンドレットのパラメーターの型](./types-of-cmdlet-parameters.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
