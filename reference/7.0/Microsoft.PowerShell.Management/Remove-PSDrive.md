---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-psdrive?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSDrive
ms.openlocfilehash: 2b5508899b61ac5460c5ce06aa7521be50c0f2d4
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209755"
---
# <span data-ttu-id="39573-103">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="39573-103">Remove-PSDrive</span></span>

## <span data-ttu-id="39573-104">概要</span><span class="sxs-lookup"><span data-stu-id="39573-104">SYNOPSIS</span></span>
<span data-ttu-id="39573-105">一時 PowerShell ドライブを削除し、マップされたネットワークドライブを切断します。</span><span class="sxs-lookup"><span data-stu-id="39573-105">Deletes temporary PowerShell drives and disconnects mapped network drives.</span></span>

## <span data-ttu-id="39573-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="39573-106">SYNTAX</span></span>

### <span data-ttu-id="39573-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="39573-107">Name (Default)</span></span>

```
Remove-PSDrive [-Name] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="39573-108">LiteralName</span><span class="sxs-lookup"><span data-stu-id="39573-108">LiteralName</span></span>

```
Remove-PSDrive [-LiteralName] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="39573-109">Description</span><span class="sxs-lookup"><span data-stu-id="39573-109">DESCRIPTION</span></span>

<span data-ttu-id="39573-110">コマンドレットでは `Remove-PSDrive` 、コマンドレットを使用して作成された一時 PowerShell ドライブを削除し `New-PSDrive` ます。</span><span class="sxs-lookup"><span data-stu-id="39573-110">The `Remove-PSDrive` cmdlet deletes temporary PowerShell drives that were created by using the `New-PSDrive` cmdlet.</span></span>

<span data-ttu-id="39573-111">Windows PowerShell 3.0 以降では、は、 `Remove-PSDrive` のパラメーターを使用して作成されたドライブも含めて、マップされたネットワークドライブを切断し `Persist` `New-PSDrive` ます。</span><span class="sxs-lookup"><span data-stu-id="39573-111">Beginning in Windows PowerShell 3.0, `Remove-PSDrive` also disconnects mapped network drives, including, but not limited to, drives created by using the `Persist` parameter of `New-PSDrive`.</span></span>

<span data-ttu-id="39573-112">`Remove-PSDrive` Windows 物理ドライブまたは論理ドライブを削除できません。</span><span class="sxs-lookup"><span data-stu-id="39573-112">`Remove-PSDrive` cannot delete Windows physical or logical drives.</span></span>

<span data-ttu-id="39573-113">Windows PowerShell 3.0 以降では、外部ドライブがコンピューターに接続されている場合、PowerShell は新しいドライブを表す PSDrive をファイルシステムに自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="39573-113">Beginning in Windows PowerShell 3.0, when an external drive is connected to the computer, PowerShell automatically adds a PSDrive to the file system that represents the new drive.</span></span>
<span data-ttu-id="39573-114">PowerShell を再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="39573-114">You do not need to restart PowerShell.</span></span>
<span data-ttu-id="39573-115">同様に、外部ドライブがコンピューターから切断されると、PowerShell は、削除されたドライブを表す PSDrive を自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="39573-115">Similarly, when an external drive is disconnected from the computer, PowerShell automatically deletes the PSDrive that represents the removed drive.</span></span>

## <span data-ttu-id="39573-116">例</span><span class="sxs-lookup"><span data-stu-id="39573-116">EXAMPLES</span></span>

### <span data-ttu-id="39573-117">例 1: ファイルシステムドライブを削除する</span><span class="sxs-lookup"><span data-stu-id="39573-117">Example 1: Remove a file system drive</span></span>

<span data-ttu-id="39573-118">このコマンドは、"smp" という名前の一時ファイル システム ドライブを削除します。</span><span class="sxs-lookup"><span data-stu-id="39573-118">This command removes a temporary file system drive named "smp".</span></span>

```powershell
Remove-PSDrive -Name smp
```

### <span data-ttu-id="39573-119">例 2: マップされたネットワークドライブを削除する</span><span class="sxs-lookup"><span data-stu-id="39573-119">Example 2: Remove mapped network drives</span></span>

<span data-ttu-id="39573-120">このコマンドは `Remove-PSDrive` 、を使用して、マップされた X: および S: ネットワークドライブを切断します。</span><span class="sxs-lookup"><span data-stu-id="39573-120">This command uses `Remove-PSDrive` to disconnect the X: and S: mapped network drives.</span></span>

```powershell
Get-PSDrive X, S | Remove-PSDrive
```

## <span data-ttu-id="39573-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="39573-121">PARAMETERS</span></span>

### <span data-ttu-id="39573-122">-Force</span><span class="sxs-lookup"><span data-stu-id="39573-122">-Force</span></span>

<span data-ttu-id="39573-123">現在の PowerShell ドライブを削除します。</span><span class="sxs-lookup"><span data-stu-id="39573-123">Removes the current PowerShell drive.</span></span>

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

### <span data-ttu-id="39573-124">-LiteralName</span><span class="sxs-lookup"><span data-stu-id="39573-124">-LiteralName</span></span>

<span data-ttu-id="39573-125">ドライブの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="39573-125">Specifies the name of the drive.</span></span>

<span data-ttu-id="39573-126">**LiteralName** の値は、入力した内容のまま使用されます。</span><span class="sxs-lookup"><span data-stu-id="39573-126">The value of **LiteralName** is used exactly as typed.</span></span>
<span data-ttu-id="39573-127">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="39573-127">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="39573-128">名前にエスケープ文字が含まれている場合は、単一引用符 (') で囲みます。</span><span class="sxs-lookup"><span data-stu-id="39573-128">If the name includes escape characters, enclose it in single quotation marks (').</span></span>
<span data-ttu-id="39573-129">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="39573-129">Single quotation marks instruct PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="39573-130">-Name</span><span class="sxs-lookup"><span data-stu-id="39573-130">-Name</span></span>

<span data-ttu-id="39573-131">削除するドライブの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="39573-131">Specifies the names of the drives to remove.</span></span>
<span data-ttu-id="39573-132">ドライブ名の後にコロン (:) を入力しないでください。</span><span class="sxs-lookup"><span data-stu-id="39573-132">Do not type a colon (:) after the drive name.</span></span>

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

### <span data-ttu-id="39573-133">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="39573-133">-PSProvider</span></span>

<span data-ttu-id="39573-134">**Psprovider** オブジェクトの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="39573-134">Specifies an array of **PSProvider** objects.</span></span>
<span data-ttu-id="39573-135">このコマンドレットは、指定された PowerShell プロバイダーに関連付けられているすべてのドライブを削除し、切断します。</span><span class="sxs-lookup"><span data-stu-id="39573-135">This cmdlet removes and disconnects all of the drives associated with the specified PowerShell provider.</span></span>

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

### <span data-ttu-id="39573-136">-スコープ</span><span class="sxs-lookup"><span data-stu-id="39573-136">-Scope</span></span>

<span data-ttu-id="39573-137">ドライブのスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="39573-137">Specifies a scope for the drive.</span></span>
<span data-ttu-id="39573-138">このパラメーターに指定できる値は、Global、Local、および Script、または現在のスコープを基準とする数値です。</span><span class="sxs-lookup"><span data-stu-id="39573-138">The acceptable values for this parameter are: Global, Local, and Script, or a number relative to the current scope.</span></span> <span data-ttu-id="39573-139">スコープは、スコープの数から0までの範囲です。</span><span class="sxs-lookup"><span data-stu-id="39573-139">Scopes number 0 through the number of scopes.</span></span> <span data-ttu-id="39573-140">現在のスコープ番号は0で、その親は1です。</span><span class="sxs-lookup"><span data-stu-id="39573-140">The current scope number is 0 and its parent is 1.</span></span>
<span data-ttu-id="39573-141">詳細については、「 [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39573-141">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="39573-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="39573-142">-Confirm</span></span>

<span data-ttu-id="39573-143">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39573-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="39573-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="39573-144">-WhatIf</span></span>

<span data-ttu-id="39573-145">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="39573-145">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="39573-146">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="39573-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="39573-147">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="39573-147">CommonParameters</span></span>

<span data-ttu-id="39573-148">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="39573-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="39573-149">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39573-149">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="39573-150">入力</span><span class="sxs-lookup"><span data-stu-id="39573-150">INPUTS</span></span>

### <span data-ttu-id="39573-151">System.Management.Automation.PSDriveInfo</span><span class="sxs-lookup"><span data-stu-id="39573-151">System.Management.Automation.PSDriveInfo</span></span>

<span data-ttu-id="39573-152">パイプを使用して、コマンドレットなどのドライブオブジェクトを `Get-PSDrive` `Remove-PSDrive` コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="39573-152">You can pipe a drive object, such as one from the `Get-PSDrive` cmdlet, to the `Remove-PSDrive` cmdlet.</span></span>

## <span data-ttu-id="39573-153">出力</span><span class="sxs-lookup"><span data-stu-id="39573-153">OUTPUTS</span></span>

### <span data-ttu-id="39573-154">なし</span><span class="sxs-lookup"><span data-stu-id="39573-154">None</span></span>

<span data-ttu-id="39573-155">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="39573-155">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="39573-156">注</span><span class="sxs-lookup"><span data-stu-id="39573-156">NOTES</span></span>

- <span data-ttu-id="39573-157">`Remove-PSDrive`コマンドレットは、PowerShell プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="39573-157">The `Remove-PSDrive` cmdlet is designed to work with the data exposed by any PowerShell provider.</span></span> <span data-ttu-id="39573-158">セッションのプロバイダーの一覧を表示するには、`Get-PSProvider` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="39573-158">To list the providers in your session, use the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="39573-159">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39573-159">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="39573-160">関連リンク</span><span class="sxs-lookup"><span data-stu-id="39573-160">RELATED LINKS</span></span>

[<span data-ttu-id="39573-161">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="39573-161">Get-PSDrive</span></span>](Get-PSDrive.md)

[<span data-ttu-id="39573-162">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="39573-162">New-PSDrive</span></span>](New-PSDrive.md)

[<span data-ttu-id="39573-163">about_Providers</span><span class="sxs-lookup"><span data-stu-id="39573-163">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)