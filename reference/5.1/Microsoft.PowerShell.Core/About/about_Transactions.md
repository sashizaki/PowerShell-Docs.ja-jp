---
description: PowerShell でのトランザクション操作の管理方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_transactions?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Transactions
ms.openlocfilehash: 522e0f727754b0b0153571039f3bf3966d0abf20
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222480"
---
# <a name="about-transactions"></a>トランザクションについて

## <a name="short-description"></a>概要

PowerShell でのトランザクション操作の管理方法について説明します。

## <a name="long-description"></a>詳細説明

Powershell 2.0 以降の PowerShell では、トランザクションがサポートされています。 この機能を使用すると、トランザクションを開始して、トランザクションの一部であるコマンドを示すことや、トランザクションをコミットまたはロールバックすることができます。

## <a name="about-transactions"></a>トランザクションについて

PowerShell では、トランザクションは1つ以上のコマンドのセットであり、論理ユニットとして管理されます。 トランザクションを完了 ("コミット済み") できます。これにより、トランザクションの影響を受けたデータが変更されます。 または、トランザクションによって影響を受けるデータが変更されないように、トランザクションを完全に元に戻す ("ロールバック") こともできます。

トランザクション内のコマンドは1つの単位として管理されるので、すべてのコマンドがコミットされるか、すべてのコマンドがロールバックされます。

トランザクションはデータ処理で広く使用されており、特にデータベース操作や財務トランザクションで使用されます。 トランザクションは、コマンドセットの最悪のシナリオでは、すべてが失敗するわけではありませんが、一部のコマンドは正常に実行されますが、他のコマンドは失敗し、破損、false、または解釈不可能な状態になることがあります。

## <a name="transaction-cmdlets"></a>トランザクションのコマンドレット

PowerShell には、トランザクションを管理するためのコマンドレットがいくつか用意されています。

- 開始トランザクション: 新しいトランザクションを開始します。
- トランザクションの使用: コマンドまたは式をトランザクションに追加します。 コマンドでは、トランザクション対応オブジェクトを使用する必要があります。
- 元に戻す-トランザクション: トランザクションによってデータが変更されないように、トランザクションをロールバックします。
- Complete-Transaction: トランザクションをコミットします。 トランザクションの影響を受けたデータは変更されます。
- トランザクションの取得: アクティブなトランザクションに関する情報を取得します。

トランザクションコマンドレットの一覧を表示するには、次のように入力します。

```powershell
get-command *transaction
```

コマンドレットの詳細については、次のように入力してください。

```powershell
get-help use-transaction -detailed
```

## <a name="transaction-enabled-elements"></a>トランザクション対応の要素

トランザクションに参加するには、コマンドレットとプロバイダーの両方でトランザクションがサポートされている必要があります。 この機能は、トランザクションによって影響を受けるオブジェクトに組み込まれています。

PowerShell レジストリプロバイダーは、Windows Vista のトランザクションをサポートしています。 TransactedString オブジェクト (TransactedString) は、PowerShell を実行するすべてのオペレーティングシステムで動作します。

他の PowerShell プロバイダーはトランザクションをサポートできます。 トランザクションをサポートするセッションで PowerShell プロバイダーを検索するには、次のコマンドを使用して、providers の Capabilities プロパティの "transaction" 値を検索します。

```powershell
get-psprovider | where {$_.Capabilities -like "*transactions*"}
```

プロバイダーの詳細については、プロバイダーのヘルプを参照してください。 プロバイダーのヘルプを表示するには、次のように入力します。

```
get-help <provider-name>
```

たとえば、Registry プロバイダーのヘルプを取得するには、次のように入力します。

```powershell
get-help registry
```

## <a name="the-usetransaction-parameter"></a>USETRANSACTION パラメーター

トランザクションをサポートするコマンドレットには、UseTransaction パラメーターがあります。 このパラメーターには、アクティブなトランザクションのコマンドが含まれます。 完全なパラメーター名またはそのエイリアスである "usetx" を使用できます。

パラメーターは、セッションにアクティブなトランザクションが含まれている場合にのみ使用できます。 アクティブなトランザクションが存在しないときに UseTransaction パラメーターを指定してコマンドを入力すると、コマンドは失敗します。

UseTransaction パラメーターを使用してコマンドレットを検索するには、次のように入力します。

```powershell
get-help * -parameter UseTransaction
```

PowerShell core では、PowerShell プロバイダーと連携するように設計されたすべてのコマンドレットがトランザクションをサポートしています。 その結果、プロバイダーのコマンドレットを使用してトランザクションを管理できます。

PowerShell プロバイダーの詳細については、「 [about_Providers](about_Providers.md)」を参照してください。

## <a name="the-transaction-object"></a>トランザクションオブジェクト

トランザクションは、PowerShell でトランザクションオブジェクトである system.string によって表されます。

このオブジェクトには、以下のプロパティがあります。

- RollbackPreference: 現在のトランザクションのロールバック設定が含まれています。 Start-Transaction を使用してトランザクションを開始するときに、ロールバックの設定を設定できます。

  ロールバックの設定によって、トランザクションが自動的にロールバックされる条件が決まります。 有効な値は、エラー、エラーの発生、および Never です。 既定値は Error です。

- Status: トランザクションの現在の状態が含まれます。 有効な値は、"アクティブ"、"コミット"、および "ロールバック" です。

- [登録回数数: トランザクションに対するサブスクライバーの数が含まれます。 別のトランザクションの進行中にトランザクションを開始すると、サブスクライバーがトランザクションに追加されます。 サブスクライバーがトランザクションをコミットすると、サブスクライバーの数が減少します。

## <a name="active-transactions"></a>アクティブなトランザクション

PowerShell では、一度にアクティブなトランザクションは1つだけです。また、アクティブなトランザクションのみを管理できます。 同じセッションで複数のトランザクションを同時に実行することはできますが、最も最近開始されたトランザクションのみがアクティブになります。

このため、トランザクションコマンドレットを使用する場合、特定のトランザクションを指定することはできません。 コマンドは、常にアクティブなトランザクションに適用されます。

これは、Get-Transaction コマンドレットの動作で最も顕著です。 Get-Transaction コマンドを入力すると、Get-Transaction は常に1つのトランザクションオブジェクトのみを取得します。 このオブジェクトは、アクティブなトランザクションを表すオブジェクトです。

別のトランザクションを管理するには、まずアクティブなトランザクションをコミットするか、ロールバックすることによって完了する必要があります。 これを行うと、前のトランザクションが自動的にアクティブになります。 トランザクションは、開始された順番とは逆にアクティブになり、最後に開始されたトランザクションが常にアクティブになります。

## <a name="subscribers-and-independent-transactions"></a>サブスクライバーと独立したトランザクション

別のトランザクションの進行中にトランザクションを開始した場合、既定では、PowerShell は新しいトランザクションを開始しません。 代わりに、現在のトランザクションに "subscriber" を追加します。

トランザクションに複数のサブスクライバーがある場合、任意のポイントで1つの Undo-Transaction コマンドを実行すると、すべてのサブスクライバーのトランザクション全体がロールバックされます。 ただし、トランザクションをコミットするには、すべてのサブスクライバーに対して Complete-Transaction コマンドを入力する必要があります。

トランザクションに対するサブスクライバーの数を調べるには、トランザクションオブジェクトの "参照カウント" プロパティを確認します。 たとえば、次のコマンドでは、Get-Transaction コマンドレットを使用して、アクティブなトランザクションの "/" プロパティの値を取得します。

```powershell
(Get-Transaction).SubscriberCount
```

サブスクライバーの追加は既定の動作です。これは、別のトランザクションの実行中に開始されるトランザクションのほとんどが、元のトランザクションに関連付けられるためです。 一般的なモデルでは、トランザクションを含むスクリプトは、独自のトランザクションを含むヘルパースクリプトを呼び出します。 トランザクションは関連しているため、ロールバックするか、1つの単位としてコミットする必要があります。

ただし、Start-Transaction コマンドレットの独立したパラメーターを使用して、現在のトランザクションから独立したトランザクションを開始できます。

独立したトランザクションを開始すると、Start-Transaction によって新しいトランザクションオブジェクトが作成され、新しいトランザクションがアクティブなトランザクションになります。
元のトランザクションに影響を与えることなく、独立したトランザクションをコミットまたはロールバックできます。

独立したトランザクションが完了 (コミットまたはロールバック) されると、元のトランザクションは再びアクティブなトランザクションになります。

## <a name="changing-data"></a>データの変更

トランザクションを使用してデータを変更する場合、トランザクションの影響を受けるデータは、トランザクションをコミットするまで変更されません。 ただし、トランザクションに含まれていないコマンドでも同じデータを変更できます。

トランザクションを使用して共有データを管理する場合は、この点に注意してください。
通常、データベースには、作業中にデータをロックし、他のユーザーやその他のコマンド、スクリプト、および関数を変更できないようにするメカニズムがあります。

ただし、ロックはデータベースの機能です。 トランザクションに関連付けられていません。 トランザクション対応のファイルシステムまたはその他のデータストアで作業している場合は、トランザクションの進行中にデータを変更できます。

## <a name="examples"></a>例

このセクションの例では、PowerShell レジストリプロバイダーを使用します。このプロバイダーについて理解していることを前提としています。 レジストリプロバイダーの詳細については、「get-help Registry」と入力してください。

### <a name="example-1-committing-a-transaction"></a>例 1: トランザクションをコミットする

トランザクションを作成するには、Start-Transaction コマンドレットを使用します。 次のコマンドは、既定の設定を使用してトランザクションを開始します。

```powershell
start-transaction
```

コマンドをトランザクションに含めるには、コマンドレットの UseTransaction パラメーターを使用します。 既定では、コマンドはトランザクションに含まれていません。

たとえば、次のコマンドは、HKCU: ドライブのソフトウェアキーの現在の場所を設定しますが、トランザクションには含まれていません。

```powershell
cd hkcu:\Software
```

MyCompany キーを作成する次のコマンドは、New-Item コマンドレットの UseTransaction パラメーターを使用して、アクティブなトランザクションにコマンドを含めます。

```powershell
new-item MyCompany -UseTransaction
```

このコマンドは、新しいキーを表すオブジェクトを返しますが、このコマンドはトランザクションの一部であるため、レジストリはまだ変更されていません。

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyCompany                      {}
```

トランザクションをコミットするには、Complete-Transaction コマンドレットを使用します。 常にアクティブなトランザクションに影響するため、トランザクションを指定することはできません。

```powershell
complete-transaction
```

その結果、MyCompany キーがレジストリに追加されます。

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-2-rolling-back-a-transaction"></a>例 2: トランザクションをロールバックする

トランザクションを作成するには、Start-Transaction コマンドレットを使用します。 次のコマンドは、既定の設定を使用してトランザクションを開始します。

```powershell
start-transaction
```

次のコマンドでは、MyOtherCompany キーを作成し、New-Item コマンドレットの UseTransaction パラメーターを使用して、アクティブなトランザクションにコマンドを含めます。

```powershell
new-item MyOtherCompany -UseTransaction
```

このコマンドは、新しいキーを表すオブジェクトを返しますが、このコマンドはトランザクションの一部であるため、レジストリはまだ変更されていません。

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyOtherCompany                 {}
```

トランザクションをロールバックするには、Undo-Transaction コマンドレットを使用します。 常にアクティブなトランザクションに影響するため、トランザクションは指定しません。

```powershell
Undo-transaction
```

その結果、MyOtherCompany キーはレジストリに追加されません。

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-3-previewing-a-transaction"></a>例 3: トランザクションのプレビュー

通常、トランザクションで使用されるコマンドは、データを変更します。 ただし、トランザクション内でデータを取得するため、データを取得するコマンドも便利です。 これにより、トランザクションのコミットによって発生する変更のプレビューが提供されます。

次の例では、Get-ChildItem コマンド (別名は "dir") を使用して、トランザクションの変更をプレビューする方法を示します。

次のコマンドを実行すると、トランザクションが開始されます。

```powershell
start-transaction
```

次のコマンドでは、New-ItemProperty コマンドレットを使用して、MyCompany キーに MyKey レジストリエントリを追加します。 このコマンドは、UseTransaction パラメーターを使用して、コマンドをトランザクションに含めます。

```powershell
new-itemproperty -path MyCompany -Name MyKey -value 123 -UseTransaction
```

このコマンドは、新しいレジストリエントリを表すオブジェクトを返しますが、レジストリエントリは変更されません。

```
MyKey
-----
123
```

現在レジストリにある項目を取得するには、UseTransaction パラメーターを指定せずに Get-ChildItem コマンド ("dir") を使用します。 次のコマンドは、"M" で始まる項目を取得します。

```powershell
dir m*
```

結果には、MyCompany キーにまだエントリが追加されていないことが示されます。

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

トランザクションのコミットの効果をプレビューするには、UseTransaction パラメーターを使用して Get-ChildItem ("dir") コマンドを入力します。 このコマンドには、トランザクション内のデータが表示されます。

```powershell
dir m* -useTransaction
```

この結果、トランザクションがコミットされると、MyKey エントリが MyCompany キーに追加されることがわかります。

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   1 MyCompany                      {MyKey}
```

### <a name="example-4-combining-transacted-and-non-transacted-commands"></a>例 4: トランザクションコマンドと非トランザクションコマンドの組み合わせ

トランザクションの実行中は、非トランザクションコマンドを入力できます。 非トランザクションコマンドはデータに直ちに影響しますが、トランザクションには影響しません。
次のコマンドを実行すると、HKCU:\ Software レジストリキーのトランザクションが開始されます。

```powershell
start-transaction
```

次の3つのコマンドは、New-Item コマンドレットを使用して、レジストリにキーを追加します。
1番目と3番目のコマンドは、UseTransaction パラメーターを使用して、トランザクションにコマンドを含めます。 2番目のコマンドは、パラメーターを省略します。 2番目のコマンドはトランザクションに含まれていないため、すぐに有効になります。

```powershell
new-item MyCompany1 -UseTransaction
new-item MyCompany2
new-item MyCompany3 -UseTransaction
```

レジストリの現在の状態を表示するには、UseTransaction パラメーターを指定せずに Get-ChildItem ("dir") コマンドを使用します。 このコマンドは、"M" で始まる項目を取得します。

```powershell
dir m*
```

結果は、MyCompany2 キーがレジストリに追加されたことを示していますが、トランザクションの一部である MyCompany1 および MyCompany3 キーは追加されていません。

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0    0 MyCompany2                     {}
```

次のコマンドは、トランザクションをコミットします。

```powershell
complete-transaction
```

これで、トランザクションの一部として追加されたキーがレジストリに表示されます。

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
83   1 Microsoft                      {(default)}
0    0 MyCompany1                     {}
0    0 MyCompany2                     {}
0    0 MyCompany3                     {}
```

### <a name="example-5-using-automatic-rollback"></a>例 5: 自動ロールバックの使用

トランザクション内のコマンドが任意の種類のエラーを生成すると、トランザクションは自動的にロールバックされます。

この既定の動作は、トランザクションを実行するスクリプト向けに設計されています。 通常、スクリプトは適切にテストされ、エラー処理ロジックを含んでいるため、エラーは想定されず、トランザクションを終了する必要があります。

最初のコマンドは、HKCU: \ Software レジストリキーでトランザクションを開始します。

```powershell
start-transaction
```

次のコマンドでは、New-Item コマンドレットを使用して、レジストリに MyCompany キーを追加します。 このコマンドは、UseTransaction パラメーター (エイリアスは "usetx") を使用して、トランザクションにコマンドを含めます。

```powershell
New-Item MyCompany -UseTX
```

MyCompany キーはレジストリに既に存在するため、コマンドは失敗し、トランザクションはロールバックされます。

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

Get-Transaction コマンドを実行すると、トランザクションがロールバックされたこと、およびそのサブスクライバー数が0であることが確認されます。

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 RolledBack
```

### <a name="example-6-changing-the-rollback-preference"></a>例 6: ロールバック設定を変更する

トランザクションのエラートレラントを向上させるには、Start-Transaction の RollbackPreference パラメーターを使用して、優先順位を変更します。

次のコマンドは、ロールバックの設定を "Never" にしてトランザクションを開始します。

```powershell
start-transaction -rollbackpreference Never
```

この場合、コマンドが失敗すると、トランザクションは自動的にロールバックされません。

```powershell
New-Item MyCompany -UseTX
```

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

トランザクションがまだアクティブであるため、トランザクションの一部としてコマンドを再送信できます。

```powershell
New-Item MyOtherCompany -UseTX
```

### <a name="example-7-using-the-use-transaction-cmdlet"></a>例 7: USE TRANSACTION コマンドレットの使用

Use-Transaction コマンドレットを使用すると、トランザクション対応の Microsoft .NET フレームワークオブジェクトに対して直接スクリプトを作成できます。 Use-Transaction は、トランザクションが有効な .NET Framework オブジェクト (TransactedString クラスのインスタンスなど) を使用するコマンドおよび式のみを含むスクリプトブロックを実行します。

次のコマンドを実行すると、トランザクションが開始されます。

```powershell
start-transaction
```

次の New-Object コマンドは、TransactedString クラスのインスタンスを作成し、$t 変数に保存します。

```powershell
$t = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
```

次のコマンドは、TransactedString オブジェクトの Append メソッドを使用して、文字列にテキストを追加します。 コマンドはトランザクションの一部ではないため、変更はすぐに有効になります。

```powershell
$t.append("Windows")
```

次のコマンドでは、同じ Append メソッドを使用してテキストを追加しますが、テキストはトランザクションの一部として追加されます。 コマンドは中かっこで囲まれ、使用される ScriptBlock パラメーターの値として設定されます。 UseTransaction パラメーター (UseTx) が必要です。

```powershell
use-transaction {$t.append(" PowerShell")} -usetx
```

$T でトランザクション処理された文字列の現在の内容を表示するには、TransactedString オブジェクトの ToString メソッドを使用します。

```powershell
$t.tostring()
```

出力には、トランザクション以外の変更のみが有効であることが示されています。

```output
Windows
```

トランザクション内から $t のトランザクション処理された文字列の現在の内容を表示するには、Use-Transaction コマンドに式を埋め込みます。

```powershell
use-transaction {$s.tostring()} -usetx
```

出力には、トランザクションビューが表示されます。

```output
PowerShell
```

次のコマンドは、トランザクションをコミットします。

```powershell
complete-transaction
```

最後の文字列を表示するには、次のようにします。

```
$t.tostring()
PowerShell
```

### <a name="example-8-managing-multi-subscriber-transactions"></a>例 8: マルチサブスクライバートランザクションを管理する

別のトランザクションの進行中にトランザクションを開始しても、既定では2番目のトランザクションは作成されません。 代わりに、現在のトランザクションにサブスクライバーを追加します。

この例では、マルチサブスクライバートランザクションを表示および管理する方法を示します。

まず、HKCU: \ Software キーでトランザクションを開始します。

```powershell
start-transaction
```

次のコマンドでは、Get-Transaction コマンドを使用して、アクティブなトランザクションを取得します。

```powershell
get-transaction
```

結果には、アクティブなトランザクションを表すオブジェクトが表示されます。

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

MyCompany キーをレジストリに追加するコマンドを次に示します。 このコマンドは、UseTransaction パラメーターを使用して、コマンドをトランザクションに含めます。

```powershell
new-item MyCompany -UseTransaction
```

次のコマンドでは、Start-Transaction コマンドを使用してトランザクションを開始します。 このコマンドはコマンドプロンプトで入力しますが、トランザクションを含むスクリプトを実行すると発生する可能性が高くなります。

```powershell
start-transaction
```

Get-Transaction コマンドは、トランザクションオブジェクトのサブスクライバー数がインクリメントされることを示します。 値は2になりました。

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

次のコマンドは、New-ItemProperty コマンドレットを使用して、MyCompany キーに MyKey レジストリエントリを追加します。 UseTransaction パラメーターを使用して、トランザクションにコマンドを含めます。

```powershell
new-itemproperty -path MyCompany -name MyKey -UseTransaction
```

MyCompany キーはレジストリに存在しませんが、2つのコマンドが同じトランザクションの一部であるため、このコマンドは成功します。

次のコマンドは、トランザクションをコミットします。 トランザクションがロールバックされた場合、トランザクションはすべてのサブスクライバーに対してロールバックされます。

```powershell
complete-transaction
```

Get-Transaction コマンドは、トランザクションオブジェクトのサブスクライバー数が1であることを示していますが、Status の値がアクティブ (コミットされていません) であることを示しています。

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

トランザクションのコミットを完了するには、2番目のトランザクションの完了コマンドを入力します。 マルチサブスクライバートランザクションをコミットするには、Start-Transaction コマンドごとに1つの Complete-Transaction コマンドを入力する必要があります。

```powershell
complete-transaction
```

もう1つの Get-Transaction コマンドは、トランザクションがコミットされたことを示します。

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 Committed
```

### <a name="example-9-managing-independent-transactions"></a>例 9: 独立したトランザクションの管理

別のトランザクションの進行中にトランザクションを開始すると、Start-Transaction の独立したパラメーターを使用して、元のトランザクションとは無関係に新しいトランザクションを作成できます。

この操作を実行すると、Start-Transaction によって新しいトランザクションオブジェクトが作成され、新しいトランザクションがアクティブなトランザクションになります。

まず、HKCU: Software キーでトランザクションを開始し \\ ます。

```powershell
start-transaction
```

次のコマンドでは、Get-Transaction コマンドを使用して、アクティブなトランザクションを取得します。

```powershell
get-transaction
```

結果には、アクティブなトランザクションを表すオブジェクトが表示されます。

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

次のコマンドは、トランザクションの一部として MyCompany レジストリキーを追加します。 UseTransaction パラメーター (UseTx) を使用して、アクティブなトランザクションにコマンドを含めます。

```powershell
new-item MyCompany -use
```

次のコマンドを実行すると、新しいトランザクションが開始されます。 このコマンドは、独立したパラメーターを使用して、このトランザクションがアクティブなトランザクションに対するサブスクライバーではないことを示します。

```powershell
start-transaction -independent
```

独立したトランザクションを作成すると、新しい (最近作成された) トランザクションがアクティブなトランザクションになります。 Get-Transaction コマンドを使用して、アクティブなトランザクションを取得できます。

```powershell
get-transaction
```

トランザクションのサブスクライバー数が1であることに注意してください。これは、他のサブスクライバーが存在せず、トランザクションが新しいものであることを示しています。

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

元のトランザクションを管理する前に、新しいトランザクションを完了する (コミットまたはロールバックする) 必要があります。

次のコマンドを実行すると、MyOtherCompany キーがレジストリに追加されます。 UseTransaction パラメーター (UseTx) を使用して、アクティブなトランザクションにコマンドを含めます。

```powershell
new-item MyOtherCompany -usetx
```

次に、トランザクションをロールバックします。 2つのサブスクライバーを持つ1つのトランザクションがある場合、トランザクションをロールバックすると、すべてのサブスクライバーのトランザクション全体がロールバックされます。

ただし、これらのトランザクションは独立しているため、最新のトランザクションをロールバックすると、レジストリの変更が取り消され、元のトランザクションがアクティブなトランザクションになります。

```powershell
undo-transaction
```

Get-Transaction コマンドは、元のトランザクションがセッションでアクティブなままであることを確認します。

```powershell
get-transaction
```

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

次のコマンドは、アクティブなトランザクションをコミットします。

```powershell
complete-transaction
```

Get-ChildItem のコマンドは、レジストリが変更されたことを示します。

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

## <a name="see-also"></a>関連項目

[Start-Transaction](xref:Microsoft.PowerShell.Management.Start-Transaction)

[Get-Transaction](xref:Microsoft.PowerShell.Management.Get-Transaction)

[Complete-Transaction](xref:Microsoft.PowerShell.Management.Complete-Transaction)

[Undo-Transaction](xref:Microsoft.PowerShell.Management.Undo-Transaction)

[Use-Transaction](xref:Microsoft.PowerShell.Management.Use-Transaction)

[Get-PSProvider](xref:Microsoft.PowerShell.Management.Get-PSProvider)

[Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

[about_Providers](about_Providers.md)
