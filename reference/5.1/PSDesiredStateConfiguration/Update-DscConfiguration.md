---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/update-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-DscConfiguration
ms.openlocfilehash: 13365902ab317a3daa41b9a951d5e2fa6e4f1b37
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213571"
---
# Update-DscConfiguration

## 概要
プルサーバーで更新された構成を確認し、適用します。

## SYNTAX

### ComputerNameSet (既定値)

```
Update-DscConfiguration [-Wait] [-JobName <String>] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CimSessionSet

```
Update-DscConfiguration [-Wait] [-JobName <String>] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
`Update-DscConfiguration`コマンドレットは、プルサーバーに接続し、ノードの現在の構成と異なる場合は構成をダウンロードしてから、構成をコンピューターに適用します。

このコマンドレットは、Microsoft サポートライブラリの [WINDOWS RT 8.1、Windows 8.1、および Windows Server 2012 R2 の11月2014更新プログラムのロールアップ](https://support.microsoft.com/kb/3000850) の一部としてのみ使用できます。

## 例

### 例 1: 構成を更新する

```
PS C:\> Update-DscConfiguration -Wait -Verbose
```

このコマンドを実行すると、サーバーは登録されたプルサービスに接続し、割り当てられている最新の構成をダウンロードして適用します。
-Wait および-Verbose パラメーターは省略可能です。
対話形式で作業すると、これらのパラメーターを組み合わせることにより、構成を適用する際の進行状況と成功または失敗に関するリアルタイムのフィードバックが可能になります。

### 例 2: CIM セッション経由で接続して構成を更新する

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Update-DscConfiguration -CimSession $Session -Wait
```

最初のコマンドは、 **New-CimSession** コマンドレットを使用して CIM セッションを作成し、 **CimSession** オブジェクトを $Session 変数に格納します。
コマンドはパスワードの入力をユーザーに求めます。
詳細を表示するには「`Get-Help New-CimSession`」を入力します。

2番目のコマンドは $Session に格納されている **CimSession** で指定されたコンピューターを更新します。
このコマンドは、 *Wait* パラメーターを指定します。
コンソールでは、現在のコマンドが終了するまで追加のコマンドは受け入れられません。

## PARAMETERS

### -CimSession
リモート セッションまたはリモート コンピューターでコマンドレットを実行します。
コンピューター名またはセッションオブジェクト ( [CimSession](/powershell/module/cimcmdlets/new-cimsession) または [CimSession](/powershell/module/cimcmdlets/get-cimsession) コマンドレットの出力など) を入力します。
既定値は、ローカル コンピューターで実行中の現在のセッションです。

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
コンピューター名の配列を指定します。
コマンドレットでは、このパラメーターで指定したコンピューターに構成設定を適用します。

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
ターゲット コンピューターに対して、ユーザー名とパスワードを、 **PSCredential** オブジェクトとして指定します。
**PSCredential** オブジェクトを取得するには、Get-Credential コマンドレットを使用します。
詳細を表示するには「`Get-Help Get-Credential`」を入力します。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobName
ジョブのフレンドリ名を指定します。
このパラメーターを指定すると、コマンドレットがジョブとして実行され、 **Job** オブジェクトを返します。

既定では、Windows PowerShell は JobN という名前を割り当てます。ここで、N は整数です。

*Wait* パラメーターを指定した場合は、このパラメーターを指定しないでください。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

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

### -Wait
コマンドレットによって、すべての構成タスクが完了するまでコンソールがブロックされることを示します。

このパラメーターを指定した場合は、 *JobName* パラメーターを指定しないでください。

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

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Stop-DscConfiguration](Stop-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)
