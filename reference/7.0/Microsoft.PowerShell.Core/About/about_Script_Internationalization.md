---
description: スクリプトがユーザーインターフェイス (UI) 言語でユーザーにメッセージや指示を簡単に表示できるようにする、スクリプト国際化機能について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 03/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_script_internationalization?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Script_Internationalization
ms.openlocfilehash: dddf090ba18ca9eb703b307db9fddcdb88e4a5ac
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220608"
---
# <a name="about-script-internationalization"></a><span data-ttu-id="4d268-104">スクリプト国際化について</span><span class="sxs-lookup"><span data-stu-id="4d268-104">About Script Internationalization</span></span>

## <a name="short-description"></a><span data-ttu-id="4d268-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="4d268-105">Short Description</span></span>
<span data-ttu-id="4d268-106">スクリプトがユーザーインターフェイス (UI) 言語でユーザーにメッセージや指示を簡単に表示できるようにする、スクリプト国際化機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="4d268-106">Describes the script internationalization features that make it easy for scripts to display messages and instructions to users in their user interface (UI) language.</span></span>

## <a name="long-description"></a><span data-ttu-id="4d268-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="4d268-107">Long Description</span></span>

<span data-ttu-id="4d268-108">PowerShell スクリプトの国際化機能を使用すると、ユーザーの言語でヘルプとユーザーのメッセージを表示することで、世界中のユーザーにより優れたサービスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="4d268-108">The PowerShell script internationalization features allow you to better serve users throughout the world by displaying help and user messages in the user's language.</span></span>

<span data-ttu-id="4d268-109">スクリプトの国際化機能は、実行中にオペレーティングシステムの UI カルチャを照会し、適切に翻訳されたテキスト文字列をインポートして、ユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="4d268-109">The script internationalization features query the UI culture of the operating system during execution, import the appropriate translated text strings, and display them to the user.</span></span> <span data-ttu-id="4d268-110">Data セクションでは、コードとは別にテキスト文字列を格納できるため、簡単に識別して抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="4d268-110">The Data section lets you store text strings separate from code so they are easily identified and extracted.</span></span> <span data-ttu-id="4d268-111">新しいコマンドレットでは、 `ConvertFrom-StringData` テキスト文字列を辞書に似たハッシュテーブルに変換し、翻訳を容易にします。</span><span class="sxs-lookup"><span data-stu-id="4d268-111">A new cmdlet, `ConvertFrom-StringData`, converts text strings into dictionary-like hash tables to facilitate translation.</span></span>

<span data-ttu-id="4d268-112">インターナショナルヘルプテキストをサポートするために、PowerShell には次の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4d268-112">To support international Help text, PowerShell includes the following features:</span></span>

- <span data-ttu-id="4d268-113">テキスト文字列をコードの命令から分離するデータセクション。</span><span class="sxs-lookup"><span data-stu-id="4d268-113">A Data section that separates text strings from code instructions.</span></span> <span data-ttu-id="4d268-114">Data セクションの詳細については、「 [about_Data_Sections](about_Data_Sections.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d268-114">For more information about the Data section, see [about_Data_Sections](about_Data_Sections.md).</span></span>

- <span data-ttu-id="4d268-115">新しい自動変数、 `$PSCulture` および `$PSUICulture` 。</span><span class="sxs-lookup"><span data-stu-id="4d268-115">New automatic variables, `$PSCulture` and `$PSUICulture`.</span></span> <span data-ttu-id="4d268-116">`$PSCulture` 日付、時刻、通貨などの要素に対してシステムで使用される UI 言語の名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="4d268-116">`$PSCulture` stores the name of the UI language used on the system for elements such as the date, time, and currency.</span></span> <span data-ttu-id="4d268-117">変数は、 `$PSUICulture` メニューやテキスト文字列などのユーザーインターフェイス要素にシステムで使用される UI 言語の名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="4d268-117">The `$PSUICulture` variable stores the name of the UI language used on the system for user interface elements such as menus and text strings.</span></span>

- <span data-ttu-id="4d268-118">`ConvertFrom-StringData`変換を容易にするためにテキスト文字列をディクショナリに似たハッシュテーブルに変換するコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="4d268-118">A cmdlet, `ConvertFrom-StringData`, that converts text strings into dictionary-like hash tables to facilitate translation.</span></span> <span data-ttu-id="4d268-119">詳細については、「 [convertfrom-csv-convertfrom-stringdata](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d268-119">For more information, see [ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData).</span></span>

- <span data-ttu-id="4d268-120">`.psd1`翻訳されたテキスト文字列を格納する新しいファイルの種類。</span><span class="sxs-lookup"><span data-stu-id="4d268-120">A new file type, `.psd1`, that stores translated text strings.</span></span> <span data-ttu-id="4d268-121">これらの `.psd1` ファイルは、スクリプトディレクトリの言語固有のサブディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="4d268-121">The `.psd1` files are stored in language-specific subdirectories of the script directory.</span></span>

- <span data-ttu-id="4d268-122">`Import-LocalizedData`実行時に、指定した言語の翻訳されたテキスト文字列をスクリプトにインポートするコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="4d268-122">A cmdlet, `Import-LocalizedData`, that imports translated text strings for a specified language into a script at runtime.</span></span> <span data-ttu-id="4d268-123">このコマンドレットは、Windows でサポートされている言語の文字列を認識し、インポートします。</span><span class="sxs-lookup"><span data-stu-id="4d268-123">This cmdlet recognizes and imports strings in any Windows-supported language.</span></span> <span data-ttu-id="4d268-124">詳細については [、「import-localizeddata](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d268-124">For more information see [Import-LocalizedData](xref:Microsoft.PowerShell.Utility.Import-LocalizedData).</span></span>

### <a name="the-data-section-storing-default-strings"></a><span data-ttu-id="4d268-125">Data セクション: 既定の文字列の格納</span><span class="sxs-lookup"><span data-stu-id="4d268-125">The Data Section: Storing Default Strings</span></span>

<span data-ttu-id="4d268-126">スクリプト内の Data セクションを使用して、テキスト文字列を既定の言語で格納します。</span><span class="sxs-lookup"><span data-stu-id="4d268-126">Use a Data section in the script to store the text strings in the default language.</span></span> <span data-ttu-id="4d268-127">キーと値のペアの文字列を、ここでは文字列に配置します。</span><span class="sxs-lookup"><span data-stu-id="4d268-127">Arrange the strings in key/value pairs in a here-string.</span></span> <span data-ttu-id="4d268-128">各キーと値のペアは、別々の行に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d268-128">Each key/value pair must be on a separate line.</span></span> <span data-ttu-id="4d268-129">コメントを含める場合は、コメントを別の行に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d268-129">If you include comments, the comments must be on separate lines.</span></span>

<span data-ttu-id="4d268-130">`ConvertFrom-StringData`このコマンドレットは、ここで指定した文字列のキーと値のペアを、Data section 変数の値に格納されているディクショナリに似たハッシュテーブルに変換します。</span><span class="sxs-lookup"><span data-stu-id="4d268-130">The `ConvertFrom-StringData` cmdlet converts the key/value pairs in the here-string into a dictionary-like hash table that is stored in the value of the Data section variable.</span></span>

<span data-ttu-id="4d268-131">次の例では、スクリプトの Data セクションに、 `World.ps1` スクリプトのプロンプトメッセージの English-United States (en-us) のセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4d268-131">In the following example, the Data section of the `World.ps1` script includes the English-United States (en-US) set of prompt messages for a script.</span></span> <span data-ttu-id="4d268-132">`ConvertFrom-StringData`コマンドレットは、文字列をハッシュテーブルに変換し、変数に格納し `$msgtable` ます。</span><span class="sxs-lookup"><span data-stu-id="4d268-132">The `ConvertFrom-StringData` cmdlet converts the strings into a hash table and stores them in the `$msgtable` variable.</span></span>

```powershell
$msgTable = Data {
    #culture="en-US"
    ConvertFrom-StringData @'
    helloWorld = Hello, World.
    errorMsg1 = You cannot leave the user name field blank.
    promptMsg = Please enter your user name.
'@
}
```

<span data-ttu-id="4d268-133">ここで説明する文字列の詳細については、「 [about_Quoting_Rules](about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d268-133">For more information about here-strings, see [about_Quoting_Rules](about_Quoting_Rules.md).</span></span>

### <a name="psd1-files-storing-translated-strings"></a><span data-ttu-id="4d268-134">.PSD1 Files: 翻訳された文字列の格納</span><span class="sxs-lookup"><span data-stu-id="4d268-134">PSD1 Files: Storing Translated Strings</span></span>

<span data-ttu-id="4d268-135">各 UI 言語のスクリプトメッセージを、スクリプトとファイル名拡張子が同じ名前の別のテキストファイルに保存し `.psd1` ます。</span><span class="sxs-lookup"><span data-stu-id="4d268-135">Save the script messages for each UI language in separate text files with the same name as the script and the `.psd1` file name extension.</span></span> <span data-ttu-id="4d268-136">次の形式のカルチャ名を使用して、スクリプトディレクトリのサブディレクトリにファイルを格納します。</span><span class="sxs-lookup"><span data-stu-id="4d268-136">Store the files in subdirectories of the script directory with names of cultures in the following format:</span></span>

`<language>-<region>`

<span data-ttu-id="4d268-137">例: de、ar-SA、zh-tw-Hans</span><span class="sxs-lookup"><span data-stu-id="4d268-137">Examples: de-DE, ar-SA, and zh-Hans</span></span>

<span data-ttu-id="4d268-138">たとえば、 `World.ps1` スクリプトがディレクトリに格納されている場合は、 `C:\Scripts` 次のようなファイルディレクトリ構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="4d268-138">For example, if the `World.ps1` script is stored in the `C:\Scripts` directory, you would create a file directory structure that resembles the following:</span></span>

```
C:\Scripts
C:\Scripts\World.ps1
C:\Scripts\de-DE\World.psd1
C:\Scripts\ar-SA\World.psd1
C:\Scripts\zh-CN\World.psd1
...
```

<span data-ttu-id="4d268-139">`World.psd1`スクリプトディレクトリのデ de サブディレクトリのファイルには、次のステートメントが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d268-139">The `World.psd1` file in the de-DE subdirectory of the script directory might include the following statement:</span></span>

```powershell
ConvertFrom-StringData -StringData @'
helloWorld = Hallo, Welt.
errorMsg1 = Das Feld Benutzername darf nicht leer sein.
promptMsg = Geben Sie Ihren Benutzernamen ein.
'@
```

<span data-ttu-id="4d268-140">同様に、 `World.psd1` スクリプトディレクトリの ar-SA サブディレクトリのファイルには、次のステートメントが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d268-140">Similarly, the `World.psd1` file in the ar-SA subdirectory of the script directory might includes the following statement:</span></span>

```powershell
ConvertFrom-StringData -StringData @'
helloWorld = مرحبًا أيها العالَم
errorMsg1 = لا يمكنك ترك حقل اسم المستخدم فارغًا
promptMsg = يرجى إدخال اسم المستخدم الخاص بك
'@
```

### <a name="import-localizeddata-dynamic-retrieval-of-translated-strings"></a><span data-ttu-id="4d268-141">Import-localizeddata: 翻訳された文字列の動的な取得</span><span class="sxs-lookup"><span data-stu-id="4d268-141">Import-LocalizedData: Dynamic Retrieval of Translated Strings</span></span>

<span data-ttu-id="4d268-142">現在のユーザーの UI 言語で文字列を取得するには、コマンドレットを使用し `Import-LocalizedData` ます。</span><span class="sxs-lookup"><span data-stu-id="4d268-142">To retrieve the strings in the UI language of the current user, use the `Import-LocalizedData` cmdlet.</span></span>

<span data-ttu-id="4d268-143">`Import-LocalizedData` 自動変数の値を検索 `$PSUICulture` し、 `<script-name>.psd1` その値に一致するサブディレクトリ内のファイルの内容をインポートし `$PSUICulture` ます。</span><span class="sxs-lookup"><span data-stu-id="4d268-143">`Import-LocalizedData` finds the value of the `$PSUICulture` automatic variable and imports the content of the `<script-name>.psd1` files in the subdirectory that matches the `$PSUICulture` value.</span></span> <span data-ttu-id="4d268-144">次に、 **Bindingvariable** パラメーターの値で指定した変数に、インポートされたコンテンツを保存します。</span><span class="sxs-lookup"><span data-stu-id="4d268-144">Then, it saves the imported content in the variable specified by the value of the **BindingVariable** parameter.</span></span>

```powershell
Import-LocalizedData -BindingVariable msgTable
```

<span data-ttu-id="4d268-145">たとえば、 `Import-LocalizedData` スクリプトにコマンドが表示され、 `C:\Scripts\World.ps1` の値 `$PSUICulture` が "ar-SA" の場合、は `Import-LocalizedData` 次のファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="4d268-145">For example, if the `Import-LocalizedData` command appears in the `C:\Scripts\World.ps1` script and the value of `$PSUICulture` is "ar-SA", `Import-LocalizedData` finds the following file:</span></span>

`C:\Scripts\ar-SA\World.psd1`

<span data-ttu-id="4d268-146">次に、ファイルからアラビア語のテキスト文字列を変数にインポートして `$msgTable` 、スクリプトの Data セクションに定義されている可能性のある既定の文字列を置き換え `World.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="4d268-146">Then, it imports the Arabic text strings from the file into the `$msgTable` variable, replacing any default strings that might be defined in the Data section of the `World.ps1` script.</span></span>

<span data-ttu-id="4d268-147">その結果、スクリプトが変数を使用してユーザーメッセージを表示すると、 `$msgTable` メッセージはアラビア語で表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d268-147">As a result, when the script uses the `$msgTable` variable to display user messages, the messages are displayed in Arabic.</span></span>

<span data-ttu-id="4d268-148">たとえば、次のスクリプトでは、アラビア語の "ユーザー名を入力してください" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d268-148">For example, the following script displays the "Please enter your user name" message in Arabic:</span></span>

```powershell
if (!($username)) { $msgTable.promptMsg }
```

<span data-ttu-id="4d268-149">が `Import-LocalizedData` `.psd1` の値と一致するファイルを見つけることができない場合、 `$PSUIculture` の値 `$msgTable` は置き換えられず、への呼び出しによって en-us の `$msgTable.promptMsg` フォールバック文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d268-149">If `Import-LocalizedData` cannot find a `.psd1` file that matches the value of `$PSUIculture`, the value of `$msgTable` is not replaced, and the call to `$msgTable.promptMsg` displays the fallback en-US strings.</span></span>

## <a name="examples"></a><span data-ttu-id="4d268-150">例</span><span class="sxs-lookup"><span data-stu-id="4d268-150">Examples</span></span>

<span data-ttu-id="4d268-151">この例では、スクリプトでスクリプトの国際化機能を使用して、コンピューターに設定されている言語でユーザーに曜日を表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4d268-151">This example shows how the script internationalization features are used in a script to display a day of the week to users in the language that is set on the computer.</span></span>

<span data-ttu-id="4d268-152">Sample1.ps1 スクリプトファイルの完全な一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4d268-152">The following is a complete listing of the Sample1.ps1 script file.</span></span>

<span data-ttu-id="4d268-153">スクリプトは、コマンドを含む Day ($Day) という名前のデータセクションから始まり `ConvertFrom-StringData` ます。</span><span class="sxs-lookup"><span data-stu-id="4d268-153">The script begins with a Data section named Day ($Day) that contains a `ConvertFrom-StringData` command.</span></span> <span data-ttu-id="4d268-154">に送信される式 `ConvertFrom-StringData` は、キーと値のペアの既定の UI カルチャ en-us の曜日名を含む、ここで指定した文字列です。</span><span class="sxs-lookup"><span data-stu-id="4d268-154">The expression submitted to `ConvertFrom-StringData` is a here-string that contains the day names in the default UI culture, en-US, in key/value pairs.</span></span> <span data-ttu-id="4d268-155">コマンドレットは、ここで指定した `ConvertFrom-StringData` 文字列のキーと値のペアをハッシュテーブルに変換し、変数の値として保存し `$Day` ます。</span><span class="sxs-lookup"><span data-stu-id="4d268-155">The `ConvertFrom-StringData` cmdlet converts the key/value pairs in the here-string into a hash table and then saves it in the value of the `$Day` variable.</span></span>

<span data-ttu-id="4d268-156">`Import-LocalizedData`このコマンドは、 `.psd1` 自動変数の値に一致するディレクトリ内のファイルの内容をインポート `$PSUICulture` し、変数に保存します。これにより、 `$Day` Data セクションで定義されているの値が置き換え `$Day` られます。</span><span class="sxs-lookup"><span data-stu-id="4d268-156">The `Import-LocalizedData` command imports the contents of the `.psd1` file in the directory that matches the value of the `$PSUICulture` automatic variable and then saves it in the `$Day` variable, replacing the values of `$Day` that are defined in the Data section.</span></span>

<span data-ttu-id="4d268-157">残りのコマンドは、文字列を配列に読み込んで表示します。</span><span class="sxs-lookup"><span data-stu-id="4d268-157">The remaining commands load the strings into an array and display them.</span></span>

```powershell
$Day = Data {
#culture="en-US"
ConvertFrom-StringData -StringData @'
    messageDate = Today is
    d0 = Sunday
    d1 = Monday
    d2 = Tuesday
    d3 = Wednesday
    d4 = Thursday
    d5 = Friday
    d6 = Saturday
'@
}

Import-LocalizedData -BindingVariable Day

#Build an array of weekdays.
$a = $Day.d0, $Day.d1, $Day.d2, $Day.d3, $Day.d4, $Day.d5, $Day.d6

# Get the day of the week as a number (Monday = 1).
# Index into $a to get the name of the day.
# Use string formatting to build a sentence.

"{0} {1}" -f $Day.messageDate, $a[(Get-Date -UFormat %u)] | Out-Host
```

<span data-ttu-id="4d268-158">`.psd1`スクリプトをサポートするファイルは、の値と一致する名前のスクリプトディレクトリのサブディレクトリに保存され `$PSUICulture` ます。</span><span class="sxs-lookup"><span data-stu-id="4d268-158">The `.psd1` files that support the script are saved in subdirectories of the script directory with names that match the `$PSUICulture` values.</span></span>

<span data-ttu-id="4d268-159">次に、の完全な一覧を示し `.\de-DE\sample1.psd1` ます。</span><span class="sxs-lookup"><span data-stu-id="4d268-159">The following is a complete listing of `.\de-DE\sample1.psd1`:</span></span>

```powershell
# culture="de-DE"
ConvertFrom-StringData @'
    messageDate = Heute ist
    d0 = Sonntag
    d1 = Montag
    d2 = Dienstag
    d3 = Mittwoch
    d4 = Donnerstag
    d5 = Freitag
    d6 = Samstag
'@
```

<span data-ttu-id="4d268-160">その結果、の値が de になっていないシステムで Sample.ps1 を実行すると、 `$PSUICulture` スクリプトの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4d268-160">As a result, when you run Sample.ps1 on a system on which the value of `$PSUICulture` is de-DE, the output of the script is:</span></span>

```Output
Heute ist Freitag
```

## <a name="see-also"></a><span data-ttu-id="4d268-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d268-161">See also</span></span>

- [<span data-ttu-id="4d268-162">about_Data_Sections</span><span class="sxs-lookup"><span data-stu-id="4d268-162">about_Data_Sections</span></span>](about_Data_Sections.md)
- [<span data-ttu-id="4d268-163">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="4d268-163">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)
- [<span data-ttu-id="4d268-164">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="4d268-164">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="4d268-165">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="4d268-165">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)
- [<span data-ttu-id="4d268-166">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="4d268-166">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
- [<span data-ttu-id="4d268-167">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="4d268-167">Import-LocalizedData</span></span>](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)