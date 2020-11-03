---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/start-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-DscConfiguration
ms.openlocfilehash: c34754aeb7fce99030cf4ddb235e3e7e8161f3eb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215288"
---
# Start-DscConfiguration

## 概要
ノードに構成を適用します。

## SYNTAX

### ComputerNameAndPathSet (既定)

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CimSessionAndPathSet

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] -CimSession <CimSession[]> [-ThrottleLimit <Int32>]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ComputerNameAndUseExistingSet

```
Start-DscConfiguration [-Wait] [-Force] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-UseExisting] [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CimSessionAndUseExistingSet

```
Start-DscConfiguration [-Wait] [-Force] -CimSession <CimSession[]> [-ThrottleLimit <Int32>] [-UseExisting]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**Start-DscConfiguration** コマンドレットはノードに構成を適用します。
*Useexisting* パラメーターと共に使用すると、ターゲットコンピューター上の既存の構成が適用されます。
コンピューター名を指定するか Common Information Model (CIM) セッションを使用して、構成を適用するコンピューターを指定します。

既定では、このコマンドレットは、ジョブを作成し、 **Job** オブジェクトを返します。
バックグラウンドジョブの詳細については、「」と入力 `Get-Help about_Jobs` してください。
このコマンドレットを対話的に使用するには、 *Wait* パラメーターを指定します。

コマンドレットが構成設定を適用するときの動作内容の詳細を確認するには、 *Verbose* パラメーターを指定します。

## 例

### 例 1: 構成設定を適用する

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\"
```

以下のコマンドは、C:\DSC\Configurations\ からの構成設定を、このフォルダーに設定を持つすべてのコンピューターに適用します。
コマンドは、配置されている対象ノードごとに **Job** オブジェクトを返します。

### 例 2: 構成設定を適用し、構成が完了するまで待機する

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -Wait -Verbose
```

以下のコマンドは、C:\DSC\Configurations\ からの構成をローカル コンピューターに適用します。
コマンドは、配置されている対象ノードごとに **Job** オブジェクトを返します (この場合はローカル コンピューターのみ)。
この例では、 *Verbose* パラメーターを指定します。
そのため、コマンドを実行すると、コンソールにメッセージが送信されます。
このコマンドには、 *Wait* パラメーターが含まれています。
そのため、コマンドがすべての構成タスクを完了するまで、コンソールを使用することはできません。

### 例 3: CIM セッションを使用して構成設定を適用する

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -CimSession $Session
```

この例では、指定したコンピューターに構成設定を適用します。
例では、コマンドレットで使用するために、Server01 という名前のコンピューター用に CIM セッションを作成します。
または、CIM セッションの配列を作成して、指定した複数のコンピューターにコマンドレットを適用します。

最初のコマンドは、 **New-CimSession** コマンドレットを使用して CIM セッションを作成し、 **CimSession** オブジェクトを $Session 変数に格納します。
コマンドはパスワードの入力をユーザーに求めます。
詳細を表示するには「`Get-Help NewCimSession`」を入力します。

2番目のコマンドは、C:\DSC\Configurations\ の構成設定を、$Session 変数に格納されている **CimSession** オブジェクトによって識別されるコンピューターに適用します。
この例で、$Session 変数には、Server01 という名前のコンピューターに対してのみ CIM セッションが含まれています。
コマンドは設定を適用します。
コマンドは、構成されているコンピューターごとに **Job** オブジェクトを作成します。

## PARAMETERS

### -CimSession
リモート セッションまたはリモート コンピューターでコマンドレットを実行します。
コンピューター名またはセッションオブジェクト ( [CimSession](/powershell/module/cimcmdlets/new-cimsession) または [CimSession](/powershell/module/cimcmdlets/get-cimsession) コマンドレットの出力など) を入力します。
既定値は、ローカル コンピューターで実行中の現在のセッションです。

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
コンピューター名の配列を指定します。
このパラメーターは、 *Path* パラメーターに構成ドキュメントがあるコンピューターを、配列で指定されているものに制限します。

```yaml
Type: System.String[]
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
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
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
対象のコンピューターで現在実行されている構成操作を停止し、新しい Start-Configuration 操作を開始します。
ローカル Configuration Manager の **Refreshmode** プロパティが **Pull** に設定されている場合、このパラメーターを指定すると **Push** に変更されます。

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

### -Path
構成設定ファイルを含むフォルダーのファイル パスを指定します。
このコマンドレットは、指定したパスに設定ファイルがあるコンピューターに、これらの構成設定を発行して適用します。
各ターゲットノードには、次の形式の設定ファイルが必要です: NetBIOS 名 .mof。

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: False
Position: 0
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

### -UseExisting
このコマンドレットが既存の構成を適用することを示します。
構成は、 **start-dscconfiguration** を使用するか、または Publish-DscConfiguration コマンドレットを使用して発行することにより、ターゲットコンピューターに存在することができます。

このコマンドレットにこのパラメーターを指定する前に、「 [Windows PowerShell 5.0 の新機能](/powershell/scripting/whats-new/what-s-new-in-windows-powershell-50)」の情報を確認してください。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameAndUseExistingSet, CimSessionAndUseExistingSet
Aliases:

Required: True
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

[Windows PowerShell Desired State Configuration の概要](/powershell/scripting/dsc/overview/overview)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Stop-DscConfiguration](Stop-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)

[Update-DscConfiguration](Update-DscConfiguration.md)
