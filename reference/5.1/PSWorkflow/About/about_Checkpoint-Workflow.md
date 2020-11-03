---
description: ワークフローでチェックポイントを取得する Checkpoint-Workflow アクティビティについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_checkpoint-workflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Checkpoint ワークフロー
ms.openlocfilehash: 223deb07ff6ed387cf04736116ea0ce3f998bb59
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221912"
---
# <a name="about-checkpoint-workflow"></a>Checkpoint-Workflow について

## <a name="short-description"></a>概要
ワークフローでチェックポイントを取得する Checkpoint-Workflow アクティビティについて説明します。

## <a name="long-description"></a>詳細説明

Checkpoint-Workflow アクティビティはチェックポイントを取得します。これにより、状態とデータがワークフローに保存されます。 ワークフローが中断または中断された場合は、再起動するのではなく、最新のチェックポイントから再開できます。

Checkpoint-Workflow アクティビティは、ワークフローでのみ有効です。

### <a name="syntax"></a>SYNTAX

```
Workflow <Verb-Noun>
{
    Checkpoint-Workflow
}
```

Checkpoint-Workflow アクティビティは、共通パラメーターやワークフロー共通パラメーターを含むパラメーターを一切受け入れません。

Checkpoint-Activity チェックポイントは、表示可能なバインドまたは Param ステートメントの後に、ワークフローの任意の場所に配置できます。 ただし、チェックポイントを配置する場合は、データを収集し、ワークフローを実行しているコンピューターのディスクに書き込むというパフォーマンスコストを考慮してください。

中断されたワークフローのセクションを再実行する時間が、チェックポイントの状態とデータをディスクに書き込む時間を超えることを必ず確認します。

重要な手順の後にチェックポイントを作成することを検討してください。再起動するのではなく、ワークフローを再開できます。 たとえば、べき等ではないコマンドの後にチェックポイントを作成します。

### <a name="about-checkpoints"></a>チェックポイントについて

"チェックポイント" とは、変数の現在の値などのワークフローの状態と、そのポイントまでに生成された出力のことで、ディスクに保存されます。

意図的または意図せずにワークフローが中断された場合、Windows PowerShell ワークフローは、最新のチェックポイントのデータを自動的に使用して、ワークフローの復旧と再開を行います。

AsJob ワークフロー共通パラメーターなどを使用してワークフローをジョブとして実行する場合、ワークフローチェックポイントは、Remove-Job コマンドレットを使用してなど、ジョブを削除するまで保持されます。
それ以外の場合、ワークフローのチェックポイントは、ワークフローが完了すると削除されます。

### <a name="other-checkpointing-techniques"></a>その他のチェックポイント方法

Windows PowerShell ワークフローでは、Checkpoint-Workflow アクティビティに加えて、次のようなチェックポイント処理手法もサポートしています。

- PSPersist ワークフロー共通パラメーター
- PSPersist アクティビティ共通パラメーター
- PSPersistPreference 変数 (ワークフロー内)

ワークフローにチェックポイントを追加する方法の詳細については、「ワークフローにチェックポイントを追加する方法」を参照してください。

## <a name="examples"></a>例

次のワークフローには、実行時間の長い関数を完了した後の Checkpoint-Workflow アクティビティの呼び出しと、データを共有するスクリプトが含まれています。

```powershell
Workflow Test-Workflow
{
    $a = Invoke-LongRunningFunction
    InlineScript { \\Server\Share\Get-DataPacks.ps1 $Using:a}
    Checkpoint-Workflow

    Invoke-LongRunningFunction
    {
        ...
    }
}
```

## <a name="see-also"></a>関連項目

[Windows PowerShell ワークフローを記述する](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
