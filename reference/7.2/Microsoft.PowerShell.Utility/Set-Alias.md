---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 02/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-alias?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Alias
ms.openlocfilehash: e9e80b4bf558dcf1e225868a1138979270ea304f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601788"
---
# <span data-ttu-id="2f592-102">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="2f592-102">Set-Alias</span></span>

## <span data-ttu-id="2f592-103">概要</span><span class="sxs-lookup"><span data-stu-id="2f592-103">SYNOPSIS</span></span>
<span data-ttu-id="2f592-104">現在の PowerShell セッションで、コマンドレットまたはその他のコマンドのエイリアスを作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="2f592-104">Creates or changes an alias for a cmdlet or other command in the current PowerShell session.</span></span>

## <span data-ttu-id="2f592-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2f592-105">SYNTAX</span></span>

### <span data-ttu-id="2f592-106">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="2f592-106">Default (Default)</span></span>

```
Set-Alias [-Name] <string> [-Value] <string> [-Description <string>] [-Option <ScopedItemOptions>]
 [-PassThru] [-Scope <string>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2f592-107">Description</span><span class="sxs-lookup"><span data-stu-id="2f592-107">DESCRIPTION</span></span>

<span data-ttu-id="2f592-108">コマンドレットは、コマンド `Set-Alias` レットまたはコマンド (関数、スクリプト、ファイル、その他の実行可能ファイルなど) のエイリアスを作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="2f592-108">The `Set-Alias` cmdlet creates or changes an alias for a cmdlet or a command, such as a function, script, file, or other executable.</span></span> <span data-ttu-id="2f592-109">エイリアスは、コマンドレットまたはコマンドを参照する代替名です。</span><span class="sxs-lookup"><span data-stu-id="2f592-109">An alias is an alternate name that refers to a cmdlet or command.</span></span>
<span data-ttu-id="2f592-110">たとえば、 `sal` はコマンドレットのエイリアスです `Set-Alias` 。</span><span class="sxs-lookup"><span data-stu-id="2f592-110">For example, `sal` is the alias for the `Set-Alias` cmdlet.</span></span> <span data-ttu-id="2f592-111">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f592-111">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="2f592-112">コマンドレットは複数のエイリアスを持つことができますが、エイリアスは1つのコマンドレットにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="2f592-112">A cmdlet can have multiple aliases, but an alias can only be associated with one cmdlet.</span></span> <span data-ttu-id="2f592-113">を使用すると、 `Set-Alias` 既存のエイリアスを別のコマンドレットに再割り当てしたり、説明などのエイリアスのプロパティを変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="2f592-113">You can use `Set-Alias` to reassign an existing alias to another cmdlet, or change an alias's properties, such as the description.</span></span>

<span data-ttu-id="2f592-114">によって作成または変更されたエイリアス `Set-Alias` は永続的ではなく、現在の PowerShell セッション中にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f592-114">An alias that is created or changed by `Set-Alias` is not permanent and is only available during the current PowerShell session.</span></span> <span data-ttu-id="2f592-115">PowerShell セッションが終了すると、エイリアスは削除されます。</span><span class="sxs-lookup"><span data-stu-id="2f592-115">When the PowerShell session is closed, the alias is removed.</span></span>

## <span data-ttu-id="2f592-116">例</span><span class="sxs-lookup"><span data-stu-id="2f592-116">EXAMPLES</span></span>

### <span data-ttu-id="2f592-117">例 1: コマンドレットのエイリアスを作成する</span><span class="sxs-lookup"><span data-stu-id="2f592-117">Example 1: Create an alias for a cmdlet</span></span>

<span data-ttu-id="2f592-118">このコマンドは、現在の PowerShell セッションのコマンドレットのエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f592-118">This command creates an alias to a cmdlet in the current PowerShell session.</span></span>

```
PS> Set-Alias -Name list -Value Get-ChildItem

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem
```

<span data-ttu-id="2f592-119">コマンドレットにより、 `Set-Alias` 現在の PowerShell セッションにエイリアスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2f592-119">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="2f592-120">**Name** パラメーターは、エイリアスの名前を指定し `list` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-120">The **Name** parameter specifies the alias's name, `list`.</span></span> <span data-ttu-id="2f592-121">**値** パラメーターは、エイリアスが実行されるコマンドレットを指定します。</span><span class="sxs-lookup"><span data-stu-id="2f592-121">The **Value** parameter specifies the cmdlet that the alias runs.</span></span>

<span data-ttu-id="2f592-122">エイリアスを実行するには、PowerShell コマンドラインで「」と入力し `list` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-122">To run the alias, type `list` on the PowerShell command line.</span></span>

### <span data-ttu-id="2f592-123">例 2: 既存のエイリアスを別のコマンドレットに再割り当てする</span><span class="sxs-lookup"><span data-stu-id="2f592-123">Example 2: Reassign an existing alias to a different cmdlet</span></span>

<span data-ttu-id="2f592-124">このコマンドは、既存のエイリアスを再割り当てして別のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="2f592-124">This command reassigns an existing alias to run a different cmdlet.</span></span>

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

<span data-ttu-id="2f592-125">コマンドレットでは、 `Get-Alias` **Name** パラメーターを使用して別名を表示し `list` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-125">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="2f592-126">`list`エイリアスは、コマンドレットに関連付けられてい `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-126">The `list` alias is associated with the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="2f592-127">エイリアスを実行すると、 `list` 現在のディレクトリ内の項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f592-127">When the `list` alias is run, the items in the current directory are displayed.</span></span>

<span data-ttu-id="2f592-128">コマンドレットでは、 `Set-Alias` **Name** パラメーターを使用してエイリアスを指定し `list` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-128">The `Set-Alias` cmdlet uses the **Name** parameter to specify the `list` alias.</span></span> <span data-ttu-id="2f592-129">**Value** パラメーターによって、エイリアスがコマンドレットに関連付けられ `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-129">The **Value** parameter associates the alias to the `Get-Location` cmdlet.</span></span>

<span data-ttu-id="2f592-130">コマンドレットでは、 `Get-Alias` **Name** パラメーターを使用して別名を表示し `list` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-130">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="2f592-131">`list`エイリアスは、コマンドレットに関連付けられてい `Get-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-131">The `list` alias is associated with the `Get-Location` cmdlet.</span></span> <span data-ttu-id="2f592-132">エイリアスを実行すると、 `list` 現在のディレクトリの場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f592-132">When the `list` alias is run, the current directory's location is displayed.</span></span>

### <span data-ttu-id="2f592-133">例 3: 読み取り専用のエイリアスを作成して変更する</span><span class="sxs-lookup"><span data-stu-id="2f592-133">Example 3: Create and change a read-only alias</span></span>

<span data-ttu-id="2f592-134">このコマンドは、読み取り専用のエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f592-134">This command creates a read-only alias.</span></span> <span data-ttu-id="2f592-135">読み取り専用オプションを指定すると、エイリアスが意図せず変更されるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="2f592-135">The read-only option prevents unintended changes to an alias.</span></span> <span data-ttu-id="2f592-136">読み取り専用エイリアスを変更または削除するには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f592-136">To change or delete a read-only alias, use the **Force** parameter.</span></span>

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

<span data-ttu-id="2f592-137">コマンドレットにより、 `Set-Alias` 現在の PowerShell セッションにエイリアスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2f592-137">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="2f592-138">**Name** パラメーターは、エイリアスの名前を指定し `loc` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-138">The **Name** parameter specifies the alias's name, `loc`.</span></span> <span data-ttu-id="2f592-139">**値** パラメーターは、 `Get-Location` エイリアスが実行されるコマンドレットを指定します。</span><span class="sxs-lookup"><span data-stu-id="2f592-139">The **Value** parameter specifies the `Get-Location` cmdlet that the alias runs.</span></span> <span data-ttu-id="2f592-140">**オプション** パラメーターは、 **ReadOnly** 値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f592-140">The **Option** parameter specifies the **ReadOnly** value.</span></span> <span data-ttu-id="2f592-141">**PassThru** パラメーターは alias オブジェクトを表し、オブジェクトをパイプラインの下にあるオブジェクトをコマンドレットに送信し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-141">The **PassThru** parameter represents the alias object and sends the object down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="2f592-142">`Format-List`**プロパティパラメーターを** アスタリスク () と共に使用して `*` 、すべてのプロパティが表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="2f592-142">`Format-List` uses the **Property** parameter with an asterisk (`*`) so that all of the properties are displayed.</span></span> <span data-ttu-id="2f592-143">出力例では、これらのプロパティの部分的なリストを示しています。</span><span class="sxs-lookup"><span data-stu-id="2f592-143">The example output shows a partial list of those properties.</span></span>

<span data-ttu-id="2f592-144">`loc`2 つのパラメーターを追加することで、別名が変更されます。</span><span class="sxs-lookup"><span data-stu-id="2f592-144">The `loc` alias is changed with the addition of two parameters.</span></span> <span data-ttu-id="2f592-145">**説明** エイリアスの目的を説明するテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="2f592-145">**Description** adds text to explain the alias's purpose.</span></span> <span data-ttu-id="2f592-146">エイリアスは読み取り専用であるため、 **Force** パラメーターが必要です `loc` 。</span><span class="sxs-lookup"><span data-stu-id="2f592-146">The **Force** parameter is needed because the `loc` alias is read-only.</span></span> <span data-ttu-id="2f592-147">**Force** パラメーターが使用されていない場合、変更は失敗します。</span><span class="sxs-lookup"><span data-stu-id="2f592-147">If the **Force** parameter is not used, the change fails.</span></span>

### <span data-ttu-id="2f592-148">例 4: 実行可能ファイルのエイリアスを作成する</span><span class="sxs-lookup"><span data-stu-id="2f592-148">Example 4: Create an alias to an executable file</span></span>

<span data-ttu-id="2f592-149">この例では、ローカルコンピューター上の実行可能ファイルのエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f592-149">This example creates an alias to an executable file on the local computer.</span></span>

```
PS> Set-Alias -Name np -Value C:\Windows\notepad.exe

PS> Get-Alias -Name np

CommandType     Name
-----------     ----
Alias           np -> notepad.exe
```

<span data-ttu-id="2f592-150">コマンドレットにより、 `Set-Alias` 現在の PowerShell セッションにエイリアスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2f592-150">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="2f592-151">**Name** パラメーターは、エイリアスの名前を指定し `np` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-151">The **Name** parameter specifies the alias's name, `np`.</span></span> <span data-ttu-id="2f592-152">**Value** パラメーターには **C:\Windows\notepad.exe** パスとアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f592-152">The **Value** parameter specifies the path and application name **C:\Windows\notepad.exe**.</span></span> <span data-ttu-id="2f592-153">この `Get-Alias` コマンドレットでは、 **Name** パラメーターを使用して、 `np` エイリアスが **notepad.exe** に関連付けられていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="2f592-153">The `Get-Alias` cmdlet uses the **Name** parameter to show that the `np` alias is associated with **notepad.exe**.</span></span>

<span data-ttu-id="2f592-154">エイリアスを実行するには、PowerShell コマンドラインで「」と入力して `np` **notepad.exe** を開きます。</span><span class="sxs-lookup"><span data-stu-id="2f592-154">To run the alias, type `np` on the PowerShell command line to open **notepad.exe**.</span></span>

### <span data-ttu-id="2f592-155">例 5: パラメーターを使用してコマンドのエイリアスを作成する</span><span class="sxs-lookup"><span data-stu-id="2f592-155">Example 5: Create an alias for a command with parameters</span></span>

<span data-ttu-id="2f592-156">この例では、パラメーターを使用して、コマンドにエイリアスを割り当てる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2f592-156">This example shows how to assign an alias to a command with parameters.</span></span>

<span data-ttu-id="2f592-157">などのコマンドレットのエイリアスを作成でき `Set-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-157">You can create an alias for a cmdlet, such as `Set-Location`.</span></span> <span data-ttu-id="2f592-158">などのパラメーターと値を使用して、コマンドのエイリアスを作成することはできません `Set-Location -Path C:\Windows\System32` 。</span><span class="sxs-lookup"><span data-stu-id="2f592-158">You cannot create an alias for a command with parameters and values, such as `Set-Location -Path C:\Windows\System32`.</span></span> <span data-ttu-id="2f592-159">コマンドのエイリアスを作成するには、コマンドを含む関数を作成し、その関数のエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f592-159">To create an alias for a command, create a function that includes the command, and then create an alias to the function.</span></span> <span data-ttu-id="2f592-160">詳細については、「 [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f592-160">For more information, see [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).</span></span>

```
PS> Function CD32 {Set-Location -Path C:\Windows\System32}

PS> Set-Alias -Name Go -Value CD32
```

<span data-ttu-id="2f592-161">という名前 `CD32` の関数が作成されます。</span><span class="sxs-lookup"><span data-stu-id="2f592-161">A function named `CD32` is created.</span></span> <span data-ttu-id="2f592-162">関数は、 `Set-Location` **Path** パラメーターを指定したコマンドレットを使用して、 **C:\Windows\System32** ディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="2f592-162">The function uses the `Set-Location` cmdlet with the **Path** parameter to specify the directory, **C:\Windows\System32**.</span></span>

<span data-ttu-id="2f592-163">コマンドレットにより、 `Set-Alias` 現在の PowerShell セッションの関数のエイリアスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2f592-163">The `Set-Alias` cmdlet creates an alias to the function in the current PowerShell session.</span></span> <span data-ttu-id="2f592-164">**Name** パラメーターは、エイリアスの名前を指定し `Go` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-164">The **Name** parameter specifies the alias's name, `Go`.</span></span> <span data-ttu-id="2f592-165">**Value** パラメーターは、関数の名前を指定し `CD32` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-165">The **Value** parameter specifies the function's name, `CD32`.</span></span>

<span data-ttu-id="2f592-166">エイリアスを実行するには、PowerShell コマンドラインで「」と入力し `Go` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-166">To run the alias, type `Go` on the PowerShell command line.</span></span> <span data-ttu-id="2f592-167">関数が実行され、 `CD32` ディレクトリ **C:\Windows\System32** に変更されます。</span><span class="sxs-lookup"><span data-stu-id="2f592-167">The `CD32` function runs and changes to the directory **C:\Windows\System32**.</span></span>

## <span data-ttu-id="2f592-168">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2f592-168">PARAMETERS</span></span>

### <span data-ttu-id="2f592-169">-Description</span><span class="sxs-lookup"><span data-stu-id="2f592-169">-Description</span></span>

<span data-ttu-id="2f592-170">エイリアスの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f592-170">Specifies a description of the alias.</span></span> <span data-ttu-id="2f592-171">任意の文字列を入力できます。</span><span class="sxs-lookup"><span data-stu-id="2f592-171">You can type any string.</span></span> <span data-ttu-id="2f592-172">説明にスペースが含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="2f592-172">If the description includes spaces, enclose it single quotation marks.</span></span>

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

### <span data-ttu-id="2f592-173">-Force</span><span class="sxs-lookup"><span data-stu-id="2f592-173">-Force</span></span>

<span data-ttu-id="2f592-174">**Force** パラメーターを使用して、**オプション** パラメーターが **ReadOnly** に設定されているエイリアスを変更または削除します。</span><span class="sxs-lookup"><span data-stu-id="2f592-174">Use the **Force** parameter to change or delete an alias that has the **Option** parameter set to **ReadOnly**.</span></span>

<span data-ttu-id="2f592-175">**Force** パラメーターは、 **Option** パラメーターを **Constant** に設定してエイリアスを変更または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f592-175">The **Force** parameter cannot change or delete an alias with the **Option** parameter set to **Constant**.</span></span>

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

### <span data-ttu-id="2f592-176">-Name</span><span class="sxs-lookup"><span data-stu-id="2f592-176">-Name</span></span>

<span data-ttu-id="2f592-177">新しいエイリアスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f592-177">Specifies the name of a new alias.</span></span> <span data-ttu-id="2f592-178">エイリアス名には、英数字とハイフンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f592-178">An alias name can contain alphanumeric characters and hyphens.</span></span> <span data-ttu-id="2f592-179">エイリアス名には、123などの数値を指定できません。</span><span class="sxs-lookup"><span data-stu-id="2f592-179">Alias names cannot be numeric, such as 123.</span></span>

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

### <span data-ttu-id="2f592-180">-Option</span><span class="sxs-lookup"><span data-stu-id="2f592-180">-Option</span></span>

<span data-ttu-id="2f592-181">エイリアスの **オプション** プロパティの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="2f592-181">Sets the **Option** property value of the alias.</span></span> <span data-ttu-id="2f592-182">**ReadOnly** や **Constant** などの値は、意図しない変更からエイリアスを保護します。</span><span class="sxs-lookup"><span data-stu-id="2f592-182">Values such as **ReadOnly** and **Constant** protect an alias from unintended changes.</span></span> <span data-ttu-id="2f592-183">セッション内のすべてのエイリアスの **Option** プロパティを表示するには、「」と入力 `Get-Alias | Format-Table -Property Name, Options -Autosize` します。</span><span class="sxs-lookup"><span data-stu-id="2f592-183">To see the **Option** property of all aliases in the session, type `Get-Alias | Format-Table -Property Name, Options -Autosize`.</span></span>

<span data-ttu-id="2f592-184">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2f592-184">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="2f592-185">**Allscope** エイリアスは、作成された新しいスコープにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="2f592-185">**AllScope** The alias is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="2f592-186">**定数** 変更または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f592-186">**Constant** Cannot be changed or deleted.</span></span>
- <span data-ttu-id="2f592-187">**なし** オプションを設定せず、既定値です。</span><span class="sxs-lookup"><span data-stu-id="2f592-187">**None** Sets no options and is the default.</span></span>
- <span data-ttu-id="2f592-188">**プライベート** エイリアスは、現在のスコープでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f592-188">**Private** The alias is available only in the current scope.</span></span>
- <span data-ttu-id="2f592-189">**読み取り専用\*\*\*\*Force** パラメーターを使用しない限り、変更または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f592-189">**ReadOnly** Cannot be changed or deleted unless the **Force** parameter is used.</span></span>
- <span data-ttu-id="2f592-190">**未指定**</span><span class="sxs-lookup"><span data-stu-id="2f592-190">**Unspecified**</span></span>

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

### <span data-ttu-id="2f592-191">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2f592-191">-PassThru</span></span>

<span data-ttu-id="2f592-192">エイリアスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2f592-192">Returns an object that represents the alias.</span></span> <span data-ttu-id="2f592-193">オブジェクトを表示するには、などの書式設定コマンドレットを使用し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-193">Use a format cmdlet such as `Format-List` to display the object.</span></span> <span data-ttu-id="2f592-194">既定で `Set-Alias` は、は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="2f592-194">By default, `Set-Alias` does not generate any output.</span></span>

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

### <span data-ttu-id="2f592-195">-スコープ</span><span class="sxs-lookup"><span data-stu-id="2f592-195">-Scope</span></span>

<span data-ttu-id="2f592-196">このエイリアスが有効なスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="2f592-196">Specifies the scope in which this alias is valid.</span></span> <span data-ttu-id="2f592-197">既定値は **Local** です。</span><span class="sxs-lookup"><span data-stu-id="2f592-197">The default value is **Local**.</span></span> <span data-ttu-id="2f592-198">詳細については、「 [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f592-198">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

<span data-ttu-id="2f592-199">使用できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2f592-199">The acceptable values are as follows:</span></span>

- <span data-ttu-id="2f592-200">グローバル</span><span class="sxs-lookup"><span data-stu-id="2f592-200">Global</span></span>
- <span data-ttu-id="2f592-201">ローカル</span><span class="sxs-lookup"><span data-stu-id="2f592-201">Local</span></span>
- <span data-ttu-id="2f592-202">プライベート</span><span class="sxs-lookup"><span data-stu-id="2f592-202">Private</span></span>
- <span data-ttu-id="2f592-203">番号付きスコープ</span><span class="sxs-lookup"><span data-stu-id="2f592-203">Numbered scopes</span></span>
- <span data-ttu-id="2f592-204">スクリプト</span><span class="sxs-lookup"><span data-stu-id="2f592-204">Script</span></span>

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

### <span data-ttu-id="2f592-205">-Value</span><span class="sxs-lookup"><span data-stu-id="2f592-205">-Value</span></span>

<span data-ttu-id="2f592-206">エイリアスが実行されるコマンドレットまたはコマンドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f592-206">Specifies the name of the cmdlet or command that the alias runs.</span></span> <span data-ttu-id="2f592-207">**値** パラメーターは、エイリアスの **定義** プロパティです。</span><span class="sxs-lookup"><span data-stu-id="2f592-207">The **Value** parameter is the alias's **Definition** property.</span></span>

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

### <span data-ttu-id="2f592-208">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2f592-208">-Confirm</span></span>

<span data-ttu-id="2f592-209">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f592-209">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2f592-210">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2f592-210">-WhatIf</span></span>

<span data-ttu-id="2f592-211">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="2f592-211">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2f592-212">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2f592-212">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2f592-213">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2f592-213">CommonParameters</span></span>

<span data-ttu-id="2f592-214">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2f592-214">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2f592-215">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f592-215">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2f592-216">入力</span><span class="sxs-lookup"><span data-stu-id="2f592-216">INPUTS</span></span>

### <span data-ttu-id="2f592-217">なし</span><span class="sxs-lookup"><span data-stu-id="2f592-217">None</span></span>

<span data-ttu-id="2f592-218">`Set-Alias` は、パイプラインからの入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="2f592-218">`Set-Alias` does not accept input from the pipeline.</span></span>

## <span data-ttu-id="2f592-219">出力</span><span class="sxs-lookup"><span data-stu-id="2f592-219">OUTPUTS</span></span>

### <span data-ttu-id="2f592-220">None または system.servicemodel. エイリアス情報</span><span class="sxs-lookup"><span data-stu-id="2f592-220">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="2f592-221">**PassThru** パラメーターを使用すると、に `Set-Alias` よって、エイリアスを表す system.string オブジェクトが生成さ **れます。**</span><span class="sxs-lookup"><span data-stu-id="2f592-221">When you use the **PassThru** parameter, `Set-Alias` generates a **System.Management.Automation.AliasInfo** object representing the alias.</span></span> <span data-ttu-id="2f592-222">それ以外の場合、 `Set-Alias` は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="2f592-222">Otherwise, `Set-Alias` does not generate any output.</span></span>

## <span data-ttu-id="2f592-223">注</span><span class="sxs-lookup"><span data-stu-id="2f592-223">NOTES</span></span>

<span data-ttu-id="2f592-224">PowerShell には、各 PowerShell セッションで使用できる組み込みエイリアスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f592-224">PowerShell includes built-in aliases that are available in each PowerShell session.</span></span> <span data-ttu-id="2f592-225">`Get-Alias`コマンドレットは、PowerShell セッションで使用できるエイリアスを表示します。</span><span class="sxs-lookup"><span data-stu-id="2f592-225">The `Get-Alias` cmdlet displays the aliases available in a PowerShell session.</span></span>

<span data-ttu-id="2f592-226">エイリアスを作成するには、コマンドレットまたはを使用し `Set-Alias` `New-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-226">To create an alias, use the cmdlets `Set-Alias` or `New-Alias`.</span></span> <span data-ttu-id="2f592-227">PowerShell 6 では、エイリアスを削除するには、コマンドレットを使用し `Remove-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-227">In PowerShell 6, to delete an alias, use the `Remove-Alias` cmdlet.</span></span> <span data-ttu-id="2f592-228">`Remove-Item` は、以前のバージョンの PowerShell で作成されたスクリプトの場合など、下位互換性のために受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="2f592-228">`Remove-Item` is accepted for backwards compatibility such as for scripts created with prior versions of PowerShell.</span></span> <span data-ttu-id="2f592-229">などのコマンドを使用し `Remove-Item -Path Alias:aliasname` ます。</span><span class="sxs-lookup"><span data-stu-id="2f592-229">Use a command such as `Remove-Item -Path Alias:aliasname`.</span></span>

<span data-ttu-id="2f592-230">各 PowerShell セッションで使用できるエイリアスを作成するには、それを PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="2f592-230">To create an alias that is available in each PowerShell session, add it to your PowerShell profile.</span></span>
<span data-ttu-id="2f592-231">詳細については、「 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f592-231">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="2f592-232">エイリアスは、エクスポートとインポートを実行することで、別の PowerShell セッションで保存して再利用できます。</span><span class="sxs-lookup"><span data-stu-id="2f592-232">An alias can be saved and reused in another PowerShell session by doing an export and import.</span></span> <span data-ttu-id="2f592-233">エイリアスをファイルに保存するには、を使用 `Export-Alias` します。</span><span class="sxs-lookup"><span data-stu-id="2f592-233">To save an alias to a file, use `Export-Alias`.</span></span> <span data-ttu-id="2f592-234">新しい PowerShell セッションに保存されたエイリアスを追加するには、を使用 `Import-Alias` します。</span><span class="sxs-lookup"><span data-stu-id="2f592-234">To add a saved alias to a new PowerShell session, use `Import-Alias`.</span></span>

## <span data-ttu-id="2f592-235">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2f592-235">RELATED LINKS</span></span>

[<span data-ttu-id="2f592-236">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="2f592-236">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="2f592-237">about_Functions</span><span class="sxs-lookup"><span data-stu-id="2f592-237">about_Functions</span></span>](../Microsoft.PowerShell.Core/about/about_Functions.md)

[<span data-ttu-id="2f592-238">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="2f592-238">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_Profiles.md)

[<span data-ttu-id="2f592-239">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="2f592-239">about_Scopes</span></span>](../Microsoft.PowerShell.Core/About/about_Scopes.md)

[<span data-ttu-id="2f592-240">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="2f592-240">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="2f592-241">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="2f592-241">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="2f592-242">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="2f592-242">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="2f592-243">New-Alias</span><span class="sxs-lookup"><span data-stu-id="2f592-243">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="2f592-244">Remove-Alias</span><span class="sxs-lookup"><span data-stu-id="2f592-244">Remove-Alias</span></span>](Remove-Alias.md)

[<span data-ttu-id="2f592-245">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="2f592-245">Remove-Item</span></span>](../Microsoft.PowerShell.Management/Remove-Item.md)

