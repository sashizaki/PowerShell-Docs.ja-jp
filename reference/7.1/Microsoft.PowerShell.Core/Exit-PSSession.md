---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/08/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession
ms.openlocfilehash: b764aadc28d175f08fdcbaf56e904ff9310eb35b
ms.sourcegitcommit: 3a1d80e27438976101f216b8c3d623c61b868db8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "99975075"
---
# <span data-ttu-id="985ef-103">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="985ef-103">Exit-PSSession</span></span>

## <span data-ttu-id="985ef-104">構文</span><span class="sxs-lookup"><span data-stu-id="985ef-104">Synopsis</span></span>
<span data-ttu-id="985ef-105">リモート コンピューターとの対話型セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="985ef-105">Ends an interactive session with a remote computer.</span></span>

## <span data-ttu-id="985ef-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="985ef-106">SYNTAX</span></span>

```
Exit-PSSession [<CommonParameters>]
```

## <span data-ttu-id="985ef-107">説明</span><span class="sxs-lookup"><span data-stu-id="985ef-107">Description</span></span>

<span data-ttu-id="985ef-108">コマンドレットは `Exit-PSSession` 、コマンドレットを使用して開始した対話型セッションを終了し `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="985ef-108">The `Exit-PSSession` cmdlet ends interactive sessions that you started by using the `Enter-PSSession` cmdlet.</span></span>

<span data-ttu-id="985ef-109">また、キーワードを使用して、 `exit` 対話型セッションを終了することもできます。</span><span class="sxs-lookup"><span data-stu-id="985ef-109">You can also use the `exit` keyword to end an interactive session.</span></span> <span data-ttu-id="985ef-110">効果は、を使用する場合と同じです `Exit-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="985ef-110">The effect is the same as using `Exit-PSSession`.</span></span>

## <span data-ttu-id="985ef-111">例</span><span class="sxs-lookup"><span data-stu-id="985ef-111">Examples</span></span>

### <span data-ttu-id="985ef-112">例 1: 対話型セッションを開始および停止する</span><span class="sxs-lookup"><span data-stu-id="985ef-112">Example 1: Start and stop an interactive session</span></span>

```powershell
PS> Enter-PSSession -ComputerName Server01
Server01\PS> Exit-PSSession
PS>
```

<span data-ttu-id="985ef-113">これらのコマンドは、Server01 リモート コンピューターで対話型セッションを開始および停止します。</span><span class="sxs-lookup"><span data-stu-id="985ef-113">These commands start and then stop an interactive session with the Server01 remote computer.</span></span>

### <span data-ttu-id="985ef-114">例 2: PSSession オブジェクトを使用して対話型セッションを開始および停止する</span><span class="sxs-lookup"><span data-stu-id="985ef-114">Example 2: Start and stop an interactive session by using a PSSession object</span></span>

```powershell
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

<span data-ttu-id="985ef-115">これらのコマンドは、PowerShell セッション (**PSSession**) を使用する Server01 コンピューターとの対話型セッションを開始および停止します。</span><span class="sxs-lookup"><span data-stu-id="985ef-115">These commands start and stop an interactive session with the Server01 computer that uses a PowerShell session (**PSSession**).</span></span>

<span data-ttu-id="985ef-116">対話型セッションは PowerShell セッションを使用して開始されたため、対話型セッションが終了しても **PSSession** は引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="985ef-116">Because the interactive session was started by using a PowerShell session, the **PSSession** is still available when the interactive session ends.</span></span> <span data-ttu-id="985ef-117">_ComputerName_ パラメーターを使用すると、 `Enter-PSSession` 対話型セッションが終了したときに閉じられる一時的なセッションがによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="985ef-117">If you use the _ComputerName_ parameter, `Enter-PSSession` creates a temporary session that it closes when the interactive session ends.</span></span>

<span data-ttu-id="985ef-118">最初のコマンドは、コマンドレットを使用して、 `New-PSSession` Server01 コンピューター上に **PSSession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="985ef-118">The first command uses the `New-PSSession` cmdlet to create a **PSSession** on the Server01 computer.</span></span> <span data-ttu-id="985ef-119">このコマンドは、 **PSSession** を変数に保存し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="985ef-119">The command saves the **PSSession** in the `$s` variable.</span></span>

<span data-ttu-id="985ef-120">2番目のコマンドは、を使用し `Enter-PSSession` て、の **PSSession** を使用して対話型セッションを開始し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="985ef-120">The second command uses `Enter-PSSession` to start an interactive session using the **PSSession** in `$s`.</span></span>

<span data-ttu-id="985ef-121">3番目のコマンドは、を使用し `Exit-PSSession` て対話型セッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="985ef-121">The third command uses `Exit-PSSession` to stop the interactive session.</span></span>

<span data-ttu-id="985ef-122">最後のコマンドは、変数内の **PSSession** を表示し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="985ef-122">The final command displays the **PSSession** in the `$s` variable.</span></span> <span data-ttu-id="985ef-123">**State** プロパティは、 **PSSession** がまだ開いており、使用可能であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="985ef-123">The **State** property shows the **PSSession** is still open and available for use.</span></span>

### <span data-ttu-id="985ef-124">例 3: Exit キーワードを使用してセッションを停止する</span><span class="sxs-lookup"><span data-stu-id="985ef-124">Example 3: Use the Exit keyword to stop a session</span></span>

```powershell
PS> Enter-PSSession -ComputerName Server01
Server01\PS> exit
PS>
```

<span data-ttu-id="985ef-125">この例では、キーワードを使用して、 `exit` を使用して開始された対話型セッションを停止し `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="985ef-125">This example uses the `exit` keyword to stop an interactive session started by using `Enter-PSSession`.</span></span> <span data-ttu-id="985ef-126">キーワードは、 `exit` を使用する場合と同じ効果があり `Exit-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="985ef-126">The `exit` keyword has the same effect as using `Exit-PSSession`.</span></span>

## <span data-ttu-id="985ef-127">パラメーター</span><span class="sxs-lookup"><span data-stu-id="985ef-127">Parameters</span></span>

### <span data-ttu-id="985ef-128">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="985ef-128">CommonParameters</span></span>

<span data-ttu-id="985ef-129">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="985ef-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="985ef-130">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="985ef-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="985ef-131">入力</span><span class="sxs-lookup"><span data-stu-id="985ef-131">Inputs</span></span>

### <span data-ttu-id="985ef-132">なし</span><span class="sxs-lookup"><span data-stu-id="985ef-132">None</span></span>

<span data-ttu-id="985ef-133">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="985ef-133">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="985ef-134">出力</span><span class="sxs-lookup"><span data-stu-id="985ef-134">Outputs</span></span>

### <span data-ttu-id="985ef-135">なし</span><span class="sxs-lookup"><span data-stu-id="985ef-135">None</span></span>

<span data-ttu-id="985ef-136">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="985ef-136">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="985ef-137">ノート</span><span class="sxs-lookup"><span data-stu-id="985ef-137">Notes</span></span>

<span data-ttu-id="985ef-138">このコマンドレットは、共通パラメーターのみを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="985ef-138">This cmdlet takes only the common parameters.</span></span>

## <span data-ttu-id="985ef-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="985ef-139">RELATED LINKS</span></span>

[<span data-ttu-id="985ef-140">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="985ef-140">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="985ef-141">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="985ef-141">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="985ef-142">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="985ef-142">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="985ef-143">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="985ef-143">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="985ef-144">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="985ef-144">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="985ef-145">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="985ef-145">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="985ef-146">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="985ef-146">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="985ef-147">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="985ef-147">Remove-PSSession</span></span>](Remove-PSSession.md)
