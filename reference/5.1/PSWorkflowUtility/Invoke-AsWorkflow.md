---
external help file: Microsoft.PowerShell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSWorkflowUtility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflowutility/invoke-asworkflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-AsWorkflow
ms.openlocfilehash: b96bce9fe4d574fe2b7e9c7c0f1e05ee0508adce
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213355"
---
# Invoke-AsWorkflow

## 概要
コマンドまたは式を Windows PowerShell ワークフローとして実行します。

## SYNTAX

### Command (既定値)

```
Invoke-AsWorkflow [-CommandName <String>] [-Parameter <Hashtable>] [-InputObject <Object>] [<CommonParameters>]
```

### Expression

```
Invoke-AsWorkflow [-Expression <String>] [-InputObject <Object>] [<CommonParameters>]
```

## Description

ワークフローは、 `Invoke-AsWorkflow` ワークフロー内のインラインスクリプトとして任意のコマンドまたは式を実行します。
これらのワークフローは、標準のワークフロー セマンティクスを使用し、すべてのワークフロー共通パラメーターを持ち、ワークフローのすべての利点 (停止、再開、復旧する機能など) を備えています。

ワークフローは、重要なデータを収集する実行時間の長いコマンドを対象にしていますが、任意のコマンドの実行に使用することができます。
詳細については、「 [about_Workflows](../PSWorkflow/About/about_Workflows.md)」を参照してください。

このコマンドにワークフロー共通パラメーターを追加することもできます。
ワークフロー共通パラメーターの詳細については、「」を参照してください [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)

このワークフローは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: コマンドレットをワークフローとして実行する

```powershell
Invoke-AsWorkflow -PSComputerName (Get-Content Servers.txt) -CommandName Get-ExecutionPolicy
```

```output
PSComputerName                     PSSourceJobInstanceId                   Value
--------------                     ---------------------                   -----
Server01                           77b1cdf8-8226-4662-9067-cd2fa5c3b711    AllSigned
Server02                           a33542d7-3cdd-4339-ab99-0e7cd8e59462    Unrestricted
Server03                           279bac28-066a-4646-9497-8fcdcfe9757e    AllSigned
localhost                          0d858009-2cc4-47a4-a2e0-da17dc2883d0    RemoteSigned
```

このコマンドは、数 `Get-ExecutionPolicy` 百のコンピューターでワークフローとしてコマンドレットを実行します。

このコマンドでは、 **CommandName** パラメーターを使用して、ワークフローで実行するコマンドレットを指定します。
**PSComputerName** ワークフロー共通パラメーターを使用して、コマンドを実行するコンピューターを指定します。
**PSComputerName** パラメーターの値は、 `Get-Content` Servers.txt ファイルからコンピューター名の一覧を取得するコマンドです。
パラメーター値は、値を使用する前にコマンドを実行するように Windows PowerShell に指示するために、かっこで囲まれてい `Get-Command` ます。

すべてのリモート コマンドと同様に、コマンドをローカル コンピューターで実行する場合 (PSComputerName パラメーターの値にローカル コンピューターが含まれている場合)、[管理者として実行] オプションで Windows PowerShell を起動する必要があります。

### 例 2: パラメーターを使用してコマンドレットを実行する

```powershell
$s = Import-Csv .\Servers.csv -Header ServerName, ServerID
Invoke-AsWorkflow -CommandName Get-ExecutionPolicy -Parameter @{Scope="Process"} -PSComputerName {$s.ServerName} -PSConnectionRetryCount 5
```

最初のコマンドは、 `Import-Csv` コマンドレットを使用して、Servers.csv ファイルのコンテンツからオブジェクトを作成します。 このコマンドは、パラメーターを使用して、 `Header` `ServerName` "リモートノード" とも呼ばれる、ターゲットコンピューターの名前を含む列のプロパティを作成します。 このコマンドは、変数に結果を保存し `$s` ます。

2番目のコマンドは、ワークフローを使用して、 `Invoke-AsWorkflow` `Get-ExecutionPolicy` Servers.csv ファイル内のコンピューターでコマンドを実行します。 このコマンドは、の **CommandName** パラメーターを使用して、 `Invoke-AsWorkflow`  ワークフローで実行するコマンドを指定します。 この例では、のパラメーターを使用して、 `Parameter` `Invoke-AsWorkflow` Process という値を指定して `Scope` コマンドレットのパラメーターを指定して `Get-ExecutionPolicy` います。 **Process** また、このコマンドは、workflow common パラメーターを使用して、 `PSConnectionRetryCount` 各コンピューターでのコマンドの試行回数を5回に制限します。また、ワークフロー共通パラメーターを使用して、 `PSComputerName` リモートノード (ターゲットコンピューター) の名前を指定します。 パラメーターの値 `PSComputerName` は、 `ServerName` 変数内のすべてのオブジェクトのプロパティを取得する式です `$s` 。

これらのコマンドは、数 `Get-ExecutionPolicy` 百のコンピューターでワークフローとしてコマンドを実行します。
このコマンドは、コマンド `Scope` レットのパラメーターを `Get-ExecutionPolicy` **Process** の値と共に使用して、現在のセッションの実行ポリシーを取得します。

### 例 3: 式をワークフローとして実行する

```powershell
Invoke-AsWorkflow -Expression "ipconfig /all" -PSComputerName (Get-Content DomainControllers.txt) -AsJob -JobName IPConfig
```

```output
Id     Name          PSJobTypeName   State         HasMoreData   Location                Command
--     ----          -------------   -----         -----------   --------                -------
2      IpConfig      PSWorkflowJob   Completed     True          Server01, Server01...   Invoke-AsWorkflow
```

このコマンドは、ワークフローを使用し `Invoke-AsWorkflow` て、DomainControllers.txt ファイルに一覧表示されているコンピューター上のワークフロージョブとして Ipconfig コマンドを実行します。

このコマンドは、パラメーターを使用して `Expression` 、実行する式を指定します。
ワークフロー共通パラメーターを使用して、 `PSComputerName` リモートノード (ターゲットコンピューター) の名前を指定します。

また、このコマンドは、ワークフロー共通パラメーターを使用して、 `AsJob` `JobName` 各コンピューターで "Ipconfig" ジョブ名を使用してワークフローをバックグラウンドジョブとして実行します。

このコマンドは、 `ContainerParentJob` `System.Management.Automation.ContainerParentJob` 各コンピューター上のワークフロージョブを格納するオブジェクト () を返します。

## PARAMETERS

### -CommandName

指定されたコマンドレットまたは高度な関数をワークフローとして実行します。
コマンドレットまたは関数の名前 (、、など) を入力し `Update-Help` `Set-ExecutionPolicy` `Set-NetFirewallRule` ます。

```yaml
Type: System.String
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -式

このコマンドレットがワークフローとして実行する式を指定します。
式を文字列として入力します。たとえば、のように `"ipconfig /all"` なります。
式にスペースや特殊文字が含まれている場合は、式を二重引用符で囲みます。

```yaml
Type: System.String
Parameter Sets: Expression
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameter

パラメーターで指定したコマンドのパラメーターとパラメーター値を指定し `CommandName` ます。
各キーがパラメーター名で、その値がパラメーター値 (など) であるハッシュテーブルを入力し `@{ExecutionPolicy="AllSigned"}` ます。

ハッシュテーブルの詳細については、「 [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)」を参照してください。

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

パイプラインの入力を許可するために使用されます。

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。

### WorkflowCommonParameters

このコマンドレットは、ワークフロー固有の共通パラメーターもサポートしています。
詳細については、「 [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)」を参照してください。

## 入力

### System.Object

パイプを使用して任意のオブジェクトをパラメーターに渡し `InputObject` ます。

## 出力

### なし

このコマンドは出力を生成しません。
ただし、実行するワークフローによって出力が生成される場合があります。

## 注

## 関連リンク

[New-PSWorkflowExecutionOption](../PSWorkflow/New-PSWorkflowExecutionOption.md)

[New-PSWorkflowSession](../PSWorkflow/New-PSWorkflowSession.md)

[about_Workflows](../PSWorkflow/About/about_Workflows.md)

[about_Workflow_Common_Parameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)
