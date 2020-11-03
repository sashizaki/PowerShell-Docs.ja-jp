---
external help file: Stop-DscConfiguration.cdxml-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/19/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/stop-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-DscConfiguration
ms.openlocfilehash: 93c8585ae948dfa360a2ae8e2563670de8fd6e93
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213600"
---
# Stop-DscConfiguration

## 概要
実行中の構成ジョブを停止します。

## SYNTAX

### All

```
Stop-DscConfiguration [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description

`Stop-DscConfiguration`コマンドレットでは、実行中の構成ジョブを停止します。 Common Information Model (CIM) セッションを使用して、このコマンドレットが適用されるコンピューターを指定します。 構成ジョブが実行されていない場合、このコマンドレットは警告メッセージを返します。

`Stop-DscConfiguration` は、Microsoft サポートライブラリの [WINDOWS RT 8.1、Windows 8.1、および Windows Server 2012 R2 の2014年11月の更新プログラムのロールアップ](https://support.microsoft.com/kb/3000850) の一部としてのみ使用できます。 このコマンドレットを使用する前に、「 [Windows PowerShell 5.0 の新機能](/powershell/scripting/whats-new/What-s-New-in-Windows-PowerShell-50)」の情報を確認してください。

## 例

### 例 1: 構成ジョブを停止する

この例では、コマンドレットを使用して CIM セッションを作成し `New-CimSession` ます。 **CimSession** オブジェクトは、実行中の構成ジョブを停止するために使用されます。

```powershell
$Session = New-CimSession -ComputerName Server01 -Credential ACCOUNTS\User01
Stop-DscConfiguration -CimSession $Session
```

`New-CimSession`**ComputerName** パラメーターを使用して、Server01 コンピューターを指定します。 **Credential** パラメーターでは、ユーザーアカウントを指定します。 **CimSession** オブジェクトは変数に格納され `$Session` ます。 コマンドを実行すると、ユーザーアカウントのパスワードを入力するように求められます。

`Stop-DscConfiguration` では、 **CimSession** パラメーターと、に格納されているオブジェクトを使用して、 `$Session` 構成ジョブを停止します。

## PARAMETERS

### -AsJob

このコマンドレットによってコマンドがバックグラウンドジョブとして実行されることを示します。 PowerShell バックグラウンドジョブの詳細については、「 [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) 」および「 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md)」を参照してください。

**AsJob** パラメーターを使用するには、ローカルコンピューターとリモートコンピューターがリモート処理用に構成されている必要があります。 Windows Vista 以降のバージョンの Windows オペレーティングシステムでは、[ **管理者として実行** ] オプションを使用して PowerShell を開く必要があります。 詳細については、「[about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)」を参照してください。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

リモート セッションまたはリモート コンピューターでコマンドレットを実行します。 コンピューター名またはセッションオブジェクト (またはからの出力など) を入力し `New-CimSession` `Get-CimSession` ます。

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

### -Confirm

`Stop-DscConfiguration`**Confirm** パラメーターはサポートされていません。 **Confirm** パラメーターが使用されている場合は、エラーが表示されます。

**確認** をサポートしている PowerShell コマンドレットの場合、パラメーターを使用すると、コマンドを実行する前に確認メッセージが表示されます。

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

ユーザーに確認せずに、直ちにコマンドを実行します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

コマンドレットを実行するために確立できる最大並行処理数を指定します。

このパラメーターを省略した場合、または値を入力した場合 `0` 、PowerShell では、コンピューターで実行されている CIM コマンドレットの数に基づいて、最適なスロットル制限が計算されます。 調整限度は、現在のコマンドレットのみに適用されます。セッションやコンピューターには適用されません。

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

### -WhatIf

コマンドレットの実行時に発生する内容を示します。 コマンドレットは実行されません。

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

### なし

## 出力

### なし

## 注

## 関連リンク

[Get-CimSession](../CimCmdlets/Get-CimSession.md)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[New-CimSession](../CimCmdlets/New-CimSession.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)

[Update-DscConfiguration](Update-DscConfiguration.md)

[Windows PowerShell Desired State Configuration の概要](/powershell/scripting/dsc/overview/overview)
