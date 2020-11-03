---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 07/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/register-wmievent?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-WmiEvent
ms.openlocfilehash: be29ce6376dea7686c0c063cc5528fbc7d840a9d
ms.sourcegitcommit: 41b072f0b6046d619b0e7f758982783fb648a3d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2020
ms.locfileid: "93219048"
---
# <span data-ttu-id="d07d5-103">Register-WmiEvent</span><span class="sxs-lookup"><span data-stu-id="d07d5-103">Register-WmiEvent</span></span>

## <span data-ttu-id="d07d5-104">概要</span><span class="sxs-lookup"><span data-stu-id="d07d5-104">SYNOPSIS</span></span>
<span data-ttu-id="d07d5-105">Windows Management Instrumentation (WMI) イベントにサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="d07d5-105">Subscribes to a Windows Management Instrumentation (WMI) event.</span></span>

## <span data-ttu-id="d07d5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d07d5-106">SYNTAX</span></span>

### <span data-ttu-id="d07d5-107">クラス (既定値)</span><span class="sxs-lookup"><span data-stu-id="d07d5-107">class (Default)</span></span>

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Class] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="d07d5-108">query</span><span class="sxs-lookup"><span data-stu-id="d07d5-108">query</span></span>

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Query] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="d07d5-109">Description</span><span class="sxs-lookup"><span data-stu-id="d07d5-109">DESCRIPTION</span></span>

<span data-ttu-id="d07d5-110">この `Register-WmiEvent` コマンドレットは、ローカルコンピューターまたはリモートコンピューター上の Windows Management Instrumentation (WMI) イベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="d07d5-110">The `Register-WmiEvent` cmdlet subscribes to Windows Management Instrumentation (WMI) events on the local computer or on a remote computer.</span></span>

<span data-ttu-id="d07d5-111">サブスクライブされた WMI イベントの発生時には、リモート コンピューター上で発生した場合でもローカル セッションのイベント キューに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-111">When the subscribed WMI event is raised, it is added to the event queue in your local session even if the event occurs on a remote computer.</span></span> <span data-ttu-id="d07d5-112">イベントキュー内のイベントを取得するには、コマンドレットを使用し `Get-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-112">To get events in the event queue, use the `Get-Event` cmdlet.</span></span>

<span data-ttu-id="d07d5-113">のパラメーターを使用して、 `Register-WmiEvent` リモートコンピューター上のイベントをサブスクライブしたり、キュー内のイベントを識別するのに役立つイベントのプロパティ値を指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-113">You can use the parameters of `Register-WmiEvent` to subscribe to events on remote computers and to specify the property values of the events that can help you identify the event in the queue.</span></span> <span data-ttu-id="d07d5-114">**Action** パラメーターを使用して、サブスクライブしたイベントが発生したときに実行するアクションを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-114">You can also use the **Action** parameter to specify actions to take when a subscribed event is raised.</span></span>

<span data-ttu-id="d07d5-115">イベントにサブスクライブするとき、イベント サブスクライバーがセッションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-115">When you subscribe to an event, an event subscriber is added to your session.</span></span> <span data-ttu-id="d07d5-116">セッションのイベント サブスクライバーを取得するには、`Get-EventSubscriber` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-116">To get the event subscribers in the session, use the `Get-EventSubscriber` cmdlet.</span></span> <span data-ttu-id="d07d5-117">サブスクリプションをキャンセルするには、`Unregister-Event` コマンドレットを使用して、セッションからイベント サブスクライバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-117">To cancel the subscription, use the `Unregister-Event` cmdlet, which deletes the event subscriber from the session.</span></span>

<span data-ttu-id="d07d5-118">Windows PowerShell 3.0 で導入された新しい Common Information Model (CIM) コマンドレットでは、WMI コマンドレットと同じタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-118">New Common Information Model (CIM) cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span> <span data-ttu-id="d07d5-119">CIM コマンドレットは、WS-Management (WSMan) 標準と CIM 標準に準拠しています。これにより、コマンドレットは、Windows オペレーティングシステムを実行するコンピューターと他のオペレーティングシステムを実行するコンピューターを管理する同じ手法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-119">The CIM cmdlets comply with WS-Management (WSMan) standards and with the CIM standard, which enables the cmdlets to use the same techniques to manage computers that run the Windows operating system and those that run other operating systems.</span></span> <span data-ttu-id="d07d5-120">を使用する代わり `Register-WmiEvent` に、 [CimIndicationEvent](../cimcmdlets/register-cimindicationevent.md) コマンドレットを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="d07d5-120">Instead of using `Register-WmiEvent`, consider using the [Register-CimIndicationEvent](../cimcmdlets/register-cimindicationevent.md) cmdlet.</span></span>

## <span data-ttu-id="d07d5-121">例</span><span class="sxs-lookup"><span data-stu-id="d07d5-121">EXAMPLES</span></span>

### <span data-ttu-id="d07d5-122">例 1: クラスによって生成されたイベントをサブスクライブする</span><span class="sxs-lookup"><span data-stu-id="d07d5-122">Example 1: Subscribe to events generated by a class</span></span>

<span data-ttu-id="d07d5-123">このコマンドは、 **Win32_ProcessStartTrace** クラスによって生成されたイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="d07d5-123">This command subscribes to the events generated by the **Win32_ProcessStartTrace** class.</span></span> <span data-ttu-id="d07d5-124">プロセスが開始されるたびに、このクラスによってイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-124">This class raises an event whenever a process starts.</span></span>

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted"
```

### <span data-ttu-id="d07d5-125">例 2: プロセスの作成イベントをサブスクライブする</span><span class="sxs-lookup"><span data-stu-id="d07d5-125">Example 2: Subscribe to creation events for a process</span></span>

<span data-ttu-id="d07d5-126">このコマンドは、クエリを使用して、Win32_process インスタンス作成イベントにサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="d07d5-126">This command uses a query to subscribe to Win32_process instance creation events.</span></span>

```powershell
$wmiParameters = @{
  Query = "select * from __instancecreationevent within 5 where targetinstance isa 'win32_process'"
  SourceIdentifier = "WMIProcess"
  MessageData = "Test 01"
  TimeOut = 500
}
Register-WmiEvent @wmiParameters
```

### <span data-ttu-id="d07d5-127">例 3: アクションを使用してイベントに応答する</span><span class="sxs-lookup"><span data-stu-id="d07d5-127">Example 3: Use an action to respond to an event</span></span>

<span data-ttu-id="d07d5-128">この例は、イベントに応えるアクションの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d07d5-128">This example shows how to use an action to respond to an event.</span></span> <span data-ttu-id="d07d5-129">この場合、プロセスの開始時に、 `Start-Process` 現在のセッションのすべてのコマンドが XML ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-129">In this case, when a process starts, any `Start-Process` commands in the current session are written to an XML file.</span></span>

```powershell
$action = { Get-History | where { $_.commandline -like "*start-process*" } | export-cliXml "commandHistory.clixml" }
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted" -Action $action
```

```Output
Id    Name            State      HasMoreData   Location  Command
--    ----            -----      -----------   --------  -------
1     ProcessStarted  NotStarted False                   get-history | where {...
```

<span data-ttu-id="d07d5-130">**Action** パラメーターを使用すると、は `Register-WmiEvent` イベントアクションを表すバックグラウンドジョブを返します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-130">When you use the **Action** parameter, `Register-WmiEvent` returns a background job that represents the event action.</span></span> <span data-ttu-id="d07d5-131">やなどの **ジョブ** コマンドレットを使用して、 `Get-Job` `Receive-Job` イベントジョブを管理できます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-131">You can use the **Job** cmdlets, such as `Get-Job` and `Receive-Job`, to manage the event job.</span></span>

<span data-ttu-id="d07d5-132">詳細については、「about_Jobs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d07d5-132">For more information, see about_Jobs.</span></span>

### <span data-ttu-id="d07d5-133">例 4: リモートコンピューターのイベントに登録する</span><span class="sxs-lookup"><span data-stu-id="d07d5-133">Example 4: Register for events on a remote computer</span></span>

<span data-ttu-id="d07d5-134">この例では、Server01 リモート コンピューターのイベントを登録します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-134">This example registers for events on the Server01 remote computer.</span></span>

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "Start" -Computername Server01
Get-Event -SourceIdentifier "Start"
```

<span data-ttu-id="d07d5-135">イベントは WMI によってローカル コンピューターに返され、現在のセッションのイベント キューに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-135">WMI returns the events to the local computer and stores them in the event queue in the current session.</span></span> <span data-ttu-id="d07d5-136">イベントを取得するには、ローカル `Get-Event` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-136">To retrieve the events, run a local `Get-Event` command.</span></span>

## <span data-ttu-id="d07d5-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d07d5-137">PARAMETERS</span></span>

### <span data-ttu-id="d07d5-138">-Action</span><span class="sxs-lookup"><span data-stu-id="d07d5-138">-Action</span></span>

<span data-ttu-id="d07d5-139">イベントを処理するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-139">Specifies commands that handle the events.</span></span> <span data-ttu-id="d07d5-140">**アクション** パラメーターのコマンドは、イベントをイベントキューに送信するのではなく、イベントが発生したときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-140">The commands in the **Action** parameter run when an event is raised instead of sending the event to the event queue.</span></span> <span data-ttu-id="d07d5-141">コマンドを中かっこ () で囲み、 `{}` スクリプトブロックを作成します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-141">Enclose the commands in braces (`{}`) to create a script block.</span></span>

<span data-ttu-id="d07d5-142">**Action** の値には `$Event` 、 `$EventSubscriber` `$Sender` `$EventArgs` `$Args` イベントに関する情報を **action** スクリプトブロックに提供する、、、、および自動変数を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-142">The value of **Action** can include the `$Event`, `$EventSubscriber`, `$Sender`, `$EventArgs`, and `$Args` automatic variables, which provide information about the event to the **Action** script block.</span></span> <span data-ttu-id="d07d5-143">詳細については、「about_Automatic_Variables」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d07d5-143">For more information, see about_Automatic_Variables.</span></span>

<span data-ttu-id="d07d5-144">アクションを指定すると、は `Register-WmiEvent` そのアクションを表すイベントジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-144">When you specify an action, `Register-WmiEvent` returns an event job object that represents that action.</span></span> <span data-ttu-id="d07d5-145">**ジョブ** の名詞を含むコマンドレット ( **job** コマンドレット) を使用して、イベントジョブを管理できます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-145">You can use the cmdlets that contain the **Job** noun (the **Job** cmdlets) to manage the event job.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: 101
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d07d5-146">-クラス</span><span class="sxs-lookup"><span data-stu-id="d07d5-146">-Class</span></span>

<span data-ttu-id="d07d5-147">サブスクライブするイベントを指定します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-147">Specifies the event to which you are subscribing.</span></span> <span data-ttu-id="d07d5-148">イベントを生成する WMI クラスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-148">Enter the WMI class that generates the events.</span></span> <span data-ttu-id="d07d5-149">すべてのコマンドで **クラス** または **クエリ** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="d07d5-149">A **Class** or **Query** parameter is required in every command.</span></span>

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d07d5-150">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d07d5-150">-ComputerName</span></span>

<span data-ttu-id="d07d5-151">コマンドを実行するコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-151">Specifies the name of the computer on which the command runs.</span></span> <span data-ttu-id="d07d5-152">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="d07d5-152">The default is the local computer.</span></span>

<span data-ttu-id="d07d5-153">コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-153">Type the NetBIOS name, an IP address, or a fully qualified domain name of the computer.</span></span> <span data-ttu-id="d07d5-154">ローカルコンピューターを指定するには、コンピューター名、ドット ( `.` )、または localhost を入力します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-154">To specify the local computer, type the computer name, a dot (`.`), or localhost.</span></span>

<span data-ttu-id="d07d5-155">このパラメーターは、Windows PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="d07d5-155">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="d07d5-156">コンピューターがリモート コマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-156">You can use the **ComputerName** parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d07d5-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="d07d5-157">-Credential</span></span>

<span data-ttu-id="d07d5-158">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-158">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="d07d5-159">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="d07d5-159">The default is the current user.</span></span>

<span data-ttu-id="d07d5-160">User01 や Domain01\user01」などのユーザー名を入力するか、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-160">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="d07d5-161">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-161">If you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d07d5-162">-転送</span><span class="sxs-lookup"><span data-stu-id="d07d5-162">-Forward</span></span>

<span data-ttu-id="d07d5-163">このコマンドレットによって、このサブスクリプションのイベントがローカルコンピューター上のセッションに送信されることを示します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-163">Indicates that this cmdlet sends events for this subscription to the session on the local computer.</span></span>
<span data-ttu-id="d07d5-164">このパラメーターは、リモート コンピューターまたはリモート セッションのイベントに登録する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-164">Use this parameter when you are registering for events on a remote computer or in a remote session.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d07d5-165">-MaxTriggerCount</span><span class="sxs-lookup"><span data-stu-id="d07d5-165">-MaxTriggerCount</span></span>

<span data-ttu-id="d07d5-166">最大トリガー数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-166">Specifies the maximum trigger count.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d07d5-167">-MessageData</span><span class="sxs-lookup"><span data-stu-id="d07d5-167">-MessageData</span></span>

<span data-ttu-id="d07d5-168">このイベント サブスクリプションに関連付けられる任意の追加データを指定します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-168">Specifies any additional data to be associated with this event subscription.</span></span> <span data-ttu-id="d07d5-169">このパラメーターの値は、このサブスクリプションに関連付けられているすべてのイベントの **Messagedata** プロパティに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-169">The value of this parameter appears in the **MessageData** property of all events associated with this subscription.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d07d5-170">-Namespace</span><span class="sxs-lookup"><span data-stu-id="d07d5-170">-Namespace</span></span>

<span data-ttu-id="d07d5-171">WMI クラスの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-171">Specifies the namespace of the WMI class.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d07d5-172">-Query</span><span class="sxs-lookup"><span data-stu-id="d07d5-172">-Query</span></span>

<span data-ttu-id="d07d5-173">WMI イベントクラスを識別する WMI Query Language (WQL) のクエリを指定します。たとえば、のように `select * from __InstanceDeletionEvent` なります。</span><span class="sxs-lookup"><span data-stu-id="d07d5-173">Specifies a query in WMI Query Language (WQL) that identifies the WMI event class, such as: `select * from __InstanceDeletionEvent`.</span></span>

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d07d5-174">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="d07d5-174">-SourceIdentifier</span></span>

<span data-ttu-id="d07d5-175">サブスクリプション用に選択した名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-175">Specifies a name that you select for the subscription.</span></span> <span data-ttu-id="d07d5-176">選択した名前は、現在のセッションで一意でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="d07d5-176">The name that you select must be unique in the current session.</span></span> <span data-ttu-id="d07d5-177">既定値は Windows PowerShell が割り当てた GUID です。</span><span class="sxs-lookup"><span data-stu-id="d07d5-177">The default value is the GUID that Windows PowerShell assigns.</span></span>

<span data-ttu-id="d07d5-178">このパラメーターの値は、サブスクライバー オブジェクトおよびこのサブスクリプションに関連付けられたすべてのイベント オブジェクトの **SourceIdentifier** プロパティの値に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-178">The value of this parameter appears in the value of the **SourceIdentifier** property of the subscriber object and of all event objects associated with this subscription.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d07d5-179">-SupportEvent</span><span class="sxs-lookup"><span data-stu-id="d07d5-179">-SupportEvent</span></span>

<span data-ttu-id="d07d5-180">このコマンドレットがイベントサブスクリプションを非表示にすることを示します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-180">Indicates that this cmdlet hides the event subscription.</span></span> <span data-ttu-id="d07d5-181">このパラメーターは、現在のサブスクリプションがさらに複雑なイベント登録メカニズムの一部であり、単独で検出されない場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-181">Use this parameter when the current subscription is part of a more complex event registration mechanism and it should not be discovered independently.</span></span>

<span data-ttu-id="d07d5-182">**Supportevent** パラメーターを使用して作成されたサブスクリプションを表示またはキャンセルする **Force** には、 `Get-EventSubscriber` コマンドレットとコマンドレットの Force パラメーターを指定し `Unregister-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-182">To view or cancel a subscription that was created by using the **SupportEvent** parameter, specify the **Force** parameter of the `Get-EventSubscriber` and `Unregister-Event` cmdlets.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d07d5-183">-タイムアウト</span><span class="sxs-lookup"><span data-stu-id="d07d5-183">-Timeout</span></span>

<span data-ttu-id="d07d5-184">このコマンドが終了するまで Windows PowerShell が待機する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-184">Specifies how long Windows PowerShell waits for this command to finish.</span></span>

<span data-ttu-id="d07d5-185">既定値は 0 (ゼロ) で、タイムアウトがないため、Windows PowerShell は無期限に待機します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-185">The default value, 0 (zero), means that there is no time-out, and it causes Windows PowerShell to wait indefinitely.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: TimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d07d5-186">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d07d5-186">CommonParameters</span></span>

<span data-ttu-id="d07d5-187">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d07d5-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d07d5-188">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d07d5-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d07d5-189">入力</span><span class="sxs-lookup"><span data-stu-id="d07d5-189">INPUTS</span></span>

### <span data-ttu-id="d07d5-190">なし</span><span class="sxs-lookup"><span data-stu-id="d07d5-190">None</span></span>

<span data-ttu-id="d07d5-191">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="d07d5-191">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="d07d5-192">出力</span><span class="sxs-lookup"><span data-stu-id="d07d5-192">OUTPUTS</span></span>

### <span data-ttu-id="d07d5-193">なし</span><span class="sxs-lookup"><span data-stu-id="d07d5-193">None</span></span>

<span data-ttu-id="d07d5-194">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="d07d5-194">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d07d5-195">注</span><span class="sxs-lookup"><span data-stu-id="d07d5-195">NOTES</span></span>

<span data-ttu-id="d07d5-196">Windows Vista 以降のバージョンの Windows オペレーティングシステムでこのコマンドレットを使用するには、[管理者として実行] オプションを使用して Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-196">To use this cmdlet in Windows Vista or a later version of the Windows operating system, start Windows PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="d07d5-197">イベント、イベント サブスクリプション、およびイベント キューは、現在のセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="d07d5-197">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="d07d5-198">現在のセッションを閉じた場合、イベント キューが破棄され、イベント サブスクリプションが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="d07d5-198">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="d07d5-199">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d07d5-199">RELATED LINKS</span></span>
