---
description: テキスト文字列とその他の読み取り専用データをスクリプトロジックから分離するデータセクションについて説明します。
Locale: en-US
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_data_sections?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Data_Sections
ms.openlocfilehash: 1f2a0bae0721bc9adf5b3ba92d5be32d21306a46
ms.sourcegitcommit: 04faa7dc1122bce839295d4891bd8b2f0ecb06ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "99600120"
---
# <a name="about-data-sections"></a><span data-ttu-id="03b7b-103">データセクションについて</span><span class="sxs-lookup"><span data-stu-id="03b7b-103">About Data Sections</span></span>

## <a name="short-description"></a><span data-ttu-id="03b7b-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="03b7b-104">Short Description</span></span>
<span data-ttu-id="03b7b-105">テキスト文字列とその他の読み取り専用データをスクリプトロジックから分離するデータセクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="03b7b-105">Explains Data sections, which isolate text strings and other read-only data from script logic.</span></span>

## <a name="long-description"></a><span data-ttu-id="03b7b-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="03b7b-106">Long Description</span></span>

<span data-ttu-id="03b7b-107">PowerShell 用に設計されたスクリプトには、データのみを含む1つまたは複数のデータセクションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="03b7b-107">Scripts that are designed for PowerShell can have one or more Data sections that contain only data.</span></span> <span data-ttu-id="03b7b-108">任意のスクリプト、関数、または高度な関数に1つ以上のデータセクションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="03b7b-108">You can include one or more Data sections in any script, function, or advanced function.</span></span> <span data-ttu-id="03b7b-109">Data セクションの内容は、PowerShell スクリプト言語の指定したサブセットに制限されます。</span><span class="sxs-lookup"><span data-stu-id="03b7b-109">The content of the Data section is restricted to a specified subset of the PowerShell scripting language.</span></span>

<span data-ttu-id="03b7b-110">コードロジックからデータを分離すると、ロジックとデータの両方を簡単に識別して管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="03b7b-110">Separating data from code logic makes it easier to identify and manage both logic and data.</span></span> <span data-ttu-id="03b7b-111">これにより、エラーメッセージやヘルプ文字列など、テキスト用の文字列リソースファイルを個別に作成できます。</span><span class="sxs-lookup"><span data-stu-id="03b7b-111">It lets you have separate string resource files for text, such as error messages and Help strings.</span></span> <span data-ttu-id="03b7b-112">また、コードロジックも分離されているため、セキュリティと検証のテストが容易になります。</span><span class="sxs-lookup"><span data-stu-id="03b7b-112">It also isolates the code logic, which facilitates security and validation tests.</span></span>

<span data-ttu-id="03b7b-113">PowerShell では、スクリプトの国際化をサポートするために Data セクションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="03b7b-113">In PowerShell, the Data section is used to support script internationalization.</span></span>
<span data-ttu-id="03b7b-114">データセクションを使用すると、多数のユーザーインターフェイス (UI) 言語に変換される文字列の分離、検索、および処理が容易になります。</span><span class="sxs-lookup"><span data-stu-id="03b7b-114">You can use Data sections to make it easier to isolate, locate, and process strings that will be translated into many user interface (UI) languages.</span></span>

<span data-ttu-id="03b7b-115">Data セクションは PowerShell 2.0 の機能です。</span><span class="sxs-lookup"><span data-stu-id="03b7b-115">The Data section is a PowerShell 2.0 feature.</span></span> <span data-ttu-id="03b7b-116">Data セクションを含むスクリプトは、リビジョンのない PowerShell 1.0 では実行されません。</span><span class="sxs-lookup"><span data-stu-id="03b7b-116">Scripts with Data sections will not run in PowerShell 1.0 without revision.</span></span>

### <a name="syntax"></a><span data-ttu-id="03b7b-117">構文</span><span class="sxs-lookup"><span data-stu-id="03b7b-117">Syntax</span></span>

<span data-ttu-id="03b7b-118">データセクションの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="03b7b-118">The syntax for a Data section is as follows:</span></span>

```
DATA [<variable-name>] [-supportedCommand <cmdlet-name>] {
    <Permitted content>
}
```

<span data-ttu-id="03b7b-119">Data キーワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="03b7b-119">The Data keyword is required.</span></span> <span data-ttu-id="03b7b-120">大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="03b7b-120">It is not case-sensitive.</span></span> <span data-ttu-id="03b7b-121">許可されるコンテンツは、次の要素に限定されます。</span><span class="sxs-lookup"><span data-stu-id="03b7b-121">The permitted content is limited to the following elements:</span></span>

- <span data-ttu-id="03b7b-122">すべての PowerShell 演算子 (を除く) `-match`</span><span class="sxs-lookup"><span data-stu-id="03b7b-122">All PowerShell operators, except `-match`</span></span>
- <span data-ttu-id="03b7b-123">`If`、 `Else` 、および `ElseIf` ステートメント</span><span class="sxs-lookup"><span data-stu-id="03b7b-123">`If`, `Else`, and `ElseIf` statements</span></span>
- <span data-ttu-id="03b7b-124">次の自動変数: `$PsCulture` 、 `$PsUICulture` 、 `$True` 、 `$False` 、および `$Null`</span><span class="sxs-lookup"><span data-stu-id="03b7b-124">The following automatic variables: `$PsCulture`, `$PsUICulture`, `$True`, `$False`, and `$Null`</span></span>
- <span data-ttu-id="03b7b-125">コメント</span><span class="sxs-lookup"><span data-stu-id="03b7b-125">Comments</span></span>
- <span data-ttu-id="03b7b-126">パイプライン</span><span class="sxs-lookup"><span data-stu-id="03b7b-126">Pipelines</span></span>
- <span data-ttu-id="03b7b-127">セミコロン () で区切られたステートメント `;`</span><span class="sxs-lookup"><span data-stu-id="03b7b-127">Statements separated by semicolons (`;`)</span></span>
- <span data-ttu-id="03b7b-128">リテラル。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="03b7b-128">Literals, such as the following:</span></span>

  ```powershell
  a
  1
  1,2,3
  "PowerShell 2.0"
  @( "red", "green", "blue" )
  @{ a = 0x1; b = "great"; c ="script" }
  [XML] @'
  <p> Hello, World </p>
  '@
  ```

- <span data-ttu-id="03b7b-129">データセクションで許可されているコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="03b7b-129">Cmdlets that are permitted in a Data section.</span></span> <span data-ttu-id="03b7b-130">既定で `ConvertFrom-StringData` は、コマンドレットのみが許可されています。</span><span class="sxs-lookup"><span data-stu-id="03b7b-130">By default, only the `ConvertFrom-StringData` cmdlet is permitted.</span></span>
- <span data-ttu-id="03b7b-131">パラメーターを使用してデータセクションで許可するコマンドレット `-SupportedCommand` 。</span><span class="sxs-lookup"><span data-stu-id="03b7b-131">Cmdlets that you permit in a Data section by using the `-SupportedCommand` parameter.</span></span>

<span data-ttu-id="03b7b-132">データセクションでコマンドレットを使用する場合は、単一引用符で囲んだ文字列または二重引用符で囲まれた文字列で、 `ConvertFrom-StringData` キーと値のペアを囲むことができます。</span><span class="sxs-lookup"><span data-stu-id="03b7b-132">When you use the `ConvertFrom-StringData` cmdlet in a Data section, you can enclose the key-value pairs in single-quoted or double-quoted strings or in single-quoted or double-quoted here-strings.</span></span> <span data-ttu-id="03b7b-133">ただし、変数と部分式を含む文字列は、単一引用符で囲まれた文字列または引用符で囲まれた文字列で囲む必要があります。これにより、変数が展開されず、部分式が実行可能ではなくなります。</span><span class="sxs-lookup"><span data-stu-id="03b7b-133">However, strings that contain variables and subexpressions must be enclosed in single-quoted strings or in single-quoted here-strings so that the variables are not expanded and the subexpressions are not executable.</span></span>

### <a name="-supportedcommand"></a><span data-ttu-id="03b7b-134">-SupportedCommand</span><span class="sxs-lookup"><span data-stu-id="03b7b-134">-SupportedCommand</span></span>

<span data-ttu-id="03b7b-135">`-SupportedCommand`パラメーターを使用すると、コマンドレットまたは関数によってのみデータが生成されることを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="03b7b-135">The `-SupportedCommand` parameter allows you to indicate that a cmdlet or function generates only data.</span></span> <span data-ttu-id="03b7b-136">これは、ユーザーが記述またはテストしたデータセクションにコマンドレットと関数を含めることができるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="03b7b-136">It is designed to allow users to include cmdlets and functions in a data section that they have written or tested.</span></span>

<span data-ttu-id="03b7b-137">の値 `-SupportedCommand` は、1つまたは複数のコマンドレットまたは関数の名前のコンマ区切りのリストです。</span><span class="sxs-lookup"><span data-stu-id="03b7b-137">The value of `-SupportedCommand` is a comma-separated list of one or more cmdlet or function names.</span></span>

<span data-ttu-id="03b7b-138">たとえば、次の data セクションには、 `Format-Xml` データを XML ファイルにフォーマットするユーザー記述のコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="03b7b-138">For example, the following data section includes a user-written cmdlet, `Format-Xml`, that formats data in an XML file:</span></span>

```powershell
DATA -supportedCommand Format-Xml
{
    Format-Xml -Strings string1, string2, string3
}
```

### <a name="using-a-data-section"></a><span data-ttu-id="03b7b-139">Data セクションの使用</span><span class="sxs-lookup"><span data-stu-id="03b7b-139">Using a Data Section</span></span>

<span data-ttu-id="03b7b-140">データセクションの内容を使用するには、それを変数に割り当て、変数表記を使用してコンテンツにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="03b7b-140">To use the content of a Data section, assign it to a variable and use variable notation to access the content.</span></span>

<span data-ttu-id="03b7b-141">たとえば、次の data セクションには、 `ConvertFrom-StringData` この文字列をハッシュテーブルに変換するコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="03b7b-141">For example, the following data section contains a `ConvertFrom-StringData` command that converts the here-string into a hash table.</span></span> <span data-ttu-id="03b7b-142">ハッシュテーブルは変数に割り当てられ `$TextMsgs` ます。</span><span class="sxs-lookup"><span data-stu-id="03b7b-142">The hash table is assigned to the `$TextMsgs` variable.</span></span>

<span data-ttu-id="03b7b-143">`$TextMsgs`変数は data セクションの一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="03b7b-143">The `$TextMsgs` variable is not part of the data section.</span></span>

```powershell
$TextMsgs = DATA {
    ConvertFrom-StringData -StringData @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}
```

<span data-ttu-id="03b7b-144">でハッシュテーブルのキーと値にアクセスするには、 `$TextMsgs` 次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="03b7b-144">To access the keys and values in hash table in `$TextMsgs`, use the following commands.</span></span>

```powershell
$TextMsgs.Text001
$TextMsgs.Text002
```

<span data-ttu-id="03b7b-145">また、変数名を Data セクションの定義に含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="03b7b-145">Alternately, you can put the variable name in the definition of the Data section.</span></span> <span data-ttu-id="03b7b-146">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="03b7b-146">For example:</span></span>

```powershell
DATA TextMsgs {
    ConvertFrom-StringData -StringData @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}

$TextMsgs
```

<span data-ttu-id="03b7b-147">結果は前の例と同じです。</span><span class="sxs-lookup"><span data-stu-id="03b7b-147">The result is the same as the previous example.</span></span>

```Output
Name                           Value
----                           -----
Text001                        Windows 7
Text002                        Windows Server 2008 R2
```

### <a name="examples"></a><span data-ttu-id="03b7b-148">例</span><span class="sxs-lookup"><span data-stu-id="03b7b-148">Examples</span></span>

<span data-ttu-id="03b7b-149">単純なデータ文字列。</span><span class="sxs-lookup"><span data-stu-id="03b7b-149">Simple data strings.</span></span>

```powershell
DATA {
    "Thank you for using my PowerShell Organize.pst script."
    "It is provided free of charge to the community."
    "I appreciate your comments and feedback."
}
```

<span data-ttu-id="03b7b-150">許可される変数を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="03b7b-150">Strings that include permitted variables.</span></span>

```powershell
DATA {
    if ($null) {
        "To get help for this cmdlet, type get-help new-dictionary."
    }
}
```

<span data-ttu-id="03b7b-151">コマンドレットを使用する単一引用符で囲まれた文字列 `ConvertFrom-StringData` :</span><span class="sxs-lookup"><span data-stu-id="03b7b-151">A single-quoted here-string that uses the `ConvertFrom-StringData` cmdlet:</span></span>

```powershell
DATA {
    ConvertFrom-StringData -stringdata @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}
```

<span data-ttu-id="03b7b-152">ここでは、コマンドレットを使用する二重引用符で囲まれた文字列 `ConvertFrom-StringData` です。</span><span class="sxs-lookup"><span data-stu-id="03b7b-152">A double-quoted here-string that uses the `ConvertFrom-StringData` cmdlet:</span></span>

```powershell
DATA  {
    ConvertFrom-StringData -stringdata @"
Msg1 = To start, press any key.
Msg2 = To exit, type "quit".
"@
}
```

<span data-ttu-id="03b7b-153">データを生成するユーザー記述のコマンドレットを含むデータセクション。</span><span class="sxs-lookup"><span data-stu-id="03b7b-153">A data section that includes a user-written cmdlet that generates data:</span></span>

```powershell
DATA -supportedCommand Format-XML {
    Format-Xml -strings string1, string2, string3
}
```

## <a name="see-also"></a><span data-ttu-id="03b7b-154">参照</span><span class="sxs-lookup"><span data-stu-id="03b7b-154">See Also</span></span>

[<span data-ttu-id="03b7b-155">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="03b7b-155">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="03b7b-156">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="03b7b-156">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="03b7b-157">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="03b7b-157">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="03b7b-158">about_If</span><span class="sxs-lookup"><span data-stu-id="03b7b-158">about_If</span></span>](about_If.md)

[<span data-ttu-id="03b7b-159">about_Operators</span><span class="sxs-lookup"><span data-stu-id="03b7b-159">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="03b7b-160">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="03b7b-160">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="03b7b-161">about_Script_Internationalization</span><span class="sxs-lookup"><span data-stu-id="03b7b-161">about_Script_Internationalization</span></span>](about_Script_Internationalization.md)

[<span data-ttu-id="03b7b-162">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="03b7b-162">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)

[<span data-ttu-id="03b7b-163">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="03b7b-163">Import-LocalizedData</span></span>](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)

