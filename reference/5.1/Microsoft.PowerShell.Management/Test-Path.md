---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-path?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Path
ms.openlocfilehash: ced5a5db05674c15fefada73ab55969d724117e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214331"
---
# <span data-ttu-id="ee371-103">Test-Path</span><span class="sxs-lookup"><span data-stu-id="ee371-103">Test-Path</span></span>

## <span data-ttu-id="ee371-104">概要</span><span class="sxs-lookup"><span data-stu-id="ee371-104">SYNOPSIS</span></span>
<span data-ttu-id="ee371-105">パスのすべての要素が存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ee371-105">Determines whether all elements of a path exist.</span></span>

## <span data-ttu-id="ee371-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ee371-106">SYNTAX</span></span>

### <span data-ttu-id="ee371-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="ee371-107">Path (Default)</span></span>

```
Test-Path [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>] [-UseTransaction]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

### <span data-ttu-id="ee371-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ee371-108">LiteralPath</span></span>

```
Test-Path -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>] [-UseTransaction]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

## <span data-ttu-id="ee371-109">Description</span><span class="sxs-lookup"><span data-stu-id="ee371-109">DESCRIPTION</span></span>

<span data-ttu-id="ee371-110">この `Test-Path` コマンドレットは、パスのすべての要素が存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ee371-110">The `Test-Path` cmdlet determines whether all elements of the path exist.</span></span> <span data-ttu-id="ee371-111">すべての `$True` 要素が存在し、不足している場合はを返し `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="ee371-111">It returns `$True` if all elements exist and `$False` if any are missing.</span></span> <span data-ttu-id="ee371-112">また、パスの構文が有効かどうか、およびパスがコンテナーまたはターミナルまたはリーフの要素を指しているかどうかを判断することもできます。</span><span class="sxs-lookup"><span data-stu-id="ee371-112">It can also tell whether the path syntax is valid and whether the path leads to a container or a terminal or leaf element.</span></span> <span data-ttu-id="ee371-113">が空白の場合は `Path` 、 `$False` が返されます。</span><span class="sxs-lookup"><span data-stu-id="ee371-113">If the `Path` is whitespace, then `$False` is returned.</span></span> <span data-ttu-id="ee371-114">`Path`が空の文字列、 `$null` 、配列 `$null` または空の配列の場合は、終了しないエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="ee371-114">If the `Path` is an empty string, `$null`, array of `$null` or empty array, a non-terminating error is returned.</span></span>

## <span data-ttu-id="ee371-115">例</span><span class="sxs-lookup"><span data-stu-id="ee371-115">EXAMPLES</span></span>

### <span data-ttu-id="ee371-116">例 1: パスをテストする</span><span class="sxs-lookup"><span data-stu-id="ee371-116">Example 1: Test a path</span></span>

```powershell
Test-Path -Path "C:\Documents and Settings\DavidC"
```

```Output
True
```

<span data-ttu-id="ee371-117">このコマンドは、パス内のすべての要素 (つまり、C: ディレクトリ、Documents and Settings ディレクトリ、および DavidC ディレクトリ) が存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ee371-117">This command checks whether all elements in the path exist, that is, the C: directory, the Documents and Settings directory, and the DavidC directory.</span></span> <span data-ttu-id="ee371-118">不足している場合、コマンドレットはを返し `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="ee371-118">If any are missing, the cmdlet returns `$False`.</span></span>
<span data-ttu-id="ee371-119">それ以外の場合は、 `$True`を返します。</span><span class="sxs-lookup"><span data-stu-id="ee371-119">Otherwise, it returns `$True`.</span></span>

### <span data-ttu-id="ee371-120">例 2: プロファイルのパスをテストする</span><span class="sxs-lookup"><span data-stu-id="ee371-120">Example 2: Test the path of a profile</span></span>

```powershell
Test-Path -Path $profile
```

```Output
False
```

```powershell
Test-Path -Path $profile -IsValid
```

```Output
True
```

<span data-ttu-id="ee371-121">これらのコマンドは、PowerShell プロファイルのパスをテストします。</span><span class="sxs-lookup"><span data-stu-id="ee371-121">These commands test the path of the PowerShell profile.</span></span>

<span data-ttu-id="ee371-122">最初のコマンドは、パス中のすべての要素が存在するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="ee371-122">The first command determines whether all elements in the path exist.</span></span> <span data-ttu-id="ee371-123">2 番目のコマンドは、パスの構文が正しいかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ee371-123">The second command determines whether the syntax of the path is correct.</span></span> <span data-ttu-id="ee371-124">この場合、パスはですが、 `$False` 構文は正しい `$True` です。</span><span class="sxs-lookup"><span data-stu-id="ee371-124">In this case, the path is `$False`, but the syntax is correct `$True`.</span></span> <span data-ttu-id="ee371-125">これらのコマンドは、プロファイルが `$profile` 存在しない場合でも、プロファイルの場所を指す自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="ee371-125">These commands use `$profile`, the automatic variable that points to the location for the profile, even if the profile does not exist.</span></span>

<span data-ttu-id="ee371-126">自動変数の詳細については、「about_Automatic_Variables」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee371-126">For more information about automatic variables, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="ee371-127">例 3: 指定された種類以外のファイルがあるかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="ee371-127">Example 3: Check whether there are any files besides a specified type</span></span>

```powershell
Test-Path -Path "C:\CAD\Commercial Buildings\*" -Exclude *.dwg
```

```Output
False
```

<span data-ttu-id="ee371-128">このコマンドは、ファイルが .dwg ファイル以外の商用施設ディレクトリにあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ee371-128">This command checks whether there are any files in the Commercial Buildings directory other than .dwg files.</span></span>

<span data-ttu-id="ee371-129">このコマンドは path **パラメーターを使用して** パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee371-129">The command uses the **Path** parameter to specify the path.</span></span> <span data-ttu-id="ee371-130">パスにはスペースが含まれているため、パスは引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="ee371-130">Because the path includes a space, the path is enclosed in quotation marks.</span></span> <span data-ttu-id="ee371-131">パスの末尾のアスタリスクは、Commercial Building ディレクトリの内容を表します。</span><span class="sxs-lookup"><span data-stu-id="ee371-131">The asterisk at the end of the path indicates the contents of the Commercial Building directory.</span></span> <span data-ttu-id="ee371-132">このような長いパスでは、パスの最初の数文字を入力し、TAB キーを使用してパスを完成させます。</span><span class="sxs-lookup"><span data-stu-id="ee371-132">With long paths, such as this one, type the first few letters of the path, and then use the TAB key to complete the path.</span></span>

<span data-ttu-id="ee371-133">このコマンドは、 **Exclude** パラメーターを指定して、評価から除外されるファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee371-133">The command specifies the **Exclude** parameter to specify files that will be omitted from the evaluation.</span></span>

<span data-ttu-id="ee371-134">この場合、ディレクトリには .dwg ファイルしか含まれていないため、結果はになり `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="ee371-134">In this case, because the directory contains only .dwg files, the result is `$False`.</span></span>

### <span data-ttu-id="ee371-135">例 4: ファイルの確認</span><span class="sxs-lookup"><span data-stu-id="ee371-135">Example 4: Check for a file</span></span>

```powershell
Test-Path -Path $profile -PathType leaf
```

```Output
True
```

<span data-ttu-id="ee371-136">このコマンドは、変数に格納されているパスがファイルを指しているかどうかを確認し `$profile` ます。</span><span class="sxs-lookup"><span data-stu-id="ee371-136">This command checks whether the path stored in the `$profile` variable leads to a file.</span></span> <span data-ttu-id="ee371-137">この場合、PowerShell プロファイルがファイルであるため、 `.ps1` コマンドレットはを返し `$True` ます。</span><span class="sxs-lookup"><span data-stu-id="ee371-137">In this case, because the PowerShell profile is a `.ps1` file, the cmdlet returns `$True`.</span></span>

### <span data-ttu-id="ee371-138">例 5: レジストリのパスを確認する</span><span class="sxs-lookup"><span data-stu-id="ee371-138">Example 5: Check paths in the Registry</span></span>

<span data-ttu-id="ee371-139">これらのコマンド `Test-Path` は、PowerShell レジストリプロバイダーと共にを使用します。</span><span class="sxs-lookup"><span data-stu-id="ee371-139">These commands use `Test-Path` with the PowerShell registry provider.</span></span>

<span data-ttu-id="ee371-140">最初のコマンドは、 **Microsoft PowerShell** レジストリキーのレジストリパスがシステム上で正しいかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="ee371-140">The first command tests whether the registry path of the **Microsoft.PowerShell** registry key is correct on the system.</span></span> <span data-ttu-id="ee371-141">PowerShell が正しくインストールされている場合、コマンドレットはを返し `$True` ます。</span><span class="sxs-lookup"><span data-stu-id="ee371-141">If PowerShell is installed correctly, the cmdlet returns `$True`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee371-142">`Test-Path` は、すべての PowerShell プロバイダーで正しく機能しません。</span><span class="sxs-lookup"><span data-stu-id="ee371-142">`Test-Path` does not work correctly with all PowerShell providers.</span></span> <span data-ttu-id="ee371-143">たとえば、を使用してレジストリキーのパスをテストすることはできますが、レジストリエントリ `Test-Path` が存在する場合でも、それを使用してレジストリエントリのパスをテストすると、常にを返し `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="ee371-143">For example, you can use `Test-Path` to test the path of a registry key, but if you use it to test the path of a registry entry, it always returns `$False`, even if the registry entry is present.</span></span>

```powershell
Test-Path -Path "HKLM:\Software\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell"
```

```Output
True
```

```powershell
Test-Path -Path "HKLM:\Software\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell\ExecutionPolicy"
```

```Output
False
```

### <span data-ttu-id="ee371-144">例 6: ファイルが指定した日付より新しいかどうかをテストする</span><span class="sxs-lookup"><span data-stu-id="ee371-144">Example 6: Test if a file is newer than a specified date</span></span>

<span data-ttu-id="ee371-145">このコマンドは、 **Newerthan** dynamic パラメーターを使用して、コンピューター上の "PowerShell.exe" ファイルが2009年7月13日より新しいかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="ee371-145">This command uses the **NewerThan** dynamic parameter to determine whether the "PowerShell.exe" file on the computer is newer than "July 13, 2009".</span></span>

<span data-ttu-id="ee371-146">NewerThan パラメーターはファイル システム ドライブでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="ee371-146">The NewerThan parameter works only in file system drives.</span></span>

```powershell
Test-Path $pshome\PowerShell.exe -NewerThan "July 13, 2009"
```

```Output
True
```

### <span data-ttu-id="ee371-147">例 7: 値として null でパスをテストする</span><span class="sxs-lookup"><span data-stu-id="ee371-147">Example 7: Test a path with null as the value</span></span>

<span data-ttu-id="ee371-148">配列の配列または空の配列に対して返されたエラーは、 `null` `null` 終了しないエラーです。</span><span class="sxs-lookup"><span data-stu-id="ee371-148">The error returned for `null`, array of `null` or empty array is a non-terminating error.</span></span> <span data-ttu-id="ee371-149">を使用して抑制することができ `-ErrorAction SilentlyContinue` ます。</span><span class="sxs-lookup"><span data-stu-id="ee371-149">It can be suppress by using `-ErrorAction SilentlyContinue`.</span></span> <span data-ttu-id="ee371-150">次の例は、エラーを返すすべてのケースを示して `NullPathNotPermitted` います。</span><span class="sxs-lookup"><span data-stu-id="ee371-150">The following example shows all cases which return the `NullPathNotPermitted` error.</span></span>

```powershell
Test-Path $null
Test-Path $null, $null
Test-Path @()
```

```Output
Test-Path : Cannot bind argument to parameter 'Path' because it is null.
At line:1 char:11
+ Test-Path $null
+           ~~~~~
    + CategoryInfo          : InvalidData: (:) [Test-Path], ParameterBindingValidationException
    + FullyQualifiedErrorId : ParameterArgumentValidationErrorNullNotAllowed,Microsoft.PowerShell.Commands.TestPathCommand
```

### <span data-ttu-id="ee371-151">例 8: 値として空白を含むパスをテストする</span><span class="sxs-lookup"><span data-stu-id="ee371-151">Example 8: Test a path with whitespace as the value</span></span>

<span data-ttu-id="ee371-152">パラメーターに空白文字列を指定すると `-Path` 、 **True** が返されます。</span><span class="sxs-lookup"><span data-stu-id="ee371-152">When a whitespace string is provided for the the `-Path` parameter, it returns **True** .</span></span> <span data-ttu-id="ee371-153">空の文字列を指定すると、は `Test-Path` エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="ee371-153">When an empty string is provided, `Test-Path` returns an error.</span></span> <span data-ttu-id="ee371-154">次の例では、空白と空の文字列を示します。</span><span class="sxs-lookup"><span data-stu-id="ee371-154">The following example shows whitespace and empty string.</span></span>

```powershell
Test-Path ' '
Test-Path ''
```

```Output
True
Test-Path : Cannot bind argument to parameter 'Path' because it is an empty string.
At line:1 char:11
+ Test-Path ''
+           ~~
    + CategoryInfo          : InvalidData: (:) [Test-Path], ParameterBindingValidationException
    + FullyQualifiedErrorId : ParameterArgumentValidationErrorEmptyStringNotAllowed,Microsoft.PowerShell.Commands.TestPathCommand
```

## <span data-ttu-id="ee371-155">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ee371-155">PARAMETERS</span></span>

### <span data-ttu-id="ee371-156">-Credential</span><span class="sxs-lookup"><span data-stu-id="ee371-156">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="ee371-157">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ee371-157">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="ee371-158">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="ee371-158">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ee371-159">-除外</span><span class="sxs-lookup"><span data-stu-id="ee371-159">-Exclude</span></span>

<span data-ttu-id="ee371-160">このコマンドレットで省略される項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="ee371-160">Specifies items that this cmdlet omits.</span></span> <span data-ttu-id="ee371-161">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="ee371-161">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="ee371-162">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="ee371-162">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="ee371-163">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ee371-163">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ee371-164">-Filter</span><span class="sxs-lookup"><span data-stu-id="ee371-164">-Filter</span></span>

<span data-ttu-id="ee371-165">プロバイダーの形式または言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee371-165">Specifies a filter in the format or language of the provider.</span></span> <span data-ttu-id="ee371-166">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="ee371-166">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="ee371-167">ワイルドカード文字の使用など、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ee371-167">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span> <span data-ttu-id="ee371-168">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、オブジェクトを取得するときにプロバイダーによって適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="ee371-168">Filters are more efficient than other parameters, because the provider applies them when it retrieves the objects instead of having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ee371-169">-Include</span><span class="sxs-lookup"><span data-stu-id="ee371-169">-Include</span></span>

<span data-ttu-id="ee371-170">このコマンドレットによってテストされるパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee371-170">Specifies paths that this cmdlet tests.</span></span> <span data-ttu-id="ee371-171">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="ee371-171">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="ee371-172">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="ee371-172">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="ee371-173">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ee371-173">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ee371-174">-IsValid</span><span class="sxs-lookup"><span data-stu-id="ee371-174">-IsValid</span></span>

<span data-ttu-id="ee371-175">パスの要素が存在するかどうかに関係なく、このコマンドレットがパスの構文をテストすることを示します。</span><span class="sxs-lookup"><span data-stu-id="ee371-175">Indicates that this cmdlet tests the syntax of the path, regardless of whether the elements of the path exist.</span></span> <span data-ttu-id="ee371-176">このコマンドレットは `$True` 、パスの構文が有効である場合はを返し、そうでない場合はを返し `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="ee371-176">This cmdlet returns `$True` if the path syntax is valid and `$False` if it is not.</span></span>

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

### <span data-ttu-id="ee371-177">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ee371-177">-LiteralPath</span></span>

<span data-ttu-id="ee371-178">テストするパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee371-178">Specifies a path to be tested.</span></span> <span data-ttu-id="ee371-179">**Path** と異なり、 **LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ee371-179">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="ee371-180">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="ee371-180">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="ee371-181">PowerShell でエスケープシーケンスとして解釈される可能性のある文字がパスに含まれている場合は、そのパスを単一引用符で囲み、解釈されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee371-181">If the path includes characters that could be interpreted by PowerShell as escape sequences, you must enclose the path in single quote so that they won't be interpreted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ee371-182">-NewerThan</span><span class="sxs-lookup"><span data-stu-id="ee371-182">-NewerThan</span></span>

<span data-ttu-id="ee371-183">時刻を **DateTime** オブジェクトとして指定します。</span><span class="sxs-lookup"><span data-stu-id="ee371-183">Specify a time as a **DateTime** object.</span></span>

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ee371-184">-OlderThan</span><span class="sxs-lookup"><span data-stu-id="ee371-184">-OlderThan</span></span>

<span data-ttu-id="ee371-185">時刻を **DateTime** オブジェクトとして指定します。</span><span class="sxs-lookup"><span data-stu-id="ee371-185">Specify a time as a **DateTime** object.</span></span>

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ee371-186">-Path</span><span class="sxs-lookup"><span data-stu-id="ee371-186">-Path</span></span>

<span data-ttu-id="ee371-187">テストするパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee371-187">Specifies a path to be tested.</span></span> <span data-ttu-id="ee371-188">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ee371-188">Wildcard characters are permitted.</span></span> <span data-ttu-id="ee371-189">パスにスペースが含まれる場合は、二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="ee371-189">If the path includes spaces, enclose it in quotation marks.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="ee371-190">-PathType</span><span class="sxs-lookup"><span data-stu-id="ee371-190">-PathType</span></span>

<span data-ttu-id="ee371-191">パスの最後の要素の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="ee371-191">Specifies the type of the final element in the path.</span></span> <span data-ttu-id="ee371-192">このコマンドレットは、指定された型の要素の場合はを返し、そうでない場合はを返し `$True` `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="ee371-192">This cmdlet returns `$True` if the element is of the specified type and `$False` if it is not.</span></span> <span data-ttu-id="ee371-193">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ee371-193">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ee371-194">コンテナー。</span><span class="sxs-lookup"><span data-stu-id="ee371-194">Container.</span></span>
  <span data-ttu-id="ee371-195">ディレクトリやレジストリ キーのように、他の要素を含む要素です。</span><span class="sxs-lookup"><span data-stu-id="ee371-195">An element that contains other elements, such as a directory or registry key.</span></span>
- <span data-ttu-id="ee371-196">リーフ.</span><span class="sxs-lookup"><span data-stu-id="ee371-196">Leaf.</span></span>
  <span data-ttu-id="ee371-197">ファイルのように、他の要素を含まない要素です。</span><span class="sxs-lookup"><span data-stu-id="ee371-197">An element that does not contain other elements, such as a file.</span></span>
- <span data-ttu-id="ee371-198">いつ.</span><span class="sxs-lookup"><span data-stu-id="ee371-198">Any.</span></span>
  <span data-ttu-id="ee371-199">コンテナーまたはリーフのどちらかです。</span><span class="sxs-lookup"><span data-stu-id="ee371-199">Either a container or a leaf.</span></span>

<span data-ttu-id="ee371-200">パスの最終要素が特定の種類かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ee371-200">Tells whether the final element in the path is of a particular type.</span></span>

> [!CAUTION]
>
> <span data-ttu-id="ee371-201">PowerShell バージョン6.1.2 までは、 **IsValid** と **pathtype** スイッチが一緒に指定されている場合、 `Test-Path` コマンドレットは **pathtype** スイッチを無視し、パスの種類を検証せずに構文パスのみを検証します。</span><span class="sxs-lookup"><span data-stu-id="ee371-201">Up to PowerShell version 6.1.2, when the **IsValid** and **PathType** switches are specified together, the `Test-Path` cmdlet ignores the **PathType** switch and only validates the syntactic path without validating the path type.</span></span>
>
> <span data-ttu-id="ee371-202">[問題 #8607](https://github.com/PowerShell/PowerShell/issues/8607)によれば、この動作を修正することは将来のバージョンでは互換性に影響する変更になる可能性があります。これは、 **IsValid** および **pathtype** スイッチが個別のパラメーターセットに属しているため、この混乱を避けるために一緒に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ee371-202">According to [issue #8607](https://github.com/PowerShell/PowerShell/issues/8607), fixing this behavior may be a breaking change in a future version, where the **IsValid** and **PathType** switches belong to separate parameter sets, and thus, cannot be used together avoiding this confusion.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.TestPathType
Parameter Sets: (All)
Aliases: Type
Accepted values: Any, Container, Leaf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ee371-203">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="ee371-203">-UseTransaction</span></span>

<span data-ttu-id="ee371-204">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ee371-204">Includes the command in the active transaction.</span></span> <span data-ttu-id="ee371-205">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="ee371-205">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="ee371-206">詳細については、「」を参照してください [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)</span><span class="sxs-lookup"><span data-stu-id="ee371-206">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ee371-207">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ee371-207">CommonParameters</span></span>

<span data-ttu-id="ee371-208">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="ee371-208">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="ee371-209">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee371-209">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="ee371-210">入力</span><span class="sxs-lookup"><span data-stu-id="ee371-210">INPUTS</span></span>

### <span data-ttu-id="ee371-211">System.String</span><span class="sxs-lookup"><span data-stu-id="ee371-211">System.String</span></span>

<span data-ttu-id="ee371-212">パイプを使用してパスを含む文字列をこのコマンドレットに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="ee371-212">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="ee371-213">出力</span><span class="sxs-lookup"><span data-stu-id="ee371-213">OUTPUTS</span></span>

### <span data-ttu-id="ee371-214">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="ee371-214">System.Boolean</span></span>

<span data-ttu-id="ee371-215">コマンドレットでは、 **ブール** 値を返します。</span><span class="sxs-lookup"><span data-stu-id="ee371-215">The cmdlet returns a **Boolean** value.</span></span>

## <span data-ttu-id="ee371-216">注</span><span class="sxs-lookup"><span data-stu-id="ee371-216">NOTES</span></span>

<span data-ttu-id="ee371-217">**パスの名詞を** 含むコマンドレット ( **path** コマンドレット) は、パス名と共に使用され、すべての PowerShell プロバイダーが解釈できる簡潔な形式の名前を返します。</span><span class="sxs-lookup"><span data-stu-id="ee371-217">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="ee371-218">プログラムやスクリプトで、パス名の全部または一部を特定の形式で表示するために使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="ee371-218">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span>
<span data-ttu-id="ee371-219">これは、 **Dirname** 、 **Normpath** 、 **realpath** 、 **Join** 、またはその他のパスマニピュレーターを使用する場合と同じように使用します。</span><span class="sxs-lookup"><span data-stu-id="ee371-219">Use them as you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

<span data-ttu-id="ee371-220">`Test-Path`は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="ee371-220">The `Test-Path` is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="ee371-221">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="ee371-221">To list the providers available in your session, type `Get-PSProvider`.</span></span>
<span data-ttu-id="ee371-222">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee371-222">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="ee371-223">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ee371-223">RELATED LINKS</span></span>

[<span data-ttu-id="ee371-224">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="ee371-224">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="ee371-225">Join-Path</span><span class="sxs-lookup"><span data-stu-id="ee371-225">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="ee371-226">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="ee371-226">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="ee371-227">Split-Path</span><span class="sxs-lookup"><span data-stu-id="ee371-227">Split-Path</span></span>](Split-Path.md)