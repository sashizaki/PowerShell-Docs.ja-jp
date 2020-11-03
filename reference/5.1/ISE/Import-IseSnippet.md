---
external help file: ISE-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/import-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-IseSnippet
ms.openlocfilehash: 810be675fc593f665ccc6f3d5b86ac2f6b633863
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212384"
---
# <span data-ttu-id="ea702-103">Import-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="ea702-103">Import-IseSnippet</span></span>

## <span data-ttu-id="ea702-104">概要</span><span class="sxs-lookup"><span data-stu-id="ea702-104">SYNOPSIS</span></span>
<span data-ttu-id="ea702-105">現在のセッションに ISE スニペットをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ea702-105">Imports ISE snippets into the current session</span></span>

## <span data-ttu-id="ea702-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ea702-106">SYNTAX</span></span>

### <span data-ttu-id="ea702-107">FromFolder (既定値)</span><span class="sxs-lookup"><span data-stu-id="ea702-107">FromFolder (Default)</span></span>

```
Import-IseSnippet [-Path] <String> [-Recurse] [<CommonParameters>]
```

### <span data-ttu-id="ea702-108">FromModule</span><span class="sxs-lookup"><span data-stu-id="ea702-108">FromModule</span></span>

```
Import-IseSnippet [-Recurse] -Module <String> [-ListAvailable] [<CommonParameters>]
```

## <span data-ttu-id="ea702-109">Description</span><span class="sxs-lookup"><span data-stu-id="ea702-109">DESCRIPTION</span></span>

<span data-ttu-id="ea702-110">`Import-IseSnippet`コマンドレットでは、再利用可能なテキスト "スニペット" をモジュールまたはディレクトリから現在のセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="ea702-110">The `Import-IseSnippet` cmdlet imports reusable text "snippets" from a module or a directory into the current session.</span></span> <span data-ttu-id="ea702-111">スニペットは、Windows PowerShell ISE ですぐに使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea702-111">The snippets are immediately available for use in Windows PowerShell ISE.</span></span> <span data-ttu-id="ea702-112">このコマンドレットは、Windows PowerShell Integrated Scripting Environment (ISE) でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="ea702-112">This cmdlet works only in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

<span data-ttu-id="ea702-113">インポートされたスニペットを表示して使用するには、Windows PowerShell ISE の [ **編集** ] メニューの [ **スニペットの開始** ] をクリックするか、 <kbd>Ctrl</kbd> + <kbd>J</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ea702-113">To view and use the imported snippets, from the Windows PowerShell ISE **Edit** menu, click **Start Snippets** or press <kbd>Ctrl</kbd>+<kbd>J</kbd>.</span></span>

<span data-ttu-id="ea702-114">インポートしたスニペットは、現在のセッションでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea702-114">Imported snippets are available only in the current session.</span></span> <span data-ttu-id="ea702-115">スニペットをすべての Windows PowerShell ISE セッションにインポートするに `Import-IseSnippet` は、Windows PowerShell プロファイルにコマンドを追加するか、スニペットファイルをローカルのスニペットディレクトリにコピーし `$home\Documents\WindowsPowershell\Snippets` ます。</span><span class="sxs-lookup"><span data-stu-id="ea702-115">To import the snippets into all Windows PowerShell ISE sessions, add an `Import-IseSnippet` command to your Windows PowerShell profile or copy the snippet files to your local snippets directory `$home\Documents\WindowsPowershell\Snippets`.</span></span>

<span data-ttu-id="ea702-116">スニペットをインポートするには、スニペット XML で Windows PowerShell ISE スニペット用に適切に書式設定し、Snippet.ps1XML ファイルに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea702-116">To import snippets, they must be properly formatted in the snippet XML for Windows PowerShell ISE snippets and saved in Snippet.ps1xml files.</span></span> <span data-ttu-id="ea702-117">対象となるスニペットを作成するには、コマンドレットを使用し `New-IseSnippet` ます。</span><span class="sxs-lookup"><span data-stu-id="ea702-117">To create eligible snippets, use the `New-IseSnippet` cmdlet.</span></span> <span data-ttu-id="ea702-118">`New-IseSnippet``<SnippetTitle>.Snippets.ps1xml`ディレクトリにファイルを作成し `$home\Documents\WindowsPowerShell\Snippets` ます。</span><span class="sxs-lookup"><span data-stu-id="ea702-118">`New-IseSnippet` creates a `<SnippetTitle>.Snippets.ps1xml` file in the `$home\Documents\WindowsPowerShell\Snippets` directory.</span></span> <span data-ttu-id="ea702-119">スニペットは、Windows PowerShell モジュールの Snippets ディレクトリまたはその他の任意のディレクトリにコピーしたり移動したりできます。</span><span class="sxs-lookup"><span data-stu-id="ea702-119">You can move or copy the snippets to the Snippets directory of a Windows PowerShell module, or to any other directory.</span></span>

<span data-ttu-id="ea702-120">`Get-IseSnippet`ローカルのスニペットディレクトリにユーザーが作成したスニペットを取得するコマンドレットは、インポートされたスニペットを取得しません。</span><span class="sxs-lookup"><span data-stu-id="ea702-120">The `Get-IseSnippet` cmdlet, which gets user-created snippets in the local snippets directory, does not get imported snippets.</span></span>

<span data-ttu-id="ea702-121">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ea702-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="ea702-122">例</span><span class="sxs-lookup"><span data-stu-id="ea702-122">EXAMPLES</span></span>

### <span data-ttu-id="ea702-123">例 1: ディレクトリからスニペットをインポートする</span><span class="sxs-lookup"><span data-stu-id="ea702-123">Example 1: Import snippets from a directory</span></span>

<span data-ttu-id="ea702-124">この例では、ディレクトリから現在のセッションにスニペットをインポートし `\\Server01\Public\Snippets` ます。</span><span class="sxs-lookup"><span data-stu-id="ea702-124">This example imports the snippets from the `\\Server01\Public\Snippets` directory into the current session.</span></span> <span data-ttu-id="ea702-125">この例では、 **再帰** パラメーターを使用して、スニペットディレクトリのすべてのサブディレクトリからスニペットを取得しています。</span><span class="sxs-lookup"><span data-stu-id="ea702-125">It uses the **Recurse** parameter to get snippets from all subdirectories of the Snippets directory.</span></span>

```powershell
Import-IseSnippet -Path \\Server01\Public\Snippets -Recurse
```

### <span data-ttu-id="ea702-126">例 2: モジュールからスニペットをインポートする</span><span class="sxs-lookup"><span data-stu-id="ea702-126">Example 2: Import snippets from a module</span></span>

<span data-ttu-id="ea702-127">この例では、 **SnippetModule** モジュールからスニペットをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ea702-127">This example imports the snippets from the **SnippetModule** module.</span></span> <span data-ttu-id="ea702-128">このコマンドは、コマンドの実行時に **SnippetModule** モジュールがユーザーのセッションにインポートされていない場合でも、 **ListAvailable** パラメーターを使用してスニペットをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ea702-128">The command uses the **ListAvailable** parameter to import the snippets even if the **SnippetModule** module is not imported into the user's session when the command runs.</span></span>

```powershell
Import-IseSnippet -Module SnippetModule -ListAvailable
```

### <span data-ttu-id="ea702-129">例 3: モジュールでスニペットを検索する</span><span class="sxs-lookup"><span data-stu-id="ea702-129">Example 3: Find snippets in modules</span></span>

<span data-ttu-id="ea702-130">この例では、PSModulePath 環境変数にインストールされているすべてのモジュールのスニペットを取得します。</span><span class="sxs-lookup"><span data-stu-id="ea702-130">This example gets snippets in all installed modules in the PSModulePath environment variable.</span></span>

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$_.fullname}
```

### <span data-ttu-id="ea702-131">例 4: すべてのモジュールスニペットをインポートする</span><span class="sxs-lookup"><span data-stu-id="ea702-131">Example 4: Import all module snippets</span></span>

<span data-ttu-id="ea702-132">この例では、すべてのインストールされているモジュールのすべてのスニペットを現在のセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="ea702-132">This example imports all snippets from all installed modules into the current session.</span></span> <span data-ttu-id="ea702-133">通常、このようなコマンドを実行する必要はありません。スニペットを持つモジュールは、モジュールをインポートするときに、コマンドレットを使用して `Import-IseSnippet` インポートします。</span><span class="sxs-lookup"><span data-stu-id="ea702-133">Typically, you don't need to run a command like this because modules that have snippets will use the `Import-IseSnippet` cmdlet to import them for you when the module is imported.</span></span>

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$psise.CurrentPowerShellTab.Snippets.Load($_)}
```

### <span data-ttu-id="ea702-134">例 5: すべてのモジュールスニペットをコピーする</span><span class="sxs-lookup"><span data-stu-id="ea702-134">Example 5: Copy all module snippets</span></span>

<span data-ttu-id="ea702-135">この例では、すべてのインストールされているモジュールから、現在のユーザーのスニペットディレクトリにスニペットファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ea702-135">This example copies the snippet files from all installed modules into the Snippets directory of the current user.</span></span> <span data-ttu-id="ea702-136">現在のセッションのみに影響を与えるインポートされたスニペットとは異なり、コピーされたスニペットはすべての Windows PowerShell ISE のセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea702-136">Unlike imported snippets, which affect only the current session, copied snippets are available in every Windows PowerShell ISE session.</span></span>

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    Copy-Item -Destination $home\Documents\WindowsPowerShell\Snippets
```

## <span data-ttu-id="ea702-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ea702-137">PARAMETERS</span></span>

### <span data-ttu-id="ea702-138">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="ea702-138">-ListAvailable</span></span>

<span data-ttu-id="ea702-139">このコマンドレットが、モジュールが現在のセッションにインポートされていない場合でも、コンピューターにインストールされているモジュールからスニペットを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="ea702-139">Indicates that this cmdlet gets snippets from modules that are installed on the computer, even if the modules are not imported into the current session.</span></span> <span data-ttu-id="ea702-140">このパラメーターを省略し、 **module** パラメーターで指定されているモジュールが現在のセッションにインポートされていない場合、モジュールからスニペットを取得しようとすると失敗します。</span><span class="sxs-lookup"><span data-stu-id="ea702-140">If this parameter is omitted, and the module that is specified by the **Module** parameter is not imported into the current session, the attempt to get the snippets from the module fails.</span></span>

<span data-ttu-id="ea702-141">このパラメーターは、 **Module** パラメーターがコマンドで使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="ea702-141">This parameter is valid only when the **Module** parameter is used in the command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FromModule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea702-142">-モジュール</span><span class="sxs-lookup"><span data-stu-id="ea702-142">-Module</span></span>

<span data-ttu-id="ea702-143">指定したモジュールからスニペットを現在のセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="ea702-143">Imports snippets from the specified module into the current session.</span></span> <span data-ttu-id="ea702-144">ワイルドカード文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ea702-144">Wildcard characters are not supported.</span></span>

<span data-ttu-id="ea702-145">このパラメーターは、モジュールパスのスニペットサブディレクトリ (など) の Snippet.ps1xml ファイルからスニペットをインポートし `$home\Documents\WindowsPowerShell\Modules\<ModuleName>\Snippets` ます。</span><span class="sxs-lookup"><span data-stu-id="ea702-145">This parameter imports snippets from Snippet.ps1xml files in the Snippets subdirectory in the module path, such as `$home\Documents\WindowsPowerShell\Modules\<ModuleName>\Snippets`.</span></span>

<span data-ttu-id="ea702-146">このパラメーターは、スタートアップ スクリプト (たとえば、モジュール マニフェストの **ScriptsToProcess** キーに指定するスクリプト) でモジュールの作成者が使用するために用意されています。</span><span class="sxs-lookup"><span data-stu-id="ea702-146">This parameter is designed to be used by module authors in a startup script, such as a script specified in the **ScriptsToProcess** key of a module manifest.</span></span> <span data-ttu-id="ea702-147">モジュール内のスニペットは、モジュールと共に自動的にインポートされませんが、コマンドを使用して `Import-IseSnippet` インポートできます。</span><span class="sxs-lookup"><span data-stu-id="ea702-147">Snippets in a module are not automatically imported with the module, but you can use an `Import-IseSnippet` command to import them.</span></span>

```yaml
Type: System.String
Parameter Sets: FromModule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea702-148">-Path</span><span class="sxs-lookup"><span data-stu-id="ea702-148">-Path</span></span>

<span data-ttu-id="ea702-149">このコマンドレットがスニペットをインポートするスニペットディレクトリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea702-149">Specifies the path to the snippets directory in which this cmdlet imports snippets.</span></span>

```yaml
Type: System.String
Parameter Sets: FromFolder
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ea702-150">-再帰</span><span class="sxs-lookup"><span data-stu-id="ea702-150">-Recurse</span></span>

<span data-ttu-id="ea702-151">このコマンドレットが **Path** パラメーターの値のすべてのサブディレクトリからスニペットをインポートすることを示します。</span><span class="sxs-lookup"><span data-stu-id="ea702-151">Indicates that this cmdlet imports snippets from all subdirectories of the value of the **Path** parameter.</span></span>

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

### <span data-ttu-id="ea702-152">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea702-152">CommonParameters</span></span>

<span data-ttu-id="ea702-153">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ea702-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ea702-154">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea702-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ea702-155">入力</span><span class="sxs-lookup"><span data-stu-id="ea702-155">INPUTS</span></span>

### <span data-ttu-id="ea702-156">なし</span><span class="sxs-lookup"><span data-stu-id="ea702-156">None</span></span>

<span data-ttu-id="ea702-157">このコマンドレットはパイプラインから入力を取得しません。</span><span class="sxs-lookup"><span data-stu-id="ea702-157">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="ea702-158">出力</span><span class="sxs-lookup"><span data-stu-id="ea702-158">OUTPUTS</span></span>

### <span data-ttu-id="ea702-159">なし</span><span class="sxs-lookup"><span data-stu-id="ea702-159">None</span></span>

<span data-ttu-id="ea702-160">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="ea702-160">This cmdlet does not generate output.</span></span>

## <span data-ttu-id="ea702-161">注</span><span class="sxs-lookup"><span data-stu-id="ea702-161">NOTES</span></span>

- <span data-ttu-id="ea702-162">コマンドレットを使用して、 `Get-IseSnippet` インポートしたスニペットを取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="ea702-162">You cannot use the `Get-IseSnippet` cmdlet to get imported snippets.</span></span> <span data-ttu-id="ea702-163">`Get-IseSnippet` ディレクトリ内のスニペットだけを取得し `$home\Documents\WindowsPowerShell\Snippets` ます。</span><span class="sxs-lookup"><span data-stu-id="ea702-163">`Get-IseSnippet` gets only snippets in the `$home\Documents\WindowsPowerShell\Snippets` directory.</span></span>
- <span data-ttu-id="ea702-164">`Import-IseSnippet`**ISESnippetCollection** オブジェクトの **Load** 静的なメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ea702-164">`Import-IseSnippet` uses the **Load** static method of **Microsoft.PowerShell.Host.ISE.ISESnippetCollection** objects.</span></span> <span data-ttu-id="ea702-165">Windows PowerShell ISE オブジェクトモデルでは、スニペットの **Load** メソッドを使用することもできます。 `$psISE.CurrentPowerShellTab.Snippets.Load()`</span><span class="sxs-lookup"><span data-stu-id="ea702-165">You can also use the **Load** method of snippets in the Windows PowerShell ISE object model: `$psISE.CurrentPowerShellTab.Snippets.Load()`</span></span>
- <span data-ttu-id="ea702-166">`New-IseSnippet`コマンドレットは、新しいユーザーが作成したスニペットを types.ps1xml ファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="ea702-166">The `New-IseSnippet` cmdlet stores new user-created snippets in unsigned .ps1xml files.</span></span> <span data-ttu-id="ea702-167">そのため、Windows PowerShell は、実行ポリシーが **AllSigned** または **Restricted** のセッションにこれらを読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="ea702-167">As such, Windows PowerShell cannot load them into a session in which the execution policy is **AllSigned** or **Restricted** .</span></span> <span data-ttu-id="ea702-168">**Restricted** または **AllSigned** セッションでは、ユーザーが作成した署名されていないスニペットを作成、取得、およびインポートできますが、それらをセッションで使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="ea702-168">In a **Restricted** or **AllSigned** session, you can create, get, and import unsigned user-created snippets, but you cannot use them in the session.</span></span>

  <span data-ttu-id="ea702-169">コマンドレットから返される、署名されていないユーザーが作成したスニペットを使用するには、 `Import-IseSnippet` 実行ポリシーを変更し、Windows PowerShell ISE を再起動します。</span><span class="sxs-lookup"><span data-stu-id="ea702-169">To use unsigned user-created snippets that the `Import-IseSnippet` cmdlet returns, change the execution policy, and then restart Windows PowerShell ISE.</span></span>

  <span data-ttu-id="ea702-170">Windows PowerShell 実行ポリシーの詳細については、「[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea702-170">For more information about Windows PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="ea702-171">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ea702-171">RELATED LINKS</span></span>

[<span data-ttu-id="ea702-172">Get-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="ea702-172">Get-IseSnippet</span></span>](Get-IseSnippet.md)

[<span data-ttu-id="ea702-173">New-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="ea702-173">New-IseSnippet</span></span>](New-IseSnippet.md)
