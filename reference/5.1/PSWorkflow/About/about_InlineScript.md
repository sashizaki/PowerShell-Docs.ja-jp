---
description: '`InlineScript`ワークフローで PowerShell コマンドを実行するアクティビティについて説明します。'
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_inlinescript?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_InlineScript
ms.openlocfilehash: 2eaeb02c6441865551b586e27a39c4000826752b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221904"
---
# <a name="about-inlinescript"></a><span data-ttu-id="2cd4a-104">InlineScript の概要</span><span class="sxs-lookup"><span data-stu-id="2cd4a-104">About InlineScript</span></span>

## <a name="short-description"></a><span data-ttu-id="2cd4a-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="2cd4a-105">Short description</span></span>

<span data-ttu-id="2cd4a-106">`InlineScript`ワークフローで PowerShell コマンドを実行するアクティビティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-106">Describes the `InlineScript` activity, that runs PowerShell commands in a workflow.</span></span>

## <a name="long-description"></a><span data-ttu-id="2cd4a-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="2cd4a-107">Long description</span></span>

<span data-ttu-id="2cd4a-108">アクティビティは、 `InlineScript` 共有 PowerShell セッションのワークフローでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-108">The `InlineScript` activity runs commands in a shared PowerShell session's workflow.</span></span> <span data-ttu-id="2cd4a-109">`InlineScript` は、ワークフローでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-109">`InlineScript` is only valid in workflows.</span></span>

## <a name="syntax"></a><span data-ttu-id="2cd4a-110">構文</span><span class="sxs-lookup"><span data-stu-id="2cd4a-110">Syntax</span></span>

```
InlineScript {<script block>} <ActivityCommonParameters>
```

## <a name="detailed-description"></a><span data-ttu-id="2cd4a-111">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="2cd4a-111">Detailed description</span></span>

<span data-ttu-id="2cd4a-112">アクティビティは、 `InlineScript` 共有 PowerShell セッションでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-112">The `InlineScript` activity runs commands in a shared PowerShell session.</span></span> <span data-ttu-id="2cd4a-113">これをワークフローに含めて、ワークフロー内で有効ではないデータとコマンドを共有するコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-113">You can include it in a workflow to run commands that share data and commands that aren't otherwise valid in a workflow.</span></span>

<span data-ttu-id="2cd4a-114">スクリプトブロックには、 `InlineScript` すべての有効な PowerShell コマンドと式を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-114">The `InlineScript` script block can include all valid PowerShell commands and expressions.</span></span> <span data-ttu-id="2cd4a-115">スクリプトブロック内のコマンドと式は同じセッションで実行されるので、インポートされた `InlineScript` モジュールと変数の値を含むすべての状態とデータを共有します。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-115">Because the commands and expressions in an `InlineScript` script block run in the same session, they share all state and data, including imported modules and the values of variables.</span></span>

<span data-ttu-id="2cd4a-116">アクティビティは、 `InlineScript` ワークフローまたは入れ子になったワークフロー内の任意の場所に配置できます。これには、ループまたは制御ステートメントの内部、並列またはシーケンスのスクリプトブロックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-116">You can place an `InlineScript` activity anywhere in a workflow or nested workflow, including inside a loop or control statement or a Parallel or Sequence script block.</span></span>

<span data-ttu-id="2cd4a-117">`InlineScript`アクティビティには、 **pspersist** などのアクティビティ共通パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-117">The `InlineScript` activity has the activity common parameters, including **PSPersist**.</span></span> <span data-ttu-id="2cd4a-118">ただし、スクリプトブロック内のコマンドと式には、 `InlineScript` チェックポイント処理、永続化、ワークフローまたはアクティビティ共通パラメーターなどのワークフロー機能がありません。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-118">However, the commands and expressions in an `InlineScript` script block don't have the workflow features such as checkpointing, or persistence, and workflow or activity common parameters.</span></span> <span data-ttu-id="2cd4a-119">詳細については、「 [about_ActivityCommonParameters](about_ActivityCommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-119">For more information, see [about_ActivityCommonParameters](about_ActivityCommonParameters.md).</span></span>

## <a name="inlinescript-variables"></a><span data-ttu-id="2cd4a-120">InlineScript 変数</span><span class="sxs-lookup"><span data-stu-id="2cd4a-120">InlineScript Variables</span></span>

<span data-ttu-id="2cd4a-121">既定では、ワークフローで定義されている変数は、スクリプトブロック内のコマンドには表示されません `InlineScript` 。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-121">By default, the variables that are defined in a workflow aren't visible to the commands in the `InlineScript` script block.</span></span> <span data-ttu-id="2cd4a-122">ワークフロー変数がに表示されるようにするには、 `InlineScript` スコープ修飾子を使用し `$Using` ます。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-122">To make workflow variables visible to the `InlineScript`, use the `$Using` scope modifier.</span></span> <span data-ttu-id="2cd4a-123">`$Using`スコープ修飾子は、の変数ごとに1回だけ指定する必要が `InlineScript` あります。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-123">The `$Using` scope modifier is required only once for each variable in the `InlineScript`.</span></span>

<span data-ttu-id="2cd4a-124">スコープ修飾子の詳細については `$Using` 、「 [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-124">For more information about the `$Using` scope modifier, see [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).</span></span>

<span data-ttu-id="2cd4a-125">次の例では、 `$Using` スコープ修飾子によって、 `$a` 最上位レベルのワークフロー変数の値をスクリプトブロック内のコマンドで使用できるようにして `InlineScript` います。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-125">The following example shows that the `$Using` scope modifier makes the value of the `$a` top-level workflow variable available to the commands in the `InlineScript` script block.</span></span>

```powershell
workflow Test-Workflow {
  $a = 3

  ## Without $Using, the $a workflow variable isn't visible
  ## in inline script.
  InlineScript {"Inline A0 = $a"}

  ## $Using imports the variable and its current value.
  InlineScript {"Inline A1 = $Using:a"}
}

Test-Workflow
```

```output
Inline A0 =
Inline A1 = 3
```

## <a name="returning-variables-in-inlinescript"></a><span data-ttu-id="2cd4a-126">InlineScript で変数を返す</span><span class="sxs-lookup"><span data-stu-id="2cd4a-126">Returning variables in InlineScript</span></span>

<span data-ttu-id="2cd4a-127">`InlineScript` コマンドは、ワークフロースコープからインポートされた変数の値を変更できますが、変更はワークフロースコープには表示されません。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-127">`InlineScript` commands can change the value of the variable that was imported from workflow scope, but the changes aren't visible in workflow scope.</span></span> <span data-ttu-id="2cd4a-128">表示されるようにするには、次の例に示すように、変更した値をワークフロー スコープに返します。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-128">To make them visible, return the changed value to the workflow scope, as shown in the following example.</span></span>

```powershell
workflow Test-Workflow {
  $a = 3

  ##  Changes to the InlineScript variable value don't
  ##  change the workflow variable.
  InlineScript {
    $a = $Using:a+1;
    "Inline A = $a"
  }
  "Workflow A = $a"

  ##  To change the variable in workflow scope, return the
  ##  new value.
  $a = InlineScript {$b = $Using:a+1; $b}
  "Workflow New A = $a"
}

Test-Workflow
```

```output
Inline A = 4
Workflow A = 3
Workflow New A = 4
```

> [!NOTE]
> <span data-ttu-id="2cd4a-129">スコープ修飾子を持つステートメントは、 `$Using` スクリプトブロック内の変数を使用する前に記述する必要があり `InlineScript` ます。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-129">A statement with the `$Using` scope modifier should appear before any use of the variable in the `InlineScript` script block.</span></span>

## <a name="running-in-process"></a><span data-ttu-id="2cd4a-130">インプロセスでの実行</span><span class="sxs-lookup"><span data-stu-id="2cd4a-130">Running in-process</span></span>

<span data-ttu-id="2cd4a-131">信頼性を高めるために、スクリプトブロック内のコマンドは、 `InlineScript` ワークフローを実行するプロセスとは別に、独自のプロセスで実行され、その出力がワークフロープロセスに返されます。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-131">To improve reliability, the commands in the `InlineScript` script block run in their own process, separate from the process in which the workflow runs, and then return their output to the workflow process.</span></span>

<span data-ttu-id="2cd4a-132">ワークフロープロセスでアクティビティを実行するように PowerShell に指示するには、 `InlineScript` `InlineScript` コマンドレットを使用してなど、セッション構成の **OutOfProcessActivity** プロパティから値を削除し `New-PSWorkflowExecutionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-132">To direct PowerShell to run the `InlineScript` activity in the workflow process, remove the `InlineScript` value from the **OutOfProcessActivity** property of the session configuration, such as by using the `New-PSWorkflowExecutionOption` cmdlet.</span></span>

### <a name="example"></a><span data-ttu-id="2cd4a-133">例</span><span class="sxs-lookup"><span data-stu-id="2cd4a-133">Example</span></span>

<span data-ttu-id="2cd4a-134">次のワークフローのには、 `InlineScript` PowerShell で有効であるものの、ワークフローでは有効ではないコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-134">The `InlineScript` in the following workflow includes commands that are valid in PowerShell but aren't valid in workflows.</span></span> <span data-ttu-id="2cd4a-135">たとえば、 `New-Object` コマンドレットには、 **ComObject** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="2cd4a-135">For example, the `New-Object` cmdlet with the **ComObject** parameter.</span></span>

```powershell
workflow Test-Workflow
{
  $ie = InlineScript {
    $ie = New-Object -ComObject InternetExplorer.Application -Property @{navigate2="www.microsoft.com"}

    $ie.Visible = $true
  }

  $ie
}

Test-Workflow
```

## <a name="see-also"></a><span data-ttu-id="2cd4a-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="2cd4a-136">See also</span></span>

[<span data-ttu-id="2cd4a-137">about_ActivityCommonParameters</span><span class="sxs-lookup"><span data-stu-id="2cd4a-137">about_ActivityCommonParameters</span></span>](about_ActivityCommonParameters.md)

[<span data-ttu-id="2cd4a-138">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="2cd4a-138">about_Remote_Variables</span></span>](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)

[<span data-ttu-id="2cd4a-139">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="2cd4a-139">about_WorkflowCommonParameters</span></span>](about_WorkflowCommonParameters.md)

<span data-ttu-id="2cd4a-140">[Psworkflow](xref:PSWorkflow) コマンドレット</span><span class="sxs-lookup"><span data-stu-id="2cd4a-140">[PSWorkflow](xref:PSWorkflow) cmdlets</span></span>

[<span data-ttu-id="2cd4a-141">ワークフロー ガイド</span><span class="sxs-lookup"><span data-stu-id="2cd4a-141">Workflows Guide</span></span>](/previous-versions/powershell/scripting/components/workflows-guide)

[<span data-ttu-id="2cd4a-142">Windows PowerShell ワークフローを記述する</span><span class="sxs-lookup"><span data-stu-id="2cd4a-142">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
