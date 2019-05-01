---
ms.date: 08/27/2018
keywords: PowerShell, コマンドレット
title: 変数を使用したオブジェクトの保存
ms.assetid: b1688d73-c173-491e-9ba6-6d0c1cc852de
ms.openlocfilehash: d166ec58dc658c1b134030c9a9592249ee40d4f5
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086546"
---
# <a name="using-variables-to-store-objects"></a>変数を使用したオブジェクトの保存

PowerShell ではオブジェクトを操作します。 PowerShell では、変数として認識される名前付きオブジェクトを作成できます。
変数名には、アンダースコア文字と任意の英数字を含めることができます。 PowerShell で使用される場合、変数は常に、\$ 文字の後ろに変数名を追加して指定されます。

## <a name="creating-a-variable"></a>変数の作成

次のように有効な変数名を入力することで、変数を作成できます。

```
PS> $loc
PS>
```

`$loc` に値がないため、この例では結果を返しません。 変数の作成と値の割り当てを同一の手順で行うことができます。 PowerShell では、変数が存在しない場合にのみ、変数を作成します。
それ以外の場合、指定された値を既存の変数に割り当てます。 次の例では、変数 `$loc` に現在の場所を格納します。

```powershell
$loc = Get-Location
```

このコマンドを入力した場合、PowerShell では出力を表示しません。 PowerShell は 'Get-Location' の出力を `$loc` に送信します。 PowerShell では、割り当てもリダイレクトもされていないデータが、画面に送信されます。 次のように `$loc` を入力すると、現在の場所が表示されます。

```
PS> $loc

Path
----
C:\temp
```

`Get-Member` を使用して変数の内容に関する情報を表示できます。 `Get-Member` は、`Get-Location` からの出力と同様に、`$loc` が **PathInfo** オブジェクトであることを示しています。

```powershell
PS> $loc | Get-Member -MemberType Property

   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   System.String Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {...
ProviderPath Property   System.String ProviderPath {get;}
```

## <a name="manipulating-variables"></a>変数の操作

PowerShell には変数を操作するためのコマンドがいくつか用意されています。 次のように入力すると、完全な一覧が読みやすい形式で表示されます。

```powershell
Get-Command -Noun Variable | Format-Table -Property Name,Definition -AutoSize -Wrap
```

また、PowerShell では、複数のシステム定義変数を作成します。 `Remove-Variable` コマンドレットを使用して、現在のセッションから、PowerShell によって制御されない変数を削除できます。 すべての変数をクリアするには、次のコマンドを入力します。

```powershell
Remove-Variable -Name * -Force -ErrorAction SilentlyContinue
```

前のコマンドを実行した後、`Get-Variable` コマンドレットでは PowerShell システム変数を表示します。

また、PowerShell では、変数ドライブも作成します。 次の例を使用して、変数ドライブを使ってすべての PowerShell 変数を表示します。

```powershell
Get-ChildItem variable:
```

## <a name="using-cmdexe-variables"></a>cmd.exe 変数の使用

PowerShell では、**cmd.exe** など、任意の Windows プロセスに利用できる同じ環境変数を使用できます。 これらの変数は `env:` という名前のドライブ経由で公開されます。 これらの変数を表示するには、次のコマンドを入力します。

```powershell
Get-ChildItem env:
```

標準の `*-Variable` コマンドレットは、環境変数を操作するように設計されていません。 環境変数は、`env:` ドライブ プレフィックスを使用してアクセスされます。 たとえば、**cmd.exe** の **%SystemRoot%** 変数には、オペレーティング システムのルート ディレクトリ名が含まれます。 PowerShell では、`$env:SystemRoot` を使用して同じ値にアクセスします。

```
PS> $env:SystemRoot
C:\WINDOWS
```

さらに、PowerShell 内から環境変数を作成および変更することもできます。 PowerShell の環境変数は、オペレーティング システムの他の場所で使用される環境変数と同じ規則に従います。 次の例では、新しい環境変数を作成します。

```powershell
$env:LIB_PATH='/usr/local/lib'
```

必須ではありませんが、環境変数名には、すべて大文字を使用するのが一般的です。
