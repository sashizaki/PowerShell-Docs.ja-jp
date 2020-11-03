---
description: 項目のコレクション内のすべての項目を走査するために使用できる言語コマンドについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 2/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_foreach?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Foreach
ms.openlocfilehash: b5f09785fbf1fa8c3c14d287efc7cf5fed2d18eb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221627"
---
# <a name="about-foreach"></a><span data-ttu-id="1104b-104">ForEach の概要</span><span class="sxs-lookup"><span data-stu-id="1104b-104">About ForEach</span></span>

## <a name="short-description"></a><span data-ttu-id="1104b-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="1104b-105">Short description</span></span>
<span data-ttu-id="1104b-106">項目のコレクション内のすべての項目を走査するために使用できる言語コマンドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1104b-106">Describes a language command you can use to traverse all the items in a collection of items.</span></span>

## <a name="long-description"></a><span data-ttu-id="1104b-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="1104b-107">Long description</span></span>

<span data-ttu-id="1104b-108">`Foreach`ステートメント (ループとも呼ばれ `Foreach` ます) は、項目のコレクション内の一連の値をステップ実行する (反復処理する) 言語構成要素です。</span><span class="sxs-lookup"><span data-stu-id="1104b-108">The `Foreach` statement (also known as a `Foreach` loop) is a language construct for stepping through (iterating) a series of values in a collection of items.</span></span>

<span data-ttu-id="1104b-109">走査する最も単純で一般的な種類のコレクションは配列です。</span><span class="sxs-lookup"><span data-stu-id="1104b-109">The simplest and most typical type of collection to traverse is an array.</span></span>
<span data-ttu-id="1104b-110">ループ内では `Foreach` 、配列内の各項目に対して1つ以上のコマンドを実行するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="1104b-110">Within a `Foreach` loop, it is common to run one or more commands against each item in an array.</span></span>

## <a name="syntax"></a><span data-ttu-id="1104b-111">構文</span><span class="sxs-lookup"><span data-stu-id="1104b-111">Syntax</span></span>

<span data-ttu-id="1104b-112">構文を次に示し `ForEach` ます。</span><span class="sxs-lookup"><span data-stu-id="1104b-112">The following shows the `ForEach` syntax:</span></span>

```
foreach ($<item> in $<collection>){<statement list>}
```

<span data-ttu-id="1104b-113">かっこで囲まれたステートメントの部分は、 `ForEach` 反復処理する変数とコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="1104b-113">The part of the `ForEach` statement enclosed in parenthesis represents a variable and a collection to iterate.</span></span> <span data-ttu-id="1104b-114">PowerShell `$<item>` は、ループの実行時に自動的に変数を作成し `Foreach` ます。</span><span class="sxs-lookup"><span data-stu-id="1104b-114">PowerShell creates the variable `$<item>` automatically when the `Foreach` loop runs.</span></span> <span data-ttu-id="1104b-115">ループの各反復処理の前に、変数はコレクション内の値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1104b-115">Prior to each iteration through the loop, the variable is set to a value in the collection.</span></span>
<span data-ttu-id="1104b-116">ステートメントに続くブロックには、 `Foreach` `{<statement list>}` コレクション内の各項目に対して実行する一連のコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1104b-116">The block following a `Foreach` statement `{<statement list>}` contains a set of commands to execute against each item in a collection.</span></span>

### <a name="examples"></a><span data-ttu-id="1104b-117">例</span><span class="sxs-lookup"><span data-stu-id="1104b-117">Examples</span></span>

<span data-ttu-id="1104b-118">たとえば、次の例のループでは、 `Foreach` 配列の値が表示され `$letterArray` ます。</span><span class="sxs-lookup"><span data-stu-id="1104b-118">For example, the `Foreach` loop in the following example displays the values in the `$letterArray` array.</span></span>

```powershell
$letterArray = "a","b","c","d"
foreach ($letter in $letterArray)
{
  Write-Host $letter
}
```

<span data-ttu-id="1104b-119">この例では、 `$letterArray` 配列が作成され、文字列値、、、およびで初期化され `"a"` `"b"` `"c"` `"d"` ます。</span><span class="sxs-lookup"><span data-stu-id="1104b-119">In this example, the `$letterArray` array is created and initialized with the string values `"a"`, `"b"`, `"c"`, and `"d"`.</span></span> <span data-ttu-id="1104b-120">ステートメントを初めて実行すると、 `Foreach` 変数は `$letter` () の最初の項目と等しくなるように設定され `$letterArray` `"a"` ます。</span><span class="sxs-lookup"><span data-stu-id="1104b-120">The first time the `Foreach` statement runs, it sets the `$letter` variable equal to the first item in `$letterArray` (`"a"`).</span></span> <span data-ttu-id="1104b-121">次に、コマンドレットを使用して、a という `Write-Host` 文字を表示します。</span><span class="sxs-lookup"><span data-stu-id="1104b-121">Then, it uses the `Write-Host` cmdlet to display the letter a.</span></span> <span data-ttu-id="1104b-122">次にループを実行するときは、を `$letter` に設定 `"b"` します。</span><span class="sxs-lookup"><span data-stu-id="1104b-122">The next time through the loop, `$letter` is set to `"b"`, and so on.</span></span> <span data-ttu-id="1104b-123">ループが `Foreach` 文字 d を表示すると、PowerShell はループを終了します。</span><span class="sxs-lookup"><span data-stu-id="1104b-123">After the `Foreach` loop displays the letter d, PowerShell exits the loop.</span></span>

<span data-ttu-id="1104b-124">`Foreach`PowerShell コマンドプロンプトでコマンドとして実行するには、ステートメント全体が1行に記述されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1104b-124">The entire `Foreach` statement must appear on a single line to run it as a command at the PowerShell command prompt.</span></span> <span data-ttu-id="1104b-125">代わりに、 `Foreach` ps1 スクリプトファイルにコマンドを配置する場合は、ステートメント全体を1行に記述する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1104b-125">The entire `Foreach` statement does not have to appear on a single line if you place the command in a .ps1 script file instead.</span></span>

<span data-ttu-id="1104b-126">`Foreach` ステートメントは、項目のコレクションを返すコマンドレットと共に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1104b-126">`Foreach` statements can also be used together with cmdlets that return a collection of items.</span></span> <span data-ttu-id="1104b-127">次の例では、Foreach ステートメントによって、コマンドレットによって返される項目のリストがステップ実行され `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="1104b-127">In the following example, the Foreach statement steps through the list of items that is returned by the `Get-ChildItem` cmdlet.</span></span>

```powershell
foreach ($file in Get-ChildItem)
{
  Write-Host $file
}
```

<span data-ttu-id="1104b-128">ステートメントを使用して、返される結果を制限することで、この例を絞り込むことができ `If` ます。</span><span class="sxs-lookup"><span data-stu-id="1104b-128">You can refine the example by using an `If` statement to limit the results that are returned.</span></span> <span data-ttu-id="1104b-129">次の例では、 `Foreach` ステートメントは前の例と同じループ操作を実行しますが、 `If` 結果を100キロバイト (kb) を超えるファイルに制限するステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="1104b-129">In the following example, the `Foreach` statement performs the same looping operation as the previous example, but it adds an `If` statement to limit the results to files that are greater than 100 kilobytes (KB):</span></span>

```powershell
foreach ($file in Get-ChildItem)
{
  if ($file.length -gt 100KB)
  {
    Write-Host $file
  }
}
```

<span data-ttu-id="1104b-130">この例では、 `Foreach` ループは変数のプロパティを使用して `$file` 比較演算 () を実行し `$file.length -gt 100KB` ます。</span><span class="sxs-lookup"><span data-stu-id="1104b-130">In this example, the `Foreach` loop uses a property of the `$file` variable to perform a comparison operation (`$file.length -gt 100KB`).</span></span> <span data-ttu-id="1104b-131">変数には、 `$file` コマンドレットによって返されるオブジェクトのすべてのプロパティが含まれてい `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="1104b-131">The `$file` variable contains all the properties in the object that is returned by the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="1104b-132">そのため、ファイル名だけを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="1104b-132">Therefore, you can return more than just a file name.</span></span>
<span data-ttu-id="1104b-133">次の例では、PowerShell は、ステートメントリスト内の長さと最後のアクセス時刻を返します。</span><span class="sxs-lookup"><span data-stu-id="1104b-133">In the next example, PowerShell returns the length and the last access time inside the statement list:</span></span>

```powershell
foreach ($file in Get-ChildItem)
{
  if ($file.length -gt 100KB)
  {
    Write-Host $file
    Write-Host $file.length
    Write-Host $file.lastaccesstime
  }
}
```

<span data-ttu-id="1104b-134">この例では、ステートメントリストで1つのコマンドを実行するだけではありません。</span><span class="sxs-lookup"><span data-stu-id="1104b-134">In this example, you are not limited to running a single command in a statement list.</span></span>

<span data-ttu-id="1104b-135">また、ループの外側で変数を使用 `Foreach` し、ループ内で変数をインクリメントすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1104b-135">You can also use a variable outside a `Foreach` loop and increment the variable inside the loop.</span></span> <span data-ttu-id="1104b-136">次の例では、ファイルのサイズが 100 KB を超えてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="1104b-136">The following example counts files over 100 KB in size:</span></span>

```powershell
$i = 0
foreach ($file in Get-ChildItem) {
  if ($file.length -gt 100KB) {
    Write-Host $file "file size:" ($file.length / 1024).ToString("F0") KB
    $i = $i + 1
  }
}

if ($i -ne 0) {
  Write-Host
  Write-Host $i " file(s) over 100 KB in the current directory."
}
else {
  Write-Host "No files greater than 100 KB in the current directory."
}
```

<span data-ttu-id="1104b-137">前の例では、 `$i` 変数がループの外部に設定され、 `0` 100 KB を超えるファイルが検出されるたびに、変数がループ内でインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="1104b-137">In the preceding example, the `$i` variable is set to `0` outside the loop, and the variable is incremented inside the loop for each file that is found that is larger than 100 KB.</span></span> <span data-ttu-id="1104b-138">ループが終了すると、 `If` ステートメントによっての値が評価され、 `$i` すべてのファイルの数が 100 KB を超えて表示されます。</span><span class="sxs-lookup"><span data-stu-id="1104b-138">When the loop exits, an `If` statement evaluates the value of `$i` to display a count of all the files over 100 KB.</span></span> <span data-ttu-id="1104b-139">または、100 KB を超えるファイルが見つからなかったことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1104b-139">Or, it displays a message stating that no files over 100 KB were found.</span></span>

<span data-ttu-id="1104b-140">前の例では、ファイルの長さの結果を書式設定する方法も示しています。</span><span class="sxs-lookup"><span data-stu-id="1104b-140">The previous example also demonstrates how to format the file length results:</span></span>

```powershell
($file.length / 1024).ToString("F0")
```

<span data-ttu-id="1104b-141">値は、バイトではなく、結果を kb 単位で示すために1024で除算され、結果の値は、結果から10進値を削除するために固定小数点書式指定子を使用して書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="1104b-141">The value is divided by 1,024 to show the results in kilobytes rather than bytes, and the resulting value is then formatted using the fixed-point format specifier to remove any decimal values from the result.</span></span> <span data-ttu-id="1104b-142">0は、書式指定子が小数点以下を表示しないようにします。</span><span class="sxs-lookup"><span data-stu-id="1104b-142">The 0 makes the format specifier show no decimal places.</span></span>

<span data-ttu-id="1104b-143">次の例では、定義された関数は、PowerShell スクリプトとスクリプトモジュールを解析し、内に含まれる関数の場所を返します。</span><span class="sxs-lookup"><span data-stu-id="1104b-143">In the following example, the function defined parses PowerShell scripts and script modules and returns the location of functions contained within.</span></span> <span data-ttu-id="1104b-144">この例では、 `MoveNext` メソッド (ループの場合と同様に動作する `skip X` `For` ) と、 `Current` `$foreach` foreach スクリプトブロック内の変数のプロパティを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1104b-144">The example demonstrates how to use the `MoveNext` method (which works similarly to `skip X` on a `For` loop) and the `Current` property of the `$foreach` variable inside of a foreach script block.</span></span> <span data-ttu-id="1104b-145">この例の関数では、複数の行にまたがる関数定義が異常であるか、または一貫性がない場合でも、スクリプト内の関数を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="1104b-145">The example function can find functions in a script even if there are unusually- or inconsistently-spaced function definitions that span multiple lines.</span></span>

<span data-ttu-id="1104b-146">詳細については、「 [列挙子の使用](about_Automatic_Variables.md#using-enumerators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1104b-146">For more information, see [Using Enumerators](about_Automatic_Variables.md#using-enumerators).</span></span>

```powershell
function Get-FunctionPosition {
  [CmdletBinding()]
  [OutputType('FunctionPosition')]
  param(
    [Parameter(Position = 0, Mandatory,
      ValueFromPipeline, ValueFromPipelineByPropertyName)]
    [ValidateNotNullOrEmpty()]
    [Alias('PSPath')]
    [System.String[]]
    $Path
  )

  process {
    try {
      $filesToProcess = if ($_ -is [System.IO.FileSystemInfo]) {
        $_
      } else {
        $filesToProcess = Get-Item -Path $Path
      }
      $parser = [System.Management.Automation.Language.Parser]
      foreach ($item in $filesToProcess) {
        if ($item.PSIsContainer -or
            $item.Extension -notin @('.ps1', '.psm1')) {
          continue
        }
        $tokens = $errors = $null
        $ast = $parser::ParseFile($item.FullName, ([REF]$tokens),
          ([REF]$errors))
        if ($errors) {
          $msg = "File '{0}' has {1} parser errors." -f $item.FullName,
            $errors.Count
          Write-Warning $msg
        }
        :tokenLoop foreach ($token in $tokens) {
          if ($token.Kind -ne 'Function') {
            continue
          }
          $position = $token.Extent.StartLineNumber
          do {
            if (-not $foreach.MoveNext()) {
              break tokenLoop
            }
            $token = $foreach.Current
          } until ($token.Kind -in @('Generic', 'Identifier'))
          $functionPosition = [pscustomobject]@{
            Name       = $token.Text
            LineNumber = $position
            Path       = $item.FullName
          }
          Add-Member -InputObject $functionPosition `
            -TypeName FunctionPosition -PassThru
        }
      }
    }
    catch {
      throw
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="1104b-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="1104b-147">SEE ALSO</span></span>

[<span data-ttu-id="1104b-148">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="1104b-148">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="1104b-149">about_If</span><span class="sxs-lookup"><span data-stu-id="1104b-149">about_If</span></span>](about_If.md)

[<span data-ttu-id="1104b-150">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="1104b-150">ForEach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
