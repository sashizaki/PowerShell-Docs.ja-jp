---
title: バック グラウンド ジョブ |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0ef5ac9-8254-4832-ace8-84b356c10f08
caps.latest.revision: 13
ms.openlocfilehash: ff4fe159eedc47fc69f4d783cd90d2b0e888c0d5
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794707"
---
# <a name="background-jobs"></a>バックグラウンド ジョブ

内部的には、Windows PowerShell コマンドレットでそれらのアクションを実行できます*バック グラウンド ジョブ*します。 コマンドレットをバック グラウンド ジョブとして実行すると、作業は、コマンドレットを使用しているパイプラインのスレッドから別の独自のスレッドで非同期に実行します。 ユーザーの観点からコマンドレットをバック グラウンド ジョブとして実行すると、コマンド プロンプトに戻りますすぐに場合でも、ジョブを完了するに非常に長い時間を受け取り、ユーザーがジョブの実行中に中断なく続行します。

## <a name="background-jobs-child-jobs-and-the-job-repository"></a>バック グラウンド ジョブの子ジョブおよびジョブ リポジトリ

バック グラウンド ジョブをサポートするコマンドレットによって返されるジョブ オブジェクトは、ジョブを定義します。 (、 [Start-job](/powershell/module/Microsoft.PowerShell.Core/Start-Job)コマンドレットはジョブ オブジェクトも返します)。この定義では、ジョブ、ジョブ、状態情報、および子ジョブを指定するために使用する識別子の名前が含まれます。 ジョブは、作業のいずれかを実行しません。 各バック グラウンド ジョブでは、子ジョブは、実際の作業を実行するために少なくとも 1 つの子ジョブがあります。 作業がバック グラウンド ジョブとして実行されるようにコマンドレットを実行するときにコマンドレットは、する必要があります、ジョブと子ジョブに追加と呼ばれる共通のリポジトリ、*のジョブ リポジトリ*します。

コマンドラインでバック グラウンド ジョブを処理する方法の詳細については、次を参照してください。

- [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs)

- [about_Job_Details](/powershell/module/microsoft.powershell.core/about/about_job_details)

- [about_Remote_Jobs](/powershell/module/microsoft.powershell.core/about/about_remote_jobs)

## <a name="writing-a-cmdlet-that-runs-as-a-background-job"></a>バック グラウンド ジョブとして実行されるコマンドレットの記述

バック グラウンド ジョブとして実行できるコマンドレットを作成するには、次のタスクを行う必要があります。

- 定義、`asJob`スイッチ パラメーターで、ユーザーが、コマンドレットをバック グラウンド ジョブとして実行するかどうかを決定できるようにします。

- 派生したオブジェクトを作成、 [System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job)クラス。 このオブジェクトは、カスタムのジョブ オブジェクトまたはジョブ オブジェクトなど、Windows PowerShell によって提供される、 [System.Management.Automation.Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob)オブジェクト。

- レコードの処理メソッドには、追加、`if`コマンドレットがバック グラウンド ジョブとして実行する必要があるかどうかを検出するステートメント。

- カスタムのジョブ オブジェクトの場合は、job クラスを実装します。

- コマンドレットをバック グラウンド ジョブとして実行するかどうかに応じて、適切なオブジェクトを返します。

コード例では、次を参照してください。[サポート ジョブ方法](./how-to-support-jobs.md)します。

## <a name="background-job-related-apis"></a>バック グラウンド ジョブに関連する Api

次の Api は、バック グラウンド ジョブを管理する Windows PowerShell によって提供されます。

[System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job)カスタムのジョブ オブジェクトを派生します。 これは、抽象クラスです。

[System.Management.Automation.Jobrepository](/dotnet/api/System.Management.Automation.JobRepository)を管理し、現在のアクティブなバック グラウンド ジョブに関する情報を提供します。

[System.Management.Automation.Jobstate](/dotnet/api/System.Management.Automation.JobState)バック グラウンド ジョブの状態を定義します。 開始、実行、および停止の状態が含まれます。

[System.Management.Automation.Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo)バック グラウンド ジョブの状態に関する情報を提供し、最新の状態を変更する場合は、エラー、ジョブの現在の状態になった理由によって発生しました。

[System.Management.Automation.Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs)バック グラウンド ジョブの状態が変更されたときに発生するイベントの引数を提供します。

## <a name="windows-powershell-job-cmdlets"></a>Windows PowerShell ジョブのコマンドレット

次のコマンドレットは、バック グラウンド ジョブを管理する Windows PowerShell によって提供されます。

[Get-Job](/powershell/module/Microsoft.PowerShell.Core/Get-Job)

現在のセッションで実行されている Windows PowerShell のバックグラウンド ジョブを取得します。

[Receive-Job](/powershell/module/Microsoft.PowerShell.Core/Receive-Job)

現在のセッションの Windows PowerShell バックグラウンド ジョブの結果を取得します。

[Remove-Job](/powershell/module/Microsoft.PowerShell.Core/Remove-Job)

Windows PowerShell バックグラウンド ジョブを削除します。

[Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job)

Windows PowerShell バックグラウンド ジョブを開始します。

[Stop-Job](/powershell/module/Microsoft.PowerShell.Core/Stop-Job)

Windows PowerShell バックグラウンド ジョブを停止します。

[Wait-Job](/powershell/module/Microsoft.PowerShell.Core/Wait-Job)

セッションで実行されている 1 つまたはすべての Windows PowerShell のバックグラウンド ジョブが完了するまでは、コマンド プロンプトが表示されないようにします。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
