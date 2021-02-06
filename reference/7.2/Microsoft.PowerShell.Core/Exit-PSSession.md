---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession
ms.openlocfilehash: b76f7dc87105318285c930b6cd2ae4ae10c2b0e7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601209"
---
# <span data-ttu-id="b066a-102">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="b066a-102">Exit-PSSession</span></span>

## <span data-ttu-id="b066a-103">概要</span><span class="sxs-lookup"><span data-stu-id="b066a-103">SYNOPSIS</span></span>
<span data-ttu-id="b066a-104">リモート コンピューターとの対話型セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="b066a-104">Ends an interactive session with a remote computer.</span></span>

## <span data-ttu-id="b066a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b066a-105">SYNTAX</span></span>

```
Exit-PSSession [<CommonParameters>]
```

## <span data-ttu-id="b066a-106">Description</span><span class="sxs-lookup"><span data-stu-id="b066a-106">DESCRIPTION</span></span>

<span data-ttu-id="b066a-107">**終了 PSSession** コマンドレットは、Enter-PSSession コマンドレットを使用して開始した対話型セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="b066a-107">The **Exit-PSSession** cmdlet ends interactive sessions that you started by using the Enter-PSSession cmdlet.</span></span>

<span data-ttu-id="b066a-108">また、 **Exit** キーワードを使用して、対話型セッションを終了することもできます。</span><span class="sxs-lookup"><span data-stu-id="b066a-108">You can also use the **Exit** keyword to end an interactive session.</span></span>
<span data-ttu-id="b066a-109">効果は、 **終了 PSSession** を使用する場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="b066a-109">The effect is the same as using **Exit-PSSession**.</span></span>

## <span data-ttu-id="b066a-110">例</span><span class="sxs-lookup"><span data-stu-id="b066a-110">EXAMPLES</span></span>

### <span data-ttu-id="b066a-111">例 1: 対話型セッションを開始および停止する</span><span class="sxs-lookup"><span data-stu-id="b066a-111">Example 1: Start and stop an interactive session</span></span>

```
PS> Enter-PSSession -computername Server01
Server01\PS> Exit-PSSession
PS>
```

<span data-ttu-id="b066a-112">これらのコマンドは、Server01 リモート コンピューターで対話型セッションを開始および停止します。</span><span class="sxs-lookup"><span data-stu-id="b066a-112">These commands start and then stop an interactive session with the Server01 remote computer.</span></span>

### <span data-ttu-id="b066a-113">例 2: PSSession オブジェクトを使用して対話型セッションを開始および停止する</span><span class="sxs-lookup"><span data-stu-id="b066a-113">Example 2: Start and stop an interactive session by using a PSSession object</span></span>

```
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

<span data-ttu-id="b066a-114">これらのコマンドは、PowerShell セッション (**PSSession**) を使用する Server01 コンピューターとの対話型セッションを開始および停止します。</span><span class="sxs-lookup"><span data-stu-id="b066a-114">These commands start and stop an interactive session with the Server01 computer that uses a PowerShell session (**PSSession**).</span></span>

<span data-ttu-id="b066a-115">対話型セッションは PowerShell セッションを使用して開始されたため、対話型セッションが終了しても **PSSession** は引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="b066a-115">Because the interactive session was started by using a PowerShell session, the **PSSession** is still available when the interactive session ends.</span></span>
<span data-ttu-id="b066a-116">*ComputerName* パラメーターを使用する場合、「 **-PSSession** 」と入力すると、対話型セッションが終了したときに閉じられる一時的なセッションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b066a-116">If you use the *ComputerName* parameter, **Enter-PSSession** creates a temporary session that it closes when the interactive session ends.</span></span>

<span data-ttu-id="b066a-117">最初のコマンドは、New-PSSession コマンドレットを使用して、Server01 コンピューター上に **PSSession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="b066a-117">The first command uses the New-PSSession cmdlet to create a **PSSession** on the Server01 computer.</span></span>
<span data-ttu-id="b066a-118">このコマンドは、 **PSSession** を $s 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="b066a-118">The command saves the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="b066a-119">2番目のコマンドは、 **Enter-pssession** を使用して、$S の **PSSession** を使用して対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="b066a-119">The second command uses **Enter-PSSession** to start an interactive session using the **PSSession** in $s.</span></span>

<span data-ttu-id="b066a-120">3番目のコマンドは、 **出口** を使用して対話型セッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="b066a-120">The third command uses **Exit-PSSession** to stop the interactive session.</span></span>

<span data-ttu-id="b066a-121">最後のコマンドは、$s 変数内の **PSSession** を表示します。</span><span class="sxs-lookup"><span data-stu-id="b066a-121">The final command displays the **PSSession** in the $s variable.</span></span>
<span data-ttu-id="b066a-122">**State** プロパティは、 **PSSession** がまだ開いており、使用可能であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="b066a-122">The **State** property shows the **PSSession** is still open and available for use.</span></span>

### <span data-ttu-id="b066a-123">例 3: Exit キーワードを使用してセッションを停止する</span><span class="sxs-lookup"><span data-stu-id="b066a-123">Example 3: Use the Exit keyword to stop a session</span></span>

```
PS> Enter-PSSession -computername Server01
Server01\PS> exit
PS>
```

<span data-ttu-id="b066a-124">この例では、 **Exit** キーワードを使用して、 **入力 PSSession** を使用して開始された対話型セッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="b066a-124">This example uses the **Exit** keyword to stop an interactive session started by using **Enter-PSSession**.</span></span>
<span data-ttu-id="b066a-125">**Exit** キーワードは、**出口** を使用する場合と同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="b066a-125">The **Exit** keyword has the same effect as using **Exit-PSSession**.</span></span>

## <span data-ttu-id="b066a-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b066a-126">PARAMETERS</span></span>

### <span data-ttu-id="b066a-127">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b066a-127">CommonParameters</span></span>

<span data-ttu-id="b066a-128">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b066a-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b066a-129">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b066a-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b066a-130">入力</span><span class="sxs-lookup"><span data-stu-id="b066a-130">INPUTS</span></span>

### <span data-ttu-id="b066a-131">なし</span><span class="sxs-lookup"><span data-stu-id="b066a-131">None</span></span>

<span data-ttu-id="b066a-132">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="b066a-132">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="b066a-133">出力</span><span class="sxs-lookup"><span data-stu-id="b066a-133">OUTPUTS</span></span>

### <span data-ttu-id="b066a-134">なし</span><span class="sxs-lookup"><span data-stu-id="b066a-134">None</span></span>

<span data-ttu-id="b066a-135">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="b066a-135">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="b066a-136">注</span><span class="sxs-lookup"><span data-stu-id="b066a-136">NOTES</span></span>

* <span data-ttu-id="b066a-137">このコマンドレットは、共通パラメーターのみを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b066a-137">This cmdlet takes only the common parameters.</span></span>

*

## <span data-ttu-id="b066a-138">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b066a-138">RELATED LINKS</span></span>

[<span data-ttu-id="b066a-139">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="b066a-139">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="b066a-140">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="b066a-140">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="b066a-141">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="b066a-141">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="b066a-142">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="b066a-142">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="b066a-143">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="b066a-143">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="b066a-144">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="b066a-144">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="b066a-145">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="b066a-145">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="b066a-146">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="b066a-146">Remove-PSSession</span></span>](Remove-PSSession.md)

