---
description: PowerShell_Ise.exe コマンドラインツールの使用方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_ise_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Ise_exe
ms.openlocfilehash: c7500eb6d8586b9dca568edc4e805c577e94bec4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223339"
---
# <a name="about-powershell-iseexe"></a>PowerShell Ise.exe について

## <a name="short-description"></a>概要

PowerShell_Ise.exe コマンドラインツールの使用方法について説明します。

## <a name="long-description"></a>詳細説明

PowerShell_Ise.exe は、Windows PowerShell Integrated Scripting Environment (ISE) セッションを開始します。 これは Cmd.exe と Windows PowerShell で実行できます。

PowerShell_ISE.exe を実行するには、「PowerShell_ISE.exe、PowerShell_ISE、または ISE」と入力します。

## <a name="syntax"></a>SYNTAX

```
PowerShell_Ise[.exe]
PowerShell_ISE[.exe]
ISE[.exe]
[-File]<FilePath[]> [-NoProfile] [-MTA]
-Help | ? | -? | /? Displays the syntax and describes the command-line switches.
```

## <a name="parameters"></a>PARAMETERS

### <a name="-file"></a>-File

Windows PowerShell ISE で指定されたファイルを開きます。 パラメーター名 ("-File") は省略可能です。 複数のファイルを一覧表示するには、1つのテキスト文字列を引用符で囲んで入力します。 文字列内でファイル名を区切るには、コンマを使用します。

次に例を示します。

PowerShell_ISE-ファイル "File1.ps1、File2.ps1、File3.xml"。

Windows PowerShell では、ファイル名の間にスペースが許可されますが、Cmd.exe などの他のプログラムでは正しく解釈されない可能性があります。

このパラメーターを使用すると、Windows PowerShell スクリプトファイルや XML ファイルなど、任意のテキストファイルを開くことができます。

### <a name="-mta"></a>-Mta

マルチスレッドアパートメントを使用して Windows PowerShell ISE を開始します。 このパラメーターは、Windows PowerShell 3.0 で導入されました。 シングルスレッドアパートメント (STA) が既定値です。

### <a name="-noprofile"></a>-NoProfile

では、Windows PowerShell プロファイルは実行されません。 既定では、Windows PowerShell プロファイルはすべてのセッションで実行されます。

異なるプロファイルを持つシステムで実行される関数やスクリプトなど、共有コンテンツを作成する場合は、このパラメーターを使用することをお勧めします。
詳細については、「 [about_Profiles](about_Profiles.md)」を参照してください。

### <a name="-help---"></a>-Help-?,/?

PowerShell_ISE.exe のヘルプを表示します。

## <a name="examples"></a>例

これらのコマンドは Windows PowerShell ISE を開始します。 コマンドは等価であり、同じ意味で使用することができます。

```
PS C:> PowerShell_ISE.exe
PS C:> PowerShell_ISE
PS C:> ISE
```

これらのコマンドは、Windows PowerShell ISE で Get-Profile.ps1 スクリプトを開きます。
コマンドは等価であり、同じ意味で使用することができます。

```
PS C:> PowerShell_ISE.exe -File .\Get-Profile.ps1
PS C:> ISE -File .\Get-Profile.ps1
PS C:> ISE .\Get-Profile.ps1
```

このコマンドは Windows PowerShell ISE で Get-Backups.ps1 スクリプトと Get-BackupInstance.ps1 スクリプトを開きます。 複数のファイルを開くには、コンマを使用してファイル名を区切り、ファイル名の値全体を引用符で囲みます。

```
PS C:> ISE -File ".\Get-Backups.ps1,Get-BackupInstance.ps1"
```

このコマンドは、プロファイルのない Windows PowerShell ISE を開始します。

```
PS C:> ISE -NoProfile
```

このコマンドは、PowerShell_ISE.exe のヘルプを取得します。

```
PS C:> ISE -help
```

## <a name="see-also"></a>関連項目

[about_PowerShell.exe](about_PowerShell_exe.md)

[about_Windows_PowerShell_ISE](about_Windows_PowerShell_ISE.md)

[Windows PowerShell Integrated Scripting Environment (ISE)](/powershell/scripting/windows-powershell/ise/introducing-the-windows-powershell-ise)
