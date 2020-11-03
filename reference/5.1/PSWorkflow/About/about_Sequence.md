---
description: '`Sequence`選択されたアクティビティを順番に実行するキーワードについて説明します。'
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_sequence?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Sequence
ms.openlocfilehash: a9dd4fb24274fe4e1478ca69c734b43a2f196792
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221883"
---
# <a name="about-sequence"></a>シーケンスについて

## <a name="short-description"></a>簡単な説明

`Sequence`選択されたアクティビティを順番に実行するキーワードについて説明します。

## <a name="long-description"></a>長い説明

キーワードは、 `Sequence` 選択したワークフローアクティビティを順番に実行します。 ワークフローアクティビティは、表示される順序で実行され、同時に実行されることはありません。 `Sequence`キーワードは、PowerShell ワークフローでのみ有効です。

キーワードは、 `Sequence` `Parallel` 選択したコマンドを順番に実行するために、スクリプトブロックで使用されます。

ワークフローアクティビティは既定では順番に実行されるため、 `Sequence` キーワードはスクリプトブロックでのみ有効です `Parallel` 。 キーワードが `Sequence` スクリプトブロックに含まれていない場合は `Parallel` 有効ですが、無効になります。

スクリプトブロックを使用すると、 `Sequence` 依存するコマンドを順番に実行できるため、より多くのコマンドを並列で実行できます。

## <a name="syntax"></a>構文

### <a name="workflow-using-sequence"></a>Sequence を使用したワークフロー

```
workflow <Verb-Noun>
{
    Sequence
    {
        [<Activity>]
        [<Activity>]
        # ...
    }
}
```

### <a name="workflow-using-parallel-and-sequence"></a>Parallel と Sequence を使用したワークフロー

```
workflow <Verb-Noun>
{
    Parallel
    {
        [<Activity>]
        Sequence
        {
            [<Activity>]
            [<Activity>]
            # ...
        }
    }
}
```

## <a name="detailed-description"></a>詳しい説明

`Parallel` スクリプト ブロックのコマンドは、同時に実行できます。 実行される順序は決まっていません。 この機能により、スクリプトワークフローのパフォーマンスが向上します。

スクリプトブロックを使用すると `Sequence` 、アクティビティがスクリプトブロックに含まれていても、選択したアクティビティを順番に実行でき `Parallel` ます。

スクリプトブロック内のアクティビティは、 `Sequence` 一覧表示されている順序で連続して実行されます。 スクリプトブロック内のアクティビティは `Sequence` 、前のアクティビティが完了した後にのみ開始されます。

ただし、スクリプトブロックにスクリプトブロックが含まれている場合は、スクリプトブロックの `Sequence` `Parallel` 実行順序が決定され `Sequence` ません。 スクリプトブロック内の他のアクティビティの前、後、または同時実行が実行される可能性があり `Parallel` ます。

たとえば、次のワークフローには、 `Parallel` コンピューター上のプロセスとサービスを取得するアクティビティを実行するスクリプトブロックが含まれています。 `Parallel`スクリプトブロックには、 `Sequence` ファイルから情報を取得し、その情報をスクリプトへの入力として使用するスクリプトブロックが含まれています。

`Get-Process`、 `Get-Service` 、および修正プログラムに関連するコマンドは、互いに独立しています。 これらのコマンドは、同時に、または任意の順序で実行できます。 ただし、修正プログラムの情報を取得するコマンドは、その情報を使用するコマンドの前に実行する必要があります。

```powershell
workflow Test-Workflow
{
    Parallel
    {
    Get-Process
    Get-Service

    Sequence
    {
        $Hotfix = Get-Content 'D:\HotFixes\Required.txt'
        Foreach ($h in $Hotfix) {'D:\Scripts\Verify-Hotfix' -Hotfix $h}
        }
    }
}
```

## <a name="see-also"></a>関連項目

[about_ForEach](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[about_ForEach-並列](about_ForEach-Parallel.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Parallel](about_Parallel.md)

[about_Workflows](about_Workflows.md)

[Windows PowerShell スクリプトを利用してワークフローを作成する](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)
