---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-path?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Path
ms.openlocfilehash: a79f12739643a873703b39d9d07e8b7db01dfbb4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599923"
---
# <span data-ttu-id="54ef6-102">Test-Path</span><span class="sxs-lookup"><span data-stu-id="54ef6-102">Test-Path</span></span>

## <span data-ttu-id="54ef6-103">概要</span><span class="sxs-lookup"><span data-stu-id="54ef6-103">SYNOPSIS</span></span>
<span data-ttu-id="54ef6-104">パスのすべての要素が存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-104">Determines whether all elements of a path exist.</span></span>

## <span data-ttu-id="54ef6-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="54ef6-105">SYNTAX</span></span>

### <span data-ttu-id="54ef6-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="54ef6-106">Path (Default)</span></span>

```
Test-Path [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

### <span data-ttu-id="54ef6-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="54ef6-107">LiteralPath</span></span>

```
Test-Path -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

## <span data-ttu-id="54ef6-108">Description</span><span class="sxs-lookup"><span data-stu-id="54ef6-108">DESCRIPTION</span></span>

<span data-ttu-id="54ef6-109">この `Test-Path` コマンドレットは、パスのすべての要素が存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-109">The `Test-Path` cmdlet determines whether all elements of the path exist.</span></span> <span data-ttu-id="54ef6-110">すべての `$True` 要素が存在し、不足している場合はを返し `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-110">It returns `$True` if all elements exist and `$False` if any are missing.</span></span> <span data-ttu-id="54ef6-111">また、パスの構文が有効かどうか、およびパスがコンテナーまたはターミナルまたはリーフの要素を指しているかどうかを判断することもできます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-111">It can also tell whether the path syntax is valid and whether the path leads to a container or a terminal or leaf element.</span></span> <span data-ttu-id="54ef6-112">が空白文字の場合は、 `Path` `$False` が返されます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-112">If the `Path` is whitespace an empty string, then `$False` is returned.</span></span> <span data-ttu-id="54ef6-113">`Path`が、配列 `$null` の配列または空の配列の場合は、 `$null` 終了しないエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-113">If the `Path` is `$null`, array of `$null` or empty array, a non-terminating error is returned.</span></span>

## <span data-ttu-id="54ef6-114">例</span><span class="sxs-lookup"><span data-stu-id="54ef6-114">EXAMPLES</span></span>

### <span data-ttu-id="54ef6-115">例 1: パスをテストする</span><span class="sxs-lookup"><span data-stu-id="54ef6-115">Example 1: Test a path</span></span>

```powershell
Test-Path -Path "C:\Documents and Settings\DavidC"
```

```Output
True
```

<span data-ttu-id="54ef6-116">このコマンドは、パス内のすべての要素 (つまり、C: ディレクトリ、Documents and Settings ディレクトリ、および DavidC ディレクトリ) が存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-116">This command checks whether all elements in the path exist, that is, the C: directory, the Documents and Settings directory, and the DavidC directory.</span></span> <span data-ttu-id="54ef6-117">不足している場合、コマンドレットはを返し `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-117">If any are missing, the cmdlet returns `$False`.</span></span>
<span data-ttu-id="54ef6-118">それ以外の場合は `$True`を返します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-118">Otherwise, it returns `$True`.</span></span>

### <span data-ttu-id="54ef6-119">例 2: プロファイルのパスをテストする</span><span class="sxs-lookup"><span data-stu-id="54ef6-119">Example 2: Test the path of a profile</span></span>

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

<span data-ttu-id="54ef6-120">これらのコマンドは、PowerShell プロファイルのパスをテストします。</span><span class="sxs-lookup"><span data-stu-id="54ef6-120">These commands test the path of the PowerShell profile.</span></span>

<span data-ttu-id="54ef6-121">最初のコマンドは、パス中のすべての要素が存在するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-121">The first command determines whether all elements in the path exist.</span></span> <span data-ttu-id="54ef6-122">2 番目のコマンドは、パスの構文が正しいかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-122">The second command determines whether the syntax of the path is correct.</span></span> <span data-ttu-id="54ef6-123">この場合、パスはですが、 `$False` 構文は正しい `$True` です。</span><span class="sxs-lookup"><span data-stu-id="54ef6-123">In this case, the path is `$False`, but the syntax is correct `$True`.</span></span> <span data-ttu-id="54ef6-124">これらのコマンドは、プロファイルが `$profile` 存在しない場合でも、プロファイルの場所を指す自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-124">These commands use `$profile`, the automatic variable that points to the location for the profile, even if the profile does not exist.</span></span>

<span data-ttu-id="54ef6-125">自動変数の詳細については、「about_Automatic_Variables」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54ef6-125">For more information about automatic variables, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="54ef6-126">例 3: 指定された種類以外のファイルがあるかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="54ef6-126">Example 3: Check whether there are any files besides a specified type</span></span>

```powershell
Test-Path -Path "C:\CAD\Commercial Buildings\*" -Exclude *.dwg
```

```Output
False
```

<span data-ttu-id="54ef6-127">このコマンドは、ファイルが .dwg ファイル以外の商用施設ディレクトリにあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-127">This command checks whether there are any files in the Commercial Buildings directory other than .dwg files.</span></span>

<span data-ttu-id="54ef6-128">このコマンドは path **パラメーターを使用して** パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-128">The command uses the **Path** parameter to specify the path.</span></span> <span data-ttu-id="54ef6-129">パスにはスペースが含まれているため、パスは引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-129">Because the path includes a space, the path is enclosed in quotation marks.</span></span> <span data-ttu-id="54ef6-130">パスの末尾のアスタリスクは、Commercial Building ディレクトリの内容を表します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-130">The asterisk at the end of the path indicates the contents of the Commercial Building directory.</span></span> <span data-ttu-id="54ef6-131">このような長いパスでは、パスの最初の数文字を入力し、TAB キーを使用してパスを完成させます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-131">With long paths, such as this one, type the first few letters of the path, and then use the TAB key to complete the path.</span></span>

<span data-ttu-id="54ef6-132">このコマンドは、 **Exclude** パラメーターを指定して、評価から除外されるファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-132">The command specifies the **Exclude** parameter to specify files that will be omitted from the evaluation.</span></span>

<span data-ttu-id="54ef6-133">この場合、ディレクトリには .dwg ファイルしか含まれていないため、結果はになり `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-133">In this case, because the directory contains only .dwg files, the result is `$False`.</span></span>

### <span data-ttu-id="54ef6-134">例 4: ファイルの確認</span><span class="sxs-lookup"><span data-stu-id="54ef6-134">Example 4: Check for a file</span></span>

```powershell
Test-Path -Path $profile -PathType leaf
```

```Output
True
```

<span data-ttu-id="54ef6-135">このコマンドは、変数に格納されているパスがファイルを指しているかどうかを確認し `$profile` ます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-135">This command checks whether the path stored in the `$profile` variable leads to a file.</span></span> <span data-ttu-id="54ef6-136">この場合、PowerShell プロファイルがファイルであるため、 `.ps1` コマンドレットはを返し `$True` ます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-136">In this case, because the PowerShell profile is a `.ps1` file, the cmdlet returns `$True`.</span></span>

### <span data-ttu-id="54ef6-137">例 5: レジストリのパスを確認する</span><span class="sxs-lookup"><span data-stu-id="54ef6-137">Example 5: Check paths in the Registry</span></span>

<span data-ttu-id="54ef6-138">これらのコマンド `Test-Path` は、PowerShell レジストリプロバイダーと共にを使用します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-138">These commands use `Test-Path` with the PowerShell registry provider.</span></span>

<span data-ttu-id="54ef6-139">最初のコマンドは、 **Microsoft PowerShell** レジストリキーのレジストリパスがシステム上で正しいかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="54ef6-139">The first command tests whether the registry path of the **Microsoft.PowerShell** registry key is correct on the system.</span></span> <span data-ttu-id="54ef6-140">PowerShell が正しくインストールされている場合、コマンドレットはを返し `$True` ます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-140">If PowerShell is installed correctly, the cmdlet returns `$True`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54ef6-141">`Test-Path` は、すべての PowerShell プロバイダーで正しく機能しません。</span><span class="sxs-lookup"><span data-stu-id="54ef6-141">`Test-Path` does not work correctly with all PowerShell providers.</span></span> <span data-ttu-id="54ef6-142">たとえば、を使用してレジストリキーのパスをテストすることはできますが、レジストリエントリ `Test-Path` が存在する場合でも、それを使用してレジストリエントリのパスをテストすると、常にを返し `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-142">For example, you can use `Test-Path` to test the path of a registry key, but if you use it to test the path of a registry entry, it always returns `$False`, even if the registry entry is present.</span></span>

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

### <span data-ttu-id="54ef6-143">例 6: ファイルが指定した日付より新しいかどうかをテストする</span><span class="sxs-lookup"><span data-stu-id="54ef6-143">Example 6: Test if a file is newer than a specified date</span></span>

<span data-ttu-id="54ef6-144">このコマンドは、 **Newerthan** dynamic パラメーターを使用して、コンピューター上の "PowerShell.exe" ファイルが2009年7月13日より新しいかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-144">This command uses the **NewerThan** dynamic parameter to determine whether the "PowerShell.exe" file on the computer is newer than "July 13, 2009".</span></span>

<span data-ttu-id="54ef6-145">NewerThan パラメーターはファイル システム ドライブでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="54ef6-145">The NewerThan parameter works only in file system drives.</span></span>

```powershell
Test-Path $pshome\PowerShell.exe -NewerThan "July 13, 2009"
```

```Output
True
```

### <span data-ttu-id="54ef6-146">例 7: 値として null でパスをテストする</span><span class="sxs-lookup"><span data-stu-id="54ef6-146">Example 7: Test a path with null as the value</span></span>

<span data-ttu-id="54ef6-147">配列の配列または空の配列に対して返されたエラーは、 `null` `null` 終了しないエラーです。</span><span class="sxs-lookup"><span data-stu-id="54ef6-147">The error returned for `null`, array of `null` or empty array is a non-terminating error.</span></span> <span data-ttu-id="54ef6-148">を使用して抑制することができ `-ErrorAction SilentlyContinue` ます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-148">It can be suppress by using `-ErrorAction SilentlyContinue`.</span></span> <span data-ttu-id="54ef6-149">次の例は、エラーを返すすべてのケースを示して `NullPathNotPermitted` います。</span><span class="sxs-lookup"><span data-stu-id="54ef6-149">The following example shows all cases which return the `NullPathNotPermitted` error.</span></span>

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

### <span data-ttu-id="54ef6-150">例 8: 値として空白を含むパスをテストする</span><span class="sxs-lookup"><span data-stu-id="54ef6-150">Example 8: Test a path with whitespace as the value</span></span>

<span data-ttu-id="54ef6-151">パラメーターに空白または空の文字列を指定すると `-Path` 、 **False** が返されます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-151">When a whitespace or empty string is provided for the the `-Path` parameter, it returns **False**.</span></span>
<span data-ttu-id="54ef6-152">次の例では、空白と空の文字列を示します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-152">The following example show whitespace and empty string.</span></span>

```powershell
Test-Path ' '
Test-Path ''
```

```Output
False
False
```

## <span data-ttu-id="54ef6-153">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="54ef6-153">PARAMETERS</span></span>

### <span data-ttu-id="54ef6-154">-Credential</span><span class="sxs-lookup"><span data-stu-id="54ef6-154">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="54ef6-155">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="54ef6-155">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="54ef6-156">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-156">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="54ef6-157">-除外</span><span class="sxs-lookup"><span data-stu-id="54ef6-157">-Exclude</span></span>

<span data-ttu-id="54ef6-158">このコマンドレットで省略される項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-158">Specifies items that this cmdlet omits.</span></span> <span data-ttu-id="54ef6-159">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-159">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="54ef6-160">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-160">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="54ef6-161">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-161">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="54ef6-162">-Filter</span><span class="sxs-lookup"><span data-stu-id="54ef6-162">-Filter</span></span>

<span data-ttu-id="54ef6-163">プロバイダーの形式または言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-163">Specifies a filter in the format or language of the provider.</span></span> <span data-ttu-id="54ef6-164">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-164">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="54ef6-165">ワイルドカード文字の使用など、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="54ef6-165">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span> <span data-ttu-id="54ef6-166">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、オブジェクトを取得するときにプロバイダーによって適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="54ef6-166">Filters are more efficient than other parameters, because the provider applies them when it retrieves the objects instead of having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="54ef6-167">-Include</span><span class="sxs-lookup"><span data-stu-id="54ef6-167">-Include</span></span>

<span data-ttu-id="54ef6-168">このコマンドレットによってテストされるパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-168">Specifies paths that this cmdlet tests.</span></span> <span data-ttu-id="54ef6-169">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-169">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="54ef6-170">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-170">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="54ef6-171">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-171">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="54ef6-172">-IsValid</span><span class="sxs-lookup"><span data-stu-id="54ef6-172">-IsValid</span></span>

<span data-ttu-id="54ef6-173">パスの要素が存在するかどうかに関係なく、このコマンドレットがパスの構文をテストすることを示します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-173">Indicates that this cmdlet tests the syntax of the path, regardless of whether the elements of the path exist.</span></span> <span data-ttu-id="54ef6-174">このコマンドレットは `$True` 、パスの構文が有効である場合はを返し、そうでない場合はを返し `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-174">This cmdlet returns `$True` if the path syntax is valid and `$False` if it is not.</span></span>

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

### <span data-ttu-id="54ef6-175">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="54ef6-175">-LiteralPath</span></span>

<span data-ttu-id="54ef6-176">テストするパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-176">Specifies a path to be tested.</span></span> <span data-ttu-id="54ef6-177">**Path** と異なり、**LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-177">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="54ef6-178">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="54ef6-178">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="54ef6-179">PowerShell でエスケープシーケンスとして解釈される可能性のある文字がパスに含まれている場合は、そのパスを単一引用符で囲み、解釈されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54ef6-179">If the path includes characters that could be interpreted by PowerShell as escape sequences, you must enclose the path in single quote so that they won't be interpreted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="54ef6-180">-NewerThan</span><span class="sxs-lookup"><span data-stu-id="54ef6-180">-NewerThan</span></span>

<span data-ttu-id="54ef6-181">時刻を **DateTime** オブジェクトとして指定します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-181">Specify a time as a **DateTime** object.</span></span>

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

### <span data-ttu-id="54ef6-182">-OlderThan</span><span class="sxs-lookup"><span data-stu-id="54ef6-182">-OlderThan</span></span>

<span data-ttu-id="54ef6-183">時刻を **DateTime** オブジェクトとして指定します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-183">Specify a time as a **DateTime** object.</span></span>

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

### <span data-ttu-id="54ef6-184">-Path</span><span class="sxs-lookup"><span data-stu-id="54ef6-184">-Path</span></span>

<span data-ttu-id="54ef6-185">テストするパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-185">Specifies a path to be tested.</span></span> <span data-ttu-id="54ef6-186">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-186">Wildcard characters are permitted.</span></span> <span data-ttu-id="54ef6-187">パスにスペースが含まれる場合は、二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-187">If the path includes spaces, enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="54ef6-188">-PathType</span><span class="sxs-lookup"><span data-stu-id="54ef6-188">-PathType</span></span>

<span data-ttu-id="54ef6-189">パスの最後の要素の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-189">Specifies the type of the final element in the path.</span></span> <span data-ttu-id="54ef6-190">このコマンドレットは、指定された型の要素の場合はを返し、そうでない場合はを返し `$True` `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-190">This cmdlet returns `$True` if the element is of the specified type and `$False` if it is not.</span></span> <span data-ttu-id="54ef6-191">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="54ef6-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="54ef6-192">コンテナー。</span><span class="sxs-lookup"><span data-stu-id="54ef6-192">Container.</span></span>
  <span data-ttu-id="54ef6-193">ディレクトリやレジストリ キーのように、他の要素を含む要素です。</span><span class="sxs-lookup"><span data-stu-id="54ef6-193">An element that contains other elements, such as a directory or registry key.</span></span>
- <span data-ttu-id="54ef6-194">リーフ.</span><span class="sxs-lookup"><span data-stu-id="54ef6-194">Leaf.</span></span>
  <span data-ttu-id="54ef6-195">ファイルのように、他の要素を含まない要素です。</span><span class="sxs-lookup"><span data-stu-id="54ef6-195">An element that does not contain other elements, such as a file.</span></span>
- <span data-ttu-id="54ef6-196">いつ.</span><span class="sxs-lookup"><span data-stu-id="54ef6-196">Any.</span></span>
  <span data-ttu-id="54ef6-197">コンテナーまたはリーフのどちらかです。</span><span class="sxs-lookup"><span data-stu-id="54ef6-197">Either a container or a leaf.</span></span>

<span data-ttu-id="54ef6-198">パスの最終要素が特定の種類かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-198">Tells whether the final element in the path is of a particular type.</span></span>

> [!CAUTION]
>
> <span data-ttu-id="54ef6-199">PowerShell バージョン6.1.2 までは、 **IsValid** と **pathtype** スイッチが一緒に指定されている場合、 `Test-Path` コマンドレットは **pathtype** スイッチを無視し、パスの種類を検証せずに構文パスのみを検証します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-199">Up to PowerShell version 6.1.2, when the **IsValid** and **PathType** switches are specified together, the `Test-Path` cmdlet ignores the **PathType** switch and only validates the syntactic path without validating the path type.</span></span>
>
> <span data-ttu-id="54ef6-200">[問題 #8607](https://github.com/PowerShell/PowerShell/issues/8607)によれば、この動作を修正することは将来のバージョンでは互換性に影響する変更になる可能性があります。これは、 **IsValid** および **pathtype** スイッチが個別のパラメーターセットに属しているため、この混乱を避けるために一緒に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="54ef6-200">According to [issue #8607](https://github.com/PowerShell/PowerShell/issues/8607), fixing this behavior may be a breaking change in a future version, where the **IsValid** and **PathType** switches belong to separate parameter sets, and thus, cannot be used together avoiding this confusion.</span></span>

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

### <span data-ttu-id="54ef6-201">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="54ef6-201">CommonParameters</span></span>

<span data-ttu-id="54ef6-202">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-202">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="54ef6-203">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54ef6-203">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="54ef6-204">入力</span><span class="sxs-lookup"><span data-stu-id="54ef6-204">INPUTS</span></span>

### <span data-ttu-id="54ef6-205">System.String</span><span class="sxs-lookup"><span data-stu-id="54ef6-205">System.String</span></span>

<span data-ttu-id="54ef6-206">パイプを使用してパスを含む文字列をこのコマンドレットに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="54ef6-206">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="54ef6-207">出力</span><span class="sxs-lookup"><span data-stu-id="54ef6-207">OUTPUTS</span></span>

### <span data-ttu-id="54ef6-208">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="54ef6-208">System.Boolean</span></span>

<span data-ttu-id="54ef6-209">コマンドレットでは、 **ブール** 値を返します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-209">The cmdlet returns a **Boolean** value.</span></span>

## <span data-ttu-id="54ef6-210">注</span><span class="sxs-lookup"><span data-stu-id="54ef6-210">NOTES</span></span>

<span data-ttu-id="54ef6-211">**パスの名詞を** 含むコマンドレット ( **path** コマンドレット) は、パス名と共に使用され、すべての PowerShell プロバイダーが解釈できる簡潔な形式の名前を返します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-211">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="54ef6-212">プログラムやスクリプトで、パス名の全部または一部を特定の形式で表示するために使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="54ef6-212">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span>
<span data-ttu-id="54ef6-213">これは、 **Dirname**、 **Normpath**、 **realpath**、 **Join**、またはその他のパスマニピュレーターを使用する場合と同じように使用します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-213">Use them as you would use **Dirname**, **Normpath**, **Realpath**, **Join**, or other path manipulators.</span></span>

<span data-ttu-id="54ef6-214">`Test-Path`は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="54ef6-214">The `Test-Path` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="54ef6-215">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="54ef6-215">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="54ef6-216">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54ef6-216">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="54ef6-217">関連リンク</span><span class="sxs-lookup"><span data-stu-id="54ef6-217">RELATED LINKS</span></span>

[<span data-ttu-id="54ef6-218">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="54ef6-218">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="54ef6-219">Join-Path</span><span class="sxs-lookup"><span data-stu-id="54ef6-219">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="54ef6-220">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="54ef6-220">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="54ef6-221">Split-Path</span><span class="sxs-lookup"><span data-stu-id="54ef6-221">Split-Path</span></span>](Split-Path.md)
