---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/29/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-string?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-String
ms.openlocfilehash: a64b11206a0755cedabad2894ecc330fac95a8d5
ms.sourcegitcommit: c8d1ffeab215e74e87ea1b0af8cd606c1a6a80ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "93220136"
---
# <span data-ttu-id="5de2c-103">Out-String</span><span class="sxs-lookup"><span data-stu-id="5de2c-103">Out-String</span></span>

## <span data-ttu-id="5de2c-104">概要</span><span class="sxs-lookup"><span data-stu-id="5de2c-104">SYNOPSIS</span></span>
<span data-ttu-id="5de2c-105">入力オブジェクトを文字列として出力します。</span><span class="sxs-lookup"><span data-stu-id="5de2c-105">Outputs input objects as a strings.</span></span>

## <span data-ttu-id="5de2c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5de2c-106">SYNTAX</span></span>

### <span data-ttu-id="5de2c-107">None Wline書式設定 (既定)</span><span class="sxs-lookup"><span data-stu-id="5de2c-107">NoNewLineFormatting (Default)</span></span>

```
Out-String [-Width <Int32>] [-NoNewline] [-InputObject <PSObject>] [<CommonParameters>]
```

### <span data-ttu-id="5de2c-108">StreamFormatting 設定</span><span class="sxs-lookup"><span data-stu-id="5de2c-108">StreamFormatting</span></span>

```
Out-String [-Stream] [-Width <Int32>] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="5de2c-109">Description</span><span class="sxs-lookup"><span data-stu-id="5de2c-109">DESCRIPTION</span></span>

<span data-ttu-id="5de2c-110">`Out-String`コマンドレットは、入力オブジェクトを文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5de2c-110">The `Out-String` cmdlet converts input objects into strings.</span></span> <span data-ttu-id="5de2c-111">既定では、は `Out-String` 文字列を累積して1つの文字列として返しますが、 **Stream** パラメーターを使用して `Out-String` 、一度に1行を返すように指示したり、文字列の配列を作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5de2c-111">By default, `Out-String` accumulates the strings and returns them as a single string, but you can use the **Stream** parameter to direct `Out-String` to return one line at a time or create and array of strings.</span></span> <span data-ttu-id="5de2c-112">オブジェクトを簡単に操作できないときに、このコマンドレットを使用すると、従来のシェルで行う場合と同じように文字列出力を検索して操作することができます。</span><span class="sxs-lookup"><span data-stu-id="5de2c-112">This cmdlet lets you search and manipulate string output as you would in traditional shells when object manipulation is less convenient.</span></span>

## <span data-ttu-id="5de2c-113">例</span><span class="sxs-lookup"><span data-stu-id="5de2c-113">EXAMPLES</span></span>

### <span data-ttu-id="5de2c-114">例 1: 現在のカルチャを取得し、データを文字列に変換する</span><span class="sxs-lookup"><span data-stu-id="5de2c-114">Example 1: Get the current culture and convert the data to strings</span></span>

<span data-ttu-id="5de2c-115">この例では、現在のユーザーの地域設定を取得し、オブジェクトデータを文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5de2c-115">This example gets the regional settings for the current user and converts the object data to strings.</span></span>

```powershell
$C = Get-Culture | Select-Object -Property *
Out-String -InputObject $C -Width 100
```

```Output
Parent                         : en
LCID                           : 1033
KeyboardLayoutId               : 1033
Name                           : en-US
IetfLanguageTag                : en-US
DisplayName                    : English (United States)
NativeName                     : English (United States)
EnglishName                    : English (United States)
TwoLetterISOLanguageName       : en
ThreeLetterISOLanguageName     : eng
ThreeLetterWindowsLanguageName : ENU
CompareInfo                    : CompareInfo - en-US
TextInfo                       : TextInfo - en-US
IsNeutralCulture               : False
CultureTypes                   : SpecificCultures, InstalledWin32Cultures, FrameworkCultures
NumberFormat                   : System.Globalization.NumberFormatInfo
DateTimeFormat                 : System.Globalization.DateTimeFormatInfo
Calendar                       : System.Globalization.GregorianCalendar
OptionalCalendars              : {System.Globalization.GregorianCalendar,
                                 System.Globalization.GregorianCalendar}
UseUserOverride                : True
IsReadOnly                     : False
```

<span data-ttu-id="5de2c-116">`$C`変数にはSelected.System が格納され **ます。グローバリゼーション** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5de2c-116">The `$C` variable stores a **Selected.System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="5de2c-117">オブジェクトは、 `Get-Culture` パイプラインの出力をに送信した結果です `Select-Object` 。</span><span class="sxs-lookup"><span data-stu-id="5de2c-117">The object is the result of `Get-Culture` sending output down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="5de2c-118">**Property** パラメーターは、アスタリスク ( `*` ) ワイルドカードを使用して、オブジェクトに含まれるすべてのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="5de2c-118">The **Property** parameter uses an asterisk (`*`) wildcard to specify all properties are contained in the object.</span></span>

<span data-ttu-id="5de2c-119">`Out-String`**InputObject** パラメーターを使用して、変数に格納されている **CultureInfo** オブジェクトを指定し `$C` ます。</span><span class="sxs-lookup"><span data-stu-id="5de2c-119">`Out-String` uses the **InputObject** parameter to specify the **CultureInfo** object stored in the `$C` variable.</span></span> <span data-ttu-id="5de2c-120">内のオブジェクト `$C` は、文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="5de2c-120">The objects in `$C` are converted to a string.</span></span>

> [!NOTE]
> <span data-ttu-id="5de2c-121">配列を表示するには `Out-String` 、出力を変数に格納し、配列インデックスを使用して要素を表示します。</span><span class="sxs-lookup"><span data-stu-id="5de2c-121">To view the `Out-String` array, store the output to a variable and use an array index to view the elements.</span></span> <span data-ttu-id="5de2c-122">配列インデックスの詳細については、「 [about_Arrays](../microsoft.powershell.core/about/about_arrays.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5de2c-122">For more information about the array index, see [about_Arrays](../microsoft.powershell.core/about/about_arrays.md).</span></span>
>
> `$str = Out-String -InputObject $C -Width 100`

### <span data-ttu-id="5de2c-123">例 2: オブジェクトの操作</span><span class="sxs-lookup"><span data-stu-id="5de2c-123">Example 2: Working with objects</span></span>

<span data-ttu-id="5de2c-124">この例では、オブジェクトの使用と文字列の使用の違いを示します。</span><span class="sxs-lookup"><span data-stu-id="5de2c-124">This example demonstrates the difference between working with objects and working with strings.</span></span> <span data-ttu-id="5de2c-125">コマンドを実行すると、 **gcm** というテキストを含むエイリアスが表示され `Get-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="5de2c-125">The command displays an alias that includes the text **gcm** , the alias for `Get-Command`.</span></span>

```powershell
Get-Alias | Out-String -Stream | Select-String -Pattern "gcm"
```

```Output
Alias           gcm -> Get-Command
```

<span data-ttu-id="5de2c-126">`Get-Alias` 各エイリアスに対して1つずつ、 **システム管理のオートメーション** オブジェクトを取得し、そのオブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="5de2c-126">`Get-Alias` gets the **System.Management.Automation.AliasInfo** objects, one for each alias, and sends the objects down the pipeline.</span></span> <span data-ttu-id="5de2c-127">`Out-String`**Stream** パラメーターを使用して、すべてのオブジェクトを1つの文字列に連結するのではなく、各オブジェクトを文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5de2c-127">`Out-String` uses the **Stream** parameter to convert each object to a string rather concatenating all the objects into a single string.</span></span> <span data-ttu-id="5de2c-128">**System.string** オブジェクトはパイプラインを介して送信され、 `Select-String` **Pattern** パラメーターを使用してテキスト **gcm** の一致を検索します。</span><span class="sxs-lookup"><span data-stu-id="5de2c-128">The **System.String** objects are sent down the pipeline and `Select-String` uses the **Pattern** parameter to find matches for the text **gcm**.</span></span>

> [!NOTE]
> <span data-ttu-id="5de2c-129">**ストリーム** パラメーターを省略した場合、は `Select-String` を返す単一の文字列で **gcm** というテキストを検索するため、すべてのエイリアスがコマンドによって表示され `Out-String` ます。</span><span class="sxs-lookup"><span data-stu-id="5de2c-129">If you omit the **Stream** parameter, the command displays all the aliases because `Select-String` finds the text **gcm** in the single string that `Out-String` returns.</span></span>

### <span data-ttu-id="5de2c-130">例 3: Width パラメーターを使用して、切り捨てが行われないようにします。</span><span class="sxs-lookup"><span data-stu-id="5de2c-130">Example 3: Use the Width parameter to prevent truncation.</span></span>

<span data-ttu-id="5de2c-131">のほとんどの出力 `Out-String` は次の行にラップされますが、に渡される前に、書式設定システムによって出力が切り捨てられる場合があり `Out-String` ます。</span><span class="sxs-lookup"><span data-stu-id="5de2c-131">While most output from `Out-String` is wrapped to the next line, there are scenarios where the output is truncated by the formatting system before being passed to `Out-String`.</span></span> <span data-ttu-id="5de2c-132">**Width** パラメーターを使用して切り捨てを回避することができます。</span><span class="sxs-lookup"><span data-stu-id="5de2c-132">You can avoid truncation using the **Width** parameter.</span></span>

```powershell
PS> @{TestKey = ('x' * 200)} | Out-String
Name                           Value
----                           -----
TestKey                        xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx...

PS> @{TestKey = ('x' * 200)} | Out-String -Width 250

Name                           Value
----                           -----
TestKey                        xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

## <span data-ttu-id="5de2c-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5de2c-133">PARAMETERS</span></span>

### <span data-ttu-id="5de2c-134">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5de2c-134">-InputObject</span></span>

<span data-ttu-id="5de2c-135">文字列に書き込むオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="5de2c-135">Specifies the objects to be written to a string.</span></span> <span data-ttu-id="5de2c-136">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="5de2c-136">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="5de2c-137">-なし Wline</span><span class="sxs-lookup"><span data-stu-id="5de2c-137">-NoNewline</span></span>

<span data-ttu-id="5de2c-138">PowerShell フォーマッタによって生成された出力からすべての改行を削除します。</span><span class="sxs-lookup"><span data-stu-id="5de2c-138">Removes all newlines from output generated by the PowerShell formatter.</span></span> <span data-ttu-id="5de2c-139">文字列オブジェクトの一部である改行は保持されます。</span><span class="sxs-lookup"><span data-stu-id="5de2c-139">Newlines that are part of the string objects are preserved.</span></span>

<span data-ttu-id="5de2c-140">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5de2c-140">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoNewLineFormatting
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de2c-141">-ストリーム</span><span class="sxs-lookup"><span data-stu-id="5de2c-141">-Stream</span></span>

<span data-ttu-id="5de2c-142">コマンドレットが入力オブジェクトの各行に対して個別の文字列を送信することを示します。</span><span class="sxs-lookup"><span data-stu-id="5de2c-142">Indicates that the cmdlet sends a separate string for each line of an input object.</span></span> <span data-ttu-id="5de2c-143">既定では、各オブジェクトのための文字列が蓄積されて 1 つの文字列として送信されます。</span><span class="sxs-lookup"><span data-stu-id="5de2c-143">By default, the strings for each object are accumulated and sent as a single string.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StreamFormatting
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de2c-144">-Width</span><span class="sxs-lookup"><span data-stu-id="5de2c-144">-Width</span></span>

<span data-ttu-id="5de2c-145">出力の各行の文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="5de2c-145">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="5de2c-146">その他の文字は、使用されるフォーマッタコマンドレットに応じて、次の行に折り返されるか、または切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="5de2c-146">Any additional characters are wrapped to the next line or truncated depending on the formatter cmdlet used.</span></span> <span data-ttu-id="5de2c-147">**Width** パラメーターは、書式設定されているオブジェクトにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="5de2c-147">The **Width** parameter applies only to objects that are being formatted.</span></span> <span data-ttu-id="5de2c-148">このパラメーターを省略した場合、ホスト プログラムの特性によって幅が決まります。</span><span class="sxs-lookup"><span data-stu-id="5de2c-148">If you omit this parameter, the width is determined by the characteristics of the host program.</span></span> <span data-ttu-id="5de2c-149">ターミナル (コンソール) ウィンドウでは、現在のウィンドウの幅が既定値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="5de2c-149">In terminal (console) windows, the current window width is used as the default value.</span></span> <span data-ttu-id="5de2c-150">PowerShell コンソールウィンドウは、インストール時に既定で80文字の幅に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5de2c-150">PowerShell console windows default to a width of 80 characters on installation.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de2c-151">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5de2c-151">CommonParameters</span></span>

<span data-ttu-id="5de2c-152">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5de2c-152">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5de2c-153">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5de2c-153">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5de2c-154">入力</span><span class="sxs-lookup"><span data-stu-id="5de2c-154">INPUTS</span></span>

### <span data-ttu-id="5de2c-155">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="5de2c-155">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="5de2c-156">オブジェクトをパイプラインからに送信でき `Out-String` ます。</span><span class="sxs-lookup"><span data-stu-id="5de2c-156">You can send objects down the pipeline to `Out-String`.</span></span>

## <span data-ttu-id="5de2c-157">出力</span><span class="sxs-lookup"><span data-stu-id="5de2c-157">OUTPUTS</span></span>

### <span data-ttu-id="5de2c-158">System.String</span><span class="sxs-lookup"><span data-stu-id="5de2c-158">System.String</span></span>

<span data-ttu-id="5de2c-159">`Out-String` 入力オブジェクトから作成された文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="5de2c-159">`Out-String` returns the string that it creates from the input object.</span></span>

## <span data-ttu-id="5de2c-160">注</span><span class="sxs-lookup"><span data-stu-id="5de2c-160">NOTES</span></span>

<span data-ttu-id="5de2c-161">動詞を含むコマンドレットは、 `Out` オブジェクトを書式設定しません。</span><span class="sxs-lookup"><span data-stu-id="5de2c-161">The cmdlets that contain the `Out` verb don't format objects.</span></span> <span data-ttu-id="5de2c-162">`Out`コマンドレットは、指定された表示先のフォーマッタにオブジェクトを送信します。</span><span class="sxs-lookup"><span data-stu-id="5de2c-162">The `Out` cmdlets send objects to the formatter for the specified display destination.</span></span>

## <span data-ttu-id="5de2c-163">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5de2c-163">RELATED LINKS</span></span>

[<span data-ttu-id="5de2c-164">about_Formatting</span><span class="sxs-lookup"><span data-stu-id="5de2c-164">about_Formatting</span></span>](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[<span data-ttu-id="5de2c-165">Out-Default</span><span class="sxs-lookup"><span data-stu-id="5de2c-165">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="5de2c-166">Out-File</span><span class="sxs-lookup"><span data-stu-id="5de2c-166">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="5de2c-167">Out-Host</span><span class="sxs-lookup"><span data-stu-id="5de2c-167">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="5de2c-168">Out-Null</span><span class="sxs-lookup"><span data-stu-id="5de2c-168">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="5de2c-169">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="5de2c-169">Out-GridView</span></span>](Out-GridView.md)

[<span data-ttu-id="5de2c-170">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="5de2c-170">Out-Printer</span></span>](Out-Printer.md)
