---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packageprovider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageProvider
ms.openlocfilehash: 43f70d400cc2d9b81e2bf59a6d2b3bb986737c69
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210456"
---
# Get-PackageProvider

## 概要
Package Management に接続されているパッケージプロバイダーの一覧を返します。

## SYNTAX

```
Get-PackageProvider [[-Name] <String[]>] [-ListAvailable] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## Description

**Get PackageProvider** コマンドレットは、Package Management に接続されているパッケージプロバイダーの一覧を返します。
これらのプロバイダーの例には、PSModule、NuGet、Chocolatey などがあります。
1つまたは複数のプロバイダー名の全体または一部に基づいて結果をフィルター処理できます。

## 例

### 例 1: 現在読み込まれているすべてのパッケージプロバイダーを取得する

```
PS C:\> Get-PackageProvider
```

このコマンドは、ローカルコンピューターに現在読み込まれているすべてのパッケージプロバイダーの一覧を取得します。

### 例 2: 使用可能なすべてのパッケージプロバイダーを取得する

```
PS C:\> Get-PackageProvider -ListAvailable
```

このコマンドは、ローカルコンピューターで使用可能なすべてのパッケージプロバイダーの一覧を取得します。

### 例 3: パッケージプロバイダーを動的に取得する

```
PS C:\> Get-PackageProvider -Name "Chocolatey" -ForceBootstrap
```

このコマンドを実行すると、コンピューターに Chocolatey プロバイダーがインストールされていない場合に、Chocolatey プロバイダーが自動的にインストールされます。

## PARAMETERS

### -Force

このコマンドレットが強制的に実行できるこのコマンドレットの他のすべての操作を強制することを示します。
**Get-PackageProvider** では、 *Force* パラメーターが *forcebootstrap* パラメーターと同じように動作することを意味します。

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

### -ForceBootstrap

このコマンドレットによって、パッケージプロバイダーを自動的にインストールするように Package Management を強制することを示します。

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

### -ListAvailable

インストールされているすべてのプロバイダーを取得します。
**PSModulePath** 環境変数およびパッケージプロバイダーアセンブリフォルダーに一覧表示されているパス **で、プロバイダーを取得** します。

**$env:P rogramfiles\packagemanagement\providerassemblies** **$env: localappdata\packagemanagement\providerassemblies から**

このパラメーターを指定しない場合、 **Get PackageProvider** は、現在のセッションに読み込まれているプロバイダーのみを取得します。

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

### -Name

1つまたは複数のプロバイダー名、またはプロバイダー名の一部を指定します。
複数のプロバイダー名はコンマで区切ります。
このパラメーターの有効な値には、パッケージと共にインストールしたプロバイダーの名前が含まれます。PackageManagement には、 **Psmodule** および **MSI** プロバイダーを含む、既定のプロバイダーのセットが付属しています。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

## 出力

### PackageProvider []

## 注

## 関連リンク

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[Get-PackageSource](Get-PackageSource.md)

[Register-PackageSource](Register-PackageSource.md)

[Unregister-PackageSource](Unregister-PackageSource.md)
