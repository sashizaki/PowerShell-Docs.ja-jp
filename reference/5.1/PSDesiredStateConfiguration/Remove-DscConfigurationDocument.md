---
external help file: Remove-DscConfigurationDocument.cdxml-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DscConfigurationDocument
ms.openlocfilehash: d3e9b15dfeea94921503247adc08b291eed9d7d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215299"
---
# Remove-DscConfigurationDocument

## 概要
構成ドキュメントを DSC 構成ストアから削除します。

## SYNTAX

```
Remove-DscConfigurationDocument -Stage <Stage> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
`Remove-DscConfigurationDocument`コマンドレットは、Windows PowerShell Desired State configuration (DSC) 構成ストアから構成ドキュメント (.mof ファイル) を削除します。
このコマンドレットは、構成時に、 `Start-DscConfiguration` 対象のコンピューター上のフォルダーに .mof ファイルをコピーします。
このコマンドレットは、その構成ドキュメントを削除し、追加のクリーンアップを行います。

このコマンドレットは、Microsoft サポートライブラリの [WINDOWS RT 8.1、Windows 8.1、および Windows Server 2012 R2 の11月2014更新プログラムのロールアップ](https://support.microsoft.com/kb/3000850) の一部としてのみ使用できます。

## 例

### 例 1: 現在の構成ドキュメントを削除する

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Remove-DscConfigurationDocument -Stage Current -CimSession $Session
```

最初のコマンドは、 **New-CimSession** コマンドレットを使用して CIM セッションを作成し、 **CimSession** オブジェクトを $Session 変数に格納します。
コマンドはパスワードの入力をユーザーに求めます。
詳細を表示するには「`Get-Help New-CimSession`」を入力します。

2番目のコマンドは、$Session に格納されている **CimSession** で指定されたコンピューターの現在の構成ドキュメントを削除します。

## PARAMETERS

### -AsJob
このコマンドレットによってコマンドがバックグラウンドジョブとして実行されることを示します。

*AsJob* パラメーターを指定すると、このコマンドはジョブを表すオブジェクトを返し、コマンドプロンプトを表示します。
ジョブが完了するまで、引き続きセッションで作業を行うことができます。
ジョブは、ローカル コンピューターで作成され、リモート コンピューターでの結果は自動的にローカル コンピューターに返されます。
ジョブを管理するには、Job コマンドレットを使用します。
ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。

このパラメーターを使用するには、ローカルコンピューターとリモートコンピューターがリモート処理用に構成されている必要があります。また、windows Vista 以降のバージョンの Windows オペレーティングシステムでは、[管理者として実行] オプションを使用して Windows PowerShell を開く必要があります。
詳細については、「[about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)」を参照してください。

Windows PowerShell のバックグラウンドジョブの詳細については、「 [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) 」および「 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md)」を参照してください。

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

### -Force
このコマンドレットが構成ドキュメントを削除する前に、実行中の構成ジョブを停止することを示します。
ユーザーに確認せずに、直ちにコマンドを実行します。

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

### -ステージ
削除する構成ドキュメントを指定します。
複数のドキュメントを指定できます。
このパラメーターの有効値は、次のとおりです。

- 現在。
システムの現在の状態を説明する構成ドキュメントを削除します。
- 保留中 
システムの保留中の状態を説明する構成ドキュメントを削除します。
- 前へ。
システムの以前の状態を説明する構成ドキュメントを削除します。

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoveDscConfigurationDocument.Stage
Parameter Sets: (All)
Aliases:
Accepted values: Current, Pending, Previous

Required: True
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

### なし

## 出力

### なし

## 注

## 関連リンク

[Windows PowerShell Desired State Configuration の概要](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)
