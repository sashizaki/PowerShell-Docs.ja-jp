---
description: 高度な関数でパラメーターセットを定義して使用する方法について説明します。
title: about_Parameter_Sets
ms.date: 02/11/2020
ms.openlocfilehash: e4cfbc13f981bcc93c8a0a3c799851e83df7746c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223808"
---
# <a name="about-parameter-sets"></a><span data-ttu-id="72418-103">パラメーターセットについて</span><span class="sxs-lookup"><span data-stu-id="72418-103">About parameter sets</span></span>

## <a name="short-description"></a><span data-ttu-id="72418-104">概要</span><span class="sxs-lookup"><span data-stu-id="72418-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="72418-105">高度な関数でパラメーターセットを定義して使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="72418-105">Describes how to define and use parameter sets in advanced functions.</span></span>

## <a name="long-description"></a><span data-ttu-id="72418-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="72418-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="72418-107">PowerShell では、パラメーターセットを使用して、さまざまなシナリオに対して異なるアクションを実行できる単一の関数を記述できます。</span><span class="sxs-lookup"><span data-stu-id="72418-107">PowerShell uses parameter sets to enable you to write a single function that can do different actions for different scenarios.</span></span> <span data-ttu-id="72418-108">パラメーターセットを使用すると、さまざまなパラメーターをユーザーに公開できます。</span><span class="sxs-lookup"><span data-stu-id="72418-108">Parameter sets enable you to expose different parameters to the user.</span></span> <span data-ttu-id="72418-109">また、ユーザーが指定したパラメーターに基づいて異なる情報を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="72418-109">And, to return different information based on the parameters specified by the user.</span></span>

## <a name="parameter-set-requirements"></a><span data-ttu-id="72418-110">パラメーターセットの要件</span><span class="sxs-lookup"><span data-stu-id="72418-110">Parameter set requirements</span></span>

<span data-ttu-id="72418-111">すべてのパラメーターセットには、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="72418-111">The following requirements apply to all parameter sets.</span></span>

- <span data-ttu-id="72418-112">各パラメーターセットには、少なくとも1つの一意のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="72418-112">Each parameter set must have at least one unique parameter.</span></span> <span data-ttu-id="72418-113">可能であれば、このパラメーターを必須パラメーターにします。</span><span class="sxs-lookup"><span data-stu-id="72418-113">If possible, make this parameter a mandatory parameter.</span></span>

- <span data-ttu-id="72418-114">複数の位置指定パラメーターを含むパラメーターセットでは、パラメーターごとに一意の位置を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72418-114">A parameter set that contains multiple positional parameters must define unique positions for each parameter.</span></span> <span data-ttu-id="72418-115">2つの位置指定パラメーターで同じ位置を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="72418-115">No two positional parameters can specify the same position.</span></span>

- <span data-ttu-id="72418-116">値がのキーワードを宣言できるのは、set 内の1つのパラメーターだけ `ValueFromPipeline` `true` です。</span><span class="sxs-lookup"><span data-stu-id="72418-116">Only one parameter in a set can declare the `ValueFromPipeline` keyword with a value of `true`.</span></span> <span data-ttu-id="72418-117">複数のパラメーターでキーワードを定義し、値をにすることができ `ValueFromPipelineByPropertyName` `true` ます。</span><span class="sxs-lookup"><span data-stu-id="72418-117">Multiple parameters can define the `ValueFromPipelineByPropertyName` keyword with a value of `true`.</span></span>

- <span data-ttu-id="72418-118">パラメーターにパラメーターセットが指定されていない場合、パラメーターはすべてのパラメーターセットに属します。</span><span class="sxs-lookup"><span data-stu-id="72418-118">If no parameter set is specified for a parameter, the parameter belongs to all parameter sets.</span></span>

> [!NOTE]
> <span data-ttu-id="72418-119">パラメーターセットは32個に制限されています。</span><span class="sxs-lookup"><span data-stu-id="72418-119">There is a limit of 32 parameter sets.</span></span>

## <a name="default-parameter-sets"></a><span data-ttu-id="72418-120">既定のパラメーターセット</span><span class="sxs-lookup"><span data-stu-id="72418-120">Default parameter sets</span></span>

<span data-ttu-id="72418-121">複数のパラメーターセットが定義されている場合は、この `DefaultParameterSetName` 属性のキーワードによって既定のパラメーターセットが指定され **CmdletBinding** ます。</span><span class="sxs-lookup"><span data-stu-id="72418-121">When multiple parameter sets are defined, the `DefaultParameterSetName` keyword of the **CmdletBinding** attribute specifies the default parameter set.</span></span>
<span data-ttu-id="72418-122">PowerShell では、コマンドに指定された情報に基づいて、使用するパラメーターセットを特定できないときに、既定のパラメーターセットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="72418-122">PowerShell uses the default parameter set when it can't determine the parameter set to use based on the information provided to the command.</span></span> <span data-ttu-id="72418-123">参照 **バインド** 属性の詳細については、「 [about_functions_cmdletbindingattribute](about_functions_cmdletbindingattribute.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72418-123">For more information about the **CmdletBinding** attribute, see [about_functions_cmdletbindingattribute](about_functions_cmdletbindingattribute.md).</span></span>

## <a name="declaring-parameter-sets"></a><span data-ttu-id="72418-124">パラメーターセットの宣言</span><span class="sxs-lookup"><span data-stu-id="72418-124">Declaring parameter sets</span></span>

<span data-ttu-id="72418-125">パラメーターセットを作成するには、パラメーター `ParameterSetName` セット内のすべてのパラメーターに対して、 **parameter** 属性のキーワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72418-125">To create a parameter set, you must specify the `ParameterSetName` keyword of the **Parameter** attribute for every parameter in the parameter set.</span></span> <span data-ttu-id="72418-126">複数のパラメーターセットに属するパラメーターの場合は、パラメーターセットごとに **パラメーター** 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="72418-126">For parameters that belong to multiple parameter sets, add a **Parameter** attribute for each parameter set.</span></span>

<span data-ttu-id="72418-127">パラメーター **属性を** 使用すると、パラメーターセットごとに異なる方法でパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="72418-127">The **Parameter** attribute enables you to define the parameter differently for each parameter set.</span></span> <span data-ttu-id="72418-128">たとえば、あるセットでは必須として、別のセットでは省略可能なパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="72418-128">For example, you can define a parameter as mandatory in one set and optional in another.</span></span> <span data-ttu-id="72418-129">ただし、各パラメーターセットには、少なくとも1つの一意のパラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="72418-129">However, each parameter set must contain at least one unique parameter.</span></span>

<span data-ttu-id="72418-130">パラメーターセット名が割り当てられていないパラメーターは、すべてのパラメーターセットに属しています。</span><span class="sxs-lookup"><span data-stu-id="72418-130">Parameters that don't have an assigned parameter set name belong to all parameter sets.</span></span>

### <a name="example"></a><span data-ttu-id="72418-131">例</span><span class="sxs-lookup"><span data-stu-id="72418-131">Example</span></span>

<span data-ttu-id="72418-132">次の関数の例では、テキストファイル内の行数、文字、および単語数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="72418-132">The following example function counts the number lines, characters, and words in a text file.</span></span> <span data-ttu-id="72418-133">パラメーターを使用すると、どの値を取得し、どのファイルを測定するかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="72418-133">Using parameters, you can specify which values you want returned and which files you want to measure.</span></span> <span data-ttu-id="72418-134">次の4つのパラメーターセットが定義されています。</span><span class="sxs-lookup"><span data-stu-id="72418-134">There are four parameter sets defined:</span></span>

- <span data-ttu-id="72418-135">Path</span><span class="sxs-lookup"><span data-stu-id="72418-135">Path</span></span>
- <span data-ttu-id="72418-136">PathAll</span><span class="sxs-lookup"><span data-stu-id="72418-136">PathAll</span></span>
- <span data-ttu-id="72418-137">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="72418-137">LiteralPath</span></span>
- <span data-ttu-id="72418-138">LiteralPathAll</span><span class="sxs-lookup"><span data-stu-id="72418-138">LiteralPathAll</span></span>

```powershell
function Measure-Lines {
    [CmdletBinding(DefaultParameterSetName = 'Path')]
    param (
        [Parameter(Mandatory = $true,
            ParameterSetName = 'Path',
            HelpMessage = 'Enter one or more filenames',
            Position = 0)]
        [Parameter(Mandatory = $true,
            ParameterSetName = 'PathAll',
            Position = 0)]
        [string[]]$Path,

        [Parameter(Mandatory = $true, ParameterSetName = 'LiteralPathAll')]
        [Parameter(Mandatory = $true,
            ParameterSetName = 'LiteralPath',
            HelpMessage = 'Enter a single filename',
            ValueFromPipeline = $true)]
        [string]$LiteralPath,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'LiteralPath')]
        [switch]$Lines,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'LiteralPath')]
        [switch]$Words,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'LiteralPath')]
        [switch]$Characters,

        [Parameter(Mandatory = $true, ParameterSetName = 'PathAll')]
        [Parameter(Mandatory = $true, ParameterSetName = 'LiteralPathAll')]
        [switch]$All,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'PathAll')]
        [switch]$Recurse
    )

    begin {
        if ($All) {
            $Lines = $Words = $Characters = $true
        }
        elseif (($Words -eq $false) -and ($Characters -eq $false)) {
            $Lines = $true
        }

        if ($Path) {
            $Files = Get-ChildItem -Path $Path -Recurse:$Recurse
        }
        else {
            $Files = Get-ChildItem -LiteralPath $LiteralPath
        }
    }
    process {
        foreach ($file in $Files) {
            $result = [ordered]@{ }
            $result.Add('File', $file.fullname)

            $content = Get-Content -LiteralPath $file.fullname

            if ($Lines) { $result.Add('Lines', $content.Length) }

            if ($Words) {
                $wc = 0
                foreach ($line in $content) { $wc += $line.split(' ').Length }
                $result.Add('Words', $wc)
            }

            if ($Characters) {
                $cc = 0
                foreach ($line in $content) { $cc += $line.Length }
                $result.Add('Characters', $cc)
            }

            New-Object -TypeName psobject -Property $result
        }
    }
}
```

<span data-ttu-id="72418-139">各パラメーターセットには、一意のパラメーターまたはパラメーターの一意の組み合わせが必要です。</span><span class="sxs-lookup"><span data-stu-id="72418-139">Each parameter set must have a unique parameter or a unique combination of parameters.</span></span> <span data-ttu-id="72418-140">パラメーター `Path` `PathAll` セットとパラメーターセットはよく似ていますが、 **All** パラメーターはパラメーターセットに対して一意です `PathAll` 。</span><span class="sxs-lookup"><span data-stu-id="72418-140">The `Path` and `PathAll` parameter sets are very similar but the **All** parameter is unique to the `PathAll` parameter set.</span></span> <span data-ttu-id="72418-141">とパラメーターセットにも同じことが当てはまり `LiteralPath` `LiteralPathAll` ます。</span><span class="sxs-lookup"><span data-stu-id="72418-141">The same is true with the `LiteralPath` and `LiteralPathAll` parameter sets.</span></span> <span data-ttu-id="72418-142">`PathAll` `LiteralPathAll` パラメーターとパラメーターセットの両方に **All** パラメーターが設定されている場合でも、 **Path** パラメーターと **LiteralPath** パラメーターはそれらを区別します。</span><span class="sxs-lookup"><span data-stu-id="72418-142">Even though the `PathAll` and `LiteralPathAll` parameter sets both have the **All** parameter, the **Path** and **LiteralPath** parameters differentiate them.</span></span>

<span data-ttu-id="72418-143">を使用 `Get-Command -Syntax` すると、各パラメーターセットの構文が表示されます。</span><span class="sxs-lookup"><span data-stu-id="72418-143">Use `Get-Command -Syntax` shows you the syntax of each parameter set.</span></span> <span data-ttu-id="72418-144">ただし、パラメーターセットの名前は表示されません。</span><span class="sxs-lookup"><span data-stu-id="72418-144">However it does not show the name of the parameter set.</span></span> <span data-ttu-id="72418-145">次の例では、各パラメーターセットで使用できるパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="72418-145">The following example shows which parameters can be used in each parameter set.</span></span>

```powershell
(Get-Command Measure-Lines).ParameterSets |
  Select-Object -Property @{n='ParameterSetName';e={$_.name}},
    @{n='Parameters';e={$_.ToString()}}
```

```Output
ParameterSetName Parameters
---------------- ----------
Path             [-Path] <string[]> [-Lines] [-Words] [-Characters] [-Recurse] [<CommonParameters>]
PathAll          [-Path] <string[]> -All [-Recurse] [<CommonParameters>]
LiteralPath      -LiteralPath <string> [-Lines] [-Words] [-Characters] [<CommonParameters>]
LiteralPathAll   -LiteralPath <string> -All [<CommonParameters>]
```

### <a name="parameter-sets-in-action"></a><span data-ttu-id="72418-146">アクションのパラメーターセット</span><span class="sxs-lookup"><span data-stu-id="72418-146">Parameter sets in action</span></span>

<span data-ttu-id="72418-147">この例では、パラメーターセットを使用してい `PathAll` ます。</span><span class="sxs-lookup"><span data-stu-id="72418-147">In this example, we are using the `PathAll` parameter set.</span></span>

```powershell
Measure-Lines test* -All
```

```Output
File                       Lines Words Characters
----                       ----- ----- ----------
C:\temp\test\test.help.txt    31   562       2059
C:\temp\test\test.md          30  1527       3224
C:\temp\test\test.ps1          3     3         79
C:\temp\test\test[1].txt      31   562       2059
```
