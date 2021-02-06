---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resume-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Service
ms.openlocfilehash: 8ce2182117167d93c8f7abd86eeb2c79abdf09c8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602777"
---
# <span data-ttu-id="0954f-102">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="0954f-102">Resume-Service</span></span>

## <span data-ttu-id="0954f-103">概要</span><span class="sxs-lookup"><span data-stu-id="0954f-103">SYNOPSIS</span></span>
<span data-ttu-id="0954f-104">中断 (一時停止) 中のサービスを 1 つ以上再開します。</span><span class="sxs-lookup"><span data-stu-id="0954f-104">Resumes one or more suspended (paused) services.</span></span>

## <span data-ttu-id="0954f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0954f-105">SYNTAX</span></span>

### <span data-ttu-id="0954f-106">InputObject (既定値)</span><span class="sxs-lookup"><span data-stu-id="0954f-106">InputObject (Default)</span></span>

```
Resume-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0954f-107">Default</span><span class="sxs-lookup"><span data-stu-id="0954f-107">Default</span></span>

```
Resume-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="0954f-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0954f-108">DisplayName</span></span>

```
Resume-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0954f-109">Description</span><span class="sxs-lookup"><span data-stu-id="0954f-109">DESCRIPTION</span></span>

<span data-ttu-id="0954f-110">`Resume-Service`コマンドレットは、指定された各サービスの Windows サービスコントローラーに再開メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="0954f-110">The `Resume-Service` cmdlet sends a resume message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="0954f-111">サービスが中断されている場合は、再開されます。</span><span class="sxs-lookup"><span data-stu-id="0954f-111">If a service is suspended, it resumes.</span></span> <span data-ttu-id="0954f-112">現在実行中の場合、メッセージは無視されます。</span><span class="sxs-lookup"><span data-stu-id="0954f-112">If it is currently running, the message is ignored.</span></span> <span data-ttu-id="0954f-113">サービスは、サービス名または表示名で指定できます。また、 **InputObject** パラメーターを使用して、再開するサービスを表すサービスオブジェクトを渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="0954f-113">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the services that you want to resume.</span></span>

## <span data-ttu-id="0954f-114">例</span><span class="sxs-lookup"><span data-stu-id="0954f-114">EXAMPLES</span></span>

### <span data-ttu-id="0954f-115">例 1: ローカルコンピューター上のサービスを再開する</span><span class="sxs-lookup"><span data-stu-id="0954f-115">Example 1: Resume a service on the local computer</span></span>

```
PS C:\> Resume-Service "sens"
```

<span data-ttu-id="0954f-116">このコマンドは、ローカルコンピューター上のシステムイベント通知サービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="0954f-116">This command resumes the System Event Notification service on the local computer.</span></span> <span data-ttu-id="0954f-117">サービス名は、コマンドでは、sens によって表されます。</span><span class="sxs-lookup"><span data-stu-id="0954f-117">The service name is represented in the command by sens.</span></span> <span data-ttu-id="0954f-118">このコマンドは、 **name** パラメーターを使用してサービスのサービス名を指定しますが、パラメーター名は省略可能であるため、コマンドはパラメーター名を省略します。</span><span class="sxs-lookup"><span data-stu-id="0954f-118">The command uses the **Name** parameter to specify the service name of the service, but the command omits the parameter name because the parameter name is optional.</span></span>

### <span data-ttu-id="0954f-119">例 2: すべての中断されたサービスを再開する</span><span class="sxs-lookup"><span data-stu-id="0954f-119">Example 2: Resume all suspended services</span></span>

```
PS C:\> Get-Service | Where-Object {$_.Status -eq "Paused"} | Resume-Service
```

<span data-ttu-id="0954f-120">このコマンドは、コンピューター上のすべての中断されたサービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="0954f-120">This command resumes all of the suspended services on the computer.</span></span> <span data-ttu-id="0954f-121">コマンドレットコマンドを実行すると、 `Get-Service` コンピューター上のすべてのサービスが取得されます。</span><span class="sxs-lookup"><span data-stu-id="0954f-121">The `Get-Service` cmdlet command gets all of the services on the computer.</span></span> <span data-ttu-id="0954f-122">パイプライン演算子 () は、 `|` 結果を `Where-Object` コマンドレットに渡します。このコマンドレットは、 **Status** プロパティが一時停止になっているサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="0954f-122">The pipeline operator (`|`) passes the results to the `Where-Object` cmdlet, which selects the services that have a **Status** property of Paused.</span></span> <span data-ttu-id="0954f-123">次のパイプライン演算子は、結果をに送信します `Resume-Service` 。これにより、一時停止したサービスが再開されます。</span><span class="sxs-lookup"><span data-stu-id="0954f-123">The next pipeline operator sends the results to `Resume-Service`, which resumes the paused services.</span></span>

<span data-ttu-id="0954f-124">実際には、 **WhatIf** パラメーターを使用して、コマンドを実行する前にその効果を判断します。</span><span class="sxs-lookup"><span data-stu-id="0954f-124">In practice, you would use the **WhatIf** parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="0954f-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0954f-125">PARAMETERS</span></span>

### <span data-ttu-id="0954f-126">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="0954f-126">-DisplayName</span></span>

<span data-ttu-id="0954f-127">再開するサービスの表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="0954f-127">Specifies the display names of the services to be resumed.</span></span>
<span data-ttu-id="0954f-128">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0954f-128">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0954f-129">-除外</span><span class="sxs-lookup"><span data-stu-id="0954f-129">-Exclude</span></span>

<span data-ttu-id="0954f-130">このコマンドレットで省略されるサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="0954f-130">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="0954f-131">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="0954f-131">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="0954f-132">「S \*」のように、名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="0954f-132">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="0954f-133">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0954f-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0954f-134">-Include</span><span class="sxs-lookup"><span data-stu-id="0954f-134">-Include</span></span>

<span data-ttu-id="0954f-135">再開するサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="0954f-135">Specifies services to resume.</span></span> <span data-ttu-id="0954f-136">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="0954f-136">The value of this parameter qualifies **Name** parameter.</span></span> <span data-ttu-id="0954f-137">「S \*」のように、名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="0954f-137">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="0954f-138">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0954f-138">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0954f-139">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0954f-139">-InputObject</span></span>

<span data-ttu-id="0954f-140">再開するサービスを表す **ServiceController** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="0954f-140">Specifies **ServiceController** objects that represent the services to resumed.</span></span> <span data-ttu-id="0954f-141">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="0954f-141">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="0954f-142">-Name</span><span class="sxs-lookup"><span data-stu-id="0954f-142">-Name</span></span>

<span data-ttu-id="0954f-143">再開するサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="0954f-143">Specifies the service names of the services to be resumed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0954f-144">-PassThru</span><span class="sxs-lookup"><span data-stu-id="0954f-144">-PassThru</span></span>

<span data-ttu-id="0954f-145">サービスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="0954f-145">Returns an object that represents the service.</span></span> <span data-ttu-id="0954f-146">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="0954f-146">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="0954f-147">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0954f-147">-Confirm</span></span>

<span data-ttu-id="0954f-148">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0954f-148">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0954f-149">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0954f-149">-WhatIf</span></span>

<span data-ttu-id="0954f-150">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="0954f-150">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0954f-151">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="0954f-151">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0954f-152">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="0954f-152">CommonParameters</span></span>

<span data-ttu-id="0954f-153">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="0954f-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0954f-154">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0954f-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0954f-155">入力</span><span class="sxs-lookup"><span data-stu-id="0954f-155">INPUTS</span></span>

### <span data-ttu-id="0954f-156">ServiceController (System.string)、System.string</span><span class="sxs-lookup"><span data-stu-id="0954f-156">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="0954f-157">このコマンドレットには、サービス名を含むサービスオブジェクトまたは文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="0954f-157">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="0954f-158">出力</span><span class="sxs-lookup"><span data-stu-id="0954f-158">OUTPUTS</span></span>

### <span data-ttu-id="0954f-159">None、ServiceController。</span><span class="sxs-lookup"><span data-stu-id="0954f-159">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="0954f-160">このコマンドレットは、 **PassThru** パラメーターを指定した場合に、再開されたサービスを表す **ServiceController** オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="0954f-160">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the resumed service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="0954f-161">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="0954f-161">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0954f-162">注</span><span class="sxs-lookup"><span data-stu-id="0954f-162">NOTES</span></span>

<span data-ttu-id="0954f-163">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0954f-163">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="0954f-164">中断されたサービスの状態は一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="0954f-164">The status of services that have been suspended is Paused.</span></span> <span data-ttu-id="0954f-165">サービスが再開されると、その状態は [実行中] になります。</span><span class="sxs-lookup"><span data-stu-id="0954f-165">When services are resumed, their status is Running.</span></span>
- <span data-ttu-id="0954f-166">`Resume-Service` 現在のユーザーがこの操作を行うためのアクセス許可を持っている場合にのみ、サービスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="0954f-166">`Resume-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="0954f-167">コマンドが正常に機能しない場合は、必要なアクセス許可が与えられていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0954f-167">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="0954f-168">システム上のサービスのサービス名と表示名を確認するには、「」と入力 `Get-Service` します。</span><span class="sxs-lookup"><span data-stu-id="0954f-168">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="0954f-169">サービス名は [ **名前** ] 列に表示され、表示名は [ **DisplayName** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0954f-169">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="0954f-170">関連リンク</span><span class="sxs-lookup"><span data-stu-id="0954f-170">RELATED LINKS</span></span>

[<span data-ttu-id="0954f-171">Get-Service</span><span class="sxs-lookup"><span data-stu-id="0954f-171">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="0954f-172">New-Service</span><span class="sxs-lookup"><span data-stu-id="0954f-172">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="0954f-173">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="0954f-173">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="0954f-174">Set-Service</span><span class="sxs-lookup"><span data-stu-id="0954f-174">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="0954f-175">Start-Service</span><span class="sxs-lookup"><span data-stu-id="0954f-175">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="0954f-176">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="0954f-176">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="0954f-177">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="0954f-177">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="0954f-178">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="0954f-178">Remove-Service</span></span>](Remove-Service.md)
