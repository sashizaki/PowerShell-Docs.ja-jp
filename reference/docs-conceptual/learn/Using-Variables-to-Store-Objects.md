---
ms.date: 08/27/2018
keywords: PowerShell, コマンドレット
title: 変数を使用したオブジェクトの保存
ms.assetid: b1688d73-c173-491e-9ba6-6d0c1cc852de
ms.openlocfilehash: 16e82b83df967674da11193c8ac60d637687a01b
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65854333"
---
# <a name="using-variables-to-store-objects"></a><span data-ttu-id="dc92b-103">変数を使用したオブジェクトの保存</span><span class="sxs-lookup"><span data-stu-id="dc92b-103">Using variables to store objects</span></span>

<span data-ttu-id="dc92b-104">PowerShell ではオブジェクトを操作します。</span><span class="sxs-lookup"><span data-stu-id="dc92b-104">PowerShell works with objects.</span></span> <span data-ttu-id="dc92b-105">PowerShell では、変数として認識される名前付きオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc92b-105">PowerShell lets you create named objects known as variables.</span></span>
<span data-ttu-id="dc92b-106">変数名には、アンダースコア文字と任意の英数字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="dc92b-106">Variable names can include the underscore character and any alphanumeric characters.</span></span> <span data-ttu-id="dc92b-107">PowerShell で使用される場合、変数は常に、\$ 文字の後ろに変数名を追加して指定されます。</span><span class="sxs-lookup"><span data-stu-id="dc92b-107">When used in PowerShell, a variable is always specified using the \$ character followed by variable name.</span></span>

## <a name="creating-a-variable"></a><span data-ttu-id="dc92b-108">変数の作成</span><span class="sxs-lookup"><span data-stu-id="dc92b-108">Creating a variable</span></span>

<span data-ttu-id="dc92b-109">次のように有効な変数名を入力することで、変数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc92b-109">You can create a variable by typing a valid variable name:</span></span>

```
PS> $loc
PS>
```

<span data-ttu-id="dc92b-110">`$loc` に値がないため、この例では結果を返しません。</span><span class="sxs-lookup"><span data-stu-id="dc92b-110">This example returns no result because `$loc` doesn't have a value.</span></span> <span data-ttu-id="dc92b-111">変数の作成と値の割り当てを同一の手順で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dc92b-111">You can create a variable and assign it a value in the same step.</span></span> <span data-ttu-id="dc92b-112">PowerShell では、変数が存在しない場合にのみ、変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="dc92b-112">PowerShell only creates the variable if it doesn't exist.</span></span>
<span data-ttu-id="dc92b-113">それ以外の場合、指定された値を既存の変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="dc92b-113">Otherwise, it assigns the specified value to the existing variable.</span></span> <span data-ttu-id="dc92b-114">次の例では、変数 `$loc` に現在の場所を格納します。</span><span class="sxs-lookup"><span data-stu-id="dc92b-114">The following example stores the current location in the variable `$loc`:</span></span>

```powershell
$loc = Get-Location
```

<span data-ttu-id="dc92b-115">このコマンドを入力した場合、PowerShell では出力を表示しません。</span><span class="sxs-lookup"><span data-stu-id="dc92b-115">PowerShell displays no output when you type this command.</span></span> <span data-ttu-id="dc92b-116">PowerShell は 'Get-Location' の出力を `$loc` に送信します。</span><span class="sxs-lookup"><span data-stu-id="dc92b-116">PowerShell sends the output of 'Get-Location' to `$loc`.</span></span> <span data-ttu-id="dc92b-117">PowerShell では、割り当てもリダイレクトもされていないデータが、画面に送信されます。</span><span class="sxs-lookup"><span data-stu-id="dc92b-117">In PowerShell, data that isn't assigned or redirected is sent to the screen.</span></span> <span data-ttu-id="dc92b-118">次のように `$loc` を入力すると、現在の場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc92b-118">Typing `$loc` shows your current location:</span></span>

```
PS> $loc

Path
----
C:\temp
```

<span data-ttu-id="dc92b-119">`Get-Member` を使用して変数の内容に関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="dc92b-119">You can use `Get-Member` to display information about the contents of variables.</span></span> <span data-ttu-id="dc92b-120">`Get-Member` は、`Get-Location` からの出力と同様に、`$loc` が **PathInfo** オブジェクトであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="dc92b-120">`Get-Member` shows you that `$loc` is a **PathInfo** object, just like the output from `Get-Location`:</span></span>

```powershell
PS> $loc | Get-Member -MemberType Property

   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   System.String Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {...
ProviderPath Property   System.String ProviderPath {get;}
```

## <a name="manipulating-variables"></a><span data-ttu-id="dc92b-121">変数の操作</span><span class="sxs-lookup"><span data-stu-id="dc92b-121">Manipulating variables</span></span>

<span data-ttu-id="dc92b-122">PowerShell には変数を操作するためのコマンドがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="dc92b-122">PowerShell provides several commands to manipulate variables.</span></span> <span data-ttu-id="dc92b-123">次のように入力すると、完全な一覧が読みやすい形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc92b-123">You can see a complete listing in a readable form by typing:</span></span>

```powershell
Get-Command -Noun Variable | Format-Table -Property Name,Definition -AutoSize -Wrap
```

<span data-ttu-id="dc92b-124">また、PowerShell では、複数のシステム定義変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="dc92b-124">PowerShell also creates several system-defined variables.</span></span> <span data-ttu-id="dc92b-125">`Remove-Variable` コマンドレットを使用して、現在のセッションから、PowerShell によって制御されない変数を削除できます。</span><span class="sxs-lookup"><span data-stu-id="dc92b-125">You can use the `Remove-Variable` cmdlet to remove variables, which are not controlled by PowerShell, from the current session.</span></span> <span data-ttu-id="dc92b-126">すべての変数をクリアするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="dc92b-126">Type the following command to clear all variables:</span></span>

```powershell
Remove-Variable -Name * -Force -ErrorAction SilentlyContinue
```

<span data-ttu-id="dc92b-127">前のコマンドを実行した後、`Get-Variable` コマンドレットでは PowerShell システム変数を表示します。</span><span class="sxs-lookup"><span data-stu-id="dc92b-127">After running the previous command, the `Get-Variable` cmdlet shows the PowerShell system variables.</span></span>

<span data-ttu-id="dc92b-128">また、PowerShell では、変数ドライブも作成します。</span><span class="sxs-lookup"><span data-stu-id="dc92b-128">PowerShell also creates a variable drive.</span></span> <span data-ttu-id="dc92b-129">次の例を使用して、変数ドライブを使ってすべての PowerShell 変数を表示します。</span><span class="sxs-lookup"><span data-stu-id="dc92b-129">Use the following example to display all PowerShell variables using the variable drive:</span></span>

```powershell
Get-ChildItem variable:
```

## <a name="using-cmdexe-variables"></a><span data-ttu-id="dc92b-130">cmd.exe 変数の使用</span><span class="sxs-lookup"><span data-stu-id="dc92b-130">Using cmd.exe variables</span></span>

<span data-ttu-id="dc92b-131">PowerShell では、**cmd.exe** など、任意の Windows プロセスに利用できる同じ環境変数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc92b-131">PowerShell can use the same environment variables available to any Windows process, including **cmd.exe**.</span></span> <span data-ttu-id="dc92b-132">これらの変数は `env:` という名前のドライブ経由で公開されます。</span><span class="sxs-lookup"><span data-stu-id="dc92b-132">These variables are exposed through a drive named `env:`.</span></span> <span data-ttu-id="dc92b-133">これらの変数を表示するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="dc92b-133">You can view these variables by typing the following command:</span></span>

```powershell
Get-ChildItem env:
```

<span data-ttu-id="dc92b-134">標準の `*-Variable` コマンドレットは、環境変数を操作するように設計されていません。</span><span class="sxs-lookup"><span data-stu-id="dc92b-134">The standard `*-Variable` cmdlets aren't designed to work with environment variables.</span></span> <span data-ttu-id="dc92b-135">環境変数は、`env:` ドライブ プレフィックスを使用してアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="dc92b-135">Environment variables are accessed using the `env:` drive prefix.</span></span> <span data-ttu-id="dc92b-136">たとえば、**cmd.exe** の **%SystemRoot%** 変数には、オペレーティング システムのルート ディレクトリ名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dc92b-136">For example, the **%SystemRoot%** variable in **cmd.exe** contains the operating system's root directory name.</span></span> <span data-ttu-id="dc92b-137">PowerShell では、`$env:SystemRoot` を使用して同じ値にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="dc92b-137">In PowerShell, you use `$env:SystemRoot` to access the same value.</span></span>

```
PS> $env:SystemRoot
C:\WINDOWS
```

<span data-ttu-id="dc92b-138">さらに、PowerShell 内から環境変数を作成および変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc92b-138">You can also create and modify environment variables from within PowerShell.</span></span> <span data-ttu-id="dc92b-139">PowerShell の環境変数は、オペレーティング システムの他の場所で使用される環境変数と同じ規則に従います。</span><span class="sxs-lookup"><span data-stu-id="dc92b-139">Environment variables in PowerShell follow the same rules for environment variables used elsewhere in the operating system.</span></span> <span data-ttu-id="dc92b-140">次の例では、新しい環境変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="dc92b-140">The following example creates a new environment variable:</span></span>

```powershell
$env:LIB_PATH='/usr/local/lib'
```

<span data-ttu-id="dc92b-141">必須ではありませんが、環境変数名には、すべて大文字を使用するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="dc92b-141">Though not required, it's common for environment variable names to use all uppercase letters.</span></span>
