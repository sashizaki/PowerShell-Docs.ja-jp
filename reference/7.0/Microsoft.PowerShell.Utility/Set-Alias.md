---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 2/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-alias?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Alias
ms.openlocfilehash: 86eff41bc9784627db82689108d01cbd71840e77
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209923"
---
# <span data-ttu-id="6256d-103">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="6256d-103">Set-Alias</span></span>

## <span data-ttu-id="6256d-104">概要</span><span class="sxs-lookup"><span data-stu-id="6256d-104">SYNOPSIS</span></span>
<span data-ttu-id="6256d-105">現在の PowerShell セッションで、コマンドレットまたはその他のコマンドのエイリアスを作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="6256d-105">Creates or changes an alias for a cmdlet or other command in the current PowerShell session.</span></span>

## <span data-ttu-id="6256d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6256d-106">SYNTAX</span></span>

### <span data-ttu-id="6256d-107">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="6256d-107">Default (Default)</span></span>

```
Set-Alias [-Name] <string> [-Value] <string> [-Description <string>] [-Option <ScopedItemOptions>]
 [-PassThru] [-Scope <string>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6256d-108">Description</span><span class="sxs-lookup"><span data-stu-id="6256d-108">DESCRIPTION</span></span>

<span data-ttu-id="6256d-109">コマンドレットは、コマンド `Set-Alias` レットまたはコマンド (関数、スクリプト、ファイル、その他の実行可能ファイルなど) のエイリアスを作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="6256d-109">The `Set-Alias` cmdlet creates or changes an alias for a cmdlet or a command, such as a function, script, file, or other executable.</span></span> <span data-ttu-id="6256d-110">エイリアスは、コマンドレットまたはコマンドを参照する代替名です。</span><span class="sxs-lookup"><span data-stu-id="6256d-110">An alias is an alternate name that refers to a cmdlet or command.</span></span>
<span data-ttu-id="6256d-111">たとえば、 `sal` はコマンドレットのエイリアスです `Set-Alias` 。</span><span class="sxs-lookup"><span data-stu-id="6256d-111">For example, `sal` is the alias for the `Set-Alias` cmdlet.</span></span> <span data-ttu-id="6256d-112">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6256d-112">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="6256d-113">コマンドレットは複数のエイリアスを持つことができますが、エイリアスは1つのコマンドレットにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="6256d-113">A cmdlet can have multiple aliases, but an alias can only be associated with one cmdlet.</span></span> <span data-ttu-id="6256d-114">を使用すると、 `Set-Alias` 既存のエイリアスを別のコマンドレットに再割り当てしたり、説明などのエイリアスのプロパティを変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="6256d-114">You can use `Set-Alias` to reassign an existing alias to another cmdlet, or change an alias's properties, such as the description.</span></span>

<span data-ttu-id="6256d-115">によって作成または変更されたエイリアス `Set-Alias` は永続的ではなく、現在の PowerShell セッション中にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6256d-115">An alias that is created or changed by `Set-Alias` is not permanent and is only available during the current PowerShell session.</span></span> <span data-ttu-id="6256d-116">PowerShell セッションが終了すると、エイリアスは削除されます。</span><span class="sxs-lookup"><span data-stu-id="6256d-116">When the PowerShell session is closed, the alias is removed.</span></span>

## <span data-ttu-id="6256d-117">例</span><span class="sxs-lookup"><span data-stu-id="6256d-117">EXAMPLES</span></span>

### <span data-ttu-id="6256d-118">例 1: コマンドレットのエイリアスを作成する</span><span class="sxs-lookup"><span data-stu-id="6256d-118">Example 1: Create an alias for a cmdlet</span></span>

<span data-ttu-id="6256d-119">このコマンドは、現在の PowerShell セッションのコマンドレットのエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6256d-119">This command creates an alias to a cmdlet in the current PowerShell session.</span></span>

```
PS> Set-Alias -Name list -Value Get-ChildItem

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem
```

<span data-ttu-id="6256d-120">コマンドレットにより、 `Set-Alias` 現在の PowerShell セッションにエイリアスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6256d-120">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="6256d-121">**Name** パラメーターは、エイリアスの名前を指定し `list` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-121">The **Name** parameter specifies the alias's name, `list`.</span></span> <span data-ttu-id="6256d-122">**値** パラメーターは、エイリアスが実行されるコマンドレットを指定します。</span><span class="sxs-lookup"><span data-stu-id="6256d-122">The **Value** parameter specifies the cmdlet that the alias runs.</span></span>

<span data-ttu-id="6256d-123">エイリアスを実行するには、PowerShell コマンドラインで「」と入力し `list` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-123">To run the alias, type `list` on the PowerShell command line.</span></span>

### <span data-ttu-id="6256d-124">例 2: 既存のエイリアスを別のコマンドレットに再割り当てする</span><span class="sxs-lookup"><span data-stu-id="6256d-124">Example 2: Reassign an existing alias to a different cmdlet</span></span>

<span data-ttu-id="6256d-125">このコマンドは、既存のエイリアスを再割り当てして別のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="6256d-125">This command reassigns an existing alias to run a different cmdlet.</span></span>

```
PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem

PS> Set-Alias -Name list -Value Get-Location

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-Location
```

<span data-ttu-id="6256d-126">コマンドレットでは、 `Get-Alias` **Name** パラメーターを使用して別名を表示し `list` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-126">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="6256d-127">`list`エイリアスは、コマンドレットに関連付けられてい `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-127">The `list` alias is associated with the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="6256d-128">エイリアスを実行すると、 `list` 現在のディレクトリ内の項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6256d-128">When the `list` alias is run, the items in the current directory are displayed.</span></span>

<span data-ttu-id="6256d-129">コマンドレットでは、 `Set-Alias` **Name** パラメーターを使用してエイリアスを指定し `list` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-129">The `Set-Alias` cmdlet uses the **Name** parameter to specify the `list` alias.</span></span> <span data-ttu-id="6256d-130">**Value** パラメーターによって、エイリアスがコマンドレットに関連付けられ `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-130">The **Value** parameter associates the alias to the `Get-Location` cmdlet.</span></span>

<span data-ttu-id="6256d-131">コマンドレットでは、 `Get-Alias` **Name** パラメーターを使用して別名を表示し `list` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-131">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="6256d-132">`list`エイリアスは、コマンドレットに関連付けられてい `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-132">The `list` alias is associated with the `Get-Location` cmdlet.</span></span> <span data-ttu-id="6256d-133">エイリアスを実行すると、 `list` 現在のディレクトリの場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6256d-133">When the `list` alias is run, the current directory's location is displayed.</span></span>

### <span data-ttu-id="6256d-134">例 3: 読み取り専用のエイリアスを作成して変更する</span><span class="sxs-lookup"><span data-stu-id="6256d-134">Example 3: Create and change a read-only alias</span></span>

<span data-ttu-id="6256d-135">このコマンドは、読み取り専用のエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6256d-135">This command creates a read-only alias.</span></span> <span data-ttu-id="6256d-136">読み取り専用オプションを指定すると、エイリアスが意図せず変更されるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="6256d-136">The read-only option prevents unintended changes to an alias.</span></span> <span data-ttu-id="6256d-137">読み取り専用エイリアスを変更または削除するには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6256d-137">To change or delete a read-only alias, use the **Force** parameter.</span></span>

```
PS> Set-Alias -Name loc -Value Get-Location -Option ReadOnly -PassThru | Format-List -Property *

DisplayName         : loc -> Get-Location
Definition          : Get-Location
Options             : ReadOnly
Description         :
Name                : loc
CommandType         : Alias

PS> Set-Alias -Name loc -Value Get-Location -Option ReadOnly -Description 'Displays the current directory' -Force -PassThru | Format-List -Property *

DisplayName         : loc -> Get-Location
Definition          : Get-Location
Options             : ReadOnly
Description         : Displays the current directory
Name                : loc
CommandType         : Alias
```

<span data-ttu-id="6256d-138">コマンドレットにより、 `Set-Alias` 現在の PowerShell セッションにエイリアスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6256d-138">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="6256d-139">**Name** パラメーターは、エイリアスの名前を指定し `loc` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-139">The **Name** parameter specifies the alias's name, `loc`.</span></span> <span data-ttu-id="6256d-140">**値** パラメーターは、 `Get-Location` エイリアスが実行されるコマンドレットを指定します。</span><span class="sxs-lookup"><span data-stu-id="6256d-140">The **Value** parameter specifies the `Get-Location` cmdlet that the alias runs.</span></span> <span data-ttu-id="6256d-141">**オプション** パラメーターは、 **ReadOnly** 値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6256d-141">The **Option** parameter specifies the **ReadOnly** value.</span></span> <span data-ttu-id="6256d-142">**PassThru** パラメーターは alias オブジェクトを表し、オブジェクトをパイプラインの下にあるオブジェクトをコマンドレットに送信し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-142">The **PassThru** parameter represents the alias object and sends the object down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="6256d-143">`Format-List`**プロパティパラメーターを** アスタリスク () と共に使用して `*` 、すべてのプロパティが表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="6256d-143">`Format-List` uses the **Property** parameter with an asterisk (`*`) so that all of the properties are displayed.</span></span> <span data-ttu-id="6256d-144">出力例では、これらのプロパティの部分的なリストを示しています。</span><span class="sxs-lookup"><span data-stu-id="6256d-144">The example output shows a partial list of those properties.</span></span>

<span data-ttu-id="6256d-145">`loc`2 つのパラメーターを追加することで、別名が変更されます。</span><span class="sxs-lookup"><span data-stu-id="6256d-145">The `loc` alias is changed with the addition of two parameters.</span></span> <span data-ttu-id="6256d-146">**説明** エイリアスの目的を説明するテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="6256d-146">**Description** adds text to explain the alias's purpose.</span></span> <span data-ttu-id="6256d-147">エイリアスは読み取り専用であるため、 **Force** パラメーターが必要です `loc` 。</span><span class="sxs-lookup"><span data-stu-id="6256d-147">The **Force** parameter is needed because the `loc` alias is read-only.</span></span> <span data-ttu-id="6256d-148">**Force** パラメーターが使用されていない場合、変更は失敗します。</span><span class="sxs-lookup"><span data-stu-id="6256d-148">If the **Force** parameter is not used, the change fails.</span></span>

### <span data-ttu-id="6256d-149">例 4: 実行可能ファイルのエイリアスを作成する</span><span class="sxs-lookup"><span data-stu-id="6256d-149">Example 4: Create an alias to an executable file</span></span>

<span data-ttu-id="6256d-150">この例では、ローカルコンピューター上の実行可能ファイルのエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6256d-150">This example creates an alias to an executable file on the local computer.</span></span>

```
PS> Set-Alias -Name np -Value C:\Windows\notepad.exe

PS> Get-Alias -Name np

CommandType     Name
-----------     ----
Alias           np -> notepad.exe
```

<span data-ttu-id="6256d-151">コマンドレットにより、 `Set-Alias` 現在の PowerShell セッションにエイリアスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6256d-151">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="6256d-152">**Name** パラメーターは、エイリアスの名前を指定し `np` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-152">The **Name** parameter specifies the alias's name, `np`.</span></span> <span data-ttu-id="6256d-153">**Value** パラメーターには **C:\Windows\notepad.exe** パスとアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="6256d-153">The **Value** parameter specifies the path and application name **C:\Windows\notepad.exe** .</span></span> <span data-ttu-id="6256d-154">この `Get-Alias` コマンドレットでは、 **Name** パラメーターを使用して、 `np` エイリアスが **notepad.exe** に関連付けられていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="6256d-154">The `Get-Alias` cmdlet uses the **Name** parameter to show that the `np` alias is associated with **notepad.exe** .</span></span>

<span data-ttu-id="6256d-155">エイリアスを実行するには、PowerShell コマンドラインで「」と入力して `np` **notepad.exe** を開きます。</span><span class="sxs-lookup"><span data-stu-id="6256d-155">To run the alias, type `np` on the PowerShell command line to open **notepad.exe** .</span></span>

### <span data-ttu-id="6256d-156">例 5: パラメーターを使用してコマンドのエイリアスを作成する</span><span class="sxs-lookup"><span data-stu-id="6256d-156">Example 5: Create an alias for a command with parameters</span></span>

<span data-ttu-id="6256d-157">この例では、パラメーターを使用して、コマンドにエイリアスを割り当てる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6256d-157">This example shows how to assign an alias to a command with parameters.</span></span>

<span data-ttu-id="6256d-158">などのコマンドレットのエイリアスを作成でき `Set-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-158">You can create an alias for a cmdlet, such as `Set-Location`.</span></span> <span data-ttu-id="6256d-159">などのパラメーターと値を使用して、コマンドのエイリアスを作成することはできません `Set-Location -Path C:\Windows\System32` 。</span><span class="sxs-lookup"><span data-stu-id="6256d-159">You cannot create an alias for a command with parameters and values, such as `Set-Location -Path C:\Windows\System32`.</span></span> <span data-ttu-id="6256d-160">コマンドのエイリアスを作成するには、コマンドを含む関数を作成し、その関数のエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6256d-160">To create an alias for a command, create a function that includes the command, and then create an alias to the function.</span></span> <span data-ttu-id="6256d-161">詳細については、「 [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6256d-161">For more information, see [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).</span></span>

```
PS> Function CD32 {Set-Location -Path C:\Windows\System32}

PS> Set-Alias -Name Go -Value CD32
```

<span data-ttu-id="6256d-162">という名前 `CD32` の関数が作成されます。</span><span class="sxs-lookup"><span data-stu-id="6256d-162">A function named `CD32` is created.</span></span> <span data-ttu-id="6256d-163">関数は、 `Set-Location` **Path** パラメーターを指定したコマンドレットを使用して、 **C:\Windows\System32** ディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="6256d-163">The function uses the `Set-Location` cmdlet with the **Path** parameter to specify the directory, **C:\Windows\System32** .</span></span>

<span data-ttu-id="6256d-164">コマンドレットにより、 `Set-Alias` 現在の PowerShell セッションの関数のエイリアスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6256d-164">The `Set-Alias` cmdlet creates an alias to the function in the current PowerShell session.</span></span> <span data-ttu-id="6256d-165">**Name** パラメーターは、エイリアスの名前を指定し `Go` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-165">The **Name** parameter specifies the alias's name, `Go`.</span></span> <span data-ttu-id="6256d-166">**Value** パラメーターは、関数の名前を指定し `CD32` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-166">The **Value** parameter specifies the function's name, `CD32`.</span></span>

<span data-ttu-id="6256d-167">エイリアスを実行するには、PowerShell コマンドラインで「」と入力し `Go` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-167">To run the alias, type `Go` on the PowerShell command line.</span></span> <span data-ttu-id="6256d-168">関数が実行され、 `CD32` ディレクトリ **C:\Windows\System32** に変更されます。</span><span class="sxs-lookup"><span data-stu-id="6256d-168">The `CD32` function runs and changes to the directory **C:\Windows\System32** .</span></span>

## <span data-ttu-id="6256d-169">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6256d-169">PARAMETERS</span></span>

### <span data-ttu-id="6256d-170">-Description</span><span class="sxs-lookup"><span data-stu-id="6256d-170">-Description</span></span>

<span data-ttu-id="6256d-171">エイリアスの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="6256d-171">Specifies a description of the alias.</span></span> <span data-ttu-id="6256d-172">任意の文字列を入力できます。</span><span class="sxs-lookup"><span data-stu-id="6256d-172">You can type any string.</span></span> <span data-ttu-id="6256d-173">説明にスペースが含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="6256d-173">If the description includes spaces, enclose it single quotation marks.</span></span>

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

### <span data-ttu-id="6256d-174">-Force</span><span class="sxs-lookup"><span data-stu-id="6256d-174">-Force</span></span>

<span data-ttu-id="6256d-175">**Force** パラメーターを使用して、 **オプション** パラメーターが **ReadOnly** に設定されているエイリアスを変更または削除します。</span><span class="sxs-lookup"><span data-stu-id="6256d-175">Use the **Force** parameter to change or delete an alias that has the **Option** parameter set to **ReadOnly** .</span></span>

<span data-ttu-id="6256d-176">**Force** パラメーターは、 **Option** パラメーターを **Constant** に設定してエイリアスを変更または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="6256d-176">The **Force** parameter cannot change or delete an alias with the **Option** parameter set to **Constant** .</span></span>

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

### <span data-ttu-id="6256d-177">-Name</span><span class="sxs-lookup"><span data-stu-id="6256d-177">-Name</span></span>

<span data-ttu-id="6256d-178">新しいエイリアスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6256d-178">Specifies the name of a new alias.</span></span> <span data-ttu-id="6256d-179">エイリアス名には、英数字とハイフンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6256d-179">An alias name can contain alphanumeric characters and hyphens.</span></span> <span data-ttu-id="6256d-180">エイリアス名には、123などの数値を指定できません。</span><span class="sxs-lookup"><span data-stu-id="6256d-180">Alias names cannot be numeric, such as 123.</span></span>

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

### <span data-ttu-id="6256d-181">-Option</span><span class="sxs-lookup"><span data-stu-id="6256d-181">-Option</span></span>

<span data-ttu-id="6256d-182">エイリアスの **オプション** プロパティの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="6256d-182">Sets the **Option** property value of the alias.</span></span> <span data-ttu-id="6256d-183">**ReadOnly** や **Constant** などの値は、意図しない変更からエイリアスを保護します。</span><span class="sxs-lookup"><span data-stu-id="6256d-183">Values such as **ReadOnly** and **Constant** protect an alias from unintended changes.</span></span> <span data-ttu-id="6256d-184">セッション内のすべてのエイリアスの **Option** プロパティを表示するには、「」と入力 `Get-Alias | Format-Table -Property Name, Options -Autosize` します。</span><span class="sxs-lookup"><span data-stu-id="6256d-184">To see the **Option** property of all aliases in the session, type `Get-Alias | Format-Table -Property Name, Options -Autosize`.</span></span>

<span data-ttu-id="6256d-185">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6256d-185">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="6256d-186">**Allscope** エイリアスは、作成された新しいスコープにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="6256d-186">**AllScope** The alias is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="6256d-187">**定数** 変更または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="6256d-187">**Constant** Cannot be changed or deleted.</span></span>
- <span data-ttu-id="6256d-188">**なし** オプションを設定せず、既定値です。</span><span class="sxs-lookup"><span data-stu-id="6256d-188">**None** Sets no options and is the default.</span></span>
- <span data-ttu-id="6256d-189">**プライベート** エイリアスは、現在のスコープでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6256d-189">**Private** The alias is available only in the current scope.</span></span>
- <span data-ttu-id="6256d-190">**読み取り専用\*\*\*\*Force** パラメーターを使用しない限り、変更または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="6256d-190">**ReadOnly** Cannot be changed or deleted unless the **Force** parameter is used.</span></span>
- <span data-ttu-id="6256d-191">**未指定**</span><span class="sxs-lookup"><span data-stu-id="6256d-191">**Unspecified**</span></span>

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: AllScope, Constant, None, Private, ReadOnly, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6256d-192">-PassThru</span><span class="sxs-lookup"><span data-stu-id="6256d-192">-PassThru</span></span>

<span data-ttu-id="6256d-193">エイリアスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="6256d-193">Returns an object that represents the alias.</span></span> <span data-ttu-id="6256d-194">オブジェクトを表示するには、などの書式設定コマンドレットを使用し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-194">Use a format cmdlet such as `Format-List` to display the object.</span></span> <span data-ttu-id="6256d-195">既定で `Set-Alias` は、は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="6256d-195">By default, `Set-Alias` does not generate any output.</span></span>

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

### <span data-ttu-id="6256d-196">-スコープ</span><span class="sxs-lookup"><span data-stu-id="6256d-196">-Scope</span></span>

<span data-ttu-id="6256d-197">このエイリアスが有効なスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="6256d-197">Specifies the scope in which this alias is valid.</span></span> <span data-ttu-id="6256d-198">既定値は **Local** です。</span><span class="sxs-lookup"><span data-stu-id="6256d-198">The default value is **Local** .</span></span> <span data-ttu-id="6256d-199">詳細については、「 [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6256d-199">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

<span data-ttu-id="6256d-200">使用できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6256d-200">The acceptable values are as follows:</span></span>

- <span data-ttu-id="6256d-201">グローバル</span><span class="sxs-lookup"><span data-stu-id="6256d-201">Global</span></span>
- <span data-ttu-id="6256d-202">ローカル</span><span class="sxs-lookup"><span data-stu-id="6256d-202">Local</span></span>
- <span data-ttu-id="6256d-203">Private</span><span class="sxs-lookup"><span data-stu-id="6256d-203">Private</span></span>
- <span data-ttu-id="6256d-204">番号付きスコープ</span><span class="sxs-lookup"><span data-stu-id="6256d-204">Numbered scopes</span></span>
- <span data-ttu-id="6256d-205">スクリプト</span><span class="sxs-lookup"><span data-stu-id="6256d-205">Script</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Global, Local, Private, Numbered scopes, Script

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6256d-206">-Value</span><span class="sxs-lookup"><span data-stu-id="6256d-206">-Value</span></span>

<span data-ttu-id="6256d-207">エイリアスが実行されるコマンドレットまたはコマンドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6256d-207">Specifies the name of the cmdlet or command that the alias runs.</span></span> <span data-ttu-id="6256d-208">**値** パラメーターは、エイリアスの **定義** プロパティです。</span><span class="sxs-lookup"><span data-stu-id="6256d-208">The **Value** parameter is the alias's **Definition** property.</span></span>

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

### <span data-ttu-id="6256d-209">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6256d-209">-Confirm</span></span>

<span data-ttu-id="6256d-210">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6256d-210">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6256d-211">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6256d-211">-WhatIf</span></span>

<span data-ttu-id="6256d-212">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="6256d-212">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6256d-213">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="6256d-213">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6256d-214">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6256d-214">CommonParameters</span></span>

<span data-ttu-id="6256d-215">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6256d-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6256d-216">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6256d-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6256d-217">入力</span><span class="sxs-lookup"><span data-stu-id="6256d-217">INPUTS</span></span>

### <span data-ttu-id="6256d-218">なし</span><span class="sxs-lookup"><span data-stu-id="6256d-218">None</span></span>

<span data-ttu-id="6256d-219">`Set-Alias` は、パイプラインからの入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="6256d-219">`Set-Alias` does not accept input from the pipeline.</span></span>

## <span data-ttu-id="6256d-220">出力</span><span class="sxs-lookup"><span data-stu-id="6256d-220">OUTPUTS</span></span>

### <span data-ttu-id="6256d-221">None または system.servicemodel. エイリアス情報</span><span class="sxs-lookup"><span data-stu-id="6256d-221">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="6256d-222">**PassThru** パラメーターを使用すると、に `Set-Alias` よって、エイリアスを表す system.string オブジェクトが生成さ **れます。**</span><span class="sxs-lookup"><span data-stu-id="6256d-222">When you use the **PassThru** parameter, `Set-Alias` generates a **System.Management.Automation.AliasInfo** object representing the alias.</span></span> <span data-ttu-id="6256d-223">それ以外の場合、 `Set-Alias` は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="6256d-223">Otherwise, `Set-Alias` does not generate any output.</span></span>

## <span data-ttu-id="6256d-224">注</span><span class="sxs-lookup"><span data-stu-id="6256d-224">NOTES</span></span>

<span data-ttu-id="6256d-225">PowerShell には、各 PowerShell セッションで使用できる組み込みエイリアスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6256d-225">PowerShell includes built-in aliases that are available in each PowerShell session.</span></span> <span data-ttu-id="6256d-226">`Get-Alias`コマンドレットは、PowerShell セッションで使用できるエイリアスを表示します。</span><span class="sxs-lookup"><span data-stu-id="6256d-226">The `Get-Alias` cmdlet displays the aliases available in a PowerShell session.</span></span>

<span data-ttu-id="6256d-227">エイリアスを作成するには、コマンドレットまたはを使用し `Set-Alias` `New-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-227">To create an alias, use the cmdlets `Set-Alias` or `New-Alias`.</span></span> <span data-ttu-id="6256d-228">PowerShell 6 では、エイリアスを削除するには、コマンドレットを使用し `Remove-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-228">In PowerShell 6, to delete an alias, use the `Remove-Alias` cmdlet.</span></span> <span data-ttu-id="6256d-229">`Remove-Item` は、以前のバージョンの PowerShell で作成されたスクリプトの場合など、下位互換性のために受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="6256d-229">`Remove-Item` is accepted for backwards compatibility such as for scripts created with prior versions of PowerShell.</span></span> <span data-ttu-id="6256d-230">などのコマンドを使用し `Remove-Item -Path Alias:aliasname` ます。</span><span class="sxs-lookup"><span data-stu-id="6256d-230">Use a command such as `Remove-Item -Path Alias:aliasname`.</span></span>

<span data-ttu-id="6256d-231">各 PowerShell セッションで使用できるエイリアスを作成するには、それを PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="6256d-231">To create an alias that is available in each PowerShell session, add it to your PowerShell profile.</span></span>
<span data-ttu-id="6256d-232">詳細については、「 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6256d-232">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="6256d-233">エイリアスは、エクスポートとインポートを実行することで、別の PowerShell セッションで保存して再利用できます。</span><span class="sxs-lookup"><span data-stu-id="6256d-233">An alias can be saved and reused in another PowerShell session by doing an export and import.</span></span> <span data-ttu-id="6256d-234">エイリアスをファイルに保存するには、を使用 `Export-Alias` します。</span><span class="sxs-lookup"><span data-stu-id="6256d-234">To save an alias to a file, use `Export-Alias`.</span></span> <span data-ttu-id="6256d-235">新しい PowerShell セッションに保存されたエイリアスを追加するには、を使用 `Import-Alias` します。</span><span class="sxs-lookup"><span data-stu-id="6256d-235">To add a saved alias to a new PowerShell session, use `Import-Alias`.</span></span>

## <span data-ttu-id="6256d-236">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6256d-236">RELATED LINKS</span></span>

[<span data-ttu-id="6256d-237">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="6256d-237">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="6256d-238">about_Functions</span><span class="sxs-lookup"><span data-stu-id="6256d-238">about_Functions</span></span>](../Microsoft.PowerShell.Core/about/about_Functions.md)

[<span data-ttu-id="6256d-239">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="6256d-239">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_Profiles.md)

[<span data-ttu-id="6256d-240">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="6256d-240">about_Scopes</span></span>](../Microsoft.PowerShell.Core/About/about_Scopes.md)

[<span data-ttu-id="6256d-241">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="6256d-241">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="6256d-242">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="6256d-242">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="6256d-243">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="6256d-243">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="6256d-244">New-Alias</span><span class="sxs-lookup"><span data-stu-id="6256d-244">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="6256d-245">Remove-Alias</span><span class="sxs-lookup"><span data-stu-id="6256d-245">Remove-Alias</span></span>](Remove-Alias.md)

[<span data-ttu-id="6256d-246">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="6256d-246">Remove-Item</span></span>](../Microsoft.PowerShell.Management/Remove-Item.md)
