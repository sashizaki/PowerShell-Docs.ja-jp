---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "コマンドに関する情報の取得"
ms.assetid: 56f8e5b4-d97c-4e59-abbe-bf13e464eb0d
ms.openlocfilehash: 98e449110860ea81939d6ec0b7b1a8534a2da2aa
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="getting-information-about-commands"></a><span data-ttu-id="f5b9a-103">コマンドに関する情報の取得</span><span class="sxs-lookup"><span data-stu-id="f5b9a-103">Getting Information About Commands</span></span>
<span data-ttu-id="f5b9a-104">Windows PowerShell の **Get-Command** コマンドレットは、現在のセッションで使用できるすべてのコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-104">The Windows PowerShell **Get-Command** cmdlet gets all commands that are available in your current session.</span></span> <span data-ttu-id="f5b9a-105">Windows PowerShell プロンプトで **Get-Command** と入力すると、次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-105">When you type **Get-Command** at a Windows PowerShell prompt, you will see output similar to the following:</span></span>

```
PS> Get-Command
CommandType     Name                            Definition
-----------     ----                            ----------
Cmdlet          Add-Content                     Add-Content [-Path] <String[...
Cmdlet          Add-History                     Add-History [[-InputObject] ...
Cmdlet          Add-Member                      Add-Member [-MemberType] <PS...
...
```

<span data-ttu-id="f5b9a-106">この出力は、Cmd.exe のヘルプの出力に似ている、内部コマンドの表形式の概要です。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-106">This output looks a lot like the Help output of Cmd.exe: a tabular summary of internal commands.</span></span> <span data-ttu-id="f5b9a-107">上記の **Get-Command** コマンドの出力の抜粋では、表示されているすべてのコマンドのコマンドレットは CommandType です。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-107">In the excerpt of the **Get-Command** command output shown above, every command shown has a CommandType of Cmdlet.</span></span> <span data-ttu-id="f5b9a-108">コマンドレットは、Windows PowerShell の組み込みコマンドの種類であり、Cmd.exe の **dir** コマンドと **cd** コマンドや、BASH などの UNIX シェルの組み込み要素にほぼ対応します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-108">A cmdlet is Windows PowerShell's intrinsic command type - a type that corresponds roughly to the **dir** and **cd** commands of Cmd.exe and to built-ins in UNIX shells such as BASH.</span></span>

<span data-ttu-id="f5b9a-109">**Get-Command** コマンドの出力では、すべての定義が省略記号 (...) で終わっており、PowerShell で使用可能なスペースにすべてのコンテンツを表示できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-109">In the output of the **Get-Command** command, all the definitions end with ellipses (...) to indicate that PowerShell cannot display all the content in the available space.</span></span> <span data-ttu-id="f5b9a-110">Windows PowerShell に出力が表示されると、出力をテキストとして書式設定し、ウィンドウにきちんと収まるようにデータを配置します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-110">When Windows PowerShell displays output, it formats the output as text and then arranges it to make the data fit cleanly into the window.</span></span> <span data-ttu-id="f5b9a-111">これについては、フォーマッタのセクションで後述します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-111">We will talk about this later in the section on formatters.</span></span>

<span data-ttu-id="f5b9a-112">**Get-Command** コマンドレットには、各コマンドレットの構文を取得する **Syntax** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-112">The **Get-Command** cmdlet has a **Syntax** parameter that gets the syntax of each cmdlet.</span></span> <span data-ttu-id="f5b9a-113">Get-help コマンドレットの構文を取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-113">To get the syntax of the Get-Help cmdlet, use the following command:</span></span>

<span data-ttu-id="f5b9a-114">**Get-Command Get-Help - 構文**</span><span class="sxs-lookup"><span data-stu-id="f5b9a-114">**Get-Command Get-Help -Syntax**</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Full] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]

Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Detailed] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]

Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Examples] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]

Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Parameter <String>] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]
```

### <a name="displaying-available-command-types"></a><span data-ttu-id="f5b9a-115">使用可能なコマンドの種類の表示</span><span class="sxs-lookup"><span data-stu-id="f5b9a-115">Displaying Available Command Types</span></span>
<span data-ttu-id="f5b9a-116">**Get-Command** コマンドは、Windows PowerShell で使用可能なコマンドのすべてを一覧表示しません。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-116">The **Get-Command** command does not list every command that is available in Windows PowerShell.</span></span> <span data-ttu-id="f5b9a-117">代わりに、**Get-Command** コマンドは、現在のセッションのコマンドレットのみを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-117">Instead, the **Get-Command** command lists only the cmdlets in the current session.</span></span> <span data-ttu-id="f5b9a-118">Windows PowerShell は、実際にはその他のいくつかの種類のコマンドをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-118">Windows PowerShell actually supports several other types of commands.</span></span> <span data-ttu-id="f5b9a-119">エイリアス、関数、およびスクリプトも Windows PowerShell のコマンドですが、『Windows PowerShell ユーザー ガイド』では詳細に説明していません。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-119">Aliases, functions, and scripts are also Windows PowerShell commands, although they are not discussed in detail in the Windows PowerShell User's Guide.</span></span> <span data-ttu-id="f5b9a-120">実行可能な外部ファイル、または登録されているファイル タイプのハンドラーを持つ外部ファイルも、コマンドとして分類されます。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-120">External files that are executable, or have a registered file type handler, are also classified as commands.</span></span>

<span data-ttu-id="f5b9a-121">セッション内のすべてのコマンドを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-121">To get all commands in the session, type:</span></span>

```
Get-Command *
```

<span data-ttu-id="f5b9a-122">この一覧には、検索パスの外部ファイルが含まれるため、何千もの項目が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-122">Because this list includes external files in your search path, it may contain thousands of items.</span></span> <span data-ttu-id="f5b9a-123">コマンド セットを削減して表示する方が実用的です。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-123">It is more useful to look at a reduced set of commands.</span></span>

<span data-ttu-id="f5b9a-124">その他の種類のネイティブ コマンドを取得するには、**Get-Command** コマンドレットの **CommandType** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-124">To get native commands of other types, use the **CommandType** parameter of the **Get-Command** cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="f5b9a-125">アスタリスク (\*) は、Windows PowerShell コマンドの引数のワイルドカードによるマッチングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-125">The asterisk (\*) is used for wildcard matching in Windows PowerShell command arguments.</span></span> <span data-ttu-id="f5b9a-126">\* は、「1 つ以上の任意の文字に一致する」という意味です。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-126">The \* means "match one or more of any characters".</span></span> <span data-ttu-id="f5b9a-127">**Get-Command a\&#42;** を入力すると、文字 "a" で始まるコマンドをすべて検索できます。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-127">You can type **Get-Command a\&#42;** to find all commands that begin with the letter "a".</span></span> <span data-ttu-id="f5b9a-128">Cmd.exe のワイルドカードのマッチングとは異なり、Windows PowerShell のワイルドカードは、ピリオドもマッチングします。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-128">Unlike wildcard matching in Cmd.exe, Windows PowerShell's wildcard will also match a period.</span></span>

<span data-ttu-id="f5b9a-129">コマンドの割り当て済みのニックネームであるコマンドのエイリアスを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-129">To get command aliases, which are the assigned nicknames of commands, type:</span></span>

```
Get-Command -CommandType Alias
```

<span data-ttu-id="f5b9a-130">現在のセッションの関数を取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-130">To get the functions in the current session, type:</span></span>

```
Get-Command -CommandType Function
```

<span data-ttu-id="f5b9a-131">Windows PowerShell の検索パス内のスクリプトを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-131">To display scripts in Windows PowerShell's search path, type:</span></span>

```
Get-Command -CommandType Script
```

