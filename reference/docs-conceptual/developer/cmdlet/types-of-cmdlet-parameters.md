---
title: コマンドレットパラメーターの種類 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6602730d-3892-4656-80c7-7bca2d14337f
caps.latest.revision: 14
ms.openlocfilehash: f5781c0c03aca41d01a44598a9a8c00d6d21d2fd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369311"
---
# <a name="types-of-cmdlet-parameters"></a>コマンドレット パラメーターの種類

このトピックでは、コマンドレットで宣言できるさまざまな種類のパラメーターについて説明します。 コマンドレットのパラメーターには、位置指定、名前付き、必須、オプション、またはスイッチのパラメーターを指定できます。

## <a name="positional-and-named-parameters"></a>位置指定パラメーターと名前付きパラメーター

すべてのコマンドレットパラメーターには、名前付きパラメーターまたは位置指定パラメーターがあります。 名前付きパラメーターを使用するには、コマンドレットを呼び出すときに、パラメーターの名前と引数を入力する必要があります。 位置指定パラメーターでは、引数を相対順序で入力するだけで済みます。 次に、最初の名前のない引数が最初の位置指定パラメーターにマップされます。 2番目の無名の引数が、2番目の無名のパラメーターにマップされます。 既定では、すべてのコマンドレットパラメーターは名前付きパラメーターです。

名前付きパラメーターを定義するには、次のパラメーター宣言に示すように、 **parameter**属性の宣言で `Position` キーワードを省略します。

```csharp
[Parameter(ValueFromPipeline=true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

位置指定パラメーターを定義するには、パラメーター属性の宣言に `Position` キーワードを追加し、位置を指定します。 次の例では、`UserName` パラメーターが位置0の位置指定パラメーターとして宣言されています。 これは、呼び出しの最初の引数がこのパラメーターに自動的にバインドされることを意味します。

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

> [!NOTE]
> 適切なコマンドレットの設計では、コマンドレットの実行時にユーザーがパラメーター名を入力する必要がないように、最も使用されるパラメーターを位置指定パラメーターとして宣言することをお勧めします。

位置指定パラメーターと名前付きパラメーターは、単一の引数またはコンマで区切られた複数の引数を受け取ります。 パラメーターが文字列の配列などのコレクションを受け入れる場合にのみ、複数の引数を指定できます。 同じコマンドレットで、位置指定パラメーターと名前付きパラメーターを混在させることができます。 この場合、システムはまず名前付き引数を取得してから、残りの名前なし引数を位置指定パラメーターにマップしようとします。

次のコマンドは、`Get-Command` コマンドレットのパラメーターに1つ以上の引数を指定するさまざまな方法を示しています。 最後の2つのサンプルでは、`Name` パラメーターが位置パラメーターとして定義されているため、 **-name**を指定する必要はありません。

```powershell
Get-Command -Name get-service
Get-Command -Name get-service,set-service
Get-Command get-service
Get-Command get-service,set-service
```

## <a name="mandatory-and-optional-parameters"></a>必須のパラメーターと省略可能なパラメーター

コマンドレットのパラメーターは、必須パラメーターまたは省略可能なパラメーターとして定義することもできます。 (Windows PowerShell ランタイムがコマンドレットを呼び出す前に、必須パラメーターを指定する必要があります)。 既定では、パラメーターはオプションとして定義されます。

必須パラメーターを定義するには、次のパラメーター宣言に示すように、Parameter 属性宣言に `Mandatory` キーワードを追加し、それを `true`に設定します。

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

省略可能なパラメーターを定義するには、次のパラメーター宣言に示すように、 **parameter**属性の宣言で `Mandatory` キーワードを省略します。

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="switch-parameters"></a>スイッチパラメーター

Windows PowerShell には、コマンドレットの呼び出し時にパラメーターが指定されていない場合に、値が自動的に `false` に設定されるパラメーターを定義できるようにする、 [switchparameter](/dotnet/api/System.Management.Automation.SwitchParameter)型が用意されています。 可能な限り、ブール型パラメーターの代わりにスイッチパラメーターを使用してください。

次の例について考えてみましょう。 既定では、いくつかの Windows PowerShell コマンドレットは、出力オブジェクトをパイプラインの下位に渡しません。 ただし、これらのコマンドレットには、既定の動作をオーバーライドする `PassThru` スイッチパラメーターがあります。 これらのコマンドレットを呼び出すときに `PassThru` パラメーターを指定した場合、コマンドレットは出力オブジェクトをパイプラインに返します。

パラメーターが呼び出しで指定されていない場合に、パラメーターの既定値 `true` を持つ必要がある場合は、パラメーターの意味を逆にすることを検討してください。 サンプルの場合は、parameter 属性を `true`のブール値に設定するのではなく、プロパティを system.string[パラメーター](/dotnet/api/System.Management.Automation.SwitchParameter)の型として宣言し、パラメーターの既定値を `false`に設定します。

スイッチパラメーターを定義するには、次の例に示すように、プロパティを system.string[パラメーター](/dotnet/api/System.Management.Automation.SwitchParameter)の型として宣言します。

```csharp
[Parameter(Position = 1)]
public SwitchParameter GoodBye
{
  get { return goodbye; }
  set { goodbye = value; }
}
private bool goodbye;
```

パラメーターを指定したときにコマンドレットを実行するには、入力処理メソッドのいずれかで次の構造体を使用します。

```csharp
protected override void ProcessRecord()
{
  WriteObject("Switch parameter test: " + userName + ".");
  if(goodbye)
  {
    WriteObject(" Goodbye!");
  }
} // End ProcessRecord
```

## <a name="see-also"></a>関連項目

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
