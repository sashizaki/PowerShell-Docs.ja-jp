---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ControlPanelItem
ms.openlocfilehash: 51bc04b4de901a611330266b6b0f58471f998432
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215475"
---
# Get-ControlPanelItem

## 概要
コントロール パネル項目を取得します。

## SYNTAX

### RegularName (既定値)

```
Get-ControlPanelItem [[-Name] <String[]>] [-Category <String[]>] [<CommonParameters>]
```

### CanonicalName

```
Get-ControlPanelItem -CanonicalName <String[]> [-Category <String[]>] [<CommonParameters>]
```

## Description

`Get-ControlPanelItem`コマンドレットは、ローカルコンピューター上のコントロールパネル項目を取得します。 ユーザー インターフェイスを持たないシステムであっても、名前、カテゴリ、または説明によってコントロール パネル項目を探すことができます。

このコマンドレットは、システムで開くことができるコントロールパネル項目だけを取得します。 コントロールパネルまたはエクスプローラーがインストールされていないコンピューターでは、このコマンドレットは、これらのコンポーネントなしで開くことができるコントロールパネル項目だけを取得します。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。 Windows 8 と Windows Server 2012 以降でのみ動作します。

## 例

### 例 1: すべてのコントロール パネル項目を取得する

このコマンドは、ローカル コンピューター上のすべてのコントロール パネル項目を取得します。

```powershell
Get-ControlPanelItem
```

```Output
Name                          CanonicalName                 Category                      Description
----                          -------------                 --------                      -----------
Action Center                 Microsoft.ActionCenter        {System and Security}         Review recent messages and...
Administrative Tools          Microsoft.AdministrativeTools {System and Security}         Configure administrative s...
AutoPlay                      Microsoft.AutoPlay            {Hardware}                    Change default settings fo...
BitLocker Drive Encryption    Microsoft.BitLockerDriveEn... {System and Security}         Protect your computer usin...
Color Management              Microsoft.ColorManagement     {All Control Panel Items}     Change advanced color mana...
Credential Manager            Microsoft.CredentialManager   {User Accounts}               Manage your Windows Creden...
Date and Time                 Microsoft.DateAndTime         {Clock, Language, and Region} Set the date, time, and ti...
...
```

### 例 2: コントロール パネル項目を名前で取得する

この例では、名前にプログラムまたはアプリが含まれているコントロールパネル項目を取得します。

```powershell
Get-ControlPanelItem -Name "*Program*", "*App*"
```

### 例 3: コントロール パネル項目をカテゴリで取得する

このコマンドは、名前にセキュリティが設定されているカテゴリのすべてのコントロールパネル項目を取得します。

```powershell
Get-ControlPanelItem -Category "*Security*"
```

### 例 4: コントロール パネル項目を開く

この例では、ローカルコンピューターの [Windows ファイアウォール] コントロールパネル項目を開きます。

```powershell
Get-ControlPanelItem -Name "Windows Firewall" | Show-ControlPanelItem
```

`Get-ControlPanelItem`コマンドレットでは、コントロールパネル項目を取得します。 コマンドレットにより、 `Show-ControlPanelItem` ファイルが開きます。

### 例 5: リモート コンピューター上のコントロール パネル項目を取得する

この例では、Server01 リモートコンピューター上のコントロールパネルの BitLocker ドライブ暗号化項目を取得します。
コマンドレットは、 `Invoke-Command` `Get-ControlPanelItem` コマンドレットをリモートで実行します。

```powershell
Invoke-Command -ComputerName "Server01" {Get-ControlPanelItem -Name "BitLocker*" }
```

### 例 6: コントロール パネル項目の説明を検索する

この例では、[コントロールパネル] 項目の [ **説明** ] プロパティを検索して、name **デバイス** を含むものだけを取得します。

```powershell
Get-ControlPanelItem | Where-Object {$_.Description -like "*Device*"}
```

```Output
Name                    CanonicalName                 Category    Description
----                    -------------                 --------    -----------
AutoPlay                Microsoft.AutoPlay            {Hardware}  Change default settings fo...
Devices and Printers    Microsoft.DevicesAndPrinters  {Hardware}  View and manage devices, p...
Sound                   Microsoft.Sound               {Hardware}  Configure your audio devic...
```

コマンドレットでは、 `Get-ControlPanelItem` すべてのコントロールパネル項目を取得します。 `Where-Object`コマンドレットは、 **Description** プロパティの値で項目をフィルター処理します。

## PARAMETERS

### -CanonicalName

コントロールパネルの項目を文字列配列として指定します。これらの項目は、このコマンドレットによって取得される正規名または名前パターンによって指定されます。 ワイルドカードを使用できます。 複数の名前を入力すると、このコマンドレットは、名前リスト内の項目が "or" 演算子で区切られた場合と同様に、任意の名前に一致するコントロールパネル項目を取得します。

既定では、このコマンドレットは、システム内のすべてのコントロールパネル項目を取得します。

```yaml
Type: System.String[]
Parameter Sets: CanonicalName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -カテゴリ

このコマンドレットが取得する指定されたカテゴリのコントロールパネル項目のカテゴリを文字列配列として指定します。 カテゴリ名または名前パターンを入力します。 ワイルドカードを使用できます。 複数の名前を入力すると、このコマンドレットは、名前リスト内の項目が "or" 演算子で区切られた場合と同様に、任意の名前に一致するコントロールパネル項目を取得します。 既定では、このコマンドレットは、システム内のすべてのコントロールパネル項目を取得します。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Name

このコマンドレットが取得するコントロールパネルの名前または名前パターンを文字列配列として指定します。
ワイルドカードを使用できます。 このコマンドレットには、パイプを使用して名前または名前パターンを指定することもできます。

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### System.String

このコマンドレットには、名前または名前パターンをパイプすることができます。

## 出力

### Microsoft. PowerShell. Controlaccess Item

このコマンドレットは、ローカルコンピューター上のコントロールパネル項目を取得します。

## 注

## 関連リンク

[Show-ControlPanelItem](Show-ControlPanelItem.md)
