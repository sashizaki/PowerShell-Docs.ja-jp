---
description: PowerShell の and 演算子を使用したパイプラインのチェーンについて説明し `&&` `||` ます。
ms.date: 09/30/2019
schema: 2.0.0
Locale: en-US
keywords: powershell,コマンドレット
title: about_Pipeline_Chain_Operators
ms.openlocfilehash: 107d5eacb7b9629a42d5eef53e0c7c66a522f32e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223096"
---
# <a name="about-pipeline-chain-operators"></a><span data-ttu-id="419da-104">パイプラインチェーン演算子について</span><span class="sxs-lookup"><span data-stu-id="419da-104">About Pipeline Chain Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="419da-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="419da-105">Short description</span></span>

<span data-ttu-id="419da-106">PowerShell の and 演算子を使用したパイプラインのチェーンについて説明し `&&` `||` ます。</span><span class="sxs-lookup"><span data-stu-id="419da-106">Describes chaining pipelines with the `&&` and `||` operators in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="419da-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="419da-107">Long description</span></span>

<span data-ttu-id="419da-108">Powershell 7 以降では、PowerShell は `&&` and 演算子を実装して、 `||` 条件に応じてパイプラインをチェーンします。</span><span class="sxs-lookup"><span data-stu-id="419da-108">Beginning in PowerShell 7, PowerShell implements the `&&` and `||` operators to conditionally chain pipelines.</span></span> <span data-ttu-id="419da-109">これらの演算子は、PowerShell で *パイプラインチェーン演算子* として知られています。また、bash、zsh および sh のような POSIX シェルの [and または list](https://pubs.opengroup.org/onlinepubs/009695399/utilities/xcu_chap02.html#tag_02_09_03) と同様に、Windows コマンドシェル (cmd.exe) の [条件付き処理シンボル](/previous-versions/windows/it-pro/windows-xp/bb490954(v=technet.10)#using-multiple-commands-and-conditional-processing-symbols) にも似ています。</span><span class="sxs-lookup"><span data-stu-id="419da-109">These operators are known in PowerShell as *pipeline chain operators* , and are similar to [AND-OR lists](https://pubs.opengroup.org/onlinepubs/009695399/utilities/xcu_chap02.html#tag_02_09_03) in POSIX shells like bash, zsh and sh, as well as [conditional processing symbols](/previous-versions/windows/it-pro/windows-xp/bb490954(v=technet.10)#using-multiple-commands-and-conditional-processing-symbols) in the Windows Command Shell (cmd.exe).</span></span>

<span data-ttu-id="419da-110">`&&` 演算子では、左側のパイプラインが成功した場合に、右側のパイプラインが実行されます。</span><span class="sxs-lookup"><span data-stu-id="419da-110">The `&&` operator executes the right-hand pipeline, if the left-hand pipeline succeeded.</span></span> <span data-ttu-id="419da-111">反対に、`||` 演算子では、左側のパイプラインが失敗した場合に、右側のパイプラインが実行されます。</span><span class="sxs-lookup"><span data-stu-id="419da-111">Conversely, the `||` operator executes the right-hand pipeline if the left-hand pipeline failed.</span></span>

<span data-ttu-id="419da-112">これらの演算子では `$?` 変数と `$LASTEXITCODE` の変数を使用して、パイプラインが失敗したかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="419da-112">These operators use the `$?` and `$LASTEXITCODE` variables to determine if a pipeline failed.</span></span> <span data-ttu-id="419da-113">これにより、コマンドレットや関数だけでなく、ネイティブ コマンドでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="419da-113">This allows you to use them with native commands and not just with cmdlets or functions.</span></span> <span data-ttu-id="419da-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="419da-114">For example:</span></span>

```powershell
# Create an SSH key pair - if successful copy the public key to clipboard
ssh-keygen -t rsa -b 2048 && Get-Content -Raw ~\.ssh\id_rsa.pub | clip
```

### <a name="examples"></a><span data-ttu-id="419da-115">例</span><span class="sxs-lookup"><span data-stu-id="419da-115">Examples</span></span>

#### <a name="two-successful-commands"></a><span data-ttu-id="419da-116">成功した2つのコマンド</span><span class="sxs-lookup"><span data-stu-id="419da-116">Two successful commands</span></span>

```powershell
Write-Output 'First' && Write-Output 'Second'
```

```Output
First
Second
```

#### <a name="first-command-fails-causing-second-not-to-be-executed"></a><span data-ttu-id="419da-117">最初のコマンドが失敗し、2番目のコマンドが実行されない</span><span class="sxs-lookup"><span data-stu-id="419da-117">First command fails, causing second not to be executed</span></span>

```powershell
Write-Error 'Bad' && Write-Output 'Second'
```

```Output
Write-Error: Bad
```

#### <a name="first-command-succeeds-so-the-second-command-is-not-executed"></a><span data-ttu-id="419da-118">最初のコマンドは成功します。そのため、2番目のコマンドは実行されません。</span><span class="sxs-lookup"><span data-stu-id="419da-118">First command succeeds, so the second command is not executed</span></span>

```powershell
Write-Output 'First' || Write-Output 'Second'
```

```Output
First
```

#### <a name="first-command-fails-so-the-second-command-is-executed"></a><span data-ttu-id="419da-119">最初のコマンドは失敗し、2番目のコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="419da-119">First command fails, so the second command is executed</span></span>

```powershell
Write-Error 'Bad' || Write-Output 'Second'
```

```Output
Write-Error: Bad
Second
```

<span data-ttu-id="419da-120">パイプラインの成功は、変数の値によって定義され `$?` ます。 PowerShell は、実行状態に基づいてパイプラインを実行した後に自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="419da-120">Pipeline success is defined by the value of the `$?` variable, which PowerShell automatically sets after executing a pipeline based on its execution status.</span></span>
<span data-ttu-id="419da-121">つまり、パイプラインチェーン演算子の等価性は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="419da-121">This means that pipeline chain operators have the following equivalence:</span></span>

```powershell
Test-Command '1' && Test-Command '2'
```

<span data-ttu-id="419da-122">と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="419da-122">works the same as</span></span>

```powershell
Test-Command '1'; if ($?) { Test-Command '2' }
```

<span data-ttu-id="419da-123">and</span><span class="sxs-lookup"><span data-stu-id="419da-123">and</span></span>

```powershell
Test-Command '1' || Test-Command '2'
```

<span data-ttu-id="419da-124">と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="419da-124">works the same as</span></span>

```powershell
Test-Command '1'; if (-not $?) { Test-Command '2' }
```

### <a name="assignment-from-pipeline-chains"></a><span data-ttu-id="419da-125">パイプラインチェーンからの割り当て</span><span class="sxs-lookup"><span data-stu-id="419da-125">Assignment from pipeline chains</span></span>

<span data-ttu-id="419da-126">パイプラインチェーンから変数を割り当てると、チェーン内のすべてのパイプラインが連結されます。</span><span class="sxs-lookup"><span data-stu-id="419da-126">Assigning a variable from a pipeline chain takes the concatenation of all the pipelines in the chain:</span></span>

```powershell
$result = Write-Output '1' && Write-Output '2'
$result
```

```Output
1
2
```

<span data-ttu-id="419da-127">パイプラインチェーンからの割り当て中にスクリプト終了エラーが発生した場合、割り当ては成功しません。</span><span class="sxs-lookup"><span data-stu-id="419da-127">If a script-terminating error occurs during assignment from a pipeline chain, the assignment does not succeed:</span></span>

```powershell
try
{
    $result = Write-Output 'Value' && $(throw 'Bad')
}
catch
{
    # Do nothing, just squash the error
}

"Result: $result"
```

```Output
Result:
```

### <a name="operator-syntax-and-precedence"></a><span data-ttu-id="419da-128">演算子の構文と優先順位</span><span class="sxs-lookup"><span data-stu-id="419da-128">Operator syntax and precedence</span></span>

<span data-ttu-id="419da-129">他の演算子とは異なり、 `&&` `||` はやなどの式ではなく、パイプラインを操作し `+` `-and` ます。</span><span class="sxs-lookup"><span data-stu-id="419da-129">Unlike other operators, `&&` and `||` operate on pipelines, rather than on expressions like `+` or `-and`, for example.</span></span>

<span data-ttu-id="419da-130">`&&` とは `||` 、パイプ () またはリダイレクト () よりも優先順位が低くなり `|` `>` ますが、ジョブ演算子 ( `&` )、割り当て ( `=` )、またはセミコロン () より優先順位が高くなり `;` ます。</span><span class="sxs-lookup"><span data-stu-id="419da-130">`&&` and `||` have a lower precedence than piping (`|`) or redirection (`>`), but a higher precedence than job operators (`&`), assignment (`=`) or semicolons (`;`).</span></span> <span data-ttu-id="419da-131">つまり、パイプラインチェーン内のパイプラインは個別にリダイレクトできます。また、パイプラインチェーン全体を backgrounded、変数に代入、またはステートメントとして分離することができます。</span><span class="sxs-lookup"><span data-stu-id="419da-131">This means that pipelines within a pipeline chain can be individually redirected, and that entire pipeline chains can be backgrounded, assigned to variables, or separated as statements.</span></span>

<span data-ttu-id="419da-132">パイプラインチェーン内で優先順位の低い構文を使用するには、かっこを使用することを検討してください `(...)` 。</span><span class="sxs-lookup"><span data-stu-id="419da-132">To use lower precedence syntax within a pipeline chain, consider the use of parentheses `(...)`.</span></span>
<span data-ttu-id="419da-133">同様に、パイプラインチェーン内にステートメントを埋め込むには、部分式を `$(...)` 使用できます。</span><span class="sxs-lookup"><span data-stu-id="419da-133">Similarly, to embed a statement within a pipeline chain, a subexpression `$(...)` can be used.</span></span>
<span data-ttu-id="419da-134">これは、ネイティブコマンドと制御フローを組み合わせる場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="419da-134">This can be useful for combining native commands with control flow:</span></span>

```powershell
foreach ($file in 'file1','file2','file3')
{
    # When find succeeds, the loop breaks
    find $file && Write-Output "Found $file" && $(break)
}
```

```Output
find: file1: No such file or directory
file2
Found file2
```

<span data-ttu-id="419da-135">PowerShell 7 の時点では、これらの構文の動作は変更されており、 `$?` かっこまたは部分式の中でコマンドが成功または失敗したときにが想定どおりに設定されるようになっています。</span><span class="sxs-lookup"><span data-stu-id="419da-135">As of PowerShell 7, the behaviour of these syntaxes has been changed so that `$?` is set as expected when a command succeeds or fails within parentheses or a subexpression.</span></span>

<span data-ttu-id="419da-136">PowerShell の他のほとんどの演算子と同じように、 `&&` と `||` は *左から結合* されています。つまり、左からグループ化します。</span><span class="sxs-lookup"><span data-stu-id="419da-136">Like most other operators in PowerShell, `&&` and `||` are also *left-associative* , meaning they group from the left.</span></span> <span data-ttu-id="419da-137">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="419da-137">For example:</span></span>

```powershell
Get-ChildItem -Path ./file.txt || Write-Error "file.txt does not exist" && Get-Content -Raw ./file.txt
```

<span data-ttu-id="419da-138">次のようにグループ化:</span><span class="sxs-lookup"><span data-stu-id="419da-138">will group as:</span></span>

```
[Get-ChildItem -Path ./file.txt || Write-Error "file.txt does not exist"] && Get-Content -Raw ./file.txt
```

<span data-ttu-id="419da-139">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="419da-139">being equivalent to:</span></span>

```powershell
Get-ChildItem -Path ./file.txt

if (-not $?) { Write-Error "file.txt does not exist" }

if ($?) { Get-Content -Raw ./file.txt }
```

### <a name="error-interaction"></a><span data-ttu-id="419da-140">エラーの操作</span><span class="sxs-lookup"><span data-stu-id="419da-140">Error interaction</span></span>

<span data-ttu-id="419da-141">パイプラインチェーン演算子は、エラーを吸収しません。</span><span class="sxs-lookup"><span data-stu-id="419da-141">Pipeline chain operators do not absorb errors.</span></span> <span data-ttu-id="419da-142">パイプラインチェーン内のステートメントがスクリプト終了エラーをスローすると、パイプラインチェーンは終了します。</span><span class="sxs-lookup"><span data-stu-id="419da-142">When a statement in a pipeline chain throws a script-terminating error, the pipeline chain is terminated.</span></span>

<span data-ttu-id="419da-143">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="419da-143">For example:</span></span>

```powershell
$(throw 'Bad') || Write-Output '2'
```

```Output
Exception: Bad
```

<span data-ttu-id="419da-144">エラーがキャッチされても、パイプラインチェーンはまだ終了しています。</span><span class="sxs-lookup"><span data-stu-id="419da-144">Even when the error is caught, the pipeline chain is still terminated:</span></span>

```powershell
try
{
    $(throw 'Bad') || Write-Output '2'
}
catch
{
    Write-Output "Caught: $_"
}
Write-Output 'Done'
```

```Output
Caught: Bad
Done
```

<span data-ttu-id="419da-145">エラーが終了しない場合、またはパイプラインを終了した場合は、次の値を考慮してパイプラインチェーンが続行され `$?` ます。</span><span class="sxs-lookup"><span data-stu-id="419da-145">If an error is non-terminating, or only terminates a pipeline, the pipeline chain continues, respecting the value of `$?`:</span></span>

```powershell
function Test-NonTerminatingError
{
    [CmdletBinding()]
    param()

    $exception = [System.Exception]::new('BAD')
    $errorId = 'BAD'
    $errorCategory = 'NotSpecified'

    $errorRecord = [System.Management.Automation.ErrorRecord]::new($exception, $errorId, $errorCategory, $null)

    $PSCmdlet.WriteError($errorRecord)
}

Test-NonTerminatingError || Write-Output 'Second'
```

```Output
Test-NonTerminatingError: BAD
Second
```

### <a name="chaining-pipelines-rather-than-commands"></a><span data-ttu-id="419da-146">コマンドではなくパイプラインのチェーン</span><span class="sxs-lookup"><span data-stu-id="419da-146">Chaining pipelines rather than commands</span></span>

<span data-ttu-id="419da-147">パイプラインチェーン演算子は、その名前を使用して、コマンドだけではなく、パイプラインをチェーンすることができます。</span><span class="sxs-lookup"><span data-stu-id="419da-147">Pipeline chain operators, by their name, can be used to chain pipelines, rather than just commands.</span></span> <span data-ttu-id="419da-148">これは他のシェルの動作と一致しますが、次のようにして *成功* を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="419da-148">This matches the behavior of other shells, but can make *success* harder to determine:</span></span>

```powershell
function Test-NotTwo
{
    [CmdletBinding()]
    param(
      [Parameter(ValueFromPipeline)]
      $Input
    )

    process
    {
        if ($Input -ne 2)
        {
            return $Input
        }

        $exception = [System.Exception]::new('Input is 2')
        $errorId = 'InputTwo'
        $errorCategory = 'InvalidData'

        $errorRecord = [System.Management.Automation.ErrorRecord]::new($exception, $errorId, $errorCategory, $null)

        $PSCmdlet.WriteError($errorRecord)
    }
}

1,2,3 | Test-NotTwo && Write-Output 'All done!'
```

```Output
1
Test-NotTwo : Input is 2
3
```

<span data-ttu-id="419da-149">は `Write-Output 'All done!'` 実行されません `Test-NotTwo` 。これは、が終了しないエラーを生成した後に失敗したと見なされるためです。</span><span class="sxs-lookup"><span data-stu-id="419da-149">Note that `Write-Output 'All done!'` is not executed, since `Test-NotTwo` is deemed to have failed after generating the non-terminating error.</span></span>

## <a name="see-also"></a><span data-ttu-id="419da-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="419da-150">See also</span></span>

- [<span data-ttu-id="419da-151">about_Operators</span><span class="sxs-lookup"><span data-stu-id="419da-151">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="419da-152">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="419da-152">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)
- [<span data-ttu-id="419da-153">about_pipelines</span><span class="sxs-lookup"><span data-stu-id="419da-153">about_pipelines</span></span>](about_pipelines.md)
