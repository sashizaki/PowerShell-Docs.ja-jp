---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-unique?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Unique
ms.openlocfilehash: f0233e24e82ce5f0ef2113f65d19134833d75cb1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213011"
---
# <span data-ttu-id="43beb-103">Get-Unique</span><span class="sxs-lookup"><span data-stu-id="43beb-103">Get-Unique</span></span>

## <span data-ttu-id="43beb-104">概要</span><span class="sxs-lookup"><span data-stu-id="43beb-104">SYNOPSIS</span></span>
<span data-ttu-id="43beb-105">並べ替えられたリストから一意の項目を返します。</span><span class="sxs-lookup"><span data-stu-id="43beb-105">Returns unique items from a sorted list.</span></span>

## <span data-ttu-id="43beb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="43beb-106">SYNTAX</span></span>

### <span data-ttu-id="43beb-107">AsString (既定値)</span><span class="sxs-lookup"><span data-stu-id="43beb-107">AsString (Default)</span></span>

```
Get-Unique [-InputObject <PSObject>] [-AsString] [<CommonParameters>]
```

### <span data-ttu-id="43beb-108">UniqueByType</span><span class="sxs-lookup"><span data-stu-id="43beb-108">UniqueByType</span></span>

```
Get-Unique [-InputObject <PSObject>] [-OnType] [<CommonParameters>]
```

## <span data-ttu-id="43beb-109">Description</span><span class="sxs-lookup"><span data-stu-id="43beb-109">DESCRIPTION</span></span>

<span data-ttu-id="43beb-110">`Get-Unique`コマンドレットは、並べ替えられたリスト内の各項目を次の項目と比較し、重複を除去して、各項目の1つのインスタンスのみを返します。</span><span class="sxs-lookup"><span data-stu-id="43beb-110">The `Get-Unique` cmdlet compares each item in a sorted list to the next item, eliminates duplicates, and returns only one instance of each item.</span></span> <span data-ttu-id="43beb-111">コマンドレットが適切に機能するためにはリストを並べ替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="43beb-111">The list must be sorted for the cmdlet to work properly.</span></span>

<span data-ttu-id="43beb-112">`Get-Unique` では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="43beb-112">`Get-Unique` is case-sensitive.</span></span> <span data-ttu-id="43beb-113">その結果、大文字と小文字のみが異なる文字列は一意であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="43beb-113">As a result, strings that differ only in character casing are considered to be unique.</span></span>

## <span data-ttu-id="43beb-114">例</span><span class="sxs-lookup"><span data-stu-id="43beb-114">EXAMPLES</span></span>

### <span data-ttu-id="43beb-115">例 1: テキストファイル内の一意の単語を取得する</span><span class="sxs-lookup"><span data-stu-id="43beb-115">Example 1: Get unique words in a text file</span></span>

<span data-ttu-id="43beb-116">これらのコマンドは、テキスト ファイルの一意の単語の数を調べます。</span><span class="sxs-lookup"><span data-stu-id="43beb-116">These commands find the number of unique words in a text file.</span></span>

```powershell
$A = $( foreach ($line in Get-Content C:\Test1\File1.txt) {
    $line.tolower().split(" ")
  }) | Sort-Object | Get-Unique
$A.count
```

<span data-ttu-id="43beb-117">最初のコマンドは、File.txt ファイルの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="43beb-117">The first command gets the content of the File.txt file.</span></span> <span data-ttu-id="43beb-118">各行のテキストが小文字に変換された後、スペース (" ") を区切りとしてそれぞれの単語が別個の行に配置されます。</span><span class="sxs-lookup"><span data-stu-id="43beb-118">It converts each line of text to lowercase letters and then splits each word onto a separate line at the space (" ").</span></span> <span data-ttu-id="43beb-119">次に、結果の一覧をアルファベット順に並べ替え (既定)、コマンドレットを使用して `Get-Unique` 重複する単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="43beb-119">Then, it sorts the resulting list alphabetically (the default) and uses the `Get-Unique` cmdlet to eliminate any duplicate words.</span></span> <span data-ttu-id="43beb-120">結果は変数に格納され `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="43beb-120">The results are stored in the `$A` variable.</span></span>

<span data-ttu-id="43beb-121">2番目のコマンドは、内の文字列のコレクションの **Count** プロパティを使用して、 `$A` に含まれる項目の数を確認し `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="43beb-121">The second command uses the **Count** property of the collection of strings in `$A` to determine how many items are in `$A`.</span></span>

### <span data-ttu-id="43beb-122">例 2: 配列内の一意の整数を取得する</span><span class="sxs-lookup"><span data-stu-id="43beb-122">Example 2: Get unique integers in an array</span></span>

<span data-ttu-id="43beb-123">このコマンドは、整数のセットの一意のメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="43beb-123">This command finds the unique members of the set of integers.</span></span>

```powershell
1,1,1,1,12,23,4,5,4643,5,3,3,3,3,3,3,3 | Sort-Object | Get-Unique
```

```Output
1
3
4
5
12
23
4643
```

<span data-ttu-id="43beb-124">最初のコマンドは、コマンドラインで入力された整数の配列を受け取り、それらをコマンドレットにパイプ `Sort-Object` して並べ替え、にパイプ処理し `Get-Unique` ます。これにより、エントリが重複しなくなります。</span><span class="sxs-lookup"><span data-stu-id="43beb-124">The first command takes an array of integers typed at the command line, pipes them to the `Sort-Object` cmdlet to be sorted, and then pipes them to `Get-Unique`, which eliminates duplicate entries.</span></span>

### <span data-ttu-id="43beb-125">例 3: ディレクトリ内の一意のオブジェクトの種類を取得する</span><span class="sxs-lookup"><span data-stu-id="43beb-125">Example 3: Get unique object types in a directory</span></span>

<span data-ttu-id="43beb-126">このコマンドは、 `Get-ChildItem` コマンドレットを使用して、ファイルとディレクトリを含むローカルディレクトリの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="43beb-126">This command uses the `Get-ChildItem` cmdlet to retrieve the contents of the local directory, which includes files and directories.</span></span>

```powershell
Get-ChildItem | Sort-Object {$_.GetType()} | Get-Unique -OnType
```

<span data-ttu-id="43beb-127">パイプライン演算子 (|) によって結果がコマンドレットに送信され `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="43beb-127">The pipeline operator (|) sends the results to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="43beb-128">この `$_.GetType()` ステートメントは、 **GetType** メソッドを各ファイルまたはディレクトリに適用します。</span><span class="sxs-lookup"><span data-stu-id="43beb-128">The `$_.GetType()` statement applies the **GetType** method to each file or directory.</span></span> <span data-ttu-id="43beb-129">次に、は `Sort-Object` 型で項目を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="43beb-129">Then, `Sort-Object` sorts the items by type.</span></span> <span data-ttu-id="43beb-130">もう1つのパイプライン演算子は、結果をに送信 `Get-Unique` します。</span><span class="sxs-lookup"><span data-stu-id="43beb-130">Another pipeline operator sends the results to `Get-Unique`.</span></span> <span data-ttu-id="43beb-131">**Ontype** パラメーターは、 `Get-Unique` 各型のオブジェクトを1つだけ返すように指示します。</span><span class="sxs-lookup"><span data-stu-id="43beb-131">The **OnType** parameter directs `Get-Unique` to return only one object of each type.</span></span>

### <span data-ttu-id="43beb-132">例 4: 一意のプロセスを取得する</span><span class="sxs-lookup"><span data-stu-id="43beb-132">Example 4: Get unique processes</span></span>

<span data-ttu-id="43beb-133">このコマンドは、コンピューター上で実行されているプロセスの名前を取得し、重複を削除してその結果を返します。</span><span class="sxs-lookup"><span data-stu-id="43beb-133">This command gets the names of processes running on the computer with duplicates eliminated.</span></span>

```powershell
Get-Process | Sort-Object | Select-Object processname | Get-Unique -AsString
```

<span data-ttu-id="43beb-134">コマンドは、 `Get-Process` コンピューター上のすべてのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="43beb-134">The `Get-Process` command gets all of the processes on the computer.</span></span> <span data-ttu-id="43beb-135">パイプライン演算子 (|) は、結果をに渡し `Sort-Object` ます。既定では、ProcessName によってプロセスがアルファベット順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="43beb-135">The pipeline operator (|) passes the result to `Sort-Object`, which, by default, sorts the processes alphabetically by ProcessName.</span></span> <span data-ttu-id="43beb-136">結果はパイプを使用してコマンドレットに渡され、 `Select-Object` 各オブジェクトの ProcessName プロパティの値のみが選択されます。</span><span class="sxs-lookup"><span data-stu-id="43beb-136">The results are piped to the `Select-Object` cmdlet, which selects only the values of the ProcessName property of each object.</span></span> <span data-ttu-id="43beb-137">結果は、にパイプ処理されて、重複が除去され `Get-Unique` ます。</span><span class="sxs-lookup"><span data-stu-id="43beb-137">The results are then piped to `Get-Unique` to eliminate duplicates.</span></span>

<span data-ttu-id="43beb-138">**Asstring** パラメーターは、 `Get-Unique` **ProcessName** 値を文字列として扱うように指示します。</span><span class="sxs-lookup"><span data-stu-id="43beb-138">The **AsString** parameter tells `Get-Unique` to treat the **ProcessName** values as strings.</span></span>
<span data-ttu-id="43beb-139">このパラメーターを指定しない場合、は `Get-Unique` **ProcessName** 値をオブジェクトとして扱い、オブジェクトの1つのインスタンス (つまりリスト内の最初のプロセス名) のみを返します。</span><span class="sxs-lookup"><span data-stu-id="43beb-139">Without this parameter, `Get-Unique` treats the **ProcessName** values as objects and returns only one instance of the object, that is, the first process name in the list.</span></span>

## <span data-ttu-id="43beb-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="43beb-140">PARAMETERS</span></span>

### <span data-ttu-id="43beb-141">-AsString</span><span class="sxs-lookup"><span data-stu-id="43beb-141">-AsString</span></span>

<span data-ttu-id="43beb-142">このコマンドレットがデータを文字列として使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="43beb-142">Indicates that this cmdlet uses the data as a string.</span></span> <span data-ttu-id="43beb-143">このパラメーターを指定しないと、データはオブジェクトとして扱われるため、ファイルのコレクションなど、同じ型のオブジェクトのコレクションをに送信すると、 `Get-Unique` 1 つだけが返されます (最初の)。</span><span class="sxs-lookup"><span data-stu-id="43beb-143">Without this parameter, data is treated as an object, so when you submit a collection of objects of the same type to `Get-Unique`, such as a collection of files, it returns just one (the first).</span></span> <span data-ttu-id="43beb-144">このパラメーターを使用すると、ファイル名などのオブジェクトのプロパティの一意の値を検索できます。</span><span class="sxs-lookup"><span data-stu-id="43beb-144">You can use this parameter to find the unique values of object properties, such as the file names.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43beb-145">-InputObject</span><span class="sxs-lookup"><span data-stu-id="43beb-145">-InputObject</span></span>

<span data-ttu-id="43beb-146">の入力を指定し `Get-Unique` ます。</span><span class="sxs-lookup"><span data-stu-id="43beb-146">Specifies input for `Get-Unique`.</span></span> <span data-ttu-id="43beb-147">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="43beb-147">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="43beb-148">このコマンドレットは、 **InputObject** を使用して送信された入力をコレクションとして扱います。</span><span class="sxs-lookup"><span data-stu-id="43beb-148">This cmdlet treats the input submitted by using **InputObject** as a collection.</span></span> <span data-ttu-id="43beb-149">コレクション内の個々の項目は列挙されません。</span><span class="sxs-lookup"><span data-stu-id="43beb-149">it does not enumerate individual items in the collection.</span></span> <span data-ttu-id="43beb-150">コレクションは1つの項目であるため、 **InputObject** を使用して送信された入力は常に変更されずに返されます。</span><span class="sxs-lookup"><span data-stu-id="43beb-150">Because the collection is a single item, input submitted by using **InputObject** is always returned unchanged.</span></span>

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

### <span data-ttu-id="43beb-151">-OnType</span><span class="sxs-lookup"><span data-stu-id="43beb-151">-OnType</span></span>

<span data-ttu-id="43beb-152">このコマンドレットが各型のオブジェクトを1つだけ返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="43beb-152">Indicates that this cmdlet returns only one object of each type.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UniqueByType
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43beb-153">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="43beb-153">CommonParameters</span></span>

<span data-ttu-id="43beb-154">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="43beb-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="43beb-155">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43beb-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="43beb-156">入力</span><span class="sxs-lookup"><span data-stu-id="43beb-156">INPUTS</span></span>

### <span data-ttu-id="43beb-157">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="43beb-157">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="43beb-158">パイプを使用して任意の型のオブジェクトをにパイプすることができ `Get-Unique` ます。</span><span class="sxs-lookup"><span data-stu-id="43beb-158">You can pipe any type of object to `Get-Unique`.</span></span>

## <span data-ttu-id="43beb-159">出力</span><span class="sxs-lookup"><span data-stu-id="43beb-159">OUTPUTS</span></span>

### <span data-ttu-id="43beb-160">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="43beb-160">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="43beb-161">が返すオブジェクトの型 `Get-Unique` は、入力によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="43beb-161">The type of object that `Get-Unique` returns is determined by the input.</span></span>

## <span data-ttu-id="43beb-162">注</span><span class="sxs-lookup"><span data-stu-id="43beb-162">NOTES</span></span>

<span data-ttu-id="43beb-163">また、組み込みエイリアスであるを参照することもでき `Get-Unique` `gu` ます。</span><span class="sxs-lookup"><span data-stu-id="43beb-163">You can also refer to `Get-Unique` by its built-in alias, `gu`.</span></span> <span data-ttu-id="43beb-164">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43beb-164">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="43beb-165">リストを並べ替えるには、Sort-Object を使用します。</span><span class="sxs-lookup"><span data-stu-id="43beb-165">To sort a list, use Sort-Object.</span></span> <span data-ttu-id="43beb-166">また、の **unique** パラメーターを使用して、 `Sort-Object` リスト内の一意の項目を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="43beb-166">You can also use the **Unique** parameter of `Sort-Object` to find the unique items in a list.</span></span>

## <span data-ttu-id="43beb-167">関連リンク</span><span class="sxs-lookup"><span data-stu-id="43beb-167">RELATED LINKS</span></span>

[<span data-ttu-id="43beb-168">Select-Object</span><span class="sxs-lookup"><span data-stu-id="43beb-168">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="43beb-169">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="43beb-169">Sort-Object</span></span>](Sort-Object.md)

