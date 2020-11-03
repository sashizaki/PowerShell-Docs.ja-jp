---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-alias?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Alias
ms.openlocfilehash: c9e6f844b25abe5f2a94aa929eeeb457efab3d44
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211176"
---
# <span data-ttu-id="4a199-103">New-Alias</span><span class="sxs-lookup"><span data-stu-id="4a199-103">New-Alias</span></span>

## <span data-ttu-id="4a199-104">概要</span><span class="sxs-lookup"><span data-stu-id="4a199-104">SYNOPSIS</span></span>
<span data-ttu-id="4a199-105">新しいエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a199-105">Creates a new alias.</span></span>

## <span data-ttu-id="4a199-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4a199-106">SYNTAX</span></span>

```
New-Alias [-Name] <String> [-Value] <String> [-Description <String>] [-Option <ScopedItemOptions>] [-PassThru]
 [-Scope <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4a199-107">Description</span><span class="sxs-lookup"><span data-stu-id="4a199-107">DESCRIPTION</span></span>

<span data-ttu-id="4a199-108">**新しい** alias コマンドレットは、現在の PowerShell セッションで新しいエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a199-108">The **New-Alias** cmdlet creates a new alias in the current PowerShell session.</span></span>
<span data-ttu-id="4a199-109">**新しいエイリアス** を使用して作成されたエイリアスは、セッションを終了した後、または PowerShell を閉じた後は保存されません。</span><span class="sxs-lookup"><span data-stu-id="4a199-109">Aliases created by using **New-Alias** are not saved after you exit the session or close PowerShell.</span></span>
<span data-ttu-id="4a199-110">Export-Alias コマンドレットを使用して、エイリアス情報をファイルに保存できます。</span><span class="sxs-lookup"><span data-stu-id="4a199-110">You can use the Export-Alias cmdlet to save your alias information to a file.</span></span>
<span data-ttu-id="4a199-111">後で、 **インポートエイリアス** を使用して、保存されたエイリアス情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4a199-111">You can later use **Import-Alias** to retrieve that saved alias information.</span></span>

## <span data-ttu-id="4a199-112">例</span><span class="sxs-lookup"><span data-stu-id="4a199-112">EXAMPLES</span></span>

### <span data-ttu-id="4a199-113">例 1: コマンドレットのエイリアスを作成する</span><span class="sxs-lookup"><span data-stu-id="4a199-113">Example 1: Create an alias for a cmdlet</span></span>

```
PS C:\> New-Alias -Name "List" Get-ChildItem
```

<span data-ttu-id="4a199-114">このコマンドは、Get-ChildItem コマンドレットを表す、alias という名前のエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a199-114">This command creates an alias named List to represent the Get-ChildItem cmdlet.</span></span>

### <span data-ttu-id="4a199-115">例 2: コマンドレットの読み取り専用エイリアスを作成する</span><span class="sxs-lookup"><span data-stu-id="4a199-115">Example 2: Create a read-only alias for a cmdlet</span></span>

```
PS C:\> New-Alias -Name "W" -Value Get-WmiObject -Description "quick wmi alias" -Option ReadOnly
PS C:\> Get-Alias -Name "W" | Format-List *
```

<span data-ttu-id="4a199-116">このコマンドは、Get-WmiObject コマンドレットを表す W という名前のエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a199-116">This command creates an alias named W to represent the Get-WmiObject cmdlet.</span></span>
<span data-ttu-id="4a199-117">エイリアスとして "クイック wmi エイリアス" という説明が作成され、読み取り専用になります。</span><span class="sxs-lookup"><span data-stu-id="4a199-117">It creates a description, quick wmi alias, for the alias and makes it read-only.</span></span>
<span data-ttu-id="4a199-118">コマンドの最後の行は、Get-Alias を使用して新しいエイリアスを取得し、パイプを使用して Format-List に渡します。これによりすべての情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a199-118">The last line of the command uses Get-Alias to get the new alias and pipes it to Format-List to display all of the information about it.</span></span>

## <span data-ttu-id="4a199-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4a199-119">PARAMETERS</span></span>

### <span data-ttu-id="4a199-120">-Description</span><span class="sxs-lookup"><span data-stu-id="4a199-120">-Description</span></span>

<span data-ttu-id="4a199-121">エイリアスの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a199-121">Specifies a description of the alias.</span></span>
<span data-ttu-id="4a199-122">任意の文字列を入力できます。</span><span class="sxs-lookup"><span data-stu-id="4a199-122">You can type any string.</span></span>
<span data-ttu-id="4a199-123">説明にスペースが含まれる場合は、二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="4a199-123">If the description includes spaces, enclose it in quotation marks.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4a199-124">-Force</span><span class="sxs-lookup"><span data-stu-id="4a199-124">-Force</span></span>

<span data-ttu-id="4a199-125">という名前のエイリアスが既に存在する場合に、コマンドレットが Set-Alias のように動作することを示します。</span><span class="sxs-lookup"><span data-stu-id="4a199-125">Indicates that the cmdlet acts like Set-Alias if the alias named already exists.</span></span>

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

### <span data-ttu-id="4a199-126">-Name</span><span class="sxs-lookup"><span data-stu-id="4a199-126">-Name</span></span>

<span data-ttu-id="4a199-127">新しいエイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a199-127">Specifies the new alias.</span></span>
<span data-ttu-id="4a199-128">エイリアス名には任意の英数字を使用できますが、最初の文字を数字にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4a199-128">You can use any alphanumeric characters in an alias, but the first character cannot be a number.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4a199-129">-Option</span><span class="sxs-lookup"><span data-stu-id="4a199-129">-Option</span></span>

<span data-ttu-id="4a199-130">エイリアスの **Options** プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a199-130">Specifies the value of the **Options** property of the alias.</span></span>
<span data-ttu-id="4a199-131">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4a199-131">Valid values are:</span></span>

- <span data-ttu-id="4a199-132">None: 別名には制約がありません (既定値)</span><span class="sxs-lookup"><span data-stu-id="4a199-132">None: The alias has no constraints (default value)</span></span>
- <span data-ttu-id="4a199-133">ReadOnly: エイリアスは削除できますが、 **Force** パラメーターを使用しない限り変更できません</span><span class="sxs-lookup"><span data-stu-id="4a199-133">ReadOnly: The alias can be deleted but cannot be changed except by using the **Force** parameter</span></span>
- <span data-ttu-id="4a199-134">定数: エイリアスを削除または変更することはできません</span><span class="sxs-lookup"><span data-stu-id="4a199-134">Constant: The alias cannot be deleted or changed</span></span>
- <span data-ttu-id="4a199-135">プライベート: エイリアスは現在のスコープでのみ使用できます</span><span class="sxs-lookup"><span data-stu-id="4a199-135">Private: The alias is available only in the current scope</span></span>
- <span data-ttu-id="4a199-136">AllScope: エイリアスは、作成された新しいスコープにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="4a199-136">AllScope: The alias is copied to any new scopes that are created</span></span>
- <span data-ttu-id="4a199-137">未指定: オプションが指定されていません</span><span class="sxs-lookup"><span data-stu-id="4a199-137">Unspecified: The option is not specified</span></span>

<span data-ttu-id="4a199-138">セッション内のすべてのエイリアスの **Options** プロパティを表示するには、「」と入力 `Get-Alias | Format-Table -Property Name, Options -AutoSize` します。</span><span class="sxs-lookup"><span data-stu-id="4a199-138">To see the **Options** property of all aliases in the session, type `Get-Alias | Format-Table -Property Name, Options -AutoSize`.</span></span>

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: [System.Management.Automation.ScopedItemOptions]::None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4a199-139">-PassThru</span><span class="sxs-lookup"><span data-stu-id="4a199-139">-PassThru</span></span>

<span data-ttu-id="4a199-140">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="4a199-140">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="4a199-141">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="4a199-141">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="4a199-142">-スコープ</span><span class="sxs-lookup"><span data-stu-id="4a199-142">-Scope</span></span>

<span data-ttu-id="4a199-143">新しいエイリアスのスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a199-143">Specifies the scope of the new alias.</span></span>
<span data-ttu-id="4a199-144">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4a199-144">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4a199-145">グローバル</span><span class="sxs-lookup"><span data-stu-id="4a199-145">Global</span></span>
- <span data-ttu-id="4a199-146">ローカル</span><span class="sxs-lookup"><span data-stu-id="4a199-146">Local</span></span>
- <span data-ttu-id="4a199-147">スクリプト</span><span class="sxs-lookup"><span data-stu-id="4a199-147">Script</span></span>
- <span data-ttu-id="4a199-148">現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1はその親)。</span><span class="sxs-lookup"><span data-stu-id="4a199-148">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>

<span data-ttu-id="4a199-149">既定値は Local です。</span><span class="sxs-lookup"><span data-stu-id="4a199-149">Local is the default.</span></span>
<span data-ttu-id="4a199-150">詳細については、「about_Scopes」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a199-150">For more information, see about_Scopes.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4a199-151">-Value</span><span class="sxs-lookup"><span data-stu-id="4a199-151">-Value</span></span>

<span data-ttu-id="4a199-152">エイリアスを作成するコマンドレットまたはコマンド要素の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a199-152">Specifies the name of the cmdlet or command element that is being aliased.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4a199-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4a199-153">-Confirm</span></span>

<span data-ttu-id="4a199-154">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a199-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4a199-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4a199-155">-WhatIf</span></span>

<span data-ttu-id="4a199-156">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="4a199-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4a199-157">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="4a199-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4a199-158">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a199-158">CommonParameters</span></span>

<span data-ttu-id="4a199-159">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4a199-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4a199-160">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a199-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4a199-161">入力</span><span class="sxs-lookup"><span data-stu-id="4a199-161">INPUTS</span></span>

### <span data-ttu-id="4a199-162">なし</span><span class="sxs-lookup"><span data-stu-id="4a199-162">None</span></span>

<span data-ttu-id="4a199-163">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="4a199-163">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="4a199-164">出力</span><span class="sxs-lookup"><span data-stu-id="4a199-164">OUTPUTS</span></span>

### <span data-ttu-id="4a199-165">None または system.servicemodel. エイリアス情報</span><span class="sxs-lookup"><span data-stu-id="4a199-165">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="4a199-166">*Passthru* パラメーターを使用すると、新しいエイリアスを表す system.string **オブジェクトが\*\*\*\*新しいエイリアス** によって生成されます。</span><span class="sxs-lookup"><span data-stu-id="4a199-166">When you use the *Passthru* parameter, **New-Alias** generates a **System.Management.Automation.AliasInfo** object representing the new alias.</span></span>
<span data-ttu-id="4a199-167">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="4a199-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="4a199-168">注</span><span class="sxs-lookup"><span data-stu-id="4a199-168">NOTES</span></span>

* <span data-ttu-id="4a199-169">新しい別名を作成するには、またはを使用し `Set-Alias` `New-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="4a199-169">To create a new alias, use `Set-Alias` or `New-Alias`.</span></span> <span data-ttu-id="4a199-170">エイリアスを変更するには、を使用 `Set-Alias` します。</span><span class="sxs-lookup"><span data-stu-id="4a199-170">To change an alias, use `Set-Alias`.</span></span> <span data-ttu-id="4a199-171">別名を削除するには、を使用 `Remove-Item` します。</span><span class="sxs-lookup"><span data-stu-id="4a199-171">To delete an alias, use `Remove-Item`.</span></span>

## <span data-ttu-id="4a199-172">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4a199-172">RELATED LINKS</span></span>

[<span data-ttu-id="4a199-173">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="4a199-173">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="4a199-174">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="4a199-174">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="4a199-175">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="4a199-175">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="4a199-176">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="4a199-176">Set-Alias</span></span>](Set-Alias.md)