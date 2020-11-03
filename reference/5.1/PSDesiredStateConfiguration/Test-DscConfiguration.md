---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/test-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-DscConfiguration
ms.openlocfilehash: 25c8bc61976ce3940e0b9bd949fa3ee60728450d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213576"
---
# Test-DscConfiguration

## 概要
ノード上の実際の構成が必要な構成と一致するかどうかをテストします。

## SYNTAX

### ComputerNameSet (既定値)

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Detailed] [<CommonParameters>]
```

### ComputerNameAndPathSet

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Path] <String> [<CommonParameters>]
```

### ComputerNameAndReferenceConfigurationSet

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] -ReferenceConfiguration <String> [<CommonParameters>]
```

### CimSessionAndPathSet

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Path] <String>
 [<CommonParameters>]
```

### CimSessionAndReferenceConfigurationSet

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob]
 -ReferenceConfiguration <String> [<CommonParameters>]
```

### CimSessionSet

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Detailed]
 [<CommonParameters>]
```

## Description
**Test-DscConfiguration** コマンドレットは、ノード上の実際の構成が、必要な構成と一致するかどうかをテストします。
コンピューター名または Common Information Model (CIM) セッションを使用して、構成をテストするコンピューターを指定します。
ターゲット コンピューターを指定しない場合、コマンドレットではローカル コンピューターの構成をテストします。

必要な構成と実際の構成が一致する場合、コマンドレットは文字列値 "True" を返します。
それ以外の場合は、文字列値 ' False ' を返します。

## 例

### 例 1: ローカルコンピューターの構成をテストする

```
PS C:\> Test-DscConfiguration
```

以下のコマンドは、ローカル コンピューターの構成をテストします。

### 例 2: 指定したコンピューターの構成をテストする

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Test-DscConfiguration -CimSession $Session
```

この例では、CIM セッションによって指定されたコンピューターからの構成をテストします。
例では、コマンドレットで使用するために、Server01 という名前のコンピューター用に CIM セッションを作成します。
または、CIM セッションの配列を作成して、指定した複数のコンピューターにコマンドレットを適用します。

最初のコマンドは、 **New-CimSession** コマンドレットを使用して CIM セッションを作成し、 **CimSession** オブジェクトを $Session 変数に格納します。
コマンドはパスワードの入力をユーザーに求めます。
詳細を表示するには「`Get-Help New-CimSession`」を入力します。

2 番目のコマンドは、 **$Session** 変数に格納された CimSession オブジェクトによって識別されるコンピューター (この場合は、Server01 という名前のコンピューター) の構成をテストします。

### 例 3: 詳細な結果を含むテスト構成

```
PS C:\> Test-DscConfiguration -ComputerName "Server01", "Server02", "Server03" -Detailed
```

このコマンドは、 *ComputerName* パラメーターで指定された一連のコンピューターの構成をテストし、全体的な状態、目的の状態にあるリソース、目的の状態ではないリソース、およびコンピューター名などの詳細情報を返します。

### 例 4: フォルダーで指定された構成をテストする

```
PS C:\> Test-DscConfiguration -Path "C:\Dsc\Configurations"
```

このコマンドは、 *Path* パラメーターで指定されたフォルダーで定義されている構成をテストします。
これらの構成は、構成ファイルのファイル名で識別される一連のコンピューターに対してテストされます。

### 例 5: ファイルに指定されている構成をテストする

```
PS C:\> Test-DscConfiguration -ReferenceConfiguration "C:\Dsc\Configurations\WebServer.mof" -ComputerName "Server01", "Server02", "Server03"
```

このコマンドは、 *ComputerName* パラメーターで指定されたコンピューターのセットに対して、ファイルで定義された構成をテストします。

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
コンピューター名またはセッションオブジェクト ( [CimSession](/powershell/module/cimcmdlets/new-cimsession) または [CimSession](/powershell/module/cimcmdlets/get-cimsession) コマンドレットの出力など) を入力します。
既定値は、ローカル コンピューターで実行中の現在のセッションです。

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndReferenceConfigurationSet, CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
このコマンドレットによって構成がテストされるコンピューター名の配列を指定します。
コマンドレットは、 *Path* パラメーターによって指定された場所にある構成ドキュメントをこれらのコンピューターに対してテストします。

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
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
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Detailed
このコマンドレットが、構成ドキュメントとノードの目的の状態を比較した結果を詳細に返すことを示します。
結果には、全体的な状態、目的の状態にあるリソース、目的の状態にないリソース、コンピューター名などの情報が含まれます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameSet, CimSessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
構成ドキュメントファイルが格納されているフォルダーのパスを指定します。
コマンドレットは、 *ComputerName* パラメーターまたは *CimSession* パラメーターで指定されたコンピューターの目的の状態に対して構成をテストします。

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReferenceConfiguration
構成ドキュメントファイルのパスを指定します。
このコマンドレットは、 *ComputerName* パラメーターまたは *CimSession* パラメーターによって指定されたコンピューターの実際の状態に対して構成をテストします。

```yaml
Type: System.String
Parameter Sets: ComputerNameAndReferenceConfigurationSet, CimSessionAndReferenceConfigurationSet
Aliases:

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
