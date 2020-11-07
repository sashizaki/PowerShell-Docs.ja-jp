---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/suspend-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Service
ms.openlocfilehash: a33cd0957fb37ce93334c08d21ef1b805188492f
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342503"
---
# <span data-ttu-id="40892-103">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="40892-103">Suspend-Service</span></span>

## <span data-ttu-id="40892-104">概要</span><span class="sxs-lookup"><span data-stu-id="40892-104">SYNOPSIS</span></span>
<span data-ttu-id="40892-105">実行中の 1 つ以上のサービスを中断 (一時停止) します。</span><span class="sxs-lookup"><span data-stu-id="40892-105">Suspends (pauses) one or more running services.</span></span>

## <span data-ttu-id="40892-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="40892-106">SYNTAX</span></span>

### <span data-ttu-id="40892-107">InputObject (既定値)</span><span class="sxs-lookup"><span data-stu-id="40892-107">InputObject (Default)</span></span>

```
Suspend-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="40892-108">Default</span><span class="sxs-lookup"><span data-stu-id="40892-108">Default</span></span>

```
Suspend-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="40892-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="40892-109">DisplayName</span></span>

```
Suspend-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="40892-110">Description</span><span class="sxs-lookup"><span data-stu-id="40892-110">DESCRIPTION</span></span>

<span data-ttu-id="40892-111">`Suspend-Service`コマンドレットは、指定された各サービスの Windows サービスコントローラーに中断メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="40892-111">The `Suspend-Service` cmdlet sends a suspend message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="40892-112">中断している間も、サービスは実行されていますが、コマンドレットを実行するなどして、再開されるまでそのアクションは停止し `Resume-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="40892-112">While suspended, the service is still running, but its action is stopped until resumed, such as by usingthe `Resume-Service` cmdlet.</span></span> <span data-ttu-id="40892-113">サービスは、サービス名または表示名で指定できます。また、 **InputObject** パラメーターを使用して、中断するサービスを表すサービスオブジェクトを渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="40892-113">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the services that you want to suspend.</span></span>

## <span data-ttu-id="40892-114">例</span><span class="sxs-lookup"><span data-stu-id="40892-114">EXAMPLES</span></span>

### <span data-ttu-id="40892-115">例 1: サービスを中断する</span><span class="sxs-lookup"><span data-stu-id="40892-115">Example 1: Suspend a service</span></span>

```
PS C:\> Suspend-Service -DisplayName "Telnet"
```

<span data-ttu-id="40892-116">このコマンドを実行すると、ローカル コンピューター上の Telnet サービス (Tlntsvr) が中断されます。</span><span class="sxs-lookup"><span data-stu-id="40892-116">This command suspends the Telnet service (Tlntsvr) service on the local computer.</span></span>

### <span data-ttu-id="40892-117">例 2: サービスを中断した場合の動作を表示する</span><span class="sxs-lookup"><span data-stu-id="40892-117">Example 2: Display what would happen if you suspend services</span></span>

```
PS C:\> Suspend-Service -Name lanman* -WhatIf
```

<span data-ttu-id="40892-118">このコマンドは、サービス名が lanman で始まるサービスを中断した場合に何が起こるかを示します。</span><span class="sxs-lookup"><span data-stu-id="40892-118">This command tells what would happen if you suspended the services that have a service name that starts with lanman.</span></span> <span data-ttu-id="40892-119">サービスを中断するには、 **WhatIf** パラメーターを指定せずにコマンドを再実行します。</span><span class="sxs-lookup"><span data-stu-id="40892-119">To suspend the services, rerun the command without the **WhatIf** parameter.</span></span>

### <span data-ttu-id="40892-120">例 3: サービスを取得して中断する</span><span class="sxs-lookup"><span data-stu-id="40892-120">Example 3: Get and suspend a service</span></span>

```
PS C:\> Get-Service schedule | Suspend-Service
```

<span data-ttu-id="40892-121">このコマンドは、 `Get-Service` コマンドレットを使用して、コンピューター上のタスクスケジューラ (スケジュール) サービスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="40892-121">This command uses the `Get-Service` cmdlet to get an object that represents the Task Scheduler (Schedule) service on the computer.</span></span> <span data-ttu-id="40892-122">パイプライン演算子 () は、 `|` 結果をに渡します `Suspend-Service` 。これにより、サービスが中断されます。</span><span class="sxs-lookup"><span data-stu-id="40892-122">The pipeline operator (`|`) passes the result to `Suspend-Service`, which suspends the service.</span></span>

### <span data-ttu-id="40892-123">例 4: 中断可能なすべてのサービスを中断する</span><span class="sxs-lookup"><span data-stu-id="40892-123">Example 4: Suspend all services that can be suspended</span></span>

```
PS C:\> Get-Service | Where-Object {$_.CanPauseAndContinue -eq "True"} | Suspend-Service -Confirm
```

<span data-ttu-id="40892-124">このコマンドを実行すると、コンピューター上の中断可能なすべてのサービスが中断されます。</span><span class="sxs-lookup"><span data-stu-id="40892-124">This command suspends all of the services on the computer that can be suspended.</span></span> <span data-ttu-id="40892-125">を使用して、 `Get-Service` コンピューター上のサービスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="40892-125">It uses `Get-Service` to get objects that represent the services on the computer.</span></span> <span data-ttu-id="40892-126">パイプライン演算子は、結果を `Where-Object` コマンドレットに渡します。このコマンドレットは、CanPauseAndContinue プロパティに値が設定されているサービスのみを選択し `$True` ます。 **CanPauseAndContinue**</span><span class="sxs-lookup"><span data-stu-id="40892-126">The pipeline operator passes the results to the `Where-Object` cmdlet, which selects only the services that have a value of `$True` for the **CanPauseAndContinue** property.</span></span> <span data-ttu-id="40892-127">もう1つのパイプライン演算子は、結果をに渡し `Suspend-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="40892-127">Another pipeline operator passes the results to `Suspend-Service`.</span></span> <span data-ttu-id="40892-128">**Confirm** パラメータは、各サービスを中断する前に確認メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="40892-128">The **Confirm** parameter prompts you for confirmation before suspending each of the services.</span></span>

## <span data-ttu-id="40892-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="40892-129">PARAMETERS</span></span>

### <span data-ttu-id="40892-130">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="40892-130">-DisplayName</span></span>

<span data-ttu-id="40892-131">中断するサービスの表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="40892-131">Specifies the display names of the services to be suspended.</span></span> <span data-ttu-id="40892-132">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="40892-132">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="40892-133">-除外</span><span class="sxs-lookup"><span data-stu-id="40892-133">-Exclude</span></span>

<span data-ttu-id="40892-134">指定されたサービスから除外するサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="40892-134">Specifies services to omit from the specified services.</span></span> <span data-ttu-id="40892-135">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="40892-135">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="40892-136">「s\*」などの名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="40892-136">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="40892-137">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="40892-137">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="40892-138">-Include</span><span class="sxs-lookup"><span data-stu-id="40892-138">-Include</span></span>

<span data-ttu-id="40892-139">中断するサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="40892-139">Specifies services to suspend.</span></span> <span data-ttu-id="40892-140">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="40892-140">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="40892-141">「s\*」などの名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="40892-141">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="40892-142">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="40892-142">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="40892-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="40892-143">-InputObject</span></span>

<span data-ttu-id="40892-144">中断するサービスを表す **ServiceController** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="40892-144">Specifies **ServiceController** objects that represent the services to suspend.</span></span> <span data-ttu-id="40892-145">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="40892-145">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="40892-146">-Name</span><span class="sxs-lookup"><span data-stu-id="40892-146">-Name</span></span>

<span data-ttu-id="40892-147">中断するサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="40892-147">Specifies the service names of the services to suspend.</span></span> <span data-ttu-id="40892-148">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="40892-148">Wildcard characters are permitted.</span></span>

<span data-ttu-id="40892-149">パラメーター名は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="40892-149">The parameter name is optional.</span></span> <span data-ttu-id="40892-150">**名前** またはそのエイリアスである **ServiceName** を使用することも、パラメーター名を省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="40892-150">You can use **Name** or its alias, **ServiceName** , or you can omit the parameter name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="40892-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="40892-151">-PassThru</span></span>

<span data-ttu-id="40892-152">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="40892-152">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="40892-153">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="40892-153">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="40892-154">-Confirm</span><span class="sxs-lookup"><span data-stu-id="40892-154">-Confirm</span></span>

<span data-ttu-id="40892-155">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="40892-155">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40892-156">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="40892-156">-WhatIf</span></span>

<span data-ttu-id="40892-157">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="40892-157">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="40892-158">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="40892-158">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40892-159">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="40892-159">CommonParameters</span></span>

<span data-ttu-id="40892-160">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="40892-160">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="40892-161">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40892-161">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="40892-162">入力</span><span class="sxs-lookup"><span data-stu-id="40892-162">INPUTS</span></span>

### <span data-ttu-id="40892-163">ServiceController (System.string)、System.string</span><span class="sxs-lookup"><span data-stu-id="40892-163">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="40892-164">このコマンドレットには、サービス名を含むサービスオブジェクトまたは文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="40892-164">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="40892-165">出力</span><span class="sxs-lookup"><span data-stu-id="40892-165">OUTPUTS</span></span>

### <span data-ttu-id="40892-166">None、ServiceController。</span><span class="sxs-lookup"><span data-stu-id="40892-166">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="40892-167">このコマンドレットは、 **PassThru** パラメーターを指定した場合に、サービスを表す **ServiceController** オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="40892-167">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="40892-168">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="40892-168">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="40892-169">注</span><span class="sxs-lookup"><span data-stu-id="40892-169">NOTES</span></span>

- <span data-ttu-id="40892-170">`Suspend-Service` 現在のユーザーがこの操作を行うためのアクセス許可を持っている場合にのみ、サービスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="40892-170">`Suspend-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="40892-171">コマンドが正常に機能しない場合は、必要なアクセス許可が与えられていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40892-171">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="40892-172">`Suspend-Service` 中断および再開がサポートされているサービスのみを中断できます。</span><span class="sxs-lookup"><span data-stu-id="40892-172">`Suspend-Service` can suspend only services that support being suspended and resumed.</span></span> <span data-ttu-id="40892-173">特定のサービスを中断できるかどうかを判断するには、 `Get-Service` **CanPauseAndContinue** プロパティと共にコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="40892-173">To determine whether a particular service can be suspended, use the `Get-Service` cmdlet together with the **CanPauseAndContinue** property.</span></span> <span data-ttu-id="40892-174">たとえば、「 `Get-Service wmi | Format-List Name, CanPauseAndContinue` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="40892-174">For example, `Get-Service wmi | Format-List Name, CanPauseAndContinue`.</span></span> <span data-ttu-id="40892-175">コンピューター上の中断可能なすべてのサービスを検索するには、「」と入力 `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}` します。</span><span class="sxs-lookup"><span data-stu-id="40892-175">To find all services on the computer that can be suspended, type `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}`.</span></span>
- <span data-ttu-id="40892-176">システム上のサービスのサービス名と表示名を確認するには、「」と入力 `Get-Service` します。</span><span class="sxs-lookup"><span data-stu-id="40892-176">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="40892-177">サービス名は [ **名前** ] 列に表示され、表示名は [ **DisplayName** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="40892-177">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="40892-178">関連リンク</span><span class="sxs-lookup"><span data-stu-id="40892-178">RELATED LINKS</span></span>

[<span data-ttu-id="40892-179">Get-Service</span><span class="sxs-lookup"><span data-stu-id="40892-179">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="40892-180">New-Service</span><span class="sxs-lookup"><span data-stu-id="40892-180">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="40892-181">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="40892-181">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="40892-182">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="40892-182">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="40892-183">Set-Service</span><span class="sxs-lookup"><span data-stu-id="40892-183">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="40892-184">Start-Service</span><span class="sxs-lookup"><span data-stu-id="40892-184">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="40892-185">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="40892-185">Stop-Service</span></span>](Stop-Service.md)
