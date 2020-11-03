---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-alias?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Alias
ms.openlocfilehash: 08ef751e0573f896c5f63737b00b55ab77ae73e3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216064"
---
# <span data-ttu-id="7afb9-103">Remove-Alias</span><span class="sxs-lookup"><span data-stu-id="7afb9-103">Remove-Alias</span></span>

## <span data-ttu-id="7afb9-104">概要</span><span class="sxs-lookup"><span data-stu-id="7afb9-104">SYNOPSIS</span></span>
<span data-ttu-id="7afb9-105">現在のセッションからエイリアスを削除します。</span><span class="sxs-lookup"><span data-stu-id="7afb9-105">Remove an alias from the current session.</span></span>

## <span data-ttu-id="7afb9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7afb9-106">SYNTAX</span></span>

### <span data-ttu-id="7afb9-107">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="7afb9-107">Default (Default)</span></span>

```
Remove-Alias [-Name] <String[]> [-Scope <String>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="7afb9-108">Description</span><span class="sxs-lookup"><span data-stu-id="7afb9-108">DESCRIPTION</span></span>

<span data-ttu-id="7afb9-109">コマンドレットでは、 `Remove-Alias` 現在の PowerShell セッションからエイリアスを削除します。</span><span class="sxs-lookup"><span data-stu-id="7afb9-109">The `Remove-Alias` cmdlet removes an alias from the current PowerShell session.</span></span> <span data-ttu-id="7afb9-110">**オプション** プロパティを **ReadOnly** に設定してエイリアスを削除するには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7afb9-110">To remove an alias with the **Option** property set to **ReadOnly** , use the **Force** parameter.</span></span>

<span data-ttu-id="7afb9-111">`Remove-Alias`コマンドレットは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7afb9-111">The `Remove-Alias` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="7afb9-112">例</span><span class="sxs-lookup"><span data-stu-id="7afb9-112">EXAMPLES</span></span>

### <span data-ttu-id="7afb9-113">例 1-エイリアスを削除する</span><span class="sxs-lookup"><span data-stu-id="7afb9-113">Example 1 - Remove an alias</span></span>

<span data-ttu-id="7afb9-114">この例で `del` は、コマンドレットを表すという名前のエイリアスを削除 `Remove-Item` します。</span><span class="sxs-lookup"><span data-stu-id="7afb9-114">This example removes an alias named `del` that represents the `Remove-Item` cmdlet.</span></span>

```powershell
Remove-Alias -Name del
```

### <span data-ttu-id="7afb9-115">例 2-すべての非定数エイリアスを削除する</span><span class="sxs-lookup"><span data-stu-id="7afb9-115">Example 2 - Remove all non-Constant aliases</span></span>

<span data-ttu-id="7afb9-116">この例では、 **Options** プロパティが **Constant** に設定されているエイリアスを除き、現在の PowerShell セッションからすべてのエイリアスを削除します。</span><span class="sxs-lookup"><span data-stu-id="7afb9-116">This example removes all aliases from the current PowerShell session, except for aliases with the **Options** property set to **Constant** .</span></span> <span data-ttu-id="7afb9-117">コマンドを実行すると、他の PowerShell セッションまたは新しい PowerShell セッションでエイリアスを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7afb9-117">After the command is run, the aliases are available in other PowerShell sessions or new PowerShell sessions.</span></span>

```powershell
Get-Alias | Where-Object { $_.Options -NE "Constant" } | Remove-Alias -Force
```

<span data-ttu-id="7afb9-118">`Get-Alias` PowerShell セッションのすべてのエイリアスを取得し、オブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="7afb9-118">`Get-Alias` gets all the aliases in the PowerShell session and sends the objects down the pipeline.</span></span>
<span data-ttu-id="7afb9-119">`Where-Object` はスクリプトブロックを使用し、自動変数 ( `$_` ) および **オプション** プロパティは現在のパイプラインオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="7afb9-119">`Where-Object` uses a script block, and the automatic variable (`$_`) and **Options** property represent the current pipeline object.</span></span> <span data-ttu-id="7afb9-120">**NE** (等しくない) パラメーターは、 **Options** 値が **Constant** に設定されていないオブジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="7afb9-120">The parameter **NE** (not equal), selects objects that don't have an **Options** value set to **Constant** .</span></span> <span data-ttu-id="7afb9-121">`Remove-Alias`**Force** パラメーターを使用して、PowerShell セッションから読み取り専用エイリアスを含むエイリアスを削除します。</span><span class="sxs-lookup"><span data-stu-id="7afb9-121">`Remove-Alias` uses the **Force** parameter to remove aliases, including read-only aliases, from the PowerShell session.</span></span>

## <span data-ttu-id="7afb9-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7afb9-122">PARAMETERS</span></span>

### <span data-ttu-id="7afb9-123">-Force</span><span class="sxs-lookup"><span data-stu-id="7afb9-123">-Force</span></span>

<span data-ttu-id="7afb9-124">コマンドレットによってエイリアスが削除されることを示します。これには、 **オプション** プロパティが **ReadOnly** に設定されているエイリアスも含まれます。</span><span class="sxs-lookup"><span data-stu-id="7afb9-124">Indicates that the cmdlet removes an alias, including aliases with the **Option** property set to **ReadOnly** .</span></span> <span data-ttu-id="7afb9-125">**Force** パラメーターは、 **Option** プロパティが **Constant** に設定されたエイリアスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="7afb9-125">The **Force** parameter can't remove an alias with an **Option** property set to **Constant** .</span></span>

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

### <span data-ttu-id="7afb9-126">-Name</span><span class="sxs-lookup"><span data-stu-id="7afb9-126">-Name</span></span>

<span data-ttu-id="7afb9-127">削除するエイリアスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7afb9-127">Specifies the name of the alias to remove.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7afb9-128">-スコープ</span><span class="sxs-lookup"><span data-stu-id="7afb9-128">-Scope</span></span>

<span data-ttu-id="7afb9-129">指定されたスコープのエイリアスのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="7afb9-129">Affects only the aliases in the specified scope.</span></span> <span data-ttu-id="7afb9-130">既定のスコープは **Local** です。</span><span class="sxs-lookup"><span data-stu-id="7afb9-130">The default scope is **Local** .</span></span> <span data-ttu-id="7afb9-131">詳細については、「 [about_Scopes](../microsoft.powershell.core/about/about_scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7afb9-131">For more information, see [about_Scopes](../microsoft.powershell.core/about/about_scopes.md).</span></span>

<span data-ttu-id="7afb9-132">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7afb9-132">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7afb9-133">グローバル</span><span class="sxs-lookup"><span data-stu-id="7afb9-133">Global</span></span>
- <span data-ttu-id="7afb9-134">ローカル</span><span class="sxs-lookup"><span data-stu-id="7afb9-134">Local</span></span>
- <span data-ttu-id="7afb9-135">スクリプト</span><span class="sxs-lookup"><span data-stu-id="7afb9-135">Script</span></span>
- <span data-ttu-id="7afb9-136">現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1はその親)</span><span class="sxs-lookup"><span data-stu-id="7afb9-136">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7afb9-137">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7afb9-137">CommonParameters</span></span>

<span data-ttu-id="7afb9-138">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7afb9-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7afb9-139">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7afb9-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7afb9-140">入力</span><span class="sxs-lookup"><span data-stu-id="7afb9-140">INPUTS</span></span>

### <span data-ttu-id="7afb9-141">System.String[]</span><span class="sxs-lookup"><span data-stu-id="7afb9-141">System.String[]</span></span>

<span data-ttu-id="7afb9-142">パイプを使用してエイリアスオブジェクトを **削除** することができます。</span><span class="sxs-lookup"><span data-stu-id="7afb9-142">You can pipe an alias object to **Remove-Alias** .</span></span>

## <span data-ttu-id="7afb9-143">出力</span><span class="sxs-lookup"><span data-stu-id="7afb9-143">OUTPUTS</span></span>

### <span data-ttu-id="7afb9-144">なし</span><span class="sxs-lookup"><span data-stu-id="7afb9-144">None</span></span>

<span data-ttu-id="7afb9-145">このコマンドレットは出力を返しません。</span><span class="sxs-lookup"><span data-stu-id="7afb9-145">This cmdlet doesn't return any output.</span></span>

## <span data-ttu-id="7afb9-146">注</span><span class="sxs-lookup"><span data-stu-id="7afb9-146">NOTES</span></span>

<span data-ttu-id="7afb9-147">変更は現在のスコープにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="7afb9-147">Changes only affect the current scope.</span></span> <span data-ttu-id="7afb9-148">すべてのセッションからエイリアスを削除するには、PowerShell プロファイルに **削除エイリアス** コマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="7afb9-148">To remove an alias from all sessions, add a **Remove-Alias** command to your PowerShell profile.</span></span>

<span data-ttu-id="7afb9-149">詳細については、「 [about_Aliases](../microsoft.powershell.core/about/about_aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7afb9-149">For more information, see [about_Aliases](../microsoft.powershell.core/about/about_aliases.md).</span></span>

## <span data-ttu-id="7afb9-150">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7afb9-150">RELATED LINKS</span></span>

[<span data-ttu-id="7afb9-151">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="7afb9-151">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="7afb9-152">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="7afb9-152">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="7afb9-153">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="7afb9-153">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="7afb9-154">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="7afb9-154">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="7afb9-155">New-Alias</span><span class="sxs-lookup"><span data-stu-id="7afb9-155">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="7afb9-156">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="7afb9-156">Set-Alias</span></span>](Set-Alias.md)

[<span data-ttu-id="7afb9-157">Where-Object</span><span class="sxs-lookup"><span data-stu-id="7afb9-157">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
