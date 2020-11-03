---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/save-help?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Help
ms.openlocfilehash: 6ed809f357cf9424008b2207519abbde22fc9280
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209891"
---
# Save-Help

## 概要
最新のヘルプ ファイルをダウンロードしてファイル システム ディレクトリに保存します。

## SYNTAX

### パス (既定値)

```
Save-Help [-DestinationPath] <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

### LiteralPath

```
Save-Help -LiteralPath <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

## Description

**Get-help** コマンドレットは、PowerShell モジュールの最新のヘルプファイルをダウンロードし、指定したディレクトリに保存します。
この機能を使用すると、インターネットにアクセスできないコンピューター上のヘルプ ファイルを更新でき、複数のコンピューター上のヘルプ ファイルを更新しやすくなります。

Windows PowerShell 3.0 では、ローカルコンピューターにインストールされているモジュールに対してのみ、 **保存** 操作が機能していました。
リモートコンピューターからモジュールをインポートしたり、PowerShell リモート処理を使用してリモートコンピューターから **PSModuleInfo** オブジェクトへの参照を取得したりすることはできましたが、 **Helpinfouri** プロパティは保持されませんでした。この **ヘルプは、** リモートモジュールヘルプでは機能しません。

Windows PowerShell 4.0 では、 **Helpinfouri** プロパティが PowerShell リモート処理によって保持されます。これにより、リモートコンピューターにインストールされているモジュールに対して、 **保存時のヘルプ** を使用できます。
また、インターネットにアクセスできないコンピューターで Export-Clixml を実行して、 **PSModuleInfo** オブジェクトをディスクまたはリムーバブルメディアに保存することもできます。その場合、インターネットにアクセスできるコンピューターにオブジェクトをインポートし、 **PSModuleInfo** オブジェクトで [ **保存** ] を実行します。
保存されたヘルプは、USB ドライブなどのリムーバブル記憶域メディアを使用してリモートコンピューターに転送できます。
ヘルプは **、update-help を実行し** てリモートコンピューターにインストールできます。
このプロセスを使用すれば、どのようなネットワーク アクセスも実行できないコンピューターにヘルプをインストールできます。

保存されたヘルプファイルをインストールするには、Update-Help コマンドレットを実行します。
その *SourcePath* パラメーターを追加して、ヘルプファイルを保存したフォルダーを指定します。

パラメーターを指定しなかった場合、 **Save-Help** コマンドは、セッション内のすべてのモジュールと、 **PSModulePath** 環境変数に設定された場所のコンピューターにインストールされているモジュールに対して、最新のヘルプをダウンロードします。
この操作により、更新可能なヘルプをサポートしていないモジュールは警告なしにスキップされます。

Get-help コマンドレットは、 **保存** 先フォルダー内のヘルプファイルのバージョンを確認します。
新しいヘルプファイルが使用可能な場合、このコマンドレットは、インターネットから最新のヘルプファイルをダウンロードし、フォルダーに保存します。
Get-help **コマンドレットは、** Update-Help コマンドレットと同じように動作しますが、ダウンロードされたキャビネット (.cab) ファイルを保存し、コンピューターにインストールするのではなく、ダウンロードしたキャビネット (.cab) ファイルを保存する点が異なります。

保存されたモジュール用ヘルプはそれぞれ、UI カルチャごとに、ヘルプ情報 (HelpInfo XML) ファイル 1 つと、ヘルプ ファイルのキャビネット (.cab) ファイル 1 つで構成されます。
キャビネットファイルからヘルプファイルを抽出する必要はありません。
Update-help **コマンドレット** は、ヘルプファイルを抽出し、XML が安全であるかどうかを検証した後、モジュールフォルダーの言語固有のサブフォルダーにヘルプファイルとヘルプ情報ファイルをインストールします。

PowerShell のインストールフォルダー ($pshome \ モジュール) にモジュールのヘルプファイルを保存するには、[管理者として実行] オプションを使用して PowerShell を起動します。
これらのモジュールのヘルプ ファイルをダウンロードするには、そのコンピューターの Administrators グループのメンバーである必要があります。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: DhcpServer モジュールのヘルプを保存する

```powershell
# Option 1: Run Invoke-Command to get the PSModuleInfo object for the remote DHCP Server module, save the PSModuleInfo object in the variable $m, and then run Save-Help.

$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock { Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 2: Open a PSSession--targeted at the remote computer that is running the DhcpServer module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$s = New-PSSession -ComputerName "RemoteServer"
$m = Get-Module -PSSession $s -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 3: Open a CIM session--targeted at the remote computer that is running the DhcpServer module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$c = New-CimSession -ComputerName "RemoteServer"
$m = Get-Module -CimSession $c -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"
```

この例では、 **DhcpServer** モジュールまたは DHCP サーバーの役割をローカルコンピューターにインストールせずに、 **DhcpServer** モジュールのヘルプをインターネットに接続されたクライアントコンピューターから保存するために、次の3つの異なる方法 **を使用し** ています。

### 例 2: DhcpServer モジュールのヘルプをインストールする

```powershell
# First, run Export-CliXml to export the PSModuleInfo object to a shared folder or to removable media.

$m = Get-Module -Name "DhcpServer" -ListAvailable
Export-CliXml -Path "E:\UsbFlashDrive\DhcpModule.xml" -InputObject $m

# Next, transport the removable media to a computer that has Internet access, and then import the PSModuleInfo object with Import-CliXml. Run Save-Help to save the Help for the imported DhcpServer module PSModuleInfo object.

$deserialized_m = Import-CliXml "E:\UsbFlashDrive\DhcpModule.xml"
Save-Help -Module $deserialized_m -DestinationPath "E:\UsbFlashDrive\SavedHelp"

# Finally, transport the removable media back to the computer that does not have network access, and then install the help by running Update-Help.

Update-Help -Module DhcpServer -SourcePath "E:\UsbFlashDrive\SavedHelp"
```

この例では、例1でインターネットにアクセスできないコンピューターの **DhcpServer** モジュールのヘルプをインストールする方法を示します。

### 例 3: すべてのモジュールのヘルプを保存する

```powershell
Save-Help -DestinationPath "\\Server01\FileShare01"
```

このコマンドは、ローカル コンピューター上の Windows に設定された UI カルチャに該当するすべてのモジュールの最新のヘルプ ファイルをダウンロードします。
ヘルプファイルは Server01\Fileshare01 フォルダーに保存され \\ \\ ます。

### 例 4: コンピューターのモジュールのヘルプを保存する

```powershell
Save-Help -Module ServerManager -DestinationPath "\\Server01\FileShare01" -Credential Domain01/Admin01
```

このコマンドは、 **ServerManager** モジュールの最新のヘルプファイルをダウンロードし、Server01\Fileshare01 フォルダーに保存し \\ \\ ます。

モジュールをコンピューターにインストールする際、モジュールが現在のセッションにインポートされていない場合でも、モジュール名を *Module* パラメーターの値として入力できます。

このコマンドは、 *Credential* パラメーターを使用して、ファイル共有への書き込みアクセス許可を持つユーザーの資格情報を指定します。

### 例 5: 別のコンピューターにモジュールのヘルプを保存する

```powershell
Invoke-Command -ComputerName Server02 {Get-Module -Name CustomSQL -ListAvailable} | Save-Help -DestinationPath \\Server01\FileShare01 -Credential Domain01\Admin01
```

これらのコマンドは、 **Customsql** モジュールの最新のヘルプファイルをダウンロードし、Server01\Fileshare01 フォルダーに保存し \\ \\ ます。

**Customsql** モジュールがコンピューターにインストールされていないため、このシーケンスには、Server02 コンピューターから customsql モジュールのモジュールオブジェクトを取得し、そのモジュールオブジェクトを **コマンドレットに** パイプする Invoke-Command コマンドが含まれています。

モジュールがコンピューターにインストールされていない場合、 **Save-Help** は、最新のヘルプ ファイルの場所に関する情報が含まれているモジュール オブジェクトを必要とします。

### 例 6: モジュールのヘルプを複数の言語で保存する

```powershell
Save-Help -Module Microsoft.PowerShell* -UICulture de-DE, en-US, fr-FR, ja-JP -DestinationPath "D:\Help"
```

このコマンドは、4つの異なる UI カルチャの PowerShell コアモジュールのヘルプを保存します。
これらのロケールの言語パックは、コンピューターにインストールされている必要はありません。

**保存** したヘルプでは、モジュールの所有者が翻訳されたファイルをインターネットで使用できるようになったときにのみ、さまざまな UI カルチャのモジュールのヘルプファイルをダウンロードできます。

### 例 7: 1 日に複数回ヘルプを保存する

```powershell
Save-Help -Force -DestinationPath "\\Server3\AdminShare\Help"
```

このコマンドは、コンピューターにインストールされているすべてのモジュールのヘルプを保存します。
このコマンドは、 **Save help** コマンドレットが24時間に複数回ダウンロードできないようにするルールを上書きする *Force* パラメーターを指定します。

*Force* パラメーターは、1 GB の制限もオーバーライドし、バージョンのチェックを回避します。
そのため、対象のフォルダーのバージョンよりも前のバージョンであっても、ファイルをダウンロードできます。

このコマンドは、get-help **コマンドレットを使用して** 、指定されたフォルダーにヘルプファイルをダウンロードして保存します。
**Save Help** コマンドを1日に複数回実行する必要がある場合は、 *Force* パラメーターが必要です。

## PARAMETERS

### -Credential

ユーザー資格情報を指定します。 このコマンドレットは、 **DestinationPath** パラメーターで指定したファイルシステムの場所にアクセスする権限を持つユーザーの資格情報を使用して、コマンドを実行します。 このパラメーターは、コマンドで **DestinationPath** パラメーターまたは **LiteralPath** パラメーターが使用されている場合にのみ有効です。

このパラメーターを使用すると `Save-Help` 、リモートコンピューターで **DestinationPath** パラメーターを使用するコマンドを実行できます。 明示的な資格情報を指定することにより、リモートコンピューターでコマンドを実行し、アクセス拒否エラーが発生しないか、CredSSP 認証を使用して資格情報を委任することなく、3台目のコンピューター上のファイル共有にアクセスできます。

**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。 ユーザー名を入力すると、パスワードを入力するように求められます。

資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。

> [!NOTE]
> **SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationPath

ヘルプファイルを保存するフォルダーのパスを指定します。
ファイル名やファイル名拡張子を指定しないでください。

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

このコマンドレットが1日に1回の制限に従っていないことを示し、バージョンチェックをスキップし、1 GB の制限を超えるファイルをダウンロードします。

このパラメーターを指定しなかった場合、 **Save-Help** コマンドは、モジュールごとに 24 時間に 1 回しか実行できません。また、ダウンロードはモジュールごとに最大 1 GB の圧縮されていないコンテンツに制限されます。モジュールのヘルプ ファイルは、コンピューター上にあるファイルよりも新しい場合にのみ、インストールされます。

1日に1回の制限により、ヘルプファイルをホストするサーバーが保護され、PowerShell プロファイルに **保存時のヘルプ** コマンドを追加できるようになります。

*Force* パラメーターを指定せずに複数の ui カルチャのモジュールのヘルプを保存するには、次のように、すべての ui カルチャを同じコマンドに含めます。`Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullyQualifiedModule

Modul特定のオブジェクトの形式で指定された名前を持つモジュールを指定します。
これについては、MSDN ライブラリの「 [Modulの注釈のコンストラクター (Hashtable)](https://msdn.microsoft.com/library/jj136290) 」の「解説」で説明されています。
たとえば、 *FullyQualifiedModule* パラメーターは、@ {ModuleName = "ModuleName"; という形式で指定されたモジュール名を受け入れます。ModuleVersion = "version_number"} または @ {ModuleName = "ModuleName";ModuleVersion = "version_number";Guid = "GUID"}。
**ModuleName** と **ModuleVersion** は必須ですが、 **Guid** は省略可能です。

*モジュール* パラメーターと同じコマンドで *FullyQualifiedModule* パラメーターを指定することはできません。

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LiteralPath

コピー先フォルダーのパスを指定します。
*DestinationPath* パラメーターの値とは異なり、 *LiteralPath* パラメーターの値は、入力されたとおりに使用されます。
ワイルドカードとして解釈される文字はありません。
パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。
単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -モジュール

このコマンドレットがヘルプをダウンロードするモジュールを指定します。
1つ以上のモジュール名または名前のパターンを、コンマ区切りのリスト、または各行に1つのモジュール名を持つファイルに入力します。
ワイルドカード文字を使用できます。
パイプを使用してモジュールオブジェクトを Get-Module コマンドレットから保存して **、ヘルプを保存** することもできます。

既定では、 **Save-Help** は、更新可能なヘルプをサポートし、 **PSModulePath** 環境変数に設定された場所のローカル コンピューターにインストールされているすべてのモジュールのヘルプをダウンロードします。

コンピューターにインストールされていないモジュールのヘルプを保存するには、リモートコンピューターで **Get モジュール** コマンドを実行します。
その結果得られたモジュール オブジェクトを、パイプを使用して **Save-Help** コマンドレットに渡すか、 *Module* パラメーターまたは *InputObject* パラメーターの値として送信します。

指定したモジュールがコンピューターにインストールされている場合は、モジュール名またはモジュール オブジェクトを入力できます。
指定したモジュールがコンピューターにインストールされていない場合は、 **Get-Module** コマンドレットによって返されたモジュール オブジェクトなど、モジュール オブジェクトを入力する必要があります。

**Save Help** コマンドレットの *module* パラメーターは、モジュールファイルまたはモジュールマニフェストファイルの完全パスを受け入れません。
**PSModulePath** の場所にないモジュールのヘルプを保存するには、[ **保存-ヘルプ** ] コマンドを実行する前に、現在のセッションにモジュールをインポートします。

"*" (すべて) の値は、コンピューターにインストールされているすべてのモジュールのヘルプを更新しようとします。
これには、更新可能なヘルプをサポートしていないモジュールも含まれます。
この値は、更新可能なヘルプをサポートしていないモジュールがコマンドによって検出された場合にエラーを生成することがあります。

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -UICulture

このコマンドレットが更新されたヘルプファイルを取得する UI カルチャの値を指定します。
Es、カルチャオブジェクトを含む変数、または Get-Culture や Get-UICulture コマンドなどのカルチャオブジェクトを取得するコマンドなど、1つまたは複数の言語コードを入力します。

ワイルドカード文字は使用できません。
"De" などの部分言語コードを指定しないでください。

既定では、[ **ヘルプ** ] は、Windows またはそのフォールバックカルチャに設定されている UI カルチャのヘルプファイルを取得します。
*UICulture* パラメーターを指定した場合、 **保存時** には、フォールバックカルチャではなく、指定した UI カルチャのヘルプのみが検索されます。

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: Current UI culture
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseDefaultCredentials

このコマンドレットが、web ダウンロードなどのコマンドを、現在のユーザーの資格情報を使用して実行することを示します。
既定では、コマンドは明示的な資格情報がない状態で実行されます。

このパラメーターは、Web ダウンロードが、NTLM、Negotiate、または Kerberos ベース認証を使用する場合に限り有効です。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -スコープ

このパラメーターは、このコマンドレットでは何も行いません。

```yaml
Type: Microsoft.PowerShell.Commands.UpdateHelpScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### PSModuleInfo (システム管理)

パイプを使用して、モジュールオブジェクトを **Get module** コマンドレットから、 **Save-Help** の *module* パラメーターにパイプすることができます。

## 出力

### なし

このコマンドレットは出力を生成しません。

## 注

* モジュールのヘルプを [$pshome] \ [モジュール] フォルダーに保存するには、[管理者として実行] オプションを使用して PowerShell を起動します。 コンピューターの Administrators グループのメンバーだけが、$pshome \ modules フォルダー内のモジュールのヘルプをダウンロードできます。
* 保存されたモジュール用ヘルプはそれぞれ、UI カルチャごとに、ヘルプ情報 (HelpInfo XML) ファイル 1 つと、ヘルプ ファイルのキャビネット (.cab) ファイル 1 つで構成されます。 キャビネットファイルからヘルプファイルを抽出する必要はありません。 Update-Help コマンドレットは、ヘルプファイルを抽出し、XML を検証した後、モジュールフォルダーの言語固有のサブフォルダーにヘルプファイルとヘルプ情報ファイルをインストールします。
* **Save-Help** コマンドレットは、コンピューターにインストールされていないモジュールのヘルプを保存できます。 ただし、ヘルプファイルはモジュールフォルダーにインストールされるため、 **update-help コマンドレット** は、コンピューターにインストールされているモジュールに対してのみ、更新されたヘルプファイルをインストールできます。
* **Save-Help** は、モジュールの更新済みヘルプ ファイルが見つからない場合や、指定された言語の更新済みファイルが見つからない場合、エラー メッセージなどを表示せずに処理を続行します。 コマンドによって保存されたファイルを確認するには、 *Verbose* パラメーターを指定します。
* モジュールは、更新可能なヘルプの最小単位です。 特定のコマンドレットのヘルプは保存できません。モジュール内のすべてのコマンドレットに対してのみ使用できます。 特定のコマンドレットを含むモジュールを見つけるには、 **ModuleName** プロパティを Get-Command コマンドレットと共に使用します。次に例を示します。 `(Get-Command \<cmdlet-name\>).ModuleName`
* [ **ヘルプ** ] は、すべてのモジュールと PowerShell Core スナップインをサポートします。その他のスナップインはサポートしていません。
* Update-help および **get-help コマンド****レットは、** 次のポートを使用してヘルプファイルをダウンロードします: HTTP の場合はポート80、HTTPS の場合はポート443。
* **Update-Help** および **Save-Help** コマンドレットは、Windows プレインストール環境 (Windows PE) ではサポートされません。

## 関連リンク

[Get-Help](Get-Help.md)

[Get-Module](Get-Module.md)

[Update-Help](Update-Help.md)
