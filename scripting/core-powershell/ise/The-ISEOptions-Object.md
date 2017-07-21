---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "ISEOptions オブジェクト"
ms.assetid: 75e2a76f-f3d1-490b-ad5d-e3829946aabb
ms.openlocfilehash: 56bdd5999b46b6e29e762c2d9a2060cebe3a1299
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="the-iseoptions-object"></a><span data-ttu-id="de407-103">ISEOptions オブジェクト</span><span class="sxs-lookup"><span data-stu-id="de407-103">The ISEOptions Object</span></span>
  <span data-ttu-id="de407-104">**ISEOptions** オブジェクトは、Windows PowerShell ISE のさまざまな設定を表します。</span><span class="sxs-lookup"><span data-stu-id="de407-104">The **ISEOptions** object represents various settings for Windows PowerShell ISE.</span></span> <span data-ttu-id="de407-105">これは **Microsoft.PowerShell.Host.ISE.ISEOptions** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="de407-105">It is an instance of the **Microsoft.PowerShell.Host.ISE.ISEOptions** class.</span></span>

 <span data-ttu-id="de407-106">**ISEOptions** オブジェクトは、次のメソッドとプロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="de407-106">The **ISEOptions** object provides the following methods and properties.</span></span>

 <span data-ttu-id="de407-107">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="de407-107">**Methods**</span></span>

-   [<span data-ttu-id="de407-108">RestoreDefaultConsoleTokenColors()</span><span class="sxs-lookup"><span data-stu-id="de407-108">RestoreDefaultConsoleTokenColors()</span></span>](#rdctc)

-   [<span data-ttu-id="de407-109">RestoreDefaults()</span><span class="sxs-lookup"><span data-stu-id="de407-109">RestoreDefaults()</span></span>](#rd)

-   [<span data-ttu-id="de407-110">RestoreDefaultTokenColors()</span><span class="sxs-lookup"><span data-stu-id="de407-110">RestoreDefaultTokenColors()</span></span>](#rdtc)

-   [<span data-ttu-id="de407-111">RestoreDefaultXmlTokenColors()</span><span class="sxs-lookup"><span data-stu-id="de407-111">RestoreDefaultXmlTokenColors()</span></span>](#rdxtc)

 <span data-ttu-id="de407-112">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="de407-112">**Properties**</span></span>

-   [<span data-ttu-id="de407-113">AutoSaveMinuteInterval</span><span class="sxs-lookup"><span data-stu-id="de407-113">AutoSaveMinuteInterval</span></span>](#asmi)

-   [<span data-ttu-id="de407-114">CommandPaneBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-114">CommandPaneBackgroundColor</span></span>](#cpbc)

-   [<span data-ttu-id="de407-115">CommandPaneUp</span><span class="sxs-lookup"><span data-stu-id="de407-115">CommandPaneUp</span></span>](#cpu)

-   [<span data-ttu-id="de407-116">ConsolePaneBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-116">ConsolePaneBackgroundColor</span></span>](#conpbc)

-   [<span data-ttu-id="de407-117">ConsolePaneForegroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-117">ConsolePaneForegroundColor</span></span>](#conpfc)

-   [<span data-ttu-id="de407-118">ConsolePaneTextBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-118">ConsolePaneTextBackgroundColor</span></span>](#conptbc)

-   [<span data-ttu-id="de407-119">ConsoleTokenColors</span><span class="sxs-lookup"><span data-stu-id="de407-119">ConsoleTokenColors</span></span>](#contc)

-   [<span data-ttu-id="de407-120">DebugBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-120">DebugBackgroundColor</span></span>](#dbc)

-   [<span data-ttu-id="de407-121">DebugForegroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-121">DebugForegroundColor</span></span>](#dfc)

-   [<span data-ttu-id="de407-122">DefaultOptions</span><span class="sxs-lookup"><span data-stu-id="de407-122">DefaultOptions</span></span>](#do)

-   [<span data-ttu-id="de407-123">ErrorBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-123">ErrorBackgroundColor</span></span>](#ebc)

-   [<span data-ttu-id="de407-124">ErrorForegroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-124">ErrorForegroundColor</span></span>](#efc)

-   [<span data-ttu-id="de407-125">FontName</span><span class="sxs-lookup"><span data-stu-id="de407-125">FontName</span></span>](#fn)

-   [<span data-ttu-id="de407-126">FontSize</span><span class="sxs-lookup"><span data-stu-id="de407-126">FontSize</span></span>](#fs)

-   [<span data-ttu-id="de407-127">IntellisenseTimeoutInSeconds</span><span class="sxs-lookup"><span data-stu-id="de407-127">IntellisenseTimeoutInSeconds</span></span>](#itis)

-   [<span data-ttu-id="de407-128">MruCount</span><span class="sxs-lookup"><span data-stu-id="de407-128">MruCount</span></span>](#mc)

-   [<span data-ttu-id="de407-129">OutputPaneBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-129">OutputPaneBackgroundColor</span></span>](#opbc)

-   [<span data-ttu-id="de407-130">OutputPaneTextForegroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-130">OutputPaneTextForegroundColor</span></span>](#optfc)

-   [<span data-ttu-id="de407-131">OutputPaneTextBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-131">OutputPaneTextBackgroundColor</span></span>](#optbc)

-   [<span data-ttu-id="de407-132">ScriptPaneBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-132">ScriptPaneBackgroundColor</span></span>](#spbc)

-   [<span data-ttu-id="de407-133">ScriptPaneForegroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-133">ScriptPaneForegroundColor</span></span>](#spfc)

-   [<span data-ttu-id="de407-134">SelectedScriptPaneState</span><span class="sxs-lookup"><span data-stu-id="de407-134">SelectedScriptPaneState</span></span>](#ssps)

-   [<span data-ttu-id="de407-135">ShowDefaultSnippets</span><span class="sxs-lookup"><span data-stu-id="de407-135">ShowDefaultSnippets</span></span>](#sds)

-   [<span data-ttu-id="de407-136">ShowIntellisenseInConsolePane</span><span class="sxs-lookup"><span data-stu-id="de407-136">ShowIntellisenseInConsolePane</span></span>](#siicp)

-   [<span data-ttu-id="de407-137">ShowIntellisenseInScriptPane</span><span class="sxs-lookup"><span data-stu-id="de407-137">ShowIntellisenseInScriptPane</span></span>](#siisp)

-   [<span data-ttu-id="de407-138">ShowLineNumbers</span><span class="sxs-lookup"><span data-stu-id="de407-138">ShowLineNumbers</span></span>](#sln)

-   [<span data-ttu-id="de407-139">ShowOutlining</span><span class="sxs-lookup"><span data-stu-id="de407-139">ShowOutlining</span></span>](#so)

-   [<span data-ttu-id="de407-140">ShowToolBar</span><span class="sxs-lookup"><span data-stu-id="de407-140">ShowToolBar</span></span>](#stb)

-   [<span data-ttu-id="de407-141">ShowWarningBeforeSavingOnRun</span><span class="sxs-lookup"><span data-stu-id="de407-141">ShowWarningBeforeSavingOnRun</span></span>](#swbsor)

-   [<span data-ttu-id="de407-142">ShowWarningForDuplicateFiles</span><span class="sxs-lookup"><span data-stu-id="de407-142">ShowWarningForDuplicateFiles</span></span>](#swfdf)

-   [<span data-ttu-id="de407-143">TokenColors</span><span class="sxs-lookup"><span data-stu-id="de407-143">TokenColors</span></span>](#tc)

-   [<span data-ttu-id="de407-144">UseEnterToSelectInConsolePaneIntellisense</span><span class="sxs-lookup"><span data-stu-id="de407-144">UseEnterToSelectInConsolePaneIntellisense</span></span>](#uetsicpi)

-   [<span data-ttu-id="de407-145">UseEnterToSelectInScriptPaneIntellisense</span><span class="sxs-lookup"><span data-stu-id="de407-145">UseEnterToSelectInScriptPaneIntellisense</span></span>](#uetsispi)

-   [<span data-ttu-id="de407-146">UseLocalHelp</span><span class="sxs-lookup"><span data-stu-id="de407-146">UseLocalHelp</span></span>](#ulh)

-   [<span data-ttu-id="de407-147">VerboseBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-147">VerboseBackgroundColor</span></span>](#vbc)

-   [<span data-ttu-id="de407-148">VerboseForegroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-148">VerboseForegroundColor</span></span>](#vfc)

-   [<span data-ttu-id="de407-149">WarningBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-149">WarningBackgroundColor</span></span>](#wbc)

-   [<span data-ttu-id="de407-150">WarningForegroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-150">WarningForegroundColor</span></span>](#wfc)

-   [<span data-ttu-id="de407-151">XmlTokenColors</span><span class="sxs-lookup"><span data-stu-id="de407-151">XmlTokenColors</span></span>](#xtc)

-   [<span data-ttu-id="de407-152">Zoom</span><span class="sxs-lookup"><span data-stu-id="de407-152">Zoom</span></span>](#z)

## <a name="methods"></a><span data-ttu-id="de407-153">メソッド</span><span class="sxs-lookup"><span data-stu-id="de407-153">Methods</span></span>

###  <span data-ttu-id="de407-154"><a name="rdctc"></a> RestoreDefaultConsoleTokenColors\(\)</span><span class="sxs-lookup"><span data-stu-id="de407-154"><a name="rdctc"></a> RestoreDefaultConsoleTokenColors\(\)</span></span>
  <span data-ttu-id="de407-155">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-155">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-156">コンソール ウィンドウのトークンの色の既定値を復元します。</span><span class="sxs-lookup"><span data-stu-id="de407-156">Restores the default values of the token colors in the Console pane.</span></span>

```
# Changes the color of the commands in the Console pane to red and then restores it to its default value.
$psISE.Options.ConsoleTokenColors["Command"] = "red"
$psISE.Options.RestoreDefaultConsoleTokenColors()
```

###  <span data-ttu-id="de407-157"><a name="rd"></a> RestoreDefaults\(\)</span><span class="sxs-lookup"><span data-stu-id="de407-157"><a name="rd"></a> RestoreDefaults\(\)</span></span>
  <span data-ttu-id="de407-158">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-158">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-159">コンソール ウィンドウのすべてのオプション設定の既定値を復元します。</span><span class="sxs-lookup"><span data-stu-id="de407-159">Restores the default values of all options settings in the Console pane.</span></span> <span data-ttu-id="de407-160">メッセージが再度表示されることを防ぐため、標準のチェック ボックスを提供する各種の警告メッセージの動作もリセットされます。</span><span class="sxs-lookup"><span data-stu-id="de407-160">It also resets the behavior of various warning messages that provide the standard check box to prevent the message from being shown again.</span></span>

```
# Changes the background color in the Console pane and then restores it to its default value.
$psISE.Options.ConsolePaneBackgroundColor = "orange"
$psISE.Options.RestoreDefaults()
```

###  <span data-ttu-id="de407-161"><a name="rdtc"></a> RestoreDefaultTokenColors\(\)</span><span class="sxs-lookup"><span data-stu-id="de407-161"><a name="rdtc"></a> RestoreDefaultTokenColors\(\)</span></span>
  <span data-ttu-id="de407-162">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-162">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-163">スクリプト ウィンドウのトークンの色の既定値を復元します。</span><span class="sxs-lookup"><span data-stu-id="de407-163">Restores the default values of the token colors in the Script pane.</span></span>

```
# Changes the color of the comments in the Script pane to red and then restores it to its default value.
$psISE.Options.TokenColors["Comment"]="red"
$psISE.Options.RestoreDefaultTokenColors()
```

###  <span data-ttu-id="de407-164"><a name="rdxtc"></a> RestoreDefaultXmlTokenColors\(\)</span><span class="sxs-lookup"><span data-stu-id="de407-164"><a name="rdxtc"></a> RestoreDefaultXmlTokenColors\(\)</span></span>
  <span data-ttu-id="de407-165">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-165">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-166">Windows PowerShell ISE で表示される XML 要素のトークンの色の既定値を復元します。</span><span class="sxs-lookup"><span data-stu-id="de407-166">Restores the default values of the token colors for XML elements that are displayed in Windows PowerShell ISE.</span></span> <span data-ttu-id="de407-167">[XmlTokenColors](#xtc) も参照してください。</span><span class="sxs-lookup"><span data-stu-id="de407-167">Also see [XmlTokenColors](#xtc).</span></span>

```
# Changes the color of the comments in XML data to red and then restores it to its default value.
$psISE.Options.XmlTokenColors["Comment"]="red"
$psISE.Options.RestoreDefaultXmlTokenColors()
```

## <a name="properties"></a><span data-ttu-id="de407-168">プロパティ</span><span class="sxs-lookup"><span data-stu-id="de407-168">Properties</span></span>

###  <span data-ttu-id="de407-169"><a name="asmi"></a> AutoSaveMinuteInterval</span><span class="sxs-lookup"><span data-stu-id="de407-169"><a name="asmi"></a> AutoSaveMinuteInterval</span></span>
  <span data-ttu-id="de407-170">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-170">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-171">Windows PowerShell ISE によるファイルの自動保存の処理間隔を分単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-171">Specifies the number of minutes between automatic save operations of your files by Windows PowerShell ISE.</span></span> <span data-ttu-id="de407-172">既定値は 2 分です。</span><span class="sxs-lookup"><span data-stu-id="de407-172">The default value is 2 minutes.</span></span> <span data-ttu-id="de407-173">値は整数です。</span><span class="sxs-lookup"><span data-stu-id="de407-173">The value is an integer.</span></span>

```
# Changes the number of minutes between automatic save operations to every 3 minutes.
$psISE.Options.AutoSaveMinuteInterval = 3
```

###  <span data-ttu-id="de407-174"><a name="cpbc"></a> CommandPaneBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-174"><a name="cpbc"></a> CommandPaneBackgroundColor</span></span>
  <span data-ttu-id="de407-175">この機能は、Windows PowerShell ISE 2.0 に存在しますが、それよりも後のバージョンの ISE では削除されているか、名前が変更されています。</span><span class="sxs-lookup"><span data-stu-id="de407-175">This feature is present in Windows PowerShell ISE 2.0, but was removed or renamed in later versions of the ISE.</span></span>  <span data-ttu-id="de407-176">後のバージョンについては、[ConsolePaneBackgroundColor](#conpbc) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de407-176">For later versions, see [ConsolePaneBackgroundColor](#conpbc).</span></span>

 <span data-ttu-id="de407-177">コマンド ウィンドウの背景色を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-177">Specifies the background color for the Command pane.</span></span> <span data-ttu-id="de407-178">これは **System.Windows.Media.Color** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="de407-178">It is an instance of the **System.Windows.Media.Color** class.</span></span>

```
# Changes the background color of the Command pane to orange.
$psISE.Options.CommandPaneBackgroundColor = "orange"
```

###  <span data-ttu-id="de407-179"><a name="cpu"></a> CommandPaneUp</span><span class="sxs-lookup"><span data-stu-id="de407-179"><a name="cpu"></a> CommandPaneUp</span></span>
  <span data-ttu-id="de407-180">この機能は、Windows PowerShell ISE 2.0 に存在しますが、それよりも後のバージョンの ISE では削除されているか、名前が変更されています。</span><span class="sxs-lookup"><span data-stu-id="de407-180">This feature is present in Windows PowerShell ISE 2.0, but was removed or renamed in later versions of the ISE.</span></span>

 <span data-ttu-id="de407-181">コマンド ウィンドウを出力ウィンドウの上に配置するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-181">Specifies whether the Command pane is located above the Output pane.</span></span>

```
# Moves the Command pane to the top of the screen.
$psISE.Options.CommandPaneUp  = $true

```

###  <span data-ttu-id="de407-182"><a name="conpbc"></a> ConsolePaneBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-182"><a name="conpbc"></a> ConsolePaneBackgroundColor</span></span>
  <span data-ttu-id="de407-183">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-183">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-184">コンソール ウィンドウの背景色を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-184">Specifies the background color for the Console pane.</span></span> <span data-ttu-id="de407-185">これは **System.Windows.Media.Color** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="de407-185">It is an instance of the **System.Windows.Media.Color** class.</span></span>

```
# Changes the background color of the Console pane to red.
$psISE.Options.ConsolePaneBackgroundColor = "red"
```

###  <span data-ttu-id="de407-186"><a name="conpfc"></a> ConsolePaneForegroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-186"><a name="conpfc"></a> ConsolePaneForegroundColor</span></span>
  <span data-ttu-id="de407-187">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-187">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-188">コンソール ウィンドウのテキストの前景色を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-188">Specifies the foreground color of the text in the Console pane.</span></span>

```
# Changes the foreground color of the text in the Console pane to yellow.
$psISE.Options.ConsolePaneForegroundColor  = "yellow"

```

###  <span data-ttu-id="de407-189"><a name="conptbc"></a> ConsolePaneTextBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-189"><a name="conptbc"></a> ConsolePaneTextBackgroundColor</span></span>
  <span data-ttu-id="de407-190">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-190">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-191">コンソール ウィンドウのテキストの背景色を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-191">Specifies the background color of the text in the Console pane.</span></span>

```
# Changes the background color of the Console pane text to pink.
$psISE.Options.ConsolePaneTextBackgroundColor = "pink"
```

###  <span data-ttu-id="de407-192"><a name="contc"></a> ConsoleTokenColors</span><span class="sxs-lookup"><span data-stu-id="de407-192"><a name="contc"></a> ConsoleTokenColors</span></span>
  <span data-ttu-id="de407-193">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-193">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-194">Windows PowerShell ISE のコンソール ウィンドウの IntelliSense のトークンの色を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-194">Specifies the colors of the IntelliSense tokens in the Windows PowerShell ISE Console pane.</span></span> <span data-ttu-id="de407-195">このプロパティは、コンソール ウィンドウのトークンの種類と色の名前/値のペアを含むディクショナリ オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="de407-195">This property is a dictionary object that contains name/value pairs of token types and colors for the Console pane.</span></span> <span data-ttu-id="de407-196">スクリプト ウィンドウで IntelliSense トークンの色を変更する場合は、[TokenColors](#tc) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de407-196">To change the colors of the IntelliSense tokens in the Script pane, see [TokenColors](#tc).</span></span> <span data-ttu-id="de407-197">色を既定値にリセットする場合、[RestoreDefaultConsoleTokenColors()](#rdctc) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de407-197">To reset the colors to the default values, see [RestoreDefaultConsoleTokenColors()](#rdctc).</span></span> <span data-ttu-id="de407-198">次のトークンの色を設定することができます: Attribute、Command、CommandArgument、CommandParameter、Comment、GroupEnd、GroupStart、Keyword、LineContinuation、LoopLabel、Member、NewLine、Number、Operator、Position、StatementSeparator、String、Type、Unknown、Variable。</span><span class="sxs-lookup"><span data-stu-id="de407-198">Token colors can be set for the following: Attribute, Command, CommandArgument, CommandParameter, Comment, GroupEnd, GroupStart, Keyword, LineContinuation, LoopLabel, Member, NewLine, Number, Operator, Position, StatementSeparator, String, Type, Unknown, Variable.</span></span>

```
# Sets the color of commands to green.
$psISE.Options.ConsoleTokenColors["Command"] = "green"
# Sets the color of keywords to magenta.
$psISE.Options.ConsoleTokenColors["Keyword"] = "magenta"

```

###  <span data-ttu-id="de407-199"><a name="dbc"></a> DebugBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-199"><a name="dbc"></a> DebugBackgroundColor</span></span>
  <span data-ttu-id="de407-200">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-200">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-201">コンソール ウィンドウに表示されるデバッグ テキストの背景色を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-201">Specifies the background color for the debug text that appears in the Console pane.</span></span> <span data-ttu-id="de407-202">これは **System.Windows.Media.Color** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="de407-202">It is an instance of the **System.Windows.Media.Color** class.</span></span>

```
# Changes the background color for the debug text that appears in the Console pane to blue.
$psISE.Options.DebugBackgroundColor ='#0000FF'
```

###  <span data-ttu-id="de407-203"><a name="dfc"></a> DebugForegroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-203"><a name="dfc"></a> DebugForegroundColor</span></span>
  <span data-ttu-id="de407-204">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-204">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-205">コンソール ウィンドウに表示されるデバッグ テキストの前景色を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-205">Specifies the foreground color for the debug text that appears in the Console pane.</span></span> <span data-ttu-id="de407-206">これは **System.Windows.Media.Color** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="de407-206">It is an instance of the **System.Windows.Media.Color** class.</span></span>

```
# Changes the foreground color for the debug text that appears in the Console pane to yellow.
$psISE.Options.DebugForegroundColor ="yellow"
```

###  <span data-ttu-id="de407-207"><a name="do"></a> DefaultOptions</span><span class="sxs-lookup"><span data-stu-id="de407-207"><a name="do"></a> DefaultOptions</span></span>
  <span data-ttu-id="de407-208">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-208">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-209">Reset メソッドを使用する場合に使用する既定値を指定するプロパティのコレクション。</span><span class="sxs-lookup"><span data-stu-id="de407-209">A collection of properties that specify the default values to be used when the Reset methods are used.</span></span>

```
# Displays the name of the default options. This example is from ISE 4.0.
$psISE.Options.DefaultOptions

SelectedScriptPaneState                   : Top
ShowDefaultSnippets                       : True
ShowToolBar                               : True
ShowOutlining                             : True
ShowLineNumbers                           : True
TokenColors                               : {[Attribute, #FF00BFFF], [Command, #FF0000FF], [CommandArgument, #FF8A2BE2], [CommandParameter, #FF000080]...}
ConsoleTokenColors                        : {[Attribute, #FFB0C4DE], [Command, #FFE0FFFF], [CommandArgument, #FFEE82EE], [CommandParameter, #FFFFE4B5]...}
XmlTokenColors                            : {[Comment, #FF006400], [CommentDelimiter, #FF008000], [ElementName, #FF8B0000], [MarkupExtension, #FFFF8C00]...}
DefaultOptions                            : Microsoft.PowerShell.Host.ISE.ISEOptions
FontSize                                  : 9
Zoom                                      : 100
FontName                                  : Lucida Console
ErrorForegroundColor                      : #FFFF0000
ErrorBackgroundColor                      : #00FFFFFF
WarningForegroundColor                    : #FFFF8C00
WarningBackgroundColor                    : #00FFFFFF
VerboseForegroundColor                    : #FF00FFFF
VerboseBackgroundColor                    : #00FFFFFF
DebugForegroundColor                      : #FF00FFFF
DebugBackgroundColor                      : #00FFFFFF
ConsolePaneBackgroundColor                : #FF012456
ConsolePaneTextBackgroundColor            : #FF012456
ConsolePaneForegroundColor                : #FFF5F5F5
ScriptPaneBackgroundColor                 : #FFFFFFFF
ScriptPaneForegroundColor                 : #FF000000
ShowWarningForDuplicateFiles              : True
ShowWarningBeforeSavingOnRun              : True
UseLocalHelp                              : True
AutoSaveMinuteInterval                    : 2
MruCount                                  : 10
ShowIntellisenseInConsolePane             : True
ShowIntellisenseInScriptPane              : True
UseEnterToSelectInConsolePaneIntellisense : True
UseEnterToSelectInScriptPaneIntellisense  : True
IntellisenseTimeoutInSeconds              : 3

```

###  <span data-ttu-id="de407-210"><a name="ebc"></a> ErrorBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-210"><a name="ebc"></a> ErrorBackgroundColor</span></span>
  <span data-ttu-id="de407-211">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-211">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-212">コンソール ウィンドウに表示されるエラー テキストの背景色を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-212">Specifies the background color for error text that appears in the Console pane.</span></span> <span data-ttu-id="de407-213">これは **System.Windows.Media.Color** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="de407-213">It is an instance of the **System.Windows.Media.Color** class.</span></span>

```
# Changes the background color for the error text that appears in the Console pane to black.
$psISE.Options.ErrorBackgroundColor="black"
```

###  <span data-ttu-id="de407-214"><a name="efc"></a> ErrorForegroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-214"><a name="efc"></a> ErrorForegroundColor</span></span>
  <span data-ttu-id="de407-215">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-215">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-216">コンソール ウィンドウに表示されるエラー テキストの前景色を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-216">Specifies the foreground color for error text that appears in the Console pane.</span></span> <span data-ttu-id="de407-217">これは **System.Windows.Media.Color** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="de407-217">It is an instance of the **System.Windows.Media.Color** class.</span></span>

```
# Changes the foreground color for the error text that appears in the console pane to green.
$psISE.Options.ErrorForegroundColor ="green"
```

###  <span data-ttu-id="de407-218"><a name="fn"></a> FontName</span><span class="sxs-lookup"><span data-stu-id="de407-218"><a name="fn"></a> FontName</span></span>
  <span data-ttu-id="de407-219">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-219">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-220">スクリプト ウィンドウおよびコンソール ウィンドウの両方で現在使用しているフォント名を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-220">Specifies the font name currently in use in both the Script pane and the Console pane.</span></span>

```
# Changes the font used in both panes.
$psISE.Options.FontName = "courier new"
```

###  <span data-ttu-id="de407-221"><a name="fs"></a> FontSize</span><span class="sxs-lookup"><span data-stu-id="de407-221"><a name="fs"></a> FontSize</span></span>
  <span data-ttu-id="de407-222">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-222">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-223">整数値としてフォント サイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-223">Specifies the font size as an integer.</span></span> <span data-ttu-id="de407-224">スクリプト ウィンドウ、コマンド ウィンドウ、出力ウィンドウで使用されます。</span><span class="sxs-lookup"><span data-stu-id="de407-224">It is used in the Script pane, the Command pane, and the Output pane.</span></span> <span data-ttu-id="de407-225">有効な値の範囲は、8 ~ 32 です。</span><span class="sxs-lookup"><span data-stu-id="de407-225">The valid range of values is 8 through 32.</span></span>

```
# Changes the font size in all panes.
$psISE.Options.FontSize = 20

```

###  <span data-ttu-id="de407-226"><a name="itis"></a> IntellisenseTimeoutInSeconds</span><span class="sxs-lookup"><span data-stu-id="de407-226"><a name="itis"></a> IntellisenseTimeoutInSeconds</span></span>
  <span data-ttu-id="de407-227">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-227">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-228">IntelliSense が、現在入力しているテキストを解決しようとするために使用する秒数を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-228">Specifies the number of seconds that IntelliSense uses to try to resolve the currently typed text.</span></span> <span data-ttu-id="de407-229">この秒数が経ったら、IntelliSense はタイムアウトし、入力を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="de407-229">After this number of seconds, IntelliSense times out and enables you to continue typing.</span></span> <span data-ttu-id="de407-230">既定値は 3 秒です。</span><span class="sxs-lookup"><span data-stu-id="de407-230">The default value is 3 seconds.</span></span> <span data-ttu-id="de407-231">値は整数です。</span><span class="sxs-lookup"><span data-stu-id="de407-231">The value is an integer.</span></span>

```
# Changes the number of seconds for IntelliSense syntax recognition to 5.
$psISE.Options.IntellisenseTimeoutInSeconds = 5
```

###  <span data-ttu-id="de407-232"><a name="mc"></a> MruCount</span><span class="sxs-lookup"><span data-stu-id="de407-232"><a name="mc"></a> MruCount</span></span>
  <span data-ttu-id="de407-233">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-233">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-234">Windows PowerShell ISE が追跡し、**[ファイルを開く]** メニューの下部で表示する、最近使ったファイルの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-234">Specifies the number of recently opened files that Windows PowerShell ISE tracks and displays at the bottom of the **File Open** menu.</span></span> <span data-ttu-id="de407-235">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="de407-235">The default value is 10.</span></span> <span data-ttu-id="de407-236">値は整数です。</span><span class="sxs-lookup"><span data-stu-id="de407-236">The value is an integer.</span></span>

```
# Changes the number of recently used files that appear at the bottom of the File Open menu to 5.
$psISE.Options.MruCount = 5
```

###  <span data-ttu-id="de407-237"><a name="opbc"></a> OutputPaneBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-237"><a name="opbc"></a> OutputPaneBackgroundColor</span></span>
  <span data-ttu-id="de407-238">この機能は、Windows PowerShell ISE 2.0 に存在しますが、それよりも後のバージョンの ISE では削除されているか、名前が変更されています。</span><span class="sxs-lookup"><span data-stu-id="de407-238">This feature is present in Windows PowerShell ISE 2.0, but was removed or renamed in later versions of the ISE.</span></span>  <span data-ttu-id="de407-239">後のバージョンについては、[ConsolePaneBackgroundColor](#conpbc) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de407-239">For later versions, see [ConsolePaneBackgroundColor](#conpbc).</span></span>

 <span data-ttu-id="de407-240">出力ウィンドウ自体の背景色を取得または設定する読み取り/書き込みのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="de407-240">The read/write property that gets or sets the background color for the Output pane itself.</span></span> <span data-ttu-id="de407-241">これは **System.Windows.Media.Color** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="de407-241">It is an instance of the **System.Windows.Media.Color** class.</span></span>

```
# Changes the background color of the Output pane to gold.
$psISE.Options.OutputPaneForegroundColor = "gold"

```

###  <span data-ttu-id="de407-242"><a name="optfc"></a> OutputPaneTextForegroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-242"><a name="optfc"></a> OutputPaneTextForegroundColor</span></span>
  <span data-ttu-id="de407-243">この機能は、Windows PowerShell ISE 2.0 に存在しますが、それよりも後のバージョンの ISE では削除されているか、名前が変更されています。</span><span class="sxs-lookup"><span data-stu-id="de407-243">This feature is present in Windows PowerShell ISE 2.0, but was removed or renamed in later versions of the ISE.</span></span>  <span data-ttu-id="de407-244">後のバージョンについては、[ConsolePaneForegroundColor](#conpfc) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de407-244">For later versions, see [ConsolePaneForegroundColor](#conpfc).</span></span>

 <span data-ttu-id="de407-245">Windows PowerShell ISE 2.0 で出力ウィンドウのテキストの前景色を変更する読み取り/書き込みプロパティ。</span><span class="sxs-lookup"><span data-stu-id="de407-245">The read/write property that changes the foreground color of the text in the Output pane in Windows PowerShell ISE 2.0.</span></span>

```
# Changes the foreground color of the text in the Output Pane to blue.
$psISE.Options.OutputPaneTextForegroundColor  = "blue"

```

###  <span data-ttu-id="de407-246"><a name="optbc"></a> OutputPaneTextBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-246"><a name="optbc"></a> OutputPaneTextBackgroundColor</span></span>
  <span data-ttu-id="de407-247">この機能は、Windows PowerShell ISE 2.0 に存在しますが、それよりも後のバージョンの ISE では削除されているか、名前が変更されています。</span><span class="sxs-lookup"><span data-stu-id="de407-247">This feature is present in Windows PowerShell ISE 2.0, but was removed or renamed in later versions of the ISE.</span></span>  <span data-ttu-id="de407-248">後のバージョンについては、[ConsolePaneTextBackgroundColor](#conptbc) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de407-248">For later versions, see [ConsolePaneTextBackgroundColor](#conptbc).</span></span>

 <span data-ttu-id="de407-249">出力ウィンドウのテキストの背景色を変更する読み取り/書き込みプロパティ。</span><span class="sxs-lookup"><span data-stu-id="de407-249">The read/write property that changes the background color of the text in the Output pane.</span></span>

```
# Changes the background color of the Output pane text to pink.
$psISE.Options.OutputPaneTextBackgroundColor = "pink"
```

###  <span data-ttu-id="de407-250"><a name="spbc"></a> ScriptPaneBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-250"><a name="spbc"></a> ScriptPaneBackgroundColor</span></span>
  <span data-ttu-id="de407-251">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-251">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-252">ファイルの背景色を取得または設定する読み取り/書き込みのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="de407-252">The read/write property that gets or sets the background color for files.</span></span> <span data-ttu-id="de407-253">これは **System.Windows.Media.Color** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="de407-253">It is an instance of the **System.Windows.Media.Color** class.</span></span>

```

# Sets the color of the script pane background to yellow.
$psISE.Options.ScriptPaneBackgroundColor = ”yellow”

```

###  <span data-ttu-id="de407-254"><a name="spfc"></a> ScriptPaneForegroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-254"><a name="spfc"></a> ScriptPaneForegroundColor</span></span>
  <span data-ttu-id="de407-255">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-255">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-256">スクリプト ウィンドウのスクリプト以外のファイルの前景色を取得または設定する読み取り/書き込みのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="de407-256">The read/write property that gets or sets the foreground color for non-script files in the Script pane.</span></span>
<span data-ttu-id="de407-257">スクリプト ファイルの前景色を設定する場合、[TokenColors](The-ISEOptions-Object.md#tc) プロパティを使用してください。</span><span class="sxs-lookup"><span data-stu-id="de407-257">To set the foreground color for script files, use the [TokenColors](The-ISEOptions-Object.md#tc) property.</span></span>

```
# Sets the foreground to color of non-script files in the script pane to green.
$psISE.Options.ScriptPaneBackgroundColor = "green"

```

###  <span data-ttu-id="de407-258"><a name="ssps"></a> SelectedScriptPaneState</span><span class="sxs-lookup"><span data-stu-id="de407-258"><a name="ssps"></a> SelectedScriptPaneState</span></span>
  <span data-ttu-id="de407-259">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-259">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-260">ディスクプレイでのスクリプト ウィンドウの位置を取得または設定する読み取り/書き込みのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="de407-260">The read/write property that gets or sets the position of the Script pane on the display.</span></span> <span data-ttu-id="de407-261">「Maximized」、「Top」、「Right」のいずれかの文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-261">The string can be either "Maximized", "Top", or "Right".</span></span>

```
# Moves the Script Pane to the top.
$psISE.Options.SelectedScriptPaneState = "Top"
# Moves the Script Pane to the right.
$psISE.Options.SelectedScriptPaneState = "Right"
# Maximizes the Script Pane
$psISE.Options.SelectedScriptPaneState = "Maximized"

```

###  <span data-ttu-id="de407-262"><a name="sds"></a> ShowDefaultSnippets</span><span class="sxs-lookup"><span data-stu-id="de407-262"><a name="sds"></a> ShowDefaultSnippets</span></span>
  <span data-ttu-id="de407-263">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-263">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-264">スニペットの **CTRL + J** 一覧に、Windows PowerShell に含まれるスターター セットを含めるどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-264">Specifies whether the **CTRL+J** list of snippets includes the starter set that is included in Windows PowerShell.</span></span> <span data-ttu-id="de407-265">**$false** に設定すると、ユーザー定義のスニペットのみが **CTRL + J** 一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="de407-265">When set to **$false**, only user-defined snippets appear in the **CTRL+J** list.</span></span> <span data-ttu-id="de407-266">既定値は **$true** です。</span><span class="sxs-lookup"><span data-stu-id="de407-266">The default value is **$true**.</span></span>

```
# Hide the default snippets from the CTRL+J list.
$psISe.Options.ShowDefaultSnippets = $false
```

###  <span data-ttu-id="de407-267"><a name="siicp"></a> ShowIntellisenseInConsolePane</span><span class="sxs-lookup"><span data-stu-id="de407-267"><a name="siicp"></a> ShowIntellisenseInConsolePane</span></span>
  <span data-ttu-id="de407-268">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-268">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-269">IntelliSense がコンソール ウィンドウで構文、パラメーター、および値の候補を提供するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-269">Specifies whether IntelliSense offers syntax, parameter, and value suggestions in the Console pane.</span></span> <span data-ttu-id="de407-270">既定値は **$true** です。</span><span class="sxs-lookup"><span data-stu-id="de407-270">The default value is **$true**.</span></span>

```
# Turn off IntelliSense in the console pane.
$psISe.Options.ShowIntellisenseInConsolePane = $false
```

###  <span data-ttu-id="de407-271"><a name="siisp"></a> ShowIntellisenseInScriptPane</span><span class="sxs-lookup"><span data-stu-id="de407-271"><a name="siisp"></a> ShowIntellisenseInScriptPane</span></span>
  <span data-ttu-id="de407-272">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-272">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-273">IntelliSense がスクリプト ウィンドウで構文、パラメーター、および値の候補を提供するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-273">Specifies whether IntelliSense offers syntax, parameter, and value suggestions in the Script pane.</span></span> <span data-ttu-id="de407-274">既定値は **$true** です。</span><span class="sxs-lookup"><span data-stu-id="de407-274">The default value is **$true**.</span></span>

```
# Turn off IntelliSense in the Script pane.
$psISe.Options.ShowIntellisenseInScriptPane = $false
```

###  <span data-ttu-id="de407-275"><a name="sln"></a> ShowLineNumbers</span><span class="sxs-lookup"><span data-stu-id="de407-275"><a name="sln"></a> ShowLineNumbers</span></span>
  <span data-ttu-id="de407-276">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-276">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-277">スクリプト ペインの左の余白に行番号を表示するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-277">Specifies whether the Script pane displays line numbers in the left margin.</span></span> <span data-ttu-id="de407-278">既定値は **$true** です。</span><span class="sxs-lookup"><span data-stu-id="de407-278">The default value is **$true**.</span></span>

```
# Turn off line numbers in the Script pane.
$psISe.Options.ShowLineNumbers = $false
```

###  <span data-ttu-id="de407-279"><a name="so"></a> ShowOutlining</span><span class="sxs-lookup"><span data-stu-id="de407-279"><a name="so"></a> ShowOutlining</span></span>
  <span data-ttu-id="de407-280">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-280">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-281">スクリプト ペインの左の余白のコードのセクションの横にある展開と折りたたみの角かっこを表示するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-281">Specifies whether the Script pane displays expandable and collapsible brackets next to sections of code in the left margin.</span></span> <span data-ttu-id="de407-282">表示する場合、テキストのブロックの横にあるマイナス アイコン \(-\) をクリックすると折りたたみ、プラス アイコン \(+\) をクリックするとテキストのブロックを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="de407-282">When they are displayed, you can click the minus \(-\) icons next to a block of text to collapse it or click the plus \(+\) icon to expand a block of text.</span></span> <span data-ttu-id="de407-283">既定値は **$true** です。</span><span class="sxs-lookup"><span data-stu-id="de407-283">The default value is **$true**.</span></span>

```
# Turn off outlining in the Script pane.
$psISe.Options.ShowOutlining = $false
```

###  <span data-ttu-id="de407-284"><a name="stb"></a> ShowToolBar</span><span class="sxs-lookup"><span data-stu-id="de407-284"><a name="stb"></a> ShowToolBar</span></span>
  <span data-ttu-id="de407-285">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-285">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-286">Windows PowerShell ISE ウィンドウの上部に ISE ツールバーを表示するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-286">Specifies whether the ISE toolbar appears at the top of the Windows PowerShell ISE window.</span></span> <span data-ttu-id="de407-287">既定値は **$true** です。</span><span class="sxs-lookup"><span data-stu-id="de407-287">The default value is **$true**.</span></span>

```
# Show the toolbar.
$psISe.Options.ShowToolBar = $true
```

###  <span data-ttu-id="de407-288"><a name="swbsor"></a> ShowWarningBeforeSavingOnRun</span><span class="sxs-lookup"><span data-stu-id="de407-288"><a name="swbsor"></a> ShowWarningBeforeSavingOnRun</span></span>
  <span data-ttu-id="de407-289">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-289">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-290">スクリプトが実行される前に自動的に保存されるときに警告メッセージを表示するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-290">Specifies whether a warning message appears when a script is saved automatically before it is run.</span></span> <span data-ttu-id="de407-291">既定値は **$true** です。</span><span class="sxs-lookup"><span data-stu-id="de407-291">The default value is **$true**.</span></span>

```
# Enable the warning message when an attempt
# is made to run a script without saving it first.
$psISE.Options.ShowWarningBeforeSavingOnRun=$true

```

###  <span data-ttu-id="de407-292"><a name="swfdf"></a> ShowWarningForDuplicateFiles</span><span class="sxs-lookup"><span data-stu-id="de407-292"><a name="swfdf"></a> ShowWarningForDuplicateFiles</span></span>
  <span data-ttu-id="de407-293">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-293">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-294">さまざまな PowerShell タブで同じファイルが開かれているときに警告メッセージを表示するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-294">Specifies whether a warning message appears when the same file is opened in different PowerShell tabs.</span></span> <span data-ttu-id="de407-295">**$true** に設定している場合、複数のタブで同じファイルが開かれると、「このファイルのコピーが別の Windows PowerShell タブで開かれています。</span><span class="sxs-lookup"><span data-stu-id="de407-295">If set to **$true**, to open the same file in multiple tabs displays this message: "A copy of this file is open in another Windows PowerShell tab.</span></span> <span data-ttu-id="de407-296">このファイルを変更すると、開かれているすべてのファイルに影響します。」というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="de407-296">Changes made to this file will affect all open copies."</span></span> <span data-ttu-id="de407-297">既定値は **$true** です。</span><span class="sxs-lookup"><span data-stu-id="de407-297">The default value is **$true**.</span></span>

```
# Enable the warning message when a file is
# opened in multiple PowerShell tabs.
$psISE.Options.ShowWarningForDuplicateFiles = $true

```

###  <span data-ttu-id="de407-298"><a name="tc"></a> TokenColors</span><span class="sxs-lookup"><span data-stu-id="de407-298"><a name="tc"></a> TokenColors</span></span>
  <span data-ttu-id="de407-299">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-299">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-300">Windows PowerShell ISE のスクリプト ウィンドウの IntelliSense トークンの色を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-300">Specifies the colors of the IntelliSense tokens in the Windows PowerShell ISE Script pane.</span></span> <span data-ttu-id="de407-301">このプロパティは、スクリプト ウィンドウのトークンの種類と色の名前/値のペアを含むディクショナリ オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="de407-301">This property is a dictionary object that contains name/value pairs of token types and colors for the Script pane.</span></span> <span data-ttu-id="de407-302">コンソール ウィンドウで IntelliSense トークンの色を変更する場合は、[ConsoleTokenColors](#contc) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de407-302">To change the colors of the IntelliSense tokens in the Console pane, see [ConsoleTokenColors](#contc).</span></span> <span data-ttu-id="de407-303">色を既定値にリセットする場合、[RestoreDefaultTokenColors()](#rdtc) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de407-303">To reset the colors to the default values, see [RestoreDefaultTokenColors()](#rdtc).</span></span> <span data-ttu-id="de407-304">次のトークンの色を設定することができます: Attribute、Command、CommandArgument、CommandParameter、Comment、GroupEnd、GroupStart、Keyword、LineContinuation、LoopLabel、Member、NewLine、Number、Operator、Position、StatementSeparator、String、Type、Unknown、Variable。</span><span class="sxs-lookup"><span data-stu-id="de407-304">Token colors can be set for the following: Attribute, Command, CommandArgument, CommandParameter, Comment, GroupEnd, GroupStart, Keyword, LineContinuation, LoopLabel, Member, NewLine, Number, Operator, Position, StatementSeparator, String, Type, Unknown, Variable.</span></span>

```
# Sets the color of commands to green.
$psISE.Options.TokenColors["Command"] = "green"
# Sets the color of keywords to magenta.
$psISE.Options.TokenColors["Keyword"] = "magenta"

```

###  <span data-ttu-id="de407-305"><a name="uetsicpi"></a> UseEnterToSelectInConsolePaneIntellisense</span><span class="sxs-lookup"><span data-stu-id="de407-305"><a name="uetsicpi"></a> UseEnterToSelectInConsolePaneIntellisense</span></span>
  <span data-ttu-id="de407-306">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-306">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-307">Enter キーを使用して、IntelliSense が提供するオプションをコンソール ウィンドウで選択できるようにするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-307">Specifies whether you can use the Enter key to select an IntelliSense provided option in the Console pane.</span></span> <span data-ttu-id="de407-308">既定値は **$true** です。</span><span class="sxs-lookup"><span data-stu-id="de407-308">The default value is **$true**.</span></span>

```
# Turn off using the ENTER key to select an IntelliSense provided option in the Console pane.
$psISE.Options.UseEnterToSelectInConsolePaneIntellisense=$false

```

###  <span data-ttu-id="de407-309"><a name="uetsispi"></a> UseEnterToSelectInScriptPaneIntellisense</span><span class="sxs-lookup"><span data-stu-id="de407-309"><a name="uetsispi"></a> UseEnterToSelectInScriptPaneIntellisense</span></span>
  <span data-ttu-id="de407-310">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-310">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-311">Enter キーを使用して、IntelliSense が提供するオプションをスクリプト ウィンドウで選択できるようにするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-311">Specifies whether you can use the Enter key to select an IntelliSense-provided option in the Script pane.</span></span> <span data-ttu-id="de407-312">既定値は **$true** です。</span><span class="sxs-lookup"><span data-stu-id="de407-312">The default value is **$true**.</span></span>

```
# Turn on using the Enter key to select an IntelliSense provided option in the Console pane.
$psISE.Options.UseEnterToSelectInConsolePaneIntellisense=$true

```

###  <span data-ttu-id="de407-313"><a name="ulh"></a> UseLocalHelp</span><span class="sxs-lookup"><span data-stu-id="de407-313"><a name="ulh"></a> UseLocalHelp</span></span>
  <span data-ttu-id="de407-314">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-314">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-315">カーソルをキーワードに置いた状態で F1 キーを押したときに、ローカルにインストールされたヘルプまたはオンラインの TechNet ライブラリのヘルプを表示するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-315">Specifies whether the locally installed Help or the online TechNet Library Help appears when you press F1 with the cursor positioned in a keyword.</span></span> <span data-ttu-id="de407-316">**$true** に設定すると、ローカルにインストールされたヘルプ コンテンツがポップアップ ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="de407-316">If set to **$true**, then a pop-up window shows content from the locally installed Help.</span></span> <span data-ttu-id="de407-317">`Update-Help` コマンドを実行すると、ヘルプ ファイルをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="de407-317">You can install the Help files by running the `Update-Help` command.</span></span> <span data-ttu-id="de407-318">**$false** に設定すると、ブラウザーが開き、TechNet ライブラリ内のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="de407-318">If set to **$false**, then your browser opens to a page in the TechNet Library.</span></span>

```
# Sets the option for the online help to be displayed.
$psISE.Options.UseLocalHelp=$false
# Sets the option for the local Help to be displayed.
$psISE.Options.UseLocalHelp=$true

```

###  <span data-ttu-id="de407-319"><a name="vbc"></a> VerboseBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-319"><a name="vbc"></a> VerboseBackgroundColor</span></span>
  <span data-ttu-id="de407-320">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-320">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-321">コンソール ウィンドウに表示される詳細テキストの背景色を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-321">Specifies the background color for verbose text that appears in the Console pane.</span></span> <span data-ttu-id="de407-322">これは **System.Windows.Media.Color** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="de407-322">It is a **System.Windows.Media.Color** object.</span></span>

```
# Changes the background color for verbose text to blue.
$psISE.Options.VerboseBackgroundColor ='#0000FF'
```

###  <span data-ttu-id="de407-323"><a name="vfc"></a> VerboseForegroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-323"><a name="vfc"></a> VerboseForegroundColor</span></span>
  <span data-ttu-id="de407-324">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-324">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-325">コンソール ウィンドウに表示される詳細テキストの前景色を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-325">Specifies the foreground color for verbose text that appears in the Console pane.</span></span> <span data-ttu-id="de407-326">これは **System.Windows.Media.Color** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="de407-326">It is a **System.Windows.Media.Color** object.</span></span>

```
# Changes the foreground color for verbose text to yellow.
$psISE.Options.VerboseForegroundColor =”yellow”
```

###  <span data-ttu-id="de407-327"><a name="wbc"></a> WarningBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-327"><a name="wbc"></a> WarningBackgroundColor</span></span>
  <span data-ttu-id="de407-328">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-328">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-329">コンソール ウィンドウに表示される警告テキストの背景色を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-329">Specifies the background color for warning text that appears in the Console pane.</span></span> <span data-ttu-id="de407-330">これは **System.Windows.Media.Color** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="de407-330">It is a **System.Windows.Media.Color** object.</span></span>

```
# Changes the background color for warning text to blue.
$psISE.Options.WarningBackgroundColor ='#0000FF'
```

###  <span data-ttu-id="de407-331"><a name="wfc"></a> WarningForegroundColor</span><span class="sxs-lookup"><span data-stu-id="de407-331"><a name="wfc"></a> WarningForegroundColor</span></span>
  <span data-ttu-id="de407-332">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de407-332">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="de407-333">出力ウィンドウに表示される警告テキストの前景色を指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-333">Specifies the foreground color for warning text that appears in the Output pane.</span></span> <span data-ttu-id="de407-334">これは **System.Windows.Media.Color** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="de407-334">It is a **System.Windows.Media.Color** object.</span></span>

```
# Changes the foreground color for warning text to yellow.
$psISE.Options.WarningForegroundColor =”yellow”
```

###  <span data-ttu-id="de407-335"><a name="xtc"></a> XmlTokenColors</span><span class="sxs-lookup"><span data-stu-id="de407-335"><a name="xtc"></a> XmlTokenColors</span></span>
  <span data-ttu-id="de407-336">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-336">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-337">Windows PowerShell ISE で表示される XML コンテンツのトークンの種類と色の名前/値のペアを含むディクショナリ オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-337">Specifies a dictionary object that contains name/value pairs of token types and colors for XML content that is displayed in Windows PowerShell ISE.</span></span> <span data-ttu-id="de407-338">次のトークンの色を設定することができます: Attribute、Command、CommandArgument、CommandParameter、Comment、GroupEnd、GroupStart、Keyword、LineContinuation、LoopLabel、Member、NewLine、Number、Operator、Position、StatementSeparator、String、Type、Unknown、Variable。</span><span class="sxs-lookup"><span data-stu-id="de407-338">Token colors can be set for the following: Attribute, Command, CommandArgument, CommandParameter, Comment, GroupEnd, GroupStart, Keyword, LineContinuation, LoopLabel, Member, NewLine, Number, Operator, Position, StatementSeparator, String, Type, Unknown, Variable.</span></span> <span data-ttu-id="de407-339">[RestoreDefaultXmlTokenColors()](#rdxtc) も参照してください。</span><span class="sxs-lookup"><span data-stu-id="de407-339">Also see [RestoreDefaultXmlTokenColors()](#rdxtc).</span></span>

```
# Sets the color of XML element names to green.
$psISE.Options.XmlTokenColors["ElementName"] = "green"
# Sets the color of XML comments to magenta.
$psISE.Options.XmlTokenColors["Comment"] = "magenta"

```

###  <span data-ttu-id="de407-340"><a name="z"></a> Zoom</span><span class="sxs-lookup"><span data-stu-id="de407-340"><a name="z"></a> Zoom</span></span>
  <span data-ttu-id="de407-341">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="de407-341">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="de407-342">コンソール ウィンドウとスクリプト ウィンドウの両方でのテキストの相対サイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="de407-342">Specifies the relative size of text in both the Console and Script panes.</span></span> <span data-ttu-id="de407-343">既定値は 100 です。</span><span class="sxs-lookup"><span data-stu-id="de407-343">The default value is 100.</span></span> <span data-ttu-id="de407-344">Windows PowerShell 内のテキストは、値が小さいと小さく表示され、値が大きいと大きく表示されます。</span><span class="sxs-lookup"><span data-stu-id="de407-344">Smaller values cause the text in Windows PowerShell ISE to appear smaller while larger numbers cause text to appear larger.</span></span> <span data-ttu-id="de407-345">値は、20 ~ 400 の範囲の整数です。</span><span class="sxs-lookup"><span data-stu-id="de407-345">The value is an integer that ranges from 20 to 400.</span></span>

```
# Changes the text in the Windows PowerShell ISE to be double its normal size.
$psISE.Options.Zoom = 200
```

## <a name="see-also"></a><span data-ttu-id="de407-346">参照</span><span class="sxs-lookup"><span data-stu-id="de407-346">See Also</span></span>
- [<span data-ttu-id="de407-347">Windows PowerShell ISE スクリプト オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="de407-347">The Windows PowerShell ISE Scripting Object Model</span></span>](The-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="de407-348">Windows PowerShell ISE オブジェクト モデル リファレンス</span><span class="sxs-lookup"><span data-stu-id="de407-348">Windows PowerShell ISE Object Model Reference</span></span>](Windows-PowerShell-ISE-Object-Model-Reference.md)

