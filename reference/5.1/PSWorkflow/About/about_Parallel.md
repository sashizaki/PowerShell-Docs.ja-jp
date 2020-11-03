---
description: ワークフロー内のアクティビティを並列実行する Parallel キーワードについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parallel
ms.openlocfilehash: 402e93672bbea4ec9b6bfda8d608f266f6c40a21
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221891"
---
# <a name="about-parallel"></a>並列について

## <a name="short-description"></a>概要
ワークフロー内のアクティビティを並列実行する Parallel キーワードについて説明します。

## <a name="long-description"></a>詳細説明

Parallel キーワードは、ワークフローアクティビティを並行して実行します。 このキーワードは、Windows PowerShell ワークフローでのみ有効です。

### <a name="syntax"></a>SYNTAX

```
workflow <Verb-Noun>
{
     Parallel
     {
          [<Activity>]
          [<Activity>]
        ...
     }
 }
```

## <a name="detailed-description"></a>詳細説明

Parallel スクリプト ブロックのコマンドは、同時に実行できます。 実行される順序は決まっていません。

たとえば、次のワークフローには、コンピューターでプロセスやサービスを取得するアクティビティを実行する Parallel スクリプト ブロックが含まれています。 Get-Process と Get-Service のコマンドは互いに独立しているため、同時に、任意の順序で実行できます。

```powershell
workflow Test-Workflow
{
    Parallel
    {
         Get-Process
         Get-Service
    }
}
```

コマンドを並列実行すると、非常に効率的で、ワークフローを完了するためにかかる時間が大幅に短縮されます。

並列スクリプトブロックで選択したコマンドを順番に実行するには、Sequence キーワードを使用します。 詳細については、「about_Sequence」を参照してください。

コレクション内の項目に対して並列スクリプトブロックを実行するには、ForEach または ForEach-Parallel キーワードを使用します。

## <a name="see-also"></a>関連項目

["スクリプトワークフローの作成"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574157(v=ws.11))

[about_ForEach](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[about_ForEach-並列](about_ForEach-Parallel.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Sequence](about_Sequence.md)

[about_Workflows](about_workflows.md)
