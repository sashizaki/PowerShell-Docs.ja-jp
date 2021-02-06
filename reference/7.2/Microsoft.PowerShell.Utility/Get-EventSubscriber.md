---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-eventsubscriber?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventSubscriber
ms.openlocfilehash: b8f55770770fa9077f654d382818386cc480c638
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599532"
---
# <span data-ttu-id="6e427-102">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="6e427-102">Get-EventSubscriber</span></span>

## <span data-ttu-id="6e427-103">概要</span><span class="sxs-lookup"><span data-stu-id="6e427-103">SYNOPSIS</span></span>
<span data-ttu-id="6e427-104">現在のセッションのイベント サブスクライバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="6e427-104">Gets the event subscribers in the current session.</span></span>

## <span data-ttu-id="6e427-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6e427-105">SYNTAX</span></span>

### <span data-ttu-id="6e427-106">BySource (既定値)</span><span class="sxs-lookup"><span data-stu-id="6e427-106">BySource (Default)</span></span>

```
Get-EventSubscriber [[-SourceIdentifier] <String>] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="6e427-107">ById</span><span class="sxs-lookup"><span data-stu-id="6e427-107">ById</span></span>

```
Get-EventSubscriber [-SubscriptionId] <Int32> [-Force] [<CommonParameters>]
```

## <span data-ttu-id="6e427-108">Description</span><span class="sxs-lookup"><span data-stu-id="6e427-108">DESCRIPTION</span></span>

<span data-ttu-id="6e427-109">**Get EventSubscriber** コマンドレットは、現在のセッションのイベントサブスクライバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="6e427-109">The **Get-EventSubscriber** cmdlet gets the event subscribers in the current session.</span></span>

<span data-ttu-id="6e427-110">Register event コマンドレットを使用してイベントをサブスクライブすると、イベントサブスクライバーが PowerShell セッションに追加され、サブスクライブしたイベントが発生するたびにイベントキューに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6e427-110">When you subscribe to an event by using a Register event cmdlet, an event subscriber is added to your PowerShell session, and the events to which you subscribed are added to your event queue whenever they are raised.</span></span>
<span data-ttu-id="6e427-111">イベント サブスクリプションを取り消すには、Unregister-Event コマンドレットを使用してイベント サブスクライバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6e427-111">To cancel an event subscription, delete the event subscriber by using the Unregister-Event cmdlet.</span></span>

## <span data-ttu-id="6e427-112">例</span><span class="sxs-lookup"><span data-stu-id="6e427-112">EXAMPLES</span></span>

### <span data-ttu-id="6e427-113">例 1: タイマーイベントのイベントサブスクライバーを取得する</span><span class="sxs-lookup"><span data-stu-id="6e427-113">Example 1: Get the event subscriber for a timer event</span></span>

```
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer | Get-Member -Type Event
PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Elapsed
PS C:\> Get-EventSubscriber
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer | Get-Member -Type Event
TypeName: System.Timers.Timer
Name     MemberType Definition
----     ---------- ----------
Disposed Event      System.EventHandler Disposed(System.Object, System.EventArgs)
Elapsed  Event      System.Timers.ElapsedEventHandler Elapsed(System.Object, System.Timers.ElapsedEventArgs) PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Elapsed
PS C:\> Get-EventSubscriber
SubscriptionId   : 4
SourceObject     : System.Timers.Timer
EventName        : Elapsed
SourceIdentifier : Timer.Elapsed
Action           :
HandlerDelegate  :
SupportEvent     : False
ForwardEvent     : False
```

<span data-ttu-id="6e427-114">この例では、 **Get eventsubscriber** コマンドを使用して、timer イベントのイベントサブスクライバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="6e427-114">This example uses a **Get-EventSubscriber** command to get the event subscriber for a timer event.</span></span>

<span data-ttu-id="6e427-115">最初のコマンドは、New-Object コマンドレットを使用して、タイマー オブジェクトのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e427-115">The first command uses the New-Object cmdlet to create an instance of a timer object.</span></span>
<span data-ttu-id="6e427-116">新しいタイマーオブジェクトを $Timer 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="6e427-116">It saves the new timer object in the $Timer variable.</span></span>

<span data-ttu-id="6e427-117">2 番目のコマンドは、Get-Member コマンドレットを使用して、タイマー オブジェクトに使用できるイベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="6e427-117">The second command uses the Get-Member cmdlet to display the events that are available for timer objects.</span></span>
<span data-ttu-id="6e427-118">このコマンドでは、 **Get Member** コマンドレットの Type パラメーターを使用して、イベントの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e427-118">The command uses the Type parameter of the **Get-Member** cmdlet with a value of Event.</span></span>

<span data-ttu-id="6e427-119">3 番目のコマンドは、Register-ObjectEvent コマンドレットを使用して、タイマー オブジェクトの Elapsed イベントを登録します。</span><span class="sxs-lookup"><span data-stu-id="6e427-119">The third command uses the Register-ObjectEvent cmdlet to register for the Elapsed event on the timer object.</span></span>

<span data-ttu-id="6e427-120">4番目のコマンドは、 **Get EventSubscriber** コマンドレットを使用して、Elapsed イベントのイベントサブスクライバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="6e427-120">The fourth command uses the **Get-EventSubscriber** cmdlet to get the event subscriber for the Elapsed event.</span></span>

### <span data-ttu-id="6e427-121">例 2: イベントサブスクライバーの Action プロパティで PSEventJob の動的モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="6e427-121">Example 2: Use the dynamic module in PSEventJob in the Action property of the event subscriber</span></span>

```
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer.Interval = 500
PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Random -Action { $Random = Get-Random -Min 0 -Max 100 }

Id  Name           State      HasMoreData  Location  Command
--  ----           -----      -----------  --------  -------
3   Timer.Random   NotStarted False                  $Random = Get-Random ...

PS C:\> $Timer.Enabled = $True
PS C:\> $Subscriber = Get-EventSubscriber -SourceIdentifier Timer.Random
PS C:\> ($Subscriber.action).gettype().fullname
System.Management.Automation.PSEventJob
PS C:\> $Subscriber.action | Format-List -Property *

State         : Running
Module        : __DynamicModule_6b5cbe82-d634-41d1-ae5e-ad7fe8d57fe0
StatusMessage :
HasMoreData   : True
Location      :
Command       : $random = Get-Random -Min 0 -Max 100
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : 88944290-133d-4b44-8752-f901bd8012e2
Id            : 1
Name          : Timer.Random
ChildJobs     : {}
...

PS C:\> & $Subscriber.action.module {$Random}
96
PS C:\> & $Subscriber.action.module {$Random}
23
```

<span data-ttu-id="6e427-122">この例では、イベントサブスクライバーの Action プロパティで **PSEventJob** オブジェクトの動的モジュールを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6e427-122">This example shows how to use the dynamic module in the **PSEventJob** object in the Action property of the event subscriber.</span></span>

<span data-ttu-id="6e427-123">最初のコマンドは、New-Object コマンドレットを使用してタイマー オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e427-123">The first command uses the New-Object cmdlet to create a timer object.</span></span>
<span data-ttu-id="6e427-124">2 番目のコマンドは、タイマーの間隔を 500 (ミリ秒) に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e427-124">The second command sets the interval of the timer to 500 (milliseconds).</span></span>

<span data-ttu-id="6e427-125">3 番目のコマンドは、Register-ObjectEvent コマンドレットを使用して、タイマー オブジェクトの Elapsed イベントを登録します。</span><span class="sxs-lookup"><span data-stu-id="6e427-125">The third command uses the Register-ObjectEvent cmdlet to register the Elapsed event of the timer object.</span></span>
<span data-ttu-id="6e427-126">このコマンドには、イベントを処理するアクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e427-126">The command includes an action that handles the event.</span></span>
<span data-ttu-id="6e427-127">タイマーの間隔が経過するたびに、イベントが発生してアクション内のコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="6e427-127">Whenever the timer interval elapses, an event is raised and the commands in the action run.</span></span>
<span data-ttu-id="6e427-128">この場合、Get-Random コマンドレットは 0 ~ 100 の範囲の乱数を生成し、$Random 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="6e427-128">In this case, the Get-Random cmdlet generates a random number between 0 and 100 and saves it in the $Random variable.</span></span>
<span data-ttu-id="6e427-129">イベントのソース識別子は Timer.Random です。</span><span class="sxs-lookup"><span data-stu-id="6e427-129">The source identifier of the event is Timer.Random.</span></span>

<span data-ttu-id="6e427-130">**ObjectEvent** コマンドで *action* パラメーターを使用すると、コマンドは、アクションを表す **PSEventJob** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="6e427-130">When you use an *Action* parameter in a **Register-ObjectEvent** command, the command returns a **PSEventJob** object that represents the action.</span></span>

<span data-ttu-id="6e427-131">4 番目のコマンドは、タイマーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6e427-131">The fourth command enables the timer.</span></span>

<span data-ttu-id="6e427-132">5番目のコマンドは、 **Get EventSubscriber** コマンドレットを使用して、タイマーのイベントサブスクライバーを取得します。 Random イベント。</span><span class="sxs-lookup"><span data-stu-id="6e427-132">The fifth command uses the **Get-EventSubscriber** cmdlet to get the event subscriber of the Timer.Random event.</span></span>
<span data-ttu-id="6e427-133">イベントサブスクライバーオブジェクトを $Subscriber 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="6e427-133">It saves the event subscriber object in the $Subscriber variable.</span></span>

<span data-ttu-id="6e427-134">6番目のコマンドは、イベントサブスクライバーオブジェクトの Action プロパティに **PSEventJob** オブジェクトが含まれていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="6e427-134">The sixth command shows that the Action property of the event subscriber object contains a **PSEventJob** object.</span></span>
<span data-ttu-id="6e427-135">実際には、このオブジェクトには、 **PSEventJob** コマンド **によって** 返されたものと同じオブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e427-135">In fact, it contains the same **PSEventJob** object that the **Register-ObjectEvent** command returned.</span></span>

<span data-ttu-id="6e427-136">7番目のコマンドは、Format-List コマンドレットを使用して、リストの Action プロパティに **PSEventJob** オブジェクトのすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="6e427-136">The seventh command uses the Format-List cmdlet to display all of the properties of the **PSEventJob** object in the Action property in a list.</span></span>
<span data-ttu-id="6e427-137">結果によって、 **PSEventJob** オブジェクトには、アクションを実装する動的スクリプトモジュールを含む Module プロパティがあることがわかります。</span><span class="sxs-lookup"><span data-stu-id="6e427-137">The result reveals that the **PSEventJob** object has a Module property that contains a dynamic script module that implements the action.</span></span>

<span data-ttu-id="6e427-138">残りのコマンドでは、呼び出し演算子 (&) を使用してモジュール内のコマンドを呼び出し、$Random 変数の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="6e427-138">The remaining commands use the call operator (&) to invoke the command in the module and display the value of the $Random variable.</span></span>
<span data-ttu-id="6e427-139">呼び出し演算子を使用すると、エクスポートされないコマンドを含め、モジュール内の任意のコマンドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="6e427-139">You can use the call operator to invoke any command in a module, including commands that are not exported.</span></span>
<span data-ttu-id="6e427-140">この例では、これらのコマンドにより Elapsed イベントが発生したときに生成される乱数が示されます。</span><span class="sxs-lookup"><span data-stu-id="6e427-140">In this case, the commands show the random number that is being generated when the Elapsed event occurs.</span></span>

<span data-ttu-id="6e427-141">モジュールの詳細については、「 [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e427-141">For more information about modules, see [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

## <span data-ttu-id="6e427-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6e427-142">PARAMETERS</span></span>

### <span data-ttu-id="6e427-143">-Force</span><span class="sxs-lookup"><span data-stu-id="6e427-143">-Force</span></span>

<span data-ttu-id="6e427-144">このコマンドレットによって、すべてのイベントサブスクライバーが取得されることを示します。これには、Register-engineevent の *supportevent* パラメーターを使用して非表示になっているイベントのサブスクライバーも含まれます。</span><span class="sxs-lookup"><span data-stu-id="6e427-144">Indicates that this cmdlet gets all event subscribers, including subscribers for events that are hidden by using the *SupportEvent* parameter of Register-ObjectEvent, Register-WmiEvent, and Register-EngineEvent.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6e427-145">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="6e427-145">-SourceIdentifier</span></span>

<span data-ttu-id="6e427-146">イベントサブスクライバーのみを取得する **SourceIdentifier** プロパティ値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e427-146">Specifies the **SourceIdentifier** property value that gets only the event subscribers.</span></span>
<span data-ttu-id="6e427-147">既定では、 **Get EventSubscriber** はセッション内のすべてのイベントサブスクライバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="6e427-147">By default, **Get-EventSubscriber** gets all event subscribers in the session.</span></span>
<span data-ttu-id="6e427-148">ワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="6e427-148">Wildcards are not permitted.</span></span>
<span data-ttu-id="6e427-149">このパラメーターでは、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="6e427-149">This parameter is case-sensitive.</span></span>

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6e427-150">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="6e427-150">-SubscriptionId</span></span>

<span data-ttu-id="6e427-151">このコマンドレットが取得するサブスクリプション識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e427-151">Specifies the subscription identifier that this cmdlet gets.</span></span>
<span data-ttu-id="6e427-152">既定では、 **Get EventSubscriber** はセッション内のすべてのイベントサブスクライバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="6e427-152">By default, **Get-EventSubscriber** gets all event subscribers in the session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6e427-153">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6e427-153">CommonParameters</span></span>

<span data-ttu-id="6e427-154">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6e427-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6e427-155">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e427-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6e427-156">入力</span><span class="sxs-lookup"><span data-stu-id="6e427-156">INPUTS</span></span>

### <span data-ttu-id="6e427-157">なし</span><span class="sxs-lookup"><span data-stu-id="6e427-157">None</span></span>

<span data-ttu-id="6e427-158">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="6e427-158">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="6e427-159">出力</span><span class="sxs-lookup"><span data-stu-id="6e427-159">OUTPUTS</span></span>

### <span data-ttu-id="6e427-160">PSEventSubscriber (システム管理)</span><span class="sxs-lookup"><span data-stu-id="6e427-160">System.Management.Automation.PSEventSubscriber</span></span>

<span data-ttu-id="6e427-161">**Get-EventSubscriber** は、各イベントサブスクライバーを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="6e427-161">**Get-EventSubscriber** returns an object that represents each event subscriber.</span></span>

## <span data-ttu-id="6e427-162">注</span><span class="sxs-lookup"><span data-stu-id="6e427-162">NOTES</span></span>

* <span data-ttu-id="6e427-163">カスタム イベントを作成する New-Event コマンドレットは、サブスクライバーを生成しません。</span><span class="sxs-lookup"><span data-stu-id="6e427-163">The New-Event cmdlet, which creates a custom event, does not generate a subscriber.</span></span> <span data-ttu-id="6e427-164">このため、 **Get eventsubscriber** コマンドレットでは、これらのイベントのサブスクライバーオブジェクトは検出されません。</span><span class="sxs-lookup"><span data-stu-id="6e427-164">Therefore, the **Get-EventSubscriber** cmdlet will not find a subscriber object for these events.</span></span> <span data-ttu-id="6e427-165">ただし、Register-EngineEvent コマンドレットを使用してカスタムイベントをサブスクライブすると (イベントを転送したりアクションを指定したりするために)、 **register-engineevent** が生成するサブスクライバーが **Get eventsubscriber** によって検出されます。</span><span class="sxs-lookup"><span data-stu-id="6e427-165">However, if you use the Register-EngineEvent cmdlet to subscribe to a custom event (in order to forward the event or to specify an action), **Get-EventSubscriber** will find the subscriber that **Register-EngineEvent** generates.</span></span>

  <span data-ttu-id="6e427-166">イベント、イベント サブスクリプション、およびイベント キューは、現在のセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="6e427-166">Events, event subscriptions, and the event queue exist only in the current session.</span></span>
<span data-ttu-id="6e427-167">現在のセッションを閉じた場合、イベント キューが破棄され、イベント サブスクリプションが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="6e427-167">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

*

## <span data-ttu-id="6e427-168">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6e427-168">RELATED LINKS</span></span>

[<span data-ttu-id="6e427-169">Get-Event</span><span class="sxs-lookup"><span data-stu-id="6e427-169">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="6e427-170">New-Event</span><span class="sxs-lookup"><span data-stu-id="6e427-170">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="6e427-171">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="6e427-171">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="6e427-172">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="6e427-172">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="6e427-173">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="6e427-173">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="6e427-174">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="6e427-174">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="6e427-175">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="6e427-175">Wait-Event</span></span>](Wait-Event.md)

