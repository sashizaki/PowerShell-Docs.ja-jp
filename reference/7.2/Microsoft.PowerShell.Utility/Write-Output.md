---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-output?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Output
ms.openlocfilehash: 7e0c958201dbd1b42d1f4c4ee286b8aca1f8595a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603026"
---
# <span data-ttu-id="7bc2d-102">Write-Output</span><span class="sxs-lookup"><span data-stu-id="7bc2d-102">Write-Output</span></span>

## <span data-ttu-id="7bc2d-103">概要</span><span class="sxs-lookup"><span data-stu-id="7bc2d-103">SYNOPSIS</span></span>
<span data-ttu-id="7bc2d-104">指定されたオブジェクトをパイプラインの次のコマンドに送信します。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-104">Sends the specified objects to the next command in the pipeline.</span></span> <span data-ttu-id="7bc2d-105">そのコマンドがパイプラインの最後のコマンドである場合、オブジェクトはコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-105">If the command is the last command in the pipeline, the objects are displayed in the console.</span></span>

## <span data-ttu-id="7bc2d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7bc2d-106">SYNTAX</span></span>

```
Write-Output [-InputObject] <PSObject[]> [-NoEnumerate] [<CommonParameters>]
```

## <span data-ttu-id="7bc2d-107">Description</span><span class="sxs-lookup"><span data-stu-id="7bc2d-107">DESCRIPTION</span></span>

<span data-ttu-id="7bc2d-108">`Write-Output`コマンドレットは、指定されたオブジェクトをパイプライン内の次のコマンドに送信します。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-108">The `Write-Output` cmdlet sends the specified object down the pipeline to the next command.</span></span>
<span data-ttu-id="7bc2d-109">そのコマンドがパイプラインの最後のコマンドである場合、オブジェクトはコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-109">If the command is the last command in the pipeline, the object is displayed in the console.</span></span>

<span data-ttu-id="7bc2d-110">`Write-Output` オブジェクトをプライマリパイプラインに送信します。 "出力ストリーム" または "成功パイプライン" とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-110">`Write-Output` sends objects down the primary pipeline, also known as the "output stream" or the "success pipeline."</span></span> <span data-ttu-id="7bc2d-111">エラー オブジェクトをエラー パイプラインを送信するには、Write-Error を使用します。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-111">To send error objects down the error pipeline, use Write-Error.</span></span>

<span data-ttu-id="7bc2d-112">このコマンドレットは通常、コンソールに文字列およびその他のオブジェクトを表示するためにスクリプトで使用されます。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-112">This cmdlet is typically used in scripts to display strings and other objects on the console.</span></span> <span data-ttu-id="7bc2d-113">の組み込みエイリアスの1つはで、を `Write-Output` `echo` 使用する他のシェルに似ていますが、 `echo` 既定の動作では、パイプラインの最後に出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-113">One of the built-in aliases for `Write-Output` is `echo` and similar to other shells that use `echo`, the default behavior is to display the output at the end of a pipeline.</span></span> <span data-ttu-id="7bc2d-114">PowerShell では、通常、出力が既定で表示されるインスタンスではコマンドレットを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-114">In PowerShell, it is generally not necessary to use the cmdlet in instances where the output is displayed by default.</span></span> <span data-ttu-id="7bc2d-115">たとえば、`Get-Process | Write-Output` は、`Get-Process` と同じです。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-115">For example, `Get-Process | Write-Output` is equivalent to `Get-Process`.</span></span> <span data-ttu-id="7bc2d-116">または、を `echo "Home directory: $HOME"` 書き込むことができ `"Home directory: $HOME"` ます。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-116">Or, `echo "Home directory: $HOME"` can be written, `"Home directory: $HOME"`.</span></span>

<span data-ttu-id="7bc2d-117">既定では、は、 `Write-Output` コマンドレットに指定されたコレクションを列挙します。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-117">By default, `Write-Output` enumerates through collections provided to the cmdlet.</span></span> <span data-ttu-id="7bc2d-118">ただし、を `Write-Output` 使用して、 **noenumerate** パラメーターを使用してコレクションを1つのオブジェクトとして渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-118">However, `Write-Output` can also be used to pass collections down the pipeline as a single object with the **NoEnumerate** parameter.</span></span>

## <span data-ttu-id="7bc2d-119">例</span><span class="sxs-lookup"><span data-stu-id="7bc2d-119">EXAMPLES</span></span>

### <span data-ttu-id="7bc2d-120">例 1: オブジェクトを取得し、コンソールに書き込む</span><span class="sxs-lookup"><span data-stu-id="7bc2d-120">Example 1: Get objects and write them to the console</span></span>

```powershell
$P = Get-Process
Write-Output $P
```

<span data-ttu-id="7bc2d-121">最初のコマンドは、コンピューター上で実行されているプロセスを取得し、変数に格納し `$P` ます。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-121">The first command gets processes running on the computer and stores them in the `$P` variable.</span></span>

<span data-ttu-id="7bc2d-122">2番目と3番目のコマンドは、コンソールののプロセスオブジェクトを表示し `$P` ます。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-122">The second and third commands display the process objects in `$P` on the console.</span></span>

### <span data-ttu-id="7bc2d-123">例 2: 別のコマンドレットに出力を渡す</span><span class="sxs-lookup"><span data-stu-id="7bc2d-123">Example 2: Pass output to another cmdlet</span></span>

```powershell
Write-Output "test output" | Get-Member
```

<span data-ttu-id="7bc2d-124">このコマンドは、パイプを使用して文字列が `Get-Member` 渡されたことを示す system.string クラスのメンバーを表示する、"test output" という文字列をコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-124">This command pipes the "test output" string to the `Get-Member` cmdlet, which displays the members of the **System.String** class, demonstrating that the string was passed along the pipeline.</span></span>

### <span data-ttu-id="7bc2d-125">例 3: 出力の列挙を抑制する</span><span class="sxs-lookup"><span data-stu-id="7bc2d-125">Example 3: Suppress enumeration in output</span></span>

```powershell
Write-Output 1,2,3 | Measure-Object
```

```Output
Count    : 3
...
```

```powershell
Write-Output 1,2,3 -NoEnumerate | Measure-Object
```

```Output
Count    : 1
...
```

<span data-ttu-id="7bc2d-126">このコマンドは、 **Noenumerate** パラメーターを追加して、コレクションまたは配列をパイプラインを介して1つのオブジェクトとして扱います。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-126">This command adds the **NoEnumerate** parameter to treat a collection or array as a single object through the pipeline.</span></span>

## <span data-ttu-id="7bc2d-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7bc2d-127">PARAMETERS</span></span>

### <span data-ttu-id="7bc2d-128">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7bc2d-128">-InputObject</span></span>

<span data-ttu-id="7bc2d-129">パイプラインに送信するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-129">Specifies the objects to send down the pipeline.</span></span> <span data-ttu-id="7bc2d-130">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-130">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7bc2d-131">-NoEnumerate</span><span class="sxs-lookup"><span data-stu-id="7bc2d-131">-NoEnumerate</span></span>

<span data-ttu-id="7bc2d-132">既定では、 `Write-Output` コマンドレットは常に出力を列挙します。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-132">By default, the `Write-Output` cmdlet always enumerates its output.</span></span> <span data-ttu-id="7bc2d-133">**Noenumerate** パラメーターを指定すると、既定の動作が抑制され、が出力を列挙できなくなり `Write-Output` ます。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-133">The **NoEnumerate** parameter suppresses the default behavior, and prevents `Write-Output` from enumerating output.</span></span> <span data-ttu-id="7bc2d-134">かっこによって列挙が強制されるため、 **Noenumerate** パラメーターは、コマンドがかっこで囲まれている場合には効果がありません。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-134">The **NoEnumerate** parameter has no effect if the command is wrapped in parentheses, because the parentheses force enumeration.</span></span> <span data-ttu-id="7bc2d-135">たとえば、は `(Write-Output 1,2,3)` 引き続き配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-135">For example, `(Write-Output 1,2,3)` still enumerates the array.</span></span>

> [!NOTE]
> <span data-ttu-id="7bc2d-136">このスイッチは、PowerShell Core 6.2 以降でのみ正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-136">This switch only works correctly with PowerShell Core 6.2 and newer.</span></span> <span data-ttu-id="7bc2d-137">以前のバージョンの PowerShell Core では、このスイッチを使用してもコレクションは引き続き列挙されます。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-137">On older versions of PowerShell Core, the collection is still enumerated even with use of this switch.</span></span>

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

### <span data-ttu-id="7bc2d-138">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7bc2d-138">CommonParameters</span></span>

<span data-ttu-id="7bc2d-139">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7bc2d-140">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7bc2d-141">入力</span><span class="sxs-lookup"><span data-stu-id="7bc2d-141">INPUTS</span></span>

### <span data-ttu-id="7bc2d-142">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="7bc2d-142">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="7bc2d-143">パイプを使用してオブジェクトをにパイプ処理でき `Write-Output` ます。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-143">You can pipe objects to `Write-Output`.</span></span>

## <span data-ttu-id="7bc2d-144">出力</span><span class="sxs-lookup"><span data-stu-id="7bc2d-144">OUTPUTS</span></span>

### <span data-ttu-id="7bc2d-145">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="7bc2d-145">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="7bc2d-146">`Write-Output` 入力として送信されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7bc2d-146">`Write-Output` returns the objects that are submitted as input.</span></span>

## <span data-ttu-id="7bc2d-147">注</span><span class="sxs-lookup"><span data-stu-id="7bc2d-147">NOTES</span></span>

## <span data-ttu-id="7bc2d-148">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7bc2d-148">RELATED LINKS</span></span>

[<span data-ttu-id="7bc2d-149">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="7bc2d-149">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="7bc2d-150">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="7bc2d-150">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="7bc2d-151">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="7bc2d-151">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="7bc2d-152">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="7bc2d-152">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="7bc2d-153">Write-Error</span><span class="sxs-lookup"><span data-stu-id="7bc2d-153">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="7bc2d-154">Write-Host</span><span class="sxs-lookup"><span data-stu-id="7bc2d-154">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="7bc2d-155">Write-Information</span><span class="sxs-lookup"><span data-stu-id="7bc2d-155">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="7bc2d-156">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="7bc2d-156">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="7bc2d-157">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="7bc2d-157">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="7bc2d-158">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="7bc2d-158">Write-Warning</span></span>](Write-Warning.md)
