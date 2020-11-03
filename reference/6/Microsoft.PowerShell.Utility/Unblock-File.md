---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unblock-File
ms.openlocfilehash: 617d36f61434d8b779d1161610cc7757c6a7725d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216200"
---
# Unblock-File

## 概要
インターネットからダウンロードされたファイルのブロックを解除します。

## SYNTAX

### ByPath (既定値)

```
Unblock-File [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Unblock-File -LiteralPath <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description

**Unblock-File** コマンドレットを使用すると、インターネットからダウンロードされたファイルを開くことができます。
これにより、powershell の実行ポリシーが **RemoteSigned** の場合でも、インターネットからダウンロードされた powershell スクリプトファイルのブロックが解除され、実行できるようになります。
既定では、信頼されていないファイルからコンピューターを保護するために、これらのファイルはブロックされています。

**Unblock-File** コマンドレットを使用する前に、ファイルとそのソースを確認して、開いても安全であることを確かめてください。

内部的には、 **Unblock-File** コマンドレットは、インターネットからダウンロードされたことを示す "3" の値を持つ、Zone.Identifier 代替データ ストリームを削除します。

PowerShell 実行ポリシーの詳細については、「 [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)」を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: ファイルのブロックを解除する

```
PS C:\> Unblock-File -Path C:\Users\User01\Documents\Downloads\PowerShellTips.chm
```

このコマンドは、PowerShellTips.chm ファイルをブロック解除します。

### 例 2: 複数のファイルのブロックを解除する

```
PS C:\> dir C:\Downloads\*PowerShell* | Unblock-File
```

このコマンドは、C:\Downloads ディレクトリにある、ファイル名に"PowerShell" が使用されているすべてのファイルをブロック解除します。
すべてのファイルが安全なことを確認してから、コマンドを実行してください。

### 例 3: スクリプトを検索してブロックを解除する

```
The first command uses the *Stream* parameter of the Get-Item cmdlet get files with the Zone.Identifier stream.Although you could pipe the output directly to the **Unblock-File** cmdlet (Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue | ForEach {Unblock-File $_.FileName}), it is prudent to review the file and confirm that it is safe before unblocking.
PS C:\> Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue
   FileName: C:\ps-test\Start-ActivityTracker.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

The second command shows what happens when you run a blocked script in a PowerShell session in which the execution policy is **RemoteSigned**. The RemoteSigned policy prevents you from running scripts that are downloaded from the Internet unless they are digitally signed.
PS C:\> C:\ps-test\Start-ActivityTracker.ps1
c:\ps-test\Start-ActivityTracker.ps1 : File c:\ps-test\Start-ActivityTracker.ps1 cannot
be loaded. The file c:\ps-test\Start-ActivityTracker.ps1 is not digitally signed. The script
will not execute on the system. For more information, see about_Execution_Policies.

At line:1 char:1
+ c:\ps-test\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

The third command uses the **Unblock-File** cmdlet to unblock the script so it can run in the session.
PS C:\> Get-Item C:\ps-test\Start-ActivityTracker.ps1 | Unblock-File
```

このコマンドは、PowerShell スクリプトを検索してブロックを解除する方法を示しています。

## PARAMETERS

### -LiteralPath
ブロックを解除するファイルを指定します。
*Path* と異なり、 *LiteralPath* パラメーターの値は入力したとおりに使用されます。
ワイルドカードとして解釈される文字はありません。
パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。
単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
ブロックを解除するファイルを指定します。
ワイルドカード文字がサポートされています。

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
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

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### System.String

パイプを使用してファイル パスを **Unblock-File** に渡すことができます。

## 出力

### なし

このコマンドレットは出力を生成しません。

## 注

* **Unblock-File** コマンドレットはファイル システム ドライブでのみ機能します。
* **ブロック解除-** ファイルエクスプローラーの [ **プロパティ** ] ダイアログボックスの [ **ブロック解除** ] ボタンと同じ操作を実行します。
* ブロックされていないファイルで **Unblock-File** コマンドレットを使用しても、ブロックされていないファイルが影響を受けることはなく、コマンドレットはエラーを生成しません。

## 関連リンク

[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[Get-Item](../Microsoft.PowerShell.Management/Get-Item.md)

[Out-File](Out-File.md)

[FileSystem プロバイダー](../Microsoft.PowerShell.Core/about/about_FileSystem_Provider.md)
