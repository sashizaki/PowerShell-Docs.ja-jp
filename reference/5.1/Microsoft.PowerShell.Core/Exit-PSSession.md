---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession
ms.openlocfilehash: efe0e6c9287b3595988aa3ffc520ce46699cafda
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212067"
---
# <span data-ttu-id="8072f-103">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="8072f-103">Exit-PSSession</span></span>

## <span data-ttu-id="8072f-104">概要</span><span class="sxs-lookup"><span data-stu-id="8072f-104">SYNOPSIS</span></span>
<span data-ttu-id="8072f-105">リモート コンピューターとの対話型セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="8072f-105">Ends an interactive session with a remote computer.</span></span>

## <span data-ttu-id="8072f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8072f-106">SYNTAX</span></span>

```
Exit-PSSession [<CommonParameters>]
```

## <span data-ttu-id="8072f-107">Description</span><span class="sxs-lookup"><span data-stu-id="8072f-107">DESCRIPTION</span></span>
<span data-ttu-id="8072f-108">**終了 PSSession** コマンドレットは、Enter-PSSession コマンドレットを使用して開始した対話型セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="8072f-108">The **Exit-PSSession** cmdlet ends interactive sessions that you started by using the Enter-PSSession cmdlet.</span></span>

<span data-ttu-id="8072f-109">また、 **Exit** キーワードを使用して、対話型セッションを終了することもできます。</span><span class="sxs-lookup"><span data-stu-id="8072f-109">You can also use the **Exit** keyword to end an interactive session.</span></span>
<span data-ttu-id="8072f-110">効果は、 **終了 PSSession** を使用する場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="8072f-110">The effect is the same as using **Exit-PSSession** .</span></span>

## <span data-ttu-id="8072f-111">例</span><span class="sxs-lookup"><span data-stu-id="8072f-111">EXAMPLES</span></span>

### <span data-ttu-id="8072f-112">例 1: 対話型セッションを開始および停止する</span><span class="sxs-lookup"><span data-stu-id="8072f-112">Example 1: Start and stop an interactive session</span></span>

```
PS C:\> Enter-PSSession -computername Server01
Server01\PS> Exit-PSSession
PS C:\>
```

<span data-ttu-id="8072f-113">これらのコマンドは、Server01 リモート コンピューターで対話型セッションを開始および停止します。</span><span class="sxs-lookup"><span data-stu-id="8072f-113">These commands start and then stop an interactive session with the Server01 remote computer.</span></span>

### <span data-ttu-id="8072f-114">例 2: PSSession オブジェクトを使用して対話型セッションを開始および停止する</span><span class="sxs-lookup"><span data-stu-id="8072f-114">Example 2: Start and stop an interactive session by using a PSSession object</span></span>

```
PS C:\> $s = New-PSSession -ComputerName Server01
PS C:\> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS C:\> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

<span data-ttu-id="8072f-115">これらのコマンドは、Windows PowerShell セッション ( **PSSession** ) を使用する Server01 コンピューターとの対話型セッションを開始および停止します。</span><span class="sxs-lookup"><span data-stu-id="8072f-115">These commands start and stop an interactive session with the Server01 computer that uses a Windows PowerShell session ( **PSSession** ).</span></span>

<span data-ttu-id="8072f-116">対話型セッションは Windows PowerShell セッションを使用して開始されたため、対話型セッションが終了しても **PSSession** は引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="8072f-116">Because the interactive session was started by using a Windows PowerShell session, the **PSSession** is still available when the interactive session ends.</span></span>
<span data-ttu-id="8072f-117">*ComputerName* パラメーターを使用する場合、「 **-PSSession** 」と入力すると、対話型セッションが終了したときに閉じられる一時的なセッションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8072f-117">If you use the *ComputerName* parameter, **Enter-PSSession** creates a temporary session that it closes when the interactive session ends.</span></span>

<span data-ttu-id="8072f-118">最初のコマンドは、New-PSSession コマンドレットを使用して、Server01 コンピューター上に **PSSession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="8072f-118">The first command uses the New-PSSession cmdlet to create a **PSSession** on the Server01 computer.</span></span>
<span data-ttu-id="8072f-119">このコマンドは、 **PSSession** を $s 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="8072f-119">The command saves the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="8072f-120">2番目のコマンドは、 **Enter-pssession** を使用して、$S の **PSSession** を使用して対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="8072f-120">The second command uses **Enter-PSSession** to start an interactive session using the **PSSession** in $s.</span></span>

<span data-ttu-id="8072f-121">3番目のコマンドは、 **出口** を使用して対話型セッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="8072f-121">The third command uses **Exit-PSSession** to stop the interactive session.</span></span>

<span data-ttu-id="8072f-122">最後のコマンドは、$s 変数内の **PSSession** を表示します。</span><span class="sxs-lookup"><span data-stu-id="8072f-122">The final command displays the **PSSession** in the $s variable.</span></span>
<span data-ttu-id="8072f-123">**State** プロパティは、 **PSSession** がまだ開いており、使用可能であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="8072f-123">The **State** property shows the **PSSession** is still open and available for use.</span></span>

### <span data-ttu-id="8072f-124">例 3: Exit キーワードを使用してセッションを停止する</span><span class="sxs-lookup"><span data-stu-id="8072f-124">Example 3: Use the Exit keyword to stop a session</span></span>

```
PS C:\> Enter-PSSession -computername Server01
Server01\PS> exit
PS C:\>
```

<span data-ttu-id="8072f-125">この例では、 **Exit** キーワードを使用して、 **入力 PSSession** を使用して開始された対話型セッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="8072f-125">This example uses the **Exit** keyword to stop an interactive session started by using **Enter-PSSession** .</span></span>
<span data-ttu-id="8072f-126">**Exit** キーワードは、 **出口** を使用する場合と同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="8072f-126">The **Exit** keyword has the same effect as using **Exit-PSSession** .</span></span>

## <span data-ttu-id="8072f-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8072f-127">PARAMETERS</span></span>

### <span data-ttu-id="8072f-128">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8072f-128">CommonParameters</span></span>
<span data-ttu-id="8072f-129">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8072f-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8072f-130">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8072f-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8072f-131">入力</span><span class="sxs-lookup"><span data-stu-id="8072f-131">INPUTS</span></span>

### <span data-ttu-id="8072f-132">なし</span><span class="sxs-lookup"><span data-stu-id="8072f-132">None</span></span>
<span data-ttu-id="8072f-133">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="8072f-133">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="8072f-134">出力</span><span class="sxs-lookup"><span data-stu-id="8072f-134">OUTPUTS</span></span>

### <span data-ttu-id="8072f-135">なし</span><span class="sxs-lookup"><span data-stu-id="8072f-135">None</span></span>
<span data-ttu-id="8072f-136">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="8072f-136">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="8072f-137">注</span><span class="sxs-lookup"><span data-stu-id="8072f-137">NOTES</span></span>

* <span data-ttu-id="8072f-138">このコマンドレットは、共通パラメーターのみを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8072f-138">This cmdlet takes only the common parameters.</span></span>


## <span data-ttu-id="8072f-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8072f-139">RELATED LINKS</span></span>

[<span data-ttu-id="8072f-140">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="8072f-140">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="8072f-141">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="8072f-141">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="8072f-142">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="8072f-142">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="8072f-143">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="8072f-143">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="8072f-144">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="8072f-144">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="8072f-145">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="8072f-145">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="8072f-146">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="8072f-146">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="8072f-147">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="8072f-147">Remove-PSSession</span></span>](Remove-PSSession.md)
