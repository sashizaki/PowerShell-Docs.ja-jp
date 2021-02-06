---
description: PowerShell のコマンドレットとコマンドに代替名を使用する方法について説明します。
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_aliases?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Aliases
ms.openlocfilehash: e8b93e2b687e779048784c1eedb15fa53972b8b0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602793"
---
# <a name="about-aliases"></a><span data-ttu-id="80c41-103">エイリアスについて</span><span class="sxs-lookup"><span data-stu-id="80c41-103">About Aliases</span></span>

## <a name="short-description"></a><span data-ttu-id="80c41-104">概要</span><span class="sxs-lookup"><span data-stu-id="80c41-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="80c41-105">PowerShell のコマンドレットとコマンドに代替名を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80c41-105">Describes how to use alternate names for cmdlets and commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="80c41-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="80c41-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="80c41-107">エイリアスは、コマンドレットまたは関数、スクリプト、ファイル、実行可能ファイルなどのコマンド要素の代替名またはニックネームです。</span><span class="sxs-lookup"><span data-stu-id="80c41-107">An alias is an alternate name or nickname for a cmdlet or for a command element, such as a function, script, file, or executable file.</span></span> <span data-ttu-id="80c41-108">PowerShell コマンドでは、コマンド名の代わりにエイリアスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="80c41-108">You can use the alias instead of the command name in any PowerShell commands.</span></span>

<span data-ttu-id="80c41-109">エイリアスを作成するには、New-Alias コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="80c41-109">To create an alias, use the New-Alias cmdlet.</span></span> <span data-ttu-id="80c41-110">たとえば、次のコマンドは、コマンドレットの "ガス" エイリアスを作成し `Get-AuthenticodeSignature` ます。</span><span class="sxs-lookup"><span data-stu-id="80c41-110">For example, the following command creates the "gas" alias for the `Get-AuthenticodeSignature` cmdlet:</span></span>

```powershell
New-Alias -Name gas -Value Get-AuthenticodeSignature
```

<span data-ttu-id="80c41-111">コマンドレット名のエイリアスを作成した後は、コマンドレット名の代わりにエイリアスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="80c41-111">After you create the alias for the cmdlet name, you can use the alias instead of the cmdlet name.</span></span> <span data-ttu-id="80c41-112">たとえば、SqlScript.ps1 ファイルの Authenticode 署名を取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80c41-112">For example, to get the Authenticode signature for the SqlScript.ps1 file, type:</span></span>

```powershell
Get-AuthenticodeSignature SqlScript.ps1
```

<span data-ttu-id="80c41-113">または、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80c41-113">Or, type:</span></span>

```powershell
gas SqlScript.ps1
```

<span data-ttu-id="80c41-114">Microsoft Office Word のエイリアスとして "word" を作成した場合は、次のように「word」と入力することができます。</span><span class="sxs-lookup"><span data-stu-id="80c41-114">If you create "word" as the alias for Microsoft Office Word, you can type "word" instead of the following:</span></span>

```powershell
"C:\Program Files\Microsoft Office\Office11\Winword.exe"
```

## <a name="built-in-aliases"></a><span data-ttu-id="80c41-115">組み込みのエイリアス</span><span class="sxs-lookup"><span data-stu-id="80c41-115">BUILT-IN ALIASES</span></span>

<span data-ttu-id="80c41-116">PowerShell には、一連の組み込みエイリアスが含まれています。これには、Set-Location コマンドレットの "cd" と "chdir"、Get-ChildItem コマンドレットの "ls" と "dir" が含まれます。</span><span class="sxs-lookup"><span data-stu-id="80c41-116">PowerShell includes a set of built-in aliases, including "cd" and "chdir" for the Set-Location cmdlet, and "ls" and "dir" for the Get-ChildItem cmdlet.</span></span>

<span data-ttu-id="80c41-117">組み込みエイリアスを含め、コンピューター上のすべてのエイリアスを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80c41-117">To get all the aliases on the computer, including the built-in aliases, type:</span></span>

```powershell
Get-Alias
```

## <a name="alias-cmdlets"></a><span data-ttu-id="80c41-118">エイリアスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="80c41-118">ALIAS CMDLETS</span></span>

<span data-ttu-id="80c41-119">PowerShell には、エイリアスを使用するように設計された次のコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="80c41-119">PowerShell includes the following cmdlets, which are designed for working with aliases:</span></span>

- <span data-ttu-id="80c41-120">`Get-Alias` -現在のセッションのすべてのエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="80c41-120">`Get-Alias` - Gets all the aliases in the current session.</span></span>
- <span data-ttu-id="80c41-121">`New-Alias` -新しいエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="80c41-121">`New-Alias` - Creates a new alias.</span></span>
- <span data-ttu-id="80c41-122">`Set-Alias` -エイリアスを作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="80c41-122">`Set-Alias` - Creates or changes an alias.</span></span>
- <span data-ttu-id="80c41-123">`Export-Alias` -1 つまたは複数のエイリアスをファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="80c41-123">`Export-Alias` - Exports one or more aliases to a file.</span></span>
- <span data-ttu-id="80c41-124">`Import-Alias` -エイリアスファイルを PowerShell にインポートします。</span><span class="sxs-lookup"><span data-stu-id="80c41-124">`Import-Alias` - Imports an alias file into PowerShell.</span></span>

<span data-ttu-id="80c41-125">コマンドレットの詳細については、次のように入力してください。</span><span class="sxs-lookup"><span data-stu-id="80c41-125">For detailed information about the cmdlets, type:</span></span>

```powershell
Get-Help <cmdlet-Name> -Detailed
```

<span data-ttu-id="80c41-126">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80c41-126">For example, type:</span></span>

```powershell
Get-Help Export-Alias -Detailed
```

## <a name="creating-an-alias"></a><span data-ttu-id="80c41-127">エイリアスの作成</span><span class="sxs-lookup"><span data-stu-id="80c41-127">CREATING AN ALIAS</span></span>

<span data-ttu-id="80c41-128">新しいエイリアスを作成するには、New-Alias コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="80c41-128">To create a new alias, use the New-Alias cmdlet.</span></span> <span data-ttu-id="80c41-129">たとえば、Get-help の "gh" エイリアスを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80c41-129">For example, to create the "gh" alias for Get-Help, type:</span></span>

```powershell
New-Alias -Name gh -Value Get-Help
```

<span data-ttu-id="80c41-130">コマンドでエイリアスを使用すると、完全なコマンドレット名を使用する場合と同様に、エイリアスをパラメーターと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="80c41-130">You can use the alias in commands, just as you would use the full cmdlet name, and you can use the alias with parameters.</span></span>

<span data-ttu-id="80c41-131">たとえば、Get-WmiObject コマンドレットの詳細なヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80c41-131">For example, to get detailed Help for the Get-WmiObject cmdlet, type:</span></span>

```powershell
Get-Help Get-WmiObject -Detailed
```

<span data-ttu-id="80c41-132">または、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80c41-132">Or, type:</span></span>

```powershell
gh Get-WmiObject -Detailed
```

## <a name="saving-aliases"></a><span data-ttu-id="80c41-133">エイリアスの保存</span><span class="sxs-lookup"><span data-stu-id="80c41-133">SAVING ALIASES</span></span>

<span data-ttu-id="80c41-134">作成したエイリアスは、現在のセッションにのみ保存されます。</span><span class="sxs-lookup"><span data-stu-id="80c41-134">The aliases that you create are saved only in the current session.</span></span> <span data-ttu-id="80c41-135">別のセッションでエイリアスを使用するには、エイリアスを PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="80c41-135">To use the aliases in a different session, add the alias to your PowerShell profile.</span></span> <span data-ttu-id="80c41-136">または、Export-Alias コマンドレットを使用して、エイリアスをファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="80c41-136">Or, use the Export-Alias cmdlet to save the aliases to a file.</span></span>

<span data-ttu-id="80c41-137">詳細については、次のように入力してください。</span><span class="sxs-lookup"><span data-stu-id="80c41-137">For more information, type:</span></span>

```powershell
Get-Help about_Profiles
```

## <a name="getting-aliases"></a><span data-ttu-id="80c41-138">エイリアスの取得</span><span class="sxs-lookup"><span data-stu-id="80c41-138">GETTING ALIASES</span></span>

<span data-ttu-id="80c41-139">組み込みエイリアス、PowerShell プロファイル内のエイリアス、現在のセッションで作成したエイリアスなど、現在のセッションのすべてのエイリアスを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80c41-139">To get all the aliases in the current session, including the built-in aliases, the aliases in your PowerShell profiles, and the aliases that you have created in the current session, type:</span></span>

```powershell
Get-Alias
```

<span data-ttu-id="80c41-140">特定のエイリアスを取得するには、Get-Alias コマンドレットの Name パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="80c41-140">To get particular aliases, use the Name parameter of the Get-Alias cmdlet.</span></span> <span data-ttu-id="80c41-141">たとえば、"p" で始まるエイリアスを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80c41-141">For example, to get aliases that begin with "p", type:</span></span>

```powershell
Get-Alias -Name p*
```

<span data-ttu-id="80c41-142">特定の項目のエイリアスを取得するには、Definition パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="80c41-142">To get the aliases for a particular item, use the Definition parameter.</span></span> <span data-ttu-id="80c41-143">たとえば、Get-ChildItem コマンドレットのエイリアスを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80c41-143">For example, to get the aliases for the Get-ChildItem cmdlet type:</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

### <a name="get-alias-output"></a><span data-ttu-id="80c41-144">取得-エイリアスの出力</span><span class="sxs-lookup"><span data-stu-id="80c41-144">GET-ALIAS OUTPUT</span></span>

<span data-ttu-id="80c41-145">Get-Alias は、1つの型のオブジェクト (エイリアス情報オブジェクト) (エイリアス情報オブジェクト) のみを返します。</span><span class="sxs-lookup"><span data-stu-id="80c41-145">Get-Alias returns only one type of object, an AliasInfo object (System.Management.Automation.AliasInfo).</span></span> <span data-ttu-id="80c41-146">"Cd" など、ハイフンを含まないエイリアスの名前は、次の形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="80c41-146">The name of aliases that don't include a hyphen, such as "cd" are displayed in the following format:</span></span>

```powershell
Get-Alias ac
```

```Output
CommandType     Name                    Version    Source
-----------     ----                    -------    ------
Alias           ac -> Add-Content
```

<span data-ttu-id="80c41-147">これにより、必要な情報をすばやく簡単に取得できます。</span><span class="sxs-lookup"><span data-stu-id="80c41-147">This makes it very quick and easy to get the information that you need.</span></span>

<span data-ttu-id="80c41-148">矢印に基づくエイリアス名の形式は、ハイフンを含むエイリアスには使用されません。</span><span class="sxs-lookup"><span data-stu-id="80c41-148">The arrow-based alias name format is not used for aliases that include a hyphen.</span></span> <span data-ttu-id="80c41-149">これらは、一般的な省略形またはニックネームの代わりに、コマンドレットと関数に優先される代替名となる可能性があり、作成者はそれらを明確にする必要がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80c41-149">These are likely to be preferred substitute names for cmdlets and functions, instead of typical abbreviations or nicknames, and the author might not want them to be as evident.</span></span>

## <a name="alternate-names-for-commands-with-parameters"></a><span data-ttu-id="80c41-150">パラメーターを使用したコマンドの代替名</span><span class="sxs-lookup"><span data-stu-id="80c41-150">ALTERNATE NAMES FOR COMMANDS WITH PARAMETERS</span></span>

<span data-ttu-id="80c41-151">コマンドレット、スクリプト、関数、または実行可能ファイルにエイリアスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="80c41-151">You can assign an alias to a cmdlet, script, function, or executable file.</span></span> <span data-ttu-id="80c41-152">コマンドとそのパラメーターにエイリアスを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="80c41-152">You cannot assign an alias to a command and its parameters.</span></span> <span data-ttu-id="80c41-153">たとえば、コマンドレットにエイリアスを割り当てることはでき `Get-Eventlog` ますが、コマンドにエイリアスを割り当てることはできません `Get-Eventlog -LogName System` 。</span><span class="sxs-lookup"><span data-stu-id="80c41-153">For example, you can assign an alias to the `Get-Eventlog` cmdlet, but you cannot assign an alias to the `Get-Eventlog -LogName System` command.</span></span>

<span data-ttu-id="80c41-154">コマンドを含む関数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="80c41-154">You can create a function that includes the command.</span></span> <span data-ttu-id="80c41-155">関数を作成するには、"function" という単語に続けて関数の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="80c41-155">To create a function, type the word "function" followed by a name for the function.</span></span> <span data-ttu-id="80c41-156">コマンドを入力し、中かっこ () で囲み {} ます。</span><span class="sxs-lookup"><span data-stu-id="80c41-156">Type the command, and enclose it in braces ({}).</span></span>

<span data-ttu-id="80c41-157">たとえば、次のコマンドは、syslog 関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="80c41-157">For example, the following command creates the syslog function.</span></span> <span data-ttu-id="80c41-158">この関数は、 `Get-Eventlog -LogName System` 次のコマンドを表します。</span><span class="sxs-lookup"><span data-stu-id="80c41-158">This function represents the `Get-Eventlog -LogName System` command:</span></span>

```powershell
function Get-SystemEventlog {Get-Eventlog -LogName System}
Set-Alias -Name syslog -Value Get-SystemEventlog
```

<span data-ttu-id="80c41-159">コマンドではなく「syslog」と入力できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="80c41-159">You can now type "syslog" instead of the command.</span></span> <span data-ttu-id="80c41-160">また、新しい関数のエイリアスを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="80c41-160">And, you can create aliases for the new function.</span></span>

<span data-ttu-id="80c41-161">関数の詳細については、次のように入力してください。</span><span class="sxs-lookup"><span data-stu-id="80c41-161">For more information about functions, type:</span></span>

```powershell
Get-Help about_Functions
```

## <a name="alias-objects"></a><span data-ttu-id="80c41-162">エイリアスオブジェクト</span><span class="sxs-lookup"><span data-stu-id="80c41-162">ALIAS OBJECTS</span></span>

<span data-ttu-id="80c41-163">PowerShell エイリアスは、system.string クラスのインスタンスであるオブジェクトによって表されます。</span><span class="sxs-lookup"><span data-stu-id="80c41-163">PowerShell aliases are represented by objects that are instances of the System.Management.Automation.AliasInfo class.</span></span> <span data-ttu-id="80c41-164">この種類のオブジェクトの詳細については、PowerShell SDK の「 [エイリアス情報クラス][aliasinfo] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80c41-164">For more information about this type of object, see [AliasInfo Class][aliasinfo] in the PowerShell SDK.</span></span>

<span data-ttu-id="80c41-165">エイリアスオブジェクトのプロパティとメソッドを表示するには、エイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="80c41-165">To view the properties and methods of the alias objects, get the aliases.</span></span>
<span data-ttu-id="80c41-166">次に、パイプを Get-Member コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="80c41-166">Then, pipe them to the Get-Member cmdlet.</span></span> <span data-ttu-id="80c41-167">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="80c41-167">For example:</span></span>

```powershell
Get-Alias | Get-Member
```

<span data-ttu-id="80c41-168">エイリアスなど、特定のエイリアスのプロパティの値を表示するには、 `dir` エイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="80c41-168">To view the values of the properties of a specific alias, such as the `dir` alias, get the alias.</span></span> <span data-ttu-id="80c41-169">次に、パイプを Format-List コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="80c41-169">Then, pipe it to the Format-List cmdlet.</span></span> <span data-ttu-id="80c41-170">たとえば、次のコマンドは、"dir" エイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="80c41-170">For example, the following command gets the "dir" alias.</span></span> <span data-ttu-id="80c41-171">次に、コマンドによって、エイリアスが Format-List コマンドレットにパイプされます。</span><span class="sxs-lookup"><span data-stu-id="80c41-171">Next, the command pipes the alias to the Format-List cmdlet.</span></span> <span data-ttu-id="80c41-172">次に、このコマンドは、Format-List の Property パラメーターをワイルドカード文字 () と共に使用して、 \* エイリアスのすべてのプロパティを表示し `dir` ます。</span><span class="sxs-lookup"><span data-stu-id="80c41-172">Then, the command uses the Property parameter of Format-List with a wildcard character (\*) to display all the properties of the `dir` alias.</span></span> <span data-ttu-id="80c41-173">次のコマンドは、これらのタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="80c41-173">The following command performs these tasks:</span></span>

```powershell
Get-Alias -Name dir | Format-List -Property *
```

## <a name="powershell-alias-provider"></a><span data-ttu-id="80c41-174">PowerShell エイリアスプロバイダー</span><span class="sxs-lookup"><span data-stu-id="80c41-174">PowerShell ALIAS PROVIDER</span></span>

<span data-ttu-id="80c41-175">PowerShell には、エイリアスプロバイダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="80c41-175">PowerShell includes the Alias provider.</span></span> <span data-ttu-id="80c41-176">エイリアスプロバイダーを使用すると、ファイルシステムドライブ上にある場合と同様に、PowerShell でエイリアスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="80c41-176">The Alias provider lets you view the aliases in PowerShell as though they were on a file system drive.</span></span>

<span data-ttu-id="80c41-177">Alias プロバイダーは Alias: ドライブを公開します。</span><span class="sxs-lookup"><span data-stu-id="80c41-177">The Alias provider exposes the Alias: drive.</span></span> <span data-ttu-id="80c41-178">Alias: ドライブにアクセスするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80c41-178">To go into the Alias: drive, type:</span></span>

```powershell
Set-Location Alias:
```

<span data-ttu-id="80c41-179">ドライブの内容を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80c41-179">To view the contents of the drive, type:</span></span>

```powershell
Get-ChildItem
```

<span data-ttu-id="80c41-180">別の PowerShell ドライブのドライブの内容を表示するには、ドライブ名でパスを開始します。</span><span class="sxs-lookup"><span data-stu-id="80c41-180">To view the contents of the drive from another PowerShell drive, begin the path with the drive name.</span></span> <span data-ttu-id="80c41-181">コロン (:) を含めます。</span><span class="sxs-lookup"><span data-stu-id="80c41-181">Include the colon (:).</span></span> <span data-ttu-id="80c41-182">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="80c41-182">For example:</span></span>

```powershell
Get-ChildItem -Path Alias:
```

<span data-ttu-id="80c41-183">特定のエイリアスに関する情報を取得するには、ドライブ名とエイリアス名を入力します。</span><span class="sxs-lookup"><span data-stu-id="80c41-183">To get information about a particular alias, type the drive name and the alias name.</span></span> <span data-ttu-id="80c41-184">または、名前のパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="80c41-184">Or, type a name pattern.</span></span> <span data-ttu-id="80c41-185">たとえば、"p" で始まるすべてのエイリアスを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80c41-185">For example, to get all the aliases that begin with "p", type:</span></span>

```powershell
Get-ChildItem -Path Alias:p*
```

<span data-ttu-id="80c41-186">PowerShell エイリアスプロバイダーの詳細については、次のように入力してください。</span><span class="sxs-lookup"><span data-stu-id="80c41-186">For more information about the PowerShell Alias provider, type:</span></span>

```powershell
Get-Help Alias
```

## <a name="see-also"></a><span data-ttu-id="80c41-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="80c41-187">SEE ALSO</span></span>

- [<span data-ttu-id="80c41-188">New-Alias</span><span class="sxs-lookup"><span data-stu-id="80c41-188">New-Alias</span></span>](xref:Microsoft.PowerShell.Utility.New-Alias)
- [<span data-ttu-id="80c41-189">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="80c41-189">Get-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [<span data-ttu-id="80c41-190">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="80c41-190">Set-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Set-Alias)
- [<span data-ttu-id="80c41-191">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="80c41-191">Export-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [<span data-ttu-id="80c41-192">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="80c41-192">Import-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [<span data-ttu-id="80c41-193">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="80c41-193">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)
- [<span data-ttu-id="80c41-194">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="80c41-194">Get-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [<span data-ttu-id="80c41-195">about_functions</span><span class="sxs-lookup"><span data-stu-id="80c41-195">about_functions</span></span>](about_functions.md)
- [<span data-ttu-id="80c41-196">about_profiles</span><span class="sxs-lookup"><span data-stu-id="80c41-196">about_profiles</span></span>](about_profiles.md)
- [<span data-ttu-id="80c41-197">about_providers</span><span class="sxs-lookup"><span data-stu-id="80c41-197">about_providers</span></span>](about_providers.md)

<!-- External links -->
[aliasinfo]: /dotnet/api/system.management.automation.aliasinfo
