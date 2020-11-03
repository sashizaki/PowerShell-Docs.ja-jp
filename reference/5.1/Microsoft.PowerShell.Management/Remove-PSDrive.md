---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-psdrive?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSDrive
ms.openlocfilehash: 4b9b466be3d52877056b948e4cc373991784416a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214539"
---
# <span data-ttu-id="fdf7b-103">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="fdf7b-103">Remove-PSDrive</span></span>

## <span data-ttu-id="fdf7b-104">概要</span><span class="sxs-lookup"><span data-stu-id="fdf7b-104">SYNOPSIS</span></span>
<span data-ttu-id="fdf7b-105">一時 PowerShell ドライブを削除し、マップされたネットワークドライブを切断します。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-105">Deletes temporary PowerShell drives and disconnects mapped network drives.</span></span>

## <span data-ttu-id="fdf7b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fdf7b-106">SYNTAX</span></span>

### <span data-ttu-id="fdf7b-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="fdf7b-107">Name (Default)</span></span>

```
Remove-PSDrive [-Name] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="fdf7b-108">LiteralName</span><span class="sxs-lookup"><span data-stu-id="fdf7b-108">LiteralName</span></span>

```
Remove-PSDrive [-LiteralName] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="fdf7b-109">Description</span><span class="sxs-lookup"><span data-stu-id="fdf7b-109">DESCRIPTION</span></span>

<span data-ttu-id="fdf7b-110">コマンドレットでは `Remove-PSDrive` 、コマンドレットを使用して作成された一時 PowerShell ドライブを削除し `New-PSDrive` ます。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-110">The `Remove-PSDrive` cmdlet deletes temporary PowerShell drives that were created by using the `New-PSDrive` cmdlet.</span></span>

<span data-ttu-id="fdf7b-111">Windows PowerShell 3.0 以降では、は、 `Remove-PSDrive` のパラメーターを使用して作成されたドライブも含めて、マップされたネットワークドライブを切断し `Persist` `New-PSDrive` ます。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-111">Beginning in Windows PowerShell 3.0, `Remove-PSDrive` also disconnects mapped network drives, including, but not limited to, drives created by using the `Persist` parameter of `New-PSDrive`.</span></span>

<span data-ttu-id="fdf7b-112">`Remove-PSDrive` Windows 物理ドライブまたは論理ドライブを削除できません。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-112">`Remove-PSDrive` cannot delete Windows physical or logical drives.</span></span>

<span data-ttu-id="fdf7b-113">Windows PowerShell 3.0 以降では、外部ドライブがコンピューターに接続されている場合、PowerShell は新しいドライブを表す PSDrive をファイルシステムに自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-113">Beginning in Windows PowerShell 3.0, when an external drive is connected to the computer, PowerShell automatically adds a PSDrive to the file system that represents the new drive.</span></span>
<span data-ttu-id="fdf7b-114">PowerShell を再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-114">You do not need to restart PowerShell.</span></span>
<span data-ttu-id="fdf7b-115">同様に、外部ドライブがコンピューターから切断されると、PowerShell は、削除されたドライブを表す PSDrive を自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-115">Similarly, when an external drive is disconnected from the computer, PowerShell automatically deletes the PSDrive that represents the removed drive.</span></span>

## <span data-ttu-id="fdf7b-116">例</span><span class="sxs-lookup"><span data-stu-id="fdf7b-116">EXAMPLES</span></span>

### <span data-ttu-id="fdf7b-117">例 1: ファイルシステムドライブを削除する</span><span class="sxs-lookup"><span data-stu-id="fdf7b-117">Example 1: Remove a file system drive</span></span>

<span data-ttu-id="fdf7b-118">このコマンドは、"smp" という名前の一時ファイル システム ドライブを削除します。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-118">This command removes a temporary file system drive named "smp".</span></span>

```powershell
Remove-PSDrive -Name smp
```

### <span data-ttu-id="fdf7b-119">例 2: マップされたネットワークドライブを削除する</span><span class="sxs-lookup"><span data-stu-id="fdf7b-119">Example 2: Remove mapped network drives</span></span>

<span data-ttu-id="fdf7b-120">このコマンドは `Remove-PSDrive` 、を使用して、マップされた X: および S: ネットワークドライブを切断します。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-120">This command uses `Remove-PSDrive` to disconnect the X: and S: mapped network drives.</span></span>

```powershell
Get-PSDrive X, S | Remove-PSDrive
```

## <span data-ttu-id="fdf7b-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fdf7b-121">PARAMETERS</span></span>

### <span data-ttu-id="fdf7b-122">-Force</span><span class="sxs-lookup"><span data-stu-id="fdf7b-122">-Force</span></span>

<span data-ttu-id="fdf7b-123">現在の PowerShell ドライブを削除します。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-123">Removes the current PowerShell drive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fdf7b-124">-LiteralName</span><span class="sxs-lookup"><span data-stu-id="fdf7b-124">-LiteralName</span></span>

<span data-ttu-id="fdf7b-125">ドライブの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-125">Specifies the name of the drive.</span></span>

<span data-ttu-id="fdf7b-126">**LiteralName** の値は、入力した内容のまま使用されます。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-126">The value of **LiteralName** is used exactly as typed.</span></span>
<span data-ttu-id="fdf7b-127">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-127">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="fdf7b-128">名前にエスケープ文字が含まれている場合は、単一引用符 (') で囲みます。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-128">If the name includes escape characters, enclose it in single quotation marks (').</span></span>
<span data-ttu-id="fdf7b-129">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-129">Single quotation marks instruct PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fdf7b-130">-Name</span><span class="sxs-lookup"><span data-stu-id="fdf7b-130">-Name</span></span>

<span data-ttu-id="fdf7b-131">削除するドライブの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-131">Specifies the names of the drives to remove.</span></span>
<span data-ttu-id="fdf7b-132">ドライブ名の後にコロン (:) を入力しないでください。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-132">Do not type a colon (:) after the drive name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="fdf7b-133">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="fdf7b-133">-PSProvider</span></span>

<span data-ttu-id="fdf7b-134">**Psprovider** オブジェクトの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-134">Specifies an array of **PSProvider** objects.</span></span>
<span data-ttu-id="fdf7b-135">このコマンドレットは、指定された PowerShell プロバイダーに関連付けられているすべてのドライブを削除し、切断します。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-135">This cmdlet removes and disconnects all of the drives associated with the specified PowerShell provider.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fdf7b-136">-スコープ</span><span class="sxs-lookup"><span data-stu-id="fdf7b-136">-Scope</span></span>

<span data-ttu-id="fdf7b-137">ドライブのスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-137">Specifies a scope for the drive.</span></span>
<span data-ttu-id="fdf7b-138">このパラメーターに指定できる値は、Global、Local、および Script、または現在のスコープを基準とする数値です。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-138">The acceptable values for this parameter are: Global, Local, and Script, or a number relative to the current scope.</span></span> <span data-ttu-id="fdf7b-139">スコープは、スコープの数から0までの範囲です。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-139">Scopes number 0 through the number of scopes.</span></span> <span data-ttu-id="fdf7b-140">現在のスコープ番号は0で、その親は1です。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-140">The current scope number is 0 and its parent is 1.</span></span>
<span data-ttu-id="fdf7b-141">詳細については、「 [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-141">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fdf7b-142">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="fdf7b-142">-UseTransaction</span></span>

<span data-ttu-id="fdf7b-143">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-143">Includes the command in the active transaction.</span></span>
<span data-ttu-id="fdf7b-144">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-144">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="fdf7b-145">詳細については、「about_Transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-145">For more information, see about_Transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fdf7b-146">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fdf7b-146">-Confirm</span></span>

<span data-ttu-id="fdf7b-147">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-147">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fdf7b-148">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fdf7b-148">-WhatIf</span></span>

<span data-ttu-id="fdf7b-149">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-149">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="fdf7b-150">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-150">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fdf7b-151">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fdf7b-151">CommonParameters</span></span>

<span data-ttu-id="fdf7b-152">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-152">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fdf7b-153">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-153">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="fdf7b-154">入力</span><span class="sxs-lookup"><span data-stu-id="fdf7b-154">INPUTS</span></span>

### <span data-ttu-id="fdf7b-155">System.Management.Automation.PSDriveInfo</span><span class="sxs-lookup"><span data-stu-id="fdf7b-155">System.Management.Automation.PSDriveInfo</span></span>

<span data-ttu-id="fdf7b-156">パイプを使用して、コマンドレットなどのドライブオブジェクトを `Get-PSDrive` `Remove-PSDrive` コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-156">You can pipe a drive object, such as one from the `Get-PSDrive` cmdlet, to the `Remove-PSDrive` cmdlet.</span></span>

## <span data-ttu-id="fdf7b-157">出力</span><span class="sxs-lookup"><span data-stu-id="fdf7b-157">OUTPUTS</span></span>

### <span data-ttu-id="fdf7b-158">なし</span><span class="sxs-lookup"><span data-stu-id="fdf7b-158">None</span></span>

<span data-ttu-id="fdf7b-159">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-159">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="fdf7b-160">注</span><span class="sxs-lookup"><span data-stu-id="fdf7b-160">NOTES</span></span>

- <span data-ttu-id="fdf7b-161">`Remove-PSDrive`コマンドレットは、PowerShell プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-161">The `Remove-PSDrive` cmdlet is designed to work with the data exposed by any PowerShell provider.</span></span> <span data-ttu-id="fdf7b-162">セッションのプロバイダーの一覧を表示するには、`Get-PSProvider` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-162">To list the providers in your session, use the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="fdf7b-163">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdf7b-163">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="fdf7b-164">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fdf7b-164">RELATED LINKS</span></span>

[<span data-ttu-id="fdf7b-165">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="fdf7b-165">Get-PSDrive</span></span>](Get-PSDrive.md)

[<span data-ttu-id="fdf7b-166">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="fdf7b-166">New-PSDrive</span></span>](New-PSDrive.md)

[<span data-ttu-id="fdf7b-167">about_Providers</span><span class="sxs-lookup"><span data-stu-id="fdf7b-167">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
