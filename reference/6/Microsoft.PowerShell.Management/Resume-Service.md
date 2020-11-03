---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resume-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Service
ms.openlocfilehash: 00de396b049259904433843e01879c75e3982ca1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212299"
---
# <span data-ttu-id="346b5-103">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="346b5-103">Resume-Service</span></span>

## <span data-ttu-id="346b5-104">概要</span><span class="sxs-lookup"><span data-stu-id="346b5-104">SYNOPSIS</span></span>
<span data-ttu-id="346b5-105">中断 (一時停止) 中のサービスを 1 つ以上再開します。</span><span class="sxs-lookup"><span data-stu-id="346b5-105">Resumes one or more suspended (paused) services.</span></span>

## <span data-ttu-id="346b5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="346b5-106">SYNTAX</span></span>

### <span data-ttu-id="346b5-107">InputObject (既定値)</span><span class="sxs-lookup"><span data-stu-id="346b5-107">InputObject (Default)</span></span>

```
Resume-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="346b5-108">Default</span><span class="sxs-lookup"><span data-stu-id="346b5-108">Default</span></span>

```
Resume-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="346b5-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="346b5-109">DisplayName</span></span>

```
Resume-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="346b5-110">Description</span><span class="sxs-lookup"><span data-stu-id="346b5-110">DESCRIPTION</span></span>

<span data-ttu-id="346b5-111">**Resume Service** コマンドレットは、指定された各サービスの Windows サービスコントローラーに再開メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="346b5-111">The **Resume-Service** cmdlet sends a resume message to the Windows Service Controller for each of the specified services.</span></span>
<span data-ttu-id="346b5-112">サービスが中断されている場合は、再開されます。</span><span class="sxs-lookup"><span data-stu-id="346b5-112">If a service is suspended, it resumes.</span></span>
<span data-ttu-id="346b5-113">現在実行中の場合、メッセージは無視されます。</span><span class="sxs-lookup"><span data-stu-id="346b5-113">If it is currently running, the message is ignored.</span></span>
<span data-ttu-id="346b5-114">サービスは、サービス名または表示名で指定できます。また、 *InputObject* パラメーターを使用して、再開するサービスを表すサービスオブジェクトを渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="346b5-114">You can specify the services by their service names or display names, or you can use the *InputObject* parameter to pass a service object that represents the services that you want to resume.</span></span>

## <span data-ttu-id="346b5-115">例</span><span class="sxs-lookup"><span data-stu-id="346b5-115">EXAMPLES</span></span>

### <span data-ttu-id="346b5-116">例 1: ローカルコンピューター上のサービスを再開する</span><span class="sxs-lookup"><span data-stu-id="346b5-116">Example 1: Resume a service on the local computer</span></span>

```
PS C:\> Resume-Service "sens"
```

<span data-ttu-id="346b5-117">このコマンドは、ローカルコンピューター上のシステムイベント通知サービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="346b5-117">This command resumes the System Event Notification service  on the local computer.</span></span>
<span data-ttu-id="346b5-118">サービス名は、コマンドでは、sens によって表されます。</span><span class="sxs-lookup"><span data-stu-id="346b5-118">The service name is represented in the command by sens.</span></span>
<span data-ttu-id="346b5-119">このコマンドは、 *name* パラメーターを使用してサービスのサービス名を指定しますが、パラメーター名は省略可能であるため、コマンドはパラメーター名を省略します。</span><span class="sxs-lookup"><span data-stu-id="346b5-119">The command uses the *Name* parameter to specify the service name of the service, but the command omits the parameter name because the parameter name is optional.</span></span>

### <span data-ttu-id="346b5-120">例 2: すべての中断されたサービスを再開する</span><span class="sxs-lookup"><span data-stu-id="346b5-120">Example 2: Resume all suspended services</span></span>

```
PS C:\> Get-Service | Where-Object {$_.Status -eq "Paused"} | Resume-Service
```

<span data-ttu-id="346b5-121">このコマンドは、コンピューター上のすべての中断されたサービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="346b5-121">This command resumes all of the suspended  services on the computer.</span></span>
<span data-ttu-id="346b5-122">Get-Service コマンドレットコマンドは、コンピューター上のすべてのサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="346b5-122">The Get-Service cmdlet command gets all of the services on the computer.</span></span>
<span data-ttu-id="346b5-123">パイプライン演算子 (|) は、Where-Object コマンドレットに結果を渡します。このコマンドレットは、 **Status** プロパティが一時停止になっているサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="346b5-123">The pipeline operator (|) passes the results to the Where-Object cmdlet, which selects the services that have a **Status** property of Paused.</span></span>
<span data-ttu-id="346b5-124">次のパイプライン演算子は、結果を **再開サービス** に送信します。これにより、一時停止したサービスが再開されます。</span><span class="sxs-lookup"><span data-stu-id="346b5-124">The next pipeline operator sends the results to **Resume-Service** , which resumes the paused services.</span></span>

<span data-ttu-id="346b5-125">実際には、 *WhatIf* パラメーターを使用して、コマンドを実行する前にその効果を判断します。</span><span class="sxs-lookup"><span data-stu-id="346b5-125">In practice, you would use the *WhatIf* parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="346b5-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="346b5-126">PARAMETERS</span></span>

### <span data-ttu-id="346b5-127">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="346b5-127">-DisplayName</span></span>

<span data-ttu-id="346b5-128">再開するサービスの表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="346b5-128">Specifies the display names of the services to be resumed.</span></span>
<span data-ttu-id="346b5-129">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="346b5-129">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="346b5-130">-除外</span><span class="sxs-lookup"><span data-stu-id="346b5-130">-Exclude</span></span>

<span data-ttu-id="346b5-131">このコマンドレットで省略されるサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="346b5-131">Specifies services that this cmdlet omits.</span></span>
<span data-ttu-id="346b5-132">このパラメーターの値は、 *Name* パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="346b5-132">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="346b5-133">「S \*」のように、名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="346b5-133">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="346b5-134">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="346b5-134">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="346b5-135">-Include</span><span class="sxs-lookup"><span data-stu-id="346b5-135">-Include</span></span>

<span data-ttu-id="346b5-136">再開するサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="346b5-136">Specifies services to resume.</span></span>
<span data-ttu-id="346b5-137">このパラメーターの値は、 *Name* パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="346b5-137">The value of this parameter qualifies *Name* parameter.</span></span>
<span data-ttu-id="346b5-138">「S \*」のように、名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="346b5-138">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="346b5-139">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="346b5-139">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="346b5-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="346b5-140">-InputObject</span></span>

<span data-ttu-id="346b5-141">再開するサービスを表す **ServiceController** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="346b5-141">Specifies **ServiceController** objects that represent the services to resumed.</span></span>
<span data-ttu-id="346b5-142">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="346b5-142">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="346b5-143">-Name</span><span class="sxs-lookup"><span data-stu-id="346b5-143">-Name</span></span>

<span data-ttu-id="346b5-144">再開するサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="346b5-144">Specifies the service names of the services to be resumed.</span></span>

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

### <span data-ttu-id="346b5-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="346b5-145">-PassThru</span></span>

<span data-ttu-id="346b5-146">サービスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="346b5-146">Returns an object that represents the service.</span></span>
<span data-ttu-id="346b5-147">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="346b5-147">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="346b5-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="346b5-148">-Confirm</span></span>

<span data-ttu-id="346b5-149">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="346b5-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="346b5-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="346b5-150">-WhatIf</span></span>

<span data-ttu-id="346b5-151">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="346b5-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="346b5-152">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="346b5-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="346b5-153">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="346b5-153">CommonParameters</span></span>

<span data-ttu-id="346b5-154">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="346b5-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="346b5-155">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="346b5-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="346b5-156">入力</span><span class="sxs-lookup"><span data-stu-id="346b5-156">INPUTS</span></span>

### <span data-ttu-id="346b5-157">ServiceController (System.string)、System.string</span><span class="sxs-lookup"><span data-stu-id="346b5-157">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="346b5-158">このコマンドレットには、サービス名を含むサービスオブジェクトまたは文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="346b5-158">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="346b5-159">出力</span><span class="sxs-lookup"><span data-stu-id="346b5-159">OUTPUTS</span></span>

### <span data-ttu-id="346b5-160">None、ServiceController。</span><span class="sxs-lookup"><span data-stu-id="346b5-160">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="346b5-161">このコマンドレットは、 *PassThru* パラメーターを指定した場合に、再開されたサービスを表す **ServiceController** オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="346b5-161">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the resumed service, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="346b5-162">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="346b5-162">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="346b5-163">注</span><span class="sxs-lookup"><span data-stu-id="346b5-163">NOTES</span></span>

* <span data-ttu-id="346b5-164">中断されたサービスの状態は一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="346b5-164">The status of services that have been suspended is Paused.</span></span> <span data-ttu-id="346b5-165">サービスが再開されると、その状態は [実行中] になります。</span><span class="sxs-lookup"><span data-stu-id="346b5-165">When services are resumed, their status is Running.</span></span>
* <span data-ttu-id="346b5-166">**Resume-サービス** は、現在のユーザーがこの操作を行うためのアクセス許可を持っている場合にのみサービスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="346b5-166">**Resume-Service** can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="346b5-167">コマンドが正常に機能しない場合は、必要なアクセス許可が与えられていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="346b5-167">If a command does not work correctly, you might not have the required permissions.</span></span>
* <span data-ttu-id="346b5-168">システム上のサービスのサービス名と表示名を確認するには、「」と入力 `Get-Service` します。</span><span class="sxs-lookup"><span data-stu-id="346b5-168">To find the service names and display names of the services on your system, type `Get-Service`.</span></span> <span data-ttu-id="346b5-169">サービス名は [ **名前** ] 列に表示され、表示名は [ **DisplayName** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="346b5-169">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="346b5-170">関連リンク</span><span class="sxs-lookup"><span data-stu-id="346b5-170">RELATED LINKS</span></span>

[<span data-ttu-id="346b5-171">Get-Service</span><span class="sxs-lookup"><span data-stu-id="346b5-171">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="346b5-172">New-Service</span><span class="sxs-lookup"><span data-stu-id="346b5-172">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="346b5-173">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="346b5-173">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="346b5-174">Set-Service</span><span class="sxs-lookup"><span data-stu-id="346b5-174">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="346b5-175">Start-Service</span><span class="sxs-lookup"><span data-stu-id="346b5-175">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="346b5-176">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="346b5-176">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="346b5-177">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="346b5-177">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="346b5-178">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="346b5-178">Remove-Service</span></span>](Remove-Service.md)