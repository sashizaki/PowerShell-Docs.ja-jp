---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Module
ms.openlocfilehash: 77a89a9189d3ae8f7c3450bdddbe9456b4e941c7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212619"
---
# Uninstall-Module

## 概要
モジュールをアンインストールします。

## SYNTAX

### NameParameterSet (既定値)

```
Uninstall-Module [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject

```
Uninstall-Module [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description

`Uninstall-Module`コマンドレットは、指定されたモジュールをローカルコンピューターからアンインストールします。 モジュールが依存関係として他のモジュールを持っている場合、モジュールをアンインストールすることはできません。

## 例

### 例 1: モジュールをアンインストールする

この例では、モジュールをアンインストールします。

```powershell
Uninstall-Module -Name SpeculationControl
```

`Uninstall-Module`**Name** パラメーターを使用して、ローカルコンピューターからアンインストールするモジュールを指定します。

### 例 2: パイプラインを使用してモジュールをアンインストールする

この例では、パイプラインを使用してモジュールをアンインストールします。

```powershell
Get-InstalledModule -Name SpeculationControl | Uninstall-Module
```

`Get-InstalledModule`**Name** パラメーターを使用してモジュールを指定します。 オブジェクトは、にパイプラインで送信され、 `Uninstall-Module` アンインストールされます。

## PARAMETERS

### -AllowPrerelease リリース

プレリリースとしてマークされているモジュールをアンインストールできます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllVersions

モジュールの使用可能なすべてのバージョンを含めることを指定します。 **AllVersions** パラメーターは、 **MinimumVersion** 、 **MaximumVersion** 、または **RequiredVersion** パラメーターと共に使用することはできません。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

を実行する前に確認メッセージを表示し `Uninstall-Module` ます。

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

### -Force

`Uninstall-Module`ユーザーの確認を求めることなく強制的に実行します。

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

### -InputObject

**できる psrepositoryiteminfo** オブジェクトを受け取ります。 たとえば、 `Get-InstalledModule` 変数に出力し、その変数を **InputObject** 引数として使用します。

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -MaximumVersion

アンインストールするモジュールの最大バージョンまたは最新バージョンを指定します。 **MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinimumVersion

アンインストールするモジュールの最小バージョンを指定します。 **MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

アンインストールするモジュール名の配列を指定します。

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequiredVersion

アンインストールするモジュールの正確なバージョン番号を指定します。

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf

が実行された場合に何が起こるか `Uninstall-Module` を示します。 コマンドレットは実行されません。

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

### System.String[]

### システムの管理. PSObject []

### System.String

## 出力

### System.Object

## 注

## 関連リンク

[Find-Module](Find-Module.md)

[Get-InstalledModule](Get-InstalledModule.md)

[Publish-Module](Publish-Module.md)

[Save-Module](Save-Module.md)

[Update-Module](Update-Module.md)

