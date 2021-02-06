---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/clear-history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-History
ms.openlocfilehash: 1b465779f56c6bd71d7adfa7ffb5b391f5402656
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603054"
---
# <span data-ttu-id="643f2-102">Clear-History</span><span class="sxs-lookup"><span data-stu-id="643f2-102">Clear-History</span></span>

## <span data-ttu-id="643f2-103">概要</span><span class="sxs-lookup"><span data-stu-id="643f2-103">SYNOPSIS</span></span>
<span data-ttu-id="643f2-104">PowerShell セッションのコマンド履歴からエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="643f2-104">Deletes entries from the PowerShell session command history.</span></span>

## <span data-ttu-id="643f2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="643f2-105">SYNTAX</span></span>

### <span data-ttu-id="643f2-106">IDParameter (既定値)</span><span class="sxs-lookup"><span data-stu-id="643f2-106">IDParameter (Default)</span></span>

```
Clear-History [[-Id] <int[]>] [[-Count] <int>] [-Newest] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="643f2-107">CommandLineParameter</span><span class="sxs-lookup"><span data-stu-id="643f2-107">CommandLineParameter</span></span>

```
Clear-History [[-Count] <int>] [-CommandLine <string[]>] [-Newest] [-WhatIf] [-Confirm]
[<CommonParameters>]
```

## <span data-ttu-id="643f2-108">Description</span><span class="sxs-lookup"><span data-stu-id="643f2-108">DESCRIPTION</span></span>

<span data-ttu-id="643f2-109">`Clear-History` PowerShell セッションからコマンド履歴を削除します。</span><span class="sxs-lookup"><span data-stu-id="643f2-109">`Clear-History` deletes the command history from a PowerShell session.</span></span> <span data-ttu-id="643f2-110">各 PowerShell セッションには、独自のコマンド履歴があります。</span><span class="sxs-lookup"><span data-stu-id="643f2-110">Each PowerShell session has its own command history.</span></span> <span data-ttu-id="643f2-111">コマンドの履歴を表示するには、コマンドレットを使用し `Get-History` ます。</span><span class="sxs-lookup"><span data-stu-id="643f2-111">To display the command history, use the `Get-History` cmdlet.</span></span>

<span data-ttu-id="643f2-112">既定では、は `Clear-History` PowerShell セッションからコマンド履歴全体を削除します。</span><span class="sxs-lookup"><span data-stu-id="643f2-112">By default, `Clear-History` deletes the entire command history from a PowerShell session.</span></span> <span data-ttu-id="643f2-113">でパラメーターを使用すると、 `Clear-History` 選択したコマンドを削除できます。</span><span class="sxs-lookup"><span data-stu-id="643f2-113">You can use parameters with `Clear-History` to delete selected commands.</span></span>

<span data-ttu-id="643f2-114">`Clear-History` では、コマンド履歴ファイルはクリアされません `PSReadLine` 。</span><span class="sxs-lookup"><span data-stu-id="643f2-114">`Clear-History` does not clear the `PSReadLine` command history file.</span></span> <span data-ttu-id="643f2-115">モジュールは、 `PSReadLine` すべての powershell セッションからのすべての powershell コマンドを含む履歴ファイルを格納します。</span><span class="sxs-lookup"><span data-stu-id="643f2-115">The `PSReadLine` module stores a history file that contains every PowerShell command from every PowerShell session.</span></span> <span data-ttu-id="643f2-116">PowerShell プロンプトで、キーボードの上矢印と下矢印を使用して、コマンドの履歴をスクロールします。</span><span class="sxs-lookup"><span data-stu-id="643f2-116">From a PowerShell prompt, use the up and down arrows on your keyboard to scroll through the command history.</span></span> <span data-ttu-id="643f2-117">コマンド履歴の構成を表示するには `PSReadLine` 、を使用 `Get-PSReadLineOption` します。</span><span class="sxs-lookup"><span data-stu-id="643f2-117">To display the `PSReadLine` configuration for command history, use `Get-PSReadLineOption`.</span></span>
<span data-ttu-id="643f2-118">`PSReadLine` PowerShell 5.0 以降に付属しています。</span><span class="sxs-lookup"><span data-stu-id="643f2-118">`PSReadLine` shipped with PowerShell 5.0 and above.</span></span> <span data-ttu-id="643f2-119">詳細については、「 [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="643f2-119">For more information, see [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="643f2-120">例</span><span class="sxs-lookup"><span data-stu-id="643f2-120">EXAMPLES</span></span>

### <span data-ttu-id="643f2-121">例 1: PowerShell セッションからコマンド履歴を削除する</span><span class="sxs-lookup"><span data-stu-id="643f2-121">Example 1: Delete the command history from a PowerShell session</span></span>

<span data-ttu-id="643f2-122">このコマンドは、PowerShell セッションの履歴からすべてのコマンドを削除します。</span><span class="sxs-lookup"><span data-stu-id="643f2-122">This command deletes all of the commands from a PowerShell session's history.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location .\Test
   2 Update-Help
   3 Set-Location C:\Test\Logs
   4 Get-Location
```

```powershell
Clear-History
Get-History
```

```Output
  Id CommandLine
  -- -----------
   5 Clear-History
```

<span data-ttu-id="643f2-123">コマンドレットにより、 `Get-History` PowerShell セッションの履歴が表示されます。</span><span class="sxs-lookup"><span data-stu-id="643f2-123">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="643f2-124">`Clear-History` コマンド履歴全体を削除します。</span><span class="sxs-lookup"><span data-stu-id="643f2-124">`Clear-History` deletes the entire command history.</span></span> <span data-ttu-id="643f2-125">`Get-History` 更新されたコマンドの履歴を表示し、以前の履歴が削除されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="643f2-125">`Get-History` displays the updated command history and confirms the prior history was deleted.</span></span>

### <span data-ttu-id="643f2-126">例 2: 最新のコマンドを削除する</span><span class="sxs-lookup"><span data-stu-id="643f2-126">Example 2: Delete the newest commands</span></span>

<span data-ttu-id="643f2-127">このコマンドは、 **Count** と **最新** のパラメーターを使用して、PowerShell セッションの履歴から最新のコマンドを削除します。</span><span class="sxs-lookup"><span data-stu-id="643f2-127">This command uses the **Count** and **Newest** parameters to delete the newest commands from a PowerShell session's history.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
```

```powershell
Clear-History -Count 5 -Newest
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
  11 Clear-History -Count 5 -Newest
```

<span data-ttu-id="643f2-128">コマンドレットにより、 `Get-History` PowerShell セッションの履歴が表示されます。</span><span class="sxs-lookup"><span data-stu-id="643f2-128">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="643f2-129">`Clear-History` コマンド履歴を削除するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="643f2-129">`Clear-History` is used to delete the command history.</span></span> <span data-ttu-id="643f2-130">**Count** パラメーターは、指定した **Id** を含む、削除するコマンドの数を指定します。**最新** のパラメーターは、最新のコマンドが履歴から消去されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="643f2-130">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id**. The **Newest** parameter specifies that the newest commands are cleared from the history.</span></span> <span data-ttu-id="643f2-131">`Get-History`更新されたコマンドの履歴を表示し、5つの最新のコマンドが削除されたことを確認します。 **id 6**  -  **id 10**。</span><span class="sxs-lookup"><span data-stu-id="643f2-131">`Get-History` displays the updated command history and confirms that the five newest commands were deleted, **Id 6** - **Id 10**.</span></span>

### <span data-ttu-id="643f2-132">例 3: 特定の条件に一致するコマンドを削除する</span><span class="sxs-lookup"><span data-stu-id="643f2-132">Example 3: Delete commands that match specific criteria</span></span>

<span data-ttu-id="643f2-133">このコマンドは、 **CommandLine** パラメーターによって定義された特定の条件に一致するコマンドを削除します。</span><span class="sxs-lookup"><span data-stu-id="643f2-133">This command deletes commands that match specific criteria defined by the **CommandLine** parameter.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
```

```powershell
Clear-History -CommandLine *Help*, *Syntax
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   4 Get-Command Clear-History -ShowCommandInfo
   8 Clear-History -CommandLine *Help*, *Syntax
```

<span data-ttu-id="643f2-134">コマンドレットにより、 `Get-History` PowerShell セッションの履歴が表示されます。</span><span class="sxs-lookup"><span data-stu-id="643f2-134">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="643f2-135">`Clear-History` コマンド履歴を削除します。</span><span class="sxs-lookup"><span data-stu-id="643f2-135">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="643f2-136">**CommandLine** パラメーターは、 **Help** または end with **構文** を含むコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="643f2-136">The **CommandLine** parameter specifies commands that contain **Help** or end with **Syntax**.</span></span> <span data-ttu-id="643f2-137">`Get-History` 更新されたコマンドの履歴を表示し、コマンド **id 3**、 **id 5**、 **id 6**、および **id 7** が削除されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="643f2-137">`Get-History` displays the updated command history and confirms that commands **Id 3**, **Id 5**, **Id 6**, and **Id 7** were deleted.</span></span>

### <span data-ttu-id="643f2-138">例 4: Id 番号を指定してコマンドを削除する</span><span class="sxs-lookup"><span data-stu-id="643f2-138">Example 4: Delete commands by Id number</span></span>

<span data-ttu-id="643f2-139">このコマンドは、 **Id** を使用して特定の履歴項目を削除します。複数のコマンドを削除するには、 **Id** 番号のコンマ区切りリストを送信します。</span><span class="sxs-lookup"><span data-stu-id="643f2-139">This command deletes specific history items using the **Id**. To delete multiple commands, submit a comma-separated list of **Id** numbers.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-History
   3 Get-Help Get-Alias
   4 Get-Command Clear-History
   5 Get-Command Clear-History -Syntax
   6 Get-Command Clear-History -ShowCommandInfo
```

```powershell
Clear-History -Id 3, 5
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-History
   4 Get-Command Clear-History
   6 Get-Command Clear-History -ShowCommandInfo
   7 Get-History
   8 Clear-History -Id 3, 5
```

<span data-ttu-id="643f2-140">コマンドレットにより、 `Get-History` PowerShell セッションの履歴が表示されます。</span><span class="sxs-lookup"><span data-stu-id="643f2-140">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="643f2-141">`Clear-History` コマンド履歴を削除します。</span><span class="sxs-lookup"><span data-stu-id="643f2-141">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="643f2-142">**Id** パラメーターは、削除するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="643f2-142">The **Id** parameter specifies which commands to delete.</span></span> <span data-ttu-id="643f2-143">`Get-History` 更新されたコマンドの履歴を表示し、 **id 3** と **id 5** が削除されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="643f2-143">`Get-History` displays the updated command history and confirms that **Id 3** and **Id 5** were deleted.</span></span>

### <span data-ttu-id="643f2-144">例 5: Id 番号と数でコマンドを削除する</span><span class="sxs-lookup"><span data-stu-id="643f2-144">Example 5: Delete commands by Id number and count</span></span>

<span data-ttu-id="643f2-145">このコマンドは、 **Id** パラメーターと **Count** パラメーターを使用してコマンド履歴を削除します。</span><span class="sxs-lookup"><span data-stu-id="643f2-145">This command uses the **Id** and **Count** parameters to delete command history.</span></span> <span data-ttu-id="643f2-146">コマンドは、指定された **Id** から逆順に削除されます。</span><span class="sxs-lookup"><span data-stu-id="643f2-146">Commands are deleted from the specified **Id** in reverse order, newest to oldest.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
```

```powershell
Clear-History -Id 7 -Count 5
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
  11 Clear-History -Id 7 -Count 5
```

<span data-ttu-id="643f2-147">コマンドレットにより、 `Get-History` PowerShell セッションの履歴が表示されます。</span><span class="sxs-lookup"><span data-stu-id="643f2-147">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="643f2-148">`Clear-History` コマンド履歴を削除します。</span><span class="sxs-lookup"><span data-stu-id="643f2-148">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="643f2-149">**Id** パラメーターは、 **id 7** で始まることを指定します。</span><span class="sxs-lookup"><span data-stu-id="643f2-149">The **Id** parameter specifies to begin with **Id 7**.</span></span> <span data-ttu-id="643f2-150">**Count** パラメーターは、指定された **Id** を含む5つのコマンドを削除するように指定します。更新された `Get-History` コマンド履歴を表示し、5つのコマンドが削除されたことを確認します。 **id 3**  -  **id 7**。</span><span class="sxs-lookup"><span data-stu-id="643f2-150">The **Count** parameter specifies to delete five commands, inclusive of the specified **Id**. `Get-History` displays the updated command history and confirms that five commands were deleted, **Id 3** - **Id 7**.</span></span>

## <span data-ttu-id="643f2-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="643f2-151">PARAMETERS</span></span>

### <span data-ttu-id="643f2-152">-CommandLine</span><span class="sxs-lookup"><span data-stu-id="643f2-152">-CommandLine</span></span>

<span data-ttu-id="643f2-153">PowerShell セッションからコマンドの履歴を削除します。</span><span class="sxs-lookup"><span data-stu-id="643f2-153">Deletes command history from a PowerShell session.</span></span> <span data-ttu-id="643f2-154">文字列は完全に一致する必要があります。または、によって表示される PowerShell セッション履歴のコマンドと一致させるには、ワイルドカードを使用し `Get-History` ます。</span><span class="sxs-lookup"><span data-stu-id="643f2-154">The string must be an exact match or use wildcards to match commands in the PowerShell session history displayed by `Get-History`.</span></span> <span data-ttu-id="643f2-155">複数の文字列を入力すると、によって、 `Clear-History` 任意の文字列に一致するコマンドが削除されます。</span><span class="sxs-lookup"><span data-stu-id="643f2-155">If you enter more than one string, `Clear-History` deletes commands that match any of the strings.</span></span> <span data-ttu-id="643f2-156">**CommandLine** パラメーターは **Count** と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="643f2-156">The **CommandLine** parameter can be used with **Count**.</span></span>

<span data-ttu-id="643f2-157">スペースを含む文字列の場合は、単一引用符を使用します。</span><span class="sxs-lookup"><span data-stu-id="643f2-157">For strings with a space, use single quotations.</span></span> <span data-ttu-id="643f2-158">詳細については、「 [about_Quoting_Rules](About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="643f2-158">For more information, see [about_Quoting_Rules](About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: CommandLineParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="643f2-159">-カウント</span><span class="sxs-lookup"><span data-stu-id="643f2-159">-Count</span></span>

<span data-ttu-id="643f2-160">が削除する履歴エントリの数を指定し `Clear-History` ます。</span><span class="sxs-lookup"><span data-stu-id="643f2-160">Specifies the number of history entries that `Clear-History` deletes.</span></span> <span data-ttu-id="643f2-161">コマンドは、履歴内の最も古いエントリから順に削除されます。</span><span class="sxs-lookup"><span data-stu-id="643f2-161">Commands are deleted in order, beginning with the oldest entry in the history.</span></span>

<span data-ttu-id="643f2-162">**Count** パラメーターと **Id** パラメーターは一緒に使用できます。</span><span class="sxs-lookup"><span data-stu-id="643f2-162">The **Count** and **Id** parameters can be used together.</span></span> <span data-ttu-id="643f2-163">**Count** パラメーターは、指定した **Id** を含む、削除するコマンドの数を指定します。指定された **Id** から開始すると、コマンドは順番に逆順に削除されます。</span><span class="sxs-lookup"><span data-stu-id="643f2-163">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id**. Beginning at the specified **Id**, commands are deleted in reverse sequential order.</span></span> <span data-ttu-id="643f2-164">たとえば、 **Id** が30で **カウント** が10の場合、に `Clear-History` よって21から30までの項目が削除されます。</span><span class="sxs-lookup"><span data-stu-id="643f2-164">For example, if the **Id** is 30 and the **Count** is 10, `Clear-History` deletes items 21 through 30.</span></span>

<span data-ttu-id="643f2-165">**Count** パラメーターと **CommandLine** パラメーターは一緒に使用できます。</span><span class="sxs-lookup"><span data-stu-id="643f2-165">The **Count** and **CommandLine** parameters can be used together.</span></span> <span data-ttu-id="643f2-166">**カウント** は、コマンド **ライン** パラメーターの値と一致する、削除するコマンドの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="643f2-166">**Count** specifies the number of commands to delete that match **CommandLine** parameter value.</span></span> <span data-ttu-id="643f2-167">コマンドは順番に削除されます。</span><span class="sxs-lookup"><span data-stu-id="643f2-167">The commands are deleted in sequential order.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="643f2-168">-Id</span><span class="sxs-lookup"><span data-stu-id="643f2-168">-Id</span></span>

<span data-ttu-id="643f2-169">が削除するコマンド履歴 **Id** を指定し `Clear-History` ます。</span><span class="sxs-lookup"><span data-stu-id="643f2-169">Specifies the command history **Id** that `Clear-History` deletes.</span></span> <span data-ttu-id="643f2-170">**Id** 番号を表示するには、コマンドレットを使用し `Get-History` ます。</span><span class="sxs-lookup"><span data-stu-id="643f2-170">To display **Id** numbers, use the `Get-History` cmdlet.</span></span> <span data-ttu-id="643f2-171">**Id** 番号は順次で、コマンドは PowerShell セッション全体で **id** 番号を保持します。</span><span class="sxs-lookup"><span data-stu-id="643f2-171">The **Id** numbers are sequential and commands keep their **Id** number throughout a PowerShell session.</span></span> <span data-ttu-id="643f2-172">**Id** パラメーターは、 **Count** **および all** と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="643f2-172">The **Id** parameter can be used with **Count** and **Newest**.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: IDParameter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="643f2-173">-最新</span><span class="sxs-lookup"><span data-stu-id="643f2-173">-Newest</span></span>

<span data-ttu-id="643f2-174">**最新** のパラメーターを使用すると、によって `Clear-History` 履歴内の最新のエントリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="643f2-174">When the **Newest** parameter is used, `Clear-History` deletes the newest entries in the history.</span></span> <span data-ttu-id="643f2-175">既定では、は `Clear-History` 履歴内の最も古いエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="643f2-175">By default, `Clear-History` deletes the oldest entries in the history.</span></span>

<span data-ttu-id="643f2-176">**最新** のパラメーターは、 **Id** と **カウント** と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="643f2-176">The **Newest** parameter can be used with **Id** and **Count**.</span></span> <span data-ttu-id="643f2-177">**Count** パラメーターは、指定した **Id** を含む、削除するコマンドの数を指定します。指定された **Id** から開始すると、コマンドは順番に削除されます。</span><span class="sxs-lookup"><span data-stu-id="643f2-177">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id**. Beginning at the specified **Id**, commands are deleted in sequential order.</span></span> <span data-ttu-id="643f2-178">たとえば、 **Id** が30で **カウント** が10の場合、では `Clear-History` 30 ~ 39 の項目が削除されます。</span><span class="sxs-lookup"><span data-stu-id="643f2-178">For example, if the **Id** is 30 and the **Count** is 10, `Clear-History` deletes items 30 through 39.</span></span>

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

### <span data-ttu-id="643f2-179">-Confirm</span><span class="sxs-lookup"><span data-stu-id="643f2-179">-Confirm</span></span>

<span data-ttu-id="643f2-180">コマンドレットを実行する前に確認メッセージを表示 `Clear-History` します。</span><span class="sxs-lookup"><span data-stu-id="643f2-180">Prompts you for confirmation before running the `Clear-History` cmdlet.</span></span>

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

### <span data-ttu-id="643f2-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="643f2-181">-WhatIf</span></span>

<span data-ttu-id="643f2-182">コマンドレットを実行した場合の動作 `Clear-History` を示します。</span><span class="sxs-lookup"><span data-stu-id="643f2-182">Shows what would happen if the `Clear-History` cmdlet runs.</span></span> <span data-ttu-id="643f2-183">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="643f2-183">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="643f2-184">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="643f2-184">CommonParameters</span></span>

<span data-ttu-id="643f2-185">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="643f2-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="643f2-186">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="643f2-186">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="643f2-187">入力</span><span class="sxs-lookup"><span data-stu-id="643f2-187">INPUTS</span></span>

### <span data-ttu-id="643f2-188">なし</span><span class="sxs-lookup"><span data-stu-id="643f2-188">None</span></span>

<span data-ttu-id="643f2-189">パイプを使用してオブジェクトをにパイプすることはできません `Clear-History` 。</span><span class="sxs-lookup"><span data-stu-id="643f2-189">You cannot pipe objects to `Clear-History`.</span></span>

## <span data-ttu-id="643f2-190">出力</span><span class="sxs-lookup"><span data-stu-id="643f2-190">OUTPUTS</span></span>

### <span data-ttu-id="643f2-191">なし</span><span class="sxs-lookup"><span data-stu-id="643f2-191">None</span></span>

<span data-ttu-id="643f2-192">`Clear-History` は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="643f2-192">`Clear-History` does not generate any output.</span></span>

## <span data-ttu-id="643f2-193">注</span><span class="sxs-lookup"><span data-stu-id="643f2-193">NOTES</span></span>

<span data-ttu-id="643f2-194">PowerShell セッションの履歴は、PowerShell セッション中に入力されたコマンドの一覧です。</span><span class="sxs-lookup"><span data-stu-id="643f2-194">The PowerShell session history is a list of the commands entered during a PowerShell session.</span></span> <span data-ttu-id="643f2-195">履歴を表示し、コマンドを追加、削除できます。また履歴からコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="643f2-195">You can view the history, add and delete commands, and run commands from the history.</span></span> <span data-ttu-id="643f2-196">詳細については、「 [about_History](About/about_History.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="643f2-196">For more information, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="643f2-197">セッション履歴は、 **Psreadline** モジュールによって保持されている履歴とは別に管理されます。</span><span class="sxs-lookup"><span data-stu-id="643f2-197">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="643f2-198">どちらの履歴も、 **Psreadline** が読み込まれたセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="643f2-198">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="643f2-199">このコマンドレットは、セッション履歴でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="643f2-199">This cmdlet only works with the session history.</span></span> <span data-ttu-id="643f2-200">詳細については、「」、「 [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="643f2-200">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="643f2-201">関連リンク</span><span class="sxs-lookup"><span data-stu-id="643f2-201">RELATED LINKS</span></span>

[<span data-ttu-id="643f2-202">about_History</span><span class="sxs-lookup"><span data-stu-id="643f2-202">about_History</span></span>](About/about_History.md)

[<span data-ttu-id="643f2-203">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="643f2-203">about_PSReadLine</span></span>](../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="643f2-204">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="643f2-204">about_Quoting_Rules</span></span>](About/about_Quoting_Rules.md)

[<span data-ttu-id="643f2-205">Add-History</span><span class="sxs-lookup"><span data-stu-id="643f2-205">Add-History</span></span>](Add-History.md)

[<span data-ttu-id="643f2-206">Get-History</span><span class="sxs-lookup"><span data-stu-id="643f2-206">Get-History</span></span>](Get-History.md)

[<span data-ttu-id="643f2-207">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="643f2-207">Invoke-History</span></span>](Invoke-History.md)

[<span data-ttu-id="643f2-208">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="643f2-208">Get-PSReadLineOption</span></span>](/powershell/module/psreadline/get-psreadlineoption)

[<span data-ttu-id="643f2-209">設定-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="643f2-209">Set-PSReadLineOption</span></span>](/powershell/module/psreadline/set-psreadlineoption)

