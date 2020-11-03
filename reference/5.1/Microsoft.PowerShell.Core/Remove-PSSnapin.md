---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSnapin
ms.openlocfilehash: e74aff3e52c61f41a54664efbab9c0f195b0d409
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212779"
---
# <span data-ttu-id="a2b2e-103">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="a2b2e-103">Remove-PSSnapin</span></span>

## <span data-ttu-id="a2b2e-104">概要</span><span class="sxs-lookup"><span data-stu-id="a2b2e-104">SYNOPSIS</span></span>
<span data-ttu-id="a2b2e-105">現在のセッションから Windows PowerShell スナップインを削除します。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-105">Removes Windows PowerShell snap-ins from the current session.</span></span>

## <span data-ttu-id="a2b2e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a2b2e-106">SYNTAX</span></span>

```
Remove-PSSnapin [-Name] <String[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a2b2e-107">Description</span><span class="sxs-lookup"><span data-stu-id="a2b2e-107">DESCRIPTION</span></span>
<span data-ttu-id="a2b2e-108">**Add-pssnapin** コマンドレットは、Windows PowerShell スナップインを現在のセッションから削除します。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-108">The **Remove-PSSnapin** cmdlet removes a Windows PowerShell snap-in from the current session.</span></span>
<span data-ttu-id="a2b2e-109">このコマンドレットを使用すると、windows PowerShell に追加したスナップインを削除できます。このコマンドレットを使用して、Windows PowerShell でインストールされているスナップインを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-109">You can use it to remove snap-ins that you have added to Windows PowerShell You cannot use this cmdlet to remove the snap-ins that are installed with Windows PowerShell.</span></span>

<span data-ttu-id="a2b2e-110">現在のセッションからスナップインを削除すると、スナップインはまだ読み込まれていますが、スナップイン内のコマンドレットとプロバイダーはセッションで使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-110">After you remove a snap-in from the current session, the snap-in is still loaded, but the cmdlets and providers in the snap-in are no longer available in the session.</span></span>

## <span data-ttu-id="a2b2e-111">例</span><span class="sxs-lookup"><span data-stu-id="a2b2e-111">EXAMPLES</span></span>

### <span data-ttu-id="a2b2e-112">例 1: スナップインを削除する</span><span class="sxs-lookup"><span data-stu-id="a2b2e-112">Example 1: Remove a snap-in</span></span>

```
PS C:\> remove-pssnapin -Name Microsoft.Exchange
```

<span data-ttu-id="a2b2e-113">このコマンドは、現在のセッションから、 **Microsoft Exchange** のスナップインを削除します。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-113">This command removes the **Microsoft.Exchange** snap-in from the current session.</span></span>
<span data-ttu-id="a2b2e-114">コマンドが完了すると、スナップインがサポートしていたコマンドレットとプロバイダーは、セッションで使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-114">When the command is complete, the cmdlets and providers that the snap-in supported are not available in the session.</span></span>

### <span data-ttu-id="a2b2e-115">例 2: パイプラインで名前を使用してスナップインを削除する</span><span class="sxs-lookup"><span data-stu-id="a2b2e-115">Example 2: Remove snap-ins by using names with the pipeline</span></span>

```
PS C:\> Get-PSSnapIn smp* | Remove-PSSnapIn
```

<span data-ttu-id="a2b2e-116">このコマンドは、現在のセッションから、smp で始まる名前を持つ Windows PowerShell スナップインを削除します。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-116">This command removes the Windows PowerShell snap-ins that have names that start with smp from the current session.</span></span>

<span data-ttu-id="a2b2e-117">このコマンドは、 **add-pssnapin** コマンドレットを使用して、スナップインを表すオブジェクトを取得します。パイプライン演算子 (|) により、結果が **add-pssnapin** コマンドレットに送信され、セッションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-117">The command uses the **Get-PSSnapin** cmdlet to get objects that represent the snap-ins. The pipeline operator (|) sends the results to the **Remove-PSSnapin** cmdlet, which removes them from the session.</span></span>
<span data-ttu-id="a2b2e-118">このスナップインがサポートするプロバイダーとコマンドレットは、セッションで使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-118">The providers and cmdlets that this snap-in supports are no longer available in the session.</span></span>

<span data-ttu-id="a2b2e-119">パイプを使用してオブジェクトを **add-pssnapin** に渡すと、オブジェクトの名前が *name* パラメーターに関連付けられます。このパラメーターは、 **name** プロパティを持つパイプラインからのオブジェクトを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-119">When you pipe objects to **Remove-PSSnapin** , the names of the objects are associated with the *Name* parameter, which accepts objects from the pipeline that have a **Name** property.</span></span>

### <span data-ttu-id="a2b2e-120">例 3: 名前を使用してスナップインを削除する</span><span class="sxs-lookup"><span data-stu-id="a2b2e-120">Example 3: Remove snap-ins by using names</span></span>

```
PS C:\> Remove-PSSnapin -Name *event*
```

<span data-ttu-id="a2b2e-121">このコマンドは、イベントを含む名前を持つすべての Windows PowerShell スナップインを削除します。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-121">This command removes all Windows PowerShell snap-ins that have names that include event.</span></span>

## <span data-ttu-id="a2b2e-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a2b2e-122">PARAMETERS</span></span>

### <span data-ttu-id="a2b2e-123">-Name</span><span class="sxs-lookup"><span data-stu-id="a2b2e-123">-Name</span></span>
<span data-ttu-id="a2b2e-124">現在のセッションから削除する Windows PowerShell スナップインの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-124">Specifies the names of Windows PowerShell snap-ins to remove from the current session.</span></span>
<span data-ttu-id="a2b2e-125">ワイルドカード文字 (\*) が許可されます。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-125">Wildcard characters (\*) are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a2b2e-126">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a2b2e-126">-PassThru</span></span>
<span data-ttu-id="a2b2e-127">スナップインを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-127">Returns an object that represents the snap-in.</span></span>
<span data-ttu-id="a2b2e-128">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-128">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="a2b2e-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a2b2e-129">-Confirm</span></span>
<span data-ttu-id="a2b2e-130">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a2b2e-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a2b2e-131">-WhatIf</span></span>
<span data-ttu-id="a2b2e-132">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a2b2e-133">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a2b2e-134">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2b2e-134">CommonParameters</span></span>
<span data-ttu-id="a2b2e-135">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a2b2e-136">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a2b2e-137">入力</span><span class="sxs-lookup"><span data-stu-id="a2b2e-137">INPUTS</span></span>

### <span data-ttu-id="a2b2e-138">システム管理. PSSnapInInfo</span><span class="sxs-lookup"><span data-stu-id="a2b2e-138">System.Management.Automation.PSSnapInInfo</span></span>
<span data-ttu-id="a2b2e-139">パイプを使用して、このコマンドレットにスナップインオブジェクトをパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-139">You can pipe a snap-in object to this cmdlet.</span></span>

## <span data-ttu-id="a2b2e-140">出力</span><span class="sxs-lookup"><span data-stu-id="a2b2e-140">OUTPUTS</span></span>

### <span data-ttu-id="a2b2e-141">なし、システム管理. PSSnapInInfo</span><span class="sxs-lookup"><span data-stu-id="a2b2e-141">None, System.Management.Automation.PSSnapInInfo</span></span>
<span data-ttu-id="a2b2e-142">このコマンドレットは、 *PassThru* パラメーターを指定した場合に、スナップインを表す **system.string オブジェクトを** 生成します。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-142">This cmdlet generates a **System.Management.Automation.PSSnapInInfo** object that represents the snap-in, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="a2b2e-143">既定では、 **add-pssnapin** は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-143">By default, **Remove-PSSnapin** does not generate any output.</span></span>

## <span data-ttu-id="a2b2e-144">注</span><span class="sxs-lookup"><span data-stu-id="a2b2e-144">NOTES</span></span>

* <span data-ttu-id="a2b2e-145">**Add-pssnapin** は、セッションからスナップインを削除する前に、Windows PowerShell のバージョンを確認しません。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-145">**Remove-PSSnapin** does not check the version of Windows PowerShell before removing a snap-in from the session.</span></span> <span data-ttu-id="a2b2e-146">スナップインを削除できない場合は、警告が表示され、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-146">If a snap-in cannot be removed, a warning appears and the command fails.</span></span>
* <span data-ttu-id="a2b2e-147">**Add-pssnapin** は、現在のセッションのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-147">**Remove-PSSnapin** affects only the current session.</span></span> <span data-ttu-id="a2b2e-148">Add-PSSnapin コマンドを Windows PowerShell プロファイルに追加した場合は、コマンドを削除して、それ以降のセッションからスナップインを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-148">If you have added an Add-PSSnapin command to your Windows PowerShell profile, you should delete the command to remove the snap-in from future sessions.</span></span> <span data-ttu-id="a2b2e-149">手順については、「」と入力 `Get-Help about_Profiles` します。</span><span class="sxs-lookup"><span data-stu-id="a2b2e-149">For instructions, type `Get-Help about_Profiles`.</span></span>

## <span data-ttu-id="a2b2e-150">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a2b2e-150">RELATED LINKS</span></span>

[<span data-ttu-id="a2b2e-151">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="a2b2e-151">Add-PSSnapin</span></span>](Add-PSSnapin.md)

[<span data-ttu-id="a2b2e-152">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="a2b2e-152">Get-PSSnapin</span></span>](Get-PSSnapin.md)
