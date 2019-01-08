---
ms.date: 08/27/2018
keywords: PowerShell, コマンドレット
title: コマンドに関する情報の取得
ms.assetid: 56f8e5b4-d97c-4e59-abbe-bf13e464eb0d
ms.openlocfilehash: 7af83e3a0e776d96e580b442430357b4ea063a72
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403313"
---
# <a name="getting-information-about-commands"></a>コマンドに関する情報の取得

PowerShell の `Get-Command` は、現在のセッションで使用できるコマンドを取得します。
`Get-Command` コマンドレットを実行すると、次のような出力が表示されます。

```output
CommandType     Name                    Version    Source
-----------     ----                    -------    ------
Cmdlet          Add-Computer            3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Add-Content             3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Add-History             3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Add-JobTrigger          1.1.0.0    PSScheduledJob
Cmdlet          Add-LocalGroupMember    1.0.0.0    Microsoft.PowerShell.LocalAccounts
Cmdlet          Add-Member              3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Add-PSSnapin            3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Add-Type                3.1.0.0    Microsoft.PowerShell.Utility
...
```

この出力は、**cmd.exe** のヘルプの出力に似ている、内部コマンドの表形式の概要です。 上記の `Get-Command` コマンドの出力の抜粋では、表示されているすべてのコマンドのコマンドレットは CommandType です。 コマンドレットは、PowerShell の組み込みのコマンドの種類です。 この種類は、おおまかに言うと、**cmd.exe** の `dir` および `cd` のようなコマンドや、バッシュのような Unix シェルの組み込みコマンドと同じです。

`Get-Command` コマンドレットには、各コマンドレットの構文を返す **Syntax** パラメーターがあります。 次の例は、`Get-Help` コマンドレットの構文を取得する方法を示しています。

```powershell
Get-Command Get-Help -Syntax
```

```output
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Full] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]

Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Detailed] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]

Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Examples] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]

Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Parameter <String>] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]
```

## <a name="displaying-available-command-by-type"></a>使用可能なコマンドを種類別に表示する

`Get-Command` コマンドは、現在のセッションのコマンドレットのみを一覧表示します。 PowerShell は、実際にはその他のいくつかの種類のコマンドをサポートします。

- エイリアス
- 関数
- スクリプト

実行可能な外部ファイル、または登録されているファイル タイプのハンドラーを持つ外部ファイルも、コマンドとして分類されます。

セッション内のすべてのコマンドを取得するには、次のように入力します。

```powershell
Get-Command *
```

この一覧には、検索パスの外部コマンドが含まれるため、何千もの項目が含まれることがあります。
コマンド セットを削減して表示する方が実用的です。

> [!NOTE]
> アスタリスク (\*) は、PowerShell コマンドの引数のワイルドカードによるマッチングに使用されます。 \* は、「1 つ以上の任意の文字に一致する」という意味です。 `Get-Command a*` を入力すると、文字 "a" で始まるコマンドをすべて検索できます。 **cmd.exe** のワイルドカードのマッチングとは異なり、PowerShell のワイルドカードは、ピリオドもマッチングします。

その他の種類のネイティブ コマンドを取得するには、`Get-Command` の **CommandType** パラメーターを使用します。
コマンドレットを実行して、返されるクォーラム リソースに関する情報を確認できます。

コマンドの割り当て済みのニックネームであるコマンドのエイリアスを取得するには、次のように入力します。

```powershell
Get-Command -CommandType Alias
```

現在のセッションの関数を取得するには、次のように入力します。

```powershell
Get-Command -CommandType Function
```

PowerShell の検索パス内のスクリプトを表示するには、次のように入力します。

```powershell
Get-Command -CommandType Script
```