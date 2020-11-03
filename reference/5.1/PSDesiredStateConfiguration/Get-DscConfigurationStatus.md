---
external help file: Get-DscConfigurationStatus.cdxml-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfigurationstatus?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfigurationStatus
ms.openlocfilehash: 0d59ce58a70eab68441ea1fe6097bbdf7792a54f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215363"
---
# Get-DscConfigurationStatus

## 概要
完了した構成の実行に関するデータを取得します。

## SYNTAX

```
Get-DscConfigurationStatus [-All] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## Description
**Get DscConfigurationStatus** コマンドレットは、システムで完了した構成の実行に関する詳細情報を取得します。
既定では、最後の構成の実行に関する情報が返されます。
このコマンドレットは、構成が実行された日時、実行の状態、構成内のリソースの数、成功または失敗したリソースなど、構成の実行に関する履歴情報を見つけるのに役立ちます。

## 例

### 例 1: 最後の構成の実行に関する情報を取得する

```
PS C:\> Get-DscConfigurationStatus
```

このコマンドは、最後の構成の実行に関する情報を取得します。

### 例 2: すべての構成に関する情報を取得する

```
PS C:\> Get-DscConfigurationStatus -All
```

このコマンドは、Windows PowerShell Desired State Configuration (DSC) 整合性チェックを含む、システムで実行されたすべての構成に関する情報を取得します。

### 例 3: リモートコンピューターでの構成の実行に関する情報を取得する

```
PS C:\> Get-DscConfigurationStatus -CimSession "Server01"
```

このコマンドは、Server01 という名前のリモートコンピューターの構成実行の詳細を取得します。
これは、WSMan トランスポートを使用してリモートコンピューターに接続し、接続しているユーザーがリモートコンピューターの管理者である必要があります。

## PARAMETERS

### -All
このコマンドレットが、構成アプリケーションや整合性チェックなど、コンピューター上のすべての構成の実行に関する情報を取得することを示します。

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

### -AsJob
このコマンドレットによってコマンドがバックグラウンドジョブとして実行されることを示します。

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

### -CimSession
リモート セッションまたはリモート コンピューターでコマンドレットを実行します。
コンピューター名またはセッションオブジェクト ( [CimSession](/powershell/module/cimcmdlets/new-cimsession) または [CimSession](/powershell/module/cimcmdlets/get-cimsession) コマンドレットの出力など) を入力します。
既定値は、ローカル コンピューターで実行中の現在のセッションです。

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
コマンドレットを実行するために確立できる最大並行処理数を指定します。
このパラメーターを省略した場合、または値を入力した場合 `0` 、Windows PowerShell は、コンピューターで実行されている CIM コマンドレットの数に基づいて、コマンドレットに最適なスロットル制限を計算します。
調整限度は、現在のコマンドレットのみに適用されます。セッションやコンピューターには適用されません。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

## 出力

## 注

## 関連リンク

[Windows PowerShell Desired State Configuration の概要](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscLocalConfigurationManager](Get-DscLocalConfigurationManager.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)
