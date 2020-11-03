---
external help file: Restore-DSCConfiguration.cdxml-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/restore-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-DscConfiguration
ms.openlocfilehash: 823032f7665d9ec83faa59c37560510e049efdd2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215296"
---
# Restore-DscConfiguration

## 概要
ノードの以前の構成を再適用します。

## SYNTAX

```
Restore-DscConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## Description
前の構成が存在する場合は、 **start-dscconfiguration** コマンドレットによって、以前の構成がノードに再適用されます。
Common Information Model (CIM) セッションを使用してコンピューターを指定します。
ターゲット コンピューターを指定しない場合、コマンドレットではローカル コンピューターの構成を復元します。
特定のノードの以前の構成がない場合、このコマンドレットはエラーメッセージを返します。

このコマンドレットでは **Confirm** パラメーターはサポートされていません。

## 例

### 例 1: ローカルコンピューターの構成を復元する

```
PS C:\> Restore-DscConfiguration
```

以下のコマンドは、ローカル コンピューターの構成を復元します。

### 例 2: 指定したコンピューターの構成を復元する

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Restore-DscConfiguration -CimSession $Session
```

この例では、CIM セッションによって指定されたコンピューター上で構成を復元します。
例では、コマンドレットで使用するために、Server01 という名前のコンピューター用に CIM セッションを作成します。
または、CIM セッションの配列を作成して、指定した複数のコンピューターにコマンドレットを適用します。

最初のコマンドは、 **New-CimSession** コマンドレットを使用して CIM セッションを作成し、 **CimSession** オブジェクトを $Session 変数に格納します。
コマンドはパスワードの入力をユーザーに求めます。
詳細を表示するには「`Get-Help New-CimSession`」を入力します。

2 番目のコマンドは、 **$Session** 変数に格納された CimSession オブジェクトによって識別されるコンピューター (この場合は、Server01 という名前のコンピューター) の構成を復元します。

## PARAMETERS

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
コンピューター名またはセッションオブジェクト ( **CimSession** または **CimSession** コマンドレットの出力など) を入力します。

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

## 出力

## 注

## 関連リンク

[Windows PowerShell Desired State Configuration の概要](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)
