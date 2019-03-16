---
title: コマンドレットのパラメーターの種類 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6602730d-3892-4656-80c7-7bca2d14337f
caps.latest.revision: 14
ms.openlocfilehash: f5781c0c03aca41d01a44598a9a8c00d6d21d2fd
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059577"
---
# <a name="types-of-cmdlet-parameters"></a>コマンドレット パラメーターの種類

このトピックでは、コマンドレットで宣言するパラメーターのさまざまな種類について説明します。 コマンドレットのパラメーターは、位置指定、名前付き、必要な省略可能なまたはスイッチ パラメーター。

## <a name="positional-and-named-parameters"></a>位置指定引数と名前付きパラメーター

すべてのコマンドレット パラメーターは、名前付きまたは位置指定パラメーターです。 名前付きパラメーターは、コマンドレットを呼び出すときに、引数とパラメーターの名前を入力することが必要です。 位置指定パラメーターは、相対的な順序で引数を入力することにのみ必要です。 システムは、名前のない最初の引数を位置指定の最初のパラメーターにマップします。 システムでは、名前のない 2 番目の引数を 2 番目のパラメーターの名前のない、という具合です。 既定では、すべてのコマンドレット パラメーターは名前付きパラメーター。

名前付きパラメーターを定義するには、省略、`Position`キーワード、**パラメーター**属性の宣言では、次のパラメーターの宣言で示すようにします。

```csharp
[Parameter(ValueFromPipeline=true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

位置指定パラメーターを定義するには、追加、`Position`パラメーターにキーワード属性宣言と位置を指定します。 次の例で、`UserName`位置 0 の位置指定パラメーターとしてパラメーターを宣言します。 つまり、呼び出しの最初の引数を自動的にこのパラメーターにバインドされます。

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
> 適切なコマンドレットのデザインは、ユーザーが、コマンドレットを実行すると、パラメーター名を入力する必要があるないように、最も使用頻度のパラメーターを位置指定パラメーターとして宣言することをお勧めします。

位置指定引数と名前付きパラメーターは、1 つの引数またはコンマで区切られた複数の引数を受け取ります。 複数の引数は、パラメーターが文字列の配列などのコレクションを受け取る場合にのみ許可されます。 同じコマンドレットで位置指定引数と名前付きパラメーターを混在させることがあります。 この場合、システムが最初に、名前付き引数を取得し、名前なし引数を位置指定パラメーターのし、残りをマップしよう。

次のコマンドは、1 つまたは複数の引数のパラメーターを指定できます、さまざまな方法を示して、`Get-Command`コマンドレット。 最後の 2 つのサンプルで **-名前**ためにを指定する必要はありません、`Name`パラメーターは位置指定パラメーターとして定義されます。

```powershell
Get-Command -Name get-service
Get-Command -Name get-service,set-service
Get-Command get-service
Get-Command get-service,set-service
```

## <a name="mandatory-and-optional-parameters"></a>必須および省略可能なパラメーター

必須またはオプションのパラメーターとしてコマンドレットのパラメーターを定義することもできます。 (必須のパラメーター指定してください、Windows PowerShell ランタイムは、コマンドレットを呼び出す前に。)既定では、パラメーターは省略可能として定義されます。

必須のパラメーターを定義するには、追加、`Mandatory`キーワード パラメーターに属性宣言、およびに設定`true`、次のパラメーターの宣言で示すようにします。

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

オプションのパラメーターを定義するには、省略、`Mandatory`キーワード、**パラメーター**属性の宣言では、次のパラメーターの宣言で示すようにします。

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="switch-parameters"></a>スイッチ パラメーター

Windows PowerShell では、 [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)に値を持つパラメーターを定義することができますの種類が自動的に設定`false`コマンドレットはときに、パラメーターが指定されていない場合と呼ばれる。 可能であれば、ブール型パラメーターの代わりにスイッチ パラメーターを使用します。

次の例を検討してください。 既定では、いくつかの Windows PowerShell コマンドレットは、パイプラインに出力オブジェクトを渡さないでください。 ただし、これらのコマンドレットがある、`PassThru`スイッチ パラメーターを既定の動作をオーバーライドします。 場合、`PassThru`これらのコマンドレットを呼び出すときに、パラメーターを指定すると、コマンドレットは、パイプラインに出力オブジェクトを返します。

かどうか、パラメーターの既定値を設定する必要があります。`true`呼び出しでは、パラメーターが指定されていない、ときには、パラメーターの意味を反転することを検討してください。 サンプルでは、パラメーター属性にブール値を設定するのではなく`true`、プロパティとして宣言、 [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)を入力し、するパラメーターの既定値を設定`false`.

スイッチ パラメーターを定義するには、プロパティとしてを宣言、 [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)の次の例に示すように入力します。

```csharp
[Parameter(Position = 1)]
public SwitchParameter GoodBye
{
  get { return goodbye; }
  set { goodbye = value; }
}
private bool goodbye;
```

指定されているときに、パラメーターを操作するコマンドレットのいずれかの入力処理メソッドは、次の構造を使用します。

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

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
