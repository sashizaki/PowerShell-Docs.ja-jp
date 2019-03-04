---
title: コマンドレットの出力の種類 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell SDK], output
ms.assetid: 547e6695-e936-4cac-a90b-417d0dab393d
caps.latest.revision: 12
ms.openlocfilehash: 3efa98c7aa22fdaee8042bae99282aea0618ef5f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853928"
---
# <a name="types-of-cmdlet-output"></a><span data-ttu-id="a6f61-102">コマンドレットの出力の種類</span><span class="sxs-lookup"><span data-stu-id="a6f61-102">Types of cmdlet output</span></span>

<span data-ttu-id="a6f61-103">PowerShell は、出力を生成するためのコマンドレットを呼び出すことができるいくつかのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="a6f61-103">PowerShell provides several methods that can be called by cmdlets to generate output.</span></span> <span data-ttu-id="a6f61-104">これらのメソッドは、成功した場合のデータ ストリームやエラーのデータ ストリームなどの特定のデータ ストリームに出力を書き込む、特定の操作を使用します。</span><span class="sxs-lookup"><span data-stu-id="a6f61-104">These methods use a specific operation to write their output to a specific data stream, such as the success data stream or the error data stream.</span></span> <span data-ttu-id="a6f61-105">この記事では、出力とそれらを生成するために使用するメソッドの型について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6f61-105">This article describes the types of output and the methods used to generate them.</span></span>

## <a name="types-of-output"></a><span data-ttu-id="a6f61-106">出力の種類</span><span class="sxs-lookup"><span data-stu-id="a6f61-106">Types of output</span></span>

### <a name="success-output"></a><span data-ttu-id="a6f61-107">成功した場合の出力</span><span class="sxs-lookup"><span data-stu-id="a6f61-107">Success output</span></span>

<span data-ttu-id="a6f61-108">コマンドレットは、次のコマンドにパイプラインによって処理できるオブジェクトを返すことによって、成功を報告できます。</span><span class="sxs-lookup"><span data-stu-id="a6f61-108">Cmdlets can report success by returning an object that can be processed by the next command in the pipeline.</span></span> <span data-ttu-id="a6f61-109">このコマンドレットでは、そのアクションが正常に実行、コマンドレットは呼び出し、 [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a6f61-109">After the cmdlet has successfully performed its action, the cmdlet calls the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method.</span></span> <span data-ttu-id="a6f61-110">代わりに、このメソッドを呼び出すことをお勧め、 [System.Console.WriteLine](/dotnet/api/System.Console.WriteLine)または[System.Management.Automation.Host.PSHostUserInterface.WriteLine](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.WriteLine)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a6f61-110">We recommend that you call this method instead of the [System.Console.WriteLine](/dotnet/api/System.Console.WriteLine) or [System.Management.Automation.Host.PSHostUserInterface.WriteLine](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.WriteLine) methods.</span></span>

<span data-ttu-id="a6f61-111">行うことができます、 **PassThru**スイッチを通常のオブジェクトを返さないコマンドレットのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="a6f61-111">You can provide a **PassThru** switch parameter for cmdlets that do not typically return objects.</span></span>
<span data-ttu-id="a6f61-112">ときに、 **PassThru**にスイッチ パラメーターをコマンドラインに指定すると、コマンドレットがオブジェクトを取得する要求。</span><span class="sxs-lookup"><span data-stu-id="a6f61-112">When the **PassThru** switch parameter is specified at the command line, the cmdlet is asked to return an object.</span></span> <span data-ttu-id="a6f61-113">あるコマンドレットの例については、 **PassThru**パラメーターを参照してください[Add-history](/powershell/module/Microsoft.PowerShell.Core/Add-History)します。</span><span class="sxs-lookup"><span data-stu-id="a6f61-113">For an example of a cmdlet that has a **PassThru** parameter, see [Add-History](/powershell/module/Microsoft.PowerShell.Core/Add-History).</span></span>

### <a name="error-output"></a><span data-ttu-id="a6f61-114">エラー出力</span><span class="sxs-lookup"><span data-stu-id="a6f61-114">Error output</span></span>

<span data-ttu-id="a6f61-115">コマンドレットは、エラーを報告できます。</span><span class="sxs-lookup"><span data-stu-id="a6f61-115">Cmdlets can report errors.</span></span> <span data-ttu-id="a6f61-116">コマンドレットは、終了エラーが発生したときに例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="a6f61-116">When a terminating error occurs, the cmdlet throws an exception.</span></span> <span data-ttu-id="a6f61-117">コマンドレットを呼び出す、未終了エラーが発生したときに、 [System.Management.Automation.Provider.CmdletProvider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError)エラー データのストリームにエラー レコードを送信する方法。</span><span class="sxs-lookup"><span data-stu-id="a6f61-117">When a non-terminating error occurs, the cmdlet calls the [System.Management.Automation.Provider.CmdletProvider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) method to send an error record to the error data stream.</span></span> <span data-ttu-id="a6f61-118">エラー報告の詳細については、次を参照してください。[エラー Reporting 概念](./error-reporting-concepts.md)します。</span><span class="sxs-lookup"><span data-stu-id="a6f61-118">For more information about error reporting, see [Error Reporting Concepts](./error-reporting-concepts.md).</span></span>

### <a name="verbose-output"></a><span data-ttu-id="a6f61-119">詳細出力</span><span class="sxs-lookup"><span data-stu-id="a6f61-119">Verbose output</span></span>

<span data-ttu-id="a6f61-120">コマンドレットできますを提供します。 役に立つ情報、コマンドレットを呼び出してレコードの処理が正しく中に、 [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a6f61-120">Cmdlets can provide useful information to you while the cmdlet is correctly processing records by calling the [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method.</span></span> <span data-ttu-id="a6f61-121">メソッドは、アクションは続行される方法を示す詳細なメッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="a6f61-121">The method generates verbose messages that indicate how the action is proceeding.</span></span>

<span data-ttu-id="a6f61-122">既定では、詳細メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a6f61-122">By default, verbose messages are not displayed.</span></span> <span data-ttu-id="a6f61-123">指定することができます、 **Verbose**パラメーターをこれらのメッセージを表示するコマンドレットを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="a6f61-123">You can specify the **Verbose** parameter when the cmdlet is run to display these messages.</span></span> <span data-ttu-id="a6f61-124">**詳細な**はすべてのコマンドレットを使用できる一般的なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="a6f61-124">**Verbose** is a common parameter that is available to all cmdlets.</span></span>

### <a name="progress-output"></a><span data-ttu-id="a6f61-125">進行状況の出力</span><span class="sxs-lookup"><span data-stu-id="a6f61-125">Progress output</span></span>

<span data-ttu-id="a6f61-126">コマンドレットは、コマンドレットがディレクトリの再帰的にコピーするなど、完了に長い時間がかかるタスクを実行するときに進行状況に関する情報を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="a6f61-126">Cmdlets can provide progress information to you when the cmdlet is performing tasks that take a long time to complete, such as copying a directory recursively.</span></span> <span data-ttu-id="a6f61-127">呼び出し、コマンドレットの進行状況に関する情報を表示するのには、 [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a6f61-127">To display progress information the cmdlet calls the [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) method.</span></span>

### <a name="debug-output"></a><span data-ttu-id="a6f61-128">デバッグ出力</span><span class="sxs-lookup"><span data-stu-id="a6f61-128">Debug output</span></span>

<span data-ttu-id="a6f61-129">コマンドレットは、コマンドレット コードのトラブルシューティングに役立つものをデバッグ メッセージを提供できます。</span><span class="sxs-lookup"><span data-stu-id="a6f61-129">Cmdlets can provide debug messages that are helpful when troubleshooting the cmdlet code.</span></span> <span data-ttu-id="a6f61-130">呼び出し、コマンドレットのデバッグ情報を表示するのには、 [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a6f61-130">To display debug information the cmdlet calls the [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method.</span></span>

<span data-ttu-id="a6f61-131">既定では、デバッグ メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a6f61-131">By default, debug messages are not displayed.</span></span> <span data-ttu-id="a6f61-132">指定することができます、**デバッグ**パラメーターをこれらのメッセージを表示するコマンドレットを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="a6f61-132">You can specify the **Debug** parameter when the cmdlet is run to display these messages.</span></span> <span data-ttu-id="a6f61-133">**デバッグ**はすべてのコマンドレットを使用できる一般的なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="a6f61-133">**Debug** is a common parameter that is available to all cmdlets.</span></span>

### <a name="warning-output"></a><span data-ttu-id="a6f61-134">警告の出力</span><span class="sxs-lookup"><span data-stu-id="a6f61-134">Warning output</span></span>

<span data-ttu-id="a6f61-135">コマンドレットは呼び出すことによって警告メッセージを表示することができます、 [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a6f61-135">Cmdlets can display warning messages by calling the [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method.</span></span>

<span data-ttu-id="a6f61-136">既定では、警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6f61-136">By default, warning messages are displayed.</span></span> <span data-ttu-id="a6f61-137">ただし、使用して警告メッセージを構成することができます、`$WarningPreference`変数またはを使用して、 **Verbose**と**デバッグ**コマンドレットが呼び出されたときにパラメーター。</span><span class="sxs-lookup"><span data-stu-id="a6f61-137">However, you can configure warning messages by using the `$WarningPreference` variable or by using the **Verbose** and **Debug** parameters when the cmdlet is called.</span></span>

## <a name="displaying-output"></a><span data-ttu-id="a6f61-138">出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="a6f61-138">Displaying output</span></span>

<span data-ttu-id="a6f61-139">すべての書き込みメソッドの呼び出しには、コンテンツの表示を特定のランタイム変数によって決まります。</span><span class="sxs-lookup"><span data-stu-id="a6f61-139">For all write-method calls, the content display is determined by specific runtime variables.</span></span> <span data-ttu-id="a6f61-140">例外は、 [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a6f61-140">The exception is the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method.</span></span> <span data-ttu-id="a6f61-141">これらの変数を使用するには、適切なコードで呼び出しの正しい場所を記述して、出力が表示される場合、またはについて心配せずの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a6f61-141">By using these variables, you can make the appropriate write call at the correct place in your code and not worry about when or if the output should be displayed.</span></span>

## <a name="accessing-the-output-functionality-of-a-host-application"></a><span data-ttu-id="a6f61-142">ホスト アプリケーションの出力の機能にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a6f61-142">Accessing the output functionality of a host application</span></span>

<span data-ttu-id="a6f61-143">直接 PowerShell ランタイムからホスト アプリケーションの出力機能にアクセスするコマンドレットを設計することもできます。</span><span class="sxs-lookup"><span data-stu-id="a6f61-143">You can also design a cmdlet to directly access the output functionality of a host application through the PowerShell runtime.</span></span> <span data-ttu-id="a6f61-144">ホストの代わりに PowerShell で提供される Api を使用して[System.Console](/dotnet/api/System.Console)または[System.Windows.Forms](/dotnet/api/System.Windows.Forms)により、コマンドレットは、さまざまなホストで動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="a6f61-144">Using the host APIs provided by PowerShell instead of [System.Console](/dotnet/api/System.Console) or [System.Windows.Forms](/dotnet/api/System.Windows.Forms) ensures that your cmdlet will work with a variety of hosts.</span></span> <span data-ttu-id="a6f61-145">例: **powershell.exe**コンソールのホスト、 **powershell_ise.exe**グラフィカル ホストでは、PowerShell リモート処理ホスト、およびサードパーティのホスト。</span><span class="sxs-lookup"><span data-stu-id="a6f61-145">For example: the **powershell.exe** console host, the **powershell_ise.exe** graphical host, the PowerShell remoting host, and third-party hosts.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6f61-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6f61-146">See also</span></span>

[<span data-ttu-id="a6f61-147">エラー報告の概念</span><span class="sxs-lookup"><span data-stu-id="a6f61-147">Error Reporting Concepts</span></span>](./error-reporting-concepts.md)

[<span data-ttu-id="a6f61-148">コマンドレットの概要</span><span class="sxs-lookup"><span data-stu-id="a6f61-148">Cmdlet Overview</span></span>](./cmdlet-overview.md)

[<span data-ttu-id="a6f61-149">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="a6f61-149">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)