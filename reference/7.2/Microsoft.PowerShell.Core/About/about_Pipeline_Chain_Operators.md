---
description: PowerShell の and 演算子を使用したパイプラインのチェーンについて説明し `&&` `||` ます。
Locale: en-US
ms.date: 09/30/2019
schema: 2.0.0
title: about_Pipeline_Chain_Operators
ms.openlocfilehash: ece84ec061126401e53bf58112cd79a07a816e8d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601231"
---
# <a name="about-pipeline-chain-operators"></a><span data-ttu-id="5a088-103">パイプラインチェーン演算子について</span><span class="sxs-lookup"><span data-stu-id="5a088-103">About Pipeline Chain Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="5a088-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="5a088-104">Short description</span></span>

<span data-ttu-id="5a088-105">PowerShell の and 演算子を使用したパイプラインのチェーンについて説明し `&&` `||` ます。</span><span class="sxs-lookup"><span data-stu-id="5a088-105">Describes chaining pipelines with the `&&` and `||` operators in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="5a088-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="5a088-106">Long description</span></span>

<span data-ttu-id="5a088-107">Powershell 7 以降では、PowerShell は `&&` and 演算子を実装して、 `||` 条件に応じてパイプラインをチェーンします。</span><span class="sxs-lookup"><span data-stu-id="5a088-107">Beginning in PowerShell 7, PowerShell implements the `&&` and `||` operators to conditionally chain pipelines.</span></span> <span data-ttu-id="5a088-108">これらの演算子は、PowerShell で *パイプラインチェーン演算子* として知られています。また、bash、zsh および sh のような POSIX シェルの [and または list](https://pubs.opengroup.org/onlinepubs/009695399/utilities/xcu_chap02.html#tag_02_09_03) と同様に、Windows コマンドシェル (cmd.exe) の [条件付き処理シンボル](/previous-versions/windows/it-pro/windows-xp/bb490954(v=technet.10)#using-multiple-commands-and-conditional-processing-symbols) にも似ています。</span><span class="sxs-lookup"><span data-stu-id="5a088-108">These operators are known in PowerShell as *pipeline chain operators*, and are similar to [AND-OR lists](https://pubs.opengroup.org/onlinepubs/009695399/utilities/xcu_chap02.html#tag_02_09_03) in POSIX shells like bash, zsh and sh, as well as [conditional processing symbols](/previous-versions/windows/it-pro/windows-xp/bb490954(v=technet.10)#using-multiple-commands-and-conditional-processing-symbols) in the Windows Command Shell (cmd.exe).</span></span>

<span data-ttu-id="5a088-109">`&&` 演算子では、左側のパイプラインが成功した場合に、右側のパイプラインが実行されます。</span><span class="sxs-lookup"><span data-stu-id="5a088-109">The `&&` operator executes the right-hand pipeline, if the left-hand pipeline succeeded.</span></span> <span data-ttu-id="5a088-110">反対に、`||` 演算子では、左側のパイプラインが失敗した場合に、右側のパイプラインが実行されます。</span><span class="sxs-lookup"><span data-stu-id="5a088-110">Conversely, the `||` operator executes the right-hand pipeline if the left-hand pipeline failed.</span></span>

<span data-ttu-id="5a088-111">これらの演算子では `$?` 変数と `$LASTEXITCODE` の変数を使用して、パイプラインが失敗したかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="5a088-111">These operators use the `$?` and `$LASTEXITCODE` variables to determine if a pipeline failed.</span></span> <span data-ttu-id="5a088-112">これにより、コマンドレットや関数だけでなく、ネイティブ コマンドでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a088-112">This allows you to use them with native commands and not just with cmdlets or functions.</span></span> <span data-ttu-id="5a088-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a088-113">For example:</span></span>

```powershell
# Create an SSH key pair - if successful copy the public key to clipboard
ssh-keygen -t rsa -b 2048 && Get-Content -Raw ~\.ssh\id_rsa.pub | clip
```

### <a name="examples"></a><span data-ttu-id="5a088-114">例</span><span class="sxs-lookup"><span data-stu-id="5a088-114">Examples</span></span>

#### <a name="two-successful-commands"></a><span data-ttu-id="5a088-115">成功した2つのコマンド</span><span class="sxs-lookup"><span data-stu-id="5a088-115">Two successful commands</span></span>

```powershell
Write-Output 'First' && Write-Output 'Second'
```

```Output
First
Second
```

#### <a name="first-command-fails-causing-second-not-to-be-executed"></a><span data-ttu-id="5a088-116">最初のコマンドが失敗し、2番目のコマンドが実行されない</span><span class="sxs-lookup"><span data-stu-id="5a088-116">First command fails, causing second not to be executed</span></span>

```powershell
Write-Error 'Bad' && Write-Output 'Second'
```

```Output
Write-Error: Bad
```

#### <a name="first-command-succeeds-so-the-second-command-is-not-executed"></a><span data-ttu-id="5a088-117">最初のコマンドは成功します。そのため、2番目のコマンドは実行されません。</span><span class="sxs-lookup"><span data-stu-id="5a088-117">First command succeeds, so the second command is not executed</span></span>

```powershell
Write-Output 'First' || Write-Output 'Second'
```

```Output
First
```

#### <a name="first-command-fails-so-the-second-command-is-executed"></a><span data-ttu-id="5a088-118">最初のコマンドは失敗し、2番目のコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="5a088-118">First command fails, so the second command is executed</span></span>

```powershell
Write-Error 'Bad' || Write-Output 'Second'
```

```Output
Write-Error: Bad
Second
```

<span data-ttu-id="5a088-119">パイプラインの成功は、変数の値によって定義され `$?` ます。 PowerShell は、実行状態に基づいてパイプラインを実行した後に自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5a088-119">Pipeline success is defined by the value of the `$?` variable, which PowerShell automatically sets after executing a pipeline based on its execution status.</span></span>
<span data-ttu-id="5a088-120">つまり、パイプラインチェーン演算子の等価性は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5a088-120">This means that pipeline chain operators have the following equivalence:</span></span>

```powershell
Test-Command '1' && Test-Command '2'
```

<span data-ttu-id="5a088-121">と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="5a088-121">works the same as</span></span>

```powershell
Test-Command '1'; if ($?) { Test-Command '2' }
```

<span data-ttu-id="5a088-122">および</span><span class="sxs-lookup"><span data-stu-id="5a088-122">and</span></span>

```powershell
Test-Command '1' || Test-Command '2'
```

<span data-ttu-id="5a088-123">と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="5a088-123">works the same as</span></span>

```powershell
Test-Command '1'; if (-not $?) { Test-Command '2' }
```

### <a name="assignment-from-pipeline-chains"></a><span data-ttu-id="5a088-124">パイプラインチェーンからの割り当て</span><span class="sxs-lookup"><span data-stu-id="5a088-124">Assignment from pipeline chains</span></span>

<span data-ttu-id="5a088-125">パイプラインチェーンから変数を割り当てると、チェーン内のすべてのパイプラインが連結されます。</span><span class="sxs-lookup"><span data-stu-id="5a088-125">Assigning a variable from a pipeline chain takes the concatenation of all the pipelines in the chain:</span></span>

```powershell
$result = Write-Output '1' && Write-Output '2'
$result
```

```Output
1
2
```

<span data-ttu-id="5a088-126">パイプラインチェーンからの割り当て中にスクリプト終了エラーが発生した場合、割り当ては成功しません。</span><span class="sxs-lookup"><span data-stu-id="5a088-126">If a script-terminating error occurs during assignment from a pipeline chain, the assignment does not succeed:</span></span>

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

### <a name="operator-syntax-and-precedence"></a><span data-ttu-id="5a088-127">演算子の構文と優先順位</span><span class="sxs-lookup"><span data-stu-id="5a088-127">Operator syntax and precedence</span></span>

<span data-ttu-id="5a088-128">他の演算子とは異なり、 `&&` `||` はやなどの式ではなく、パイプラインを操作し `+` `-and` ます。</span><span class="sxs-lookup"><span data-stu-id="5a088-128">Unlike other operators, `&&` and `||` operate on pipelines, rather than on expressions like `+` or `-and`, for example.</span></span>

<span data-ttu-id="5a088-129">`&&` とは `||` 、パイプ () またはリダイレクト () よりも優先順位が低くなり `|` `>` ますが、ジョブ演算子 ( `&` )、割り当て ( `=` )、またはセミコロン () より優先順位が高くなり `;` ます。</span><span class="sxs-lookup"><span data-stu-id="5a088-129">`&&` and `||` have a lower precedence than piping (`|`) or redirection (`>`), but a higher precedence than job operators (`&`), assignment (`=`) or semicolons (`;`).</span></span> <span data-ttu-id="5a088-130">つまり、パイプラインチェーン内のパイプラインは個別にリダイレクトできます。また、パイプラインチェーン全体を backgrounded、変数に代入、またはステートメントとして分離することができます。</span><span class="sxs-lookup"><span data-stu-id="5a088-130">This means that pipelines within a pipeline chain can be individually redirected, and that entire pipeline chains can be backgrounded, assigned to variables, or separated as statements.</span></span>

<span data-ttu-id="5a088-131">パイプラインチェーン内で優先順位の低い構文を使用するには、かっこを使用することを検討してください `(...)` 。</span><span class="sxs-lookup"><span data-stu-id="5a088-131">To use lower precedence syntax within a pipeline chain, consider the use of parentheses `(...)`.</span></span>
<span data-ttu-id="5a088-132">同様に、パイプラインチェーン内にステートメントを埋め込むには、部分式を `$(...)` 使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a088-132">Similarly, to embed a statement within a pipeline chain, a subexpression `$(...)` can be used.</span></span>
<span data-ttu-id="5a088-133">これは、ネイティブコマンドと制御フローを組み合わせる場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="5a088-133">This can be useful for combining native commands with control flow:</span></span>

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

<span data-ttu-id="5a088-134">PowerShell 7 の時点では、これらの構文の動作は変更されており、 `$?` かっこまたは部分式の中でコマンドが成功または失敗したときにが想定どおりに設定されるようになっています。</span><span class="sxs-lookup"><span data-stu-id="5a088-134">As of PowerShell 7, the behaviour of these syntaxes has been changed so that `$?` is set as expected when a command succeeds or fails within parentheses or a subexpression.</span></span>

<span data-ttu-id="5a088-135">PowerShell の他のほとんどの演算子と同じように、 `&&` と `||` は *左から結合* されています。つまり、左からグループ化します。</span><span class="sxs-lookup"><span data-stu-id="5a088-135">Like most other operators in PowerShell, `&&` and `||` are also *left-associative*, meaning they group from the left.</span></span> <span data-ttu-id="5a088-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a088-136">For example:</span></span>

```powershell
Get-ChildItem -Path ./file.txt || Write-Error "file.txt does not exist" && Get-Content -Raw ./file.txt
```

<span data-ttu-id="5a088-137">次のようにグループ化:</span><span class="sxs-lookup"><span data-stu-id="5a088-137">will group as:</span></span>

```
[Get-ChildItem -Path ./file.txt || Write-Error "file.txt does not exist"] && Get-Content -Raw ./file.txt
```

<span data-ttu-id="5a088-138">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="5a088-138">being equivalent to:</span></span>

```powershell
Get-ChildItem -Path ./file.txt

if (-not $?) { Write-Error "file.txt does not exist" }

if ($?) { Get-Content -Raw ./file.txt }
```

### <a name="error-interaction"></a><span data-ttu-id="5a088-139">エラーの操作</span><span class="sxs-lookup"><span data-stu-id="5a088-139">Error interaction</span></span>

<span data-ttu-id="5a088-140">パイプラインチェーン演算子は、エラーを吸収しません。</span><span class="sxs-lookup"><span data-stu-id="5a088-140">Pipeline chain operators do not absorb errors.</span></span> <span data-ttu-id="5a088-141">パイプラインチェーン内のステートメントがスクリプト終了エラーをスローすると、パイプラインチェーンは終了します。</span><span class="sxs-lookup"><span data-stu-id="5a088-141">When a statement in a pipeline chain throws a script-terminating error, the pipeline chain is terminated.</span></span>

<span data-ttu-id="5a088-142">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a088-142">For example:</span></span>

```powershell
$(throw 'Bad') || Write-Output '2'
```

```Output
Exception: Bad
```

<span data-ttu-id="5a088-143">エラーがキャッチされても、パイプラインチェーンはまだ終了しています。</span><span class="sxs-lookup"><span data-stu-id="5a088-143">Even when the error is caught, the pipeline chain is still terminated:</span></span>

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

<span data-ttu-id="5a088-144">エラーが終了しない場合、またはパイプラインを終了した場合は、次の値を考慮してパイプラインチェーンが続行され `$?` ます。</span><span class="sxs-lookup"><span data-stu-id="5a088-144">If an error is non-terminating, or only terminates a pipeline, the pipeline chain continues, respecting the value of `$?`:</span></span>

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

### <a name="chaining-pipelines-rather-than-commands"></a><span data-ttu-id="5a088-145">コマンドではなくパイプラインのチェーン</span><span class="sxs-lookup"><span data-stu-id="5a088-145">Chaining pipelines rather than commands</span></span>

<span data-ttu-id="5a088-146">パイプラインチェーン演算子は、その名前を使用して、コマンドだけではなく、パイプラインをチェーンすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a088-146">Pipeline chain operators, by their name, can be used to chain pipelines, rather than just commands.</span></span> <span data-ttu-id="5a088-147">これは他のシェルの動作と一致しますが、次のようにして *成功* を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="5a088-147">This matches the behavior of other shells, but can make *success* harder to determine:</span></span>

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

<span data-ttu-id="5a088-148">は `Write-Output 'All done!'` 実行されません `Test-NotTwo` 。これは、が終了しないエラーを生成した後に失敗したと見なされるためです。</span><span class="sxs-lookup"><span data-stu-id="5a088-148">Note that `Write-Output 'All done!'` is not executed, since `Test-NotTwo` is deemed to have failed after generating the non-terminating error.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a088-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a088-149">See also</span></span>

- [<span data-ttu-id="5a088-150">about_Operators</span><span class="sxs-lookup"><span data-stu-id="5a088-150">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="5a088-151">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="5a088-151">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)
- [<span data-ttu-id="5a088-152">about_pipelines</span><span class="sxs-lookup"><span data-stu-id="5a088-152">about_pipelines</span></span>](about_pipelines.md)

