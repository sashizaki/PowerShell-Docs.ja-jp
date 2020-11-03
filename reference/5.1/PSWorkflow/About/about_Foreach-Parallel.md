---
description: '`ForEach -Parallel`Windows PowerShell ワークフローの言語構成要素について説明します。'
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_foreach-parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Foreach 並列
ms.openlocfilehash: 1012b45396b65d424dacac067c2af8d3b6823f92
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221907"
---
# <a name="about-foreach-parallel"></a>Foreach-Parallel について

## <a name="short-description"></a>概要
`ForEach -Parallel`Windows PowerShell ワークフローの言語構成要素について説明します。

## <a name="long-description"></a>詳細説明

キーワードの **Parallel** パラメーターは、 `ForEach` `ForEach` 指定されたコレクション内の各項目に対して、スクリプトブロック内のコマンドを1回実行します。

ディスクのコレクション内のディスクなど、コレクション内の項目は並行して処理されます。 スクリプトブロック内のコマンドは、コレクション内の各項目に対して順番に実行されます。

`ForEach -Parallel` は、Windows PowerShell ワークフローでのみ有効です。

### <a name="syntax"></a>SYNTAX

```
ForEach -Parallel ($<item> in $<collection>)
{
    [<Activity1>]
    [<Activity2>]
    ...
}
```

### <a name="detailed-description"></a>詳細説明

Windows PowerShell の ForEach ステートメントと同様に、コレクションを含む変数は、 `$<collection>` ステートメントの前に定義する必要があり `ForEach -Parallel` ますが、現在のアイテムを表す変数は、ステートメントで定義されてい `$<item>` `ForEach -Parallel` ます。

`ForEach -Parallel`コンストラクトは、 `ForEach` キーワードと **Parallel** パラメーターとは異なります。 キーワードは、 `ForEach` コレクション内の項目を順番に処理します。 **Parallel** パラメーターは、スクリプトブロック内のコマンドを並列で実行します。 並列スクリプトブロックは、スクリプトブロックで囲むことができ `ForEach -Parallel` ます。

ワークフロー内の対象コンピューター ( **PSComputerName** workflow 共通パラメーターによって指定されたものなど) は、常に並列で処理されます。
この目的のためにキーワードを指定する必要はありません `ForEach -Parallel` 。

### <a name="examples"></a>例

次のワークフローには、 `ForEach -Parallel` アクティビティが取得するディスクを処理するステートメントが含まれてい `Get-Disk` ます。 スクリプトブロック内のコマンドは順番に実行され `ForEach -Parallel` ますが、ディスク上で並列実行されます。 ディスクは、同時に、任意の順序で処理される可能性があります。

```powershell
workflow Test-Workflow
{
    $Disks = Get-Disk

    # The disks are processed in parallel.
    ForEach -Parallel ($Disk in $Disks)
    {
        # The commands run sequentially on each disk.
        $DiskPath = $Disk.Path
        $Disk | Initialize-Disk
        Set-Disk -Path $DiskPath
    }
}

workflow Test-Workflow
{
    #Run commands in parallel.
    Parallel
    {
        Get-Process
        Get-Service
    }

   $Disks = Get-Disk

   # The disks are processed in parallel.
   ForEach -Parallel ($Disk in $Disks)
   {
       # The commands run in parallel on each disk.
       Parallel
       {
           Initialize-Disk
           InlineScript {.\Get-DiskInventory}
       }
   }
}
```

## <a name="see-also"></a>関連項目

[Writing a Script Workflow](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)

[about_ForEach](../../Microsoft.PowerShell.Core/About/about_ForEach.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Parallel](about_Parallel.md)

[about_Workflows](about_Workflows.md)
