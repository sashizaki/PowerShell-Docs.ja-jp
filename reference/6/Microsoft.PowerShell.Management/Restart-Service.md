---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Service
ms.openlocfilehash: edbe7f93a3bef4b82adbba6b8a39b761fa54c28e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212304"
---
# <span data-ttu-id="7a612-103">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="7a612-103">Restart-Service</span></span>

## <span data-ttu-id="7a612-104">概要</span><span class="sxs-lookup"><span data-stu-id="7a612-104">SYNOPSIS</span></span>
<span data-ttu-id="7a612-105">1 つ以上のサービスを停止し、再起動します。</span><span class="sxs-lookup"><span data-stu-id="7a612-105">Stops and then starts one or more services.</span></span>

## <span data-ttu-id="7a612-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7a612-106">SYNTAX</span></span>

### <span data-ttu-id="7a612-107">InputObject (既定値)</span><span class="sxs-lookup"><span data-stu-id="7a612-107">InputObject (Default)</span></span>

```
Restart-Service [-Force] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7a612-108">Default</span><span class="sxs-lookup"><span data-stu-id="7a612-108">Default</span></span>

```
Restart-Service [-Force] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7a612-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7a612-109">DisplayName</span></span>

```
Restart-Service [-Force] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7a612-110">Description</span><span class="sxs-lookup"><span data-stu-id="7a612-110">DESCRIPTION</span></span>

<span data-ttu-id="7a612-111">**Restart service** コマンドレットは、指定されたサービスの Windows サービスコントローラーに停止メッセージを送信した後、開始メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="7a612-111">The **Restart-Service** cmdlet sends a stop message and then a start message to the Windows Service Controller for a specified service.</span></span>
<span data-ttu-id="7a612-112">サービスが既に停止している場合は、エラーを通知せずに起動されます。</span><span class="sxs-lookup"><span data-stu-id="7a612-112">If a service was already stopped, it is started without notifying you of an error.</span></span>
<span data-ttu-id="7a612-113">サービスは、サービス名または表示名で指定できます。また、 *InputObject* パラメーターを使用して、再起動する各サービスを表すオブジェクトを渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="7a612-113">You can specify the services by their service names or display names, or you can use the *InputObject* parameter to pass an object that represents each service that you want to restart.</span></span>

## <span data-ttu-id="7a612-114">例</span><span class="sxs-lookup"><span data-stu-id="7a612-114">EXAMPLES</span></span>

### <span data-ttu-id="7a612-115">例 1: ローカルコンピューター上のサービスを再起動する</span><span class="sxs-lookup"><span data-stu-id="7a612-115">Example 1: Restart a service on the local computer</span></span>

```powershell
PS C:\> Restart-Service -Name winmgmt
```

<span data-ttu-id="7a612-116">このコマンドを実行すると、ローカル コンピューター上の Windows Management Instrumentation サービス (WinMgmt) が再起動されます。</span><span class="sxs-lookup"><span data-stu-id="7a612-116">This command restarts the Windows Management Instrumentation service (WinMgmt) on the local computer.</span></span>

### <span data-ttu-id="7a612-117">例 2: サービスを除外する</span><span class="sxs-lookup"><span data-stu-id="7a612-117">Example 2: Exclude a service</span></span>

```powershell
PS C:\> Restart-Service -DisplayName "net*" -Exclude "net logon"
```

<span data-ttu-id="7a612-118">このコマンドは、net Logon サービスを除き、Net で始まる表示名を持つサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="7a612-118">This command restarts the services that have a display name that starts with Net, except for the Net Logon service.</span></span>

### <span data-ttu-id="7a612-119">例 3: 停止したすべてのネットワークサービスを開始する</span><span class="sxs-lookup"><span data-stu-id="7a612-119">Example 3: Start all stopped network services</span></span>

```powershell
PS C:\> Get-Service -Name "net*" | Where-Object {$_.Status -eq "Stopped"} | Restart-Service
```

<span data-ttu-id="7a612-120">このコマンドを実行すると、コンピューター上で停止しているネットワーク サービスがすべて開始されます。</span><span class="sxs-lookup"><span data-stu-id="7a612-120">This command starts all of the stopped network services on the computer.</span></span>

<span data-ttu-id="7a612-121">このコマンドは、Get-Service コマンドレットを使用して、サービス名が net で始まるサービスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="7a612-121">This command uses the Get-Service cmdlet to get objects that represent the services whose service name starts with net.</span></span>
<span data-ttu-id="7a612-122">パイプライン演算子 (|) により、サービスオブジェクトが Where-Object コマンドレットに送信されます。このコマンドレットは、status が stopped のサービスだけを選択します。</span><span class="sxs-lookup"><span data-stu-id="7a612-122">The pipeline operator (|) sends the services object to the Where-Object cmdlet, which selects only the services that have a status of stopped.</span></span>
<span data-ttu-id="7a612-123">もう1つのパイプライン演算子は、選択したサービスを **再起動サービス** に送信します。</span><span class="sxs-lookup"><span data-stu-id="7a612-123">Another pipeline operator sends the selected services to **Restart-Service** .</span></span>

<span data-ttu-id="7a612-124">実際には、 *WhatIf* パラメーターを使用して、コマンドを実行する前にその効果を判断します。</span><span class="sxs-lookup"><span data-stu-id="7a612-124">In practice, you would use the *WhatIf* parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="7a612-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7a612-125">PARAMETERS</span></span>

### <span data-ttu-id="7a612-126">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="7a612-126">-DisplayName</span></span>

<span data-ttu-id="7a612-127">再起動するサービスの表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="7a612-127">Specifies the display names of services to restarted.</span></span>
<span data-ttu-id="7a612-128">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a612-128">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="7a612-129">-除外</span><span class="sxs-lookup"><span data-stu-id="7a612-129">-Exclude</span></span>

<span data-ttu-id="7a612-130">このコマンドレットで省略されるサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7a612-130">Specifies services that this cmdlet omits.</span></span>
<span data-ttu-id="7a612-131">このパラメーターの値は、 *Name* パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="7a612-131">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="7a612-132">「S \*」のように、名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="7a612-132">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="7a612-133">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a612-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="7a612-134">-Force</span><span class="sxs-lookup"><span data-stu-id="7a612-134">-Force</span></span>

<span data-ttu-id="7a612-135">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a612-135">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="7a612-136">-Include</span><span class="sxs-lookup"><span data-stu-id="7a612-136">-Include</span></span>

<span data-ttu-id="7a612-137">このコマンドレットによって再起動されるサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7a612-137">Specifies services that this cmdlet restarts.</span></span>
<span data-ttu-id="7a612-138">このパラメーターの値は、 *Name* パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="7a612-138">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="7a612-139">「S \*」のように、名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="7a612-139">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="7a612-140">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a612-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="7a612-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7a612-141">-InputObject</span></span>

<span data-ttu-id="7a612-142">再起動するサービスを表す **ServiceController** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7a612-142">Specifies **ServiceController** objects that represent the services to restart.</span></span>
<span data-ttu-id="7a612-143">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="7a612-143">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="7a612-144">-Name</span><span class="sxs-lookup"><span data-stu-id="7a612-144">-Name</span></span>

<span data-ttu-id="7a612-145">再起動するサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="7a612-145">Specifies the service names of the services to restart.</span></span>

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

### <span data-ttu-id="7a612-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="7a612-146">-PassThru</span></span>

<span data-ttu-id="7a612-147">サービスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7a612-147">Returns an object that represents the service.</span></span>
<span data-ttu-id="7a612-148">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="7a612-148">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="7a612-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7a612-149">-Confirm</span></span>

<span data-ttu-id="7a612-150">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a612-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7a612-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7a612-151">-WhatIf</span></span>

<span data-ttu-id="7a612-152">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="7a612-152">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7a612-153">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="7a612-153">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7a612-154">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7a612-154">CommonParameters</span></span>

<span data-ttu-id="7a612-155">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7a612-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7a612-156">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a612-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7a612-157">入力</span><span class="sxs-lookup"><span data-stu-id="7a612-157">INPUTS</span></span>

### <span data-ttu-id="7a612-158">ServiceController (System.string)、System.string</span><span class="sxs-lookup"><span data-stu-id="7a612-158">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="7a612-159">このコマンドレットには、サービス名を含むサービスオブジェクトまたは文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="7a612-159">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="7a612-160">出力</span><span class="sxs-lookup"><span data-stu-id="7a612-160">OUTPUTS</span></span>

### <span data-ttu-id="7a612-161">None、ServiceController。</span><span class="sxs-lookup"><span data-stu-id="7a612-161">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="7a612-162">このコマンドレットは、 *PassThru* パラメーターを指定した場合に、再起動されたサービスを表す **ServiceController** オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="7a612-162">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the restarted service, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="7a612-163">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="7a612-163">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7a612-164">注</span><span class="sxs-lookup"><span data-stu-id="7a612-164">NOTES</span></span>

* <span data-ttu-id="7a612-165">**サービスの再起動で** は、現在のユーザーがこの操作を行うためのアクセス許可を持っている場合にのみサービスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="7a612-165">**Restart-Service** can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="7a612-166">コマンドが正常に機能しない場合は、必要なアクセス許可が与えられていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7a612-166">If a command does not work correctly, you might not have the required permissions.</span></span>
* <span data-ttu-id="7a612-167">システム上のサービスのサービス名と表示名を確認するには、「 **Get service** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="7a612-167">To find the service names and display names of the services on your system, type **Get-Service** ".</span></span> <span data-ttu-id="7a612-168">サービス名は [ **名前** ] 列に表示され、表示名は [ **DisplayName** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a612-168">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="7a612-169">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7a612-169">RELATED LINKS</span></span>

[<span data-ttu-id="7a612-170">Get-Service</span><span class="sxs-lookup"><span data-stu-id="7a612-170">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="7a612-171">New-Service</span><span class="sxs-lookup"><span data-stu-id="7a612-171">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="7a612-172">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="7a612-172">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="7a612-173">Set-Service</span><span class="sxs-lookup"><span data-stu-id="7a612-173">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="7a612-174">Start-Service</span><span class="sxs-lookup"><span data-stu-id="7a612-174">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="7a612-175">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="7a612-175">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="7a612-176">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="7a612-176">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="7a612-177">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="7a612-177">Remove-Service</span></span>](Remove-Service.md)
