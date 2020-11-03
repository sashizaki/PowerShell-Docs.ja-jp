---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 04/29/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/set-dsclocalconfigurationmanager?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DscLocalConfigurationManager
ms.openlocfilehash: 0d35aa56a52f0e6c17abd0e7b2707869e780324c
ms.sourcegitcommit: 0d4d3e47f6979876550591f62061096e7a568f7e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2020
ms.locfileid: "93218016"
---
# Set-DscLocalConfigurationManager

## 概要

ローカル Configuration Manager (LCM) 設定をノードに適用します。

## SYNTAX

### ComputerNameSet (既定値)

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CimSessionSet

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description

`Set-DscLocalConfigurationManager`コマンドレットは、LCM 設定またはメタ構成をノードに適用します。 コンピューターの名前を指定するか、または Common Information Model (CIM) セッションを使用してコンピューターを指定します。 ターゲット コンピューターを指定しない場合、コマンドレットは、ローカル コンピューターに設定を適用します。

## 例

### 例 1: LCM 設定を適用する

```
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\"
```

このコマンドは、からターゲットノードに LCM 設定を適用し `C:\DSC\Configurations\` ます。 設定を受け取った後、LCM はそれらを処理します。

> [!WARNING]
> 指定されたフォルダーに格納されている同じコンピューターに複数の meta mof が存在する場合は、最初のメタ mof のみが適用されます。

### 例 2: CIM セッションを使用して LCM 設定を適用する

```
$Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\" -CimSession $Session
```

この例では、LCM 設定をコンピューターに適用し、設定を適用します。 例では、コマンドレットで使用するために、Server01 という名前のコンピューター用に CIM セッションを作成します。 または、CIM セッションの配列を作成して、指定した複数のコンピューターにコマンドレットを適用します。

最初のコマンドは、コマンドレットを使用して CIM セッションを作成し、 `New-CimSession` **CimSession** オブジェクトを変数に格納し `$Session` ます。 コマンドはパスワードの入力をユーザーに求めます。 詳細を表示するには「`Get-Help New-CimSession`」を入力します。

2番目のコマンドは、ターゲットノードの LCM 設定をから、 `C:\DSC\Configurations\` 変数に格納されている **CimSession** オブジェクトによって識別されるコンピューターに適用し `$Session` ます。 この例では、 `$Session` 変数には Server01 という名前のコンピューターに対してのみ CIM セッションが含まれています。 コマンドは設定を適用します。 設定を受け取った後、LCM はそれらを処理します。

## PARAMETERS

### -CimSession

リモート セッションまたはリモート コンピューターでコマンドレットを実行します。 コンピューター名またはセッションオブジェクト ( [CimSession](/powershell/module/CimCmdlets/New-CimSession) または [CimSession](/powershell/module/CimCmdlets/Get-CimSession) コマンドレットの出力など) を入力します。
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

コンピューター名の配列を指定します。 このパラメーターは、 **Path** パラメーターにメタ構成ドキュメントが含まれるコンピューターを、配列で指定されているものに制限します。

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

ターゲット コンピューターに対して、ユーザー名とパスワードを、 **PSCredential** オブジェクトとして指定します。 **PSCredential** オブジェクトを取得するには、Get-Credential コマンドレットを使用します。 詳細を表示するには「`Get-Help Get-Credential`」を入力します。

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

### -Force

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

### -Path

構成設定ファイルを含むフォルダーのファイル パスを指定します。 このコマンドレットは、指定されたパスに設定ファイルがあるコンピューターに、これらの LCM 設定を発行して適用します。 各ターゲットノードには、という形式の設定ファイルが必要 `NetBIOS Name.meta.mof` です。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

コマンドレットを実行するために確立できる最大並行処理数を指定します。 このパラメーターを省略した場合、または値を入力した場合 `0` 、Windows PowerShell は、コンピューターで実行されている CIM コマンドレットの数に基づいて、コマンドレットに最適なスロットル制限を計算します。 調整限度は、現在のコマンドレットのみに適用されます。セッションやコンピューターには適用されません。

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

[Windows PowerShell Desired State Configuration の概要](/powershell/scripting/dsc/overview/overview)

[Get-DscLocalConfigurationManager](Get-DscLocalConfigurationManager.md)
