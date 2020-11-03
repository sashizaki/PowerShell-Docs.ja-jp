---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Service
ms.openlocfilehash: 13ef4d483ad91b38c175f850da9cd4d1da771935
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209752"
---
# <span data-ttu-id="6b3e4-103">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="6b3e4-103">Remove-Service</span></span>

## <span data-ttu-id="6b3e4-104">概要</span><span class="sxs-lookup"><span data-stu-id="6b3e4-104">SYNOPSIS</span></span>
<span data-ttu-id="6b3e4-105">Windows サービスを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-105">Removes a Windows service.</span></span>

## <span data-ttu-id="6b3e4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6b3e4-106">SYNTAX</span></span>

### <span data-ttu-id="6b3e4-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="6b3e4-107">Name (Default)</span></span>

```
Remove-Service [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6b3e4-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="6b3e4-108">InputObject</span></span>

```
Remove-Service [-InputObject <ServiceController>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6b3e4-109">Description</span><span class="sxs-lookup"><span data-stu-id="6b3e4-109">DESCRIPTION</span></span>

<span data-ttu-id="6b3e4-110">`Remove-Service`コマンドレットは、レジストリとサービスデータベース内の Windows サービスを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-110">The `Remove-Service` cmdlet removes a Windows service in the registry and in the service database.</span></span>

<span data-ttu-id="6b3e4-111">`Remove-Service`コマンドレットは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-111">The `Remove-Service` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="6b3e4-112">例</span><span class="sxs-lookup"><span data-stu-id="6b3e4-112">EXAMPLES</span></span>

### <span data-ttu-id="6b3e4-113">例 1: サービスを削除する</span><span class="sxs-lookup"><span data-stu-id="6b3e4-113">Example 1: Remove a service</span></span>

<span data-ttu-id="6b3e4-114">これにより、TestService という名前のサービスが削除されます。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-114">This removes a service named TestService.</span></span>

```powershell
Remove-Service -Name "TestService"
```

### <span data-ttu-id="6b3e4-115">例 2: 表示名を使用してサービスを削除する</span><span class="sxs-lookup"><span data-stu-id="6b3e4-115">Example 2: Remove a service using the display name</span></span>

<span data-ttu-id="6b3e4-116">この例では、TestService という名前のサービスを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-116">This example removes a service named TestService.</span></span> <span data-ttu-id="6b3e4-117">このコマンドは、を使用し `Get-Service` て、TestService サービスを表すオブジェクトを表示名を使用して取得します。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-117">The command uses `Get-Service` to get an object that represents the TestService service using the display name.</span></span> <span data-ttu-id="6b3e4-118">パイプライン演算子 () は、 `|` オブジェクトをにパイプ `Remove-Service` 処理します。これにより、サービスが削除されます。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-118">The pipeline operator (`|`) pipes the object to `Remove-Service`, which removes the service.</span></span>

```powershell
Get-Service -DisplayName "Test Service" | Remove-Service
```

## <span data-ttu-id="6b3e4-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6b3e4-119">PARAMETERS</span></span>

### <span data-ttu-id="6b3e4-120">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6b3e4-120">-InputObject</span></span>

<span data-ttu-id="6b3e4-121">削除するサービスを表す **ServiceController** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-121">Specifies **ServiceController** objects that represent the services to remove.</span></span> <span data-ttu-id="6b3e4-122">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-122">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6b3e4-123">-Name</span><span class="sxs-lookup"><span data-stu-id="6b3e4-123">-Name</span></span>

<span data-ttu-id="6b3e4-124">削除するサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-124">Specifies the service names of the services to remove.</span></span> <span data-ttu-id="6b3e4-125">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-125">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="6b3e4-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6b3e4-126">-Confirm</span></span>

<span data-ttu-id="6b3e4-127">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6b3e4-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6b3e4-128">-WhatIf</span></span>

<span data-ttu-id="6b3e4-129">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-129">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6b3e4-130">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6b3e4-131">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b3e4-131">CommonParameters</span></span>

<span data-ttu-id="6b3e4-132">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6b3e4-133">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6b3e4-134">入力</span><span class="sxs-lookup"><span data-stu-id="6b3e4-134">INPUTS</span></span>

### <span data-ttu-id="6b3e4-135">ServiceController (System.string)、System.string</span><span class="sxs-lookup"><span data-stu-id="6b3e4-135">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="6b3e4-136">このコマンドレットには、サービスオブジェクトまたはサービス名を含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-136">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="6b3e4-137">出力</span><span class="sxs-lookup"><span data-stu-id="6b3e4-137">OUTPUTS</span></span>

### <span data-ttu-id="6b3e4-138">なし</span><span class="sxs-lookup"><span data-stu-id="6b3e4-138">None</span></span>

<span data-ttu-id="6b3e4-139">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-139">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="6b3e4-140">注</span><span class="sxs-lookup"><span data-stu-id="6b3e4-140">NOTES</span></span>

<span data-ttu-id="6b3e4-141">このコマンドレットを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="6b3e4-141">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="6b3e4-142">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6b3e4-142">RELATED LINKS</span></span>

[<span data-ttu-id="6b3e4-143">Get-Service</span><span class="sxs-lookup"><span data-stu-id="6b3e4-143">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="6b3e4-144">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="6b3e4-144">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="6b3e4-145">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="6b3e4-145">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="6b3e4-146">Set-Service</span><span class="sxs-lookup"><span data-stu-id="6b3e4-146">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="6b3e4-147">Start-Service</span><span class="sxs-lookup"><span data-stu-id="6b3e4-147">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="6b3e4-148">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="6b3e4-148">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="6b3e4-149">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="6b3e4-149">Suspend-Service</span></span>](Suspend-Service.md)
