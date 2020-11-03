---
description: PowerShell の実行ポリシーについて説明し、その管理方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Execution_Policies
ms.openlocfilehash: 7a20a5a3743934a5be884766956d34d52b95da5f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221675"
---
# <a name="about-execution-policies"></a><span data-ttu-id="e7987-104">実行ポリシーについて</span><span class="sxs-lookup"><span data-stu-id="e7987-104">About Execution Policies</span></span>

## <a name="short-description"></a><span data-ttu-id="e7987-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="e7987-105">Short Description</span></span>
<span data-ttu-id="e7987-106">PowerShell の実行ポリシーについて説明し、その管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7987-106">Describes the PowerShell execution policies and explains how to manage them.</span></span>

## <a name="long-description"></a><span data-ttu-id="e7987-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="e7987-107">Long Description</span></span>

<span data-ttu-id="e7987-108">PowerShell の実行ポリシーは、PowerShell が構成ファイルを読み込み、スクリプトを実行するときの条件を制御する安全性機能です。</span><span class="sxs-lookup"><span data-stu-id="e7987-108">PowerShell's execution policy is a safety feature that controls the conditions under which PowerShell loads configuration files and runs scripts.</span></span> <span data-ttu-id="e7987-109">この機能は、悪意のあるスクリプトの実行を防止するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e7987-109">This feature helps prevent the execution of malicious scripts.</span></span>

<span data-ttu-id="e7987-110">Windows コンピューターでは、ローカルコンピューター、現在のユーザー、または特定のセッションの実行ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e7987-110">On a Windows computer you can set an execution policy for the local computer, for the current user, or for a particular session.</span></span> <span data-ttu-id="e7987-111">グループポリシー設定を使用して、コンピューターとユーザーの実行ポリシーを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e7987-111">You can also use a Group Policy setting to set execution policies for computers and users.</span></span>

<span data-ttu-id="e7987-112">ローカルコンピューターと現在のユーザーの実行ポリシーは、レジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e7987-112">Execution policies for the local computer and current user are stored in the registry.</span></span> <span data-ttu-id="e7987-113">PowerShell プロファイルで実行ポリシーを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e7987-113">You don't need to set execution policies in your PowerShell profile.</span></span>
<span data-ttu-id="e7987-114">特定のセッションの実行ポリシーはメモリにのみ格納され、セッションが閉じられると失われます。</span><span class="sxs-lookup"><span data-stu-id="e7987-114">The execution policy for a particular session is stored only in memory and is lost when the session is closed.</span></span>

<span data-ttu-id="e7987-115">実行ポリシーは、ユーザーの操作を制限するセキュリティシステムではありません。</span><span class="sxs-lookup"><span data-stu-id="e7987-115">The execution policy isn't a security system that restricts user actions.</span></span> <span data-ttu-id="e7987-116">たとえば、スクリプトを実行できない場合、ユーザーはコマンドラインでスクリプトの内容を入力することで、ポリシーを簡単にバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="e7987-116">For example, users can easily bypass a policy by typing the script contents at the command line when they cannot run a script.</span></span> <span data-ttu-id="e7987-117">代わりに、実行ポリシーを使用して、ユーザーが基本的な規則を設定し、意図せずに違反しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e7987-117">Instead, the execution policy helps users to set basic rules and prevents them from violating them unintentionally.</span></span>

<span data-ttu-id="e7987-118">Windows 以外のコンピューターでは、既定の実行ポリシーは **無制限** で、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e7987-118">On non-Windows computers, the default execution policy is **Unrestricted** and cannot be changed.</span></span> <span data-ttu-id="e7987-119">`Set-ExecutionPolicy`コマンドレットは使用できますが、PowerShell にはサポートされていないコンソールメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7987-119">The `Set-ExecutionPolicy` cmdlet is available, but PowerShell displays a console message that it's not supported.</span></span> <span data-ttu-id="e7987-120">`Get-ExecutionPolicy`Windows 以外のプラットフォームでは **無制限** が返されますが、これらのプラットフォームには windows セキュリティゾーンが実装されていないため、この動作は実際には **バイパス** に一致します。</span><span class="sxs-lookup"><span data-stu-id="e7987-120">While `Get-ExecutionPolicy` returns **Unrestricted** on non-Windows platforms, the behavior really matches **Bypass** because those platforms do not implement the Windows Security Zones.</span></span>

## <a name="powershell-execution-policies"></a><span data-ttu-id="e7987-121">PowerShell 実行ポリシー</span><span class="sxs-lookup"><span data-stu-id="e7987-121">PowerShell execution policies</span></span>

<span data-ttu-id="e7987-122">これらのポリシーの適用は、Windows プラットフォームでのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="e7987-122">Enforcement of these policies only occurs on Windows platforms.</span></span> <span data-ttu-id="e7987-123">PowerShell の実行ポリシーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e7987-123">The PowerShell execution policies are as follows:</span></span>

### <a name="allsigned"></a><span data-ttu-id="e7987-124">AllSigned</span><span class="sxs-lookup"><span data-stu-id="e7987-124">AllSigned</span></span>

- <span data-ttu-id="e7987-125">スクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e7987-125">Scripts can run.</span></span>
- <span data-ttu-id="e7987-126">ローカル コンピューター上に記述するスクリプトを含め、すべてのスクリプトと構成ファイルが信頼された発行元によって署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7987-126">Requires that all scripts and configuration files be signed by a trusted publisher, including scripts that you write on the local computer.</span></span>
- <span data-ttu-id="e7987-127">信頼済みまたは信頼できないものとして分類されていない発行元からのスクリプトを実行する前に、プロンプトを表示します。</span><span class="sxs-lookup"><span data-stu-id="e7987-127">Prompts you before running scripts from publishers that you haven't yet classified as trusted or untrusted.</span></span>
- <span data-ttu-id="e7987-128">署名されたが悪意のあるスクリプトを実行するリスク。</span><span class="sxs-lookup"><span data-stu-id="e7987-128">Risks running signed, but malicious, scripts.</span></span>

### <a name="bypass"></a><span data-ttu-id="e7987-129">バイパス</span><span class="sxs-lookup"><span data-stu-id="e7987-129">Bypass</span></span>

- <span data-ttu-id="e7987-130">何もブロックされず、警告やプロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="e7987-130">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="e7987-131">この実行ポリシーは、PowerShell スクリプトが大規模なアプリケーションに組み込まれる構成や、PowerShell が独自のセキュリティモデルを持つプログラムの基礎となる構成用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="e7987-131">This execution policy is designed for configurations in which a PowerShell script is built in to a larger application or for configurations in which PowerShell is the foundation for a program that has its own security model.</span></span>

### <a name="default"></a><span data-ttu-id="e7987-132">Default</span><span class="sxs-lookup"><span data-stu-id="e7987-132">Default</span></span>

- <span data-ttu-id="e7987-133">既定の実行ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7987-133">Sets the default execution policy.</span></span>
- <span data-ttu-id="e7987-134">Windows クライアントでは **制限** されています。</span><span class="sxs-lookup"><span data-stu-id="e7987-134">**Restricted** for Windows clients.</span></span>
- <span data-ttu-id="e7987-135">Windows サーバーの場合は **RemoteSigned** 。</span><span class="sxs-lookup"><span data-stu-id="e7987-135">**RemoteSigned** for Windows servers.</span></span>

### <a name="remotesigned"></a><span data-ttu-id="e7987-136">RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="e7987-136">RemoteSigned</span></span>

- <span data-ttu-id="e7987-137">Windows server コンピューターの既定の実行ポリシー。</span><span class="sxs-lookup"><span data-stu-id="e7987-137">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="e7987-138">スクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e7987-138">Scripts can run.</span></span>
- <span data-ttu-id="e7987-139">では、電子メールやインスタントメッセージングプログラムを含む、インターネットからダウンロードされるスクリプトと構成ファイルに対する信頼された発行元からのデジタル署名が必要です。</span><span class="sxs-lookup"><span data-stu-id="e7987-139">Requires a digital signature from a trusted publisher on scripts and configuration files that are downloaded from the internet which includes email and instant messaging programs.</span></span>
- <span data-ttu-id="e7987-140">では、ローカルコンピューター上に記述され、インターネットからダウンロードされないスクリプトに対してデジタル署名は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e7987-140">Doesn't require digital signatures on scripts that are written on the local computer and not downloaded from the internet.</span></span>
- <span data-ttu-id="e7987-141">コマンドレットなどを使用して、スクリプトのブロックが解除された場合に、インターネットからダウンロードされ、署名されていないスクリプトを実行し `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="e7987-141">Runs scripts that are downloaded from the internet and not signed, if the scripts are unblocked, such as by using the `Unblock-File` cmdlet.</span></span>
- <span data-ttu-id="e7987-142">インターネット以外のソースからの署名されていないスクリプトや、悪意のあると考えられる署名済みスクリプトを実行するリスク。</span><span class="sxs-lookup"><span data-stu-id="e7987-142">Risks running unsigned scripts from sources other than the internet and signed scripts that could be malicious.</span></span>

### <a name="restricted"></a><span data-ttu-id="e7987-143">制限付き</span><span class="sxs-lookup"><span data-stu-id="e7987-143">Restricted</span></span>

- <span data-ttu-id="e7987-144">Windows クライアントコンピューターの既定の実行ポリシー。</span><span class="sxs-lookup"><span data-stu-id="e7987-144">The default execution policy for Windows client computers.</span></span>
- <span data-ttu-id="e7987-145">個々のコマンドを許可しますが、スクリプトは許可しません。</span><span class="sxs-lookup"><span data-stu-id="e7987-145">Permits individual commands, but does not allow scripts.</span></span>
- <span data-ttu-id="e7987-146">書式設定ファイル、構成ファイル () `.ps1xml` 、モジュールスクリプトファイル ()、PowerShell プロファイル () など、すべてのスクリプトファイルの実行を禁止 `.psm1` `.ps1` します。</span><span class="sxs-lookup"><span data-stu-id="e7987-146">Prevents running of all script files, including formatting and configuration files (`.ps1xml`), module script files (`.psm1`), and PowerShell profiles (`.ps1`).</span></span>

### <a name="undefined"></a><span data-ttu-id="e7987-147">未定義。</span><span class="sxs-lookup"><span data-stu-id="e7987-147">Undefined</span></span>

- <span data-ttu-id="e7987-148">現在のスコープには実行ポリシーが設定されていません。</span><span class="sxs-lookup"><span data-stu-id="e7987-148">There is no execution policy set in the current scope.</span></span>
- <span data-ttu-id="e7987-149">すべてのスコープの実行ポリシーが **定義** されていない場合、有効な実行ポリシーは windows クライアントおよび windows Server 用 **RemoteSigned** に **制限** されます。</span><span class="sxs-lookup"><span data-stu-id="e7987-149">If the execution policy in all scopes is **Undefined** , the effective execution policy is **Restricted** for Windows clients and **RemoteSigned** for Windows Server.</span></span>

### <a name="unrestricted"></a><span data-ttu-id="e7987-150">無制限</span><span class="sxs-lookup"><span data-stu-id="e7987-150">Unrestricted</span></span>

- <span data-ttu-id="e7987-151">Windows 以外のコンピューターの既定の実行ポリシーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e7987-151">The default execution policy for non-Windows computers and cannot be changed.</span></span>
- <span data-ttu-id="e7987-152">署名されていないスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e7987-152">Unsigned scripts can run.</span></span> <span data-ttu-id="e7987-153">悪意のあるスクリプトを実行するリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="e7987-153">There is a risk of running malicious scripts.</span></span>
- <span data-ttu-id="e7987-154">ローカルイントラネットゾーンからのものではないスクリプトと構成ファイルを実行する前に、ユーザーに警告します。</span><span class="sxs-lookup"><span data-stu-id="e7987-154">Warns the user before running scripts and configuration files that are not from the local intranet zone.</span></span>

> [!NOTE]
> <span data-ttu-id="e7987-155">インターネットパスから汎用名前付け規則 (UNC) パスを区別しないシステムでは、UNC パスによって識別されるスクリプトは、 **RemoteSigned** 実行ポリシーでの実行が許可されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e7987-155">On systems that do not distinguish Universal Naming Convention (UNC) paths from internet paths, scripts that are identified by a UNC path might not be permitted to run with the **RemoteSigned** execution policy.</span></span>

## <a name="execution-policy-scope"></a><span data-ttu-id="e7987-156">実行ポリシーのスコープ</span><span class="sxs-lookup"><span data-stu-id="e7987-156">Execution policy scope</span></span>

<span data-ttu-id="e7987-157">特定のスコープでのみ有効な実行ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e7987-157">You can set an execution policy that is effective only in a particular scope.</span></span>

<span data-ttu-id="e7987-158">**スコープ** の有効な値は **、machinepolicy** 、 **userpolicy** 、 **Process** 、 **CurrentUser** 、および **LocalMachine** です。</span><span class="sxs-lookup"><span data-stu-id="e7987-158">The valid values for **Scope** are **MachinePolicy** , **UserPolicy** , **Process** , **CurrentUser** , and **LocalMachine**.</span></span> <span data-ttu-id="e7987-159">**LocalMachine** は、実行ポリシーを設定するときの既定値です。</span><span class="sxs-lookup"><span data-stu-id="e7987-159">**LocalMachine** is the default when setting an execution policy.</span></span>

<span data-ttu-id="e7987-160">**スコープ** 値は、優先順位順に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7987-160">The **Scope** values are listed in precedence order.</span></span> <span data-ttu-id="e7987-161">より制限の厳しいポリシーが優先順位の低いレベルで設定されている場合でも、現在のセッションでは、優先されるポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="e7987-161">The policy that takes precedence is effective in the current session, even if a more restrictive policy was set at a lower level of precedence.</span></span>

<span data-ttu-id="e7987-162">詳細については、「 [set-executionpolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7987-162">For more information, see [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy).</span></span>

### <a name="machinepolicy"></a><span data-ttu-id="e7987-163">MachinePolicy</span><span class="sxs-lookup"><span data-stu-id="e7987-163">MachinePolicy</span></span>

<span data-ttu-id="e7987-164">コンピューターのすべてのユーザーに対してグループポリシーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="e7987-164">Set by a Group Policy for all users of the computer.</span></span>

### <a name="userpolicy"></a><span data-ttu-id="e7987-165">UserPolicy</span><span class="sxs-lookup"><span data-stu-id="e7987-165">UserPolicy</span></span>

<span data-ttu-id="e7987-166">コンピューターの現在のユーザーのグループポリシーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="e7987-166">Set by a Group Policy for the current user of the computer.</span></span>

### <a name="process"></a><span data-ttu-id="e7987-167">プロセス</span><span class="sxs-lookup"><span data-stu-id="e7987-167">Process</span></span>

<span data-ttu-id="e7987-168">**プロセス** のスコープは、現在の PowerShell セッションにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="e7987-168">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="e7987-169">実行ポリシーは、レジストリではなく、環境変数に保存され `$env:PSExecutionPolicyPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="e7987-169">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="e7987-170">PowerShell セッションが終了すると、変数と値が削除されます。</span><span class="sxs-lookup"><span data-stu-id="e7987-170">When the PowerShell session is closed, the variable and value are deleted.</span></span>

### <a name="currentuser"></a><span data-ttu-id="e7987-171">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="e7987-171">CurrentUser</span></span>

<span data-ttu-id="e7987-172">実行ポリシーは、現在のユーザーのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="e7987-172">The execution policy affects only the current user.</span></span> <span data-ttu-id="e7987-173">これは **HKEY_CURRENT_USER** レジストリサブキーに格納されています。</span><span class="sxs-lookup"><span data-stu-id="e7987-173">It's stored in the **HKEY_CURRENT_USER** registry subkey.</span></span>

### <a name="localmachine"></a><span data-ttu-id="e7987-174">LocalMachine</span><span class="sxs-lookup"><span data-stu-id="e7987-174">LocalMachine</span></span>

<span data-ttu-id="e7987-175">実行ポリシーは、現在のコンピューター上のすべてのユーザーに影響します。</span><span class="sxs-lookup"><span data-stu-id="e7987-175">The execution policy affects all users on the current computer.</span></span> <span data-ttu-id="e7987-176">これは **HKEY_LOCAL_MACHINE** レジストリサブキーに格納されています。</span><span class="sxs-lookup"><span data-stu-id="e7987-176">It's stored in the **HKEY_LOCAL_MACHINE** registry subkey.</span></span>

## <a name="managing-the-execution-policy-with-powershell"></a><span data-ttu-id="e7987-177">PowerShell を使用した実行ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="e7987-177">Managing the execution policy with PowerShell</span></span>

<span data-ttu-id="e7987-178">現在の PowerShell セッションに対して有効な実行ポリシーを取得するには、コマンドレットを使用し `Get-ExecutionPolicy` ます。</span><span class="sxs-lookup"><span data-stu-id="e7987-178">To get the effective execution policy for the current PowerShell session, use the `Get-ExecutionPolicy` cmdlet.</span></span>

<span data-ttu-id="e7987-179">次のコマンドは、有効な実行ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="e7987-179">The following command gets the effective execution policy:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="e7987-180">現在のセッションに影響するすべての実行ポリシーを取得し、優先順位で表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="e7987-180">To get all of the execution policies that affect the current session and display them in precedence order:</span></span>

```powershell
Get-ExecutionPolicy -List
```

<span data-ttu-id="e7987-181">結果は次のサンプル出力のようになります。</span><span class="sxs-lookup"><span data-stu-id="e7987-181">The result looks similar to the following sample output:</span></span>

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine       AllSigned
```

<span data-ttu-id="e7987-182">この場合、有効な実行ポリシーは、現在のユーザーの実行ポリシーがローカルコンピューターに設定されている実行ポリシーよりも優先されるため、 **RemoteSigned** になります。</span><span class="sxs-lookup"><span data-stu-id="e7987-182">In this case, the effective execution policy is **RemoteSigned** because the execution policy for the current user takes precedence over the execution policy set for the local computer.</span></span>

<span data-ttu-id="e7987-183">特定のスコープに対して設定された実行ポリシーを取得するには、の **scope** パラメーターを使用し `Get-ExecutionPolicy` ます。</span><span class="sxs-lookup"><span data-stu-id="e7987-183">To get the execution policy set for a particular scope, use the **Scope** parameter of `Get-ExecutionPolicy`.</span></span>

<span data-ttu-id="e7987-184">たとえば、次のコマンドは、 **CurrentUser** スコープの実行ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="e7987-184">For example, the following command gets the execution policy for the **CurrentUser** scope:</span></span>

```powershell
Get-ExecutionPolicy -Scope CurrentUser
```

### <a name="change-the-execution-policy"></a><span data-ttu-id="e7987-185">実行ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="e7987-185">Change the execution policy</span></span>

<span data-ttu-id="e7987-186">Windows コンピューターの PowerShell 実行ポリシーを変更するには、コマンドレットを使用し `Set-ExecutionPolicy` ます。</span><span class="sxs-lookup"><span data-stu-id="e7987-186">To change the PowerShell execution policy on your Windows computer, use the `Set-ExecutionPolicy` cmdlet.</span></span> <span data-ttu-id="e7987-187">変更はすぐに有効になります。</span><span class="sxs-lookup"><span data-stu-id="e7987-187">The change is effective immediately.</span></span> <span data-ttu-id="e7987-188">PowerShell を再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e7987-188">You don't need to restart PowerShell.</span></span>

<span data-ttu-id="e7987-189">スコープ **LocalMachine** または **CurrentUser** の実行ポリシーを設定した場合、変更はレジストリに保存され、再度変更するまで有効のままになります。</span><span class="sxs-lookup"><span data-stu-id="e7987-189">If you set the execution policy for the scopes **LocalMachine** or the **CurrentUser** , the change is saved in the registry and remains effective until you change it again.</span></span>

<span data-ttu-id="e7987-190">**プロセス** スコープの実行ポリシーを設定しても、レジストリには保存されません。</span><span class="sxs-lookup"><span data-stu-id="e7987-190">If you set the execution policy for the **Process** scope, it's not saved in the registry.</span></span> <span data-ttu-id="e7987-191">実行ポリシーは、現在のプロセスと子プロセスが閉じられるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="e7987-191">The execution policy is retained until the current process and any child processes are closed.</span></span>

> [!NOTE]
> <span data-ttu-id="e7987-192">Windows Vista 以降のバージョンの Windows では、ローカルコンピューターの **LocalMachine** スコープの実行ポリシーを変更するコマンドを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="e7987-192">In Windows Vista and later versions of Windows, to run commands that change the execution policy for the local computer, **LocalMachine** scope, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="e7987-193">実行ポリシーを変更するには:</span><span class="sxs-lookup"><span data-stu-id="e7987-193">To change your execution policy:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName>
```

<span data-ttu-id="e7987-194">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e7987-194">For example:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="e7987-195">特定のスコープで実行ポリシーを設定するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="e7987-195">To set the execution policy in a particular scope:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName> -Scope <scope>
```

<span data-ttu-id="e7987-196">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e7987-196">For example:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

<span data-ttu-id="e7987-197">実行ポリシーを変更するコマンドは成功しても、有効な実行ポリシーは変更されません。</span><span class="sxs-lookup"><span data-stu-id="e7987-197">A command to change an execution policy can succeed but still not change the effective execution policy.</span></span>

<span data-ttu-id="e7987-198">たとえば、ローカルコンピューターの実行ポリシーを設定するコマンドは成功しますが、現在のユーザーの実行ポリシーによって上書きされます。</span><span class="sxs-lookup"><span data-stu-id="e7987-198">For example, a command that sets the execution policy for the local computer can succeed but be overridden by the execution policy for the current user.</span></span>

### <a name="remove-the-execution-policy"></a><span data-ttu-id="e7987-199">実行ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e7987-199">Remove the execution policy</span></span>

<span data-ttu-id="e7987-200">特定のスコープの実行ポリシーを削除するには、実行ポリシーを **Undefined** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e7987-200">To remove the execution policy for a particular scope, set the execution policy to **Undefined**.</span></span>

<span data-ttu-id="e7987-201">たとえば、ローカルコンピューターのすべてのユーザーの実行ポリシーを削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="e7987-201">For example, to remove the execution policy for all the users of the local computer:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope LocalMachine
```

<span data-ttu-id="e7987-202">**スコープ** の実行ポリシーを削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="e7987-202">To remove the execution policy for a **Scope** :</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
```

<span data-ttu-id="e7987-203">どのスコープにも実行ポリシーが設定されていない場合は、有効な実行ポリシーが **制限** されます。これは、Windows クライアントの既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="e7987-203">If no execution policy is set in any scope, the effective execution policy is **Restricted** , which is the default for Windows clients.</span></span>

### <a name="set-a-different-policy-for-one-session"></a><span data-ttu-id="e7987-204">1つのセッションに対して別のポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="e7987-204">Set a different policy for one session</span></span>

<span data-ttu-id="e7987-205">**pwsh.exe** の **set-executionpolicy** パラメーターを使用して、新しい PowerShell セッションの実行ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e7987-205">You can use the **ExecutionPolicy** parameter of **pwsh.exe** to set an execution policy for a new PowerShell session.</span></span> <span data-ttu-id="e7987-206">ポリシーは、現在のセッションと子セッションにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="e7987-206">The policy affects only the current session and child sessions.</span></span>

<span data-ttu-id="e7987-207">新しいセッションの実行ポリシーを設定するには、コマンドライン ( **cmd.exe** や powershell など) で powershell を起動し、 **pwsh.exe** の **set-executionpolicy** パラメーターを使用して実行ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7987-207">To set the execution policy for a new session, start PowerShell at the command line, such as **cmd.exe** or from PowerShell, and then use the **ExecutionPolicy** parameter of **pwsh.exe** to set the execution policy.</span></span>

<span data-ttu-id="e7987-208">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e7987-208">For example:</span></span>

```powershell
pwsh.exe -ExecutionPolicy AllSigned
```

<span data-ttu-id="e7987-209">設定した実行ポリシーはレジストリに格納されていません。</span><span class="sxs-lookup"><span data-stu-id="e7987-209">The execution policy that you set isn't stored in the registry.</span></span> <span data-ttu-id="e7987-210">代わりに、環境変数に格納され `$env:PSExecutionPolicyPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="e7987-210">Instead, it's stored in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="e7987-211">変数は、ポリシーが設定されているセッションを閉じると削除されます。</span><span class="sxs-lookup"><span data-stu-id="e7987-211">The variable is deleted when you close the session in which the policy is set.</span></span> <span data-ttu-id="e7987-212">変数の値を編集することによって、ポリシーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e7987-212">You cannot change the policy by editing the variable value.</span></span>

<span data-ttu-id="e7987-213">セッション中に、セッションに対して設定されている実行ポリシーが、ローカルコンピューターまたは現在のユーザーのレジストリで設定されている実行ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="e7987-213">During the session, the execution policy that is set for the session takes precedence over an execution policy that is set in the registry for the local computer or current user.</span></span> <span data-ttu-id="e7987-214">ただし、グループポリシーを使用して設定された実行ポリシーより優先されることはありません。</span><span class="sxs-lookup"><span data-stu-id="e7987-214">However, it doesn't take precedence over the execution policy set by using a Group Policy.</span></span>

## <a name="use-group-policy-to-manage-execution-policy"></a><span data-ttu-id="e7987-215">グループポリシーを使用して実行ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="e7987-215">Use Group Policy to Manage Execution Policy</span></span>

<span data-ttu-id="e7987-216">**[スクリプトのグループポリシー実行を有効** にする] 設定を使用すると、企業内のコンピューターの実行ポリシーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e7987-216">You can use the **Turn on Script Execution** Group Policy setting to manage the execution policy of computers in your enterprise.</span></span> <span data-ttu-id="e7987-217">グループポリシー設定は、すべてのスコープの PowerShell で設定されている実行ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="e7987-217">The Group Policy setting overrides the execution policies set in PowerShell in all scopes.</span></span>

<span data-ttu-id="e7987-218">**[スクリプト実行の有効化** ] ポリシー設定は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e7987-218">The **Turn on Script Execution** policy settings are as follows:</span></span>

- <span data-ttu-id="e7987-219">**[スクリプトの実行を有効** にする] を無効にした場合、スクリプトは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e7987-219">If you disable **Turn on Script Execution** , scripts do not run.</span></span> <span data-ttu-id="e7987-220">これは、 **制限** された実行ポリシーに相当します。</span><span class="sxs-lookup"><span data-stu-id="e7987-220">This is equivalent to the **Restricted** execution policy.</span></span>
- <span data-ttu-id="e7987-221">**[スクリプトの実行** を有効にする] を有効にした場合は、実行ポリシーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e7987-221">If you enable **Turn on Script Execution** , you can select an execution policy.</span></span> <span data-ttu-id="e7987-222">グループポリシー設定は、次の実行ポリシー設定と同じです。</span><span class="sxs-lookup"><span data-stu-id="e7987-222">The Group Policy settings are equivalent to the following execution policy settings:</span></span>

  | <span data-ttu-id="e7987-223">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="e7987-223">Group Policy</span></span>                                  | <span data-ttu-id="e7987-224">実行ポリシー</span><span class="sxs-lookup"><span data-stu-id="e7987-224">Execution Policy</span></span> |
  | --------------------------------------------- | ---------------- |
  | <span data-ttu-id="e7987-225">すべてのスクリプトを許可する</span><span class="sxs-lookup"><span data-stu-id="e7987-225">Allow all scripts</span></span>                             | <span data-ttu-id="e7987-226">無制限</span><span class="sxs-lookup"><span data-stu-id="e7987-226">Unrestricted</span></span>     |
  | <span data-ttu-id="e7987-227">ローカル スクリプトおよびリモートの署名済みスクリプトを許可する</span><span class="sxs-lookup"><span data-stu-id="e7987-227">Allow local scripts and remote signed scripts</span></span> | <span data-ttu-id="e7987-228">RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="e7987-228">RemoteSigned</span></span>     |
  | <span data-ttu-id="e7987-229">署名済みスクリプトのみ許可する</span><span class="sxs-lookup"><span data-stu-id="e7987-229">Allow only signed scripts</span></span>                     | <span data-ttu-id="e7987-230">AllSigned</span><span class="sxs-lookup"><span data-stu-id="e7987-230">AllSigned</span></span>        |

- <span data-ttu-id="e7987-231">**[スクリプトの実行を有効にする** ] が構成されていない場合、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="e7987-231">If **Turn on Script Execution** is not configured, it has no effect.</span></span> <span data-ttu-id="e7987-232">PowerShell で設定された実行ポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="e7987-232">The execution policy set in PowerShell is effective.</span></span>

<span data-ttu-id="e7987-233">PowerShellExecutionPolicy ファイルと PowerShellExecutionPolicy ファイルは、次のパスのグループポリシーエディターの [コンピューターの構成] ノードと [ユーザーの構成] ノードに **[スクリプト実行を有効に** する] ポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="e7987-233">The PowerShellExecutionPolicy.adm and PowerShellExecutionPolicy.admx files add the **Turn on Script Execution** policy to the Computer Configuration and User Configuration nodes in Group Policy Editor in the following paths.</span></span>

<span data-ttu-id="e7987-234">Windows XP および Windows Server 2003 の場合:</span><span class="sxs-lookup"><span data-stu-id="e7987-234">For Windows XP and Windows Server 2003:</span></span>

<span data-ttu-id="e7987-235">管理用テンプレート \Windows コンポーネント \Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7987-235">Administrative Templates\Windows Components\Windows PowerShell</span></span>

<span data-ttu-id="e7987-236">Windows Vista 以降のバージョンの場合:</span><span class="sxs-lookup"><span data-stu-id="e7987-236">For Windows Vista and later versions of Windows:</span></span>

<span data-ttu-id="e7987-237">管理 Templates\Classic 管理用テンプレート </span><span class="sxs-lookup"><span data-stu-id="e7987-237">Administrative Templates\Classic Administrative Templates</span></span>\
<span data-ttu-id="e7987-238">Windows \Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7987-238">Windows Components\Windows PowerShell</span></span>

<span data-ttu-id="e7987-239">[コンピュータの構成」ノードで設定されたポリシーは、[ユーザーの構成」ノードで設定されたポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="e7987-239">Policies set in the Computer Configuration node take precedence over policies set in the User Configuration node.</span></span>

<span data-ttu-id="e7987-240">詳細については、「[about_Group_Policy_Settings](about_Group_Policy_Settings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e7987-240">For more information, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

### <a name="execution-policy-precedence"></a><span data-ttu-id="e7987-241">実行ポリシーの優先順位</span><span class="sxs-lookup"><span data-stu-id="e7987-241">Execution policy precedence</span></span>

<span data-ttu-id="e7987-242">PowerShell は、セッションの有効な実行ポリシーを決定するときに、次の優先順位で実行ポリシーを評価します。</span><span class="sxs-lookup"><span data-stu-id="e7987-242">When determining the effective execution policy for a session, PowerShell evaluates the execution policies in the following precedence order:</span></span>

- <span data-ttu-id="e7987-243">グループポリシー: MachinePolicy</span><span class="sxs-lookup"><span data-stu-id="e7987-243">Group Policy: MachinePolicy</span></span>
- <span data-ttu-id="e7987-244">グループポリシー: UserPolicy</span><span class="sxs-lookup"><span data-stu-id="e7987-244">Group Policy: UserPolicy</span></span>
- <span data-ttu-id="e7987-245">実行ポリシー: Process (または `pwsh.exe -ExecutionPolicy` )</span><span class="sxs-lookup"><span data-stu-id="e7987-245">Execution Policy: Process (or `pwsh.exe -ExecutionPolicy`)</span></span>
- <span data-ttu-id="e7987-246">実行ポリシー: CurrentUser</span><span class="sxs-lookup"><span data-stu-id="e7987-246">Execution Policy: CurrentUser</span></span>
- <span data-ttu-id="e7987-247">実行ポリシー: LocalMachine</span><span class="sxs-lookup"><span data-stu-id="e7987-247">Execution Policy: LocalMachine</span></span>

## <a name="manage-signed-and-unsigned-scripts"></a><span data-ttu-id="e7987-248">署名されたスクリプトと署名されていないスクリプトの管理</span><span class="sxs-lookup"><span data-stu-id="e7987-248">Manage signed and unsigned scripts</span></span>

<span data-ttu-id="e7987-249">Windows では、Internet Explorer や Microsoft Edge などのプログラムは、ダウンロードされたファイルに代替データストリームを追加します。</span><span class="sxs-lookup"><span data-stu-id="e7987-249">In Windows, programs like Internet Explorer and Microsoft Edge add an alternate data stream to files that are downloaded.</span></span> <span data-ttu-id="e7987-250">これにより、ファイルが "インターネットからの受信" としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="e7987-250">This marks the file as "coming from the Internet".</span></span> <span data-ttu-id="e7987-251">PowerShell の実行ポリシーが **RemoteSigned** の場合、powershell では、電子メールやインスタントメッセージングプログラムを含む、インターネットからダウンロードされた未署名のスクリプトは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e7987-251">If your PowerShell execution policy is **RemoteSigned** , PowerShell won't run unsigned scripts that are downloaded from the internet which includes email and instant messaging programs.</span></span>

<span data-ttu-id="e7987-252">スクリプトに署名するか、実行ポリシーを変更せずに、署名されていないスクリプトを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="e7987-252">You can sign the script or elect to run an unsigned script without changing the execution policy.</span></span>

<span data-ttu-id="e7987-253">PowerShell 3.0 以降では、コマンドレットの **Stream** パラメーターを使用して、 `Get-Item` インターネットからダウンロードされたためにブロックされているファイルを検出することができます。</span><span class="sxs-lookup"><span data-stu-id="e7987-253">Beginning in PowerShell 3.0, you can use the **Stream** parameter of the `Get-Item` cmdlet to detect files that are blocked because they were downloaded from the internet.</span></span> <span data-ttu-id="e7987-254">`Unblock-File`コマンドレットを使用してスクリプトのブロックを解除し、PowerShell で実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e7987-254">Use the `Unblock-File` cmdlet to unblock the scripts so that you can run them in PowerShell.</span></span>

<span data-ttu-id="e7987-255">詳細については、「 [about_Signing](about_Signing.md)、 [取得項目](xref:Microsoft.PowerShell.Management.Get-Item)、および [ブロック解除-ファイル](xref:Microsoft.PowerShell.Utility.Unblock-File)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7987-255">For more information, see [about_Signing](about_Signing.md), [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item), and [Unblock-File](xref:Microsoft.PowerShell.Utility.Unblock-File).</span></span>

> [!NOTE]
> <span data-ttu-id="e7987-256">他の方法でファイルをダウンロードすると、ファイルはインターネットゾーンからのものとしてマークされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e7987-256">Other methods of downloading files may not mark the files as coming from the Internet Zone.</span></span> <span data-ttu-id="e7987-257">次に例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="e7987-257">Some examples include:</span></span>
>
> - `curl.exe`
> - `Invoke-RestMethod`
> - `Invoke-WebRequest`

## <a name="execution-policy-on-windows-server-core-and-window-nano-server"></a><span data-ttu-id="e7987-258">Windows Server Core および Windows Nano Server での実行ポリシー</span><span class="sxs-lookup"><span data-stu-id="e7987-258">Execution policy on Windows Server Core and Window Nano Server</span></span>

<span data-ttu-id="e7987-259">特定の条件下で Windows Server Core または Windows Nano Server で PowerShell 6 を実行すると、実行ポリシーが次のエラーで失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="e7987-259">When PowerShell 6 is run on Windows Server Core or Windows Nano Server under certain conditions, execution policies can fail with the following error:</span></span>

```Output
AuthorizationManager check failed.
At line:1 char:1
+ C:\scriptpath\scriptname.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

<span data-ttu-id="e7987-260">PowerShell は、Windows デスクトップシェル () の Api を使用し `explorer.exe` て、スクリプトファイルのゾーンを検証します。</span><span class="sxs-lookup"><span data-stu-id="e7987-260">PowerShell uses APIs in the Windows Desktop Shell (`explorer.exe`) to validate the Zone of a script file.</span></span> <span data-ttu-id="e7987-261">Windows Powershell は、windows Server Core および Windows Nano Server では使用できません。</span><span class="sxs-lookup"><span data-stu-id="e7987-261">The Windows Shell is not available on Windows Server Core and Windows Nano Server.</span></span>

<span data-ttu-id="e7987-262">Windows デスクトップシェルが使用できないか、応答しない場合は、Windows システムでこのエラーを受け取ることもできます。</span><span class="sxs-lookup"><span data-stu-id="e7987-262">You could also get this error on any Windows system if the Windows Desktop Shell is unavailable or unresponsive.</span></span> <span data-ttu-id="e7987-263">たとえば、サインオン中に、Windows デスクトップの準備が整う前に PowerShell ログオンスクリプトの実行が開始され、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e7987-263">For example, during sign on, a PowerShell logon script could start execution before the Windows Desktop is ready, resulting in failure.</span></span>

<span data-ttu-id="e7987-264">**バイパス** または **AllSigned** の実行ポリシーを使用しても、問題を回避するゾーンチェックは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e7987-264">Using an execution policy of **ByPass** or **AllSigned** does not require a Zone check which avoids the problem.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7987-265">参照</span><span class="sxs-lookup"><span data-stu-id="e7987-265">See Also</span></span>

[<span data-ttu-id="e7987-266">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="e7987-266">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="e7987-267">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="e7987-267">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="e7987-268">about_Signing</span><span class="sxs-lookup"><span data-stu-id="e7987-268">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="e7987-269">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="e7987-269">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="e7987-270">Get-Item</span><span class="sxs-lookup"><span data-stu-id="e7987-270">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

[<span data-ttu-id="e7987-271">Pwsh コンソールのヘルプ</span><span class="sxs-lookup"><span data-stu-id="e7987-271">Pwsh Console Help</span></span>](about_pwsh.md)

[<span data-ttu-id="e7987-272">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="e7987-272">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="e7987-273">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="e7987-273">Unblock-File</span></span>](xref:Microsoft.PowerShell.Utility.Unblock-File)
