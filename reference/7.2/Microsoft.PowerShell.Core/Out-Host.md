---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Host
ms.openlocfilehash: 4fefb133416b3db6c19c71a916d73fe00f86f3a4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599713"
---
# <span data-ttu-id="245cb-102">Out-Host</span><span class="sxs-lookup"><span data-stu-id="245cb-102">Out-Host</span></span>

## <span data-ttu-id="245cb-103">概要</span><span class="sxs-lookup"><span data-stu-id="245cb-103">SYNOPSIS</span></span>
<span data-ttu-id="245cb-104">コマンド ラインに出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="245cb-104">Sends output to the command line.</span></span>

## <span data-ttu-id="245cb-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="245cb-105">SYNTAX</span></span>

### <span data-ttu-id="245cb-106">すべて</span><span class="sxs-lookup"><span data-stu-id="245cb-106">All</span></span>

```
Out-Host [-Paging] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="245cb-107">Description</span><span class="sxs-lookup"><span data-stu-id="245cb-107">DESCRIPTION</span></span>

<span data-ttu-id="245cb-108">`Out-Host`コマンドレットは、出力を PowerShell ホストに送信して表示します。</span><span class="sxs-lookup"><span data-stu-id="245cb-108">The `Out-Host` cmdlet sends output to the PowerShell host for display.</span></span> <span data-ttu-id="245cb-109">ホストは、コマンド ラインに出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="245cb-109">The host displays the output at the command line.</span></span> <span data-ttu-id="245cb-110">`Out-Host`が既定値であるため、パラメーターを使用する場合を除き、指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="245cb-110">Because `Out-Host` is the default, you don't have to specify it unless you want to use its parameters.</span></span>

<span data-ttu-id="245cb-111">`Out-Host` は、実行されるすべてのコマンドに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="245cb-111">`Out-Host` is automatically appended to every command that is executed.</span></span> <span data-ttu-id="245cb-112">パイプラインの出力を、コマンドを実行しているホストに渡します。</span><span class="sxs-lookup"><span data-stu-id="245cb-112">It passes the output of the pipeline to the host executing the command.</span></span> <span data-ttu-id="245cb-113">`Out-Host` は、ANSI エスケープシーケンスを無視します。</span><span class="sxs-lookup"><span data-stu-id="245cb-113">`Out-Host` ignores ANSI escape sequences.</span></span> <span data-ttu-id="245cb-114">エスケープシーケンスはホストによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="245cb-114">The escape sequences are handled by the host.</span></span> <span data-ttu-id="245cb-115">`Out-Host` は、ANSI エスケープシーケンスを解釈または変更せずにホストに渡します。</span><span class="sxs-lookup"><span data-stu-id="245cb-115">`Out-Host` passes ANSI escape sequences to the host without trying to interpret or change them.</span></span>

## <span data-ttu-id="245cb-116">例</span><span class="sxs-lookup"><span data-stu-id="245cb-116">EXAMPLES</span></span>

### <span data-ttu-id="245cb-117">例 1: 出力を1ページずつ表示する</span><span class="sxs-lookup"><span data-stu-id="245cb-117">Example 1: Display output one page at a time</span></span>

<span data-ttu-id="245cb-118">この例では、システムによって一度に1ページずつ処理されます。</span><span class="sxs-lookup"><span data-stu-id="245cb-118">This example displays the system processes one page at a time.</span></span>

```powershell
Get-Process | Out-Host -Paging
```

```Output
NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     30    24.12      36.95      15.86   21004  14 ApplicationFrameHost
     55    24.33      60.48      10.80   12904  14 BCompare
<SPACE> next page; <CR> next line; Q quit
      9     4.71       8.94       0.00   16864  14 explorer
<SPACE> next page; <CR> next line; Q quit
```

<span data-ttu-id="245cb-119">`Get-Process` システムプロセスを取得し、オブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="245cb-119">`Get-Process` gets the system processes and sends the objects down the pipeline.</span></span> <span data-ttu-id="245cb-120">`Out-Host`**ページング** パラメーターを使用して、一度に1ページのデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="245cb-120">`Out-Host` uses the **Paging** parameter to display one page of data at a time.</span></span>

### <span data-ttu-id="245cb-121">例 2: 入力として変数を使用する</span><span class="sxs-lookup"><span data-stu-id="245cb-121">Example 2: Use a variable as input</span></span>

<span data-ttu-id="245cb-122">この例では、変数に格納されているオブジェクトをの入力として使用 `Out-Host` します。</span><span class="sxs-lookup"><span data-stu-id="245cb-122">This example uses objects stored in a variable as the input for `Out-Host`.</span></span>

```powershell
$io = Get-History
Out-Host -InputObject $io
```

<span data-ttu-id="245cb-123">`Get-History` PowerShell セッションの履歴を取得し、そのオブジェクトを変数に格納し `$io` ます。</span><span class="sxs-lookup"><span data-stu-id="245cb-123">`Get-History` gets the PowerShell session's history, and stores the objects in the `$io` variable.</span></span>
<span data-ttu-id="245cb-124">`Out-Host`**InputObject** パラメーターを使用して変数を指定 `$io` し、履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="245cb-124">`Out-Host` uses the **InputObject** parameter to specify the `$io` variable and displays the history.</span></span>

## <span data-ttu-id="245cb-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="245cb-125">PARAMETERS</span></span>

### <span data-ttu-id="245cb-126">-InputObject</span><span class="sxs-lookup"><span data-stu-id="245cb-126">-InputObject</span></span>

<span data-ttu-id="245cb-127">コンソールに書き込まれるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="245cb-127">Specifies the objects that are written to the console.</span></span> <span data-ttu-id="245cb-128">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="245cb-128">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="245cb-129">-ページング</span><span class="sxs-lookup"><span data-stu-id="245cb-129">-Paging</span></span>

<span data-ttu-id="245cb-130">は `Out-Host` 、一度に1ページの出力を表示し、残りのページが表示される前にユーザー入力を待機することを示します。</span><span class="sxs-lookup"><span data-stu-id="245cb-130">Indicates that `Out-Host` displays one page of output at a time, and waits for user input before the remaining pages are displayed.</span></span> <span data-ttu-id="245cb-131">既定では、すべての出力が1ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="245cb-131">By default, all the output is displayed on a single page.</span></span> <span data-ttu-id="245cb-132">ページ サイズは、ホストの特性によって決まります。</span><span class="sxs-lookup"><span data-stu-id="245cb-132">The page size is determined by the characteristics of the host.</span></span>

<span data-ttu-id="245cb-133"><kbd>スペース</kbd>バーを押すと、次の出力ページが表示されます。 <kbd>enter</kbd>キーを押すと、次の出力行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="245cb-133">Press the <kbd>Space</kbd> bar to display the next page of output or the <kbd>Enter</kbd> key to view the next line of output.</span></span> <span data-ttu-id="245cb-134"><kbd>Q</kbd>キーを押して終了します。</span><span class="sxs-lookup"><span data-stu-id="245cb-134">Press <kbd>Q</kbd> to quit.</span></span>

<span data-ttu-id="245cb-135">**ページング** は、 **more** コマンドに似ています。</span><span class="sxs-lookup"><span data-stu-id="245cb-135">**Paging** is similar to the **more** command.</span></span>

> [!NOTE]
> <span data-ttu-id="245cb-136">**ページング** パラメーターは、PowerShell ISE ホストではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="245cb-136">The **Paging** parameter isn't supported by the PowerShell ISE host.</span></span>

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

### <span data-ttu-id="245cb-137">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="245cb-137">CommonParameters</span></span>

<span data-ttu-id="245cb-138">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="245cb-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="245cb-139">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="245cb-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="245cb-140">入力</span><span class="sxs-lookup"><span data-stu-id="245cb-140">INPUTS</span></span>

### <span data-ttu-id="245cb-141">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="245cb-141">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="245cb-142">オブジェクトをパイプラインからに送信でき `Out-Host` ます。</span><span class="sxs-lookup"><span data-stu-id="245cb-142">You can send objects down the pipeline to `Out-Host`.</span></span>

## <span data-ttu-id="245cb-143">出力</span><span class="sxs-lookup"><span data-stu-id="245cb-143">OUTPUTS</span></span>

### <span data-ttu-id="245cb-144">なし</span><span class="sxs-lookup"><span data-stu-id="245cb-144">None</span></span>

<span data-ttu-id="245cb-145">`Out-Host` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="245cb-145">`Out-Host` doesn't generate any output.</span></span> <span data-ttu-id="245cb-146">表示するために、オブジェクトをホストに送信します。</span><span class="sxs-lookup"><span data-stu-id="245cb-146">It sends objects to the host for display.</span></span>

## <span data-ttu-id="245cb-147">注</span><span class="sxs-lookup"><span data-stu-id="245cb-147">NOTES</span></span>

<span data-ttu-id="245cb-148">**ページング** パラメーターは、すべての PowerShell ホストではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="245cb-148">The **Paging** parameter isn't supported by all PowerShell hosts.</span></span> <span data-ttu-id="245cb-149">たとえば、PowerShell ISE で **Paging** パラメーターを使用すると、次のエラーが表示されます。 `out-lineoutput : The method or operation is not implemented.`</span><span class="sxs-lookup"><span data-stu-id="245cb-149">For example, if you use the **Paging** parameter in the PowerShell ISE, the following error is displayed: `out-lineoutput : The method or operation is not implemented.`</span></span>

<span data-ttu-id="245cb-150">**Out** 動詞を含むコマンドレットは、 `Out-` オブジェクトを書式設定しません。</span><span class="sxs-lookup"><span data-stu-id="245cb-150">The cmdlets that contain the **Out** verb, `Out-`, don't format objects.</span></span> <span data-ttu-id="245cb-151">オブジェクトをレンダリングし、指定された表示先に送信します。</span><span class="sxs-lookup"><span data-stu-id="245cb-151">They render objects and send them to the specified display destination.</span></span> <span data-ttu-id="245cb-152">書式設定されていないオブジェクトをコマンドレットに送信すると、コマンドレットによって、 `Out-` レンダリングされる前に書式設定コマンドレットに送信されます。</span><span class="sxs-lookup"><span data-stu-id="245cb-152">If you send an unformatted object to an `Out-` cmdlet, the cmdlet sends it to a formatting cmdlet before rendering it.</span></span>

<span data-ttu-id="245cb-153">`Out-`コマンドレットには、名前またはファイルパスのパラメーターがありません。</span><span class="sxs-lookup"><span data-stu-id="245cb-153">The `Out-` cmdlets don't have parameters for names or file paths.</span></span> <span data-ttu-id="245cb-154">コマンドレットにデータを送信するには、パイプラインを使用して `Out-` PowerShell コマンドの出力をコマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="245cb-154">To send data to an `Out-` cmdlet, use the pipeline to send a PowerShell command's output to the cmdlet.</span></span> <span data-ttu-id="245cb-155">または、変数にデータを格納し、 **InputObject** パラメーターを使用してデータをコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="245cb-155">Or, you can store data in a variable and use the **InputObject** parameter to pass the data to the cmdlet.</span></span>

<span data-ttu-id="245cb-156">`Out-Host` データを送信しますが、出力オブジェクトは生成しません。</span><span class="sxs-lookup"><span data-stu-id="245cb-156">`Out-Host` sends data, but it doesn't produce any output objects.</span></span> <span data-ttu-id="245cb-157">の出力を `Out-Host` コマンドレットにパイプラインすると `Get-Member` 、は `Get-Member` オブジェクトが指定されていないことを報告します。</span><span class="sxs-lookup"><span data-stu-id="245cb-157">If you pipeline the output of `Out-Host` to the `Get-Member` cmdlet, `Get-Member` reports that no objects have been specified.</span></span>

## <span data-ttu-id="245cb-158">関連リンク</span><span class="sxs-lookup"><span data-stu-id="245cb-158">RELATED LINKS</span></span>

[<span data-ttu-id="245cb-159">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="245cb-159">Clear-Host</span></span>](Clear-Host.md)

[<span data-ttu-id="245cb-160">Out-Default</span><span class="sxs-lookup"><span data-stu-id="245cb-160">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="245cb-161">Out-File</span><span class="sxs-lookup"><span data-stu-id="245cb-161">Out-File</span></span>](../Microsoft.PowerShell.Utility/Out-File.md)

[<span data-ttu-id="245cb-162">Out-Null</span><span class="sxs-lookup"><span data-stu-id="245cb-162">Out-Null</span></span>](Out-Null.md)

[<span data-ttu-id="245cb-163">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="245cb-163">Out-Printer</span></span>](../Microsoft.PowerShell.Utility/Out-Printer.md)

[<span data-ttu-id="245cb-164">Out-String</span><span class="sxs-lookup"><span data-stu-id="245cb-164">Out-String</span></span>](../Microsoft.PowerShell.Utility/Out-String.md)

[<span data-ttu-id="245cb-165">Write-Host</span><span class="sxs-lookup"><span data-stu-id="245cb-165">Write-Host</span></span>](../Microsoft.PowerShell.Utility/Write-Host.md)

