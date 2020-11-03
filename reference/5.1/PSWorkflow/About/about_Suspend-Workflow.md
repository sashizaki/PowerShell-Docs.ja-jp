---
description: アクティビティについて説明し `Suspend-Workflow` ます。このアクティビティは、アクティビティが表示されるワークフローを中断します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_suspend-workflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Suspend ワークフロー
ms.openlocfilehash: cbe5386ae5aa4bd863079fde240ddf2ce5384727
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221864"
---
# <a name="about-suspend-workflow"></a>Suspend-Workflow について

## <a name="short-description"></a>簡単な説明

アクティビティについて説明し `Suspend-Workflow` ます。このアクティビティは、アクティビティが表示されるワークフローを中断します。

## <a name="long-description"></a>長い説明

アクティビティは、ワークフロー `Suspend-Workflow` 内からワークフロー処理を一時的に停止します。 中断する前に、Windows PowerShell ワークフローはチェックポイントを取得して、ワークフローの状態とデータが保持され、ワークフローが中断ポイントから再開できるようにします。

ワークフローを再開するには、ワークフローを実行するユーザーがコマンドレットを使用し `Resume-Job` ます。 ワークフロー内からワークフローを再開することはできません。

## <a name="syntax"></a>構文

```
workflow <Verb-Noun>
{
    Suspend-Workflow
}
```

## <a name="detailed-description"></a>詳しい説明

は、 `Suspend-Workflow` ワークフローを一時的に停止し、ワークフロージョブを表すジョブオブジェクトを返します。 ジョブとしてワークフローを実行していない場合でも、ジョブオブジェクトが返されます。 たとえば、 **AsJob** workflow 共通パラメーターを使用するなどです。 ジョブの状態は **中断** されています。

Job コマンドレットを使用して、中断されたワークフロージョブを管理できます。 ワークフロージョブを再開するには、 `Resume-Job` コマンドレットを使用します。

ワークフロージョブを再開すると、アクティビティの後のコマンドでワークフローが再開され `Suspend-Workflow` ます。

たとえば、次のワークフローにはアクティビティが含まれてい `Suspend-Workflow` ます。
ワークフローを実行すると、アクティビティが実行され、その出力が変数に保存された後、ワークフローが中断され、中断された `Get-Date` `$a` ワークフローを表すジョブオブジェクトが返されます。 ジョブの種類は **Psworkflowjob** です。

などのジョブコマンドレットを使用して、 `Get-Job` ワークフロージョブを管理できます。

```powershell
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

Test-Suspend
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Suspended  True         localhost Test-Suspend
```

## <a name="resuming-a-workflow-job"></a>ワークフロージョブの再開

ワークフロージョブを再開するには、 `Resume-Job` コマンドレットを使用します。 `Resume-Job` コマンドレットは、ワークフロー ジョブ オブジェクトを即座に返します (まだ再開されていない場合でも)。 ジョブが再開されるまで待機するには、 **wait** パラメーターを使用するか、コマンドレットを使用して `Get-Job` 現在のジョブオブジェクトを取得します。

```powershell
Resume-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State    HasMoreData  Location  Command
--  ----  -------------  -----    -----------  --------  -------
8   Job8  PSWorkflowJob  Running  True         localhost Test-Suspend
```

```powershell
Get-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Completed  True         localhost Test-Suspend
```

## <a name="getting-the-output-of-a-workflow-job"></a>ワークフロージョブの出力の取得

ワークフロージョブの出力を取得するには、コマンドレットを使用し `Receive-Job` ます。 出力は、コマンドレットの後に続くコマンドでワークフローが再開されたことを示して `Suspend-Workflow` います。 `$a`中断前に作成された変数の値は、再開時にワークフローで使用できます。

```powershell
Get-Job -Name Job8 | Receive-Job
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 19
Milliseconds      : 823
Ticks             : 198230041
TotalDays         : 0.000229432917824074
TotalHours        : 0.00550639002777778
TotalMinutes      : 0.330383401666667
TotalSeconds      : 19.8230041
TotalMilliseconds : 19823.0041
PSComputerName    : localhost
```

## <a name="see-also"></a>関連項目

[about_Workflows](about_Workflows.md)

[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)

[Psworkflow](xref:PSWorkflow) コマンドレット

[ワークフロー ガイド](/previous-versions/powershell/scripting/components/workflows-guide)

[Windows PowerShell ワークフローを記述する](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
