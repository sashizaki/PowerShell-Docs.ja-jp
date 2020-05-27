---
ms.date: 08/27/2018
keywords: powershell,コマンドレット
title: コマンドに関する情報の取得
ms.openlocfilehash: eb918c6f89d8369db775258263a8f7a7902a6cc7
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808638"
---
# <a name="getting-information-about-commands"></a><span data-ttu-id="8b95a-103">コマンドに関する情報の取得</span><span class="sxs-lookup"><span data-stu-id="8b95a-103">Getting information about commands</span></span>

<span data-ttu-id="8b95a-104">PowerShell の `Get-Command` は、現在のセッションで使用できるコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="8b95a-104">The PowerShell `Get-Command` displays commands that are available in your current session.</span></span>
<span data-ttu-id="8b95a-105">`Get-Command` コマンドレットを実行すると、次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b95a-105">When you run the `Get-Command` cmdlet, you see something similar to the following output:</span></span>

```output
CommandType     Name                    Version    Source
-----------     ----                    -------    ------
Cmdlet          Add-Computer            3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Add-Content             3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Add-History             3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Add-JobTrigger          1.1.0.0    PSScheduledJob
Cmdlet          Add-LocalGroupMember    1.0.0.0    Microsoft.PowerShell.LocalAccounts
Cmdlet          Add-Member              3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Add-PSSnapin            3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Add-Type                3.1.0.0    Microsoft.PowerShell.Utility
...
```

<span data-ttu-id="8b95a-106">この出力は、**cmd.exe** のヘルプの出力に似ている、内部コマンドの表形式の概要です。</span><span class="sxs-lookup"><span data-stu-id="8b95a-106">This output looks a lot like the Help output of **cmd.exe**: a tabular summary of internal commands.</span></span> <span data-ttu-id="8b95a-107">上記の `Get-Command` コマンドの出力の抜粋では、表示されているすべてのコマンドのコマンドレットは CommandType です。</span><span class="sxs-lookup"><span data-stu-id="8b95a-107">In the excerpt of the `Get-Command` command output shown above, every command shown has a CommandType of Cmdlet.</span></span> <span data-ttu-id="8b95a-108">コマンドレットは、PowerShell の組み込みのコマンドの種類です。</span><span class="sxs-lookup"><span data-stu-id="8b95a-108">A cmdlet is PowerShell's intrinsic command type.</span></span> <span data-ttu-id="8b95a-109">この種類は、おおまかに言うと、**cmd.exe** の `dir` および `cd` のようなコマンドや、バッシュのような Unix シェルの組み込みコマンドと同じです。</span><span class="sxs-lookup"><span data-stu-id="8b95a-109">This type corresponds roughly to commands like `dir` and `cd` in **cmd.exe** or the built-in commands of Unix shells like bash.</span></span>

<span data-ttu-id="8b95a-110">`Get-Command` コマンドレットには、各コマンドレットの構文を返す **Syntax** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="8b95a-110">The `Get-Command` cmdlet has a **Syntax** parameter that returns syntax of each cmdlet.</span></span> <span data-ttu-id="8b95a-111">次の例は、`Get-Help` コマンドレットの構文を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8b95a-111">The following example shows how to get the syntax of the `Get-Help` cmdlet:</span></span>

```powershell
Get-Command Get-Help -Syntax
```

```output
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Full] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]

Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Detailed] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]

Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Examples] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]

Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Parameter <String>] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]
```

## <a name="displaying-available-command-by-type"></a><span data-ttu-id="8b95a-112">使用可能なコマンドを種類別に表示する</span><span class="sxs-lookup"><span data-stu-id="8b95a-112">Displaying available command by type</span></span>

<span data-ttu-id="8b95a-113">`Get-Command` コマンドは、現在のセッションのコマンドレットのみを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8b95a-113">The `Get-Command` command lists only the cmdlets in the current session.</span></span> <span data-ttu-id="8b95a-114">PowerShell は、実際にはその他のいくつかの種類のコマンドをサポートします。</span><span class="sxs-lookup"><span data-stu-id="8b95a-114">PowerShell actually supports several other types of commands:</span></span>

- <span data-ttu-id="8b95a-115">エイリアス</span><span class="sxs-lookup"><span data-stu-id="8b95a-115">Aliases</span></span>
- <span data-ttu-id="8b95a-116">関数</span><span class="sxs-lookup"><span data-stu-id="8b95a-116">Functions</span></span>
- <span data-ttu-id="8b95a-117">スクリプト</span><span class="sxs-lookup"><span data-stu-id="8b95a-117">Scripts</span></span>

<span data-ttu-id="8b95a-118">実行可能な外部ファイル、または登録されているファイル タイプのハンドラーを持つ外部ファイルも、コマンドとして分類されます。</span><span class="sxs-lookup"><span data-stu-id="8b95a-118">External executable files, or files that have a registered file type handler, are also classified as commands.</span></span>

<span data-ttu-id="8b95a-119">セッション内のすべてのコマンドを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8b95a-119">To get all commands in the session, type:</span></span>

```powershell
Get-Command *
```

<span data-ttu-id="8b95a-120">この一覧には、検索パスの外部コマンドが含まれるため、何千もの項目が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="8b95a-120">This list includes external commands in your search path so it can contain thousands of items.</span></span>
<span data-ttu-id="8b95a-121">コマンド セットを削減して表示する方が実用的です。</span><span class="sxs-lookup"><span data-stu-id="8b95a-121">It is more useful to look at a reduced set of commands.</span></span>

> [!NOTE]
> <span data-ttu-id="8b95a-122">アスタリスク (\*) は、PowerShell コマンドの引数のワイルドカードによるマッチングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8b95a-122">The asterisk (\*) is used for wildcard matching in PowerShell command arguments.</span></span> <span data-ttu-id="8b95a-123">\* は、「1 つ以上の任意の文字に一致する」という意味です。</span><span class="sxs-lookup"><span data-stu-id="8b95a-123">The \* means "match one or more of any characters".</span></span> <span data-ttu-id="8b95a-124">`Get-Command a*` を入力すると、文字 "a" で始まるコマンドをすべて検索できます。</span><span class="sxs-lookup"><span data-stu-id="8b95a-124">You can type `Get-Command a*` to find all commands that begin with the letter "a".</span></span> <span data-ttu-id="8b95a-125">**cmd.exe** のワイルドカードのマッチングとは異なり、PowerShell のワイルドカードは、ピリオドもマッチングします。</span><span class="sxs-lookup"><span data-stu-id="8b95a-125">Unlike wildcard matching in **cmd.exe**, PowerShell's wildcard will also match a period.</span></span>

<span data-ttu-id="8b95a-126">その他の種類のネイティブ コマンドを取得するには、`Get-Command` の **CommandType** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b95a-126">Use the **CommandType** parameter of `Get-Command` to get native commands of other types.</span></span>
<span data-ttu-id="8b95a-127">コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="8b95a-127">cmdlet.</span></span>

<span data-ttu-id="8b95a-128">コマンドの割り当て済みのニックネームであるコマンドのエイリアスを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8b95a-128">To get command aliases, which are the assigned nicknames of commands, type:</span></span>

```powershell
Get-Command -CommandType Alias
```

<span data-ttu-id="8b95a-129">現在のセッションの関数を取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8b95a-129">To get the functions in the current session, type:</span></span>

```powershell
Get-Command -CommandType Function
```

<span data-ttu-id="8b95a-130">PowerShell の検索パス内のスクリプトを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8b95a-130">To display scripts in PowerShell's search path, type:</span></span>

```powershell
Get-Command -CommandType Script
```
