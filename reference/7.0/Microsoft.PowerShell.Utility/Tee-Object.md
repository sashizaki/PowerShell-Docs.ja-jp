---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/tee-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Tee-Object
ms.openlocfilehash: 47c1eb6b31f762e3950c07f9edec81a081ce616e
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211424"
---
# <span data-ttu-id="a0e52-103">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="a0e52-103">Tee-Object</span></span>

## <span data-ttu-id="a0e52-104">概要</span><span class="sxs-lookup"><span data-stu-id="a0e52-104">SYNOPSIS</span></span>
<span data-ttu-id="a0e52-105">ファイルまたは変数にコマンドの出力を保存し、またそれをパイプラインに送信します。</span><span class="sxs-lookup"><span data-stu-id="a0e52-105">Saves command output in a file or variable and also sends it down the pipeline.</span></span>

## <span data-ttu-id="a0e52-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a0e52-106">SYNTAX</span></span>

### <span data-ttu-id="a0e52-107">File (既定値)</span><span class="sxs-lookup"><span data-stu-id="a0e52-107">File (Default)</span></span>

```
Tee-Object [-InputObject <PSObject>] [-FilePath] <String> [-Append] [<CommonParameters>]
```

### <span data-ttu-id="a0e52-108">LiteralFile</span><span class="sxs-lookup"><span data-stu-id="a0e52-108">LiteralFile</span></span>

```
Tee-Object [-InputObject <PSObject>] -LiteralPath <String> [<CommonParameters>]
```

### <span data-ttu-id="a0e52-109">変数</span><span class="sxs-lookup"><span data-stu-id="a0e52-109">Variable</span></span>

```
Tee-Object [-InputObject <PSObject>] -Variable <String> [<CommonParameters>]
```

## <span data-ttu-id="a0e52-110">Description</span><span class="sxs-lookup"><span data-stu-id="a0e52-110">DESCRIPTION</span></span>

<span data-ttu-id="a0e52-111">`Tee-Object`コマンドレットは、出力をリダイレクトします。つまり、コマンドの出力を2方向 (文字 T など) で送信します。</span><span class="sxs-lookup"><span data-stu-id="a0e52-111">The `Tee-Object` cmdlet redirects output, that is, it sends the output of a command in two directions (like the letter T).</span></span> <span data-ttu-id="a0e52-112">出力は、ファイルまたは変数に保存され、パイプラインにも送信されます。</span><span class="sxs-lookup"><span data-stu-id="a0e52-112">It stores the output in a file or variable and also sends it down the pipeline.</span></span> <span data-ttu-id="a0e52-113">がパイプラインの最後のコマンドである場合は、 `Tee-Object` コマンドの出力がプロンプトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0e52-113">If `Tee-Object` is the last command in the pipeline, the command output is displayed at the prompt.</span></span>

## <span data-ttu-id="a0e52-114">例</span><span class="sxs-lookup"><span data-stu-id="a0e52-114">EXAMPLES</span></span>

### <span data-ttu-id="a0e52-115">例 1: ファイルとコンソールにプロセスを出力する</span><span class="sxs-lookup"><span data-stu-id="a0e52-115">Example 1: Output processes to a file and to the console</span></span>

<span data-ttu-id="a0e52-116">この例では、コンピューター上で実行されているプロセスの一覧を取得し、その結果をファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="a0e52-116">This example gets a list of the processes running on the computer and sends the result to a file.</span></span>
<span data-ttu-id="a0e52-117">2 番目のパスを指定していないため、プロセスはコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0e52-117">Because a second path is not specified, the processes are also displayed in the console.</span></span>

```powershell
Get-Process | Tee-Object -FilePath "C:\Test1\testfile2.txt"
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
83       4     2300       4520    39     0.30    4032 00THotkey
272      6     1400       3944    34     0.06    3088 alg
81       3      804       3284    21     2.45     148 ApntEx
81       4     2008       5808    38     0.75    3684 Apoint
...
```

### <span data-ttu-id="a0e52-118">例 2: 変数にプロセスを出力する `Select-Object`</span><span class="sxs-lookup"><span data-stu-id="a0e52-118">Example 2: Output processes to a variable and `Select-Object`</span></span>

<span data-ttu-id="a0e52-119">この例では、コンピューター上で実行されているプロセスの一覧を取得し、変数に保存 `$proc` して、にパイプ処理し `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="a0e52-119">This example gets a list of the processes running on the computer, saves them to the `$proc` variable, and pipes them to `Select-Object`.</span></span>

```powershell
Get-Process notepad | Tee-Object -Variable proc | Select-Object processname,handles
```

```Output
ProcessName                              Handles
-----------                              -------
notepad                                  43
notepad                                  37
notepad                                  38
notepad                                  38
```

<span data-ttu-id="a0e52-120">`Select-Object`コマンドレットでは、 **ProcessName** を選択し、プロパティを **処理** します。</span><span class="sxs-lookup"><span data-stu-id="a0e52-120">The `Select-Object` cmdlet selects the **ProcessName** and **Handles** properties.</span></span> <span data-ttu-id="a0e52-121">変数には、 `$proc` によって返される既定の情報が含まれていることに注意して `Get-Process` ください。</span><span class="sxs-lookup"><span data-stu-id="a0e52-121">Note that the `$proc` variable includes the default information returned by `Get-Process`.</span></span>

### <span data-ttu-id="a0e52-122">例 3: 2 つのログファイルにシステムファイルを出力する</span><span class="sxs-lookup"><span data-stu-id="a0e52-122">Example 3: Output system files to two log files</span></span>

<span data-ttu-id="a0e52-123">この例では、システムファイルの一覧を、累積ファイルと現在のファイルの2つのログファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="a0e52-123">This example saves a list of system files in a two log files, a cumulative file and a current file.</span></span>

```powershell
Get-ChildItem -Path D: -File -System -Recurse |
  Tee-Object -FilePath "c:\test\AllSystemFiles.txt" -Append |
    Out-File c:\test\NewSystemFiles.txt
```

<span data-ttu-id="a0e52-124">このコマンドは、コマンドレットを使用して、 `Get-ChildItem` D: ドライブ上のシステムファイルを再帰的に検索します。</span><span class="sxs-lookup"><span data-stu-id="a0e52-124">The command uses the `Get-ChildItem` cmdlet to do a recursive search for system files on the D: drive.</span></span> <span data-ttu-id="a0e52-125">パイプライン演算子 (|) によってにリストが送信され `Tee-Object` 、AllSystemFiles.txt ファイルにリストが追加され、コマンドレットに一覧が渡されます。この一覧は、 `Out-File` NewSystemFiles.txt ファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="a0e52-125">A pipeline operator (|) sends the list to `Tee-Object`, which appends the list to the AllSystemFiles.txt file and passes the list down the pipeline to the `Out-File` cmdlet, which saves the list in the NewSystemFiles.txt file.</span></span>

## <span data-ttu-id="a0e52-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a0e52-126">PARAMETERS</span></span>

### <span data-ttu-id="a0e52-127">-追加</span><span class="sxs-lookup"><span data-stu-id="a0e52-127">-Append</span></span>

<span data-ttu-id="a0e52-128">コマンドレットによって、指定したファイルに出力が追加されることを示します。</span><span class="sxs-lookup"><span data-stu-id="a0e52-128">Indicates that the cmdlet appends the output to the specified file.</span></span> <span data-ttu-id="a0e52-129">このパラメーターを指定しない場合、ファイル内の既存の内容が警告なしで新しい内容に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="a0e52-129">Without this parameter, the new content replaces any existing content in the file without warning.</span></span>

<span data-ttu-id="a0e52-130">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a0e52-130">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: File
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0e52-131">-FilePath</span><span class="sxs-lookup"><span data-stu-id="a0e52-131">-FilePath</span></span>

<span data-ttu-id="a0e52-132">このコマンドレットがオブジェクトをワイルドカード文字に保存するファイルを指定しますが、1つのファイルに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0e52-132">Specifies a file that this cmdlet saves the object to Wildcard characters are permitted, but must resolve to a single file.</span></span>

```yaml
Type: System.String
Parameter Sets: File
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a0e52-133">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a0e52-133">-InputObject</span></span>

<span data-ttu-id="a0e52-134">保存されて表示されるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a0e52-134">Specifies the object to be saved and displayed.</span></span> <span data-ttu-id="a0e52-135">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0e52-135">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="a0e52-136">パイプを使用してオブジェクトをにパイプすることもでき `Tee-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="a0e52-136">You can also pipe an object to `Tee-Object`.</span></span>

<span data-ttu-id="a0e52-137">で **inputobject** パラメーターを使用すると `Tee-Object` 、コマンドの結果をにパイプするのではなく、 `Tee-Object` 値がコレクションの場合でも、 **inputobject** 値は単一のオブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="a0e52-137">When you use the **InputObject** parameter with `Tee-Object`, instead of piping command results to `Tee-Object`, the **InputObject** value is treated as a single object even if the value is a collection.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a0e52-138">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a0e52-138">-LiteralPath</span></span>

<span data-ttu-id="a0e52-139">このコマンドレットでオブジェクトを保存するファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="a0e52-139">Specifies a file that this cmdlet saves the object to.</span></span> <span data-ttu-id="a0e52-140">**FilePath** とは異なり、 **LiteralPath** パラメーターの値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0e52-140">Unlike **FilePath** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="a0e52-141">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="a0e52-141">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="a0e52-142">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="a0e52-142">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="a0e52-143">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="a0e52-143">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralFile
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0e52-144">-Variable</span><span class="sxs-lookup"><span data-stu-id="a0e52-144">-Variable</span></span>

<span data-ttu-id="a0e52-145">コマンドレットによってオブジェクトが保存される変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a0e52-145">Specifies a variable that the cmdlet saves the object to.</span></span> <span data-ttu-id="a0e52-146">前のドル記号 () を付けずに変数名を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="a0e52-146">Enter a variable name without the preceding dollar sign (`$`).</span></span>

```yaml
Type: System.String
Parameter Sets: Variable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0e52-147">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a0e52-147">CommonParameters</span></span>

<span data-ttu-id="a0e52-148">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a0e52-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a0e52-149">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0e52-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a0e52-150">入力</span><span class="sxs-lookup"><span data-stu-id="a0e52-150">INPUTS</span></span>

### <span data-ttu-id="a0e52-151">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="a0e52-151">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="a0e52-152">パイプを使用してオブジェクトをにパイプ処理でき `Tee-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="a0e52-152">You can pipe objects to `Tee-Object`.</span></span>

## <span data-ttu-id="a0e52-153">出力</span><span class="sxs-lookup"><span data-stu-id="a0e52-153">OUTPUTS</span></span>

### <span data-ttu-id="a0e52-154">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="a0e52-154">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="a0e52-155">`Tee-Object` リダイレクトするオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a0e52-155">`Tee-Object` returns the object that it redirects.</span></span>

## <span data-ttu-id="a0e52-156">注</span><span class="sxs-lookup"><span data-stu-id="a0e52-156">NOTES</span></span>

<span data-ttu-id="a0e52-157">コマンドレットまたはリダイレクト演算子を使用することもできます `Out-File` 。どちらも、出力をファイルに保存しますが、パイプラインには送信しません。</span><span class="sxs-lookup"><span data-stu-id="a0e52-157">You can also use the `Out-File` cmdlet or the redirection operator, both of which save the output in a file but do not send it down the pipeline.</span></span>

<span data-ttu-id="a0e52-158">PowerShell 6 以降、で `Tee-Object` は、ファイルへの書き込み時に、BOM のない utf-8 エンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0e52-158">Beginning in PowerShell 6, `Tee-Object` uses BOM-less UTF-8 encoding when it writes to files.</span></span> <span data-ttu-id="a0e52-159">別のエンコーディングが必要な場合は、 `Out-File` **encoding** パラメーターを指定してコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a0e52-159">If you need a different encoding, use the `Out-File` cmdlet with the **Encoding** parameter.</span></span>

## <span data-ttu-id="a0e52-160">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a0e52-160">RELATED LINKS</span></span>

[<span data-ttu-id="a0e52-161">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="a0e52-161">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="a0e52-162">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="a0e52-162">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="a0e52-163">Group-Object</span><span class="sxs-lookup"><span data-stu-id="a0e52-163">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="a0e52-164">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="a0e52-164">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="a0e52-165">New-Object</span><span class="sxs-lookup"><span data-stu-id="a0e52-165">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="a0e52-166">Select-Object</span><span class="sxs-lookup"><span data-stu-id="a0e52-166">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="a0e52-167">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="a0e52-167">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="a0e52-168">Where-Object</span><span class="sxs-lookup"><span data-stu-id="a0e52-168">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)

[<span data-ttu-id="a0e52-169">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="a0e52-169">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)
