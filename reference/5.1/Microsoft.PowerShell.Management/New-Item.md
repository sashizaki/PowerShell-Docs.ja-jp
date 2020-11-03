---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
ms.openlocfilehash: b1657d369d44d575ee7bed8b76d36224ea2748f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214616"
---
# New-Item

## 概要
新しい項目を作成します。

## SYNTAX

### pathSet (既定)

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### nameSet

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## Description

コマンドレットにより、 `New-Item` 新しい項目が作成され、その値が設定されます。 作成できる項目の種類は、項目の場所によって異なります。 たとえば、ファイルシステムで、に `New-Item` よってファイルとフォルダーが作成されます。 レジストリで、は `New-Item` レジストリキーとエントリを作成します。

`New-Item` では、作成する項目の値を設定することもできます。 たとえば、新しいファイルを作成するときに、は `New-Item` ファイルに初期コンテンツを追加できます。

## 例

### 例 1: 現在のディレクトリにファイルを作成する

このコマンドは、現在のディレクトリに "testfile1.txt" という名前のテキストファイルを作成します。 **Path** パラメーターの値のドット ('. ') は、現在のディレクトリを示します。 **Value** パラメーターの後の引用符で囲まれたテキストは、内容としてファイルに追加されます。

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### 例 2: ディレクトリを作成する

このコマンドにより、ドライブに "ログログ" という名前のディレクトリが作成さ `C:` れます。 **ItemType** パラメーターは、新しい項目がファイルまたはその他のファイルシステムオブジェクトではなく、ディレクトリであることを指定します。

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### 例 3: プロファイルを作成する

このコマンドは、変数で指定されたパスに PowerShell プロファイルを作成し `$profile` ます。

プロファイルを使用して、PowerShell をカスタマイズできます。 `$profile` は、"CurrentUser/CurrentHost" プロファイルのパスとファイル名を格納する自動 (組み込み) 変数です。 既定では、PowerShell にはパスとファイル名が格納されていますが、プロファイルは存在しません。

このコマンドでは、 `$profile` 変数はファイルのパスを表します。 **ItemType** パラメーターは、コマンドによってファイルが作成されることを指定します。 **Force** パラメーターを使用すると、パス内のディレクトリが存在しない場合でも、プロファイルパスにファイルを作成できます。

プロファイルを作成したら、エイリアス、関数、およびスクリプトをプロファイルに入力して、シェルをカスタマイズできます。

詳細については、「 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) 」および「 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)」を参照してください。

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

> [!NOTE]
> このメソッドを使用してファイルを作成すると、生成されるファイルはバイト順マーク (BOM) なしで UTF-8 としてエンコードされます。

### 例 4: 別のディレクトリにディレクトリを作成する

この例では、"C:\ テスト" ディレクトリに新しい Scripts ディレクトリを作成します。

新しいディレクトリ項目の名前 "Scripts" は、[ **名前** ] の値に指定されるのではなく、 **Path** パラメーターの値に含まれます。 構文に示すとおり、どちらのコマンド形式も有効です。

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### 例 5: 複数のファイルを作成する

この例では、2つの異なるディレクトリにファイルを作成します。 **Path** は複数の文字列を受け取るため、複数の項目を作成するために使用できます。

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

### 例 6:-Force パラメーターを使用してフォルダーの再作成を試みる

この例では、内にファイルを含むフォルダーを作成します。 次に、はを使用して同じフォルダーを作成しようとし `-Force` ます。 フォルダーは上書きされませんが、ファイルがそのまま作成された状態で既存のフォルダーオブジェクトを返すだけです。

```powershell
PS> New-Item -Path .\TestFolder -ItemType Directory
PS> New-Item -Path .\TestFolder\TestFile.txt -ItemType File

PS> New-Item -Path .\TestFolder -ItemType Directory -Force

    Directory: C:\
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         5/1/2020   8:03 AM                TestFolder

PS> Get-ChildItem .\TestFolder\

    Directory: C:\TestFolder
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:03 AM              0 TestFile.txt
```

### 例 7:-Force パラメーターを使用して既存のファイルを上書きする

この例では、値を指定してファイルを作成し、を使用してファイルを再作成し `-Force` ます。 これにより、既存のファイルが上書きされ、length プロパティで確認できるようにコンテンツが失われます。

```powershell
PS> New-Item ./TestFile.txt -ItemType File -Value 'This is just a test file'

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM             24 TestFile.txt

New-Item ./TestFile.txt -ItemType File -Force

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM              0 TestFile.txt
```

> [!NOTE]
> スイッチと共にを使用してレジストリキーを作成する場合、 `New-Item` `-Force` コマンドはファイルを上書きする場合と同様に動作します。 レジストリキーが既に存在する場合、キーとすべてのプロパティと値は空のレジストリキーで上書きされます。

## PARAMETERS

### -Credential

> [!NOTE]
> このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。 このコマンドレットの実行時に別のユーザーの権限を借用するか、資格情報を昇格するには、を使用し `Invoke-Command` ます。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

このコマンドレットに対して、既存の読み取り専用項目を上書きする項目を強制的に作成します。 実装はプロバイダーごとに異なります。 **Force** パラメーターを使用しても、コマンドレットはセキュリティ制限を上書きできません。

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

### -ItemType

プロバイダーによって指定された新しい項目の種類を指定します。 このパラメーターで使用できる値は、使用している現在のプロバイダーによって異なります。

場所がドライブにある場合は、 `FileSystem` 次の値が許可されます。

- ファイル
- ディレクトリ
- SymbolicLink
- ジャンクション
- Hardlink create

このメソッドを使用してファイルを作成すると、生成されるファイルはバイト順マーク (BOM) なしで UTF-8 としてエンコードされます。

ドライブで `Certificate` は、次の値を指定できます。

- 証明書プロバイダー
- Certificate
- ストア
- StoreLocation

詳細については、「 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

新しい項目の名前を指定します。 **名前** または **パス** のパラメーター値に新しい項目の名前を指定したり、[ **名前** ] または [ **パス** ] の値で新しい項目のパスを指定したりすることができます。 **Name** パラメーターを使用して渡された項目名は、 **Path** パラメーターの値に対して相対的に作成されます。

```yaml
Type: System.String
Parameter Sets: nameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

新しい項目の場所のパスを指定します。 既定値は、 **Path** が省略された場合の現在の場所です。 [ **名前** ] に新しい項目の名前を指定することも、[ **パス** ] に含めることもできます。 **Name** パラメーターを使用して渡された項目名は、 **Path** パラメーターの値に対して相対的に作成されます。

このコマンドレットでは、 **Path** パラメーターは他のコマンドレットの **LiteralPath** パラメーターのように機能します。
ワイルドカード文字は解釈されません。 すべての文字が場所のプロバイダーに渡されます。 プロバイダーがすべての文字をサポートしていない可能性があります。 たとえば、アスタリスク () 文字を含むファイル名を作成することはできません `*` 。

```yaml
Type: System.String[]
Parameter Sets: pathSet, nameSet
Aliases:

Required: True (pathSet), False (nameSet)
Position: 0
Default value: Current location
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseTransaction

アクティブなトランザクションのコマンドが含まれます。 このパラメーターは、トランザクションが進行中の場合のみ有効です。 詳細については、「[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)」を参照してください。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

新しい項目の値を指定します。 パイプを使用して値をにパイプすることもでき `New-Item` ます。

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Target

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm

コマンドレットの実行前に確認を求めるメッセージが表示されます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

コマンドレットの実行時に発生する内容を示します。
このコマンドレットは実行されません。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。 詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。

## 入力

### System.Object

パイプを使用して、新しい項目の値をこのコマンドレットに渡します。

## 出力

### System.Object

このコマンドレットは、作成された項目を返します。

## 注

`New-Item` は、プロバイダーによって公開されるデータを使用するように設計されています。 セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。 詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。

## 関連リンク

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Get-Item](Get-Item.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
