---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSProvider
ms.openlocfilehash: 997d86460837946a2cf18fc78f058f21472dd909
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215400"
---
# Get-PSProvider

## 概要
指定した Windows PowerShell プロバイダーに関する情報を取得します。

## SYNTAX

```
Get-PSProvider [[-PSProvider] <String[]>] [<CommonParameters>]
```

## Description
**Get PSProvider** コマンドレットは、現在のセッションの Windows PowerShell プロバイダーを取得します。
セッション内の特定のドライブを取得することも、すべてのドライブを取得することもできます。

Windows PowerShell プロバイダーを使用すると、さまざまなデータ ストアにファイル システム ドライブと同様にアクセスできます。
Windows PowerShell プロバイダーの詳細については、「about_Providers」を参照してください。

## 例

### 例 1: 使用可能なすべてのプロバイダーの一覧を表示する

```
PS C:\> Get-PSProvider
```

このコマンドを実行すると、利用可能なすべての Windows PowerShell プロバイダーの一覧が表示されます。

### 例 2: 指定した文字で始まるすべての Windows PowerShell プロバイダーの一覧を表示する

```
PS C:\> Get-PSProvider f*, r* | Format-List
```

このコマンドは、名前が f または r で始まるすべての Windows PowerShell プロバイダーの一覧を表示します。

### 例 3: プロバイダーをセッションに追加したスナップインまたはモジュールを検索する

```
PS C:\> Get-PSProvider | Format-Table name, module, pssnapin -auto

Name        Module       PSSnapIn
----        ------       --------
Test        TestModule
WSMan                    Microsoft.WSMan.Management
Alias                    Microsoft.PowerShell.Core
Environment              Microsoft.PowerShell.Core
FileSystem               Microsoft.PowerShell.Core
Function                 Microsoft.PowerShell.Core
Registry                 Microsoft.PowerShell.Core
Variable                 Microsoft.PowerShell.Core
Certificate              Microsoft.PowerShell.Security

PS C:\> Get-PSProvider | Where {$_.pssnapin -eq "Microsoft.PowerShell.Security"}

Name            Capabilities      Drives
----            ------------      ------
Certificate     ShouldProcess     {cert}
```

これらのコマンドは、セッションにプロバイダーを追加した Windows PowerShell スナップインまたはモジュールを見つけます。
プロバイダーを含むすべての Windows PowerShell 要素は、スナップインまたはモジュールから取得されます。

これらのコマンドは、Add-pssnapin **プロバイダー** が返す **providerinfo** オブジェクトのプロパティとモジュールのプロパティを使用します。
これらのプロパティの値には、プロバイダーを追加するスナップインまたはモジュールの名前が含まれます。

最初のコマンドは、セッションのすべてのプロバイダーを取得し、Name、Module、および PSSnapin プロパティの値を含め、表形式に書式設定します。

2番目のコマンドは、Where-Object コマンドレットを使用して、 **Microsoft. PowerShell** スナップインから取得されたプロバイダーを取得します。

### 例 4: ファイルシステムプロバイダーの Home プロパティのパスを解決する

```
PS C:\> Resolve-Path ~

Path
----
C:\Users\User01

PS C:\> (get-psprovider FileSystem).home
C:\Users\User01
```

この例では、チルダ記号 (~) が FileSystem プロバイダーの Home プロパティの値を表すことを示します。
Home プロパティの値は省略可能ですが、FileSystem プロバイダーの場合は $env: homedrive \$ env: ホームパスまたは $home として定義されます。

## PARAMETERS

### -PSProvider
このコマンドレットが情報を取得する Windows PowerShell プロバイダーの名前を指定します。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### String[]

パイプを使用して、1つまたは複数のプロバイダー名文字列をこのコマンドレットに渡します。

## 出力

### システムの管理. ProviderInfo
このコマンドレットは、セッション内の Windows PowerShell プロバイダーを表すオブジェクトを返します。

## 注

## 関連リンク

## 関連リンク
