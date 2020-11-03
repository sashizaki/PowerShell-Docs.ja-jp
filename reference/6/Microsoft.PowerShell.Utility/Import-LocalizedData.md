---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-localizeddata?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-LocalizedData
ms.openlocfilehash: 08f959d38fc8ab861934f9a93004e67c649d9786
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "93240003"
---
# <span data-ttu-id="2c25f-103">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="2c25f-103">Import-LocalizedData</span></span>

## <span data-ttu-id="2c25f-104">概要</span><span class="sxs-lookup"><span data-stu-id="2c25f-104">SYNOPSIS</span></span>
<span data-ttu-id="2c25f-105">オペレーティング システム用に選択されている UI カルチャに基づき、言語固有のデータをスクリプトと関数にインポートします。</span><span class="sxs-lookup"><span data-stu-id="2c25f-105">Imports language-specific data into scripts and functions based on the UI culture that is selected for the operating system.</span></span>

## <span data-ttu-id="2c25f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2c25f-106">SYNTAX</span></span>

```
Import-LocalizedData [[-BindingVariable] <String>] [[-UICulture] <String>] [-BaseDirectory <String>]
 [-FileName <String>] [-SupportedCommand <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="2c25f-107">Description</span><span class="sxs-lookup"><span data-stu-id="2c25f-107">DESCRIPTION</span></span>

<span data-ttu-id="2c25f-108">コマンドレットでは、 `Import-LocalizedData` オペレーティングシステムの現在のユーザーに設定されている UI 言語と一致する名前を持つサブディレクトリから文字列を動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-108">The `Import-LocalizedData` cmdlet dynamically retrieves strings from a subdirectory whose name matches the UI language set for the current user of the operating system.</span></span> <span data-ttu-id="2c25f-109">スクリプトにより、現在のユーザーが選択している UI 言語でユーザー メッセージを表示できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="2c25f-109">It is designed to enable scripts to display user messages in the UI language selected by the current user.</span></span>

<span data-ttu-id="2c25f-110">`Import-LocalizedData``.psd1`スクリプトディレクトリの言語固有のサブディレクトリにあるファイルからデータをインポートし、コマンドで指定されたローカル変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-110">`Import-LocalizedData` imports data from `.psd1` files in language-specific subdirectories of the script directory and saves them in a local variable that is specified in the command.</span></span> <span data-ttu-id="2c25f-111">コマンドレットでは、自動変数の値に基づいてサブディレクトリとファイルを選択し `$PSUICulture` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-111">The cmdlet selects the subdirectory and file based on the value of the `$PSUICulture` automatic variable.</span></span> <span data-ttu-id="2c25f-112">スクリプトのローカル変数を使用してユーザー メッセージを表示すると、ユーザーの UI 言語でメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-112">When you use the local variable in the script to display a user message, the message appears in the user's UI language.</span></span>

<span data-ttu-id="2c25f-113">のパラメーターを使用し `Import-LocalizedData` て、代替 UI カルチャ、パス、およびファイル名を指定し、サポートされているコマンドを追加して、ファイルが見つからない場合に表示されるエラーメッセージを非表示にすることができ `.psd1` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-113">You can use the parameters of `Import-LocalizedData` to specify an alternate UI culture, path, and filename, to add supported commands, and to suppress the error message that appears if the `.psd1` files are not found.</span></span>

<span data-ttu-id="2c25f-114">この `Import-LocalizedData` コマンドレットは、Windows PowerShell 2.0 で導入されたスクリプト国際化イニシアチブをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2c25f-114">The `Import-LocalizedData` cmdlet supports the script internationalization initiative that was introduced in Windows PowerShell 2.0.</span></span> <span data-ttu-id="2c25f-115">このイニシアチブは、スクリプトを使用して現在のユーザーの UI 言語でユーザー メッセージを容易に表示できるようにして、世界中のユーザーのサービス向上を目的としています。</span><span class="sxs-lookup"><span data-stu-id="2c25f-115">This initiative aims to better serve users worldwide by making it easy for scripts to display user messages in the UI language of the current user.</span></span> <span data-ttu-id="2c25f-116">この詳細およびファイルの形式の詳細について `.psd1` は、「 [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c25f-116">For more information about this and about the format of the `.psd1` files, see [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).</span></span>

## <span data-ttu-id="2c25f-117">例</span><span class="sxs-lookup"><span data-stu-id="2c25f-117">EXAMPLES</span></span>

### <span data-ttu-id="2c25f-118">例 1: テキスト文字列をインポートする</span><span class="sxs-lookup"><span data-stu-id="2c25f-118">Example 1: Import text strings</span></span>

<span data-ttu-id="2c25f-119">この例では、テキスト文字列を変数にインポート `$Messages` します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-119">This example imports text strings into the `$Messages` variable.</span></span> <span data-ttu-id="2c25f-120">その他のすべてのコマンドレットのパラメーターの既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-120">It uses the default values of all other cmdlet parameters.</span></span>

```powershell
Import-LocalizedData -BindingVariable "Messages"
```

<span data-ttu-id="2c25f-121">コマンドがディレクトリ内の Archives.ps1 スクリプトに含まれていて、 `C:\Test` 自動変数の値 `$PsUICulture` が zh-tw である場合、は `Import-LocalizedData` `Archives.psd1` ディレクトリ内のファイルを `C:\test\zh-CN` 変数にインポートし `$Messages` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-121">If the command is included in the Archives.ps1 script in the `C:\Test` directory, and the value of the `$PsUICulture` automatic variable is zh-CN, `Import-LocalizedData` imports the `Archives.psd1` file in the `C:\test\zh-CN` directory into the `$Messages` variable.</span></span>

### <span data-ttu-id="2c25f-122">例 2: ローカライズされたデータ文字列をインポートする</span><span class="sxs-lookup"><span data-stu-id="2c25f-122">Example 2: Import localized data strings</span></span>

<span data-ttu-id="2c25f-123">この例は、スクリプトではなく、コマンドラインで実行されます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-123">This example is run at the command line not in a script.</span></span> <span data-ttu-id="2c25f-124">Test.psd1 ファイルからローカライズされたデータの文字列を取得し、コマンドラインに表示します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-124">It gets localized data strings from the Test.psd1 file and displays them at the command line.</span></span> <span data-ttu-id="2c25f-125">コマンドはスクリプトでは使用されないため、 **FileName** パラメーターが必要になります。</span><span class="sxs-lookup"><span data-stu-id="2c25f-125">Because the command is not used in a script, the **FileName** parameter is required.</span></span> <span data-ttu-id="2c25f-126">このコマンドは、 **UICulture** パラメーターを使用して、en-us カルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-126">The command uses the **UICulture** parameter to specify the en-US culture.</span></span>

```powershell
Import-LocalizedData -FileName "Test.psd1" -UICulture "en-US"
```

```Output
Name                           Value
----                           -----
Msg3                           "Use $_ to represent the object that is being processed."
Msg2                           "This command requires the credentials of a member of the Administrators group on the...
Msg1                           "The Name parameter is missing from the command."
```

<span data-ttu-id="2c25f-127">`Import-LocalizedData` ローカライズされたデータ文字列を含むハッシュテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-127">`Import-LocalizedData` returns a hash table that contains the localized data strings.</span></span>

### <span data-ttu-id="2c25f-128">例 3: UI カルチャ文字列をインポートする</span><span class="sxs-lookup"><span data-stu-id="2c25f-128">Example 3: Import UI culture strings</span></span>

```powershell
Import-LocalizedData -BindingVariable "MsgTbl" -UICulture "ar-SA" -FileName "Simple" -BaseDirectory "C:\Data\Localized"
```

<span data-ttu-id="2c25f-129">このコマンドは、テキスト文字列を `$MsgTbl` スクリプトの変数にインポートします。</span><span class="sxs-lookup"><span data-stu-id="2c25f-129">This command imports text strings into the `$MsgTbl` variable of a script.</span></span>

<span data-ttu-id="2c25f-130">**UICulture** パラメーターを使用して、 `Simple.psd1` のサブディレクトリにあるファイルからデータをインポートするようにコマンドレットに指示し `ar-SA` `C:\Data\Localized` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-130">It uses the **UICulture** parameter to direct the cmdlet to import data from the `Simple.psd1` file in the `ar-SA` subdirectory of `C:\Data\Localized`.</span></span>

### <span data-ttu-id="2c25f-131">例 4: ローカライズされたデータをスクリプトにインポートする</span><span class="sxs-lookup"><span data-stu-id="2c25f-131">Example 4: Import localized data into a script</span></span>

<span data-ttu-id="2c25f-132">この例は、単純なスクリプト内のローカライズされたデータを表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-132">This example shows how to use localized data in a simple script.</span></span>

```powershell
PS C:\> # In C:\Test\en-US\Test.psd1:

ConvertFrom-StringData @'

# English strings

Msg1 = "The Name parameter is missing from the command."
Msg2 = "This command requires the credentials of a member of the Administrators group on the computer."
Msg3 = "Use $_ to represent the object that is being processed."
'@

# In C:\Test\Test.ps1

Import-LocalizedData -BindingVariable "Messages"
Write-Host $Messages.Msg2

# In Windows PowerShell

PS C:\> .\Test.ps1

This command requires the credentials of a member of the Administrators group on the computer.
```

<span data-ttu-id="2c25f-133">この例の最初の部分では、ファイルの内容を示し `Test.psd1` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-133">The first part of the example shows the contents of the `Test.psd1` file.</span></span> <span data-ttu-id="2c25f-134">これには、 `ConvertFrom-StringData` 一連の名前付きテキスト文字列をハッシュテーブルに変換するコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c25f-134">It contains a `ConvertFrom-StringData` command that converts a series of named text strings into a hash table.</span></span> <span data-ttu-id="2c25f-135">この `Test.psd1` ファイルは、 `C:\Test` スクリプトが格納されているディレクトリの en-us サブディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="2c25f-135">The `Test.psd1` file is located in the en-US subdirectory of the `C:\Test` directory that contains the script.</span></span>

<span data-ttu-id="2c25f-136">この例の2番目の部分は、スクリプトの内容を示して `Test.ps1` います。</span><span class="sxs-lookup"><span data-stu-id="2c25f-136">The second part of the example shows the contents of the `Test.ps1` script.</span></span> <span data-ttu-id="2c25f-137">これには、 `Import-LocalizedData` 一致するファイルから変数にデータをインポートするコマンド `.psd1` と、 `$Messages` `Write-Host` 変数内のいずれかのメッセージを `$Messages` ホストプログラムに書き込むコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c25f-137">It contains an `Import-LocalizedData` command that imports the data from the matching `.psd1` file into the `$Messages` variable and a `Write-Host` command that writes one of the messages in the `$Messages` variable to the host program.</span></span>

<span data-ttu-id="2c25f-138">例の最後の部分で、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-138">The last part of the example runs the script.</span></span> <span data-ttu-id="2c25f-139">出力は、オペレーティング システムの現在のユーザーのために設定された UI の言語で正しいユーザー メッセージが表示されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="2c25f-139">The output shows that it displays the correct user message in the UI language set for the current user of the operating system.</span></span>

### <span data-ttu-id="2c25f-140">例 5: スクリプト内の既定のテキスト文字列を置き換える</span><span class="sxs-lookup"><span data-stu-id="2c25f-140">Example 5: Replace default text strings in a script</span></span>

<span data-ttu-id="2c25f-141">この例では、を使用し `Import-LocalizedData` て、スクリプトの DATA セクションに定義されている既定のテキスト文字列を置換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-141">This example shows how to use `Import-LocalizedData` to replace default text strings defined in the DATA section of a script.</span></span>

```powershell
PS C:\> # In TestScript.ps1
$UserMessages = DATA

{    ConvertFrom-StringData @'

    # English strings

        Msg1 = "Enter a name."
        Msg2 = "Enter your employee ID."
        Msg3 = "Enter your building number."
'@
}

Import-LocalizedData -BindingVariable "UserMessages"
$UserMessages.Msg1...
```

<span data-ttu-id="2c25f-142">この例では、TestScript.ps1 スクリプトの DATA セクションに、 `ConvertFrom-StringData` データセクションの内容をハッシュテーブルに変換し、変数の値に格納するコマンドが含まれてい `$UserMessages` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-142">In this example, the DATA section of the TestScript.ps1 script contains a `ConvertFrom-StringData` command that converts the contents of the DATA section to a hash table and stores in the value of the `$UserMessages` variable.</span></span>

<span data-ttu-id="2c25f-143">このスクリプトには、 `Import-LocalizedData` 変数の値で指定されたサブディレクトリ内の TestScript.psd1 ファイルから翻訳済みのテキスト文字列のハッシュテーブルをインポートするコマンドも含まれてい `$PsUICulture` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-143">The script also includes an `Import-LocalizedData` command, which imports a hash table of translated text strings from the TestScript.psd1 file in the subdirectory specified by the value of the `$PsUICulture` variable.</span></span> <span data-ttu-id="2c25f-144">コマンドがファイルを検索した場合 `.psd1` 、ファイルから翻訳された文字列を同じ変数の値に保存し `$UserMessages` 、データセクションロジックによって保存されたハッシュテーブルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="2c25f-144">If the command finds the `.psd1` file, it saves the translated strings from the file in the value of the same `$UserMessages` variable, overwriting the hash table saved by the DATA section logic.</span></span>

<span data-ttu-id="2c25f-145">3番目のコマンドは、変数内の最初のメッセージを表示し `$UserMessages` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-145">The third command displays the first message in the `$UserMessages` variable.</span></span>

<span data-ttu-id="2c25f-146">コマンドが `Import-LocalizedData` 言語のファイルを検索した場合 `.psd1` `$PsUICulture` 、変数の値には `$UserMessages` 翻訳されたテキスト文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-146">If the `Import-LocalizedData` command finds a `.psd1` file for the `$PsUICulture` language, the value of the `$UserMessages` variable contains the translated text strings.</span></span> <span data-ttu-id="2c25f-147">コマンドが何らかの理由で失敗した場合、スクリプトの DATA セクションに定義されている既定のテキスト文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-147">If the command fails for any reason, the command displays the default text strings defined in the DATA section of the script.</span></span>

### <span data-ttu-id="2c25f-148">例 6: UI カルチャが見つからない場合にエラーメッセージを表示しない</span><span class="sxs-lookup"><span data-stu-id="2c25f-148">Example 6: Suppress error messages if the UI culture is not found</span></span>

<span data-ttu-id="2c25f-149">この例で `Import-LocalizedData` は、ユーザーの UI カルチャに一致するディレクトリが見つからない場合、またはディレクトリ内のスクリプトのファイルが見つからない場合に表示されるエラーメッセージを非表示にする方法を示し `.psd1` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-149">This example shows how to suppress the error messages that appear when `Import-LocalizedData` cannot find the directories that match the user's UI culture or cannot find a `.psd1` file for the script in those directories.</span></span>

```powershell
PS C:\> # In Day1.ps1

Import-LocalizedData -BindingVariable "Day"

# In Day2.ps1

Import-LocalizedData -BindingVariable "Day" -ErrorAction:SilentlyContinue

PS C:\> .\Day1.ps1
Import-LocalizedData : Cannot find PowerShell data file 'Day1.psd1' in directory 'C:\ps-test\fr-BE\' or any parent culture directories.
At C:\ps-test\Day1.ps1:17 char:21+ Import-LocalizedData <<<<  Day
Today is Tuesday

PS C:\> .\Day2.ps1
Today is Tuesday
```

<span data-ttu-id="2c25f-150">**SilentlyContinue** の値を持つ ErrorAction 共通パラメーターを使用して、エラー メッセージを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-150">You can use the **ErrorAction** common parameter with a value of SilentlyContinue to suppress the error message.</span></span> <span data-ttu-id="2c25f-151">これは、既定の言語またはフォールバック言語でユーザーメッセージを提供し、エラーメッセージが必要ない場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="2c25f-151">This is especially useful when you have provided user messages in a default or fallback language, and no error message is needed.</span></span>

<span data-ttu-id="2c25f-152">この例では、コマンドを含む2つのスクリプト `Day1.ps1` と Day2.ps1 を比較し `Import-LocalizedData` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-152">This example compares two scripts, `Day1.ps1` and Day2.ps1, that include an `Import-LocalizedData` command.</span></span> <span data-ttu-id="2c25f-153">スクリプトは同じですが、Day2.ps1 では値がで **Erroraction** 共通パラメーターを使用する点が異なり `SilentlyContinue` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-153">The scripts are identical, except that Day2 uses the **ErrorAction** common parameter with a value of `SilentlyContinue`.</span></span>

<span data-ttu-id="2c25f-154">このサンプル出力は、UI カルチャがに設定され、 `fr-BE` その ui カルチャに一致するファイルまたはディレクトリがない場合に、両方のスクリプトを実行した結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="2c25f-154">The sample output shows the results of running both scripts when the UI culture is set to `fr-BE` and there are no matching files or directories for that UI culture.</span></span> <span data-ttu-id="2c25f-155">`Day1.ps1` エラーメッセージと英語の出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-155">`Day1.ps1` displays an error message and English output.</span></span> <span data-ttu-id="2c25f-156">`Day2.ps1` 英語の出力のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-156">`Day2.ps1` just displays the English output.</span></span>

## <span data-ttu-id="2c25f-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2c25f-157">PARAMETERS</span></span>

### <span data-ttu-id="2c25f-158">-BaseDirectory</span><span class="sxs-lookup"><span data-stu-id="2c25f-158">-BaseDirectory</span></span>

<span data-ttu-id="2c25f-159">ファイルが配置されているベースディレクトリを指定し `.psd1` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-159">Specifies the base directory where the `.psd1` files are located.</span></span> <span data-ttu-id="2c25f-160">既定では、スクリプトが配置されているディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="2c25f-160">The default is the directory where the script is located.</span></span> <span data-ttu-id="2c25f-161">`Import-LocalizedData``.psd1`ベースディレクトリの言語固有のサブディレクトリで、スクリプトのファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-161">`Import-LocalizedData` searches for the `.psd1` file for the script in a language-specific subdirectory of the base directory.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c25f-162">-BindingVariable</span><span class="sxs-lookup"><span data-stu-id="2c25f-162">-BindingVariable</span></span>

<span data-ttu-id="2c25f-163">テキスト文字列のインポート先の変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-163">Specifies the variable into which the text strings are imported.</span></span> <span data-ttu-id="2c25f-164">ドル記号を付けずに変数名を入力してください ( `$` )。</span><span class="sxs-lookup"><span data-stu-id="2c25f-164">Enter a variable name without a dollar sign (`$`).</span></span>

<span data-ttu-id="2c25f-165">Windows PowerShell 2.0 ではこのパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="2c25f-165">In Windows PowerShell 2.0, this parameter is required.</span></span> <span data-ttu-id="2c25f-166">Windows PowerShell 3.0 ではこのパラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2c25f-166">In Windows PowerShell 3.0, this parameter is optional.</span></span> <span data-ttu-id="2c25f-167">このパラメーターを省略すると、は `Import-LocalizedData` テキスト文字列のハッシュテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-167">If you omit this parameter, `Import-LocalizedData` returns a hash table of the text strings.</span></span> <span data-ttu-id="2c25f-168">ハッシュ テーブルは、パイプラインに渡されるか、コマンドラインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-168">The hash table is passed down the pipeline or displayed at the command line.</span></span>

<span data-ttu-id="2c25f-169">を使用して、 `Import-LocalizedData` スクリプトの data セクションに指定されている既定のテキスト文字列を置き換える場合は、データセクションを変数に割り当て、 **bindingvariable** パラメーターの値に data section 変数の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-169">When using `Import-LocalizedData` to replace default text strings specified in the DATA section of a script, assign the DATA section to a variable and enter the name of the DATA section variable in the value of the **BindingVariable** parameter.</span></span> <span data-ttu-id="2c25f-170">次に、 `Import-LocalizedData` インポートしたコンテンツを **bindingvariable** に保存するときに、インポートされたデータによって既定のテキスト文字列が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-170">Then, when `Import-LocalizedData` saves the imported content in the **BindingVariable** , the imported data will replace the default text strings.</span></span> <span data-ttu-id="2c25f-171">既定のテキスト文字列を指定しない場合は、任意の変数名を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-171">If you are not specifying default text strings, you can select any variable name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Variable

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c25f-172">-FileName</span><span class="sxs-lookup"><span data-stu-id="2c25f-172">-FileName</span></span>

<span data-ttu-id="2c25f-173">インポートするデータファイルの名前を指定し `.psd1)` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-173">Specifies the name of the data file (`.psd1)` to be imported.</span></span> <span data-ttu-id="2c25f-174">ファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-174">Enter a file name.</span></span> <span data-ttu-id="2c25f-175">ファイル名拡張子を含まないファイル名を指定することも、ファイル名拡張子を含むファイル名を指定することもでき `.psd1` `.psd1` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-175">You can specify a file name that does not include its `.psd1` file name extension, or you can specify the file name including the `.psd1` file name extension.</span></span> <span data-ttu-id="2c25f-176">データファイルは Unicode または UTF-8 として保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c25f-176">Data files should be saved as Unicode or UTF-8.</span></span>

<span data-ttu-id="2c25f-177">**FileName** `Import-LocalizedData` がスクリプトで使用されていない場合は、FileName パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="2c25f-177">The **FileName** parameter is required when `Import-LocalizedData` is not used in a script.</span></span>
<span data-ttu-id="2c25f-178">それ以外の場合、このパラメーターは省略可能であり、既定値はスクリプトのベース名です。</span><span class="sxs-lookup"><span data-stu-id="2c25f-178">Otherwise, the parameter is optional and the default value is the base name of the script.</span></span> <span data-ttu-id="2c25f-179">このパラメーターを使用すると `Import-LocalizedData` 、別のファイルを検索するように指示でき `.psd1` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-179">You can use this parameter to direct `Import-LocalizedData` to search for a different `.psd1` file.</span></span>

<span data-ttu-id="2c25f-180">たとえば、 **ファイル名** が省略されていて、スクリプト名が FindFiles.ps1 である場合、は `Import-LocalizedData` FindFiles.psd1 のデータファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-180">For example, if the **FileName** is omitted and the script name is FindFiles.ps1, `Import-LocalizedData` searches for the FindFiles.psd1 data file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c25f-181">-SupportedCommand</span><span class="sxs-lookup"><span data-stu-id="2c25f-181">-SupportedCommand</span></span>

<span data-ttu-id="2c25f-182">データのみを生成するコマンドレットと関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-182">Specifies cmdlets and functions that generate only data.</span></span>

<span data-ttu-id="2c25f-183">このパラメーターを使用して、記述またはテストしたコマンドレットと関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-183">Use this parameter to include cmdlets and functions that you have written or tested.</span></span> <span data-ttu-id="2c25f-184">詳細については、「 [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c25f-184">For more information, see [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c25f-185">-UICulture</span><span class="sxs-lookup"><span data-stu-id="2c25f-185">-UICulture</span></span>

<span data-ttu-id="2c25f-186">代替の UI カルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-186">Specifies an alternate UI culture.</span></span>
<span data-ttu-id="2c25f-187">既定値は、自動変数の値です `$PsUICulture` 。</span><span class="sxs-lookup"><span data-stu-id="2c25f-187">The default is the value of the `$PsUICulture` automatic variable.</span></span>
<span data-ttu-id="2c25f-188">、、などの形式で UI カルチャを入力し `<language>-<region>` `en-US` `de-DE` `ar-SA` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-188">Enter a UI culture in `<language>-<region>` format, such as `en-US`, `de-DE`, or `ar-SA`.</span></span>

<span data-ttu-id="2c25f-189">**UICulture** パラメーターの値によって、から `Import-LocalizedData` スクリプトのファイルを取得する、言語固有のサブディレクトリ (ベースディレクトリ内) が決定され `.psd1` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-189">The value of the **UICulture** parameter determines the language-specific subdirectory (within the base directory) from which `Import-LocalizedData` gets the `.psd1` file for the script.</span></span>

<span data-ttu-id="2c25f-190">このコマンドレットは、 **UICulture** パラメーターの値と同じ名前のサブディレクトリ、 `$PsUICulture` またはやなどの自動変数を検索し `de-DE` `ar-SA` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-190">The cmdlet searches for a subdirectory with the same name as the value of the **UICulture** parameter or the `$PsUICulture` automatic variable, such as `de-DE` or `ar-SA`.</span></span> <span data-ttu-id="2c25f-191">ディレクトリが見つからない場合、またはディレクトリにスクリプトのファイルが含まれていない場合は、 `.psd1` de や ar などの言語コードの名前を持つサブディレクトリが検索されます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-191">If it cannot find the directory, or the directory does not contain a `.psd1` file for the script, it searches for a subdirectory with the name of the language code, such as de or ar.</span></span> <span data-ttu-id="2c25f-192">サブディレクトリまたはファイルが見つからない場合 `.psd1` 、コマンドは失敗し、スクリプトで指定された既定の言語でデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-192">If it cannot find the subdirectory or `.psd1` file, the command fails and the data is displayed in the default language specified in the script.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c25f-193">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2c25f-193">CommonParameters</span></span>

<span data-ttu-id="2c25f-194">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2c25f-194">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2c25f-195">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c25f-195">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2c25f-196">入力</span><span class="sxs-lookup"><span data-stu-id="2c25f-196">INPUTS</span></span>

### <span data-ttu-id="2c25f-197">なし</span><span class="sxs-lookup"><span data-stu-id="2c25f-197">None</span></span>

<span data-ttu-id="2c25f-198">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="2c25f-198">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="2c25f-199">出力</span><span class="sxs-lookup"><span data-stu-id="2c25f-199">OUTPUTS</span></span>

### <span data-ttu-id="2c25f-200">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="2c25f-200">System.Collections.Hashtable</span></span>

<span data-ttu-id="2c25f-201">`Import-LocalizedData`**bindingvariable** パラメーターの値で指定された変数にハッシュテーブルを保存します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-201">`Import-LocalizedData` saves the hash table in the variable that is specified by the value of the **BindingVariable** parameter.</span></span>

## <span data-ttu-id="2c25f-202">注</span><span class="sxs-lookup"><span data-stu-id="2c25f-202">NOTES</span></span>

- <span data-ttu-id="2c25f-203">を使用する前に `Import-LocalizedData` 、ユーザーメッセージをローカライズします。</span><span class="sxs-lookup"><span data-stu-id="2c25f-203">Before using `Import-LocalizedData`, localize your user messages.</span></span> <span data-ttu-id="2c25f-204">キーと値のペアのハッシュテーブルで各ロケール (UI カルチャ) のメッセージの書式を設定し、スクリプトとファイル名の拡張子が同じであるファイルにハッシュテーブルを保存し `.psd1` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-204">Format the messages for each locale (UI culture) in a hash table of key-value pairs, and save the hash table in a file with the same name as the script and a `.psd1` file name extension.</span></span> <span data-ttu-id="2c25f-205">サポートされている各 UI カルチャのスクリプトディレクトリの下にディレクトリを作成し、ui カルチャ名を使用して、 `.psd1` 各 ui カルチャのファイルをディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-205">Create a directory under the script directory for each supported UI culture, and then save the `.psd1` file for each UI culture in the directory with the UI culture name.</span></span>

  <span data-ttu-id="2c25f-206">たとえば、de-DE ロケールのユーザー メッセージをローカライズし、ハッシュ テーブルで書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-206">For example, localize your user messages for the de-DE locale and format them in a hash table.</span></span>
  <span data-ttu-id="2c25f-207">ハッシュテーブルをファイルに保存 `<ScriptName>.psd1` します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-207">Save the hash table in a `<ScriptName>.psd1` file.</span></span> <span data-ttu-id="2c25f-208">次に、 `de-DE` スクリプトディレクトリの下にサブディレクトリを作成し、ドイツ語 `<ScriptName\>.psd1` ファイルをサブディレクトリに保存し `de-DE` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-208">Then create a `de-DE` subdirectory under the script directory, and save the German `<ScriptName\>.psd1` file in the `de-DE` subdirectory.</span></span>
  <span data-ttu-id="2c25f-209">サポートしているロケールごとにこのメソッドを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-209">Repeat this method for each locale that you support.</span></span>

- <span data-ttu-id="2c25f-210">`Import-LocalizedData` スクリプトのローカライズされたユーザーメッセージの構造化検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-210">`Import-LocalizedData` performs a structured search for the localized user messages for a script.</span></span>

  <span data-ttu-id="2c25f-211">`Import-LocalizedData` スクリプトファイルが格納されているディレクトリ (または **Basedirectory** パラメーターの値) の検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-211">`Import-LocalizedData` begins the search in the directory where the script file is located (or the value of the **BaseDirectory** parameter).</span></span> <span data-ttu-id="2c25f-212">次に、ベースディレクトリ内で、変数の値と同じ名前のサブディレクトリ `$PsUICulture` (または、 **UICulture** パラメーターの値) を検索し `de-DE` `ar-SA` ます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-212">It then searches within the base directory for a subdirectory with the same name as the value of the `$PsUICulture` variable (or the value of the **UICulture** parameter), such as `de-DE` or `ar-SA`.</span></span> <span data-ttu-id="2c25f-213">次に、そのサブディレクトリで、 `.psd1` スクリプトと同じ名前のファイル (または **FileName** パラメーターの値) を検索します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-213">Then, it searches in that subdirectory for a `.psd1` file with the same name as the script (or the value of the **FileName** parameter).</span></span>

  <span data-ttu-id="2c25f-214">が `Import-LocalizedData` UI カルチャの名前を持つサブディレクトリを見つけられない場合、またはサブディレクトリにスクリプト用のファイルが含まれていない場合は `.psd1` 、 `.psd1` de や ar などの言語コードの名前を持つサブディレクトリで、スクリプトのファイルが検索されます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-214">If `Import-LocalizedData` cannot find a subdirectory with the name of the UI culture, or the subdirectory does not contain a `.psd1` file for the script, it searches for a `.psd1` file for the script in a subdirectory with the name of the language code, such as de or ar.</span></span> <span data-ttu-id="2c25f-215">サブディレクトリまたはファイルが見つからない場合、 `.psd1` コマンドは失敗し、スクリプト内の既定の言語でデータが表示され、データをインポートできなかったことを示すエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-215">If it cannot find the subdirectory or `.psd1` file, the command fails, the data is displayed in the default language in the script, and an error message is displayed explaining that the data could not be imported.</span></span> <span data-ttu-id="2c25f-216">メッセージを非表示にして適切に失敗させるには、SilentlyContinue の値を指定した **Erroraction** 共通パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2c25f-216">To suppress the message and fail gracefully, use the **ErrorAction** common parameter with a value of SilentlyContinue.</span></span>

  <span data-ttu-id="2c25f-217">が `Import-LocalizedData` サブディレクトリとファイルを検出すると `.psd1` 、ユーザーメッセージのハッシュテーブルをコマンドの **bindingvariable** パラメーターの値にインポートします。</span><span class="sxs-lookup"><span data-stu-id="2c25f-217">If `Import-LocalizedData` finds the subdirectory and the `.psd1` file, it imports the hash table of user messages into the value of the **BindingVariable** parameter in the command.</span></span> <span data-ttu-id="2c25f-218">次に、変数のハッシュ テーブルからメッセージを表示すると、ローカライズされたメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c25f-218">Then, when you display a message from the hash table in the variable, the localized message is displayed.</span></span>

  <span data-ttu-id="2c25f-219">詳細については、「 [about_Script_Internationalization](../Microsoft.Powershell.Core/About/about_Script_Internationalization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c25f-219">For more information, see [about_Script_Internationalization](../Microsoft.Powershell.Core/About/about_Script_Internationalization.md).</span></span>

## <span data-ttu-id="2c25f-220">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2c25f-220">RELATED LINKS</span></span>

[<span data-ttu-id="2c25f-221">Write-Host</span><span class="sxs-lookup"><span data-stu-id="2c25f-221">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="2c25f-222">Import-PowerShellDataFile</span><span class="sxs-lookup"><span data-stu-id="2c25f-222">Import-PowerShellDataFile</span></span>](Import-PowerShellDataFile.md)
