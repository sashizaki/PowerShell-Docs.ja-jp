---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unblock-File
ms.openlocfilehash: 8bbfe761a71b38b541f23730d84eb0023a059318
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602621"
---
# <span data-ttu-id="63024-102">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="63024-102">Unblock-File</span></span>

## <span data-ttu-id="63024-103">概要</span><span class="sxs-lookup"><span data-stu-id="63024-103">SYNOPSIS</span></span>
<span data-ttu-id="63024-104">インターネットからダウンロードされたファイルのブロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="63024-104">Unblocks files that were downloaded from the Internet.</span></span>

## <span data-ttu-id="63024-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="63024-105">SYNTAX</span></span>

### <span data-ttu-id="63024-106">ByPath (既定値)</span><span class="sxs-lookup"><span data-stu-id="63024-106">ByPath (Default)</span></span>

```
Unblock-File [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="63024-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="63024-107">ByLiteralPath</span></span>

```
Unblock-File -LiteralPath <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="63024-108">Description</span><span class="sxs-lookup"><span data-stu-id="63024-108">DESCRIPTION</span></span>

<span data-ttu-id="63024-109">`Unblock-File`コマンドレットを使用すると、インターネットからダウンロードされたファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="63024-109">The `Unblock-File` cmdlet lets you open files that were downloaded from the Internet.</span></span> <span data-ttu-id="63024-110">これにより、powershell の実行ポリシーが **RemoteSigned** の場合でも、インターネットからダウンロードされた powershell スクリプトファイルのブロックが解除され、実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="63024-110">It unblocks PowerShell script files that were downloaded from the Internet so you can run them, even when the PowerShell execution policy is **RemoteSigned**.</span></span> <span data-ttu-id="63024-111">既定では、信頼されていないファイルからコンピューターを保護するために、これらのファイルはブロックされています。</span><span class="sxs-lookup"><span data-stu-id="63024-111">By default, these files are blocked to protect the computer from untrusted files.</span></span>

<span data-ttu-id="63024-112">コマンドレットを使用する前に、 `Unblock-File` ファイルとそのソースを確認し、開いても安全であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63024-112">Before using the `Unblock-File` cmdlet, review the file and its source and verify that it is safe to open.</span></span>

<span data-ttu-id="63024-113">内部的には、 `Unblock-File` コマンドレットは、インターネットからダウンロードされたことを示す値が "3" である、ゾーン識別子の代替データストリームを削除します。</span><span class="sxs-lookup"><span data-stu-id="63024-113">Internally, the `Unblock-File` cmdlet removes the Zone.Identifier alternate data stream, which has a value of "3" to indicate that it was downloaded from the Internet.</span></span>

<span data-ttu-id="63024-114">PowerShell 実行ポリシーの詳細については、「 [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63024-114">For more information about PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

<span data-ttu-id="63024-115">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="63024-115">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="63024-116">例</span><span class="sxs-lookup"><span data-stu-id="63024-116">EXAMPLES</span></span>

### <span data-ttu-id="63024-117">例 1: ファイルのブロックを解除する</span><span class="sxs-lookup"><span data-stu-id="63024-117">Example 1: Unblock a file</span></span>

<span data-ttu-id="63024-118">このコマンドは、PowerShellTips.chm ファイルをブロック解除します。</span><span class="sxs-lookup"><span data-stu-id="63024-118">This command unblocks the PowerShellTips.chm file.</span></span>

```
PS C:\> Unblock-File -Path C:\Users\User01\Documents\Downloads\PowerShellTips.chm
```

### <span data-ttu-id="63024-119">例 2: 複数のファイルのブロックを解除する</span><span class="sxs-lookup"><span data-stu-id="63024-119">Example 2: Unblock multiple files</span></span>

<span data-ttu-id="63024-120">このコマンドは、 `C:\Downloads` 名前に "PowerShell" が含まれているディレクトリ内のすべてのファイルのブロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="63024-120">This command unblocks all of the files in the `C:\Downloads` directory whose names include "PowerShell".</span></span> <span data-ttu-id="63024-121">すべてのファイルが安全なことを確認してから、コマンドを実行してください。</span><span class="sxs-lookup"><span data-stu-id="63024-121">Do not run a command like this one until you have verified that all files are safe.</span></span>

```
PS C:\> dir C:\Downloads\*PowerShell* | Unblock-File
```

### <span data-ttu-id="63024-122">例 3: スクリプトを検索してブロックを解除する</span><span class="sxs-lookup"><span data-stu-id="63024-122">Example 3: Find and unblock scripts</span></span>

<span data-ttu-id="63024-123">このコマンドは、PowerShell スクリプトを検索してブロックを解除する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="63024-123">This command shows how to find and unblock PowerShell scripts.</span></span>

<span data-ttu-id="63024-124">最初のコマンドは、 *Get Item* コマンドレット get Files の **stream** パラメーターを、ゾーン識別子ストリームと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="63024-124">The first command uses the **Stream** parameter of the *Get-Item* cmdlet get files with the Zone.Identifier stream.</span></span>

<span data-ttu-id="63024-125">2番目のコマンドは、実行ポリシーが **RemoteSigned** されている PowerShell セッションでブロックされているスクリプトを実行するとどうなるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="63024-125">The second command shows what happens when you run a blocked script in a PowerShell session in which the execution policy is **RemoteSigned**.</span></span> <span data-ttu-id="63024-126">RemoteSigned ポリシーにより、デジタル署名されている場合を除き、インターネットからダウンロードされたスクリプトの実行は防止されます。</span><span class="sxs-lookup"><span data-stu-id="63024-126">The RemoteSigned policy prevents you from running scripts that are downloaded from the Internet unless they are digitally signed.</span></span>

<span data-ttu-id="63024-127">3番目のコマンドは、コマンドレットを使用して、 `Unblock-File` セッションで実行できるようにスクリプトのブロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="63024-127">The third command uses the `Unblock-File` cmdlet to unblock the script so it can run in the session.</span></span>

```
PS C:\> Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue
   FileName: C:\ps-test\Start-ActivityTracker.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

PS C:\> C:\ps-test\Start-ActivityTracker.ps1
c:\ps-test\Start-ActivityTracker.ps1 : File c:\ps-test\Start-ActivityTracker.ps1 cannot
be loaded. The file c:\ps-test\Start-ActivityTracker.ps1 is not digitally signed. The script
will not execute on the system. For more information, see about_Execution_Policies.

At line:1 char:1
+ c:\ps-test\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

PS C:\> Get-Item C:\ps-test\Start-ActivityTracker.ps1 | Unblock-File
```

## <span data-ttu-id="63024-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="63024-128">PARAMETERS</span></span>

### <span data-ttu-id="63024-129">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="63024-129">-LiteralPath</span></span>

<span data-ttu-id="63024-130">ブロックを解除するファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="63024-130">Specifies the files to unblock.</span></span> <span data-ttu-id="63024-131">**Path** と異なり、**LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="63024-131">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="63024-132">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="63024-132">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="63024-133">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="63024-133">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="63024-134">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="63024-134">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="63024-135">-Path</span><span class="sxs-lookup"><span data-stu-id="63024-135">-Path</span></span>

<span data-ttu-id="63024-136">ブロックを解除するファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="63024-136">Specifies the files to unblock.</span></span> <span data-ttu-id="63024-137">ワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="63024-137">Wildcard characters are supported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="63024-138">-Confirm</span><span class="sxs-lookup"><span data-stu-id="63024-138">-Confirm</span></span>

<span data-ttu-id="63024-139">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63024-139">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="63024-140">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="63024-140">-WhatIf</span></span>

<span data-ttu-id="63024-141">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="63024-141">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="63024-142">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="63024-142">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="63024-143">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="63024-143">CommonParameters</span></span>

<span data-ttu-id="63024-144">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="63024-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="63024-145">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63024-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="63024-146">入力</span><span class="sxs-lookup"><span data-stu-id="63024-146">INPUTS</span></span>

### <span data-ttu-id="63024-147">System.String</span><span class="sxs-lookup"><span data-stu-id="63024-147">System.String</span></span>

<span data-ttu-id="63024-148">パイプを使用して、ファイルパスをにパイプすることができ `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="63024-148">You can pipe a file path to `Unblock-File`.</span></span>

## <span data-ttu-id="63024-149">出力</span><span class="sxs-lookup"><span data-stu-id="63024-149">OUTPUTS</span></span>

### <span data-ttu-id="63024-150">なし</span><span class="sxs-lookup"><span data-stu-id="63024-150">None</span></span>

<span data-ttu-id="63024-151">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="63024-151">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="63024-152">注</span><span class="sxs-lookup"><span data-stu-id="63024-152">NOTES</span></span>

- <span data-ttu-id="63024-153">PowerShell 7 で macOS のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="63024-153">Support for macOS was added in PowerShell 7.</span></span>
- <span data-ttu-id="63024-154">`Unblock-File`コマンドレットは、ファイルシステムドライブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="63024-154">The `Unblock-File` cmdlet works only in file system drives.</span></span>
- <span data-ttu-id="63024-155">`Unblock-File`ファイルエクスプローラーの [**プロパティ**] ダイアログボックスの [**ブロック解除**] ボタンと同じ操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="63024-155">`Unblock-File` performs the same operation as the **Unblock** button on the **Properties** dialog box in File Explorer.</span></span>
- <span data-ttu-id="63024-156">ブロックされていないファイルに対してコマンドレットを使用しても、コマンドはブロックされていない `Unblock-File` ファイルには影響せず、コマンドレットはエラーを生成しません。</span><span class="sxs-lookup"><span data-stu-id="63024-156">If you use the `Unblock-File` cmdlet on a file that is not blocked, the command has no effect on the unblocked file and the cmdlet does not generate errors.</span></span>

## <span data-ttu-id="63024-157">関連リンク</span><span class="sxs-lookup"><span data-stu-id="63024-157">RELATED LINKS</span></span>

[<span data-ttu-id="63024-158">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="63024-158">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="63024-159">Get-Item</span><span class="sxs-lookup"><span data-stu-id="63024-159">Get-Item</span></span>](../Microsoft.PowerShell.Management/Get-Item.md)

[<span data-ttu-id="63024-160">Out-File</span><span class="sxs-lookup"><span data-stu-id="63024-160">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="63024-161">FileSystem プロバイダー</span><span class="sxs-lookup"><span data-stu-id="63024-161">FileSystem Provider</span></span>](../Microsoft.PowerShell.Core/about/about_FileSystem_Provider.md)
