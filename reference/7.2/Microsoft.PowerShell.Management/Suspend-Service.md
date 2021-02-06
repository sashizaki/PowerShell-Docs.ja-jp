---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/suspend-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Service
ms.openlocfilehash: 9515f524df38813817b3fefd1437a3e2df296392
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600112"
---
# <span data-ttu-id="e63b9-102">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="e63b9-102">Suspend-Service</span></span>

## <span data-ttu-id="e63b9-103">概要</span><span class="sxs-lookup"><span data-stu-id="e63b9-103">SYNOPSIS</span></span>
<span data-ttu-id="e63b9-104">実行中の 1 つ以上のサービスを中断 (一時停止) します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-104">Suspends (pauses) one or more running services.</span></span>

## <span data-ttu-id="e63b9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e63b9-105">SYNTAX</span></span>

### <span data-ttu-id="e63b9-106">InputObject (既定値)</span><span class="sxs-lookup"><span data-stu-id="e63b9-106">InputObject (Default)</span></span>

```
Suspend-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e63b9-107">Default</span><span class="sxs-lookup"><span data-stu-id="e63b9-107">Default</span></span>

```
Suspend-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="e63b9-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e63b9-108">DisplayName</span></span>

```
Suspend-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e63b9-109">Description</span><span class="sxs-lookup"><span data-stu-id="e63b9-109">DESCRIPTION</span></span>

<span data-ttu-id="e63b9-110">`Suspend-Service`コマンドレットは、指定された各サービスの Windows サービスコントローラーに中断メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-110">The `Suspend-Service` cmdlet sends a suspend message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="e63b9-111">中断している間も、サービスは実行されていますが、コマンドレットを実行するなどして、再開されるまでそのアクションは停止し `Resume-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-111">While suspended, the service is still running, but its action is stopped until resumed, such as by usingthe `Resume-Service` cmdlet.</span></span> <span data-ttu-id="e63b9-112">サービスは、サービス名または表示名で指定できます。また、 **InputObject** パラメーターを使用して、中断するサービスを表すサービスオブジェクトを渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-112">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the services that you want to suspend.</span></span>

## <span data-ttu-id="e63b9-113">例</span><span class="sxs-lookup"><span data-stu-id="e63b9-113">EXAMPLES</span></span>

### <span data-ttu-id="e63b9-114">例 1: サービスを中断する</span><span class="sxs-lookup"><span data-stu-id="e63b9-114">Example 1: Suspend a service</span></span>

```
PS C:\> Suspend-Service -DisplayName "Telnet"
```

<span data-ttu-id="e63b9-115">このコマンドを実行すると、ローカル コンピューター上の Telnet サービス (Tlntsvr) が中断されます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-115">This command suspends the Telnet service (Tlntsvr) service on the local computer.</span></span>

### <span data-ttu-id="e63b9-116">例 2: サービスを中断した場合の動作を表示する</span><span class="sxs-lookup"><span data-stu-id="e63b9-116">Example 2: Display what would happen if you suspend services</span></span>

```
PS C:\> Suspend-Service -Name lanman* -WhatIf
```

<span data-ttu-id="e63b9-117">このコマンドは、サービス名が lanman で始まるサービスを中断した場合に何が起こるかを示します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-117">This command tells what would happen if you suspended the services that have a service name that starts with lanman.</span></span> <span data-ttu-id="e63b9-118">サービスを中断するには、 **WhatIf** パラメーターを指定せずにコマンドを再実行します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-118">To suspend the services, rerun the command without the **WhatIf** parameter.</span></span>

### <span data-ttu-id="e63b9-119">例 3: サービスを取得して中断する</span><span class="sxs-lookup"><span data-stu-id="e63b9-119">Example 3: Get and suspend a service</span></span>

```
PS C:\> Get-Service schedule | Suspend-Service
```

<span data-ttu-id="e63b9-120">このコマンドは、 `Get-Service` コマンドレットを使用して、コンピューター上のタスクスケジューラ (スケジュール) サービスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-120">This command uses the `Get-Service` cmdlet to get an object that represents the Task Scheduler (Schedule) service on the computer.</span></span> <span data-ttu-id="e63b9-121">パイプライン演算子 () は、 `|` 結果をに渡します `Suspend-Service` 。これにより、サービスが中断されます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-121">The pipeline operator (`|`) passes the result to `Suspend-Service`, which suspends the service.</span></span>

### <span data-ttu-id="e63b9-122">例 4: 中断可能なすべてのサービスを中断する</span><span class="sxs-lookup"><span data-stu-id="e63b9-122">Example 4: Suspend all services that can be suspended</span></span>

```
PS C:\> Get-Service | Where-Object {$_.CanPauseAndContinue -eq "True"} | Suspend-Service -Confirm
```

<span data-ttu-id="e63b9-123">このコマンドを実行すると、コンピューター上の中断可能なすべてのサービスが中断されます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-123">This command suspends all of the services on the computer that can be suspended.</span></span> <span data-ttu-id="e63b9-124">を使用して、 `Get-Service` コンピューター上のサービスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-124">It uses `Get-Service` to get objects that represent the services on the computer.</span></span> <span data-ttu-id="e63b9-125">パイプライン演算子は、結果を `Where-Object` コマンドレットに渡します。このコマンドレットは、CanPauseAndContinue プロパティに値が設定されているサービスのみを選択し `$True` ます。 </span><span class="sxs-lookup"><span data-stu-id="e63b9-125">The pipeline operator passes the results to the `Where-Object` cmdlet, which selects only the services that have a value of `$True` for the **CanPauseAndContinue** property.</span></span> <span data-ttu-id="e63b9-126">もう1つのパイプライン演算子は、結果をに渡し `Suspend-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-126">Another pipeline operator passes the results to `Suspend-Service`.</span></span> <span data-ttu-id="e63b9-127">**Confirm** パラメータは、各サービスを中断する前に確認メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-127">The **Confirm** parameter prompts you for confirmation before suspending each of the services.</span></span>

## <span data-ttu-id="e63b9-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e63b9-128">PARAMETERS</span></span>

### <span data-ttu-id="e63b9-129">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="e63b9-129">-DisplayName</span></span>

<span data-ttu-id="e63b9-130">中断するサービスの表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-130">Specifies the display names of the services to be suspended.</span></span> <span data-ttu-id="e63b9-131">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-131">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="e63b9-132">-除外</span><span class="sxs-lookup"><span data-stu-id="e63b9-132">-Exclude</span></span>

<span data-ttu-id="e63b9-133">指定されたサービスから除外するサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-133">Specifies services to omit from the specified services.</span></span> <span data-ttu-id="e63b9-134">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-134">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="e63b9-135">「s\*」などの名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-135">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="e63b9-136">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-136">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="e63b9-137">-Include</span><span class="sxs-lookup"><span data-stu-id="e63b9-137">-Include</span></span>

<span data-ttu-id="e63b9-138">中断するサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-138">Specifies services to suspend.</span></span> <span data-ttu-id="e63b9-139">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-139">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="e63b9-140">「s\*」などの名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-140">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="e63b9-141">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-141">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="e63b9-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e63b9-142">-InputObject</span></span>

<span data-ttu-id="e63b9-143">中断するサービスを表す **ServiceController** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-143">Specifies **ServiceController** objects that represent the services to suspend.</span></span> <span data-ttu-id="e63b9-144">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-144">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="e63b9-145">-Name</span><span class="sxs-lookup"><span data-stu-id="e63b9-145">-Name</span></span>

<span data-ttu-id="e63b9-146">中断するサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-146">Specifies the service names of the services to suspend.</span></span> <span data-ttu-id="e63b9-147">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-147">Wildcard characters are permitted.</span></span>

<span data-ttu-id="e63b9-148">パラメーター名は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e63b9-148">The parameter name is optional.</span></span> <span data-ttu-id="e63b9-149">**名前** またはそのエイリアスである **ServiceName** を使用することも、パラメーター名を省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-149">You can use **Name** or its alias, **ServiceName**, or you can omit the parameter name.</span></span>

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

### <span data-ttu-id="e63b9-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e63b9-150">-PassThru</span></span>

<span data-ttu-id="e63b9-151">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-151">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="e63b9-152">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="e63b9-152">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="e63b9-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e63b9-153">-Confirm</span></span>

<span data-ttu-id="e63b9-154">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e63b9-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e63b9-155">-WhatIf</span></span>

<span data-ttu-id="e63b9-156">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e63b9-157">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e63b9-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e63b9-158">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e63b9-158">CommonParameters</span></span>

<span data-ttu-id="e63b9-159">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e63b9-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e63b9-160">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e63b9-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e63b9-161">入力</span><span class="sxs-lookup"><span data-stu-id="e63b9-161">INPUTS</span></span>

### <span data-ttu-id="e63b9-162">ServiceController (System.string)、System.string</span><span class="sxs-lookup"><span data-stu-id="e63b9-162">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="e63b9-163">このコマンドレットには、サービス名を含むサービスオブジェクトまたは文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-163">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="e63b9-164">出力</span><span class="sxs-lookup"><span data-stu-id="e63b9-164">OUTPUTS</span></span>

### <span data-ttu-id="e63b9-165">None、ServiceController。</span><span class="sxs-lookup"><span data-stu-id="e63b9-165">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="e63b9-166">このコマンドレットは、 **PassThru** パラメーターを指定した場合に、サービスを表す **ServiceController** オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-166">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="e63b9-167">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="e63b9-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e63b9-168">注</span><span class="sxs-lookup"><span data-stu-id="e63b9-168">NOTES</span></span>

<span data-ttu-id="e63b9-169">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-169">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="e63b9-170">`Suspend-Service` 現在のユーザーがこの操作を行うためのアクセス許可を持っている場合にのみ、サービスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-170">`Suspend-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="e63b9-171">コマンドが正常に機能しない場合は、必要なアクセス許可が与えられていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e63b9-171">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="e63b9-172">`Suspend-Service` 中断および再開がサポートされているサービスのみを中断できます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-172">`Suspend-Service` can suspend only services that support being suspended and resumed.</span></span> <span data-ttu-id="e63b9-173">特定のサービスを中断できるかどうかを判断するには、 `Get-Service` **CanPauseAndContinue** プロパティと共にコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-173">To determine whether a particular service can be suspended, use the `Get-Service` cmdlet together with the **CanPauseAndContinue** property.</span></span> <span data-ttu-id="e63b9-174">たとえば、「 `Get-Service wmi | Format-List Name, CanPauseAndContinue` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-174">For example, `Get-Service wmi | Format-List Name, CanPauseAndContinue`.</span></span> <span data-ttu-id="e63b9-175">コンピューター上の中断可能なすべてのサービスを検索するには、「」と入力 `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}` します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-175">To find all services on the computer that can be suspended, type `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}`.</span></span>
- <span data-ttu-id="e63b9-176">システム上のサービスのサービス名と表示名を確認するには、「」と入力 `Get-Service` します。</span><span class="sxs-lookup"><span data-stu-id="e63b9-176">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="e63b9-177">サービス名は [ **名前** ] 列に表示され、表示名は [ **DisplayName** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e63b9-177">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="e63b9-178">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e63b9-178">RELATED LINKS</span></span>

[<span data-ttu-id="e63b9-179">Get-Service</span><span class="sxs-lookup"><span data-stu-id="e63b9-179">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="e63b9-180">New-Service</span><span class="sxs-lookup"><span data-stu-id="e63b9-180">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="e63b9-181">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="e63b9-181">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="e63b9-182">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="e63b9-182">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="e63b9-183">Set-Service</span><span class="sxs-lookup"><span data-stu-id="e63b9-183">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="e63b9-184">Start-Service</span><span class="sxs-lookup"><span data-stu-id="e63b9-184">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="e63b9-185">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="e63b9-185">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="e63b9-186">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="e63b9-186">Remove-Service</span></span>](Remove-Service.md)
