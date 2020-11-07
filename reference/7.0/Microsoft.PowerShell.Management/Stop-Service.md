---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Service
ms.openlocfilehash: 9dd0e04476d9f935d3284c30d1628b31417c14c2
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346294"
---
# <span data-ttu-id="a66ea-103">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="a66ea-103">Stop-Service</span></span>

## <span data-ttu-id="a66ea-104">概要</span><span class="sxs-lookup"><span data-stu-id="a66ea-104">SYNOPSIS</span></span>
<span data-ttu-id="a66ea-105">実行中のサービスを 1 つ以上停止します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-105">Stops one or more running services.</span></span>

## <span data-ttu-id="a66ea-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a66ea-106">SYNTAX</span></span>

### <span data-ttu-id="a66ea-107">InputObject (既定値)</span><span class="sxs-lookup"><span data-stu-id="a66ea-107">InputObject (Default)</span></span>

```
Stop-Service [-Force] [-NoWait] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a66ea-108">Default</span><span class="sxs-lookup"><span data-stu-id="a66ea-108">Default</span></span>

```
Stop-Service [-Force] [-NoWait] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a66ea-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a66ea-109">DisplayName</span></span>

```
Stop-Service [-Force] [-NoWait] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a66ea-110">Description</span><span class="sxs-lookup"><span data-stu-id="a66ea-110">DESCRIPTION</span></span>

<span data-ttu-id="a66ea-111">`Stop-Service`コマンドレットは、指定された各サービスについて、Windows サービスコントローラーに停止メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-111">The `Stop-Service` cmdlet sends a stop message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="a66ea-112">サービスは、サービス名または表示名で指定できます。また、 **InputObject** パラメーターを使用して、停止するサービスを表すサービスオブジェクトを渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="a66ea-112">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the service that you want to stop.</span></span>

## <span data-ttu-id="a66ea-113">例</span><span class="sxs-lookup"><span data-stu-id="a66ea-113">EXAMPLES</span></span>

### <span data-ttu-id="a66ea-114">例 1: ローカルコンピューター上のサービスを停止する</span><span class="sxs-lookup"><span data-stu-id="a66ea-114">Example 1: Stop a service on the local computer</span></span>

```
PS C:\> Stop-Service -Name "sysmonlog"
```

<span data-ttu-id="a66ea-115">このコマンドを実行すると、ローカル コンピューター上のパフォーマンス ログと警告 (SysmonLog) サービスが停止されます。</span><span class="sxs-lookup"><span data-stu-id="a66ea-115">This command stops the Performance Logs and Alerts (SysmonLog) service on the local computer.</span></span>

### <span data-ttu-id="a66ea-116">例 2: 表示名を使用してサービスを停止する</span><span class="sxs-lookup"><span data-stu-id="a66ea-116">Example 2: Stop a service by using the display name</span></span>

```
PS C:\> Get-Service -DisplayName "telnet" | Stop-Service
```

<span data-ttu-id="a66ea-117">このコマンドを実行すると、ローカル コンピューター上の Telnet サービスが停止されます。</span><span class="sxs-lookup"><span data-stu-id="a66ea-117">This command stops the Telnet service on the local computer.</span></span> <span data-ttu-id="a66ea-118">このコマンドは、を使用して、 `Get-Service` Telnet サービスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-118">The command uses `Get-Service` to get an object that represents the Telnet service.</span></span> <span data-ttu-id="a66ea-119">パイプライン演算子 () は、 `|` オブジェクトをにパイプ処理して `Stop-Service` 、サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-119">The pipeline operator (`|`) pipes the object to `Stop-Service`, which stops the service.</span></span>

### <span data-ttu-id="a66ea-120">例 3: 依存サービスを持つサービスを停止する</span><span class="sxs-lookup"><span data-stu-id="a66ea-120">Example 3: Stop a service that has dependent services</span></span>

```
PS C:\> Get-Service -Name "iisadmin" | Format-List -Property Name, DependentServices
PS C:\> Stop-Service -Name "iisadmin" -Force -Confirm
```

<span data-ttu-id="a66ea-121">この例では、ローカルコンピューター上の IISAdmin サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-121">This example stops the IISAdmin service on the local computer.</span></span> <span data-ttu-id="a66ea-122">このサービスを停止すると、IISAdmin サービスに依存するサービスも停止されるため、その前に、 `Stop-Service` iisadmin サービスに依存するサービスを一覧表示するコマンドを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a66ea-122">Because stopping this service also stops the services that depend on the IISAdmin service, it is best to precede `Stop-Service` with a command that lists the services that depend on the IISAdmin service.</span></span>

<span data-ttu-id="a66ea-123">最初のコマンドを実行すると、IISAdmin に依存するサービスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a66ea-123">The first command lists the services that depend on IISAdmin.</span></span> <span data-ttu-id="a66ea-124">を使用して、 `Get-Service` IISAdmin サービスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-124">It uses `Get-Service` to get an object that represents the IISAdmin service.</span></span> <span data-ttu-id="a66ea-125">パイプライン演算子 () は、 `|` 結果を `Format-List` コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-125">The pipeline operator (`|`) passes the result to the `Format-List` cmdlet.</span></span> <span data-ttu-id="a66ea-126">このコマンドは、の **Property** パラメーターを使用して、 `Format-List` サービスの **Name** プロパティと **dependentservices** プロパティのみを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-126">The command uses the **Property** parameter of `Format-List` to list only the **Name** and **DependentServices** properties of the service.</span></span>

<span data-ttu-id="a66ea-127">2 番目のコマンドを実行すると、IISAdmin サービスが停止します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-127">The second command stops the IISAdmin service.</span></span> <span data-ttu-id="a66ea-128">**Force** パラメーターは、依存サービスを持つサービスを停止するために必要です。</span><span class="sxs-lookup"><span data-stu-id="a66ea-128">The **Force** parameter is required to stop a service that has dependent services.</span></span> <span data-ttu-id="a66ea-129">このコマンドでは、 **Confirm** パラメーターを使用して、各サービスを停止する前にユーザーに確認を要求します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-129">The command uses the **Confirm** parameter to request confirmation from the user before it stops each service.</span></span>

## <span data-ttu-id="a66ea-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a66ea-130">PARAMETERS</span></span>

### <span data-ttu-id="a66ea-131">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="a66ea-131">-DisplayName</span></span>

<span data-ttu-id="a66ea-132">停止するサービスの表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-132">Specifies the display names of the services to stop.</span></span>
<span data-ttu-id="a66ea-133">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a66ea-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a66ea-134">-除外</span><span class="sxs-lookup"><span data-stu-id="a66ea-134">-Exclude</span></span>

<span data-ttu-id="a66ea-135">このコマンドレットで省略されるサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-135">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="a66ea-136">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-136">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="a66ea-137">「S \*」のように、名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-137">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="a66ea-138">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a66ea-138">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a66ea-139">-Force</span><span class="sxs-lookup"><span data-stu-id="a66ea-139">-Force</span></span>

<span data-ttu-id="a66ea-140">サービスに依存するサービスがある場合でも、強制的にサービスを停止するようにコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-140">Forces the cmdlet to stop a service even if that service has dependent services.</span></span>

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

### <span data-ttu-id="a66ea-141">-Include</span><span class="sxs-lookup"><span data-stu-id="a66ea-141">-Include</span></span>

<span data-ttu-id="a66ea-142">このコマンドレットが停止するサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-142">Specifies services that this cmdlet stops.</span></span> <span data-ttu-id="a66ea-143">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-143">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="a66ea-144">「S \*」のように、名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-144">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="a66ea-145">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a66ea-145">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a66ea-146">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a66ea-146">-InputObject</span></span>

<span data-ttu-id="a66ea-147">停止するサービスを表す **ServiceController** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-147">Specifies **ServiceController** objects that represent the services to stop.</span></span> <span data-ttu-id="a66ea-148">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-148">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="a66ea-149">-Name</span><span class="sxs-lookup"><span data-stu-id="a66ea-149">-Name</span></span>

<span data-ttu-id="a66ea-150">停止するサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-150">Specifies the service names of the services to stop.</span></span> <span data-ttu-id="a66ea-151">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a66ea-151">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a66ea-152">-NoWait</span><span class="sxs-lookup"><span data-stu-id="a66ea-152">-NoWait</span></span>

<span data-ttu-id="a66ea-153">このコマンドレットが no wait オプションを使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-153">Indicates that this cmdlet uses the no wait option.</span></span>

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

### <span data-ttu-id="a66ea-154">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a66ea-154">-PassThru</span></span>

<span data-ttu-id="a66ea-155">サービスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-155">Returns an object that represents the service.</span></span> <span data-ttu-id="a66ea-156">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="a66ea-156">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="a66ea-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a66ea-157">-Confirm</span></span>

<span data-ttu-id="a66ea-158">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a66ea-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a66ea-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a66ea-159">-WhatIf</span></span>

<span data-ttu-id="a66ea-160">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-160">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a66ea-161">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a66ea-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a66ea-162">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a66ea-162">CommonParameters</span></span>

<span data-ttu-id="a66ea-163">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a66ea-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a66ea-164">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a66ea-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a66ea-165">入力</span><span class="sxs-lookup"><span data-stu-id="a66ea-165">INPUTS</span></span>

### <span data-ttu-id="a66ea-166">ServiceController (System.string)、System.string</span><span class="sxs-lookup"><span data-stu-id="a66ea-166">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="a66ea-167">このコマンドレットには、サービスオブジェクトまたはサービス名を含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="a66ea-167">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="a66ea-168">出力</span><span class="sxs-lookup"><span data-stu-id="a66ea-168">OUTPUTS</span></span>

### <span data-ttu-id="a66ea-169">None、ServiceController。</span><span class="sxs-lookup"><span data-stu-id="a66ea-169">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="a66ea-170">このコマンドレットは、 **PassThru** パラメーターを使用する場合に、サービスを表す **ServiceController** オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-170">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you use the **PassThru** parameter.</span></span> <span data-ttu-id="a66ea-171">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="a66ea-171">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a66ea-172">注</span><span class="sxs-lookup"><span data-stu-id="a66ea-172">NOTES</span></span>

<span data-ttu-id="a66ea-173">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a66ea-173">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="a66ea-174">また、 `Stop-Service` 組み込みエイリアスである **spsv** でを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="a66ea-174">You can also refer to `Stop-Service` by its built-in alias, **spsv**.</span></span> <span data-ttu-id="a66ea-175">詳細については、「about_Aliases」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a66ea-175">For more information, see about_Aliases.</span></span>

<span data-ttu-id="a66ea-176">`Stop-Service` 現在のユーザーがこの操作を行うためのアクセス許可を持っている場合にのみ、サービスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="a66ea-176">`Stop-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="a66ea-177">コマンドが正常に機能しない場合は、必要なアクセス許可が与えられていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a66ea-177">If a command does not work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="a66ea-178">システム上のサービスのサービス名と表示名を確認するには、「」と入力 `Get-Service` します。</span><span class="sxs-lookup"><span data-stu-id="a66ea-178">To find the service names and display names of the services on your system, type `Get-Service`.</span></span> <span data-ttu-id="a66ea-179">サービス名は [ **名前** ] 列に表示され、表示名は [ **DisplayName** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a66ea-179">The service names appear in the **Name** column and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="a66ea-180">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a66ea-180">RELATED LINKS</span></span>

[<span data-ttu-id="a66ea-181">Get-Service</span><span class="sxs-lookup"><span data-stu-id="a66ea-181">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="a66ea-182">New-Service</span><span class="sxs-lookup"><span data-stu-id="a66ea-182">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="a66ea-183">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="a66ea-183">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="a66ea-184">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="a66ea-184">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="a66ea-185">Set-Service</span><span class="sxs-lookup"><span data-stu-id="a66ea-185">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="a66ea-186">Start-Service</span><span class="sxs-lookup"><span data-stu-id="a66ea-186">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="a66ea-187">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="a66ea-187">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="a66ea-188">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="a66ea-188">Remove-Service</span></span>](Remove-Service.md)
