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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369291"
---
# <a name="types-of-cmdlet-output"></a><span data-ttu-id="cc94f-102">コマンドレットの出力の種類</span><span class="sxs-lookup"><span data-stu-id="cc94f-102">Types of cmdlet output</span></span>

<span data-ttu-id="cc94f-103">PowerShell には、コマンドレットによって出力を生成するために呼び出すことができるメソッドがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="cc94f-103">PowerShell provides several methods that can be called by cmdlets to generate output.</span></span> <span data-ttu-id="cc94f-104">これらのメソッドは、特定の操作を使用して、成功データストリームやエラーデータストリームなどの特定のデータストリームに出力を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="cc94f-104">These methods use a specific operation to write their output to a specific data stream, such as the success data stream or the error data stream.</span></span> <span data-ttu-id="cc94f-105">この記事では、出力の種類と、それらを生成するために使用されるメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cc94f-105">This article describes the types of output and the methods used to generate them.</span></span>

## <a name="types-of-output"></a><span data-ttu-id="cc94f-106">出力の種類</span><span class="sxs-lookup"><span data-stu-id="cc94f-106">Types of output</span></span>

### <a name="success-output"></a><span data-ttu-id="cc94f-107">成功の出力</span><span class="sxs-lookup"><span data-stu-id="cc94f-107">Success output</span></span>

<span data-ttu-id="cc94f-108">コマンドレットは、パイプラインの次のコマンドで処理できるオブジェクトを返すことで成功を報告できます。</span><span class="sxs-lookup"><span data-stu-id="cc94f-108">Cmdlets can report success by returning an object that can be processed by the next command in the pipeline.</span></span> <span data-ttu-id="cc94f-109">コマンドレットは、アクションを正常に実行した後、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cc94f-109">After the cmdlet has successfully performed its action, the cmdlet calls the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method.</span></span> <span data-ttu-id="cc94f-110">[PSHostUserInterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.WriteLine)メソッドまたはメソッドの代わりに、このメソッドを呼び出すことをお勧めします。この[メソッドは、](/dotnet/api/System.Console.WriteLine)</span><span class="sxs-lookup"><span data-stu-id="cc94f-110">We recommend that you call this method instead of the [System.Console.WriteLine](/dotnet/api/System.Console.WriteLine) or [System.Management.Automation.Host.PSHostUserInterface.WriteLine](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.WriteLine) methods.</span></span>

<span data-ttu-id="cc94f-111">通常はオブジェクトを返さないコマンドレットには、 **PassThru**スイッチパラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="cc94f-111">You can provide a **PassThru** switch parameter for cmdlets that do not typically return objects.</span></span>
<span data-ttu-id="cc94f-112">コマンドラインで**PassThru**スイッチパラメーターを指定すると、コマンドレットはオブジェクトを返すように求められます。</span><span class="sxs-lookup"><span data-stu-id="cc94f-112">When the **PassThru** switch parameter is specified at the command line, the cmdlet is asked to return an object.</span></span> <span data-ttu-id="cc94f-113">**PassThru**パラメーターを持つコマンドレットの例については、「[追加-履歴](/powershell/module/Microsoft.PowerShell.Core/Add-History)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc94f-113">For an example of a cmdlet that has a **PassThru** parameter, see [Add-History](/powershell/module/Microsoft.PowerShell.Core/Add-History).</span></span>

### <a name="error-output"></a><span data-ttu-id="cc94f-114">エラー出力</span><span class="sxs-lookup"><span data-stu-id="cc94f-114">Error output</span></span>

<span data-ttu-id="cc94f-115">コマンドレットはエラーを報告できます。</span><span class="sxs-lookup"><span data-stu-id="cc94f-115">Cmdlets can report errors.</span></span> <span data-ttu-id="cc94f-116">終了エラーが発生すると、コマンドレットは例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="cc94f-116">When a terminating error occurs, the cmdlet throws an exception.</span></span> <span data-ttu-id="cc94f-117">終了しないエラーが発生すると、コマンドレットは[WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError)メソッドを呼び出して、エラーレコードをエラーデータストリームに送信しています。</span><span class="sxs-lookup"><span data-stu-id="cc94f-117">When a non-terminating error occurs, the cmdlet calls the [System.Management.Automation.Provider.CmdletProvider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) method to send an error record to the error data stream.</span></span> <span data-ttu-id="cc94f-118">エラー報告の詳細については、「[エラーレポートの概念](./error-reporting-concepts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc94f-118">For more information about error reporting, see [Error Reporting Concepts](./error-reporting-concepts.md).</span></span>

### <a name="verbose-output"></a><span data-ttu-id="cc94f-119">詳細出力</span><span class="sxs-lookup"><span data-stu-id="cc94f-119">Verbose output</span></span>

<span data-ttu-id="cc94f-120">コマンドレットは、使用しているユーザーにとって有用な情報を提供します。また、コマンドレットで[は、このメソッドを](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)呼び出すことによってレコードが正しく処理されます。</span><span class="sxs-lookup"><span data-stu-id="cc94f-120">Cmdlets can provide useful information to you while the cmdlet is correctly processing records by calling the [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method.</span></span> <span data-ttu-id="cc94f-121">メソッドは、アクションの進行状況を示す詳細メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="cc94f-121">The method generates verbose messages that indicate how the action is proceeding.</span></span>

<span data-ttu-id="cc94f-122">既定では、詳細メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="cc94f-122">By default, verbose messages are not displayed.</span></span> <span data-ttu-id="cc94f-123">これらのメッセージを表示するには、コマンドレットを実行するときに**Verbose**パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc94f-123">You can specify the **Verbose** parameter when the cmdlet is run to display these messages.</span></span> <span data-ttu-id="cc94f-124">**Verbose**は、すべてのコマンドレットで使用できる共通のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="cc94f-124">**Verbose** is a common parameter that is available to all cmdlets.</span></span>

### <a name="progress-output"></a><span data-ttu-id="cc94f-125">進行状況の出力</span><span class="sxs-lookup"><span data-stu-id="cc94f-125">Progress output</span></span>

<span data-ttu-id="cc94f-126">コマンドレットは、ディレクトリを再帰的にコピーするなど、完了までに時間がかかるタスクを実行しているときに、進行状況に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cc94f-126">Cmdlets can provide progress information to you when the cmdlet is performing tasks that take a long time to complete, such as copying a directory recursively.</span></span> <span data-ttu-id="cc94f-127">進行状況に関する情報を表示するには、コマンドレットで[system.servicemodel メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress)呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cc94f-127">To display progress information the cmdlet calls the [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) method.</span></span>

### <a name="debug-output"></a><span data-ttu-id="cc94f-128">デバッグ出力</span><span class="sxs-lookup"><span data-stu-id="cc94f-128">Debug output</span></span>

<span data-ttu-id="cc94f-129">コマンドレットは、コマンドレットコードのトラブルシューティングに役立つデバッグメッセージを提供できます。</span><span class="sxs-lookup"><span data-stu-id="cc94f-129">Cmdlets can provide debug messages that are helpful when troubleshooting the cmdlet code.</span></span> <span data-ttu-id="cc94f-130">デバッグ情報を表示するには、コマンドレットに[よって、system.string メソッドが](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cc94f-130">To display debug information the cmdlet calls the [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method.</span></span>

<span data-ttu-id="cc94f-131">既定では、デバッグメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="cc94f-131">By default, debug messages are not displayed.</span></span> <span data-ttu-id="cc94f-132">コマンドレットを実行してこれらのメッセージを表示する場合は、 **Debug**パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="cc94f-132">You can specify the **Debug** parameter when the cmdlet is run to display these messages.</span></span> <span data-ttu-id="cc94f-133">**Debug**は、すべてのコマンドレットで使用できる共通パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="cc94f-133">**Debug** is a common parameter that is available to all cmdlets.</span></span>

### <a name="warning-output"></a><span data-ttu-id="cc94f-134">警告出力</span><span class="sxs-lookup"><span data-stu-id="cc94f-134">Warning output</span></span>

<span data-ttu-id="cc94f-135">コマンドレット[では、system.string メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning)呼び出すことで警告メッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="cc94f-135">Cmdlets can display warning messages by calling the [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method.</span></span>

<span data-ttu-id="cc94f-136">既定では、警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc94f-136">By default, warning messages are displayed.</span></span> <span data-ttu-id="cc94f-137">ただし、警告メッセージを構成するには、`$WarningPreference` 変数を使用するか、コマンドレットが呼び出されたときに**Verbose**パラメーターと**Debug**パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="cc94f-137">However, you can configure warning messages by using the `$WarningPreference` variable or by using the **Verbose** and **Debug** parameters when the cmdlet is called.</span></span>

## <a name="displaying-output"></a><span data-ttu-id="cc94f-138">出力の表示</span><span class="sxs-lookup"><span data-stu-id="cc94f-138">Displaying output</span></span>

<span data-ttu-id="cc94f-139">すべての書き込みメソッド呼び出しでは、コンテンツの表示は特定のランタイム変数によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="cc94f-139">For all write-method calls, the content display is determined by specific runtime variables.</span></span> <span data-ttu-id="cc94f-140">例外として、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="cc94f-140">The exception is the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method.</span></span> <span data-ttu-id="cc94f-141">これらの変数を使用すると、適切な書き込み呼び出しをコード内の適切な場所で行うことができ、出力を表示するタイミングやタイミングを気にする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="cc94f-141">By using these variables, you can make the appropriate write call at the correct place in your code and not worry about when or if the output should be displayed.</span></span>

## <a name="accessing-the-output-functionality-of-a-host-application"></a><span data-ttu-id="cc94f-142">ホストアプリケーションの出力機能へのアクセス</span><span class="sxs-lookup"><span data-stu-id="cc94f-142">Accessing the output functionality of a host application</span></span>

<span data-ttu-id="cc94f-143">PowerShell ランタイムを使用してホストアプリケーションの出力機能に直接アクセスするようにコマンドレットを設計することもできます。</span><span class="sxs-lookup"><span data-stu-id="cc94f-143">You can also design a cmdlet to directly access the output functionality of a host application through the PowerShell runtime.</span></span> <span data-ttu-id="cc94f-144">[System.](/dotnet/api/System.Console) [Windows. フォーム](/dotnet/api/System.Windows.Forms)ではなく、PowerShell によって提供されるホスト api を使用すると、コマンドレットがさまざまなホストで動作することが保証されます。</span><span class="sxs-lookup"><span data-stu-id="cc94f-144">Using the host APIs provided by PowerShell instead of [System.Console](/dotnet/api/System.Console) or [System.Windows.Forms](/dotnet/api/System.Windows.Forms) ensures that your cmdlet will work with a variety of hosts.</span></span> <span data-ttu-id="cc94f-145">たとえば、 **powershell**のコンソールホスト、 **powershell_ise**のグラフィカルホスト、powershell リモート処理ホスト、サードパーティのホストなどです。</span><span class="sxs-lookup"><span data-stu-id="cc94f-145">For example: the **powershell.exe** console host, the **powershell_ise.exe** graphical host, the PowerShell remoting host, and third-party hosts.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc94f-146">「</span><span class="sxs-lookup"><span data-stu-id="cc94f-146">See also</span></span>

[<span data-ttu-id="cc94f-147">エラー報告の概念</span><span class="sxs-lookup"><span data-stu-id="cc94f-147">Error Reporting Concepts</span></span>](./error-reporting-concepts.md)

[<span data-ttu-id="cc94f-148">コマンドレットの概要</span><span class="sxs-lookup"><span data-stu-id="cc94f-148">Cmdlet Overview</span></span>](./cmdlet-overview.md)

[<span data-ttu-id="cc94f-149">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="cc94f-149">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)