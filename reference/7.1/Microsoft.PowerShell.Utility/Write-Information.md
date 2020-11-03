---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-information?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Information
ms.openlocfilehash: 2c6d9a66a7253af4621053a9006730dce856353c
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224363"
---
# <span data-ttu-id="ebf03-103">Write-Information</span><span class="sxs-lookup"><span data-stu-id="ebf03-103">Write-Information</span></span>

## <span data-ttu-id="ebf03-104">概要</span><span class="sxs-lookup"><span data-stu-id="ebf03-104">SYNOPSIS</span></span>

<span data-ttu-id="ebf03-105">PowerShell がコマンドの情報ストリームデータを処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebf03-105">Specifies how PowerShell handles information stream data for a command.</span></span>

## <span data-ttu-id="ebf03-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ebf03-106">SYNTAX</span></span>

```
Write-Information [-MessageData] <Object> [[-Tags] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="ebf03-107">Description</span><span class="sxs-lookup"><span data-stu-id="ebf03-107">DESCRIPTION</span></span>

<span data-ttu-id="ebf03-108">`Write-Information`コマンドレットは、PowerShell がコマンドの情報ストリームデータを処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebf03-108">The `Write-Information` cmdlet specifies how PowerShell handles information stream data for a command.</span></span>

<span data-ttu-id="ebf03-109">Windows PowerShell 5.0 では、新しい構造化された情報ストリームが導入されています。</span><span class="sxs-lookup"><span data-stu-id="ebf03-109">Windows PowerShell 5.0 introduces a new, structured information stream.</span></span> <span data-ttu-id="ebf03-110">このストリームを使用して、スクリプトとその呼び出し元またはホストアプリケーションとの間で構造化データを転送できます。</span><span class="sxs-lookup"><span data-stu-id="ebf03-110">You can use this stream to transmit structured data between a script and its callers or the host application.</span></span>
<span data-ttu-id="ebf03-111">`Write-Information` ストリームに情報メッセージを追加したり、PowerShell がコマンドの情報ストリームデータを処理する方法を指定したりできます。</span><span class="sxs-lookup"><span data-stu-id="ebf03-111">`Write-Information` lets you add an informational message to the stream, and specify how PowerShell handles information stream data for a command.</span></span> <span data-ttu-id="ebf03-112">情報ストリームは `PowerShell.Streams` 、、ジョブ、およびスケジュールされたタスクにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebf03-112">Information streams also work for `PowerShell.Streams`, jobs, and scheduled tasks.</span></span>

> [!NOTE]
> <span data-ttu-id="ebf03-113">情報ストリームは、メッセージを "[Stream Name]:" にプレフィックスとする標準規約に従っていません。</span><span class="sxs-lookup"><span data-stu-id="ebf03-113">The information stream does not follow the standard convention of prefixing its messages with "[Stream Name]:".</span></span> <span data-ttu-id="ebf03-114">これは簡潔さと視覚的な cleanliness を目的としています。</span><span class="sxs-lookup"><span data-stu-id="ebf03-114">This was intended for brevity and visual cleanliness.</span></span>

<span data-ttu-id="ebf03-115">ユーザー設定変数の値によって、 `$InformationPreference` に対して指定したメッセージ `Write-Information` が、スクリプトの操作の予想される位置に表示されるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="ebf03-115">The `$InformationPreference` preference variable value determines whether the message you provide to `Write-Information` is displayed at the expected point in a script's operation.</span></span> <span data-ttu-id="ebf03-116">この変数の既定値はであるため、 `SilentlyContinue` 既定では情報メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="ebf03-116">Because the default value of this variable is `SilentlyContinue`, by default, informational messages are not shown.</span></span> <span data-ttu-id="ebf03-117">の値を変更しない場合は `$InformationPreference` 、コマンドに共通パラメーターを追加することで、その値をオーバーライドでき `InformationAction` ます。</span><span class="sxs-lookup"><span data-stu-id="ebf03-117">If you don't want to change the value of `$InformationPreference`, you can override its value by adding the `InformationAction` common parameter to your command.</span></span> <span data-ttu-id="ebf03-118">詳細については、「 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md) 」および「 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebf03-118">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md) and [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ebf03-119">Windows PowerShell 5.0 以降では、を `Write-Host` 使用して、 `Write-Information` `Write-Host` 情報ストリームに出力を出力することができます。</span><span class="sxs-lookup"><span data-stu-id="ebf03-119">Starting in Windows PowerShell 5.0, `Write-Host` is a wrapper for `Write-Information` This allows you to use `Write-Host` to emit output to the information stream.</span></span> <span data-ttu-id="ebf03-120">これにより、後方互換性を維持しながら、を使用して書き込まれたデータを **キャプチャ** または **抑制** でき `Write-Host` ます。</span><span class="sxs-lookup"><span data-stu-id="ebf03-120">This enables the **capture** or **suppression** of data written using `Write-Host` while preserving backwards compatibility.</span></span> <span data-ttu-id="ebf03-121">詳細については[、「書き込み-ホスト](Write-Host.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebf03-121">For more information see [Write-Host](Write-Host.md)</span></span>

<span data-ttu-id="ebf03-122">`Write-Information` は、PowerShell 5.x でサポートされているワークフローアクティビティでもあります。</span><span class="sxs-lookup"><span data-stu-id="ebf03-122">`Write-Information` is also a supported workflow activity in PowerShell 5.x.</span></span>

## <span data-ttu-id="ebf03-123">例</span><span class="sxs-lookup"><span data-stu-id="ebf03-123">EXAMPLES</span></span>

### <span data-ttu-id="ebf03-124">例 1: Get 結果の情報を書き込む</span><span class="sxs-lookup"><span data-stu-id="ebf03-124">Example 1: Write information for Get- results</span></span>

<span data-ttu-id="ebf03-125">この例では、コマンドを実行した後、" `Get-WindowsFeature` p" で始まる名前値を持つすべての機能を検索するために、"取得した機能!" という情報メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebf03-125">In this example, you show an informational message, "Got your features!", after running the `Get-WindowsFeature` command to find all features that have a Name value that starts with 'p'.</span></span>
<span data-ttu-id="ebf03-126">`$InformationPreference`変数はまだ既定値に設定されているので、パラメーターを追加して `SilentlyContinue` `InformationAction` `$InformationPreference` 値をオーバーライドし、メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="ebf03-126">Because the `$InformationPreference` variable is still set to its default, `SilentlyContinue`, you add the `InformationAction` parameter to override the `$InformationPreference` value, and show the message.</span></span> <span data-ttu-id="ebf03-127">`InformationAction`値は Continue です。つまり、メッセージが表示されますが、まだ完了していない場合は、スクリプトまたはコマンドが続行されます。</span><span class="sxs-lookup"><span data-stu-id="ebf03-127">The `InformationAction` value is Continue, which means that your message is shown, but the script or command continues, if it is not yet finished.</span></span>

```powershell
Get-WindowsFeature -Name p*
Write-Information -MessageData "Got your features!" -InformationAction Continue
```

```Output
Display Name                                            Name                       Install State
------------                                            ----                       -------------
[ ] Print and Document Services                         Print-Services                 Available
    [ ] Print Server                                    Print-Server                   Available
    [ ] Distributed Scan Server                         Print-Scan-Server              Available
    [ ] Internet Printing                               Print-Internet                 Available
    [ ] LPD Service                                     Print-LPD-Service              Available
[ ] Peer Name Resolution Protocol                       PNRP                           Available
[X] Windows PowerShell                                  PowerShellRoot                 Installed
    [X] Windows PowerShell 5.0                          PowerShell                     Installed
    [ ] Windows PowerShell 2.0 Engine                   PowerShell-V2                    Removed
    [X] Windows PowerShell ISE                          PowerShell-ISE                 Installed
Got your features!
```

### <span data-ttu-id="ebf03-128">例 2: 情報を書き込んでタグを付ける</span><span class="sxs-lookup"><span data-stu-id="ebf03-128">Example 2: Write information and tag it</span></span>

<span data-ttu-id="ebf03-129">この例では、を使用し `Write-Information` て、現在のコマンドの実行が完了した後に別のコマンドを実行する必要があることをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="ebf03-129">In this example, you use `Write-Information` to let users know they'll need to run another command after they're done running the current command.</span></span> <span data-ttu-id="ebf03-130">この例では、情報メッセージにタグ命令を追加します。</span><span class="sxs-lookup"><span data-stu-id="ebf03-130">The example adds the tag Instructions to the informational message.</span></span> <span data-ttu-id="ebf03-131">このコマンドを実行した後、情報ストリームでタグ付きのメッセージを検索すると、ここで指定したメッセージが結果の中に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebf03-131">After running this command, if you search the information stream for messages tagged Instructions, the message specified here would be among the results.</span></span>

```powershell
$message = "To filter your results for PowerShell, pipe your results to the Where-Object cmdlet."
Get-WindowsFeature -Name p*
Write-Information -MessageData $message -Tags "Instructions" -InformationAction Continue
```

```Output
Display Name                                            Name                       Install State
------------                                            ----                       -------------
[ ] Print and Document Services                         Print-Services                 Available
    [ ] Print Server                                    Print-Server                   Available
    [ ] Distributed Scan Server                         Print-Scan-Server              Available
    [ ] Internet Printing                               Print-Internet                 Available
    [ ] LPD Service                                     Print-LPD-Service              Available
[ ] Peer Name Resolution Protocol                       PNRP                           Available
[X] Windows PowerShell                                  PowerShellRoot                 Installed
    [X] Windows PowerShell 5.0                          PowerShell                     Installed
    [ ] Windows PowerShell 2.0 Engine                   PowerShell-V2                    Removed
    [X] Windows PowerShell ISE                          PowerShell-ISE                 Installed
To filter your results for PowerShell, pipe your results to the Where-Object cmdlet.
```

### <span data-ttu-id="ebf03-132">例 3: ファイルに情報を書き込む</span><span class="sxs-lookup"><span data-stu-id="ebf03-132">Example 3: Write information to a file</span></span>

<span data-ttu-id="ebf03-133">この例では、コードを使用して関数の情報ストリームをにリダイレクトし `Info.txt` `6>` ます。</span><span class="sxs-lookup"><span data-stu-id="ebf03-133">In this example, you redirect the information stream in the function to a `Info.txt` using the code `6>`.</span></span> <span data-ttu-id="ebf03-134">ファイルを開くと、 `Info.txt` "ここに入力してください" というテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebf03-134">When you open the `Info.txt` file, you see the text, "Here you go."</span></span>

```powershell
function Test-Info
{
    Get-Process P*
    Write-Information "Here you go"
}
Test-Info 6> Info.txt
```

### <span data-ttu-id="ebf03-135">例 4: オブジェクトを渡して情報を書き込む</span><span class="sxs-lookup"><span data-stu-id="ebf03-135">Example 4: Pass object to write information</span></span>

<span data-ttu-id="ebf03-136">この例では、を使用し `Write-Information` て、複数のパイプラインを通過するオブジェクト出力から上位10個の CPU 使用率プロセスを書き込むことができ `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="ebf03-136">In this example, you can use `Write-Information` to write the top 10 highest CPU utilization processes from the `Get-Process` object output that has passes through multiple pipelines.</span></span>

```powershell
Get-Process | Sort-Object CPU -Descending |
    Select-Object Id, ProcessName, CPU -First 10 |
        Write-Information -InformationAction Continue
```

```Output
@{Id=12692; ProcessName=chrome; CPU=39431.296875}
@{Id=21292; ProcessName=OUTLOOK; CPU=23991.875}
@{Id=10548; ProcessName=CefSharp.BrowserSubprocess; CPU=20546.203125}
@{Id=312848; ProcessName=Taskmgr; CPU=13173.1875}
@{Id=10848; ProcessName=SnapClient; CPU=7014.265625}
@{Id=9760; ProcessName=Receiver; CPU=6792.359375}
@{Id=12040; ProcessName=Teams; CPU=5605.578125}
@{Id=498388; ProcessName=chrome; CPU=3062.453125}
@{Id=6900; ProcessName=chrome; CPU=2546.9375}
@{Id=9044; ProcessName=explorer; CPU=2358.765625}
```

## <span data-ttu-id="ebf03-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ebf03-137">PARAMETERS</span></span>

### <span data-ttu-id="ebf03-138">-MessageData</span><span class="sxs-lookup"><span data-stu-id="ebf03-138">-MessageData</span></span>

<span data-ttu-id="ebf03-139">スクリプトまたはコマンドを実行するときにユーザーに表示する情報メッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="ebf03-139">Specifies an informational message that you want to display to users as they run a script or command.</span></span> <span data-ttu-id="ebf03-140">最適な結果を得るには、情報メッセージを引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="ebf03-140">For best results, enclose the informational message in quotation marks.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Msg, Message

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ebf03-141">-タグ</span><span class="sxs-lookup"><span data-stu-id="ebf03-141">-Tags</span></span>

<span data-ttu-id="ebf03-142">で情報ストリームに追加したメッセージの並べ替えとフィルター処理に使用できる単純な文字列を指定し `Write-Information` ます。</span><span class="sxs-lookup"><span data-stu-id="ebf03-142">Specifies a simple string that you can use to sort and filter messages that you have added to the information stream with `Write-Information`.</span></span> <span data-ttu-id="ebf03-143">このパラメーターは、の **Tags** パラメーターと同じように動作 `New-ModuleManifest` します。</span><span class="sxs-lookup"><span data-stu-id="ebf03-143">This parameter works similarly to the **Tags** parameter in `New-ModuleManifest`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ebf03-144">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ebf03-144">CommonParameters</span></span>

<span data-ttu-id="ebf03-145">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ebf03-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ebf03-146">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebf03-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ebf03-147">入力</span><span class="sxs-lookup"><span data-stu-id="ebf03-147">INPUTS</span></span>

### <span data-ttu-id="ebf03-148">System.Object</span><span class="sxs-lookup"><span data-stu-id="ebf03-148">System.Object</span></span>

<span data-ttu-id="ebf03-149">`Write-Information` 情報ストリームに渡すパイプされたオブジェクトを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="ebf03-149">`Write-Information` accepts piped objects to pass to the information stream.</span></span>

## <span data-ttu-id="ebf03-150">出力</span><span class="sxs-lookup"><span data-stu-id="ebf03-150">OUTPUTS</span></span>

### <span data-ttu-id="ebf03-151">システムの... InformationRecord</span><span class="sxs-lookup"><span data-stu-id="ebf03-151">System.Management.Automation.InformationRecord</span></span>

## <span data-ttu-id="ebf03-152">注</span><span class="sxs-lookup"><span data-stu-id="ebf03-152">NOTES</span></span>

## <span data-ttu-id="ebf03-153">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ebf03-153">RELATED LINKS</span></span>

[<span data-ttu-id="ebf03-154">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="ebf03-154">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="ebf03-155">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="ebf03-155">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="ebf03-156">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ebf03-156">about_CommonParameters</span></span>](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)

[<span data-ttu-id="ebf03-157">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="ebf03-157">about_Preference_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[<span data-ttu-id="ebf03-158">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="ebf03-158">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="ebf03-159">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="ebf03-159">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="ebf03-160">Write-Host</span><span class="sxs-lookup"><span data-stu-id="ebf03-160">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="ebf03-161">Write-Information</span><span class="sxs-lookup"><span data-stu-id="ebf03-161">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="ebf03-162">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="ebf03-162">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="ebf03-163">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="ebf03-163">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="ebf03-164">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="ebf03-164">Write-Warning</span></span>](Write-Warning.md)

[<span data-ttu-id="ebf03-165">Write-Output</span><span class="sxs-lookup"><span data-stu-id="ebf03-165">Write-Output</span></span>](Write-Output.md)
