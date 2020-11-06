---
description: PowerShell のスコープの概念について説明し、要素のスコープを設定および変更する方法を示します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 11/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_scopes?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_scopes
ms.openlocfilehash: 6dc416632a6948c60c8016df6066694ce01a8b5d
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354968"
---
# <a name="about-scopes"></a><span data-ttu-id="67300-104">スコープについて</span><span class="sxs-lookup"><span data-stu-id="67300-104">About Scopes</span></span>

## <a name="short-description"></a><span data-ttu-id="67300-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="67300-105">Short description</span></span>
<span data-ttu-id="67300-106">PowerShell のスコープの概念について説明し、要素のスコープを設定および変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="67300-106">Explains the concept of scope in PowerShell and shows how to set and change the scope of elements.</span></span>

## <a name="long-description"></a><span data-ttu-id="67300-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="67300-107">Long description</span></span>

<span data-ttu-id="67300-108">PowerShell では、変数、エイリアス、関数、および PowerShell ドライブ (PSDrives) へのアクセスを、読み取りと変更が可能な場所を制限することによって保護します。</span><span class="sxs-lookup"><span data-stu-id="67300-108">PowerShell protects access to variables, aliases, functions, and PowerShell drives (PSDrives) by limiting where they can be read and changed.</span></span> <span data-ttu-id="67300-109">PowerShell では、スコープルールを使用して、変更しない項目を誤って変更しないようにします。</span><span class="sxs-lookup"><span data-stu-id="67300-109">PowerShell uses scope rules to ensure that you do not inadvertently change an item that should not be changed.</span></span>

<span data-ttu-id="67300-110">スコープの基本的な規則を次に示します。</span><span class="sxs-lookup"><span data-stu-id="67300-110">The following are the basic rules of scope:</span></span>

- <span data-ttu-id="67300-111">スコープは入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="67300-111">Scopes may nest.</span></span> <span data-ttu-id="67300-112">外側のスコープは親スコープと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="67300-112">An outer scope is referred to as a parent scope.</span></span> <span data-ttu-id="67300-113">入れ子になったスコープは、その親の子スコープです。</span><span class="sxs-lookup"><span data-stu-id="67300-113">Any nested scopes are child scopes of that parent.</span></span>

- <span data-ttu-id="67300-114">項目は、明示的にプライベートにしない限り、作成されたスコープと任意の子スコープに表示されます。</span><span class="sxs-lookup"><span data-stu-id="67300-114">An item is visible in the scope in which it was created and in any child scopes, unless you explicitly make it private.</span></span> <span data-ttu-id="67300-115">変数、エイリアス、関数、または PowerShell ドライブは、1つまたは複数のスコープに配置できます。</span><span class="sxs-lookup"><span data-stu-id="67300-115">You can place variables, aliases, functions, or PowerShell drives in one or more scopes.</span></span>

- <span data-ttu-id="67300-116">スコープ内で作成した項目は、別のスコープを明示的に指定しない限り、その項目が作成されたスコープ内でのみ変更できます。</span><span class="sxs-lookup"><span data-stu-id="67300-116">An item that you created within a scope can be changed only in the scope in which it was created, unless you explicitly specify a different scope.</span></span>

<span data-ttu-id="67300-117">スコープ内に項目を作成し、その項目の名前を別のスコープ内の項目と共有すると、元の項目は新しい項目の下で非表示になりますが、オーバーライドまたは変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="67300-117">If you create an item in a scope, and the item shares its name with an item in a different scope, the original item might be hidden under the new item, but it is not overridden or changed.</span></span>

## <a name="powershell-scopes"></a><span data-ttu-id="67300-118">PowerShell のスコープ</span><span class="sxs-lookup"><span data-stu-id="67300-118">PowerShell Scopes</span></span>

<span data-ttu-id="67300-119">PowerShell では、次のスコープがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="67300-119">PowerShell supports the following scopes:</span></span>

- <span data-ttu-id="67300-120">グローバル: PowerShell が開始されたとき、または新しいセッションまたは実行空間を作成したときに有効なスコープ。</span><span class="sxs-lookup"><span data-stu-id="67300-120">Global: The scope that is in effect when PowerShell starts or when you create a new session or runspace.</span></span> <span data-ttu-id="67300-121">PowerShell の起動時に存在する変数と関数は、自動変数やユーザー設定変数など、グローバルスコープで作成されています。</span><span class="sxs-lookup"><span data-stu-id="67300-121">Variables and functions that are present when PowerShell starts have been created in the global scope, such as automatic variables and preference variables.</span></span> <span data-ttu-id="67300-122">PowerShell プロファイル内の変数、エイリアス、および関数も、グローバルスコープで作成されます。</span><span class="sxs-lookup"><span data-stu-id="67300-122">The variables, aliases, and functions in your PowerShell profiles are also created in the global scope.</span></span> <span data-ttu-id="67300-123">グローバルスコープは、セッションのルート親スコープです。</span><span class="sxs-lookup"><span data-stu-id="67300-123">The global scope is the root parent scope in a session.</span></span>

- <span data-ttu-id="67300-124">Local: 現在のスコープ。</span><span class="sxs-lookup"><span data-stu-id="67300-124">Local: The current scope.</span></span> <span data-ttu-id="67300-125">ローカルスコープには、グローバルスコープまたはその他のスコープを指定できます。</span><span class="sxs-lookup"><span data-stu-id="67300-125">The local scope can be the global scope or any other scope.</span></span>

- <span data-ttu-id="67300-126">スクリプト: スクリプトファイルの実行中に作成されるスコープです。</span><span class="sxs-lookup"><span data-stu-id="67300-126">Script: The scope that is created while a script file runs.</span></span> <span data-ttu-id="67300-127">スクリプト内のコマンドだけがスクリプトスコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="67300-127">Only the commands in the script run in the script scope.</span></span> <span data-ttu-id="67300-128">スクリプト内のコマンドに対して、スクリプトスコープはローカルスコープです。</span><span class="sxs-lookup"><span data-stu-id="67300-128">To the commands in a script, the script scope is the local scope.</span></span>

> [!NOTE]
> <span data-ttu-id="67300-129">**プライベート** はスコープではありません。</span><span class="sxs-lookup"><span data-stu-id="67300-129">**Private** is not a scope.</span></span> <span data-ttu-id="67300-130">これは、項目が定義されているスコープ外の項目の表示を変更する [オプション](#private-option) です。</span><span class="sxs-lookup"><span data-stu-id="67300-130">It is an [option](#private-option) that changes the visibility of an item outside of the scope where the item is defined.</span></span>

## <a name="parent-and-child-scopes"></a><span data-ttu-id="67300-131">親と子のスコープ</span><span class="sxs-lookup"><span data-stu-id="67300-131">Parent and Child Scopes</span></span>

<span data-ttu-id="67300-132">新しい子スコープを作成するには、スクリプトまたは関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="67300-132">You can create a new child scope by calling a script or function.</span></span> <span data-ttu-id="67300-133">呼び出し元のスコープは親スコープです。</span><span class="sxs-lookup"><span data-stu-id="67300-133">The calling scope is the parent scope.</span></span> <span data-ttu-id="67300-134">呼び出されたスクリプトまたは関数は、子スコープです。</span><span class="sxs-lookup"><span data-stu-id="67300-134">The called script or function is the child scope.</span></span>
<span data-ttu-id="67300-135">呼び出す関数またはスクリプトは、他の関数を呼び出して、ルートスコープがグローバルスコープである子スコープの階層を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="67300-135">The functions or scripts you call may call other functions, creating a hierarchy of child scopes whose root scope is the global scope.</span></span>

<span data-ttu-id="67300-136">項目をプライベートに明示的に設定しない限り、親スコープ内の項目は子スコープで使用できます。</span><span class="sxs-lookup"><span data-stu-id="67300-136">Unless you explicitly make the items private, the items in the parent scope are available to the child scope.</span></span> <span data-ttu-id="67300-137">ただし、子スコープで作成および変更した項目は、項目の作成時にスコープを明示的に指定しない限り、親スコープには影響しません。</span><span class="sxs-lookup"><span data-stu-id="67300-137">However, items that you create and change in the child scope do not affect the parent scope, unless you explicitly specify the scope when you create the items.</span></span>

> [!NOTE]
> <span data-ttu-id="67300-138">モジュールの関数は、呼び出し元のスコープの子スコープでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="67300-138">Functions from a module do not run in a child scope of the calling scope.</span></span>
> <span data-ttu-id="67300-139">モジュールには、グローバルスコープにリンクされている独自のセッション状態があります。</span><span class="sxs-lookup"><span data-stu-id="67300-139">Modules have their own session state that is linked to the global scope.</span></span>
> <span data-ttu-id="67300-140">すべてのモジュールコードは、独自のルートスコープを持つスコープのモジュール固有階層で実行されます。</span><span class="sxs-lookup"><span data-stu-id="67300-140">All module code runs in a module-specific hierarchy of scopes that has its own root scope.</span></span>

## <a name="inheritance"></a><span data-ttu-id="67300-141">継承</span><span class="sxs-lookup"><span data-stu-id="67300-141">Inheritance</span></span>

<span data-ttu-id="67300-142">子スコープは、親スコープから変数、エイリアス、および関数を継承しません。</span><span class="sxs-lookup"><span data-stu-id="67300-142">A child scope does not inherit the variables, aliases, and functions from the parent scope.</span></span> <span data-ttu-id="67300-143">アイテムがプライベートでない限り、子スコープは親スコープ内のアイテムを表示できます。</span><span class="sxs-lookup"><span data-stu-id="67300-143">Unless an item is private, the child scope can view the items in the parent scope.</span></span> <span data-ttu-id="67300-144">また、親スコープを明示的に指定することによって項目を変更できますが、項目は子スコープの一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="67300-144">And, it can change the items by explicitly specifying the parent scope, but the items are not part of the child scope.</span></span>

<span data-ttu-id="67300-145">ただし、項目のセットを使用して子スコープが作成されます。</span><span class="sxs-lookup"><span data-stu-id="67300-145">However, a child scope is created with a set of items.</span></span> <span data-ttu-id="67300-146">通常は、 **Allscope** オプションを持つすべてのエイリアスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="67300-146">Typically, it includes all the aliases that have the **AllScope** option.</span></span> <span data-ttu-id="67300-147">このオプションについては、この記事の後半で説明します。</span><span class="sxs-lookup"><span data-stu-id="67300-147">This option is discussed later in this article.</span></span> <span data-ttu-id="67300-148">これには、 **Allscope** オプションを持つすべての変数に加えて、一部の自動変数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="67300-148">It includes all the variables that have the **AllScope** option, plus some automatic variables.</span></span>

<span data-ttu-id="67300-149">特定のスコープ内の項目を検索するには、またはの Scope パラメーターを使用し `Get-Variable` `Get-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-149">To find the items in a particular scope, use the Scope parameter of `Get-Variable` or `Get-Alias`.</span></span>

<span data-ttu-id="67300-150">たとえば、ローカルスコープ内のすべての変数を取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="67300-150">For example, to get all the variables in the local scope, type:</span></span>

```powershell
Get-Variable -Scope local
```

<span data-ttu-id="67300-151">グローバルスコープ内のすべての変数を取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="67300-151">To get all the variables in the global scope, type:</span></span>

```powershell
Get-Variable -Scope global
```

## <a name="scope-modifiers"></a><span data-ttu-id="67300-152">スコープ修飾子</span><span class="sxs-lookup"><span data-stu-id="67300-152">Scope Modifiers</span></span>

<span data-ttu-id="67300-153">変数、別名、または関数の名前には、次のいずれかのオプションのスコープ修飾子を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="67300-153">A variable, alias, or function name can include any one of the following optional scope modifiers:</span></span>

- <span data-ttu-id="67300-154">`global:` -名前が **グローバル** スコープ内に存在することを指定します。</span><span class="sxs-lookup"><span data-stu-id="67300-154">`global:` - Specifies that the name exists in the **Global** scope.</span></span>
- <span data-ttu-id="67300-155">`local:` -名前が **ローカル** スコープ内に存在することを指定します。</span><span class="sxs-lookup"><span data-stu-id="67300-155">`local:` - Specifies that the name exists in the **Local** scope.</span></span> <span data-ttu-id="67300-156">現在のスコープは、常に **ローカル** スコープです。</span><span class="sxs-lookup"><span data-stu-id="67300-156">The current scope is always the **Local** scope.</span></span>
- <span data-ttu-id="67300-157">`private:` -名前が **プライベート** であり、現在のスコープからのみ参照可能であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="67300-157">`private:` - Specifies that the name is **Private** and only visible to the current scope.</span></span>
- <span data-ttu-id="67300-158">`script:` -名前が **スクリプト** スコープに存在することを指定します。</span><span class="sxs-lookup"><span data-stu-id="67300-158">`script:` - Specifies that the name exists in the **Script** scope.</span></span>
  <span data-ttu-id="67300-159">**スクリプト** スコープは、最も近い祖先スクリプトファイルのスコープ、または最も近い祖先スクリプトファイルがない場合は **グローバル** です。</span><span class="sxs-lookup"><span data-stu-id="67300-159">**Script** scope is the nearest ancestor script file's scope or **Global** if there is no nearest ancestor script file.</span></span>
- <span data-ttu-id="67300-160">`using:` -やなどのコマンドレットを使用してスクリプトを実行中に、別のスコープで定義された変数にアクセスするために使用され `Start-Job` `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-160">`using:` - Used to access variables defined in another scope while running scripts via cmdlets like `Start-Job` and `Invoke-Command`.</span></span>
- <span data-ttu-id="67300-161">`workflow:` -名前がワークフロー内に存在することを指定します。</span><span class="sxs-lookup"><span data-stu-id="67300-161">`workflow:` - Specifies that the name exists within a workflow.</span></span> <span data-ttu-id="67300-162">注: ワークフローは、PowerShell Core ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="67300-162">Note: Workflows are not supported in PowerShell Core.</span></span>
- <span data-ttu-id="67300-163">`<variable-namespace>` -PowerShell PSDrive プロバイダーによって作成された修飾子。</span><span class="sxs-lookup"><span data-stu-id="67300-163">`<variable-namespace>` - A modifier created by a PowerShell PSDrive provider.</span></span>
  <span data-ttu-id="67300-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="67300-164">For example:</span></span>

  |  <span data-ttu-id="67300-165">名前空間</span><span class="sxs-lookup"><span data-stu-id="67300-165">Namespace</span></span>  |                    <span data-ttu-id="67300-166">説明</span><span class="sxs-lookup"><span data-stu-id="67300-166">Description</span></span>                     |
  | ----------- | -------------------------------------------------- |
  | `Alias:`    | <span data-ttu-id="67300-167">現在のスコープで定義されている別名</span><span class="sxs-lookup"><span data-stu-id="67300-167">Aliases defined in the current scope</span></span>               |
  | `Env:`      | <span data-ttu-id="67300-168">現在のスコープで定義されている環境変数</span><span class="sxs-lookup"><span data-stu-id="67300-168">Environment variables defined in the current scope</span></span> |
  | `Function:` | <span data-ttu-id="67300-169">現在のスコープで定義されている関数</span><span class="sxs-lookup"><span data-stu-id="67300-169">Functions defined in the current scope</span></span>             |
  | `Variable:` | <span data-ttu-id="67300-170">現在のスコープで定義されている変数</span><span class="sxs-lookup"><span data-stu-id="67300-170">Variables defined in the current scope</span></span>             |

<span data-ttu-id="67300-171">スクリプトの既定のスコープは、スクリプトのスコープです。</span><span class="sxs-lookup"><span data-stu-id="67300-171">The default scope for scripts is the script scope.</span></span> <span data-ttu-id="67300-172">関数および別名の既定のスコープは、スクリプトで定義されている場合でも、ローカルスコープです。</span><span class="sxs-lookup"><span data-stu-id="67300-172">The default scope for functions and aliases is the local scope, even if they are defined in a script.</span></span>

### <a name="using-scope-modifiers"></a><span data-ttu-id="67300-173">スコープ修飾子の使用</span><span class="sxs-lookup"><span data-stu-id="67300-173">Using scope modifiers</span></span>

<span data-ttu-id="67300-174">新しい変数、別名、または関数のスコープを指定するには、スコープ修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="67300-174">To specify the scope of a new variable, alias, or function, use a scope modifier.</span></span>

<span data-ttu-id="67300-175">変数のスコープ修飾子の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67300-175">The syntax for a scope modifier in a variable is:</span></span>

```
$[<scope-modifier>:]<name> = <value>
```

<span data-ttu-id="67300-176">関数のスコープ修飾子の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67300-176">The syntax for a scope modifier in a function is:</span></span>

```
function [<scope-modifier>:]<name> {<function-body>}
```

<span data-ttu-id="67300-177">スコープ修飾子を使用しない次のコマンドは、現在のスコープまたは **ローカル** スコープに変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="67300-177">The following command, which does not use a scope modifier, creates a variable in the current or **local** scope:</span></span>

```powershell
$a = "one"
```

<span data-ttu-id="67300-178">**グローバル** スコープで同じ変数を作成するには、スコープ修飾子を使用し `global:` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-178">To create the same variable in the **global** scope, use the scope `global:` modifier:</span></span>

```powershell
$global:a = "one"
```

<span data-ttu-id="67300-179">**スクリプト** スコープで同じ変数を作成するには、スコープ修飾子を使用し `script:` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-179">To create the same variable in the **script** scope, use the `script:` scope modifier:</span></span>

```powershell
$script:a = "one"
```

<span data-ttu-id="67300-180">関数でスコープ修飾子を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="67300-180">You can also use a scope modifier with functions.</span></span> <span data-ttu-id="67300-181">次の関数定義は、 **グローバル** スコープに関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="67300-181">The following function definition creates a function in the **global** scope:</span></span>

```powershell
function global:Hello {
  Write-Host "Hello, World"
}
```

<span data-ttu-id="67300-182">スコープ修飾子を使用して、異なるスコープ内の変数を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="67300-182">You can also use scope modifiers to refer to a variable in a different scope.</span></span>
<span data-ttu-id="67300-183">次のコマンドは、変数を参照します。この変数は、 `$test` まずローカルスコープで、次にグローバルスコープにあります。</span><span class="sxs-lookup"><span data-stu-id="67300-183">The following command refers to the `$test` variable, first in the local scope and then in the global scope:</span></span>

```powershell
$test
$global:test
```

### <a name="the-using-scope-modifier"></a><span data-ttu-id="67300-184">`Using:`スコープ修飾子</span><span class="sxs-lookup"><span data-stu-id="67300-184">The `Using:` scope modifier</span></span>

<span data-ttu-id="67300-185">を使用すると、リモートコマンドでローカル変数を識別する特別なスコープ修飾子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="67300-185">Using is a special scope modifier that identifies a local variable in a remote command.</span></span> <span data-ttu-id="67300-186">修飾子を指定しない場合、PowerShell ではリモートコマンド内の変数をリモートセッションで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67300-186">Without a modifier, PowerShell expects variables in remote commands to be defined in the remote session.</span></span>

<span data-ttu-id="67300-187">`Using`スコープ修飾子は、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="67300-187">The `Using` scope modifier is introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="67300-188">セッションが不足しているスクリプトまたはコマンドについては、 `Using` 呼び出し元のセッションスコープから変数の値を埋め込むためにスコープ修飾子が必要です。これにより、セッションコードが不足してしまうことがあります。</span><span class="sxs-lookup"><span data-stu-id="67300-188">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span> <span data-ttu-id="67300-189">`Using`スコープ修飾子は、次のコンテキストでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="67300-189">The `Using` scope modifier is supported in the following contexts:</span></span>

- <span data-ttu-id="67300-190">リモートで実行されたコマンド。 `Invoke-Command` **ComputerName** 、 **HostName** 、 **SSHConnection** 、または **Session** パラメーター (リモートセッション) の使用を開始しました。</span><span class="sxs-lookup"><span data-stu-id="67300-190">Remotely executed commands, started with `Invoke-Command` using the **ComputerName** , **HostName** , **SSHConnection** or **Session** parameters (remote session)</span></span>
- <span data-ttu-id="67300-191">バックグラウンドジョブ、で開始 `Start-Job` (アウトプロセスセッション)</span><span class="sxs-lookup"><span data-stu-id="67300-191">Background jobs, started with `Start-Job` (out-of-process session)</span></span>
- <span data-ttu-id="67300-192">スレッドジョブ `Start-ThreadJob` 。または `ForEach-Object -Parallel` (個別のスレッドセッション) を使用して開始</span><span class="sxs-lookup"><span data-stu-id="67300-192">Thread jobs, started via `Start-ThreadJob` or `ForEach-Object -Parallel` (separate thread session)</span></span>

<span data-ttu-id="67300-193">コンテキストによっては、埋め込み変数の値は、呼び出し元のスコープ内のデータの独立したコピーか、またはそれに対する参照です。</span><span class="sxs-lookup"><span data-stu-id="67300-193">Depending on the context, embedded variable values are either independent copies of the data in the caller's scope or references to it.</span></span> <span data-ttu-id="67300-194">リモートとアウトプロセスのセッションでは、これらは常に独立したコピーです。</span><span class="sxs-lookup"><span data-stu-id="67300-194">In remote and out-of-process sessions, they are always independent copies.</span></span>

<span data-ttu-id="67300-195">詳細については、「 [about_Remote_Variables](about_Remote_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67300-195">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

<span data-ttu-id="67300-196">スレッドセッションでは、参照によって渡されます。</span><span class="sxs-lookup"><span data-stu-id="67300-196">In thread sessions, they are passed by reference.</span></span> <span data-ttu-id="67300-197">これは、別のスレッドで呼び出しスコープ変数を変更できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="67300-197">This means it is possible to modify call scope variables in a different thread.</span></span> <span data-ttu-id="67300-198">変数を安全に変更するには、スレッドの同期が必要です。</span><span class="sxs-lookup"><span data-stu-id="67300-198">To safely modify variables requires thread synchronization.</span></span>

<span data-ttu-id="67300-199">詳細情報</span><span class="sxs-lookup"><span data-stu-id="67300-199">For more information see:</span></span>

- [<span data-ttu-id="67300-200">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="67300-200">Start-ThreadJob</span></span>](xref:ThreadJob.Start-ThreadJob)
- [<span data-ttu-id="67300-201">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="67300-201">ForEach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)

#### <a name="serialization-of-variable-values"></a><span data-ttu-id="67300-202">変数値のシリアル化</span><span class="sxs-lookup"><span data-stu-id="67300-202">Serialization of variable values</span></span>

<span data-ttu-id="67300-203">リモートで実行されるコマンドとバックグラウンドジョブはアウトプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="67300-203">Remotely executed commands and background jobs run out-of-process.</span></span>
<span data-ttu-id="67300-204">アウトプロセスセッションでは、XML ベースのシリアル化と逆シリアル化を使用して、プロセスの境界を越えて変数の値を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="67300-204">Out-of-process sessions use XML-based serialization and deserialization to make the values of variables available across the process boundaries.</span></span> <span data-ttu-id="67300-205">シリアル化プロセスでは、オブジェクトは元のオブジェクトのプロパティを含む **PSObject** に変換されますが、そのメソッドは含まれません。</span><span class="sxs-lookup"><span data-stu-id="67300-205">The serialization process converts objects to a **PSObject** that contains the original objects properties but not its methods.</span></span>

<span data-ttu-id="67300-206">型の限定されたセットでは、逆シリアル化によって元の型に復元オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="67300-206">For a limited set of types, deserialization rehydrates objects back to the original type.</span></span> <span data-ttu-id="67300-207">復元オブジェクトは、元のオブジェクトインスタンスのコピーです。</span><span class="sxs-lookup"><span data-stu-id="67300-207">The rehydrated object is a copy of the original object instance.</span></span>
<span data-ttu-id="67300-208">これには、型のプロパティとメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="67300-208">It has the type properties and methods.</span></span> <span data-ttu-id="67300-209">System.string などの単純型の **場合、コピー** は完全に一致します。</span><span class="sxs-lookup"><span data-stu-id="67300-209">For simple types, such as **System.Version** , the copy is exact.</span></span> <span data-ttu-id="67300-210">複合型の場合、コピーは不完全です。</span><span class="sxs-lookup"><span data-stu-id="67300-210">For complex types, the copy is imperfect.</span></span> <span data-ttu-id="67300-211">たとえば、復元された証明書オブジェクトには、秘密キーは含まれません。</span><span class="sxs-lookup"><span data-stu-id="67300-211">For example, rehydrated certificate objects do not include the private key.</span></span>

<span data-ttu-id="67300-212">他のすべての型のインスタンスは **PSObject** インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="67300-212">Instances of all other types are **PSObject** instances.</span></span> <span data-ttu-id="67300-213">**PSTypeNames** プロパティには、 **逆シリアル化** された元の型名 (たとえば、Deserialized.System) が含まれてい **ます。Data. DataTable**</span><span class="sxs-lookup"><span data-stu-id="67300-213">The **PSTypeNames** property contains the original type name prefixed with **Deserialized** , for example, **Deserialized.System.Data.DataTable**</span></span>

### <a name="the-allscope-option"></a><span data-ttu-id="67300-214">AllScope オプション</span><span class="sxs-lookup"><span data-stu-id="67300-214">The AllScope Option</span></span>

<span data-ttu-id="67300-215">変数とエイリアスには、 **Allscope** の値を取ることができる **オプション** プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="67300-215">Variables and aliases have an **Option** property that can take a value of **AllScope**.</span></span> <span data-ttu-id="67300-216">**Allscope** プロパティを持つアイテムは、作成した子スコープの一部になりますが、親スコープによってさかのぼって継承されることはありません。</span><span class="sxs-lookup"><span data-stu-id="67300-216">Items that have the **AllScope** property become part of any child scopes that you create, although they are not retroactively inherited by parent scopes.</span></span>

<span data-ttu-id="67300-217">**Allscope** プロパティを持つアイテムは、子スコープに表示され、そのスコープの一部になります。</span><span class="sxs-lookup"><span data-stu-id="67300-217">An item that has the **AllScope** property is visible in the child scope, and it is part of that scope.</span></span> <span data-ttu-id="67300-218">任意のスコープ内の項目に対する変更は、その変数が定義されているすべてのスコープに影響します。</span><span class="sxs-lookup"><span data-stu-id="67300-218">Changes to the item in any scope affect all the scopes in which the variable is defined.</span></span>

### <a name="managing-scope"></a><span data-ttu-id="67300-219">スコープの管理</span><span class="sxs-lookup"><span data-stu-id="67300-219">Managing Scope</span></span>

<span data-ttu-id="67300-220">いくつかのコマンドレットには、特定のスコープ内の項目を取得または設定 (作成および変更) できる **スコープ** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="67300-220">Several cmdlets have a **Scope** parameter that lets you get or set (create and change) items in a particular scope.</span></span> <span data-ttu-id="67300-221">次のコマンドを使用して、 **スコープ** パラメーターを持つセッション内のすべてのコマンドレットを検索します。</span><span class="sxs-lookup"><span data-stu-id="67300-221">Use the following command to find all the cmdlets in your session that have a **Scope** parameter:</span></span>

```powershell
Get-Help * -Parameter scope
```

<span data-ttu-id="67300-222">特定のスコープで参照できる変数を検索するには、のパラメーターを使用し `Scope` `Get-Variable` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-222">To find the variables that are visible in a particular scope, use the `Scope` parameter of `Get-Variable`.</span></span> <span data-ttu-id="67300-223">表示される変数には、グローバル変数、親スコープ内の変数、および現在のスコープ内の変数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="67300-223">The visible variables include global variables, variables in the parent scope, and variables in the current scope.</span></span>

<span data-ttu-id="67300-224">たとえば、次のコマンドは、ローカルスコープで参照できる変数を取得します。</span><span class="sxs-lookup"><span data-stu-id="67300-224">For example, the following command gets the variables that are visible in the local scope:</span></span>

```powershell
Get-Variable -Scope local
```

<span data-ttu-id="67300-225">特定のスコープで変数を作成するには、スコープ修飾子またはの **スコープ** パラメーターを使用し `Set-Variable` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-225">To create a variable in a particular scope, use a scope modifier or the **Scope** parameter of `Set-Variable`.</span></span> <span data-ttu-id="67300-226">グローバルスコープに変数を作成するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="67300-226">The following command creates a variable in the global scope:</span></span>

```powershell
New-Variable -Scope global -Name a -Value "One"
```

<span data-ttu-id="67300-227">`New-Alias`また、、 `Set-Alias` 、またはコマンドレットの scope パラメーターを使用して、スコープを指定することもでき `Get-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-227">You can also use the Scope parameter of the `New-Alias`, `Set-Alias`, or `Get-Alias` cmdlets to specify the scope.</span></span> <span data-ttu-id="67300-228">グローバルスコープにエイリアスを作成するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="67300-228">The following command creates an alias in the global scope:</span></span>

```powershell
New-Alias -Scope global -Name np -Value Notepad.exe
```

<span data-ttu-id="67300-229">特定のスコープ内の関数を取得するに `Get-Item` は、スコープ内でコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="67300-229">To get the functions in a particular scope, use the `Get-Item` cmdlet when you are in the scope.</span></span> <span data-ttu-id="67300-230">`Get-Item`コマンドレットに **スコープ** パラメーターがありません。</span><span class="sxs-lookup"><span data-stu-id="67300-230">The `Get-Item` cmdlet does not have a **Scope** parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="67300-231">**Scope** パラメーターを使用するコマンドレットについては、数値でスコープを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="67300-231">For the cmdlets that use the **Scope** parameter, you can also refer to scopes by number.</span></span> <span data-ttu-id="67300-232">この数値は、あるスコープと別のスコープの相対的な位置を表します。</span><span class="sxs-lookup"><span data-stu-id="67300-232">The number describes the relative position of one scope to another.</span></span> <span data-ttu-id="67300-233">スコープ0は、現在のスコープまたはローカルスコープを表します。</span><span class="sxs-lookup"><span data-stu-id="67300-233">Scope 0 represents the current, or local, scope.</span></span> <span data-ttu-id="67300-234">スコープ1は、直接の親スコープを示します。</span><span class="sxs-lookup"><span data-stu-id="67300-234">Scope 1 indicates the immediate parent scope.</span></span> <span data-ttu-id="67300-235">スコープ2は、親スコープの親を示します。</span><span class="sxs-lookup"><span data-stu-id="67300-235">Scope 2 indicates the parent of the parent scope, and so on.</span></span> <span data-ttu-id="67300-236">多数の再帰的なスコープを作成した場合は、番号付きスコープが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="67300-236">Numbered scopes are useful if you have created many recursive scopes.</span></span>

### <a name="using-dot-source-notation-with-scope"></a><span data-ttu-id="67300-237">スコープでのドットソース表記の使用</span><span class="sxs-lookup"><span data-stu-id="67300-237">Using Dot Source Notation with Scope</span></span>

<span data-ttu-id="67300-238">スクリプトと関数は、スコープのすべての規則に従います。</span><span class="sxs-lookup"><span data-stu-id="67300-238">Scripts and functions follow all the rules of scope.</span></span> <span data-ttu-id="67300-239">これらは特定のスコープで作成し、コマンドレットパラメーターまたはスコープ修飾子を使用してスコープを変更しない限り、そのスコープにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="67300-239">You create them in a particular scope, and they affect only that scope unless you use a cmdlet parameter or a scope modifier to change that scope.</span></span>

<span data-ttu-id="67300-240">ただし、ドットソース表記を使用して、スクリプトまたは関数を現在のスコープに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="67300-240">But, you can add a script or function to the current scope by using dot source notation.</span></span> <span data-ttu-id="67300-241">次に、スクリプトが現在のスコープで実行されると、スクリプトによって作成される関数、エイリアス、および変数が現在のスコープで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="67300-241">Then, when a script runs in the current scope, any functions, aliases, and variables that the script creates are available in the current scope.</span></span>

<span data-ttu-id="67300-242">関数を現在のスコープに追加するには、関数呼び出しで、関数のパスと名前の前にドット (.) とスペースを入力します。</span><span class="sxs-lookup"><span data-stu-id="67300-242">To add a function to the current scope, type a dot (.) and a space before the path and name of the function in the function call.</span></span>

<span data-ttu-id="67300-243">たとえば、スクリプトのスコープ (スクリプトの既定値) の C:\Scripts ディレクトリから Sample.ps1 スクリプトを実行するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="67300-243">For example, to run the Sample.ps1 script from the C:\Scripts directory in the script scope (the default for scripts), use the following command:</span></span>

```powershell
c:\scripts\sample.ps1
```

<span data-ttu-id="67300-244">ローカルスコープで Sample.ps1 スクリプトを実行するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="67300-244">To run the Sample.ps1 script in the local scope, use the following command:</span></span>

```powershell
. c:\scripts.sample.ps1
```

<span data-ttu-id="67300-245">呼び出し演算子 (&) を使用して関数またはスクリプトを実行すると、現在のスコープには追加されません。</span><span class="sxs-lookup"><span data-stu-id="67300-245">When you use the call operator (&) to run a function or script, it is not added to the current scope.</span></span> <span data-ttu-id="67300-246">次の例では、呼び出し演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="67300-246">The following example uses the call operator:</span></span>

```powershell
& c:\scripts.sample.ps1
```

<span data-ttu-id="67300-247">呼び出し演算子の詳細については、 [about_operators](about_operators.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67300-247">You can read more about the call operator in [about_operators](about_operators.md).</span></span>

<span data-ttu-id="67300-248">Sample.ps1 スクリプトによって作成されるエイリアス、関数、または変数は、現在のスコープでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="67300-248">Any aliases, functions, or variables that the Sample.ps1 script creates are not available in the current scope.</span></span>

## <a name="restricting-without-scope"></a><span data-ttu-id="67300-249">スコープを使用しない制限</span><span class="sxs-lookup"><span data-stu-id="67300-249">Restricting Without Scope</span></span>

<span data-ttu-id="67300-250">いくつかの PowerShell の概念は、スコープに似ています。また、スコープと対話します。</span><span class="sxs-lookup"><span data-stu-id="67300-250">A few PowerShell concepts are similar to scope or interact with scope.</span></span> <span data-ttu-id="67300-251">これらの概念は、スコープまたはスコープの動作と混同される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67300-251">These concepts may be confused with scope or the behavior of scope.</span></span>

<span data-ttu-id="67300-252">セッション、モジュール、および入れ子になったプロンプトは自己完結型の環境ですが、セッション内のグローバルスコープの子スコープではありません。</span><span class="sxs-lookup"><span data-stu-id="67300-252">Sessions, modules, and nested prompts are self-contained environments, but they are not child scopes of the global scope in the session.</span></span>

### <a name="sessions"></a><span data-ttu-id="67300-253">セッション</span><span class="sxs-lookup"><span data-stu-id="67300-253">Sessions</span></span>

<span data-ttu-id="67300-254">セッションとは、PowerShell が実行される環境です。</span><span class="sxs-lookup"><span data-stu-id="67300-254">A session is an environment in which PowerShell runs.</span></span> <span data-ttu-id="67300-255">リモートコンピューターにセッションを作成すると、PowerShell によって、リモートコンピューターへの永続的な接続が確立されます。</span><span class="sxs-lookup"><span data-stu-id="67300-255">When you create a session on a remote computer, PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="67300-256">永続的な接続では、複数の関連するコマンドにセッションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="67300-256">The persistent connection lets you use the session for multiple related commands.</span></span>

<span data-ttu-id="67300-257">セッションは包含環境であるため、独自のスコープを持ちますが、セッションは作成されたセッションの子スコープではありません。</span><span class="sxs-lookup"><span data-stu-id="67300-257">Because a session is a contained environment, it has its own scope, but a session is not a child scope of the session in which it was created.</span></span> <span data-ttu-id="67300-258">セッションは、独自のグローバルスコープで開始されます。</span><span class="sxs-lookup"><span data-stu-id="67300-258">The session starts with its own global scope.</span></span> <span data-ttu-id="67300-259">このスコープは、セッションのグローバルスコープに依存しません。</span><span class="sxs-lookup"><span data-stu-id="67300-259">This scope is independent of the global scope of the session.</span></span> <span data-ttu-id="67300-260">セッションでは、子スコープを作成できます。</span><span class="sxs-lookup"><span data-stu-id="67300-260">You can create child scopes in the session.</span></span> <span data-ttu-id="67300-261">たとえば、スクリプトを実行して、セッションに子スコープを作成できます。</span><span class="sxs-lookup"><span data-stu-id="67300-261">For example, you can run a script to create a child scope in a session.</span></span>

### <a name="modules"></a><span data-ttu-id="67300-262">モジュール</span><span class="sxs-lookup"><span data-stu-id="67300-262">Modules</span></span>

<span data-ttu-id="67300-263">Powershell モジュールを使用して、PowerShell ツールを共有し、配布することができます。</span><span class="sxs-lookup"><span data-stu-id="67300-263">You can use a PowerShell module to share and deliver PowerShell tools.</span></span> <span data-ttu-id="67300-264">モジュールは、コマンドレット、スクリプト、関数、変数、別名、およびその他の便利な項目を格納できる単位です。</span><span class="sxs-lookup"><span data-stu-id="67300-264">A module is a unit that can contain cmdlets, scripts, functions, variables, aliases, and other useful items.</span></span> <span data-ttu-id="67300-265">明示的に定義されていない限り、モジュール内の項目にはモジュールの外部からアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="67300-265">Unless explicitly defined, the items in a module are not accessible outside the module.</span></span> <span data-ttu-id="67300-266">そのため、セッションにモジュールを追加し、他の項目がセッションのコマンドレット、スクリプト、関数、およびその他の項目をオーバーライドする可能性があることを心配することなく、パブリック項目を使用できます。</span><span class="sxs-lookup"><span data-stu-id="67300-266">Therefore, you can add the module to your session and use the public items without worrying that the other items might override the cmdlets, scripts, functions, and other items in your session.</span></span>

<span data-ttu-id="67300-267">既定では、モジュールは現在の _スコープ_ ではなく、現在の _セッション状態_ の最上位レベルに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="67300-267">By default, modules are loaded into the top-level of the current _session state_ not the current _scope_.</span></span> <span data-ttu-id="67300-268">現在のセッション状態は、モジュールのセッション状態またはグローバルセッション状態である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67300-268">The current session state could be a module session state or the global session state.</span></span> <span data-ttu-id="67300-269">セッションにモジュールを追加しても、スコープは変更されません。</span><span class="sxs-lookup"><span data-stu-id="67300-269">Adding a module to a session does not change the scope.</span></span> <span data-ttu-id="67300-270">グローバルスコープにいる場合は、モジュールがグローバルセッション状態に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="67300-270">If you are in the global scope, then modules are loaded into the global session state.</span></span> <span data-ttu-id="67300-271">すべてのエクスポートは、グローバルテーブルに配置されます。</span><span class="sxs-lookup"><span data-stu-id="67300-271">Any exports are placed into the global tables.</span></span>
<span data-ttu-id="67300-272">Module1 _内_ から module2 を読み込むと、module2 がグローバルセッション状態ではなく、module1.vb のセッション状態に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="67300-272">If you load module2 from _within_ module1, module2 is loaded into the session state of module1 not the global session state.</span></span> <span data-ttu-id="67300-273">Module2 からのエクスポートは、module1 セッション状態の先頭に配置されます。</span><span class="sxs-lookup"><span data-stu-id="67300-273">Any exports from module2 are placed at the top of the module1 session state.</span></span> <span data-ttu-id="67300-274">を使用する場合、 `Import-Module -Scope local` エクスポートは最上位レベルではなく現在のスコープオブジェクトに配置されます。</span><span class="sxs-lookup"><span data-stu-id="67300-274">If you use `Import-Module -Scope local`, then the exports are placed into the current scope object rather than at the top level.</span></span> <span data-ttu-id="67300-275">_モジュール_ を使用していて、 `Import-Module -Scope global` (または) を使用して `Import-Module -Global` 別のモジュールを読み込む場合、そのモジュールとそのエクスポートは、モジュールのローカルセッション状態ではなく、グローバルセッション状態に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="67300-275">If you are _in a module_ and use `Import-Module -Scope global` (or `Import-Module -Global`) to load another module, that module and it's exports are loaded into the global session state instead of the module's local session state.</span></span> <span data-ttu-id="67300-276">この機能は、モジュールを操作するモジュールを作成するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="67300-276">This feature was designed for writing module that manipulate modules.</span></span> <span data-ttu-id="67300-277">**Windowscompatibility** モジュールはこれを行い、プロキシモジュールをグローバルセッション状態にインポートします。</span><span class="sxs-lookup"><span data-stu-id="67300-277">The **WindowsCompatibility** module does this to import proxy modules into the global session state.</span></span>

<span data-ttu-id="67300-278">セッション状態では、モジュールは独自のスコープを持ちます。</span><span class="sxs-lookup"><span data-stu-id="67300-278">Within the session state, modules have their own scope.</span></span> <span data-ttu-id="67300-279">次のモジュールを考えてみましょう `C:\temp\mod1.psm1` 。</span><span class="sxs-lookup"><span data-stu-id="67300-279">Consider the following module `C:\temp\mod1.psm1`:</span></span>

```powershell
$a = "Hello"

function foo {
    "`$a = $a"
    "`$global:a = $global:a"
}
```

<span data-ttu-id="67300-280">次に、グローバル変数を作成し `$a` 、値を指定して、関数 **foo** を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="67300-280">Now we create a global variable `$a`, give it a value and call the function **foo**.</span></span>

```powershell
$a = "Goodbye"
foo
```

<span data-ttu-id="67300-281">モジュールは `$a` モジュールスコープ内で変数を宣言し、関数 **foo** は両方のスコープで変数の値を出力します。</span><span class="sxs-lookup"><span data-stu-id="67300-281">The module declares the variable `$a` in the module scope then the function **foo** outputs the value of the variable in both scopes.</span></span>

```Output
$a = Hello
$global:a = Goodbye
```

### <a name="nested-prompts"></a><span data-ttu-id="67300-282">入れ子になったプロンプト</span><span class="sxs-lookup"><span data-stu-id="67300-282">Nested Prompts</span></span>

<span data-ttu-id="67300-283">入れ子になったプロンプトには、独自のスコープがありません。</span><span class="sxs-lookup"><span data-stu-id="67300-283">Nested prompts do not have their own scope.</span></span> <span data-ttu-id="67300-284">入れ子になったプロンプトを入力すると、入れ子になったプロンプトは環境のサブセットになります。</span><span class="sxs-lookup"><span data-stu-id="67300-284">When you enter a nested prompt, the nested prompt is a subset of the environment.</span></span> <span data-ttu-id="67300-285">ただし、ローカルスコープ内にとどまります。</span><span class="sxs-lookup"><span data-stu-id="67300-285">But, you remain within the local scope.</span></span>

<span data-ttu-id="67300-286">スクリプトには独自のスコープがあります。</span><span class="sxs-lookup"><span data-stu-id="67300-286">Scripts do have their own scope.</span></span> <span data-ttu-id="67300-287">スクリプトをデバッグしているときに、スクリプト内のブレークポイントに近づいた場合は、スクリプトのスコープを入力します。</span><span class="sxs-lookup"><span data-stu-id="67300-287">If you are debugging a script, and you reach a breakpoint in the script, you enter the script scope.</span></span>

### <a name="private-option"></a><span data-ttu-id="67300-288">プライベートオプション</span><span class="sxs-lookup"><span data-stu-id="67300-288">Private Option</span></span>

<span data-ttu-id="67300-289">エイリアスと変数には、 **Private** という値を取ることができる **オプション** プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="67300-289">Aliases and variables have an **Option** property that can take a value of **Private**.</span></span> <span data-ttu-id="67300-290">**プライベート** オプションを持つアイテムは、作成されたスコープ内で表示および変更できますが、スコープ外で表示または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="67300-290">Items that have the **Private** option can be viewed and changed in the scope in which they are created, but they cannot be viewed or changed outside that scope.</span></span>

<span data-ttu-id="67300-291">たとえば、グローバルスコープでプライベートオプションを持つ変数を作成し、スクリプトを実行すると、 `Get-Variable` スクリプト内のコマンドにプライベート変数は表示されません。</span><span class="sxs-lookup"><span data-stu-id="67300-291">For example, if you create a variable that has a private option in the global scope and then run a script, `Get-Variable` commands in the script do not display the private variable.</span></span> <span data-ttu-id="67300-292">このインスタンスでグローバルスコープ修飾子を使用しても、プライベート変数は表示されません。</span><span class="sxs-lookup"><span data-stu-id="67300-292">Using the global scope modifier in this instance does not display the private variable.</span></span>

<span data-ttu-id="67300-293">、、、およびコマンドレットの option パラメーターを使用して、 `New-Variable` `Set-Variable` `New-Alias` `Set-Alias` option プロパティの値を Private に設定できます。</span><span class="sxs-lookup"><span data-stu-id="67300-293">You can use the Option parameter of the `New-Variable`, `Set-Variable`, `New-Alias`, and `Set-Alias` cmdlets to set the value of the Option property to Private.</span></span>

### <a name="visibility"></a><span data-ttu-id="67300-294">表示</span><span class="sxs-lookup"><span data-stu-id="67300-294">Visibility</span></span>

<span data-ttu-id="67300-295">変数またはエイリアスの **可視性** プロパティによって、コンテナーの外側に項目が作成されたことを確認できるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="67300-295">The **Visibility** property of a variable or alias determines whether you can see the item outside the container, in which it was created.</span></span> <span data-ttu-id="67300-296">コンテナーには、モジュール、スクリプト、またはスナップインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="67300-296">A container could be a module, script, or snap-in.</span></span> <span data-ttu-id="67300-297">可視性は、 **Option** プロパティの **プライベート** 値がスコープ向けに設計されているのと同じ方法でコンテナー用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="67300-297">Visibility is designed for containers in the same way that the **Private** value of the **Option** property is designed for scopes.</span></span>

<span data-ttu-id="67300-298">**可視性** プロパティは、 **パブリック** と **プライベート** の値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="67300-298">The **Visibility** property takes the **Public** and **Private** values.</span></span> <span data-ttu-id="67300-299">プライベート可視性を持つアイテムは、そのアイテムが作成されたコンテナー内でのみ表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="67300-299">Items that have private visibility can be viewed and changed only in the container in which they were created.</span></span> <span data-ttu-id="67300-300">コンテナーを追加またはインポートした場合、プライベート可視性を持つアイテムを表示または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="67300-300">If the container is added or imported, the items that have private visibility cannot be viewed or changed.</span></span>

<span data-ttu-id="67300-301">可視性はコンテナー用に設計されているため、スコープでは異なる方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="67300-301">Because visibility is designed for containers, it works differently in a scope.</span></span>

- <span data-ttu-id="67300-302">グローバルスコープでプライベート可視性を持つアイテムを作成した場合、そのアイテムを表示または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="67300-302">If you create an item that has private visibility in the global scope, you cannot view or change the item in any scope.</span></span>
- <span data-ttu-id="67300-303">プライベート可視性を持つ変数の値を表示または変更しようとすると、PowerShell によってエラーメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="67300-303">If you try to view or change the value of a variable that has private visibility, PowerShell returns an error message.</span></span>

<span data-ttu-id="67300-304">およびコマンドレットを使用して、 `New-Variable` `Set-Variable` プライベート可視性を持つ変数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="67300-304">You can use the `New-Variable` and `Set-Variable` cmdlets to create a variable that has private visibility.</span></span>

## <a name="examples"></a><span data-ttu-id="67300-305">例</span><span class="sxs-lookup"><span data-stu-id="67300-305">Examples</span></span>

### <a name="example-1-change-a-variable-value-only-in-a-script"></a><span data-ttu-id="67300-306">例 1: スクリプト内の変数の値のみを変更する</span><span class="sxs-lookup"><span data-stu-id="67300-306">Example 1: Change a Variable Value Only in a Script</span></span>

<span data-ttu-id="67300-307">次のコマンドは、スクリプト内の変数の値を変更し `$ConfirmPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-307">The following command changes the value of the `$ConfirmPreference` variable in a script.</span></span> <span data-ttu-id="67300-308">この変更はグローバルスコープには影響しません。</span><span class="sxs-lookup"><span data-stu-id="67300-308">The change does not affect the global scope.</span></span>

<span data-ttu-id="67300-309">最初に、ローカルスコープの変数の値を表示するには、 `$ConfirmPreference` 次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="67300-309">First, to display the value of the `$ConfirmPreference` variable in the local scope, use the following command:</span></span>

```
PS>  $ConfirmPreference
High
```

<span data-ttu-id="67300-310">次のコマンドを含む Scope.ps1 スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="67300-310">Create a Scope.ps1 script that contains the following commands:</span></span>

```powershell
$ConfirmPreference = "Low"
"The value of `$ConfirmPreference is $ConfirmPreference."
```

<span data-ttu-id="67300-311">スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="67300-311">Run the script.</span></span> <span data-ttu-id="67300-312">スクリプトによって変数の値が変更され、 `$ConfirmPreference` スクリプトスコープでその値が報告されます。</span><span class="sxs-lookup"><span data-stu-id="67300-312">The script changes the value of the `$ConfirmPreference` variable and then reports its value in the script scope.</span></span> <span data-ttu-id="67300-313">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="67300-313">The output should resemble the following output:</span></span>

```output
The value of $ConfirmPreference is Low.
```

<span data-ttu-id="67300-314">次に、現在のスコープ内の変数の現在の値をテストし `$ConfirmPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-314">Next, test the current value of the `$ConfirmPreference` variable in the current scope.</span></span>

```
PS>  $ConfirmPreference
High
```

<span data-ttu-id="67300-315">この例は、スクリプトスコープ内の変数の値を変更しても、親スコープ内の変数の値には影響しないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="67300-315">This example shows that changes to the value of a variable in the script scope does not affect the variable\`s value in the parent scope.</span></span>

### <a name="example-2-view-a-variable-value-in-different-scopes"></a><span data-ttu-id="67300-316">例 2: 異なるスコープの変数値を表示する</span><span class="sxs-lookup"><span data-stu-id="67300-316">Example 2: View a Variable Value in Different Scopes</span></span>

<span data-ttu-id="67300-317">スコープ修飾子を使用して、ローカルスコープおよび親スコープ内の変数の値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="67300-317">You can use scope modifiers to view the value of a variable in the local scope and in a parent scope.</span></span>

<span data-ttu-id="67300-318">まず、 `$test` グローバルスコープで変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="67300-318">First, define a `$test` variable in the global scope.</span></span>

```powershell
$test = "Global"
```

<span data-ttu-id="67300-319">次に、変数を定義する Sample.ps1 スクリプトを作成し `$test` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-319">Next, create a Sample.ps1 script that defines the `$test` variable.</span></span> <span data-ttu-id="67300-320">スクリプトでは、スコープ修飾子を使用して、変数のグローバルバージョンまたはローカルバージョンのいずれかを参照し `$test` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-320">In the script, use a scope modifier to refer to either the global or local versions of the `$test` variable.</span></span>

<span data-ttu-id="67300-321">Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="67300-321">In Sample.ps1:</span></span>

```powershell
$test = "Local"
"The local value of `$test is $test."
"The global value of `$test is $global:test."
```

<span data-ttu-id="67300-322">Sample.ps1 を実行すると、出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="67300-322">When you run Sample.ps1, the output should resemble the following output:</span></span>

```output
The local value of $test is Local.
The global value of $test is Global.
```

<span data-ttu-id="67300-323">スクリプトが完了すると、のグローバル値のみ `$test` がセッションで定義されます。</span><span class="sxs-lookup"><span data-stu-id="67300-323">When the script is complete, only the global value of `$test` is defined in the session.</span></span>

```
PS>  $test
Global
```

### <a name="example-3-change-the-value-of-a-variable-in-a-parent-scope"></a><span data-ttu-id="67300-324">例 3: 親スコープ内の変数の値を変更する</span><span class="sxs-lookup"><span data-stu-id="67300-324">Example 3: Change the Value of a Variable in a Parent Scope</span></span>

<span data-ttu-id="67300-325">プライベートオプションや別の方法を使用して項目を保護しない限り、親スコープ内の変数の値を表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="67300-325">Unless you protect an item by using the Private option or another method, you can view and change the value of a variable in a parent scope.</span></span>

<span data-ttu-id="67300-326">まず、 `$test` グローバルスコープで変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="67300-326">First, define a `$test` variable in the global scope.</span></span>

```powershell
$test = "Global"
```

<span data-ttu-id="67300-327">次に、変数を定義する Sample.ps1 スクリプトを作成し `$test` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-327">Next, create a Sample.ps1 script that defines the `$test` variable.</span></span> <span data-ttu-id="67300-328">スクリプトでは、スコープ修飾子を使用して、変数のグローバルバージョンまたはローカルバージョンのいずれかを参照し `$test` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-328">In the script, use a scope modifier to refer to either the global or local versions of the `$test` variable.</span></span>

<span data-ttu-id="67300-329">Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="67300-329">In Sample.ps1:</span></span>

```powershell
$global:test = "Local"
"The global value of `$test is $global:test."
```

<span data-ttu-id="67300-330">スクリプトが完了すると、のグローバル値 `$test` が変更されます。</span><span class="sxs-lookup"><span data-stu-id="67300-330">When the script is complete, the global value of `$test` is changed.</span></span>

```
PS>  $test
Local
```

### <a name="example-4-creating-a-private-variable"></a><span data-ttu-id="67300-331">例 4: プライベート変数の作成</span><span class="sxs-lookup"><span data-stu-id="67300-331">Example 4: Creating a Private Variable</span></span>

<span data-ttu-id="67300-332">プライベート変数は、value が *private* である **オプション** プロパティを持つ変数です。</span><span class="sxs-lookup"><span data-stu-id="67300-332">A private variable is a variable that has an **Option** property that has a value of *Private*.</span></span> <span data-ttu-id="67300-333">*プライベート* 変数は子スコープによって継承されますが、作成されたスコープ内でのみ表示または変更できます。</span><span class="sxs-lookup"><span data-stu-id="67300-333">*Private* variables are inherited by the child scope, but they can only be viewed or changed in the scope in which they were created.</span></span>

<span data-ttu-id="67300-334">次のコマンドは、ローカルスコープ内にというプライベート変数を作成し `$ptest` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-334">The following command creates a private variable called `$ptest` in the local scope.</span></span>

```powershell
New-Variable -Name ptest -Value 1 -Option private
```

<span data-ttu-id="67300-335">ローカルスコープのの値を表示および変更でき `$ptest` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-335">You can display and change the value of `$ptest` in the local scope.</span></span>

```
PS>  $ptest
1

PS>  $ptest = 2
PS>  $ptest
2
```

<span data-ttu-id="67300-336">次に、次のコマンドを含む Sample.ps1 スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="67300-336">Next, create a Sample.ps1 script that contains the following commands.</span></span> <span data-ttu-id="67300-337">コマンドは、の値を表示して変更しようとし `$ptest` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-337">The command tries to display and change the value of `$ptest`.</span></span>

<span data-ttu-id="67300-338">Sample.ps1:</span><span class="sxs-lookup"><span data-stu-id="67300-338">In Sample.ps1:</span></span>

```powershell
"The value of `$Ptest is $Ptest."
"The value of `$Ptest is $global:Ptest."
```

<span data-ttu-id="67300-339">`$ptest`変数はスクリプトスコープに表示されません。出力は空です。</span><span class="sxs-lookup"><span data-stu-id="67300-339">The `$ptest` variable is not visible in the script scope, the output is empty.</span></span>

```powershell
"The value of $Ptest is ."
"The value of $Ptest is ."
```

### <a name="example-5-using-a-local-variable-in-a-remote-command"></a><span data-ttu-id="67300-340">例 5: リモートコマンドでローカル変数を使用する</span><span class="sxs-lookup"><span data-stu-id="67300-340">Example 5: Using a Local Variable in a Remote Command</span></span>

<span data-ttu-id="67300-341">ローカルセッションで作成されたリモートコマンドの変数については、スコープ修飾子を使用し `Using` ます。</span><span class="sxs-lookup"><span data-stu-id="67300-341">For variables in a remote command created in the local session, use the `Using` scope modifier.</span></span> <span data-ttu-id="67300-342">PowerShell では、リモートコマンドの変数がリモートセッションで作成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="67300-342">PowerShell assumes that the variables in remote commands were created in the remote session.</span></span>

<span data-ttu-id="67300-343">の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67300-343">The syntax is:</span></span>

```
$Using:<VariableName>
```

<span data-ttu-id="67300-344">たとえば、次のコマンドは、 `$Cred` ローカルセッションで変数を作成し、 `$Cred` リモートコマンドでその変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="67300-344">For example, the following commands create a `$Cred` variable in the local session and then use the `$Cred` variable in a remote command:</span></span>

```powershell
$Cred = Get-Credential
Invoke-Command $s {Remove-Item .\Test*.ps1 -Credential $Using:Cred}
```

<span data-ttu-id="67300-345">Using スコープは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="67300-345">The Using scope was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="67300-346">PowerShell 2.0 で、変数がローカルセッションで作成されたことを示すには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="67300-346">In PowerShell 2.0, to indicate that a variable was created in the local session, use the following command format.</span></span>

```powershell
$Cred = Get-Credential
Invoke-Command $s {
  param($c)
  Remove-Item .\Test*.ps1 -Credential $c
} -ArgumentList $Cred
```

## <a name="see-also"></a><span data-ttu-id="67300-347">関連項目</span><span class="sxs-lookup"><span data-stu-id="67300-347">See also</span></span>

[<span data-ttu-id="67300-348">about_Variables</span><span class="sxs-lookup"><span data-stu-id="67300-348">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="67300-349">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="67300-349">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="67300-350">about_Functions</span><span class="sxs-lookup"><span data-stu-id="67300-350">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="67300-351">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="67300-351">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="67300-352">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="67300-352">Start-ThreadJob</span></span>](/powershell/module/ThreadJob/Start-ThreadJob)
