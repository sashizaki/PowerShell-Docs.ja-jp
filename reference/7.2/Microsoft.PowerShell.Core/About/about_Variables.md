---
description: PowerShell で使用できる値を変数に格納する方法について説明します。
Locale: en-US
ms.date: 11/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Variables
ms.openlocfilehash: 8d8c8d3098d33980c9c802bf00846a21e8baeb40
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603023"
---
# <a name="about-variables"></a><span data-ttu-id="20c6a-103">変数について</span><span class="sxs-lookup"><span data-stu-id="20c6a-103">About Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="20c6a-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="20c6a-104">Short description</span></span>

<span data-ttu-id="20c6a-105">PowerShell で使用できる値を変数に格納する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-105">Describes how variables store values that can be used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="20c6a-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="20c6a-106">Long description</span></span>

<span data-ttu-id="20c6a-107">すべての種類の値を PowerShell 変数に格納できます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-107">You can store all types of values in PowerShell variables.</span></span> <span data-ttu-id="20c6a-108">たとえば、コマンドの結果を格納したり、名前、パス、設定、値などのコマンドや式で使用される要素を格納したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-108">For example, store the results of commands, and store elements that are used in commands and expressions, such as names, paths, settings, and values.</span></span>

<span data-ttu-id="20c6a-109">変数は、値が格納されるメモリの単位です。</span><span class="sxs-lookup"><span data-stu-id="20c6a-109">A variable is a unit of memory in which values are stored.</span></span> <span data-ttu-id="20c6a-110">PowerShell では、変数は、、、などのドル記号 () で始まるテキスト文字列によって表され `$` `$a` `$process` `$my_var` ます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-110">In PowerShell, variables are represented by text strings that begin with a dollar sign (`$`), such as `$a`, `$process`, or `$my_var`.</span></span>

<span data-ttu-id="20c6a-111">変数名の大文字と小文字は区別されず、スペースや特殊文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-111">Variable names aren't case-sensitive, and can include spaces and special characters.</span></span> <span data-ttu-id="20c6a-112">ただし、特殊文字やスペースを含む変数名は使用するのが困難であり、避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="20c6a-112">But, variable names that include special characters and spaces are difficult to use and should be avoided.</span></span> <span data-ttu-id="20c6a-113">詳細については、「 [特殊文字を含む変数名](#variable-names-that-include-special-characters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c6a-113">For more information, see [Variable names that include special characters](#variable-names-that-include-special-characters).</span></span>

<span data-ttu-id="20c6a-114">PowerShell には、さまざまな種類の変数があります。</span><span class="sxs-lookup"><span data-stu-id="20c6a-114">There are several different types of variables in PowerShell.</span></span>

- <span data-ttu-id="20c6a-115">ユーザーが作成した変数: ユーザーが作成した変数は、ユーザーによって作成および管理されます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-115">User-created variables: User-created variables are created and maintained by the user.</span></span> <span data-ttu-id="20c6a-116">既定では、powershell コマンドラインで作成した変数は、PowerShell ウィンドウが開いている間だけ存在します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-116">By default, the variables that you create at the PowerShell command line exist only while the PowerShell window is open.</span></span> <span data-ttu-id="20c6a-117">PowerShell ウィンドウが閉じられると、変数は削除されます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-117">When the PowerShell windows is closed, the variables are deleted.</span></span> <span data-ttu-id="20c6a-118">変数を保存するには、PowerShell プロファイルに変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-118">To save a variable, add it to your PowerShell profile.</span></span> <span data-ttu-id="20c6a-119">スクリプトには、グローバル、スクリプト、またはローカルスコープの変数を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-119">You can also create variables in scripts with global, script, or local scope.</span></span>

- <span data-ttu-id="20c6a-120">自動変数: 自動変数は、PowerShell の状態を格納します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-120">Automatic variables: Automatic variables store the state of PowerShell.</span></span> <span data-ttu-id="20c6a-121">これらの変数は PowerShell によって作成され、それらの値の精度を維持するために PowerShell が必要に応じて値を変更します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-121">These variables are created by PowerShell, and PowerShell changes their values as required to maintain their accuracy.</span></span> <span data-ttu-id="20c6a-122">ユーザーはこれらの変数の値を変更できません。</span><span class="sxs-lookup"><span data-stu-id="20c6a-122">Users can't change the value of these variables.</span></span> <span data-ttu-id="20c6a-123">たとえば、変数には、 `$PSHOME` PowerShell インストールディレクトリへのパスが格納されます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-123">For example, the `$PSHOME` variable stores the path to the PowerShell installation directory.</span></span>

  <span data-ttu-id="20c6a-124">詳細、一覧、および自動変数の説明については、「 [about_Automatic_Variables](about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c6a-124">For more information, a list, and a description of the automatic variables, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

- <span data-ttu-id="20c6a-125">ユーザー設定変数: ユーザー設定を PowerShell に格納します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-125">Preference variables: Preference variables store user preferences for PowerShell.</span></span> <span data-ttu-id="20c6a-126">これらの変数は PowerShell によって作成され、既定値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-126">These variables are created by PowerShell and are populated with default values.</span></span> <span data-ttu-id="20c6a-127">ユーザーは、これらの変数の値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-127">Users can change the values of these variables.</span></span> <span data-ttu-id="20c6a-128">たとえば、変数は、 `$MaximumHistoryCount` セッション履歴内のエントリの最大数を決定します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-128">For example, the `$MaximumHistoryCount` variable determines the maximum number of entries in the session history.</span></span>

  <span data-ttu-id="20c6a-129">詳細、一覧、およびユーザー設定変数の説明については、「 [about_Preference_Variables](about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c6a-129">For more information, a list, and a description of the preference variables, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

## <a name="working-with-variables"></a><span data-ttu-id="20c6a-130">変数の操作</span><span class="sxs-lookup"><span data-stu-id="20c6a-130">Working with variables</span></span>

<span data-ttu-id="20c6a-131">新しい変数を作成するには、代入ステートメントを使用して変数に値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-131">To create a new variable, use an assignment statement to assign a value to the variable.</span></span> <span data-ttu-id="20c6a-132">変数を使用する前に宣言する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="20c6a-132">You don't have to declare the variable before using it.</span></span> <span data-ttu-id="20c6a-133">すべての変数の既定値は `$null` です。</span><span class="sxs-lookup"><span data-stu-id="20c6a-133">The default value of all variables is `$null`.</span></span>

<span data-ttu-id="20c6a-134">PowerShell セッションのすべての変数の一覧を取得するには、「」と入力 `Get-Variable` します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-134">To get a list of all the variables in your PowerShell session, type `Get-Variable`.</span></span> <span data-ttu-id="20c6a-135">変数名は、 `$` 変数を参照するために使用される前のドル () 記号なしで表示されます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-135">The variable names are displayed without the preceding dollar (`$`) sign that is used to reference variables.</span></span>

<span data-ttu-id="20c6a-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-136">For example:</span></span>

```powershell
$MyVariable = 1, 2, 3

$Path = "C:\Windows\System32"
```

<span data-ttu-id="20c6a-137">変数は、コマンドの結果を格納するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-137">Variables are useful for storing the results of commands.</span></span>

<span data-ttu-id="20c6a-138">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-138">For example:</span></span>

```powershell
$Processes = Get-Process

$Today = (Get-Date).DateTime
```

<span data-ttu-id="20c6a-139">変数の値を表示するには、変数名の前にドル記号 () を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-139">To display the value of a variable, type the variable name, preceded by a dollar sign (`$`).</span></span>

<span data-ttu-id="20c6a-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-140">For example:</span></span>

```powershell
$MyVariable
```

```Output
1
2
3
```

```powershell
$Today
```

```Output
Tuesday, September 3, 2019 09:46:46
```

<span data-ttu-id="20c6a-141">変数の値を変更するには、変数に新しい値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-141">To change the value of a variable, assign a new value to the variable.</span></span>

<span data-ttu-id="20c6a-142">次の例では、変数の値を表示し、 `$MyVariable` 変数の値を変更して、新しい値を表示します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-142">The following examples display the value of the `$MyVariable` variable, changes the value of the variable, and then displays the new value.</span></span>

```powershell
$MyVariable = 1, 2, 3
$MyVariable
```

```Output
1
2
3
```

```powershell
$MyVariable = "The green cat."
$MyVariable
```

```Output
The green cat.
```

<span data-ttu-id="20c6a-143">変数の値を削除するには、コマンドレットを使用する `Clear-Variable` か、値をに変更し `$null` ます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-143">To delete the value of a variable, use the `Clear-Variable` cmdlet or change the value to `$null`.</span></span>

```powershell
Clear-Variable -Name MyVariable
```

```powershell
$MyVariable = $null
```

<span data-ttu-id="20c6a-144">変数を削除するには、 [削除変数](xref:Microsoft.PowerShell.Utility.Remove-Variable) または [削除項目](xref:Microsoft.PowerShell.Management.Remove-Item)を使用します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-144">To delete the variable, use [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) or [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item).</span></span>

```powershell
Remove-Variable -Name MyVariable
```

```powershell
Remove-Item -Path Variable:\MyVariable
```

## <a name="types-of-variables"></a><span data-ttu-id="20c6a-145">変数の種類</span><span class="sxs-lookup"><span data-stu-id="20c6a-145">Types of variables</span></span>

<span data-ttu-id="20c6a-146">整数、文字列、配列、ハッシュテーブルなど、任意の型のオブジェクトを変数に格納できます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-146">You can store any type of object in a variable, including integers, strings, arrays, and hash tables.</span></span> <span data-ttu-id="20c6a-147">およびは、プロセス、サービス、イベントログ、およびコンピューターを表すオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="20c6a-147">And, objects that represent processes, services, event logs, and computers.</span></span>

<span data-ttu-id="20c6a-148">PowerShell 変数は、厳密に型指定されていません。つまり、特定の種類のオブジェクトに限定されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-148">PowerShell variables are loosely typed, which means that they aren't limited to a particular type of object.</span></span> <span data-ttu-id="20c6a-149">1つの変数に、異なる種類のオブジェクトのコレクション (配列) を同時に含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-149">A single variable can even contain a collection, or array, of different types of objects at the same time.</span></span>

<span data-ttu-id="20c6a-150">変数のデータ型は、変数の値の .NET 型によって決まります。</span><span class="sxs-lookup"><span data-stu-id="20c6a-150">The data type of a variable is determined by the .NET types of the values of the variable.</span></span> <span data-ttu-id="20c6a-151">変数のオブジェクト型を表示するには、 [Get Member](xref:Microsoft.PowerShell.Utility.Get-Member)を使用します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-151">To view a variable's object type, use [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member).</span></span>

<span data-ttu-id="20c6a-152">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-152">For example:</span></span>

```powershell
$a = 12                         # System.Int32
$a = "Word"                     # System.String
$a = 12, "Word"                 # array of System.Int32, System.String
$a = Get-ChildItem C:\Windows   # FileInfo and DirectoryInfo types
```

<span data-ttu-id="20c6a-153">型属性とキャスト表記を使用して、変数に特定のオブジェクト型またはその型に変換できるオブジェクトのみを含めることができるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-153">You can use a type attribute and cast notation to ensure that a variable can contain only specific object types or objects that can be converted to that type.</span></span> <span data-ttu-id="20c6a-154">別の型の値を割り当てようとすると、PowerShell は値をその型に変換しようとします。</span><span class="sxs-lookup"><span data-stu-id="20c6a-154">If you try to assign a value of another type, PowerShell tries to convert the value to its type.</span></span> <span data-ttu-id="20c6a-155">型を変換できない場合、代入ステートメントは失敗します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-155">If the type can't be converted, the assignment statement fails.</span></span>

<span data-ttu-id="20c6a-156">キャスト表記を使用するには、(代入ステートメントの左側の) 変数名の前に、角かっこで囲まれた型名を入力します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-156">To use cast notation, enter a type name, enclosed in brackets, before the variable name (on the left side of the assignment statement).</span></span> <span data-ttu-id="20c6a-157">次の例では、整数のみを含む変数、文字列のみを含むことができる変数、 `$number` `$words` および `$dates` **DateTime** オブジェクトのみを含むことができる変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-157">The following example creates a `$number` variable that can contain only integers, a `$words` variable that can contain only strings, and a `$dates` variable that can contain only **DateTime** objects.</span></span>

```powershell
[int]$number = 8
$number = "12345"  # The string is converted to an integer.
$number = "Hello"
```

```Output
Cannot convert value "Hello" to type "System.Int32". Error: "Input string was
 not in a correct format."
At line:1 char:1
+ $number = "Hello"
+ ~~~~~~~~~~~~~~~~~
+ CategoryInfo          : MetadataError: (:) [],
    ArgumentTransformationMetadataException
+ FullyQualifiedErrorId : RuntimeException
```

```powershell
[string]$words = "Hello"
$words = 2       # The integer is converted to a string.
$words += 10     # The plus (+) sign concatenates the strings.
$words
```

```Output
210
```

```powershell
[datetime] $dates = "09/12/91"  # The string is converted to a DateTime object.
$dates
```

```Output
Thursday, September 12, 1991 00:00:00
```

```powershell
$dates = 10    # The integer is converted to a DateTime object.
$dates
```

```Output
Monday, January 1, 0001 00:00:00
```

## <a name="using-variables-in-commands-and-expressions"></a><span data-ttu-id="20c6a-158">コマンドおよび式での変数の使用</span><span class="sxs-lookup"><span data-stu-id="20c6a-158">Using variables in commands and expressions</span></span>

<span data-ttu-id="20c6a-159">コマンドまたは式で変数を使用するには、変数名の前にドル () 記号を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-159">To use a variable in a command or expression, type the variable name, preceded by the dollar (`$`) sign.</span></span>

<span data-ttu-id="20c6a-160">変数名とドル記号が引用符で囲まれていない場合、または二重引用符 () で囲まれている場合は、 `"` 変数の値がコマンドまたは式で使用されます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-160">If the variable name and dollar sign aren't enclosed in quotation marks, or if they're enclosed in double quotation (`"`) marks, the value of the variable is used in the command or expression.</span></span>

<span data-ttu-id="20c6a-161">変数名とドル記号を単一引用符 () で囲むと、 `'` 変数名が式で使用されます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-161">If the variable name and dollar sign are enclosed in single quotation (`'`) marks, the variable name is used in the expression.</span></span>

<span data-ttu-id="20c6a-162">PowerShell での引用符の使用の詳細については、「 [about_Quoting_Rules](about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c6a-162">For more information about using quotation marks in PowerShell, see [about_Quoting_Rules](about_Quoting_Rules.md).</span></span>

<span data-ttu-id="20c6a-163">この例では、変数の値を取得し `$PROFILE` ます。これは、powershell コンソールの powershell ユーザープロファイルファイルへのパスです。</span><span class="sxs-lookup"><span data-stu-id="20c6a-163">This example gets the value of the `$PROFILE` variable, which is the path to the PowerShell user profile file in the PowerShell console.</span></span>

```powershell
$PROFILE
```

```Output
C:\Users\User01\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
```

<span data-ttu-id="20c6a-164">この例では、 **notepad.exe** で PowerShell プロファイルを開くことができる2つのコマンドを示しています。</span><span class="sxs-lookup"><span data-stu-id="20c6a-164">In this example, two commands are shown that can open the PowerShell profile in **notepad.exe**.</span></span> <span data-ttu-id="20c6a-165">二重引用符 () マークの例では `"` 、変数の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-165">The example with double-quote (`"`) marks uses the variable's value.</span></span>

```powershell
notepad $PROFILE

notepad "$PROFILE"
```

<span data-ttu-id="20c6a-166">次の例では、変数を `'` リテラルテキストとして扱う一重引用符 () を使用します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-166">The following examples use single-quote (`'`) marks that treat the variable as literal text.</span></span>

```powershell
'$PROFILE'
```

```Output
$PROFILE
```

```powershell
'Use the $PROFILE variable.'
```

```Output
Use the $PROFILE variable.
```

## <a name="variable-names-that-include-special-characters"></a><span data-ttu-id="20c6a-167">特殊文字を含む変数名</span><span class="sxs-lookup"><span data-stu-id="20c6a-167">Variable names that include special characters</span></span>

<span data-ttu-id="20c6a-168">変数名はドル ( `$` ) 記号で始まり、英数字と特殊文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-168">Variable names begin with a dollar (`$`) sign and can include alphanumeric characters and special characters.</span></span> <span data-ttu-id="20c6a-169">変数名の長さは、使用可能なメモリによってのみ制限されます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-169">The variable name length is limited only by available memory.</span></span>

<span data-ttu-id="20c6a-170">変数名には英数字とアンダースコア () 文字のみが含まれることがベストプラクティスです `_` 。</span><span class="sxs-lookup"><span data-stu-id="20c6a-170">The best practice is that variable names include only alphanumeric characters and the underscore (`_`) character.</span></span> <span data-ttu-id="20c6a-171">空白や特殊文字を含む変数名は使用するのが困難であり、避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="20c6a-171">Variable names that include spaces and other special characters, are difficult to use and should be avoided.</span></span>

<span data-ttu-id="20c6a-172">英数字の変数名には、次の文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-172">Alphanumeric variable names can contain these characters:</span></span>

- <span data-ttu-id="20c6a-173">これらのカテゴリの Unicode 文字: **Lu**、 **Ll**、 **Lt**、 **Lm**、 **Lo**、 **Nd**。</span><span class="sxs-lookup"><span data-stu-id="20c6a-173">Unicode characters from these categories: **Lu**, **Ll**, **Lt**, **Lm**, **Lo**, or **Nd**.</span></span>
- <span data-ttu-id="20c6a-174">アンダースコア ( `_` ) 文字。</span><span class="sxs-lookup"><span data-stu-id="20c6a-174">Underscore (`_`) character.</span></span>
- <span data-ttu-id="20c6a-175">疑問符 ( `?` ) 文字。</span><span class="sxs-lookup"><span data-stu-id="20c6a-175">Question mark (`?`) character.</span></span>

<span data-ttu-id="20c6a-176">次の一覧には、Unicode カテゴリの説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="20c6a-176">The following list contains the Unicode category descriptions.</span></span> <span data-ttu-id="20c6a-177">詳細については、「 [「system.globalization.unicodecategory](/dotnet/api/system.globalization.unicodecategory)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c6a-177">For more information, see [UnicodeCategory](/dotnet/api/system.globalization.unicodecategory).</span></span>

- <span data-ttu-id="20c6a-178">**Lu** -UppercaseLetter</span><span class="sxs-lookup"><span data-stu-id="20c6a-178">**Lu** - UppercaseLetter</span></span>
- <span data-ttu-id="20c6a-179">**Ll** -LowercaseLetter</span><span class="sxs-lookup"><span data-stu-id="20c6a-179">**Ll** - LowercaseLetter</span></span>
- <span data-ttu-id="20c6a-180">**Lt** -TitlecaseLetter</span><span class="sxs-lookup"><span data-stu-id="20c6a-180">**Lt** - TitlecaseLetter</span></span>
- <span data-ttu-id="20c6a-181">**Lm** -ModifierLetter</span><span class="sxs-lookup"><span data-stu-id="20c6a-181">**Lm** - ModifierLetter</span></span>
- <span data-ttu-id="20c6a-182">**Lo** -その他の文字</span><span class="sxs-lookup"><span data-stu-id="20c6a-182">**Lo** - OtherLetter</span></span>
- <span data-ttu-id="20c6a-183">**Nd** -DecimalDigitNumber</span><span class="sxs-lookup"><span data-stu-id="20c6a-183">**Nd** - DecimalDigitNumber</span></span>

<span data-ttu-id="20c6a-184">スペースや特殊文字を含む変数名を作成または表示するには、変数名を中かっこ ( `{}` ) で囲みます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-184">To create or display a variable name that includes spaces or special characters, enclose the variable name with the curly braces (`{}`) characters.</span></span>
<span data-ttu-id="20c6a-185">中かっこでは、変数名の文字をリテラルとして解釈します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-185">The curly braces direct PowerShell to interpret the variable name's characters as literals.</span></span>

<span data-ttu-id="20c6a-186">特殊文字の変数名には、次の文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-186">Special character variable names can contain these characters:</span></span>

- <span data-ttu-id="20c6a-187">任意の Unicode 文字。ただし、次の例外があります。</span><span class="sxs-lookup"><span data-stu-id="20c6a-187">Any Unicode character, with the following exceptions:</span></span>
  - <span data-ttu-id="20c6a-188">右中かっこ ( `}` ) 文字 (U + 007D)。</span><span class="sxs-lookup"><span data-stu-id="20c6a-188">The closing curly brace (`}`) character (U+007D).</span></span>
  - <span data-ttu-id="20c6a-189">バックティック ( `` ` `` ) 文字 (U + 0060)。</span><span class="sxs-lookup"><span data-stu-id="20c6a-189">The backtick (`` ` ``) character (U+0060).</span></span> <span data-ttu-id="20c6a-190">バックティックは、リテラルとして扱われるように Unicode 文字をエスケープするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-190">The backtick is used to escape Unicode characters so they're treated as literals.</span></span>

<span data-ttu-id="20c6a-191">PowerShell には `$$` 、 `$?` `$^` 英数字と特殊文字を含む、、、などの変数が予約されてい `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-191">PowerShell has reserved variables such as `$$`, `$?`, `$^`, and `$_` that contain alphanumeric and special characters.</span></span> <span data-ttu-id="20c6a-192">詳細については、「 [about_Automatic_Variables](about_automatic_variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c6a-192">For more information, see [about_Automatic_Variables](about_automatic_variables.md).</span></span>

<span data-ttu-id="20c6a-193">たとえば、次のコマンドは、という名前の変数を作成し `save-items` ます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-193">For example, the following command creates the variable named `save-items`.</span></span> <span data-ttu-id="20c6a-194">変数名には `{}` ハイフン () の特殊文字が含まれているため、中かっこ () が必要です `-` 。</span><span class="sxs-lookup"><span data-stu-id="20c6a-194">The curly braces (`{}`) are needed because variable name includes a hyphen (`-`) special character.</span></span>

```powershell
${save-items} = "a", "b", "c"
${save-items}
```

```Output
a
b
c
```

<span data-ttu-id="20c6a-195">環境変数によって表されるディレクトリ内の子項目を取得するコマンドを次に示し `ProgramFiles(x86)` ます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-195">The following command gets the child items in the directory that is represented by the `ProgramFiles(x86)` environment variable.</span></span>

```powershell
Get-ChildItem ${env:ProgramFiles(x86)}
```

<span data-ttu-id="20c6a-196">中かっこを含む変数名を参照するには、変数名を中かっこで囲み、バックティック文字を使用して中かっこをエスケープします。</span><span class="sxs-lookup"><span data-stu-id="20c6a-196">To reference a variable name that includes braces, enclose the variable name in braces, and use the backtick character to escape the braces.</span></span> <span data-ttu-id="20c6a-197">たとえば、という名前の変数を作成するには、次のように `this{value}is` 入力します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-197">For example, to create a variable named `this{value}is` type:</span></span>

```powershell
${this`{value`}is} = "This variable name uses braces and backticks."
${this`{value`}is}
```

```Output
This variable name uses braces and backticks.
```

## <a name="variables-and-scope"></a><span data-ttu-id="20c6a-198">変数とスコープ</span><span class="sxs-lookup"><span data-stu-id="20c6a-198">Variables and scope</span></span>

<span data-ttu-id="20c6a-199">既定では、変数は、作成されたスコープ内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-199">By default, variables are only available in the scope in which they're created.</span></span>

<span data-ttu-id="20c6a-200">たとえば、関数で作成した変数は、関数内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-200">For example, a variable that you create in a function is available only within the function.</span></span> <span data-ttu-id="20c6a-201">スクリプトで作成した変数は、スクリプト内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-201">A variable that you create in a script is available only within the script.</span></span> <span data-ttu-id="20c6a-202">スクリプトをドットソースで作成すると、変数は現在のスコープに追加されます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-202">If you dot-source the script, the variable is added to the current scope.</span></span> <span data-ttu-id="20c6a-203">詳細については、「 [about_Scopes](about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c6a-203">For more information, see [about_Scopes](about_Scopes.md).</span></span>

<span data-ttu-id="20c6a-204">スコープ修飾子を使用して、変数の既定のスコープを変更できます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-204">You can use a scope modifier to change the default scope of the variable.</span></span> <span data-ttu-id="20c6a-205">次の式では、という名前の変数が作成され `Computers` ます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-205">The following expression creates a variable named `Computers`.</span></span> <span data-ttu-id="20c6a-206">変数は、スクリプトまたは関数で作成された場合でも、グローバルスコープを持ちます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-206">The variable has a global scope, even when it's created in a script or function.</span></span>

```powershell
$Global:Computers = "Server01"
```

<span data-ttu-id="20c6a-207">セッションが不足しているスクリプトまたはコマンドについては、 `Using` 呼び出し元のセッションスコープから変数の値を埋め込むためにスコープ修飾子が必要です。これにより、セッションコードが不足してしまうことがあります。</span><span class="sxs-lookup"><span data-stu-id="20c6a-207">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span>

<span data-ttu-id="20c6a-208">詳細については、「 [about_Remote_Variables](about_Remote_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c6a-208">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="saving-variables"></a><span data-ttu-id="20c6a-209">保存 (変数を)</span><span class="sxs-lookup"><span data-stu-id="20c6a-209">Saving variables</span></span>

<span data-ttu-id="20c6a-210">作成した変数は、作成元のセッションでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-210">Variables that you create are available only in the session in which you create them.</span></span> <span data-ttu-id="20c6a-211">セッションを閉じたときに失われます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-211">They're lost when you close your session.</span></span>

<span data-ttu-id="20c6a-212">開始するすべての PowerShell セッションで変数を作成するには、PowerShell プロファイルに変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-212">To create the variable in every PowerShell session that you start, add the variable to your PowerShell profile.</span></span>

<span data-ttu-id="20c6a-213">たとえば、すべての PowerShell セッションで変数の値を変更するには、 `$VerbosePreference` 次のコマンドを powershell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-213">For example, to change the value of the `$VerbosePreference` variable in every PowerShell session, add the following command to your PowerShell profile.</span></span>

```powershell
$VerbosePreference = "Continue"
```

<span data-ttu-id="20c6a-214">このコマンドを PowerShell プロファイルに追加するには、 `$PROFILE` **notepad.exe** などのテキストエディターでファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-214">You can add this command to your PowerShell profile by opening the `$PROFILE` file in a text editor, such as **notepad.exe**.</span></span> <span data-ttu-id="20c6a-215">PowerShell プロファイルの詳細については、「 [about_Profiles](about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c6a-215">For more information about PowerShell profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="the-variable-drive"></a><span data-ttu-id="20c6a-216">Variable: ドライブ</span><span class="sxs-lookup"><span data-stu-id="20c6a-216">The Variable: drive</span></span>

<span data-ttu-id="20c6a-217">PowerShell 変数プロバイダーは、 `Variable:` ファイルシステムドライブのように見えるドライブを作成しますが、セッション内の変数とその値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="20c6a-217">The PowerShell Variable provider creates a `Variable:` drive that looks and acts like a file system drive, but it contains the variables in your session and their values.</span></span>

<span data-ttu-id="20c6a-218">ドライブに変更するには `Variable:` 、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-218">To change to the `Variable:` drive, use the following command:</span></span>

```powershell
Set-Location Variable:
```

<span data-ttu-id="20c6a-219">ドライブ内の項目と変数の一覧を表示するに `Variable:` `Get-Item` は、コマンドレットまたはコマンドレットを使用し `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-219">To list the items and variables in the `Variable:` drive, use the `Get-Item` or `Get-ChildItem` cmdlets.</span></span>

```powershell
Get-ChildItem Variable:
```

<span data-ttu-id="20c6a-220">特定の変数の値を取得するには、ファイルシステム表記を使用して、ドライブ名と変数名を指定します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-220">To get the value of a particular variable, use file system notation to specify the name of the drive and the name of the variable.</span></span> <span data-ttu-id="20c6a-221">たとえば、自動変数を取得するには、 `$PSCulture` 次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-221">For example, to get the `$PSCulture` automatic variable, use the following command.</span></span>

```powershell
Get-Item Variable:\PSCulture
```

```Output
Name                           Value
----                           -----
PSCulture                      en-US
```

<span data-ttu-id="20c6a-222">ドライブと PowerShell 変数プロバイダーに関する詳細情報を表示するには `Variable:` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-222">To display more information about the `Variable:` drive and the PowerShell Variable provider, type:</span></span>

```powershell
Get-Help Variable
```

## <a name="variable-syntax-with-provider-paths"></a><span data-ttu-id="20c6a-223">プロバイダーパスを使用した変数構文</span><span class="sxs-lookup"><span data-stu-id="20c6a-223">Variable syntax with provider paths</span></span>

<span data-ttu-id="20c6a-224">プロバイダーパスをドル ( `$` ) 記号でプレフィックスし、 [IContentCmdletProvider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) インターフェイスを実装する任意のプロバイダーのコンテンツにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="20c6a-224">You can prefix a provider path with the dollar (`$`) sign, and access the content of any provider that implements the [IContentCmdletProvider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) interface.</span></span>

<span data-ttu-id="20c6a-225">次の組み込みの PowerShell プロバイダーでは、この表記がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="20c6a-225">The following built-in PowerShell providers support this notation:</span></span>

- [<span data-ttu-id="20c6a-226">about_Environment_Provider</span><span class="sxs-lookup"><span data-stu-id="20c6a-226">about_Environment_Provider</span></span>](about_Environment_Provider.md)
- [<span data-ttu-id="20c6a-227">about_Variable_Provider</span><span class="sxs-lookup"><span data-stu-id="20c6a-227">about_Variable_Provider</span></span>](about_Variable_Provider.md)
- [<span data-ttu-id="20c6a-228">about_Function_Provider</span><span class="sxs-lookup"><span data-stu-id="20c6a-228">about_Function_Provider</span></span>](about_Function_Provider.md)
- [<span data-ttu-id="20c6a-229">about_Alias_Provider</span><span class="sxs-lookup"><span data-stu-id="20c6a-229">about_Alias_Provider</span></span>](about_Alias_Provider.md)

## <a name="the-variable-cmdlets"></a><span data-ttu-id="20c6a-230">変数コマンドレット</span><span class="sxs-lookup"><span data-stu-id="20c6a-230">The variable cmdlets</span></span>

<span data-ttu-id="20c6a-231">PowerShell には、変数を管理するために設計された一連のコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="20c6a-231">PowerShell includes a set of cmdlets that are designed to manage variables.</span></span>

<span data-ttu-id="20c6a-232">コマンドレットの一覧を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-232">To list the cmdlets, type:</span></span>

```powershell
Get-Command -Noun Variable
```

<span data-ttu-id="20c6a-233">特定のコマンドレットのヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-233">To get help for a specific cmdlet, type:</span></span>

```powershell
Get-Help <cmdlet-name>
```

| <span data-ttu-id="20c6a-234">コマンドレット名</span><span class="sxs-lookup"><span data-stu-id="20c6a-234">Cmdlet Name</span></span>       | <span data-ttu-id="20c6a-235">説明</span><span class="sxs-lookup"><span data-stu-id="20c6a-235">Description</span></span>                                |
| ---------------   | ------------------------------------------ |
| `Clear-Variable`  | <span data-ttu-id="20c6a-236">変数の値を削除します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-236">Deletes the value of a variable.</span></span>           |
| `Get-Variable`    | <span data-ttu-id="20c6a-237">現在のコンソール内の変数を取得します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-237">Gets the variables in the current console.</span></span> |
| `New-Variable`    | <span data-ttu-id="20c6a-238">新しい変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-238">Creates a new variable.</span></span>                    |
| `Remove-Variable` | <span data-ttu-id="20c6a-239">変数とその値を削除します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-239">Deletes a variable and its value.</span></span>          |
| `Set-Variable`    | <span data-ttu-id="20c6a-240">変数の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="20c6a-240">Changes the value of a variable.</span></span>           |

## <a name="see-also"></a><span data-ttu-id="20c6a-241">関連項目</span><span class="sxs-lookup"><span data-stu-id="20c6a-241">See also</span></span>

[<span data-ttu-id="20c6a-242">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="20c6a-242">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="20c6a-243">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="20c6a-243">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="20c6a-244">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="20c6a-244">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="20c6a-245">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="20c6a-245">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="20c6a-246">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="20c6a-246">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="20c6a-247">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="20c6a-247">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="20c6a-248">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="20c6a-248">about_Remote_Variables</span></span>](about_Remote_Variables.md)

