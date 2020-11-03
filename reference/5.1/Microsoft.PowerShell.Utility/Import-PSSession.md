---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PSSession
ms.openlocfilehash: 2fe48f90b020d0566364f4f24554cb3442880ab5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213867"
---
# Import-PSSession

## 概要
別のセッションから現在のセッションにコマンドをインポートします。

## SYNTAX

```
Import-PSSession [-Prefix <String>] [-DisableNameChecking] [[-CommandName] <String[]>] [-AllowClobber]
 [-ArgumentList <Object[]>] [-CommandType <CommandTypes>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-FormatTypeName] <String[]>]
 [-Certificate <X509Certificate2>] [-Session] <PSSession> [<CommonParameters>]
```

## Description
**インポート pssession** コマンドレットは、コマンドレット、関数、エイリアスなどのコマンドを、ローカルコンピューターまたはリモートコンピューター上の PSSession から現在のセッションにインポートします。
Get-Command コマンドレットが PSSession で検索できる任意のコマンドをインポートできます。

Microsoft Exchange Server シェルなどのカスタム シェルから、または現在のセッションに存在しない Windows PowerShell モジュールやスナップインなどの要素が存在するセッションからコマンドをインポートするには、 **Import-PSSession** コマンドを使用します。

コマンドをインポートするには、最初に New-PSSession コマンドレットを使用して PSSession を作成します。
次に、 **Import-PSSession** コマンドレットを使用して、コマンドをインポートします。
既定では、 **Import-PSSession** は、現在のセッションのコマンドと同じ名前のコマンドを除くすべてのコマンドをインポートします。
すべてのコマンドをインポートするには、 *AllowClobber* パラメーターを使用します。

インポートしたコマンドは、セッションのコマンドを使用する場合と同じように使用できます。
インポートしたコマンドを使用すると、インポートした部分のコマンドがインポート元のセッションで暗黙的に実行されます。
ただし、リモート操作はすべて Windows PowerShell によって処理されます。
リモート操作に注意を払う必要はありませんが、もう一方のセッション (PSSession) への接続を開いたままにする必要があります。
接続を閉じると、インポートしたコマンドを利用できなくなります。

インポートしたコマンドは、実行時間がローカル コマンドよりも長い場合があるため、 **Import-PSSession** はインポートしたすべてのコマンドに *AsJob* パラメーターを追加します。
このパラメーターを使用すると、コマンドを Windows PowerShell のバックグラウンド ジョブとして実行することができます。
詳細については、「about_Jobs」を参照してください。

**Import-PSSession** を使用すると、現在のセッションにのみ存在する一時的なモジュールにインポートしたコマンドが追加され、そのモジュールを表すオブジェクトが返されます。
今後のセッションで使用できる永続的なモジュールを作成するには、Export-PSSession コマンドレットを使用します。

**Import-PSSession** コマンドレットは、Windows PowerShell の暗黙的なリモート処理機能を使用します。
現在のセッションにコマンドをインポートすると、元のセッションまたは元のコンピューターの同様のセッションで、コマンドが暗黙的に実行されます。

Windows PowerShell 3.0 以降では、Import-Module コマンドレットを使用して、リモートセッションから現在のセッションにモジュールをインポートできます。
この機能では、暗黙的なリモート処理が使用されます。
これは、 **Import-PSSession** を使用してリモート セッションから現在のセッションに選択したモジュールをインポートした場合と同じです。

## 例

### 例 1: PSSession からすべてのコマンドをインポートする

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S
```

このコマンドは、Server01 コンピューターの PSSession から現在のセッションに、現在のセッションのコマンドと同じ名前のコマンドを除くすべてのコマンドをインポートします。

このコマンドでは *CommandName* パラメーターを使用しないため、インポートされたコマンドに必要な書式データもすべてインポートされます。

### 例 2: 特定の文字列で終わるコマンドをインポートする

```
PS C:\> $S = New-PSSession https://ps.testlabs.com/powershell
PS C:\> Import-PSSession -Session $S -CommandName *-test -FormatTypeName *
PS C:\> New-Test -Name Test1
PS C:\> Get-Test test1 | Run-Test
```

これらのコマンドは、PSSession からローカル セッションに名前が "-test" で終わるコマンドをインポートします。その後、インポートしたコマンドレットを使用する方法も示します。

最初のコマンドは、New-PSSession コマンドレットを使用して PSSession を作成します。
$S 変数に PSSession を保存します。

2番目のコマンドは、 **import-pssession** コマンドレットを使用して、$S の pssession から現在のセッションにコマンドをインポートします。
*CommandName* パラメーターを使用して "Test" という名詞を含むコマンドを指定し、 *FormatTypeName* パラメーターを使用して Test コマンドの書式データをインポートします。

3 番目と 4 番目のコマンドは、現在のセッションでインポートされたコマンドを使用します。
インポートされたコマンドは、現在のセッションに実際に追加されるため、ローカル構文を使用して実行できます。
Invoke-Command コマンドレットを使用して、インポートしたコマンドを実行する必要はありません。

### 例 3: PSSession からコマンドレットをインポートする

```
PS C:\> $S1 = New-PSSession -ComputerName s1
PS C:\> $S2 = New-PSSession -ComputerName s2
PS C:\> Import-PSSession -Session s1 -Type cmdlet -Name New-Test, Get-Test -FormatTypeName *
PS C:\> Import-PSSession -Session s2 -Type Cmdlet -Name Set-Test -FormatTypeName *
PS C:\> New-Test Test1 | Set-Test -RunType Full
```

この例では、ローカルのコマンドレットを使用するのと同じように、インポートされたコマンドレットを使用できることを示します。

これらのコマンドは、Server01 コンピューターの PSSession から New-Test コマンドレットと Get-Test コマンドレットをインポートし、Server02 コンピューターの PSSession から Set-Test コマンドレットをインポートします。

別々の PSSession からコマンドレットをインポートした場合でも、パイプを使用して 1 つのコマンドレットから別のコマンドレットにオブジェクトを渡すことができます。エラーにはなりません。

### 例 4: インポートされたコマンドをバックグラウンドジョブとして実行する

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S -CommandName *-test* -FormatTypeName *
PS C:\> $batch = New-Test -Name Batch -AsJob
PS C:\> Receive-Job $batch
```

この例では、インポートしたコマンドをバックグラウンド ジョブとして実行する方法を示します。

インポートしたコマンドは、実行時間がローカル コマンドよりも長い場合があるため、 **Import-PSSession** はインポートしたすべてのコマンドに *AsJob* パラメーターを追加します。
*AsJob* パラメーターを使用すると、コマンドをバックグラウンド ジョブとして実行できます。

最初のコマンドは、Server01 コンピューター上に PSSession を作成し、PSSession オブジェクトを $S 変数に保存します。

2番目のコマンドは、 **インポート-PSSession** を使用して、$S の PSSession から現在のセッションにテストコマンドレットをインポートします。

3 番目のコマンドは、インポートした New-Test コマンドレットの *AsJob* パラメーターを使用して、New-Test コマンドをバックグラウンド ジョブとして実行します。
このコマンドでは、New-Test から返されたジョブ オブジェクトを $batch 変数に保存します。

4番目のコマンドは、Receive-Job コマンドレットを使用して、ジョブの結果を $batch 変数に取得します。

### 例 5: Windows PowerShell モジュールからコマンドレットと関数をインポートする

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Invoke-Command -Session $S {Import-Module TestManagement}
PS C:\> Import-PSSession -Session $S -Module TestManagement
```

この例では、リモート コンピューターの Windows PowerShell モジュールから現在のセッションにコマンドレットと関数をインポートする方法を示します。

最初のコマンドは、Server01 コンピューター上に PSSession を作成し、$S 変数に保存します。

2番目のコマンドは、 **コマンド** レットを使用して、$S 内の PSSession で Import-Module コマンドを実行します。

通常、Windows PowerShell プロファイルの **Import-Module** コマンドによってすべてのセッションにモジュールが追加されますが、PSSession ではプロファイルは実行されません。

3番目のコマンドは、 **import-PSSession** の *module* パラメーターを使用して、モジュール内のコマンドレットと関数を現在のセッションにインポートします。

### 例 6: 一時ファイルにモジュールを作成する

```
PS C:\> Import-PSSession $S -CommandName Get-Date, SearchHelp -FormatTypeName * -AllowClobber

Name              : tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
Path              : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf\tmp_79468106-4e1d-4d90-af97-1154f9317239_
tcw1zunz.ttf.psm1
Description       : Implicit remoting for http://server01.corp.fabrikam.com/wsman
Guid              : 79468106-4e1d-4d90-af97-1154f9317239
Version           : 1.0
ModuleBase        : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
ModuleType        : Script
PrivateData       : {ImplicitRemoting}
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Get-Date, Get-Date], [SearchHelp, SearchHelp]}
ExportedVariables : {}
NestedModules     : {}
```

この例では、 **Import-PSSession** でディスク上の一時ファイルにモジュールを作成します。
また、現在のセッションにインポートする前に、すべてのコマンドを関数に変換します。

このコマンドは、Get-Date コマンドレットと SearchHelp 関数を現在のセッションにインポートするために、 **import-PSSession** コマンドレットを使用します。

**Import-PSSession** コマンドレットは、一時的なモジュールを表す **PSModuleInfo** オブジェクトを返します。
**Path** プロパティの値は、 **Import-PSSession** によって、一時的な場所にスクリプト モジュール (.psm1) ファイルが作成されたことを示しています。
**ExportedFunctions** プロパティは、 **Get-Date** コマンドレットと SearchHelp 関数が両方とも関数としてインポートされたことを示しています。

### 例 7: インポートされたコマンドによって非表示になっているコマンドを実行する

```
PS C:\> Import-PSSession $S -CommandName Get-Date -FormatTypeName * -AllowClobber

PS C:\> Get-Command Get-Date -All

CommandType   Name       Definition
-----------   ----       ----------
Function      Get-Date   ...
Cmdlet        Get-Date   Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>]

PS C:\> Get-Date
09074

PS C:\> (Get-Command -Type Cmdlet -Name Get-Date).PSSnapin.Name
Microsoft.PowerShell.Utility

PS C:\> Microsoft.PowerShell.Utility\Get-Date
Sunday, March 15, 2009 2:08:26 PM
```

この例では、インポートされたコマンドによって非表示になったコマンドを実行する方法を示します。

最初のコマンドは、$S 変数の PSSession から Get-Date コマンドレットをインポートします。
現在のセッションには **Get-Date** コマンドレットが含まれているため、このコマンドには *AllowClobber* パラメーターが必要です。

2番目のコマンドは、Get-Command コマンドレットの **all** パラメーターを使用して、現在のセッションのすべての **get Date** コマンドを取得します。
出力には、セッションに元の **Get-Date** コマンドレットと **Get-Date** 関数が含まれていることが示されています。
**Get date** 関数は、$S の PSSession でインポートされた **get date** コマンドレットを実行します。

3 番目のコマンドは、 **Get-Date** コマンドを実行します。
Windows PowerShell では、関数はコマンドレットよりも優先されるため、インポートされた **Get-Date** 関数が実行され、ユリウス日が返されます。

4 番目と 5 番目のコマンドは、修飾名を使用して、インポートされたコマンドによって非表示になったコマンドを実行する方法を示しています。

4 番目のコマンドは、元の **Get-Date** コマンドレットを現在のセッションに追加した Windows PowerShell スナップインの名前を取得します。

5 番目のコマンドは、スナップインで修飾された **Get-Date** コマンドレットの名前を使用して、 **Get-Date** コマンドを実行します。

コマンドの優先順位と非表示のコマンドの詳細については、「about_Command_Precedence」を参照してください。

### 例 8: 名前に特定の文字列が含まれているコマンドをインポートする

```
PS C:\> Import-PSSession -Session $S -CommandName *Item* -AllowClobber
```

このコマンドは、$S の PSSession からの項目を含む名前を持つコマンドをインポートします。
このコマンドには、 *CommandName* パラメーターは含まれていますが、 *formattypedata* パラメーターは含まれていないため、コマンドのみがインポートされます。

このコマンドは、現在のセッションにコマンドの書式データが既に存在しており、 **Import-PSSession** を使用してリモート コンピューターでそのコマンドを実行する場合に使用します。

### 例 9: モジュールパラメーターを使用して、セッションにインポートされたコマンドを検出する

```
PS C:\> $M = Import-PSSession -Session $S -CommandName *bits* -FormatTypeName *bits*
PS C:\> Get-Command -Module $M
CommandType     Name
-----------     ----
Function        Add-BitsFile
Function        Complete-BitsTransfer
Function        Get-BitsTransfer
Function        Remove-BitsTransfer
Function        Resume-BitsTransfer
Function        Set-BitsTransfer
Function        Start-BitsTransfer
Function        Suspend-BitsTransfer
```

このコマンドは、 **Get コマンド** の *Module* パラメーターを使用して、 **Import-PSSession** コマンドによってセッションにインポートされたコマンドを確認する方法を示しています。

最初のコマンドは、 **import-pssession** コマンドレットを使用して、$S 変数の PSSession から "bits" を含む名前のコマンドをインポートします。
**Import-PSSession** コマンドは、一時的なモジュールを返し、そのモジュールを $m 変数に保存します。

2番目のコマンドは、Get-Command コマンドレットを使用して、モジュールによって $M 変数にエクスポートされたコマンドを取得します。

*Module* パラメーターは、モジュール名用に設計されており、文字列値を受け取ります。
ただし、モジュール オブジェクトを渡すと、Windows PowerShell は、モジュール オブジェクトの **ToString** メソッドを使用して、モジュール名を返します。

**Get command** コマンドは、"" に相当し `Get-Command $M.Name` ます。

## PARAMETERS

### -AllowClobber
このコマンドレットが、現在のセッションのコマンドと同じ名前を持つ場合でも、指定したコマンドをインポートすることを示します。

現在のセッションにあるコマンドと同じ名前のコマンドをインポートする場合、インポートされたコマンドを非表示にするか、元のコマンドを置き換えます。
詳細については、「about_Command_Precedence」を参照してください。

既定では、 **Import-PSSession** は、現在のセッションのコマンドと同じ名前のコマンドをインポートしません。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ArgumentList
指定された引数 (パラメーター値) を使用した結果として得られるコマンドの配列を指定します。

たとえば、証明書 (Cert:) の Get-Item コマンドのバリアントをインポートするには、$S の PSSession のドライブに、「」と入力 `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:` します。

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -証明書
**Import-PSSession** によって作成された一時的なモジュールの書式ファイル (*Format.ps1xml) またはスクリプト モジュール ファイル (.psm1) の署名に使用するクライアント証明書を指定します。

証明書が格納されている変数を入力するか、証明書を取得するコマンドまたは式を入力します。

証明書を検索するには、Get-PfxCertificate コマンドレットを使用するか、証明書 (Cert:) で Get-ChildItem コマンドレットを使用します。駆動.
証明書が無効な場合、または証明書に十分な権限がない場合、コマンドは失敗します。

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandName
指定された名前または名前パターンのコマンドを指定します。
ワイルドカードを使用できます。
*CommandName* またはそのエイリアスである *Name* を使用します。

既定では、 **Import-PSSession** は、現在のセッションのコマンドと同じ名前のコマンドを除いて、セッションのすべてのコマンドをインポートします。
そのため、インポート先のセッションでインポートしたコマンドが非表示になることや、置き換えられることがありません。
非表示になったり、他のコマンドを置き換えたりするコマンドを含め、すべてのコマンドをインポートするには、 *AllowClobber* パラメーターを使用します。

*CommandName* パラメーターを使用する場合は、 *FormatTypeName* パラメーターを使用しない限り、コマンドの書式ファイルはインポートされません。
同様に、 *FormatTypeName* パラメーターを使用する場合は、 *CommandName* パラメーターを使用しない限り、コマンドはインポートされません。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandType
コマンドオブジェクトの種類を指定します。
既定値は Cmdlet です。
*CommandType* またはそのエイリアスの *Type* を使用します。
このパラメーターの有効値は、次のとおりです。

- エイリアス.
リモート セッションの Windows PowerShell エイリアス。
- すべて。
リモート セッションのコマンドレットと関数。
- アプリケーション をクリックします。
リモート セッションの Path 環境変数 ($env:path) に格納されているパスにある Windows PowerShell ファイル以外のすべてのファイル (.txt、.exe、.dll ファイルなど)。
- コマンドレット.
リモート セッションのコマンドレット。
"Cmdlet" が既定値です。
- ExternalScript。
リモート セッションの Path 環境変数 ($env:path) に格納されているパスにある .ps1 ファイル。
- フィルターと関数。
リモート セッションの Windows PowerShell 関数。
- スクリプティング。
リモート セッションのスクリプト ブロック。

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableNameChecking
このコマンドレットが、許可されていない動詞または禁止された文字を含んでいる名前を持つコマンドレットまたは関数をインポートしたときに警告するメッセージを抑制することを示します。

既定では、インポートしたモジュールが、名前に許可されていない動詞を持つコマンドレットまたは関数をエクスポートすると、Windows PowerShell によって次の警告メッセージが表示されます。

"警告: インポートされたコマンド名には、許可されていない動詞が含まれているため、検出できない可能性があります。
詳細については Verbose パラメーターを使用するか、「Get-Verb」と入力して承認されている動詞の一覧を参照してください。"

このメッセージは、単なる警告です。
実際には、非準拠のコマンドを含む、すべてのモジュールがインポートされます。
モジュール ユーザーにメッセージが表示されますが、名前付けの問題はモジュール作成者が解決する必要があります。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FormatTypeName
指定された Microsoft .NET Framework 型の書式設定命令を指定します。
型名を入力します。
ワイルドカードを使用できます。

このパラメーターの値は、コマンドのインポート元のセッションで Get-FormatData コマンドによって返される型名である必要があります。
リモート セッション内のすべての書式設定データを取得するには、「*」を入力します。

コマンドに *CommandName* パラメーターまたは *formattypename* パラメーターのいずれかが含まれていない場合は、リモートセッションで、 **formattypename** コマンドによって返されたすべての .NET Framework 型の書式設定命令が **インポート** されます。

*FormatTypeName* パラメーターを使用する場合は、 *CommandName* パラメーターを使用しない限り、コマンドはインポートされません。

同様に、 *CommandName* パラメーターを使用する場合は、 *FormatTypeName* パラメーターを使用しない限り、コマンドの書式ファイルはインポートされません。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullyQualifiedModule
**Modulの** 特定のオブジェクトの形式で指定された名前を持つモジュールを指定します (MSDN ライブラリの「 [Modulの注意事項コンストラクター (Hashtable)](https://msdn.microsoft.com/library/jj136290) 」の「解説」で説明しています)。
たとえば、 *FullyQualifiedModule* パラメーターは、@ {ModuleName = "ModuleName"; という形式で指定されたモジュール名を受け入れます。ModuleVersion = "version_number"} または @ {ModuleName = "ModuleName";ModuleVersion = "version_number";Guid = "GUID"}。
**ModuleName** と **ModuleVersion** は必須ですが、 **Guid** は省略可能です。

*モジュール* パラメーターと同じコマンドで *FullyQualifiedModule* パラメーターを指定することはできません。2つのパラメーターは相互に排他的です。

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -モジュール
Windows PowerShell スナップインおよびモジュールのコマンドの配列とを指定します。
スナップインとモジュールの名前を入力します。
ワイルドカードは使用できません。

**インポート-PSSession** では、スナップインからプロバイダーをインポートできません。

詳細については、「about_PSSnapins」と「[about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md)」を参照してください。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prefix
インポートされたコマンドの名前の名詞のプレフィックスを指定します。

セッションに同じ名前の別のコマンドが存在する場合に発生する名前の競合を回避するには、このパラメーターを使用します。

たとえば、プレフィックス Remote を指定して Get-Date コマンドレットをインポートした場合、このコマンドレットはセッションでは Get-help Date として認識され、元の **Get date** コマンドレットと混同されることはありません。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -セッション
コマンドレットのインポート元の **PSSession** を指定します。
セッションオブジェクトを含む変数、または New-PSSession や Get-PSSession コマンドなどのセッションオブジェクトを取得するコマンドを入力します。
指定できるセッションは 1 つだけです。
このパラメーターは必須です。

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし
このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。

## 出力

### PSModuleInfo (システム管理)
**インポート-PSSession** は、New-Module と Get-Module のコマンドレットが返すのと同じモジュールオブジェクトを返します。
ただし、インポートされたモジュールは一時的なもので、現在のセッションにのみ存在します。
ディスクにパーマネントモジュールを作成するには、Export-PSSession コマンドレットを使用します。

## 注

* **インポート-PSSession** は、Windows PowerShell リモート処理インフラストラクチャに依存します。 このコマンドレットを使用するには、WS-Management リモート処理用にコンピューターを構成する必要があります。 詳細については、「about_Remote」および「about_Remote_Requirements」を参照してください。
* **インポート-PSSession** は、変数または Windows PowerShell プロバイダーをインポートしません。
* 現在のセッションのコマンドと同じ名前のコマンドをインポートすると、インポートされたコマンドによって、現在のセッションのエイリアス、関数、およびコマンドレットが非表示になったり、現在のセッションの関数や変数が置き換えられたりすることがあります。 名前の競合を回避するには、 *Prefix* パラメーターを使用します。 詳細については、「about_Command_Precedence」を参照してください。
* **インポート-PSSession** は、すべてのコマンドをインポート前に関数に変換します。 そのため、インポートされたコマンドの動作は、元のコマンドの種類が維持されている場合と少し異なります。 たとえば、PSSession からコマンドレットをインポートした後、モジュールまたはスナップインから同じ名前のコマンドレットをインポートした場合は、関数はコマンドレットよりも優先されるため、既定では PSSession からインポートしたコマンドレットが常に実行されます。 また、同じ名前のエイリアスが存在するセッションにエイリアスをインポートした場合は、エイリアスは関数よりも優先されるため、元のエイリアスが常に使用されます。 詳細については、「about_Command_Precedence」を参照してください。
* Write-Progress コマンドレット **を使用し** て、コマンドの進行状況を表示します。 コマンドが実行中の場合、進行状況バーが表示されます。
* インポートするコマンドを見つけるには、Invoke-Command コマンドレット **を使用し** て、pssession で Get-Command コマンドを実行します。 コマンドの書式設定データを取得するには、Get-FormatData コマンドレットを使用します。 これらのコマンドレットのエラーメッセージは、 **インポート-PSSession** コマンドを実行すると表示できます。 また、 **インポート pssession** では、コマンドレットの get Command、Get Formatdata、Select-Object、および Get-Help を含まない pssession からコマンドをインポートすることはできません。
* インポートされたコマンドには、ユーザー インターフェイスを備えたプログラム (たとえば、メモ帳) を起動できないなど、他のリモート コマンドと同じ制限があります。
* Windows PowerShell プロファイルは PSSession で実行されないため、プロファイルによってセッションに追加されたコマンドは **Import-PSSession** で利用することができません。 プロファイルからコマンドをインポートするには、コマンドをインポートする前に、Invoke-Command コマンドを使用して、PSSession でプロファイルを手動で実行します。
* **Import-PSSession** によって作成された一時的なモジュールには、そのコマンドで書式データがインポートされない場合でも、書式ファイルが含まれていることがあります。 コマンドで書式データがインポートされない場合、作成される書式ファイルに書式データは含まれません。
* **Import-PSSession** を使用する場合は、現在のセッションの実行ポリシーを Restricted または AllSigned に設定することはできません。これは、 **Import-PSSession** によって作成される一時的なモジュールに含まれる未署名のスクリプト ファイルがこれらのポリシーによって禁止されているためです。 ローカルコンピューターの実行ポリシーを変更せずに **インポート PSSession** を使用するには、Set-ExecutionPolicy の *Scope* パラメーターを使用して、1つのプロセスに対して制限の少ない実行ポリシーを設定します。
* Windows PowerShell 2.0 では、別のセッションからインポートしたコマンドのヘルプ トピックに、 *Prefix* パラメーターを使用して割り当てたプレフィックスが含まれません。 Windows PowerShell 2.0 でインポートしたコマンドのヘルプを取得するには、元の (プレフィックスなしの) コマンド名を使用します。

## 関連リンク

[Export-PSSession](Export-PSSession.md)
