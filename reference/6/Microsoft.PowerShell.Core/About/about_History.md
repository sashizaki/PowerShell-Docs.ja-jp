---
description: コマンド履歴のコマンドを取得して実行する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_history?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_History
ms.openlocfilehash: e009b6d1ecd739c321bdc45e5b043cbdea392db0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221563"
---
# <a name="about-history"></a><span data-ttu-id="a2883-104">履歴について</span><span class="sxs-lookup"><span data-stu-id="a2883-104">About History</span></span>

## <a name="short-description"></a><span data-ttu-id="a2883-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="a2883-105">Short Description</span></span>
<span data-ttu-id="a2883-106">コマンド履歴のコマンドを取得して実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2883-106">Describes how to get and run commands in the command history.</span></span>

## <a name="long-description"></a><span data-ttu-id="a2883-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="a2883-107">Long Description</span></span>

<span data-ttu-id="a2883-108">コマンドプロンプトでコマンドを入力すると、PowerShell によってコマンド履歴にコマンドが保存されます。</span><span class="sxs-lookup"><span data-stu-id="a2883-108">When you enter a command at the command prompt, PowerShell saves the command in the command history.</span></span> <span data-ttu-id="a2883-109">履歴内のコマンドは、作業のレコードとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2883-109">You can use the commands in the history as a record of your work.</span></span> <span data-ttu-id="a2883-110">また、コマンドの履歴からコマンドを再呼び出しし、実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2883-110">And, you can recall and run the commands from the command history.</span></span>

<span data-ttu-id="a2883-111">PowerShell には、組み込み履歴と **Psreadline** モジュールによって管理される履歴という2つの異なる履歴プロバイダーがあります。</span><span class="sxs-lookup"><span data-stu-id="a2883-111">PowerShell has two different history providers: the built-in history and the history managed by the **PSReadLine** module.</span></span> <span data-ttu-id="a2883-112">履歴は個別に管理されますが、両方の履歴は、 **Psreadline** が読み込まれるセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2883-112">The histories are managed separately, but both histories are available in sessions where **PSReadLine** is loaded.</span></span>

## <a name="using-the-psreadline-history"></a><span data-ttu-id="a2883-113">PSReadLine 履歴の使用</span><span class="sxs-lookup"><span data-stu-id="a2883-113">Using the PSReadLine history</span></span>

<span data-ttu-id="a2883-114">PSReadLine 履歴は、すべての PowerShell セッションで使用されているコマンドを追跡します。</span><span class="sxs-lookup"><span data-stu-id="a2883-114">The PSReadLine history tracks the commands used in all PowerShell sessions.</span></span>
<span data-ttu-id="a2883-115">履歴は、ホストごとに中央のファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="a2883-115">The history is written to a central file per host.</span></span> <span data-ttu-id="a2883-116">その履歴ファイルはすべてのセッションで使用でき、過去のすべての履歴が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a2883-116">That history file is available to all sessions and contains all past history.</span></span> <span data-ttu-id="a2883-117">セッションが終了しても、履歴は削除されません。</span><span class="sxs-lookup"><span data-stu-id="a2883-117">The history is not deleted when the session ends.</span></span> <span data-ttu-id="a2883-118">また、この履歴をコマンドレットで管理することはできません `*-History` 。</span><span class="sxs-lookup"><span data-stu-id="a2883-118">Also, that history cannot be managed by the `*-History` cmdlets.</span></span> <span data-ttu-id="a2883-119">詳細については、「 [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2883-119">For more information, see [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span></span>

## <a name="using-the-built-in-session-history"></a><span data-ttu-id="a2883-120">組み込みのセッション履歴を使用する</span><span class="sxs-lookup"><span data-stu-id="a2883-120">Using the built-in session history</span></span>

<span data-ttu-id="a2883-121">組み込みの履歴は、現在のセッションで使用されているコマンドのみを追跡します。</span><span class="sxs-lookup"><span data-stu-id="a2883-121">The built-in history only tracks the commands used in the current session.</span></span> <span data-ttu-id="a2883-122">履歴は、他のセッションでは使用できず、セッションが終了すると削除されます。</span><span class="sxs-lookup"><span data-stu-id="a2883-122">The history is not available to other sessions and is deleted when the session ends.</span></span>

### <a name="history-cmdlets"></a><span data-ttu-id="a2883-123">History コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a2883-123">History Cmdlets</span></span>

<span data-ttu-id="a2883-124">PowerShell には、コマンドの履歴を管理するコマンドレットのセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a2883-124">PowerShell has a set of cmdlets that manage the command history.</span></span>

| <span data-ttu-id="a2883-125">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a2883-125">Cmdlet</span></span>           | <span data-ttu-id="a2883-126">エイリアス</span><span class="sxs-lookup"><span data-stu-id="a2883-126">Alias</span></span>  | <span data-ttu-id="a2883-127">説明</span><span class="sxs-lookup"><span data-stu-id="a2883-127">Description</span></span>                                |
| ---------------- | ------ | ------------------------------------------ |
| `Get-History`    | `h`    | <span data-ttu-id="a2883-128">コマンドの履歴を取得します。</span><span class="sxs-lookup"><span data-stu-id="a2883-128">Gets the command history.</span></span>                  |
| `Invoke-History` | `r`    | <span data-ttu-id="a2883-129">コマンドの履歴でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a2883-129">Runs a command in the command history.</span></span>     |
| `Add-History`    |        | <span data-ttu-id="a2883-130">コマンドの履歴にコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="a2883-130">Adds a command to the command history.</span></span>     |
| `Clear-History`  | `clhy` | <span data-ttu-id="a2883-131">コマンド履歴からコマンドを削除します。</span><span class="sxs-lookup"><span data-stu-id="a2883-131">Deletes commands from the command history.</span></span> |

### <a name="keyboard-shortcuts-for-managing-history"></a><span data-ttu-id="a2883-132">履歴を管理するためのキーボードショートカット</span><span class="sxs-lookup"><span data-stu-id="a2883-132">Keyboard Shortcuts for Managing History</span></span>

<span data-ttu-id="a2883-133">PowerShell コンソールでは、次のショートカットを使用してコマンドの履歴を管理できます。</span><span class="sxs-lookup"><span data-stu-id="a2883-133">In the PowerShell console, you can use the following shortcuts to manage the command history.</span></span>

- <span data-ttu-id="a2883-134">[ <kbd>Uparrow</kbd> ]: 前のコマンドを表示します。</span><span class="sxs-lookup"><span data-stu-id="a2883-134"><kbd>UpArrow</kbd> - Displays the previous command.</span></span>
- <span data-ttu-id="a2883-135"><kbd>Downarrow</kbd> -次のコマンドを表示します。</span><span class="sxs-lookup"><span data-stu-id="a2883-135"><kbd>DownArrow</kbd> - Displays the next command.</span></span>
- <span data-ttu-id="a2883-136"><kbd>F7</kbd> -コマンドの履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="a2883-136"><kbd>F7</kbd> - Displays the command history.</span></span>
- <span data-ttu-id="a2883-137"><kbd>ESC</kbd> -履歴を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="a2883-137"><kbd>ESC</kbd> - To hide the history.</span></span>
- <span data-ttu-id="a2883-138"><kbd>F8</kbd> -コマンドを検索します。</span><span class="sxs-lookup"><span data-stu-id="a2883-138"><kbd>F8</kbd> - Finds a command.</span></span> <span data-ttu-id="a2883-139">1つ以上の文字を入力してから、 <kbd>F8</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a2883-139">Type one or more characters then press <kbd>F8</kbd>.</span></span> <span data-ttu-id="a2883-140">次のインスタンスにもう一度 <kbd>F8</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a2883-140">Press <kbd>F8</kbd> again the next instance.</span></span>
- <span data-ttu-id="a2883-141"><kbd>F9</kbd> -履歴 ID を使ってコマンドを検索します。</span><span class="sxs-lookup"><span data-stu-id="a2883-141"><kbd>F9</kbd> - Find a command by history ID.</span></span> <span data-ttu-id="a2883-142">履歴 ID を入力し、 <kbd>F9</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a2883-142">Type the history ID then press <kbd>F9</kbd>.</span></span> <span data-ttu-id="a2883-143"><kbd>F7</kbd>キーを押して ID を検索します。</span><span class="sxs-lookup"><span data-stu-id="a2883-143">Press <kbd>F7</kbd> to find the ID.</span></span>
- <span data-ttu-id="a2883-144"><kbd>#</kbd>`<string>`</kbd><kbd>[] タブ</kbd> -の履歴を検索 `*<string>*` し、最新の一致を返します。</span><span class="sxs-lookup"><span data-stu-id="a2883-144"><kbd>#</kbd>`<string>`</kbd><kbd>Tab</kbd> - Search the history for `*<string>*` and returns the most recent match.</span></span> <span data-ttu-id="a2883-145"><kbd>Tab</kbd>キーを繰り返し押すと、履歴内の一致する項目が順番に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2883-145">If you press <kbd>Tab</kbd> repeatedly, it cycles through the matching items in your history.</span></span>

> [!NOTE]
> <span data-ttu-id="a2883-146">これらのキーバインドは、コンソールホストアプリケーションによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="a2883-146">These key bindings are implemented by the console host application.</span></span> <span data-ttu-id="a2883-147">Visual Studio Code や Windows ターミナルなどの他のアプリケーションでは、異なるキーバインドを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="a2883-147">Other applications, such as Visual Studio Code or Windows Terminal, can have different key bindings.</span></span> <span data-ttu-id="a2883-148">バインドは、PSReadLine モジュールでオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="a2883-148">The bindings can be overridden by the PSReadLine module.</span></span> <span data-ttu-id="a2883-149">PSReadLine は、PowerShell セッションを開始すると自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="a2883-149">PSReadLine loads automatically when you start a PowerShell session.</span></span>
> <span data-ttu-id="a2883-150">PSReadLine が読み込まれている場合、 <kbd>F7</kbd> と <kbd>F9</kbd> はどの関数にもバインドされていません。</span><span class="sxs-lookup"><span data-stu-id="a2883-150">With PSReadLine loaded, <kbd>F7</kbd> and <kbd>F9</kbd> are not bound to any function.</span></span> <span data-ttu-id="a2883-151">PSReadLine では、同等の機能は提供されません。</span><span class="sxs-lookup"><span data-stu-id="a2883-151">PSReadLine does not provide equivalent functionality.</span></span> <span data-ttu-id="a2883-152">詳細については、「 [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2883-152">For more information, see [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span></span>

### <a name="maximumhistorycount"></a><span data-ttu-id="a2883-153">Maximumhistorycount ユーザー</span><span class="sxs-lookup"><span data-stu-id="a2883-153">MaximumHistoryCount</span></span>

<span data-ttu-id="a2883-154">ユーザー `$MaximumHistoryCount` 設定変数は、PowerShell がコマンドの履歴に保存するコマンドの最大数を決定します。</span><span class="sxs-lookup"><span data-stu-id="a2883-154">The `$MaximumHistoryCount` preference variable determines the maximum number of commands that PowerShell saves in the command history.</span></span> <span data-ttu-id="a2883-155">既定値は</span><span class="sxs-lookup"><span data-stu-id="a2883-155">The default value is</span></span>
4096.

<span data-ttu-id="a2883-156">たとえば、次のコマンドは、 `$MaximumHistoryCount` を100コマンドに下げます。</span><span class="sxs-lookup"><span data-stu-id="a2883-156">For example, the following command lowers the `$MaximumHistoryCount` to 100 commands:</span></span>

```powershell
$MaximumHistoryCount = 100
```

<span data-ttu-id="a2883-157">設定を適用するには、PowerShell を再起動します。</span><span class="sxs-lookup"><span data-stu-id="a2883-157">To apply the setting, restart PowerShell.</span></span>

<span data-ttu-id="a2883-158">すべての PowerShell セッションの新しい変数値を保存するには、割り当てステートメントを PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="a2883-158">To save the new variable value for all your PowerShell sessions, add the assignment statement to a PowerShell profile.</span></span> <span data-ttu-id="a2883-159">プロファイルの詳細については、「[about_Profiles](about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2883-159">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="a2883-160">ユーザー設定変数の詳細については `$MaximumHistoryCount` 、「 [about_Preference_Variables](about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2883-160">For more information about the `$MaximumHistoryCount` preference variable, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

### <a name="order-of-commands-in-the-history"></a><span data-ttu-id="a2883-161">履歴内のコマンドの順序</span><span class="sxs-lookup"><span data-stu-id="a2883-161">Order of Commands in the History</span></span>

<span data-ttu-id="a2883-162">コマンドの実行が完了すると、コマンドが入力されたときではなく、コマンドが履歴に追加されます。</span><span class="sxs-lookup"><span data-stu-id="a2883-162">Commands are added to the history when the command finishes executing, not when the command is entered.</span></span> <span data-ttu-id="a2883-163">コマンドが完了するまでに時間がかかる場合、またはコマンドが入れ子になったプロンプトで実行されている場合は、コマンドが履歴に表示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2883-163">If commands take some time to be completed, or if the commands are executing in a nested prompt, the commands might appear to be out of order in the history.</span></span> <span data-ttu-id="a2883-164">入れ子になったプロンプトで実行されているコマンドは、プロンプトレベルを終了した場合にのみ完了します。</span><span class="sxs-lookup"><span data-stu-id="a2883-164">Commands that are executing in a nested prompt are completed only when you exit the prompt level.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2883-165">参照</span><span class="sxs-lookup"><span data-stu-id="a2883-165">See Also</span></span>

- [<span data-ttu-id="a2883-166">about_Line_Editing</span><span class="sxs-lookup"><span data-stu-id="a2883-166">about_Line_Editing</span></span>](about_Line_Editing.md)
- [<span data-ttu-id="a2883-167">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="a2883-167">about_Preference_Variables</span></span>](about_Preference_Variables.md)
- [<span data-ttu-id="a2883-168">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="a2883-168">about_Profiles</span></span>](about_Profiles.md)
- [<span data-ttu-id="a2883-169">about_Variables</span><span class="sxs-lookup"><span data-stu-id="a2883-169">about_Variables</span></span>](about_Variables.md)
- [<span data-ttu-id="a2883-170">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="a2883-170">about_PSReadLine</span></span>](../../PSReadLine/About/about_PSReadLine.md)
