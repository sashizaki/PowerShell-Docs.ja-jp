---
description: PowerShell の実行ポリシーについて説明し、その管理方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Execution_Policies
ms.openlocfilehash: 3332adb76c76fa644d23060abe2af43bd45a15a6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223512"
---
# <a name="about-execution-policies"></a><span data-ttu-id="25ced-104">実行ポリシーについて</span><span class="sxs-lookup"><span data-stu-id="25ced-104">About Execution Policies</span></span>

## <a name="short-description"></a><span data-ttu-id="25ced-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="25ced-105">Short Description</span></span>

<span data-ttu-id="25ced-106">PowerShell の実行ポリシーについて説明し、その管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="25ced-106">Describes the PowerShell execution policies and explains how to manage them.</span></span>

## <a name="long-description"></a><span data-ttu-id="25ced-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="25ced-107">Long Description</span></span>

<span data-ttu-id="25ced-108">PowerShell の実行ポリシーは、PowerShell が構成ファイルを読み込み、スクリプトを実行するときの条件を制御する安全性機能です。</span><span class="sxs-lookup"><span data-stu-id="25ced-108">PowerShell's execution policy is a safety feature that controls the conditions under which PowerShell loads configuration files and runs scripts.</span></span> <span data-ttu-id="25ced-109">この機能は、悪意のあるスクリプトの実行を防止するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="25ced-109">This feature helps prevent the execution of malicious scripts.</span></span>

<span data-ttu-id="25ced-110">Windows コンピューターでは、ローカルコンピューター、現在のユーザー、または特定のセッションの実行ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="25ced-110">On a Windows computer you can set an execution policy for the local computer, for the current user, or for a particular session.</span></span> <span data-ttu-id="25ced-111">グループポリシー設定を使用して、コンピューターとユーザーの実行ポリシーを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="25ced-111">You can also use a Group Policy setting to set execution policies for computers and users.</span></span>

<span data-ttu-id="25ced-112">ローカルコンピューターと現在のユーザーの実行ポリシーは、レジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="25ced-112">Execution policies for the local computer and current user are stored in the registry.</span></span> <span data-ttu-id="25ced-113">PowerShell プロファイルで実行ポリシーを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="25ced-113">You don't need to set execution policies in your PowerShell profile.</span></span>
<span data-ttu-id="25ced-114">特定のセッションの実行ポリシーはメモリにのみ格納され、セッションが閉じられると失われます。</span><span class="sxs-lookup"><span data-stu-id="25ced-114">The execution policy for a particular session is stored only in memory and is lost when the session is closed.</span></span>

<span data-ttu-id="25ced-115">実行ポリシーは、ユーザーの操作を制限するセキュリティシステムではありません。</span><span class="sxs-lookup"><span data-stu-id="25ced-115">The execution policy isn't a security system that restricts user actions.</span></span> <span data-ttu-id="25ced-116">たとえば、スクリプトを実行できない場合、ユーザーはコマンドラインでスクリプトの内容を入力することで、ポリシーを簡単にバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="25ced-116">For example, users can easily bypass a policy by typing the script contents at the command line when they cannot run a script.</span></span> <span data-ttu-id="25ced-117">代わりに、実行ポリシーを使用して、ユーザーが基本的な規則を設定し、意図せずに違反しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="25ced-117">Instead, the execution policy helps users to set basic rules and prevents them from violating them unintentionally.</span></span>

## <a name="powershell-execution-policies"></a><span data-ttu-id="25ced-118">PowerShell 実行ポリシー</span><span class="sxs-lookup"><span data-stu-id="25ced-118">PowerShell execution policies</span></span>

<span data-ttu-id="25ced-119">PowerShell の実行ポリシーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="25ced-119">The PowerShell execution policies are as follows:</span></span>

### <a name="allsigned"></a><span data-ttu-id="25ced-120">AllSigned</span><span class="sxs-lookup"><span data-stu-id="25ced-120">AllSigned</span></span>

- <span data-ttu-id="25ced-121">スクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="25ced-121">Scripts can run.</span></span>
- <span data-ttu-id="25ced-122">ローカル コンピューター上に記述するスクリプトを含め、すべてのスクリプトと構成ファイルが信頼された発行元によって署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="25ced-122">Requires that all scripts and configuration files be signed by a trusted publisher, including scripts that you write on the local computer.</span></span>
- <span data-ttu-id="25ced-123">信頼済みまたは信頼できないものとして分類されていない発行元からのスクリプトを実行する前に、プロンプトを表示します。</span><span class="sxs-lookup"><span data-stu-id="25ced-123">Prompts you before running scripts from publishers that you haven't yet classified as trusted or untrusted.</span></span>
- <span data-ttu-id="25ced-124">署名されたが悪意のあるスクリプトを実行するリスク。</span><span class="sxs-lookup"><span data-stu-id="25ced-124">Risks running signed, but malicious, scripts.</span></span>

### <a name="bypass"></a><span data-ttu-id="25ced-125">バイパス</span><span class="sxs-lookup"><span data-stu-id="25ced-125">Bypass</span></span>

- <span data-ttu-id="25ced-126">何もブロックされず、警告やプロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="25ced-126">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="25ced-127">この実行ポリシーは、PowerShell スクリプトが大規模なアプリケーションに組み込まれる構成や、PowerShell が独自のセキュリティモデルを持つプログラムの基礎となる構成用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="25ced-127">This execution policy is designed for configurations in which a PowerShell script is built in to a larger application or for configurations in which PowerShell is the foundation for a program that has its own security model.</span></span>

### <a name="default"></a><span data-ttu-id="25ced-128">Default</span><span class="sxs-lookup"><span data-stu-id="25ced-128">Default</span></span>

- <span data-ttu-id="25ced-129">既定の実行ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="25ced-129">Sets the default execution policy.</span></span>
- <span data-ttu-id="25ced-130">Windows クライアントでは **制限** されています。</span><span class="sxs-lookup"><span data-stu-id="25ced-130">**Restricted** for Windows clients.</span></span>
- <span data-ttu-id="25ced-131">Windows サーバーの場合は **RemoteSigned** 。</span><span class="sxs-lookup"><span data-stu-id="25ced-131">**RemoteSigned** for Windows servers.</span></span>

### <a name="remotesigned"></a><span data-ttu-id="25ced-132">RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="25ced-132">RemoteSigned</span></span>

- <span data-ttu-id="25ced-133">Windows server コンピューターの既定の実行ポリシー。</span><span class="sxs-lookup"><span data-stu-id="25ced-133">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="25ced-134">スクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="25ced-134">Scripts can run.</span></span>
- <span data-ttu-id="25ced-135">では、電子メールやインスタントメッセージングプログラムを含む、インターネットからダウンロードされるスクリプトと構成ファイルに対する信頼された発行元からのデジタル署名が必要です。</span><span class="sxs-lookup"><span data-stu-id="25ced-135">Requires a digital signature from a trusted publisher on scripts and configuration files that are downloaded from the internet which includes email and instant messaging programs.</span></span>
- <span data-ttu-id="25ced-136">では、ローカルコンピューター上に記述され、インターネットからダウンロードされないスクリプトに対してデジタル署名は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="25ced-136">Doesn't require digital signatures on scripts that are written on the local computer and not downloaded from the internet.</span></span>
- <span data-ttu-id="25ced-137">コマンドレットなどを使用して、スクリプトのブロックが解除された場合に、インターネットからダウンロードされ、署名されていないスクリプトを実行し `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="25ced-137">Runs scripts that are downloaded from the internet and not signed, if the scripts are unblocked, such as by using the `Unblock-File` cmdlet.</span></span>
- <span data-ttu-id="25ced-138">インターネット以外のソースからの署名されていないスクリプトや、悪意のあると考えられる署名済みスクリプトを実行するリスク。</span><span class="sxs-lookup"><span data-stu-id="25ced-138">Risks running unsigned scripts from sources other than the internet and signed scripts that could be malicious.</span></span>

### <a name="restricted"></a><span data-ttu-id="25ced-139">制限付き</span><span class="sxs-lookup"><span data-stu-id="25ced-139">Restricted</span></span>

- <span data-ttu-id="25ced-140">Windows クライアントコンピューターの既定の実行ポリシー。</span><span class="sxs-lookup"><span data-stu-id="25ced-140">The default execution policy for Windows client computers.</span></span>
- <span data-ttu-id="25ced-141">個々のコマンドを許可しますが、スクリプトは許可しません。</span><span class="sxs-lookup"><span data-stu-id="25ced-141">Permits individual commands, but does not allow scripts.</span></span>
- <span data-ttu-id="25ced-142">書式設定ファイル、構成ファイル () `.ps1xml` 、モジュールスクリプトファイル ()、PowerShell プロファイル () など、すべてのスクリプトファイルの実行を禁止 `.psm1` `.ps1` します。</span><span class="sxs-lookup"><span data-stu-id="25ced-142">Prevents running of all script files, including formatting and configuration files (`.ps1xml`), module script files (`.psm1`), and PowerShell profiles (`.ps1`).</span></span>

### <a name="undefined"></a><span data-ttu-id="25ced-143">未定義。</span><span class="sxs-lookup"><span data-stu-id="25ced-143">Undefined</span></span>

- <span data-ttu-id="25ced-144">現在のスコープには実行ポリシーが設定されていません。</span><span class="sxs-lookup"><span data-stu-id="25ced-144">There is no execution policy set in the current scope.</span></span>
- <span data-ttu-id="25ced-145">すべてのスコープの実行ポリシーが **定義** されていない場合、有効な実行ポリシーは windows クライアントおよび windows Server 用 **RemoteSigned** に **制限** されます。</span><span class="sxs-lookup"><span data-stu-id="25ced-145">If the execution policy in all scopes is **Undefined** , the effective execution policy is **Restricted** for Windows clients and **RemoteSigned** for Windows Server.</span></span>

### <a name="unrestricted"></a><span data-ttu-id="25ced-146">無制限</span><span class="sxs-lookup"><span data-stu-id="25ced-146">Unrestricted</span></span>

- <span data-ttu-id="25ced-147">署名されていないスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="25ced-147">Unsigned scripts can run.</span></span> <span data-ttu-id="25ced-148">悪意のあるスクリプトを実行するリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="25ced-148">There is a risk of running malicious scripts.</span></span>
- <span data-ttu-id="25ced-149">ローカルイントラネットゾーンからのものではないスクリプトと構成ファイルを実行する前に、ユーザーに警告します。</span><span class="sxs-lookup"><span data-stu-id="25ced-149">Warns the user before running scripts and configuration files that are not from the local intranet zone.</span></span>

> [!NOTE]
> <span data-ttu-id="25ced-150">インターネットパスから汎用名前付け規則 (UNC) パスを区別しないシステムでは、UNC パスによって識別されるスクリプトは、 **RemoteSigned** 実行ポリシーでの実行が許可されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="25ced-150">On systems that do not distinguish Universal Naming Convention (UNC) paths from internet paths, scripts that are identified by a UNC path might not be permitted to run with the **RemoteSigned** execution policy.</span></span>

## <a name="execution-policy-scope"></a><span data-ttu-id="25ced-151">実行ポリシーのスコープ</span><span class="sxs-lookup"><span data-stu-id="25ced-151">Execution policy scope</span></span>

<span data-ttu-id="25ced-152">特定のスコープでのみ有効な実行ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="25ced-152">You can set an execution policy that is effective only in a particular scope.</span></span>

<span data-ttu-id="25ced-153">**スコープ** の有効な値は **、machinepolicy** 、 **userpolicy** 、 **Process** 、 **CurrentUser** 、および **LocalMachine** です。</span><span class="sxs-lookup"><span data-stu-id="25ced-153">The valid values for **Scope** are **MachinePolicy** , **UserPolicy** , **Process** , **CurrentUser** , and **LocalMachine**.</span></span> <span data-ttu-id="25ced-154">**LocalMachine** は、実行ポリシーを設定するときの既定値です。</span><span class="sxs-lookup"><span data-stu-id="25ced-154">**LocalMachine** is the default when setting an execution policy.</span></span>

<span data-ttu-id="25ced-155">**スコープ** 値は、優先順位順に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="25ced-155">The **Scope** values are listed in precedence order.</span></span> <span data-ttu-id="25ced-156">より制限の厳しいポリシーが優先順位の低いレベルで設定されている場合でも、現在のセッションでは、優先されるポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="25ced-156">The policy that takes precedence is effective in the current session, even if a more restrictive policy was set at a lower level of precedence.</span></span>

<span data-ttu-id="25ced-157">詳細については、「 [set-executionpolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25ced-157">For more information, see [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy).</span></span>

### <a name="machinepolicy"></a><span data-ttu-id="25ced-158">MachinePolicy</span><span class="sxs-lookup"><span data-stu-id="25ced-158">MachinePolicy</span></span>

<span data-ttu-id="25ced-159">コンピューターのすべてのユーザーに対してグループポリシーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="25ced-159">Set by a Group Policy for all users of the computer.</span></span>

### <a name="userpolicy"></a><span data-ttu-id="25ced-160">UserPolicy</span><span class="sxs-lookup"><span data-stu-id="25ced-160">UserPolicy</span></span>

<span data-ttu-id="25ced-161">コンピューターの現在のユーザーのグループポリシーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="25ced-161">Set by a Group Policy for the current user of the computer.</span></span>

### <a name="process"></a><span data-ttu-id="25ced-162">プロセス</span><span class="sxs-lookup"><span data-stu-id="25ced-162">Process</span></span>

<span data-ttu-id="25ced-163">**プロセス** のスコープは、現在の PowerShell セッションにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="25ced-163">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="25ced-164">実行ポリシーは、レジストリではなく、環境変数に保存され `$env:PSExecutionPolicyPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="25ced-164">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="25ced-165">PowerShell セッションが終了すると、変数と値が削除されます。</span><span class="sxs-lookup"><span data-stu-id="25ced-165">When the PowerShell session is closed, the variable and value are deleted.</span></span>

### <a name="currentuser"></a><span data-ttu-id="25ced-166">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="25ced-166">CurrentUser</span></span>

<span data-ttu-id="25ced-167">実行ポリシーは、現在のユーザーのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="25ced-167">The execution policy affects only the current user.</span></span> <span data-ttu-id="25ced-168">これは **HKEY_CURRENT_USER** レジストリサブキーに格納されています。</span><span class="sxs-lookup"><span data-stu-id="25ced-168">It's stored in the **HKEY_CURRENT_USER** registry subkey.</span></span>

### <a name="localmachine"></a><span data-ttu-id="25ced-169">LocalMachine</span><span class="sxs-lookup"><span data-stu-id="25ced-169">LocalMachine</span></span>

<span data-ttu-id="25ced-170">実行ポリシーは、現在のコンピューター上のすべてのユーザーに影響します。</span><span class="sxs-lookup"><span data-stu-id="25ced-170">The execution policy affects all users on the current computer.</span></span> <span data-ttu-id="25ced-171">これは **HKEY_LOCAL_MACHINE** レジストリサブキーに格納されています。</span><span class="sxs-lookup"><span data-stu-id="25ced-171">It's stored in the **HKEY_LOCAL_MACHINE** registry subkey.</span></span>

## <a name="managing-the-execution-policy-with-powershell"></a><span data-ttu-id="25ced-172">PowerShell を使用した実行ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="25ced-172">Managing the execution policy with PowerShell</span></span>

<span data-ttu-id="25ced-173">現在の PowerShell セッションに対して有効な実行ポリシーを取得するには、コマンドレットを使用し `Get-ExecutionPolicy` ます。</span><span class="sxs-lookup"><span data-stu-id="25ced-173">To get the effective execution policy for the current PowerShell session, use the `Get-ExecutionPolicy` cmdlet.</span></span>

<span data-ttu-id="25ced-174">次のコマンドは、有効な実行ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="25ced-174">The following command gets the effective execution policy:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="25ced-175">現在のセッションに影響するすべての実行ポリシーを取得し、優先順位で表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="25ced-175">To get all of the execution policies that affect the current session and display them in precedence order:</span></span>

```powershell
Get-ExecutionPolicy -List
```

<span data-ttu-id="25ced-176">結果は次のサンプル出力のようになります。</span><span class="sxs-lookup"><span data-stu-id="25ced-176">The result looks similar to the following sample output:</span></span>

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine       AllSigned
```

<span data-ttu-id="25ced-177">この場合、有効な実行ポリシーは、現在のユーザーの実行ポリシーがローカルコンピューターに設定されている実行ポリシーよりも優先されるため、 **RemoteSigned** になります。</span><span class="sxs-lookup"><span data-stu-id="25ced-177">In this case, the effective execution policy is **RemoteSigned** because the execution policy for the current user takes precedence over the execution policy set for the local computer.</span></span>

<span data-ttu-id="25ced-178">特定のスコープに対して設定された実行ポリシーを取得するには、の **scope** パラメーターを使用し `Get-ExecutionPolicy` ます。</span><span class="sxs-lookup"><span data-stu-id="25ced-178">To get the execution policy set for a particular scope, use the **Scope** parameter of `Get-ExecutionPolicy`.</span></span>

<span data-ttu-id="25ced-179">たとえば、次のコマンドは、 **CurrentUser** スコープの実行ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="25ced-179">For example, the following command gets the execution policy for the **CurrentUser** scope:</span></span>

```powershell
Get-ExecutionPolicy -Scope CurrentUser
```

### <a name="change-the-execution-policy"></a><span data-ttu-id="25ced-180">実行ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="25ced-180">Change the execution policy</span></span>

<span data-ttu-id="25ced-181">Windows コンピューターの PowerShell 実行ポリシーを変更するには、コマンドレットを使用し `Set-ExecutionPolicy` ます。</span><span class="sxs-lookup"><span data-stu-id="25ced-181">To change the PowerShell execution policy on your Windows computer, use the `Set-ExecutionPolicy` cmdlet.</span></span> <span data-ttu-id="25ced-182">変更はすぐに有効になります。</span><span class="sxs-lookup"><span data-stu-id="25ced-182">The change is effective immediately.</span></span> <span data-ttu-id="25ced-183">PowerShell を再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="25ced-183">You don't need to restart PowerShell.</span></span>

<span data-ttu-id="25ced-184">スコープ **LocalMachine** または **CurrentUser** の実行ポリシーを設定した場合、変更はレジストリに保存され、再度変更するまで有効のままになります。</span><span class="sxs-lookup"><span data-stu-id="25ced-184">If you set the execution policy for the scopes **LocalMachine** or the **CurrentUser** , the change is saved in the registry and remains effective until you change it again.</span></span>

<span data-ttu-id="25ced-185">**プロセス** スコープの実行ポリシーを設定しても、レジストリには保存されません。</span><span class="sxs-lookup"><span data-stu-id="25ced-185">If you set the execution policy for the **Process** scope, it's not saved in the registry.</span></span> <span data-ttu-id="25ced-186">実行ポリシーは、現在のプロセスと子プロセスが閉じられるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="25ced-186">The execution policy is retained until the current process and any child processes are closed.</span></span>

> [!NOTE]
> <span data-ttu-id="25ced-187">Windows Vista 以降のバージョンの Windows では、ローカルコンピューターの **LocalMachine** スコープの実行ポリシーを変更するコマンドを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="25ced-187">In Windows Vista and later versions of Windows, to run commands that change the execution policy for the local computer, **LocalMachine** scope, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="25ced-188">実行ポリシーを変更するには:</span><span class="sxs-lookup"><span data-stu-id="25ced-188">To change your execution policy:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName>
```

<span data-ttu-id="25ced-189">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="25ced-189">For example:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="25ced-190">特定のスコープで実行ポリシーを設定するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="25ced-190">To set the execution policy in a particular scope:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName> -Scope <scope>
```

<span data-ttu-id="25ced-191">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="25ced-191">For example:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

<span data-ttu-id="25ced-192">実行ポリシーを変更するコマンドは成功しても、有効な実行ポリシーは変更されません。</span><span class="sxs-lookup"><span data-stu-id="25ced-192">A command to change an execution policy can succeed but still not change the effective execution policy.</span></span>

<span data-ttu-id="25ced-193">たとえば、ローカルコンピューターの実行ポリシーを設定するコマンドは成功しますが、現在のユーザーの実行ポリシーによって上書きされます。</span><span class="sxs-lookup"><span data-stu-id="25ced-193">For example, a command that sets the execution policy for the local computer can succeed but be overridden by the execution policy for the current user.</span></span>

### <a name="remove-the-execution-policy"></a><span data-ttu-id="25ced-194">実行ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="25ced-194">Remove the execution policy</span></span>

<span data-ttu-id="25ced-195">特定のスコープの実行ポリシーを削除するには、実行ポリシーを **Undefined** に設定します。</span><span class="sxs-lookup"><span data-stu-id="25ced-195">To remove the execution policy for a particular scope, set the execution policy to **Undefined**.</span></span>

<span data-ttu-id="25ced-196">たとえば、ローカルコンピューターのすべてのユーザーの実行ポリシーを削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="25ced-196">For example, to remove the execution policy for all the users of the local computer:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope LocalMachine
```

<span data-ttu-id="25ced-197">**スコープ** の実行ポリシーを削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="25ced-197">To remove the execution policy for a **Scope** :</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
```

<span data-ttu-id="25ced-198">どのスコープにも実行ポリシーが設定されていない場合は、有効な実行ポリシーが **制限** されます。これは、Windows クライアントの既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="25ced-198">If no execution policy is set in any scope, the effective execution policy is **Restricted** , which is the default for Windows clients.</span></span>

### <a name="set-a-different-policy-for-one-session"></a><span data-ttu-id="25ced-199">1つのセッションに対して別のポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="25ced-199">Set a different policy for one session</span></span>

<span data-ttu-id="25ced-200">**powershell.exe** の **set-executionpolicy** パラメーターを使用して、新しい PowerShell セッションの実行ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="25ced-200">You can use the **ExecutionPolicy** parameter of **powershell.exe** to set an execution policy for a new PowerShell session.</span></span> <span data-ttu-id="25ced-201">ポリシーは、現在のセッションと子セッションにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="25ced-201">The policy affects only the current session and child sessions.</span></span>

<span data-ttu-id="25ced-202">新しいセッションの実行ポリシーを設定するには、コマンドライン ( **cmd.exe** や powershell など) で powershell を起動し、 **powershell.exe** の **set-executionpolicy** パラメーターを使用して実行ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="25ced-202">To set the execution policy for a new session, start PowerShell at the command line, such as **cmd.exe** or from PowerShell, and then use the **ExecutionPolicy** parameter of **powershell.exe** to set the execution policy.</span></span>

<span data-ttu-id="25ced-203">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="25ced-203">For example:</span></span>

```powershell
powershell.exe -ExecutionPolicy AllSigned
```

<span data-ttu-id="25ced-204">設定した実行ポリシーはレジストリに格納されていません。</span><span class="sxs-lookup"><span data-stu-id="25ced-204">The execution policy that you set isn't stored in the registry.</span></span> <span data-ttu-id="25ced-205">代わりに、環境変数に格納され `$env:PSExecutionPolicyPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="25ced-205">Instead, it's stored in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="25ced-206">変数は、ポリシーが設定されているセッションを閉じると削除されます。</span><span class="sxs-lookup"><span data-stu-id="25ced-206">The variable is deleted when you close the session in which the policy is set.</span></span> <span data-ttu-id="25ced-207">変数の値を編集することによって、ポリシーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="25ced-207">You cannot change the policy by editing the variable value.</span></span>

<span data-ttu-id="25ced-208">セッション中に、セッションに対して設定されている実行ポリシーが、ローカルコンピューターまたは現在のユーザーのレジストリで設定されている実行ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="25ced-208">During the session, the execution policy that is set for the session takes precedence over an execution policy that is set in the registry for the local computer or current user.</span></span> <span data-ttu-id="25ced-209">ただし、グループポリシーを使用して設定された実行ポリシーより優先されることはありません。</span><span class="sxs-lookup"><span data-stu-id="25ced-209">However, it doesn't take precedence over the execution policy set by using a Group Policy.</span></span>

## <a name="use-group-policy-to-manage-execution-policy"></a><span data-ttu-id="25ced-210">グループポリシーを使用して実行ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="25ced-210">Use Group Policy to Manage Execution Policy</span></span>

<span data-ttu-id="25ced-211">**[スクリプトのグループポリシー実行を有効** にする] 設定を使用すると、企業内のコンピューターの実行ポリシーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="25ced-211">You can use the **Turn on Script Execution** Group Policy setting to manage the execution policy of computers in your enterprise.</span></span> <span data-ttu-id="25ced-212">グループポリシー設定は、すべてのスコープの PowerShell で設定されている実行ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="25ced-212">The Group Policy setting overrides the execution policies set in PowerShell in all scopes.</span></span>

<span data-ttu-id="25ced-213">**[スクリプト実行の有効化** ] ポリシー設定は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="25ced-213">The **Turn on Script Execution** policy settings are as follows:</span></span>

- <span data-ttu-id="25ced-214">**[スクリプトの実行を有効** にする] を無効にした場合、スクリプトは実行されません。</span><span class="sxs-lookup"><span data-stu-id="25ced-214">If you disable **Turn on Script Execution** , scripts do not run.</span></span> <span data-ttu-id="25ced-215">これは、 **制限** された実行ポリシーに相当します。</span><span class="sxs-lookup"><span data-stu-id="25ced-215">This is equivalent to the **Restricted** execution policy.</span></span>
- <span data-ttu-id="25ced-216">**[スクリプトの実行** を有効にする] を有効にした場合は、実行ポリシーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="25ced-216">If you enable **Turn on Script Execution** , you can select an execution policy.</span></span> <span data-ttu-id="25ced-217">グループポリシー設定は、次の実行ポリシー設定と同じです。</span><span class="sxs-lookup"><span data-stu-id="25ced-217">The Group Policy settings are equivalent to the following execution policy settings:</span></span>

  | <span data-ttu-id="25ced-218">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="25ced-218">Group Policy</span></span>                                  | <span data-ttu-id="25ced-219">実行ポリシー</span><span class="sxs-lookup"><span data-stu-id="25ced-219">Execution Policy</span></span> |
  | --------------------------------------------- | ---------------- |
  | <span data-ttu-id="25ced-220">すべてのスクリプトを許可する</span><span class="sxs-lookup"><span data-stu-id="25ced-220">Allow all scripts</span></span>                             | <span data-ttu-id="25ced-221">無制限</span><span class="sxs-lookup"><span data-stu-id="25ced-221">Unrestricted</span></span>     |
  | <span data-ttu-id="25ced-222">ローカル スクリプトおよびリモートの署名済みスクリプトを許可する</span><span class="sxs-lookup"><span data-stu-id="25ced-222">Allow local scripts and remote signed scripts</span></span> | <span data-ttu-id="25ced-223">RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="25ced-223">RemoteSigned</span></span>     |
  | <span data-ttu-id="25ced-224">署名済みスクリプトのみ許可する</span><span class="sxs-lookup"><span data-stu-id="25ced-224">Allow only signed scripts</span></span>                     | <span data-ttu-id="25ced-225">AllSigned</span><span class="sxs-lookup"><span data-stu-id="25ced-225">AllSigned</span></span>        |

- <span data-ttu-id="25ced-226">**[スクリプトの実行を有効にする** ] が構成されていない場合、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="25ced-226">If **Turn on Script Execution** is not configured, it has no effect.</span></span> <span data-ttu-id="25ced-227">PowerShell で設定された実行ポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="25ced-227">The execution policy set in PowerShell is effective.</span></span>

<span data-ttu-id="25ced-228">PowerShellExecutionPolicy ファイルと PowerShellExecutionPolicy ファイルは、次のパスのグループポリシーエディターの [コンピューターの構成] ノードと [ユーザーの構成] ノードに **[スクリプト実行を有効に** する] ポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="25ced-228">The PowerShellExecutionPolicy.adm and PowerShellExecutionPolicy.admx files add the **Turn on Script Execution** policy to the Computer Configuration and User Configuration nodes in Group Policy Editor in the following paths.</span></span>

<span data-ttu-id="25ced-229">Windows XP および Windows Server 2003 の場合:</span><span class="sxs-lookup"><span data-stu-id="25ced-229">For Windows XP and Windows Server 2003:</span></span>

<span data-ttu-id="25ced-230">管理用テンプレート \Windows コンポーネント \Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="25ced-230">Administrative Templates\Windows Components\Windows PowerShell</span></span>

<span data-ttu-id="25ced-231">Windows Vista 以降のバージョンの場合:</span><span class="sxs-lookup"><span data-stu-id="25ced-231">For Windows Vista and later versions of Windows:</span></span>

<span data-ttu-id="25ced-232">管理 Templates\Classic 管理用テンプレート </span><span class="sxs-lookup"><span data-stu-id="25ced-232">Administrative Templates\Classic Administrative Templates</span></span>\
<span data-ttu-id="25ced-233">Windows \Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="25ced-233">Windows Components\Windows PowerShell</span></span>

<span data-ttu-id="25ced-234">[コンピュータの構成」ノードで設定されたポリシーは、[ユーザーの構成」ノードで設定されたポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="25ced-234">Policies set in the Computer Configuration node take precedence over policies set in the User Configuration node.</span></span>

<span data-ttu-id="25ced-235">詳細については、「[about_Group_Policy_Settings](about_Group_Policy_Settings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="25ced-235">For more information, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

### <a name="execution-policy-precedence"></a><span data-ttu-id="25ced-236">実行ポリシーの優先順位</span><span class="sxs-lookup"><span data-stu-id="25ced-236">Execution policy precedence</span></span>

<span data-ttu-id="25ced-237">PowerShell は、セッションの有効な実行ポリシーを決定するときに、次の優先順位で実行ポリシーを評価します。</span><span class="sxs-lookup"><span data-stu-id="25ced-237">When determining the effective execution policy for a session, PowerShell evaluates the execution policies in the following precedence order:</span></span>

- <span data-ttu-id="25ced-238">グループポリシー: MachinePolicy</span><span class="sxs-lookup"><span data-stu-id="25ced-238">Group Policy: MachinePolicy</span></span>
- <span data-ttu-id="25ced-239">グループポリシー: UserPolicy</span><span class="sxs-lookup"><span data-stu-id="25ced-239">Group Policy: UserPolicy</span></span>
- <span data-ttu-id="25ced-240">実行ポリシー: Process (または `powershell.exe -ExecutionPolicy` )</span><span class="sxs-lookup"><span data-stu-id="25ced-240">Execution Policy: Process (or `powershell.exe -ExecutionPolicy`)</span></span>
- <span data-ttu-id="25ced-241">実行ポリシー: CurrentUser</span><span class="sxs-lookup"><span data-stu-id="25ced-241">Execution Policy: CurrentUser</span></span>
- <span data-ttu-id="25ced-242">実行ポリシー: LocalMachine</span><span class="sxs-lookup"><span data-stu-id="25ced-242">Execution Policy: LocalMachine</span></span>

## <a name="manage-signed-and-unsigned-scripts"></a><span data-ttu-id="25ced-243">署名されたスクリプトと署名されていないスクリプトの管理</span><span class="sxs-lookup"><span data-stu-id="25ced-243">Manage signed and unsigned scripts</span></span>

<span data-ttu-id="25ced-244">Windows では、Internet Explorer や Microsoft Edge などのプログラムは、ダウンロードされたファイルに代替データストリームを追加します。</span><span class="sxs-lookup"><span data-stu-id="25ced-244">In Windows, programs like Internet Explorer and Microsoft Edge add an alternate data stream to files that are downloaded.</span></span> <span data-ttu-id="25ced-245">これにより、ファイルが "インターネットからの受信" としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="25ced-245">This marks the file as "coming from the Internet".</span></span> <span data-ttu-id="25ced-246">PowerShell の実行ポリシーが **RemoteSigned** の場合、powershell では、電子メールやインスタントメッセージングプログラムを含む、インターネットからダウンロードされた未署名のスクリプトは実行されません。</span><span class="sxs-lookup"><span data-stu-id="25ced-246">If your PowerShell execution policy is **RemoteSigned** , PowerShell won't run unsigned scripts that are downloaded from the internet which includes email and instant messaging programs.</span></span>

<span data-ttu-id="25ced-247">スクリプトに署名するか、実行ポリシーを変更せずに、署名されていないスクリプトを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="25ced-247">You can sign the script or elect to run an unsigned script without changing the execution policy.</span></span>

<span data-ttu-id="25ced-248">PowerShell 3.0 以降では、コマンドレットの **Stream** パラメーターを使用して、 `Get-Item` インターネットからダウンロードされたためにブロックされているファイルを検出することができます。</span><span class="sxs-lookup"><span data-stu-id="25ced-248">Beginning in PowerShell 3.0, you can use the **Stream** parameter of the `Get-Item` cmdlet to detect files that are blocked because they were downloaded from the internet.</span></span> <span data-ttu-id="25ced-249">`Unblock-File`コマンドレットを使用してスクリプトのブロックを解除し、PowerShell で実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="25ced-249">Use the `Unblock-File` cmdlet to unblock the scripts so that you can run them in PowerShell.</span></span>

<span data-ttu-id="25ced-250">詳細については、「 [about_Signing](about_Signing.md)、 [取得項目](xref:Microsoft.PowerShell.Management.Get-Item)、および [ブロック解除-ファイル](xref:Microsoft.PowerShell.Utility.Unblock-File)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25ced-250">For more information, see [about_Signing](about_Signing.md), [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item), and [Unblock-File](xref:Microsoft.PowerShell.Utility.Unblock-File).</span></span>

> [!NOTE]
> <span data-ttu-id="25ced-251">他の方法でファイルをダウンロードすると、ファイルはインターネットゾーンからのものとしてマークされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="25ced-251">Other methods of downloading files may not mark the files as coming from the Internet Zone.</span></span> <span data-ttu-id="25ced-252">次に例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="25ced-252">Some examples include:</span></span>
>
> - `curl.exe`
> - `Invoke-RestMethod`
> - `Invoke-WebRequest`

## <a name="execution-policy-on-windows-server-core-and-window-nano-server"></a><span data-ttu-id="25ced-253">Windows Server Core および Windows Nano Server での実行ポリシー</span><span class="sxs-lookup"><span data-stu-id="25ced-253">Execution policy on Windows Server Core and Window Nano Server</span></span>

<span data-ttu-id="25ced-254">特定の条件下で Windows Server Core または Windows Nano Server で PowerShell 5.1 を実行すると、実行ポリシーが次のエラーで失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="25ced-254">When PowerShell 5.1 is run on Windows Server Core or Windows Nano Server under certain conditions, execution policies can fail with the following error:</span></span>

```Output
AuthorizationManager check failed.
At line:1 char:1
+ C:\scriptpath\scriptname.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

<span data-ttu-id="25ced-255">PowerShell は、Windows デスクトップシェル () の Api を使用し `explorer.exe` て、スクリプトファイルのゾーンを検証します。</span><span class="sxs-lookup"><span data-stu-id="25ced-255">PowerShell uses APIs in the Windows Desktop Shell (`explorer.exe`) to validate the Zone of a script file.</span></span> <span data-ttu-id="25ced-256">Windows Powershell は、windows Server Core および Windows Nano Server では使用できません。</span><span class="sxs-lookup"><span data-stu-id="25ced-256">The Windows Shell is not available on Windows Server Core and Windows Nano Server.</span></span>

<span data-ttu-id="25ced-257">Windows デスクトップシェルが使用できないか、応答しない場合は、Windows システムでこのエラーを受け取ることもできます。</span><span class="sxs-lookup"><span data-stu-id="25ced-257">You could also get this error on any Windows system if the Windows Desktop Shell is unavailable or unresponsive.</span></span> <span data-ttu-id="25ced-258">たとえば、サインオン中に、Windows デスクトップの準備が整う前に PowerShell ログオンスクリプトの実行が開始され、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="25ced-258">For example, during sign on, a PowerShell logon script could start execution before the Windows Desktop is ready, resulting in failure.</span></span>

<span data-ttu-id="25ced-259">**バイパス** または **AllSigned** の実行ポリシーを使用しても、問題を回避するゾーンチェックは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="25ced-259">Using an execution policy of **ByPass** or **AllSigned** does not require a Zone check which avoids the problem.</span></span>

## <a name="see-also"></a><span data-ttu-id="25ced-260">参照</span><span class="sxs-lookup"><span data-stu-id="25ced-260">See Also</span></span>

[<span data-ttu-id="25ced-261">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="25ced-261">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="25ced-262">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="25ced-262">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="25ced-263">about_Signing</span><span class="sxs-lookup"><span data-stu-id="25ced-263">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="25ced-264">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="25ced-264">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="25ced-265">Get-Item</span><span class="sxs-lookup"><span data-stu-id="25ced-265">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

[<span data-ttu-id="25ced-266">PowerShell.exe Command-Line のヘルプ</span><span class="sxs-lookup"><span data-stu-id="25ced-266">PowerShell.exe Command-Line Help</span></span>](about_PowerShell_exe.md)

[<span data-ttu-id="25ced-267">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="25ced-267">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="25ced-268">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="25ced-268">Unblock-File</span></span>](xref:Microsoft.PowerShell.Utility.Unblock-File)
