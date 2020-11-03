---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-host?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Host
ms.openlocfilehash: f0b7542d551fa0dbbdec186980dcdb7ac600b60c
ms.sourcegitcommit: 758e6dbb428295698d4852b3e19f5d03deade037
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "93219936"
---
# <span data-ttu-id="5e9da-103">Write-Host</span><span class="sxs-lookup"><span data-stu-id="5e9da-103">Write-Host</span></span>

## <span data-ttu-id="5e9da-104">概要</span><span class="sxs-lookup"><span data-stu-id="5e9da-104">SYNOPSIS</span></span>

<span data-ttu-id="5e9da-105">カスタマイズした出力をホストに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="5e9da-105">Writes customized output to a host.</span></span>

## <span data-ttu-id="5e9da-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5e9da-106">SYNTAX</span></span>

```
Write-Host [[-Object] <Object>] [-NoNewline] [-Separator <Object>] [-ForegroundColor <ConsoleColor>]
 [-BackgroundColor <ConsoleColor>] [<CommonParameters>]
```

## <span data-ttu-id="5e9da-107">Description</span><span class="sxs-lookup"><span data-stu-id="5e9da-107">DESCRIPTION</span></span>

<span data-ttu-id="5e9da-108">`Write-Host`コマンドレットの主な目的は、-(ホスト) から表示専用の出力を生成することです。たとえば、[読み取りホスト](Read-Host.md)との組み合わせでユーザーに入力を求める場合などに色付きのテキストを印刷することができます。</span><span class="sxs-lookup"><span data-stu-id="5e9da-108">The `Write-Host` cmdlet's primary purpose is to produce for-(host)-display-only output, such as printing colored text like when prompting the user for input in conjunction with [Read-Host](Read-Host.md).</span></span>
<span data-ttu-id="5e9da-109">`Write-Host`[ToString ()](/dotnet/api/system.object.tostring)メソッドを使用して出力を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="5e9da-109">`Write-Host` uses the [ToString()](/dotnet/api/system.object.tostring) method to write the output.</span></span> <span data-ttu-id="5e9da-110">これに対し、パイプラインにデータを出力するには、 [書き込み出力](Write-Output.md) または暗黙の出力を使用します。</span><span class="sxs-lookup"><span data-stu-id="5e9da-110">By contrast, to output data to the pipeline, use [Write-Output](Write-Output.md) or implicit output.</span></span>

<span data-ttu-id="5e9da-111">パラメーターを使用してテキストの色を指定できます。また、パラメーターを使用して背景色を指定することもでき `ForegroundColor` `BackgroundColor` ます。</span><span class="sxs-lookup"><span data-stu-id="5e9da-111">You can specify the color of text by using the `ForegroundColor` parameter, and you can specify the background color by using the `BackgroundColor` parameter.</span></span> <span data-ttu-id="5e9da-112">Separator パラメーターを使用すると、個々の表示オブジェクトを区切るための文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5e9da-112">The Separator parameter lets you specify a string to use to separate displayed objects.</span></span> <span data-ttu-id="5e9da-113">具体的な結果は、PowerShell をホストしているプログラムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="5e9da-113">The particular result depends on the program that is hosting PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="5e9da-114">Windows PowerShell 5.0 以降では、を `Write-Host` 使用して、 `Write-Information` `Write-Host` 情報ストリームに出力を出力することができます。</span><span class="sxs-lookup"><span data-stu-id="5e9da-114">Starting in Windows PowerShell 5.0, `Write-Host` is a wrapper for `Write-Information` This allows you to use `Write-Host` to emit output to the information stream.</span></span> <span data-ttu-id="5e9da-115">これにより、後方互換性を維持しながら、を使用して書き込まれたデータを **キャプチャ** または **抑制** でき `Write-Host` ます。</span><span class="sxs-lookup"><span data-stu-id="5e9da-115">This enables the **capture** or **suppression** of data written using `Write-Host` while preserving backwards compatibility.</span></span>
>
> <span data-ttu-id="5e9da-116">ユーザー `$InformationPreference` 設定変数と `InformationAction` 共通パラメーターは、メッセージには影響しません `Write-Host` 。</span><span class="sxs-lookup"><span data-stu-id="5e9da-116">The `$InformationPreference` preference variable and `InformationAction` common parameter do not affect `Write-Host` messages.</span></span> <span data-ttu-id="5e9da-117">この規則の例外はです。これにより `-InformationAction Ignore` 、出力が実質的に抑制さ `Write-Host` れます。</span><span class="sxs-lookup"><span data-stu-id="5e9da-117">The exception to this rule is `-InformationAction Ignore`, which effectively suppresses `Write-Host` output.</span></span> <span data-ttu-id="5e9da-118">(「例5」を参照)</span><span class="sxs-lookup"><span data-stu-id="5e9da-118">(see "Example 5")</span></span>

## <span data-ttu-id="5e9da-119">例</span><span class="sxs-lookup"><span data-stu-id="5e9da-119">EXAMPLES</span></span>

### <span data-ttu-id="5e9da-120">例 1: 新しい行を追加せずにコンソールに書き込む</span><span class="sxs-lookup"><span data-stu-id="5e9da-120">Example 1: Write to the console without adding a new line</span></span>

```powershell
Write-Host "no newline test " -NoNewline
Write-Host "second string"
```

```output
no newline test second string
```

<span data-ttu-id="5e9da-121">このコマンドは、パラメーターを使用して "no 改行テスト" という文字列を表示し `NoNewline` ます。</span><span class="sxs-lookup"><span data-stu-id="5e9da-121">This command displays the string 'no newline test' with the `NoNewline` parameter.</span></span>

<span data-ttu-id="5e9da-122">2番目の文字列が書き込まれますが、文字列を区切る改行がないため、最初の文字列と同じ行に記述されます。</span><span class="sxs-lookup"><span data-stu-id="5e9da-122">A second string is written, but it ends up on the same line as the first due to the absence of a newline separating the strings.</span></span>

### <span data-ttu-id="5e9da-123">例 2: コンソールに書き込んで区切り記号を含める</span><span class="sxs-lookup"><span data-stu-id="5e9da-123">Example 2: Write to the console and include a separator</span></span>

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", +2= "
```

```output
2, +2= 4, +2= 6, +2= 8, +2= 10, +2= 12
```

このコマンドは、2 ~ 12 の偶数を表示します。 <span data-ttu-id="5e9da-125">**Separator** パラメーターを使用して、文字列 `, +2= ` (コンマ、スペース、、 `+` 、 `2` `=` 、スペース) を追加します。</span><span class="sxs-lookup"><span data-stu-id="5e9da-125">The **Separator** parameter is used to add the string `, +2= ` (comma, space, `+`, `2`, `=`, space).</span></span>

### <span data-ttu-id="5e9da-126">例 3: 異なるテキストと背景の色で記述する</span><span class="sxs-lookup"><span data-stu-id="5e9da-126">Example 3: Write with different text and background colors</span></span>

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", -> " -ForegroundColor DarkGreen -BackgroundColor White
```

```output
2, -> 4, -> 6, -> 8, -> 10, -> 12
```

<span data-ttu-id="5e9da-127">このコマンドは、2 ~ 12 の偶数を表示します。</span><span class="sxs-lookup"><span data-stu-id="5e9da-127">This command displays the even numbers from two through twelve.</span></span> <span data-ttu-id="5e9da-128">この例では、パラメーターを使用して `ForegroundColor` 濃い緑のテキストを出力し、パラメーターを使用して `BackgroundColor` 白い背景を表示しています。</span><span class="sxs-lookup"><span data-stu-id="5e9da-128">It uses the `ForegroundColor` parameter to output dark green text and the `BackgroundColor` parameter to display a white background.</span></span>

### <span data-ttu-id="5e9da-129">例 4: 異なるテキストと背景の色で記述する</span><span class="sxs-lookup"><span data-stu-id="5e9da-129">Example 4: Write with different text and background colors</span></span>

```powershell
Write-Host "Red on white text." -ForegroundColor red -BackgroundColor white
```

```output
Red on white text.
```

<span data-ttu-id="5e9da-130">このコマンドは、文字列 "Red on white text" を表示します。</span><span class="sxs-lookup"><span data-stu-id="5e9da-130">This command displays the string "Red on white text."</span></span> <span data-ttu-id="5e9da-131">テキストは、パラメーターで定義されているように、赤色で表示され `ForegroundColor` ます。</span><span class="sxs-lookup"><span data-stu-id="5e9da-131">The text is red, as defined by the `ForegroundColor` parameter.</span></span> <span data-ttu-id="5e9da-132">背景は、パラメーターで定義されているように白に `BackgroundColor` なります。</span><span class="sxs-lookup"><span data-stu-id="5e9da-132">The background is white, as defined by the `BackgroundColor` parameter.</span></span>

### <span data-ttu-id="5e9da-133">例 5: Write-Host からの出力を抑制する</span><span class="sxs-lookup"><span data-stu-id="5e9da-133">Example 5: Suppress output from Write-Host</span></span>

```powershell
# The following two statements can be used to effectively suppress output from Write-Host
Write-Host "I won't print" -InformationAction Ignore
Write-Host "I won't print" 6>$null
```

```output

```

<span data-ttu-id="5e9da-134">これらのコマンドは、コマンドレットの出力を効果的に抑制 `Write-Host` します。</span><span class="sxs-lookup"><span data-stu-id="5e9da-134">These commands effectively suppress output of the `Write-Host` cmdlet.</span></span> <span data-ttu-id="5e9da-135">最初の例では、パラメーターを値と共に使用して、 `InformationAction` `Ignore` 情報ストリームへの出力を抑制しています。</span><span class="sxs-lookup"><span data-stu-id="5e9da-135">The first one uses the `InformationAction` parameter with the `Ignore` Value to suppress output to the information stream.</span></span>
<span data-ttu-id="5e9da-136">2番目の例では、コマンドの情報ストリームを変数にリダイレクト `$null` し、その結果を抑制します。</span><span class="sxs-lookup"><span data-stu-id="5e9da-136">The second example redirects the information stream of the command to the `$null` variable and thereby suppresses it.</span></span>

## <span data-ttu-id="5e9da-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5e9da-137">PARAMETERS</span></span>

### <span data-ttu-id="5e9da-138">-BackgroundColor</span><span class="sxs-lookup"><span data-stu-id="5e9da-138">-BackgroundColor</span></span>

<span data-ttu-id="5e9da-139">背景色を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e9da-139">Specifies the background color.</span></span> <span data-ttu-id="5e9da-140">既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="5e9da-140">There is no default.</span></span> <span data-ttu-id="5e9da-141">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5e9da-141">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5e9da-142">Black</span><span class="sxs-lookup"><span data-stu-id="5e9da-142">Black</span></span>
- <span data-ttu-id="5e9da-143">濃い青</span><span class="sxs-lookup"><span data-stu-id="5e9da-143">DarkBlue</span></span>
- <span data-ttu-id="5e9da-144">濃い緑</span><span class="sxs-lookup"><span data-stu-id="5e9da-144">DarkGreen</span></span>
- <span data-ttu-id="5e9da-145">濃いシアン</span><span class="sxs-lookup"><span data-stu-id="5e9da-145">DarkCyan</span></span>
- <span data-ttu-id="5e9da-146">濃い赤</span><span class="sxs-lookup"><span data-stu-id="5e9da-146">DarkRed</span></span>
- <span data-ttu-id="5e9da-147">濃いマゼンタ</span><span class="sxs-lookup"><span data-stu-id="5e9da-147">DarkMagenta</span></span>
- <span data-ttu-id="5e9da-148">濃い黄色</span><span class="sxs-lookup"><span data-stu-id="5e9da-148">DarkYellow</span></span>
- <span data-ttu-id="5e9da-149">グレー</span><span class="sxs-lookup"><span data-stu-id="5e9da-149">Gray</span></span>
- <span data-ttu-id="5e9da-150">濃い灰色</span><span class="sxs-lookup"><span data-stu-id="5e9da-150">DarkGray</span></span>
- <span data-ttu-id="5e9da-151">青</span><span class="sxs-lookup"><span data-stu-id="5e9da-151">Blue</span></span>
- <span data-ttu-id="5e9da-152">[緑]</span><span class="sxs-lookup"><span data-stu-id="5e9da-152">Green</span></span>
- <span data-ttu-id="5e9da-153">シアン</span><span class="sxs-lookup"><span data-stu-id="5e9da-153">Cyan</span></span>
- <span data-ttu-id="5e9da-154">[赤]</span><span class="sxs-lookup"><span data-stu-id="5e9da-154">Red</span></span>
- <span data-ttu-id="5e9da-155">赤紫</span><span class="sxs-lookup"><span data-stu-id="5e9da-155">Magenta</span></span>
- <span data-ttu-id="5e9da-156">黄</span><span class="sxs-lookup"><span data-stu-id="5e9da-156">Yellow</span></span>
- <span data-ttu-id="5e9da-157">White</span><span class="sxs-lookup"><span data-stu-id="5e9da-157">White</span></span>

```yaml
Type: System.ConsoleColor
Parameter Sets: (All)
Aliases:
Accepted values: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9da-158">-ForegroundColor</span><span class="sxs-lookup"><span data-stu-id="5e9da-158">-ForegroundColor</span></span>

<span data-ttu-id="5e9da-159">文字の色を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e9da-159">Specifies the text color.</span></span> <span data-ttu-id="5e9da-160">既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="5e9da-160">There is no default.</span></span> <span data-ttu-id="5e9da-161">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5e9da-161">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5e9da-162">Black</span><span class="sxs-lookup"><span data-stu-id="5e9da-162">Black</span></span>
- <span data-ttu-id="5e9da-163">濃い青</span><span class="sxs-lookup"><span data-stu-id="5e9da-163">DarkBlue</span></span>
- <span data-ttu-id="5e9da-164">濃い緑</span><span class="sxs-lookup"><span data-stu-id="5e9da-164">DarkGreen</span></span>
- <span data-ttu-id="5e9da-165">濃いシアン</span><span class="sxs-lookup"><span data-stu-id="5e9da-165">DarkCyan</span></span>
- <span data-ttu-id="5e9da-166">濃い赤</span><span class="sxs-lookup"><span data-stu-id="5e9da-166">DarkRed</span></span>
- <span data-ttu-id="5e9da-167">濃いマゼンタ</span><span class="sxs-lookup"><span data-stu-id="5e9da-167">DarkMagenta</span></span>
- <span data-ttu-id="5e9da-168">濃い黄色</span><span class="sxs-lookup"><span data-stu-id="5e9da-168">DarkYellow</span></span>
- <span data-ttu-id="5e9da-169">グレー</span><span class="sxs-lookup"><span data-stu-id="5e9da-169">Gray</span></span>
- <span data-ttu-id="5e9da-170">濃い灰色</span><span class="sxs-lookup"><span data-stu-id="5e9da-170">DarkGray</span></span>
- <span data-ttu-id="5e9da-171">青</span><span class="sxs-lookup"><span data-stu-id="5e9da-171">Blue</span></span>
- <span data-ttu-id="5e9da-172">[緑]</span><span class="sxs-lookup"><span data-stu-id="5e9da-172">Green</span></span>
- <span data-ttu-id="5e9da-173">シアン</span><span class="sxs-lookup"><span data-stu-id="5e9da-173">Cyan</span></span>
- <span data-ttu-id="5e9da-174">[赤]</span><span class="sxs-lookup"><span data-stu-id="5e9da-174">Red</span></span>
- <span data-ttu-id="5e9da-175">赤紫</span><span class="sxs-lookup"><span data-stu-id="5e9da-175">Magenta</span></span>
- <span data-ttu-id="5e9da-176">黄</span><span class="sxs-lookup"><span data-stu-id="5e9da-176">Yellow</span></span>
- <span data-ttu-id="5e9da-177">White</span><span class="sxs-lookup"><span data-stu-id="5e9da-177">White</span></span>

```yaml
Type: System.ConsoleColor
Parameter Sets: (All)
Aliases:
Accepted values: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9da-178">-なし Wline</span><span class="sxs-lookup"><span data-stu-id="5e9da-178">-NoNewline</span></span>

<span data-ttu-id="5e9da-179">入力オブジェクトの文字列形式が連結され、出力が形成されます。</span><span class="sxs-lookup"><span data-stu-id="5e9da-179">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="5e9da-180">出力文字列間にスペースや改行は挿入されません。</span><span class="sxs-lookup"><span data-stu-id="5e9da-180">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="5e9da-181">最後の出力文字列の後に改行は追加されません。</span><span class="sxs-lookup"><span data-stu-id="5e9da-181">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="5e9da-182">-オブジェクト</span><span class="sxs-lookup"><span data-stu-id="5e9da-182">-Object</span></span>

<span data-ttu-id="5e9da-183">ホストに表示するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5e9da-183">Objects to display in the host.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Msg, Message

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5e9da-184">-Separator</span><span class="sxs-lookup"><span data-stu-id="5e9da-184">-Separator</span></span>

<span data-ttu-id="5e9da-185">ホストによって表示されるオブジェクト間に挿入する区切り文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e9da-185">Specifies a separator string to insert between objects displayed by the host.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5e9da-186">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e9da-186">CommonParameters</span></span>
<span data-ttu-id="5e9da-187">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5e9da-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5e9da-188">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e9da-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5e9da-189">入力</span><span class="sxs-lookup"><span data-stu-id="5e9da-189">INPUTS</span></span>

### <span data-ttu-id="5e9da-190">System.Object</span><span class="sxs-lookup"><span data-stu-id="5e9da-190">System.Object</span></span>

<span data-ttu-id="5e9da-191">ホストに書き込むオブジェクトはパイプ処理で渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="5e9da-191">You can pipe objects to be written to the host.</span></span>

## <span data-ttu-id="5e9da-192">出力</span><span class="sxs-lookup"><span data-stu-id="5e9da-192">OUTPUTS</span></span>

### <span data-ttu-id="5e9da-193">なし</span><span class="sxs-lookup"><span data-stu-id="5e9da-193">None</span></span>

<span data-ttu-id="5e9da-194">`Write-Host` オブジェクトをホストに送信します。</span><span class="sxs-lookup"><span data-stu-id="5e9da-194">`Write-Host` sends the objects to the host.</span></span> <span data-ttu-id="5e9da-195">このコマンドはオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="5e9da-195">It does not return any objects.</span></span> <span data-ttu-id="5e9da-196">ただし、ホストは、に送信するオブジェクトを表示し `Write-Host` ます。</span><span class="sxs-lookup"><span data-stu-id="5e9da-196">However, the host displays the objects that `Write-Host` sends to it.</span></span>

## <span data-ttu-id="5e9da-197">注</span><span class="sxs-lookup"><span data-stu-id="5e9da-197">NOTES</span></span>

- <span data-ttu-id="5e9da-198">コレクションをホストに書き込む場合、コレクションの要素は、1つの空白で区切られた同じ行に出力されます。</span><span class="sxs-lookup"><span data-stu-id="5e9da-198">When writing a collection to the host, elements of the collection are printed on the same line separated by a single space.</span></span> <span data-ttu-id="5e9da-199">これは、 **Separator** パラメーターを使用してオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="5e9da-199">This can be overridden with the **Separator** parameter.</span></span>

- <span data-ttu-id="5e9da-200">プロパティを持つオブジェクトなどの非プリミティブデータ型では、予期しない結果が発生し、意味のある出力が得られない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5e9da-200">Non-primitive data types such as objects with properties can cause unexpected results and not provide meaningful output.</span></span> <span data-ttu-id="5e9da-201">たとえば、 `Write-Host @{a = 1; b = 2}` は `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` ホストに出力します。</span><span class="sxs-lookup"><span data-stu-id="5e9da-201">For example, `Write-Host @{a = 1; b = 2}` will print `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` to the host.</span></span>

## <span data-ttu-id="5e9da-202">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5e9da-202">RELATED LINKS</span></span>

[<span data-ttu-id="5e9da-203">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="5e9da-203">Clear-Host</span></span>](../Microsoft.PowerShell.Core/Clear-Host.md)

[<span data-ttu-id="5e9da-204">Out-Host</span><span class="sxs-lookup"><span data-stu-id="5e9da-204">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="5e9da-205">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="5e9da-205">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="5e9da-206">書き込み-エラー</span><span class="sxs-lookup"><span data-stu-id="5e9da-206">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="5e9da-207">Write-Output</span><span class="sxs-lookup"><span data-stu-id="5e9da-207">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="5e9da-208">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="5e9da-208">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="5e9da-209">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="5e9da-209">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="5e9da-210">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="5e9da-210">Write-Warning</span></span>](Write-Warning.md)
