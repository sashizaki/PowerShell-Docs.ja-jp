---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-packageprovider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-PackageProvider
ms.openlocfilehash: ceae77cb6ef2e36f62da7872e9592292e6065ada
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214824"
---
# Install-PackageProvider

## 概要
1つまたは複数の Package Management パッケージプロバイダーをインストールします。

## SYNTAX

### PackageBySearch (既定)

```
Install-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Credential <PSCredential>] [-Scope <String>] [-Source <String[]>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### PackageByInputObject

```
Install-PackageProvider [-Scope <String>] [-InputObject] <SoftwareIdentity[]> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## Description

**Install-PackageProvider** コマンドレットは、 **PowerShellGet** に登録されているパッケージソースで使用できる、一致する Package Management プロバイダーをインストールします。
既定では、 **PackageManagement** タグを持つ PowerShell ギャラリーで利用できるモジュールが含まれます。
**PowerShellGet** Package Management プロバイダーは、これらのリポジトリ内のプロバイダーを検索するために使用されます。

このコマンドレットは、Package Management ブートストラップアプリケーションを使用して使用できる一致する Package Management プロバイダーもインストールします。

このコマンドレットは、Package Management Azure Blob ストアで利用できる一致する Package Management プロバイダーもインストールします。
ブートストラッププロバイダーを使用して、それらを検索してインストールします。

最初に実行するには、PackageManagement が Nuget パッケージプロバイダーをダウンロードするためにインターネット接続を必要とします。
ただし、コンピューターがインターネットに接続されておらず、Nuget または PowerShellGet プロバイダーを使用する必要がある場合は、それらを別のコンピューターにダウンロードして、対象のコンピューターにコピーすることができます。
これを行うには、次の手順を使用します。

1.
を実行し `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` て、インターネットに接続されたコンピューターからプロバイダーをインストールします。

2.
インストール後、またはにインストールされているプロバイダーを見つけることができ `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\\\<ProviderName\>\\\<ProviderVersion\>` `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\\\<ProviderName\>\\\<ProviderVersion\>` ます。

3.
\<ProviderName\>フォルダー (この場合は Nuget フォルダー) を、ターゲットコンピューター上の対応する場所に配置します。
ターゲットコンピューターが Nano server の場合は、Nano Server から **Install-PackageProvider** を実行して、正しい Nuget バイナリをダウンロードする必要があります。

4.
PowerShell を再起動して、パッケージプロバイダーを自動読み込みします。
または、を実行して、 `Get-PackageProvider -ListAvailable` コンピューターで使用可能なすべてのパッケージプロバイダーを一覧表示します。
次に、を使用して、 `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` 現在の PowerShell セッションにプロバイダーをインポートします。

## 例

### 例 1: PowerShell ギャラリーからパッケージプロバイダーをインストールする

```
PS C:\> Install-PackageProvider -Name "Gistprovider" -Verbose
```

このコマンドは、PowerShell ギャラリーから Gistprovider をインストールします。

### 例 2: 指定したバージョンのパッケージプロバイダーをインストールする

```
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
PS C:\> Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.216" -Force
```

この例では、指定されたバージョンの Nuget パッケージプロバイダーをインストールします。

最初のコマンドは、Nuget という名前のパッケージプロバイダーのすべてのバージョンを検索します。
2番目のコマンドは、指定されたバージョンの Nuget パッケージプロバイダーをインストールします。

### 例 3: プロバイダーを検索してインストールする

```
PS C:\> Find-PackageProvider -Name "Gistprovider" | Install-PackageProvider -Verbose
```

このコマンドは、 **検索 packageprovider** とパイプラインを使用して、Gist プロバイダーを検索してインストールします。

### 例 4: 現在のユーザーのモジュールフォルダーにプロバイダーをインストールする

```
PS C:\> Install-PackageProvider -Name Gistprovider -Verbose -Scope CurrentUser
```

このコマンドは、現在のユーザーのみが使用できるように $env: Localappdata\packagemanagement\providerassemblies からにパッケージプロバイダーをインストールします。

## PARAMETERS

### -AllVersions

このコマンドレットによって、使用可能なすべてのバージョンのパッケージプロバイダーがインストールされることを示します。
既定では、 **Install-PackageProvider** は、使用可能な最も高いバージョンのみを返します。

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

### -Credential

パッケージプロバイダーをインストールするアクセス許可を持つユーザーアカウントを指定します。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

このコマンドレットが強制的に実行できるこのコマンドレットのすべての操作を強制することを示します。
現時点では、 *Force* パラメーターは *forcebootstrap* パラメーターと同じように動作します。

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

このコマンドレットによってパッケージプロバイダーが自動的にインストールされることを示します。

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

**ソフトウェア id** オブジェクトを指定します。
**検索 packageprovider** コマンドレットを使用して、 **Install-packageprovider** にパイプするための **ソフトウェア id** オブジェクトを取得します。

```yaml
Type: Microsoft.PackageManagement.Packaging.SoftwareIdentity[]
Parameter Sets: PackageByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaximumVersion

インストールするパッケージプロバイダーの許可される最大バージョンを指定します。
このパラメーターを追加しない場合、 **インストール-PackageProvider** は、使用可能な最も高いバージョンのプロバイダーをインストールします。

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumVersion

インストールするパッケージプロバイダーの許可される最小バージョンを指定します。
このパラメーターを追加しない場合、 **Install-PackageProvider** は、 *MaximumVersion* パラメーターで指定された要件を満たす、利用可能な最も高いバージョンのパッケージをインストールします。

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

1つまたは複数のパッケージプロバイダーモジュール名を指定します。
複数のパッケージ名はコンマで区切ります。
ワイルドカード文字はサポートされていません。

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -プロキシ

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyCredential

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

### -RequiredVersion

インストールするパッケージプロバイダーの完全に許可されているバージョンを指定します。
このパラメーターを追加しない場合、 **Install-PackageProvider** は、 *MaximumVersion* パラメーターで指定された最大バージョンも満たすプロバイダーの利用可能な最も高いバージョンをインストールします。

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -スコープ

プロバイダーのインストールスコープを指定します。
このパラメーターに指定できる値は、 **AllUsers** と **CurrentUser** です。

**AllUsers** スコープは、コンピューターのすべてのユーザーがアクセスできる場所にプロバイダーをインストールします。
既定では、これは **$env:P rogramfiles\packagemanagement\providerassemblies.**

**CurrentUser** スコープでは、現在のユーザーだけがアクセスできる場所にプロバイダーがインストールされます。
既定では **$env: LOCALAPPDATA\PackageManagement\ProviderAssemblies.**

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

1つまたは複数のパッケージソースを指定します。
使用可能なパッケージソースの一覧を取得するには、Get-PackageSource コマンドレットを使用します。

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### Microsoft. パッケージ Id

パイプを使用して、このコマンドレットに **ソフトウェア id** オブジェクトをパイプすることができます。
Find-PackageProvider を使用して、 **インストール-PackageProvider** にパイプできる **ソフトウェア id** オブジェクトを取得します。

## 出力

## 注

## 関連リンク

[Find-PackageProvider](Find-PackageProvider.md)

[Get-PackageProvider](Get-PackageProvider.md)

[Import-PackageProvider](Import-PackageProvider.md)
