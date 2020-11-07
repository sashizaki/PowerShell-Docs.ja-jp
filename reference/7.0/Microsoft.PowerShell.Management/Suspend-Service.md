---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/suspend-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Service
ms.openlocfilehash: 11c957157231a858c9e76b5a339872538b142270
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346185"
---
# <span data-ttu-id="05906-103">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="05906-103">Suspend-Service</span></span>

## <span data-ttu-id="05906-104">概要</span><span class="sxs-lookup"><span data-stu-id="05906-104">SYNOPSIS</span></span>
<span data-ttu-id="05906-105">実行中の 1 つ以上のサービスを中断 (一時停止) します。</span><span class="sxs-lookup"><span data-stu-id="05906-105">Suspends (pauses) one or more running services.</span></span>

## <span data-ttu-id="05906-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="05906-106">SYNTAX</span></span>

### <span data-ttu-id="05906-107">InputObject (既定値)</span><span class="sxs-lookup"><span data-stu-id="05906-107">InputObject (Default)</span></span>

```
Suspend-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="05906-108">Default</span><span class="sxs-lookup"><span data-stu-id="05906-108">Default</span></span>

```
Suspend-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="05906-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="05906-109">DisplayName</span></span>

```
Suspend-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="05906-110">Description</span><span class="sxs-lookup"><span data-stu-id="05906-110">DESCRIPTION</span></span>

<span data-ttu-id="05906-111">`Suspend-Service`コマンドレットは、指定された各サービスの Windows サービスコントローラーに中断メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="05906-111">The `Suspend-Service` cmdlet sends a suspend message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="05906-112">中断している間も、サービスは実行されていますが、コマンドレットを実行するなどして、再開されるまでそのアクションは停止し `Resume-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="05906-112">While suspended, the service is still running, but its action is stopped until resumed, such as by usingthe `Resume-Service` cmdlet.</span></span> <span data-ttu-id="05906-113">サービスは、サービス名または表示名で指定できます。また、 **InputObject** パラメーターを使用して、中断するサービスを表すサービスオブジェクトを渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="05906-113">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the services that you want to suspend.</span></span>

## <span data-ttu-id="05906-114">例</span><span class="sxs-lookup"><span data-stu-id="05906-114">EXAMPLES</span></span>

### <span data-ttu-id="05906-115">例 1: サービスを中断する</span><span class="sxs-lookup"><span data-stu-id="05906-115">Example 1: Suspend a service</span></span>

```
PS C:\> Suspend-Service -DisplayName "Telnet"
```

<span data-ttu-id="05906-116">このコマンドを実行すると、ローカル コンピューター上の Telnet サービス (Tlntsvr) が中断されます。</span><span class="sxs-lookup"><span data-stu-id="05906-116">This command suspends the Telnet service (Tlntsvr) service on the local computer.</span></span>

### <span data-ttu-id="05906-117">例 2: サービスを中断した場合の動作を表示する</span><span class="sxs-lookup"><span data-stu-id="05906-117">Example 2: Display what would happen if you suspend services</span></span>

```
PS C:\> Suspend-Service -Name lanman* -WhatIf
```

<span data-ttu-id="05906-118">このコマンドは、サービス名が lanman で始まるサービスを中断した場合に何が起こるかを示します。</span><span class="sxs-lookup"><span data-stu-id="05906-118">This command tells what would happen if you suspended the services that have a service name that starts with lanman.</span></span> <span data-ttu-id="05906-119">サービスを中断するには、 **WhatIf** パラメーターを指定せずにコマンドを再実行します。</span><span class="sxs-lookup"><span data-stu-id="05906-119">To suspend the services, rerun the command without the **WhatIf** parameter.</span></span>

### <span data-ttu-id="05906-120">例 3: サービスを取得して中断する</span><span class="sxs-lookup"><span data-stu-id="05906-120">Example 3: Get and suspend a service</span></span>

```
PS C:\> Get-Service schedule | Suspend-Service
```

<span data-ttu-id="05906-121">このコマンドは、 `Get-Service` コマンドレットを使用して、コンピューター上のタスクスケジューラ (スケジュール) サービスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="05906-121">This command uses the `Get-Service` cmdlet to get an object that represents the Task Scheduler (Schedule) service on the computer.</span></span> <span data-ttu-id="05906-122">パイプライン演算子 () は、 `|` 結果をに渡します `Suspend-Service` 。これにより、サービスが中断されます。</span><span class="sxs-lookup"><span data-stu-id="05906-122">The pipeline operator (`|`) passes the result to `Suspend-Service`, which suspends the service.</span></span>

### <span data-ttu-id="05906-123">例 4: 中断可能なすべてのサービスを中断する</span><span class="sxs-lookup"><span data-stu-id="05906-123">Example 4: Suspend all services that can be suspended</span></span>

```
PS C:\> Get-Service | Where-Object {$_.CanPauseAndContinue -eq "True"} | Suspend-Service -Confirm
```

<span data-ttu-id="05906-124">このコマンドを実行すると、コンピューター上の中断可能なすべてのサービスが中断されます。</span><span class="sxs-lookup"><span data-stu-id="05906-124">This command suspends all of the services on the computer that can be suspended.</span></span> <span data-ttu-id="05906-125">を使用して、 `Get-Service` コンピューター上のサービスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="05906-125">It uses `Get-Service` to get objects that represent the services on the computer.</span></span> <span data-ttu-id="05906-126">パイプライン演算子は、結果を `Where-Object` コマンドレットに渡します。このコマンドレットは、CanPauseAndContinue プロパティに値が設定されているサービスのみを選択し `$True` ます。 **CanPauseAndContinue**</span><span class="sxs-lookup"><span data-stu-id="05906-126">The pipeline operator passes the results to the `Where-Object` cmdlet, which selects only the services that have a value of `$True` for the **CanPauseAndContinue** property.</span></span> <span data-ttu-id="05906-127">もう1つのパイプライン演算子は、結果をに渡し `Suspend-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="05906-127">Another pipeline operator passes the results to `Suspend-Service`.</span></span> <span data-ttu-id="05906-128">**Confirm** パラメータは、各サービスを中断する前に確認メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="05906-128">The **Confirm** parameter prompts you for confirmation before suspending each of the services.</span></span>

## <span data-ttu-id="05906-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="05906-129">PARAMETERS</span></span>

### <span data-ttu-id="05906-130">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="05906-130">-DisplayName</span></span>

<span data-ttu-id="05906-131">中断するサービスの表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="05906-131">Specifies the display names of the services to be suspended.</span></span> <span data-ttu-id="05906-132">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="05906-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="05906-133">-除外</span><span class="sxs-lookup"><span data-stu-id="05906-133">-Exclude</span></span>

<span data-ttu-id="05906-134">指定されたサービスから除外するサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="05906-134">Specifies services to omit from the specified services.</span></span> <span data-ttu-id="05906-135">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="05906-135">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="05906-136">「s\*」などの名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="05906-136">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="05906-137">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="05906-137">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="05906-138">-Include</span><span class="sxs-lookup"><span data-stu-id="05906-138">-Include</span></span>

<span data-ttu-id="05906-139">中断するサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="05906-139">Specifies services to suspend.</span></span> <span data-ttu-id="05906-140">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="05906-140">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="05906-141">「s\*」などの名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="05906-141">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="05906-142">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="05906-142">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="05906-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="05906-143">-InputObject</span></span>

<span data-ttu-id="05906-144">中断するサービスを表す **ServiceController** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="05906-144">Specifies **ServiceController** objects that represent the services to suspend.</span></span> <span data-ttu-id="05906-145">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="05906-145">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="05906-146">-Name</span><span class="sxs-lookup"><span data-stu-id="05906-146">-Name</span></span>

<span data-ttu-id="05906-147">中断するサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="05906-147">Specifies the service names of the services to suspend.</span></span> <span data-ttu-id="05906-148">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="05906-148">Wildcard characters are permitted.</span></span>

<span data-ttu-id="05906-149">パラメーター名は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="05906-149">The parameter name is optional.</span></span> <span data-ttu-id="05906-150">**名前** またはそのエイリアスである **ServiceName** を使用することも、パラメーター名を省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="05906-150">You can use **Name** or its alias, **ServiceName** , or you can omit the parameter name.</span></span>

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

### <span data-ttu-id="05906-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="05906-151">-PassThru</span></span>

<span data-ttu-id="05906-152">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="05906-152">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="05906-153">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="05906-153">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="05906-154">-Confirm</span><span class="sxs-lookup"><span data-stu-id="05906-154">-Confirm</span></span>

<span data-ttu-id="05906-155">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="05906-155">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="05906-156">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="05906-156">-WhatIf</span></span>

<span data-ttu-id="05906-157">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="05906-157">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="05906-158">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="05906-158">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="05906-159">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="05906-159">CommonParameters</span></span>

<span data-ttu-id="05906-160">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="05906-160">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="05906-161">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05906-161">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="05906-162">入力</span><span class="sxs-lookup"><span data-stu-id="05906-162">INPUTS</span></span>

### <span data-ttu-id="05906-163">ServiceController (System.string)、System.string</span><span class="sxs-lookup"><span data-stu-id="05906-163">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="05906-164">このコマンドレットには、サービス名を含むサービスオブジェクトまたは文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="05906-164">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="05906-165">出力</span><span class="sxs-lookup"><span data-stu-id="05906-165">OUTPUTS</span></span>

### <span data-ttu-id="05906-166">None、ServiceController。</span><span class="sxs-lookup"><span data-stu-id="05906-166">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="05906-167">このコマンドレットは、 **PassThru** パラメーターを指定した場合に、サービスを表す **ServiceController** オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="05906-167">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="05906-168">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="05906-168">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="05906-169">注</span><span class="sxs-lookup"><span data-stu-id="05906-169">NOTES</span></span>

<span data-ttu-id="05906-170">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="05906-170">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="05906-171">`Suspend-Service` 現在のユーザーがこの操作を行うためのアクセス許可を持っている場合にのみ、サービスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="05906-171">`Suspend-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="05906-172">コマンドが正常に機能しない場合は、必要なアクセス許可が与えられていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="05906-172">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="05906-173">`Suspend-Service` 中断および再開がサポートされているサービスのみを中断できます。</span><span class="sxs-lookup"><span data-stu-id="05906-173">`Suspend-Service` can suspend only services that support being suspended and resumed.</span></span> <span data-ttu-id="05906-174">特定のサービスを中断できるかどうかを判断するには、 `Get-Service` **CanPauseAndContinue** プロパティと共にコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="05906-174">To determine whether a particular service can be suspended, use the `Get-Service` cmdlet together with the **CanPauseAndContinue** property.</span></span> <span data-ttu-id="05906-175">たとえば、「 `Get-Service wmi | Format-List Name, CanPauseAndContinue` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="05906-175">For example, `Get-Service wmi | Format-List Name, CanPauseAndContinue`.</span></span> <span data-ttu-id="05906-176">コンピューター上の中断可能なすべてのサービスを検索するには、「」と入力 `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}` します。</span><span class="sxs-lookup"><span data-stu-id="05906-176">To find all services on the computer that can be suspended, type `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}`.</span></span>
- <span data-ttu-id="05906-177">システム上のサービスのサービス名と表示名を確認するには、「」と入力 `Get-Service` します。</span><span class="sxs-lookup"><span data-stu-id="05906-177">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="05906-178">サービス名は [ **名前** ] 列に表示され、表示名は [ **DisplayName** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="05906-178">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="05906-179">関連リンク</span><span class="sxs-lookup"><span data-stu-id="05906-179">RELATED LINKS</span></span>

[<span data-ttu-id="05906-180">Get-Service</span><span class="sxs-lookup"><span data-stu-id="05906-180">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="05906-181">New-Service</span><span class="sxs-lookup"><span data-stu-id="05906-181">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="05906-182">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="05906-182">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="05906-183">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="05906-183">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="05906-184">Set-Service</span><span class="sxs-lookup"><span data-stu-id="05906-184">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="05906-185">Start-Service</span><span class="sxs-lookup"><span data-stu-id="05906-185">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="05906-186">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="05906-186">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="05906-187">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="05906-187">Remove-Service</span></span>](Remove-Service.md)
