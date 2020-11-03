---
description: PowerShell のコマンドレットとコマンドに代替名を使用する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_aliases?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Aliases
ms.openlocfilehash: 409e6b01f32c5a6f60ac4b450ff08998caf1084a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223136"
---
# <a name="about-aliases"></a><span data-ttu-id="615a8-104">エイリアスについて</span><span class="sxs-lookup"><span data-stu-id="615a8-104">About Aliases</span></span>

## <a name="short-description"></a><span data-ttu-id="615a8-105">概要</span><span class="sxs-lookup"><span data-stu-id="615a8-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="615a8-106">PowerShell のコマンドレットとコマンドに代替名を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="615a8-106">Describes how to use alternate names for cmdlets and commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="615a8-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="615a8-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="615a8-108">エイリアスは、コマンドレットまたは関数、スクリプト、ファイル、実行可能ファイルなどのコマンド要素の代替名またはニックネームです。</span><span class="sxs-lookup"><span data-stu-id="615a8-108">An alias is an alternate name or nickname for a cmdlet or for a command element, such as a function, script, file, or executable file.</span></span> <span data-ttu-id="615a8-109">PowerShell コマンドでは、コマンド名の代わりにエイリアスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="615a8-109">You can use the alias instead of the command name in any PowerShell commands.</span></span>

<span data-ttu-id="615a8-110">エイリアスを作成するには、New-Alias コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="615a8-110">To create an alias, use the New-Alias cmdlet.</span></span> <span data-ttu-id="615a8-111">たとえば、次のコマンドは、コマンドレットの "ガス" エイリアスを作成し `Get-AuthenticodeSignature` ます。</span><span class="sxs-lookup"><span data-stu-id="615a8-111">For example, the following command creates the "gas" alias for the `Get-AuthenticodeSignature` cmdlet:</span></span>

```powershell
New-Alias -Name gas -Value Get-AuthenticodeSignature
```

<span data-ttu-id="615a8-112">コマンドレット名のエイリアスを作成した後は、コマンドレット名の代わりにエイリアスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="615a8-112">After you create the alias for the cmdlet name, you can use the alias instead of the cmdlet name.</span></span> <span data-ttu-id="615a8-113">たとえば、SqlScript.ps1 ファイルの Authenticode 署名を取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="615a8-113">For example, to get the Authenticode signature for the SqlScript.ps1 file, type:</span></span>

```powershell
Get-AuthenticodeSignature SqlScript.ps1
```

<span data-ttu-id="615a8-114">または、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="615a8-114">Or, type:</span></span>

```powershell
gas SqlScript.ps1
```

<span data-ttu-id="615a8-115">Microsoft Office Word のエイリアスとして "word" を作成した場合は、次のように「word」と入力することができます。</span><span class="sxs-lookup"><span data-stu-id="615a8-115">If you create "word" as the alias for Microsoft Office Word, you can type "word" instead of the following:</span></span>

```powershell
"C:\Program Files\Microsoft Office\Office11\Winword.exe"
```

## <a name="built-in-aliases"></a><span data-ttu-id="615a8-116">組み込みのエイリアス</span><span class="sxs-lookup"><span data-stu-id="615a8-116">BUILT-IN ALIASES</span></span>

<span data-ttu-id="615a8-117">PowerShell には、一連の組み込みエイリアスが含まれています。これには、Set-Location コマンドレットの "cd" と "chdir"、Get-ChildItem コマンドレットの "ls" と "dir" が含まれます。</span><span class="sxs-lookup"><span data-stu-id="615a8-117">PowerShell includes a set of built-in aliases, including "cd" and "chdir" for the Set-Location cmdlet, and "ls" and "dir" for the Get-ChildItem cmdlet.</span></span>

<span data-ttu-id="615a8-118">組み込みエイリアスを含め、コンピューター上のすべてのエイリアスを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="615a8-118">To get all the aliases on the computer, including the built-in aliases, type:</span></span>

```powershell
Get-Alias
```

## <a name="alias-cmdlets"></a><span data-ttu-id="615a8-119">エイリアスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="615a8-119">ALIAS CMDLETS</span></span>

<span data-ttu-id="615a8-120">PowerShell には、エイリアスを使用するように設計された次のコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="615a8-120">PowerShell includes the following cmdlets, which are designed for working with aliases:</span></span>

- <span data-ttu-id="615a8-121">`Get-Alias` -現在のセッションのすべてのエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="615a8-121">`Get-Alias` - Gets all the aliases in the current session.</span></span>
- <span data-ttu-id="615a8-122">`New-Alias` -新しいエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="615a8-122">`New-Alias` - Creates a new alias.</span></span>
- <span data-ttu-id="615a8-123">`Set-Alias` -エイリアスを作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="615a8-123">`Set-Alias` - Creates or changes an alias.</span></span>
- <span data-ttu-id="615a8-124">`Export-Alias` -1 つまたは複数のエイリアスをファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="615a8-124">`Export-Alias` - Exports one or more aliases to a file.</span></span>
- <span data-ttu-id="615a8-125">`Import-Alias` -エイリアスファイルを PowerShell にインポートします。</span><span class="sxs-lookup"><span data-stu-id="615a8-125">`Import-Alias` - Imports an alias file into PowerShell.</span></span>

<span data-ttu-id="615a8-126">コマンドレットの詳細については、次のように入力してください。</span><span class="sxs-lookup"><span data-stu-id="615a8-126">For detailed information about the cmdlets, type:</span></span>

```powershell
Get-Help <cmdlet-Name> -Detailed
```

<span data-ttu-id="615a8-127">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="615a8-127">For example, type:</span></span>

```powershell
Get-Help Export-Alias -Detailed
```

## <a name="creating-an-alias"></a><span data-ttu-id="615a8-128">エイリアスの作成</span><span class="sxs-lookup"><span data-stu-id="615a8-128">CREATING AN ALIAS</span></span>

<span data-ttu-id="615a8-129">新しいエイリアスを作成するには、New-Alias コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="615a8-129">To create a new alias, use the New-Alias cmdlet.</span></span> <span data-ttu-id="615a8-130">たとえば、Get-help の "gh" エイリアスを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="615a8-130">For example, to create the "gh" alias for Get-Help, type:</span></span>

```powershell
New-Alias -Name gh -Value Get-Help
```

<span data-ttu-id="615a8-131">コマンドでエイリアスを使用すると、完全なコマンドレット名を使用する場合と同様に、エイリアスをパラメーターと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="615a8-131">You can use the alias in commands, just as you would use the full cmdlet name, and you can use the alias with parameters.</span></span>

<span data-ttu-id="615a8-132">たとえば、Get-WmiObject コマンドレットの詳細なヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="615a8-132">For example, to get detailed Help for the Get-WmiObject cmdlet, type:</span></span>

```powershell
Get-Help Get-WmiObject -Detailed
```

<span data-ttu-id="615a8-133">または、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="615a8-133">Or, type:</span></span>

```powershell
gh Get-WmiObject -Detailed
```

## <a name="saving-aliases"></a><span data-ttu-id="615a8-134">エイリアスの保存</span><span class="sxs-lookup"><span data-stu-id="615a8-134">SAVING ALIASES</span></span>

<span data-ttu-id="615a8-135">作成したエイリアスは、現在のセッションにのみ保存されます。</span><span class="sxs-lookup"><span data-stu-id="615a8-135">The aliases that you create are saved only in the current session.</span></span> <span data-ttu-id="615a8-136">別のセッションでエイリアスを使用するには、エイリアスを PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="615a8-136">To use the aliases in a different session, add the alias to your PowerShell profile.</span></span> <span data-ttu-id="615a8-137">または、Export-Alias コマンドレットを使用して、エイリアスをファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="615a8-137">Or, use the Export-Alias cmdlet to save the aliases to a file.</span></span>

<span data-ttu-id="615a8-138">詳細については、次のように入力してください。</span><span class="sxs-lookup"><span data-stu-id="615a8-138">For more information, type:</span></span>

```powershell
Get-Help about_Profiles
```

## <a name="getting-aliases"></a><span data-ttu-id="615a8-139">エイリアスの取得</span><span class="sxs-lookup"><span data-stu-id="615a8-139">GETTING ALIASES</span></span>

<span data-ttu-id="615a8-140">組み込みエイリアス、PowerShell プロファイル内のエイリアス、現在のセッションで作成したエイリアスなど、現在のセッションのすべてのエイリアスを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="615a8-140">To get all the aliases in the current session, including the built-in aliases, the aliases in your PowerShell profiles, and the aliases that you have created in the current session, type:</span></span>

```powershell
Get-Alias
```

<span data-ttu-id="615a8-141">特定のエイリアスを取得するには、Get-Alias コマンドレットの Name パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="615a8-141">To get particular aliases, use the Name parameter of the Get-Alias cmdlet.</span></span> <span data-ttu-id="615a8-142">たとえば、"p" で始まるエイリアスを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="615a8-142">For example, to get aliases that begin with "p", type:</span></span>

```powershell
Get-Alias -Name p*
```

<span data-ttu-id="615a8-143">特定の項目のエイリアスを取得するには、Definition パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="615a8-143">To get the aliases for a particular item, use the Definition parameter.</span></span> <span data-ttu-id="615a8-144">たとえば、Get-ChildItem コマンドレットのエイリアスを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="615a8-144">For example, to get the aliases for the Get-ChildItem cmdlet type:</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

### <a name="get-alias-output"></a><span data-ttu-id="615a8-145">取得-エイリアスの出力</span><span class="sxs-lookup"><span data-stu-id="615a8-145">GET-ALIAS OUTPUT</span></span>

<span data-ttu-id="615a8-146">Get-Alias は、1つの型のオブジェクト (エイリアス情報オブジェクト) (エイリアス情報オブジェクト) のみを返します。</span><span class="sxs-lookup"><span data-stu-id="615a8-146">Get-Alias returns only one type of object, an AliasInfo object (System.Management.Automation.AliasInfo).</span></span> <span data-ttu-id="615a8-147">"Cd" など、ハイフンを含まないエイリアスの名前は、次の形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="615a8-147">The name of aliases that don't include a hyphen, such as "cd" are displayed in the following format:</span></span>

```powershell
Get-Alias ac
```

```Output
CommandType     Name                    Version    Source
-----------     ----                    -------    ------
Alias           ac -> Add-Content
```

<span data-ttu-id="615a8-148">これにより、必要な情報をすばやく簡単に取得できます。</span><span class="sxs-lookup"><span data-stu-id="615a8-148">This makes it very quick and easy to get the information that you need.</span></span>

<span data-ttu-id="615a8-149">矢印に基づくエイリアス名の形式は、ハイフンを含むエイリアスには使用されません。</span><span class="sxs-lookup"><span data-stu-id="615a8-149">The arrow-based alias name format is not used for aliases that include a hyphen.</span></span> <span data-ttu-id="615a8-150">これらは、一般的な省略形またはニックネームの代わりに、コマンドレットと関数に優先される代替名となる可能性があり、作成者はそれらを明確にする必要がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="615a8-150">These are likely to be preferred substitute names for cmdlets and functions, instead of typical abbreviations or nicknames, and the author might not want them to be as evident.</span></span>

## <a name="alternate-names-for-commands-with-parameters"></a><span data-ttu-id="615a8-151">パラメーターを使用したコマンドの代替名</span><span class="sxs-lookup"><span data-stu-id="615a8-151">ALTERNATE NAMES FOR COMMANDS WITH PARAMETERS</span></span>

<span data-ttu-id="615a8-152">コマンドレット、スクリプト、関数、または実行可能ファイルにエイリアスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="615a8-152">You can assign an alias to a cmdlet, script, function, or executable file.</span></span> <span data-ttu-id="615a8-153">コマンドとそのパラメーターにエイリアスを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="615a8-153">You cannot assign an alias to a command and its parameters.</span></span> <span data-ttu-id="615a8-154">たとえば、コマンドレットにエイリアスを割り当てることはでき `Get-Eventlog` ますが、コマンドにエイリアスを割り当てることはできません `Get-Eventlog -LogName System` 。</span><span class="sxs-lookup"><span data-stu-id="615a8-154">For example, you can assign an alias to the `Get-Eventlog` cmdlet, but you cannot assign an alias to the `Get-Eventlog -LogName System` command.</span></span>

<span data-ttu-id="615a8-155">コマンドを含む関数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="615a8-155">You can create a function that includes the command.</span></span> <span data-ttu-id="615a8-156">関数を作成するには、"function" という単語に続けて関数の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="615a8-156">To create a function, type the word "function" followed by a name for the function.</span></span> <span data-ttu-id="615a8-157">コマンドを入力し、中かっこ () で囲み {} ます。</span><span class="sxs-lookup"><span data-stu-id="615a8-157">Type the command, and enclose it in braces ({}).</span></span>

<span data-ttu-id="615a8-158">たとえば、次のコマンドは、syslog 関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="615a8-158">For example, the following command creates the syslog function.</span></span> <span data-ttu-id="615a8-159">この関数は、 `Get-Eventlog -LogName System` 次のコマンドを表します。</span><span class="sxs-lookup"><span data-stu-id="615a8-159">This function represents the `Get-Eventlog -LogName System` command:</span></span>

```powershell
function Get-SystemEventlog {Get-Eventlog -LogName System}
Set-Alias -Name syslog -Value Get-SystemEventlog
```

<span data-ttu-id="615a8-160">コマンドではなく「syslog」と入力できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="615a8-160">You can now type "syslog" instead of the command.</span></span> <span data-ttu-id="615a8-161">また、新しい関数のエイリアスを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="615a8-161">And, you can create aliases for the new function.</span></span>

<span data-ttu-id="615a8-162">関数の詳細については、次のように入力してください。</span><span class="sxs-lookup"><span data-stu-id="615a8-162">For more information about functions, type:</span></span>

```powershell
Get-Help about_Functions
```

## <a name="alias-objects"></a><span data-ttu-id="615a8-163">エイリアスオブジェクト</span><span class="sxs-lookup"><span data-stu-id="615a8-163">ALIAS OBJECTS</span></span>

<span data-ttu-id="615a8-164">PowerShell エイリアスは、system.string クラスのインスタンスであるオブジェクトによって表されます。</span><span class="sxs-lookup"><span data-stu-id="615a8-164">PowerShell aliases are represented by objects that are instances of the System.Management.Automation.AliasInfo class.</span></span> <span data-ttu-id="615a8-165">この種類のオブジェクトの詳細については、Microsoft Developer Network (MSDN) ライブラリの「 [エイリアス情報クラス][aliasinfo] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="615a8-165">For more information about this type of object, see [AliasInfo Class][aliasinfo] in the Microsoft Developer Network (MSDN) library.</span></span>

<span data-ttu-id="615a8-166">エイリアスオブジェクトのプロパティとメソッドを表示するには、エイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="615a8-166">To view the properties and methods of the alias objects, get the aliases.</span></span>
<span data-ttu-id="615a8-167">次に、パイプを Get-Member コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="615a8-167">Then, pipe them to the Get-Member cmdlet.</span></span> <span data-ttu-id="615a8-168">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="615a8-168">For example:</span></span>

```powershell
Get-Alias | Get-Member
```

<span data-ttu-id="615a8-169">エイリアスなど、特定のエイリアスのプロパティの値を表示するには、 `dir` エイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="615a8-169">To view the values of the properties of a specific alias, such as the `dir` alias, get the alias.</span></span> <span data-ttu-id="615a8-170">次に、パイプを Format-List コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="615a8-170">Then, pipe it to the Format-List cmdlet.</span></span> <span data-ttu-id="615a8-171">たとえば、次のコマンドは、"dir" エイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="615a8-171">For example, the following command gets the "dir" alias.</span></span> <span data-ttu-id="615a8-172">次に、コマンドによって、エイリアスが Format-List コマンドレットにパイプされます。</span><span class="sxs-lookup"><span data-stu-id="615a8-172">Next, the command pipes the alias to the Format-List cmdlet.</span></span> <span data-ttu-id="615a8-173">次に、このコマンドは、Format-List の Property パラメーターをワイルドカード文字 () と共に使用して、 \* エイリアスのすべてのプロパティを表示し `dir` ます。</span><span class="sxs-lookup"><span data-stu-id="615a8-173">Then, the command uses the Property parameter of Format-List with a wildcard character (\*) to display all the properties of the `dir` alias.</span></span> <span data-ttu-id="615a8-174">次のコマンドは、これらのタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="615a8-174">The following command performs these tasks:</span></span>

```powershell
Get-Alias -Name dir | Format-List -Property *
```

## <a name="powershell-alias-provider"></a><span data-ttu-id="615a8-175">PowerShell エイリアスプロバイダー</span><span class="sxs-lookup"><span data-stu-id="615a8-175">PowerShell ALIAS PROVIDER</span></span>

<span data-ttu-id="615a8-176">PowerShell には、エイリアスプロバイダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="615a8-176">PowerShell includes the Alias provider.</span></span> <span data-ttu-id="615a8-177">エイリアスプロバイダーを使用すると、ファイルシステムドライブ上にある場合と同様に、PowerShell でエイリアスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="615a8-177">The Alias provider lets you view the aliases in PowerShell as though they were on a file system drive.</span></span>

<span data-ttu-id="615a8-178">Alias プロバイダーは Alias: ドライブを公開します。</span><span class="sxs-lookup"><span data-stu-id="615a8-178">The Alias provider exposes the Alias: drive.</span></span> <span data-ttu-id="615a8-179">Alias: ドライブにアクセスするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="615a8-179">To go into the Alias: drive, type:</span></span>

```powershell
Set-Location Alias:
```

<span data-ttu-id="615a8-180">ドライブの内容を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="615a8-180">To view the contents of the drive, type:</span></span>

```powershell
Get-ChildItem
```

<span data-ttu-id="615a8-181">別の PowerShell ドライブのドライブの内容を表示するには、ドライブ名でパスを開始します。</span><span class="sxs-lookup"><span data-stu-id="615a8-181">To view the contents of the drive from another PowerShell drive, begin the path with the drive name.</span></span> <span data-ttu-id="615a8-182">コロン (:) を含めます。</span><span class="sxs-lookup"><span data-stu-id="615a8-182">Include the colon (:).</span></span> <span data-ttu-id="615a8-183">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="615a8-183">For example:</span></span>

```powershell
Get-ChildItem -Path Alias:
```

<span data-ttu-id="615a8-184">特定のエイリアスに関する情報を取得するには、ドライブ名とエイリアス名を入力します。</span><span class="sxs-lookup"><span data-stu-id="615a8-184">To get information about a particular alias, type the drive name and the alias name.</span></span> <span data-ttu-id="615a8-185">または、名前のパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="615a8-185">Or, type a name pattern.</span></span> <span data-ttu-id="615a8-186">たとえば、"p" で始まるすべてのエイリアスを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="615a8-186">For example, to get all the aliases that begin with "p", type:</span></span>

```powershell
Get-ChildItem -Path Alias:p*
```

<span data-ttu-id="615a8-187">PowerShell エイリアスプロバイダーの詳細については、次のように入力してください。</span><span class="sxs-lookup"><span data-stu-id="615a8-187">For more information about the PowerShell Alias provider, type:</span></span>

```powershell
Get-Help Alias
```

## <a name="see-also"></a><span data-ttu-id="615a8-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="615a8-188">SEE ALSO</span></span>

- [<span data-ttu-id="615a8-189">New-Alias</span><span class="sxs-lookup"><span data-stu-id="615a8-189">New-Alias</span></span>](xref:Microsoft.PowerShell.Utility.New-Alias)
- [<span data-ttu-id="615a8-190">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="615a8-190">Get-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [<span data-ttu-id="615a8-191">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="615a8-191">Set-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Set-Alias)
- [<span data-ttu-id="615a8-192">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="615a8-192">Export-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [<span data-ttu-id="615a8-193">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="615a8-193">Import-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [<span data-ttu-id="615a8-194">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="615a8-194">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)
- [<span data-ttu-id="615a8-195">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="615a8-195">Get-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [<span data-ttu-id="615a8-196">about_functions</span><span class="sxs-lookup"><span data-stu-id="615a8-196">about_functions</span></span>](about_functions.md)
- [<span data-ttu-id="615a8-197">about_profiles</span><span class="sxs-lookup"><span data-stu-id="615a8-197">about_profiles</span></span>](about_profiles.md)
- [<span data-ttu-id="615a8-198">about_providers</span><span class="sxs-lookup"><span data-stu-id="615a8-198">about_providers</span></span>](about_providers.md)

<!-- External links -->
[aliasinfo]: /dotnet/api/system.management.automation.aliasinfo
