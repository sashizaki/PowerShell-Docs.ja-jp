---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-output?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Output
ms.openlocfilehash: ccc72ac961adbcba542a7b8be55ad49df68a5ef6
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224296"
---
# <span data-ttu-id="cb06b-103">Write-Output</span><span class="sxs-lookup"><span data-stu-id="cb06b-103">Write-Output</span></span>

## <span data-ttu-id="cb06b-104">概要</span><span class="sxs-lookup"><span data-stu-id="cb06b-104">SYNOPSIS</span></span>
<span data-ttu-id="cb06b-105">指定されたオブジェクトをパイプラインの次のコマンドに送信します。</span><span class="sxs-lookup"><span data-stu-id="cb06b-105">Sends the specified objects to the next command in the pipeline.</span></span> <span data-ttu-id="cb06b-106">そのコマンドがパイプラインの最後のコマンドである場合、オブジェクトはコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb06b-106">If the command is the last command in the pipeline, the objects are displayed in the console.</span></span>

## <span data-ttu-id="cb06b-107">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cb06b-107">SYNTAX</span></span>

```
Write-Output [-InputObject] <PSObject[]> [-NoEnumerate] [<CommonParameters>]
```

## <span data-ttu-id="cb06b-108">Description</span><span class="sxs-lookup"><span data-stu-id="cb06b-108">DESCRIPTION</span></span>

<span data-ttu-id="cb06b-109">`Write-Output`コマンドレットは、指定されたオブジェクトをパイプライン内の次のコマンドに送信します。</span><span class="sxs-lookup"><span data-stu-id="cb06b-109">The `Write-Output` cmdlet sends the specified object down the pipeline to the next command.</span></span>
<span data-ttu-id="cb06b-110">そのコマンドがパイプラインの最後のコマンドである場合、オブジェクトはコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb06b-110">If the command is the last command in the pipeline, the object is displayed in the console.</span></span>

<span data-ttu-id="cb06b-111">`Write-Output` オブジェクトをプライマリパイプラインに送信します。 "出力ストリーム" または "成功パイプライン" とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="cb06b-111">`Write-Output` sends objects down the primary pipeline, also known as the "output stream" or the "success pipeline."</span></span> <span data-ttu-id="cb06b-112">エラー オブジェクトをエラー パイプラインを送信するには、Write-Error を使用します。</span><span class="sxs-lookup"><span data-stu-id="cb06b-112">To send error objects down the error pipeline, use Write-Error.</span></span>

<span data-ttu-id="cb06b-113">このコマンドレットは通常、コンソールに文字列およびその他のオブジェクトを表示するためにスクリプトで使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb06b-113">This cmdlet is typically used in scripts to display strings and other objects on the console.</span></span> <span data-ttu-id="cb06b-114">の組み込みエイリアスの1つはで、を `Write-Output` `echo` 使用する他のシェルに似ていますが、 `echo` 既定の動作では、パイプラインの最後に出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb06b-114">One of the built-in aliases for `Write-Output` is `echo` and similar to other shells that use `echo`, the default behavior is to display the output at the end of a pipeline.</span></span> <span data-ttu-id="cb06b-115">PowerShell では、通常、出力が既定で表示されるインスタンスではコマンドレットを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cb06b-115">In PowerShell, it is generally not necessary to use the cmdlet in instances where the output is displayed by default.</span></span> <span data-ttu-id="cb06b-116">たとえば、`Get-Process | Write-Output` は、`Get-Process` と同じです。</span><span class="sxs-lookup"><span data-stu-id="cb06b-116">For example, `Get-Process | Write-Output` is equivalent to `Get-Process`.</span></span> <span data-ttu-id="cb06b-117">または、を `echo "Home directory: $HOME"` 書き込むことができ `"Home directory: $HOME"` ます。</span><span class="sxs-lookup"><span data-stu-id="cb06b-117">Or, `echo "Home directory: $HOME"` can be written, `"Home directory: $HOME"`.</span></span>

<span data-ttu-id="cb06b-118">既定では、は、 `Write-Output` コマンドレットに指定されたコレクションを列挙します。</span><span class="sxs-lookup"><span data-stu-id="cb06b-118">By default, `Write-Output` enumerates through collections provided to the cmdlet.</span></span> <span data-ttu-id="cb06b-119">ただし、を `Write-Output` 使用して、 **noenumerate** パラメーターを使用してコレクションを1つのオブジェクトとして渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="cb06b-119">However, `Write-Output` can also be used to pass collections down the pipeline as a single object with the **NoEnumerate** parameter.</span></span>

## <span data-ttu-id="cb06b-120">例</span><span class="sxs-lookup"><span data-stu-id="cb06b-120">EXAMPLES</span></span>

### <span data-ttu-id="cb06b-121">例 1: オブジェクトを取得し、コンソールに書き込む</span><span class="sxs-lookup"><span data-stu-id="cb06b-121">Example 1: Get objects and write them to the console</span></span>

```powershell
$P = Get-Process
Write-Output $P
```

<span data-ttu-id="cb06b-122">最初のコマンドは、コンピューター上で実行されているプロセスを取得し、変数に格納し `$P` ます。</span><span class="sxs-lookup"><span data-stu-id="cb06b-122">The first command gets processes running on the computer and stores them in the `$P` variable.</span></span>

<span data-ttu-id="cb06b-123">2番目と3番目のコマンドは、コンソールののプロセスオブジェクトを表示し `$P` ます。</span><span class="sxs-lookup"><span data-stu-id="cb06b-123">The second and third commands display the process objects in `$P` on the console.</span></span>

### <span data-ttu-id="cb06b-124">例 2: 別のコマンドレットに出力を渡す</span><span class="sxs-lookup"><span data-stu-id="cb06b-124">Example 2: Pass output to another cmdlet</span></span>

```powershell
Write-Output "test output" | Get-Member
```

<span data-ttu-id="cb06b-125">このコマンドは、パイプを使用して文字列が `Get-Member` 渡されたことを示す system.string クラス **System.String** のメンバーを表示する、"test output" という文字列をコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="cb06b-125">This command pipes the "test output" string to the `Get-Member` cmdlet, which displays the members of the **System.String** class, demonstrating that the string was passed along the pipeline.</span></span>

### <span data-ttu-id="cb06b-126">例 3: 出力の列挙を抑制する</span><span class="sxs-lookup"><span data-stu-id="cb06b-126">Example 3: Suppress enumeration in output</span></span>

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

<span data-ttu-id="cb06b-127">このコマンドは、 **Noenumerate** パラメーターを追加して、コレクションまたは配列をパイプラインを介して1つのオブジェクトとして扱います。</span><span class="sxs-lookup"><span data-stu-id="cb06b-127">This command adds the **NoEnumerate** parameter to treat a collection or array as a single object through the pipeline.</span></span>

## <span data-ttu-id="cb06b-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cb06b-128">PARAMETERS</span></span>

### <span data-ttu-id="cb06b-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="cb06b-129">-InputObject</span></span>

<span data-ttu-id="cb06b-130">パイプラインに送信するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cb06b-130">Specifies the objects to send down the pipeline.</span></span> <span data-ttu-id="cb06b-131">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="cb06b-131">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="cb06b-132">-NoEnumerate</span><span class="sxs-lookup"><span data-stu-id="cb06b-132">-NoEnumerate</span></span>

<span data-ttu-id="cb06b-133">既定では、 `Write-Output` コマンドレットは常に出力を列挙します。</span><span class="sxs-lookup"><span data-stu-id="cb06b-133">By default, the `Write-Output` cmdlet always enumerates its output.</span></span> <span data-ttu-id="cb06b-134">**Noenumerate** パラメーターを指定すると、既定の動作が抑制され、が出力を列挙できなくなり `Write-Output` ます。</span><span class="sxs-lookup"><span data-stu-id="cb06b-134">The **NoEnumerate** parameter suppresses the default behavior, and prevents `Write-Output` from enumerating output.</span></span> <span data-ttu-id="cb06b-135">かっこによって列挙が強制されるため、 **Noenumerate** パラメーターは、コマンドがかっこで囲まれている場合には効果がありません。</span><span class="sxs-lookup"><span data-stu-id="cb06b-135">The **NoEnumerate** parameter has no effect if the command is wrapped in parentheses, because the parentheses force enumeration.</span></span> <span data-ttu-id="cb06b-136">たとえば、は `(Write-Output 1,2,3)` 引き続き配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="cb06b-136">For example, `(Write-Output 1,2,3)` still enumerates the array.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb06b-137">PowerShell 6.2 以降で修正された Windows PowerShell では、このスイッチに問題があります。</span><span class="sxs-lookup"><span data-stu-id="cb06b-137">There is an issue with this switch in Windows PowerShell that is fixed in PowerShell 6.2 and above.</span></span> <span data-ttu-id="cb06b-138">**Noenumerate** を使用し、 **InputObject** パラメーターを明示的に使用すると、コマンドは引き続きを列挙します。</span><span class="sxs-lookup"><span data-stu-id="cb06b-138">When using **NoEnumerate** and explicitly using the **InputObject** parameter, the command still enumerates.</span></span> <span data-ttu-id="cb06b-139">この問題を回避するには、 **InputObject** 引数を位置に渡します。</span><span class="sxs-lookup"><span data-stu-id="cb06b-139">To work around this, pass the **InputObject** argument(s) positionally.</span></span>

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

### <span data-ttu-id="cb06b-140">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="cb06b-140">CommonParameters</span></span>

<span data-ttu-id="cb06b-141">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="cb06b-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cb06b-142">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb06b-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cb06b-143">入力</span><span class="sxs-lookup"><span data-stu-id="cb06b-143">INPUTS</span></span>

### <span data-ttu-id="cb06b-144">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="cb06b-144">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="cb06b-145">パイプを使用してオブジェクトをにパイプ処理でき `Write-Output` ます。</span><span class="sxs-lookup"><span data-stu-id="cb06b-145">You can pipe objects to `Write-Output`.</span></span>

## <span data-ttu-id="cb06b-146">出力</span><span class="sxs-lookup"><span data-stu-id="cb06b-146">OUTPUTS</span></span>

### <span data-ttu-id="cb06b-147">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="cb06b-147">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="cb06b-148">`Write-Output` 入力として送信されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="cb06b-148">`Write-Output` returns the objects that are submitted as input.</span></span>

## <span data-ttu-id="cb06b-149">注</span><span class="sxs-lookup"><span data-stu-id="cb06b-149">NOTES</span></span>

## <span data-ttu-id="cb06b-150">関連リンク</span><span class="sxs-lookup"><span data-stu-id="cb06b-150">RELATED LINKS</span></span>

[<span data-ttu-id="cb06b-151">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="cb06b-151">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="cb06b-152">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="cb06b-152">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="cb06b-153">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="cb06b-153">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="cb06b-154">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="cb06b-154">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="cb06b-155">書き込み-エラー</span><span class="sxs-lookup"><span data-stu-id="cb06b-155">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="cb06b-156">Write-Host</span><span class="sxs-lookup"><span data-stu-id="cb06b-156">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="cb06b-157">Write-Information</span><span class="sxs-lookup"><span data-stu-id="cb06b-157">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="cb06b-158">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="cb06b-158">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="cb06b-159">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="cb06b-159">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="cb06b-160">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="cb06b-160">Write-Warning</span></span>](Write-Warning.md)