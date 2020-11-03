---
external help file: Get-DSCConfiguration.cdxml-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfiguration
ms.openlocfilehash: 42b24e72de4c4bcc9326d52861c08a05853b18e0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215355"
---
# Get-DscConfiguration

## 概要
ノードの現在の構成を取得します。

## SYNTAX

```
Get-DscConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## Description
構成が存在する場合、 **start-dscconfiguration** コマンドレットは、ノードの現在の構成を取得します。
Common Information Model (CIM) セッションを使用してコンピューターを指定します。
ターゲット コンピューターを指定しない場合、コマンドレットではローカル コンピューターから構成を取得します。

## 例

### 例 1: ローカルコンピューターの構成を取得する

```
PS C:\> Get-DscConfiguration
```

このコマンドは、ローカルコンピューターの現在の状態を取得します。

### 例 2: 指定したコンピューターの構成を取得する

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Get-DscConfiguration -CimSession $Session
```

この例では、CIM セッションによって指定されたコンピューターから現在の状態を取得します。
例では、コマンドレットで使用するために、Server01 という名前のコンピューター用に CIM セッションを作成します。
または、CIM セッションの配列を作成して、指定した複数のコンピューターにコマンドレットを適用します。

最初のコマンドは、 **New-CimSession** コマンドレットを使用して CIM セッションを作成し、 **CimSession** オブジェクトを **$Session** 変数に格納します。
コマンドはパスワードの入力をユーザーに求めます。
詳細を表示するには「`Get-Help New-CimSession`」を入力します。

2 番目のコマンドは、 **$Session** 変数に格納された **CimSession** オブジェクトによって識別されるコンピューター (この場合は、Server01 という名前のコンピューター) の現在の構成を取得します。

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

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)
