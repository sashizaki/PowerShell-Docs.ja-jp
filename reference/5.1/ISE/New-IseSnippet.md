---
external help file: ISE-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/new-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-IseSnippet
ms.openlocfilehash: 0ed1c2913fc7531574bfbdd435a002d60931d24a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212379"
---
# <span data-ttu-id="a2c5a-103">New-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="a2c5a-103">New-IseSnippet</span></span>

## <span data-ttu-id="a2c5a-104">概要</span><span class="sxs-lookup"><span data-stu-id="a2c5a-104">SYNOPSIS</span></span>
<span data-ttu-id="a2c5a-105">Windows PowerShell ISE のコード スニペットを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-105">Creates a Windows PowerShell ISE code snippet.</span></span>

## <span data-ttu-id="a2c5a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a2c5a-106">SYNTAX</span></span>

```
New-IseSnippet [-Title] <String> [-Description] <String> [-Text] <String> [-Author <String>]
 [-CaretOffset <Int32>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="a2c5a-107">Description</span><span class="sxs-lookup"><span data-stu-id="a2c5a-107">DESCRIPTION</span></span>

<span data-ttu-id="a2c5a-108">コマンドレットにより、 `New-ISESnippet` Windows PowerShell ISE 用の再利用可能なテキスト "スニペット" が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-108">The `New-ISESnippet` cmdlet creates a reusable text "snippet" for Windows PowerShell ISE.</span></span> <span data-ttu-id="a2c5a-109">スニペットを使用すると、Windows PowerShell ISE のスクリプト ペインまたはコマンド ペインにテキストを追加できます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-109">You can use snippets to add text to the Script pane or Command pane in Windows PowerShell ISE.</span></span> <span data-ttu-id="a2c5a-110">このコマンドレットは、Windows PowerShell ISE でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-110">This cmdlet is available only in Windows PowerShell ISE.</span></span>

<span data-ttu-id="a2c5a-111">Windows PowerShell 3.0 以降、Windows PowerShell ISE には組み込みのスニペットのコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-111">Beginning in Windows PowerShell 3.0, Windows PowerShell ISE includes a collection of built-in snippets.</span></span> <span data-ttu-id="a2c5a-112">`New-ISESnippet`コマンドレットを使用すると、独自のスニペットを作成して組み込みコレクションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-112">The `New-ISESnippet` cmdlet lets you create your own snippets to add to the built-in collection.</span></span> <span data-ttu-id="a2c5a-113">スニペット ファイルは、表示、変更、追加、削除、および共有でき、Windows PowerShell モジュールに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-113">You can view, change, add, delete, and share snippet files and include them in Windows PowerShell modules.</span></span> <span data-ttu-id="a2c5a-114">Windows PowerShell ISE のスニペットを表示するには、[ **編集** ] メニューの [ **スニペットの開始** ] を選択するか、 <kbd>CTRL</kbd> + <kbd>J</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-114">To see snippets in Windows PowerShell ISE, from the **Edit** menu, select **Start Snippets** or press <kbd>CTRL</kbd>+<kbd>J</kbd>.</span></span>

<span data-ttu-id="a2c5a-115">`New-ISESnippet`コマンドレットにより、指定した `<Title>.Snippets.ps1xml` タイトルのファイルがディレクトリに作成され `$home\Documents\WindowsPowerShell\Snippets` ます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-115">The `New-ISESnippet` cmdlet creates a `<Title>.Snippets.ps1xml` file in the `$home\Documents\WindowsPowerShell\Snippets` directory with the title that you specify.</span></span> <span data-ttu-id="a2c5a-116">作成しているモジュールにスニペット ファイルを含めるには、モジュール ディレクトリの Snippets サブディレクトリにスニペット ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-116">To include a snippet file in a module that you are authoring, add the snippet file to a Snippets subdirectory of your module directory.</span></span>

<span data-ttu-id="a2c5a-117">実行ポリシーが **Restricted** または **AllSigned** のセッションでは、ユーザーが作成したスニペットを使用できません。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-117">You cannot use user-created snippets in a session in which the execution policy is **Restricted** or **AllSigned** .</span></span>

<span data-ttu-id="a2c5a-118">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-118">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="a2c5a-119">例</span><span class="sxs-lookup"><span data-stu-id="a2c5a-119">EXAMPLES</span></span>

### <span data-ttu-id="a2c5a-120">例 1: Comment-Based ヘルプスニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="a2c5a-120">Example 1: Create a Comment-Based help snippet</span></span>

```
New-IseSnippet -Title Comment-BasedHelp -Description "A template for comment-based help." -Text "<#
    .SYNOPSIS

    .DESCRIPTION
    .PARAMETER  <Parameter-Name>
    .INPUTS
    .OUTPUTS
    .EXAMPLE
    .LINK
#>"
```

<span data-ttu-id="a2c5a-121">このコマンドは、Windows PowerShell ISE の Comment-BasedHelp スニペットを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-121">This command creates a Comment-BasedHelp snippet for Windows PowerShell ISE.</span></span> <span data-ttu-id="a2c5a-122">これにより、という名前のファイルが `Comment-BasedHelp.snippets.ps1xml` ユーザーのスニペットディレクトリに作成さ `$home\Documents\WindowsPowerShell\Snippets` れます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-122">It creates a file named `Comment-BasedHelp.snippets.ps1xml` in the user's Snippets directory `$home\Documents\WindowsPowerShell\Snippets`.</span></span>

### <span data-ttu-id="a2c5a-123">例 2: 必須のスニペットを作成する</span><span class="sxs-lookup"><span data-stu-id="a2c5a-123">Example 2: Create a mandatory snippet</span></span>

```
$M = @'
Param
(
  [parameter(Mandatory=$true)]
  [String[]]
  $<ParameterName>
)
'@

New-ISESnippet -Text $M -Title Mandatory -Description "Adds a mandatory function parameter." -Author "Patti Fuller, Fabrikam Corp." -Force
```

<span data-ttu-id="a2c5a-124">この例では、Windows PowerShell ISE に **必須** という名前のスニペットを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-124">This example creates a snippet named **Mandatory** for Windows PowerShell ISE.</span></span> <span data-ttu-id="a2c5a-125">最初のコマンドは、変数にスニペットのテキストを保存し `$M` ます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-125">The first command saves the snippet text in the `$M` variable.</span></span> <span data-ttu-id="a2c5a-126">2番目のコマンドは、 `New-ISESnippet` コマンドレットを使用してスニペットを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-126">The second command uses the `New-ISESnippet` cmdlet to create the snippet.</span></span> <span data-ttu-id="a2c5a-127">このコマンドは、 **Force** パラメーターを使用して、同じ名前で前のスニペットを上書きします。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-127">The command uses the **Force** parameter to overwrite a previous snippet with the same name.</span></span>

### <span data-ttu-id="a2c5a-128">例 3: 必須のスニペットをフォルダーから目的のフォルダーにコピーする</span><span class="sxs-lookup"><span data-stu-id="a2c5a-128">Example 3: Copy a mandatory snippet from a folder to a destination folder</span></span>

```
Copy-Item "$Home\Documents\WindowsPowerShell\Snippets\Mandatory.Snippets.ps1xml" -Destination "\\Server\Share"
```

<span data-ttu-id="a2c5a-129">このコマンドは、コマンドレットを使用して、 `Copy-Item` がファイル共有に置かれているフォルダーから **必須** のスニペットをコピーし `New-ISESnippet` ます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-129">This command uses the `Copy-Item` cmdlet to copy the **Mandatory** snippet from the folder where `New-ISESnippet` places it to the Server\Share file share.</span></span>

## <span data-ttu-id="a2c5a-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a2c5a-130">PARAMETERS</span></span>

### <span data-ttu-id="a2c5a-131">-作成者</span><span class="sxs-lookup"><span data-stu-id="a2c5a-131">-Author</span></span>

<span data-ttu-id="a2c5a-132">スニペットの作成者を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-132">Specifies the author of the snippet.</span></span> <span data-ttu-id="a2c5a-133">作成者フィールドは、スニペット ファイルに表示されますが、Windows PowerShell ISE でスニペットの名前をクリックしたときに表示されません。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-133">The author field appears in the snippet file, but it does not appear when you click the snippet name in Windows PowerShell ISE.</span></span>

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

### <span data-ttu-id="a2c5a-134">-CaretOffset</span><span class="sxs-lookup"><span data-stu-id="a2c5a-134">-CaretOffset</span></span>

<span data-ttu-id="a2c5a-135">このコマンドレットがカーソルを配置するスニペットテキストの文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-135">Specifies the character of the snippet text that this cmdlet places the cursor on.</span></span> <span data-ttu-id="a2c5a-136">カーソルの位置を表す整数を入力します。"1" は、テキストの最初の文字を表します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-136">Enter an integer that represents the cursor position, with "1" representing the first character of text.</span></span> <span data-ttu-id="a2c5a-137">既定値の 0 (ゼロ) の場合、テキストの最初の文字の直前にカーソルが配置されます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-137">The default value, 0 (zero), places the cursor immediately before the first character of text.</span></span> <span data-ttu-id="a2c5a-138">このパラメーターは、スニペットのテキストをインデントする機能は提供しません。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-138">This parameter does not indent the snippet text.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2c5a-139">-Description</span><span class="sxs-lookup"><span data-stu-id="a2c5a-139">-Description</span></span>

<span data-ttu-id="a2c5a-140">スニペットの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-140">Specifies a description of the snippet.</span></span> <span data-ttu-id="a2c5a-141">説明の値は、Windows PowerShell ISE でスニペット名をクリックしたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-141">The description value appears when you click the snippet name in Windows PowerShell ISE.</span></span> <span data-ttu-id="a2c5a-142">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-142">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2c5a-143">-Force</span><span class="sxs-lookup"><span data-stu-id="a2c5a-143">-Force</span></span>

<span data-ttu-id="a2c5a-144">このコマンドレットが同じ場所にある同じ名前のスニペットファイルを上書きすることを示します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-144">Indicates that this cmdlet overwrites snippet files with the same name in the same location.</span></span> <span data-ttu-id="a2c5a-145">既定で `New-ISESnippet` は、はファイルを上書きしません。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-145">By default, `New-ISESnippet` does not overwrite files.</span></span>

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

### <span data-ttu-id="a2c5a-146">-Text</span><span class="sxs-lookup"><span data-stu-id="a2c5a-146">-Text</span></span>

<span data-ttu-id="a2c5a-147">スニペットを選択するときに追加されるテキスト値を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-147">Specifies the text value that is added when you select the snippet.</span></span> <span data-ttu-id="a2c5a-148">スニペットのテキストは、Windows PowerShell ISE でスニペット名をクリックしたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-148">The snippet text appears when you click the snippet name in Windows PowerShell ISE.</span></span> <span data-ttu-id="a2c5a-149">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-149">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2c5a-150">-Title</span><span class="sxs-lookup"><span data-stu-id="a2c5a-150">-Title</span></span>

<span data-ttu-id="a2c5a-151">スニペットのタイトルまたは名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-151">Specifies a title or name for the snippet.</span></span> <span data-ttu-id="a2c5a-152">このタイトルはスニペット ファイルの名前にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-152">The title also names the snippet file.</span></span> <span data-ttu-id="a2c5a-153">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-153">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2c5a-154">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2c5a-154">CommonParameters</span></span>

<span data-ttu-id="a2c5a-155">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a2c5a-156">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a2c5a-157">入力</span><span class="sxs-lookup"><span data-stu-id="a2c5a-157">INPUTS</span></span>

### <span data-ttu-id="a2c5a-158">なし</span><span class="sxs-lookup"><span data-stu-id="a2c5a-158">None</span></span>

<span data-ttu-id="a2c5a-159">このコマンドレットはパイプラインから入力を取得しません。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-159">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="a2c5a-160">出力</span><span class="sxs-lookup"><span data-stu-id="a2c5a-160">OUTPUTS</span></span>

### <span data-ttu-id="a2c5a-161">なし</span><span class="sxs-lookup"><span data-stu-id="a2c5a-161">None</span></span>

<span data-ttu-id="a2c5a-162">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-162">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a2c5a-163">注</span><span class="sxs-lookup"><span data-stu-id="a2c5a-163">NOTES</span></span>

<span data-ttu-id="a2c5a-164">`New-IseSnippet` 新しいユーザーが作成したスニペットを types.ps1xml ファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-164">`New-IseSnippet` stores new user-created snippets in unsigned .ps1xml files.</span></span> <span data-ttu-id="a2c5a-165">そのため、Windows PowerShell は、実行ポリシーが **AllSigned** または **Restricted** のセッションにこれらを追加できません。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-165">As such, Windows PowerShell cannot add them to a session in which the execution policy is **AllSigned** or **Restricted** .</span></span> <span data-ttu-id="a2c5a-166">**Restricted** または **AllSigned** セッションでは、ユーザーが作成した署名されていないスニペットを作成、取得、およびインポートできますが、それらをセッションで使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-166">In a **Restricted** or **AllSigned** session, you can create, get, and import unsigned user-created snippets, but you cannot use them in the session.</span></span>

<span data-ttu-id="a2c5a-167">`New-IseSnippet`**制限付き** セッションまたは **AllSigned** セッションでコマンドレットを使用すると、スニペットが作成されますが、Windows PowerShell が新しく作成されたスニペットをセッションに追加しようとすると、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-167">If you use the `New-IseSnippet` cmdlet in a **Restricted** or **AllSigned** session, the snippet is created, but an error message appears when Windows PowerShell tries to add the newly created snippet to the session.</span></span> <span data-ttu-id="a2c5a-168">新しいスニペット (およびその他のユーザーが作成した署名されていないスニペット) を使用するには、実行ポリシーを変更してから Windows PowerShell ISE を再起動します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-168">To use the new snippet (and other unsigned user-created snippets), change the execution policy, and then restart Windows PowerShell ISE.</span></span>

<span data-ttu-id="a2c5a-169">Windows PowerShell 実行ポリシーの詳細については、「about_Execution_Policies」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-169">For more information about Windows PowerShell execution policies, see about_Execution_Policies.</span></span>

- <span data-ttu-id="a2c5a-170">スニペットを変更するには、スニペットファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-170">To change a snippet, edit the snippet file.</span></span> <span data-ttu-id="a2c5a-171">スニペットファイルは Windows PowerShell ISE のスクリプトウィンドウで編集できます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-171">You can edit snippet files in the Script pane of Windows PowerShell ISE.</span></span>
- <span data-ttu-id="a2c5a-172">追加したスニペットを削除するには、スニペットファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-172">To delete a snippet that you added, delete the snippet file.</span></span>
- <span data-ttu-id="a2c5a-173">組み込みのスニペットを削除することはできませんが、"$psise を使用すると、組み込みのスニペットをすべて非表示にすることができます。Options. ShowDefaultSnippets = $false "コマンド。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-173">You cannot delete a built-in snippet, but you can hide all built-in snippets by using the "$psise.Options.ShowDefaultSnippets=$false" command.</span></span>
- <span data-ttu-id="a2c5a-174">組み込みのスニペットと同じ名前を持つスニペットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-174">You can create a snippet that has the same name as a built-in snippet.</span></span> <span data-ttu-id="a2c5a-175">両方のスニペットが、Windows PowerShell ISE のスニペット メニューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2c5a-175">Both snippets appear in the snippet menu in Windows PowerShell ISE.</span></span>

## <span data-ttu-id="a2c5a-176">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a2c5a-176">RELATED LINKS</span></span>

[<span data-ttu-id="a2c5a-177">Get-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="a2c5a-177">Get-IseSnippet</span></span>](Get-IseSnippet.md)

[<span data-ttu-id="a2c5a-178">Import-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="a2c5a-178">Import-IseSnippet</span></span>](Import-IseSnippet.md)
