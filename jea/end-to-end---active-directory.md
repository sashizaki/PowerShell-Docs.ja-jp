---
description: 
manager: dongill
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット, JEA"
ms.date: 2016-06-22
title: "エンド ツー エンド - Active Directory"
ms.technology: powershell
ms.openlocfilehash: 3108f5dad96ef54feb3cf559fae38812ed46849c
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
ms.translationtype: HT
ms.contentlocale: ja-JP
---
# <a name="end-to-end---active-directory"></a><span data-ttu-id="3572e-103">エンド ツー エンド - Active Directory</span><span class="sxs-lookup"><span data-stu-id="3572e-103">End to End - Active Directory</span></span>
<span data-ttu-id="3572e-104">プログラムの適用範囲が拡大されたと思ってください。</span><span class="sxs-lookup"><span data-stu-id="3572e-104">Imagine the scope of your program has increased.</span></span>
<span data-ttu-id="3572e-105">Active Directory の操作を実行するために、ドメイン コントローラーに JEA を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3572e-105">You are now responsible for adding JEA to Domain Controllers to perform Active Directory actions.</span></span>
<span data-ttu-id="3572e-106">ヘルプ デスクのスタッフは、JEA を使用して、アカウントのロック解除、パスワードのリセット、その他の類似する操作を実行することになります。</span><span class="sxs-lookup"><span data-stu-id="3572e-106">The help desk people are going to use JEA to unlock accounts, reset passwords, and do other similar actions.</span></span>

<span data-ttu-id="3572e-107">まったく新しいコマンド セットを、異なるユーザー グループに公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3572e-107">You need to expose a completely new set of commands to a different group of people.</span></span>
<span data-ttu-id="3572e-108">それに加えて、公開する必要がある既存の Active Directory スクリプトが多数あります。</span><span class="sxs-lookup"><span data-stu-id="3572e-108">On top of that, you have a bunch of existing Active Directory scripts you need to expose.</span></span>
<span data-ttu-id="3572e-109">このセクションでは、このタスクを実行するためのセッション構成とロール機能の作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="3572e-109">This section will walk through authoring a Session Configuration and Role Capability for this task.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3572e-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="3572e-110">Prerequisites</span></span>
<span data-ttu-id="3572e-111">このセクションの手順を実行するには、ドメイン コントローラーを操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3572e-111">To follow this section step-by-step, you'll need to be operating on a domain controller.</span></span>
<span data-ttu-id="3572e-112">ドメイン コントローラーにアクセスしたことがなくても大丈夫です。</span><span class="sxs-lookup"><span data-stu-id="3572e-112">If you don't have access to your domain controller, don't worry.</span></span>
<span data-ttu-id="3572e-113">熟知している他のシナリオやロールでの作業を想像しながら、読み進めてください。</span><span class="sxs-lookup"><span data-stu-id="3572e-113">Try to follow along with by working against some other scenario or role with which you are familiar.</span></span>
<span data-ttu-id="3572e-114">新しいドメイン コントローラーをすぐに設定する場合は、付録の「[ドメイン コントローラーの作成](.\creating-a-domain-controller.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3572e-114">If you want to quickly set up a new domain controller, check out the [Creating a Domain Controller appendix](.\creating-a-domain-controller.md).</span></span>

## <a name="steps-to-make-a-new-role-capability-and-session-configuration"></a><span data-ttu-id="3572e-115">新しいロール機能とセッション構成の作成手順</span><span class="sxs-lookup"><span data-stu-id="3572e-115">Steps to Make a new Role Capability and Session Configuration</span></span>

<span data-ttu-id="3572e-116">新しいロール機能の作成は、最初はやっかいな作業に思えるかもしれませんが、それは、次に示す非常に単純な手順に分解することができます。</span><span class="sxs-lookup"><span data-stu-id="3572e-116">Making a new role capability can seem daunting at first, but it can be broken into fairly simple steps:</span></span>

1.  <span data-ttu-id="3572e-117">有効にする必要があるタスクを特定する</span><span class="sxs-lookup"><span data-stu-id="3572e-117">Identify the tasks you need to enable</span></span>
2.  <span data-ttu-id="3572e-118">必要に応じて、それらのタスクを制限する</span><span class="sxs-lookup"><span data-stu-id="3572e-118">Restrict those tasks as necessary</span></span>
3.  <span data-ttu-id="3572e-119">タスクが JEA で機能することを確認する</span><span class="sxs-lookup"><span data-stu-id="3572e-119">Confirm they work with JEA</span></span>
4.  <span data-ttu-id="3572e-120">タスクをロール機能ファイルに配置する</span><span class="sxs-lookup"><span data-stu-id="3572e-120">Put them in a Role Capability file</span></span>
5.  <span data-ttu-id="3572e-121">ロール機能を公開するセッション構成を登録する</span><span class="sxs-lookup"><span data-stu-id="3572e-121">Register a Session Configuration that exposes that Role Capability</span></span>

## <a name="step-1-identify-what-needs-to-be-exposed"></a><span data-ttu-id="3572e-122">手順 1: 何を公開する必要があるかを識別する</span><span class="sxs-lookup"><span data-stu-id="3572e-122">Step 1: Identify What Needs to Be Exposed</span></span>
<span data-ttu-id="3572e-123">新しいロール機能またはセッション構成を作成する前に、ユーザーが JEA エンドポイントで何を実行する必要があり、それらを PowerShell でどのように実行する必要があるかを、すべて識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3572e-123">Before you make a new Role Capability or Session Configuration, you need to identify all of the things users will need to do through the JEA endpoint, as well as how to do them through PowerShell.</span></span>
<span data-ttu-id="3572e-124">これには、相当量の要件の収集と調査が伴います。</span><span class="sxs-lookup"><span data-stu-id="3572e-124">This will involve a fair amount of requirement gathering and research.</span></span>
<span data-ttu-id="3572e-125">このプロセスをどのように進めるかは、組織と目標によって決まります。</span><span class="sxs-lookup"><span data-stu-id="3572e-125">How you go about this process will depend on your organization and goals.</span></span>
<span data-ttu-id="3572e-126">重要なのは、要件の収集と調査を、非常に意味のある作業として実施することです。</span><span class="sxs-lookup"><span data-stu-id="3572e-126">It is important to call out requirement gathering and research as a critical part of the real world process.</span></span>
<span data-ttu-id="3572e-127">これは、JEA の採用プロセスの中で、最も困難な手順である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3572e-127">This may be the most difficult step in the process of adopting JEA.</span></span>

### <a name="find-resources"></a><span data-ttu-id="3572e-128">リソースを見つける</span><span class="sxs-lookup"><span data-stu-id="3572e-128">Find Resources</span></span>
<span data-ttu-id="3572e-129">Active Directory 管理エンドポイントを作成するための調査で利用されている可能性があるオンライン リソースがあります。</span><span class="sxs-lookup"><span data-stu-id="3572e-129">Here is a set of online resources that might have come up in your research on creating an Active Directory management endpoint:</span></span>
-   [<span data-ttu-id="3572e-130">Active Directory PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="3572e-130">Active Directory PowerShell Overview</span></span>](http://blogs.msdn.com/b/adpowershell/archive/2009/03/05/active-directory-powershell-overview.aspx)
-   [<span data-ttu-id="3572e-131">Active Directory 用 PowerShell コマンド ガイド</span><span class="sxs-lookup"><span data-stu-id="3572e-131">CMD to PowerShell Guide for Active Directory</span></span>](http://blogs.technet.com/b/ashleymcglone/archive/2013/01/02/free-download-cmd-to-powershell-guide-for-ad.aspx)

### <a name="make-a-list"></a><span data-ttu-id="3572e-132">リストを作成する</span><span class="sxs-lookup"><span data-stu-id="3572e-132">Make a List</span></span>
<span data-ttu-id="3572e-133">このセクションの残りの部分で扱う 10 個の操作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3572e-133">Here is a set of ten actions that you will be working from in the remainder of this section.</span></span>
<span data-ttu-id="3572e-134">これは単なる例であり、組織の要件によって異なる可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3572e-134">Keep in mind this is simply an example, your organizations requirements may be different:</span></span>

|<span data-ttu-id="3572e-135">操作</span><span class="sxs-lookup"><span data-stu-id="3572e-135">Action</span></span>                                                         |<span data-ttu-id="3572e-136">PowerShell コマンド</span><span class="sxs-lookup"><span data-stu-id="3572e-136">PowerShell Command</span></span>                                             |
|---------------------------------------------------------------|---------------------------------------------------------------|
|<span data-ttu-id="3572e-137">アカウントのロック解除</span><span class="sxs-lookup"><span data-stu-id="3572e-137">Account Unlock</span></span>                                                 |`Unlock-ADAccount`                                             |
|<span data-ttu-id="3572e-138">パスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="3572e-138">Password Reset</span></span>                                                 |<span data-ttu-id="3572e-139">`Set-ADAccountPassword`、`Set-ADUser -ChangePasswordAtLogon`</span><span class="sxs-lookup"><span data-stu-id="3572e-139">`Set-ADAccountPassword` and `Set-ADUser -ChangePasswordAtLogon`</span></span>|
|<span data-ttu-id="3572e-140">ユーザーのタイトルの変更</span><span class="sxs-lookup"><span data-stu-id="3572e-140">Change a User's Title</span></span>                                          |`Set-ADUser -Title`                                            |  
|<span data-ttu-id="3572e-141">ロックアウト済み、無効化、非アクティブなどの状態になっている AD アカウントの検索</span><span class="sxs-lookup"><span data-stu-id="3572e-141">Find AD Accounts that are locked out, disabled, inactive, etc.</span></span> |`Search-ADAccount`                                             |
|<span data-ttu-id="3572e-142">グループへのユーザーの追加</span><span class="sxs-lookup"><span data-stu-id="3572e-142">Add User to Group</span></span>                                              |`Add-ADGroupMember -Identity (with whitelist) -Members`        |
|<span data-ttu-id="3572e-143">グループからのユーザーの削除</span><span class="sxs-lookup"><span data-stu-id="3572e-143">Remove User from Group</span></span>                                         |`Remove-ADGroupMember -Identity (with whitelist) -Members`     |
|<span data-ttu-id="3572e-144">ユーザー アカウントの有効化</span><span class="sxs-lookup"><span data-stu-id="3572e-144">Enable a user account</span></span>                                          |`Enable-ADAccount`                                             |
|<span data-ttu-id="3572e-145">ユーザー アカウントの無効化</span><span class="sxs-lookup"><span data-stu-id="3572e-145">Disable a user account</span></span>                                         |`Disable-ADAccount`                                            |

## <a name="step-2-restrict-tasks-as-necessary"></a><span data-ttu-id="3572e-146">手順 2: 必要に応じてタスクを制限する</span><span class="sxs-lookup"><span data-stu-id="3572e-146">Step 2: Restrict Tasks as Necessary</span></span>

<span data-ttu-id="3572e-147">操作リストができたら、各コマンドの機能を徹底的に検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3572e-147">Now that you have your list of actions, you need to think through the capabilities of each command.</span></span>
<span data-ttu-id="3572e-148">これを行う 2 つの重要な理由があります。</span><span class="sxs-lookup"><span data-stu-id="3572e-148">There are two important reasons to do this:</span></span>

1.  <span data-ttu-id="3572e-149">意図以上の機能がユーザーに与えられる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3572e-149">It is easy to give users more capabilities than you intend.</span></span>
<span data-ttu-id="3572e-150">たとえば、`Set-ADUser` は非常に強力で柔軟なコマンドです。</span><span class="sxs-lookup"><span data-stu-id="3572e-150">For example, `Set-ADUser` is an incredibly powerful and flexible command.</span></span>
<span data-ttu-id="3572e-151">このコマンドで実行できるすべての操作をヘルプ デスクのユーザーに公開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3572e-151">You may not want to expose everything it can do to help desk users.</span></span>  

2.  <span data-ttu-id="3572e-152">さらに悪いのは、ユーザーが JEA の制限を逃れることを可能にするコマンドが公開される可能性があることです。</span><span class="sxs-lookup"><span data-stu-id="3572e-152">Even worse, it's possible to expose commands that allow users to escape JEA's restrictions.</span></span>
<span data-ttu-id="3572e-153">これが発生した場合、JEA はセキュリティ境界として機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="3572e-153">If this happens, JEA ceases to function as a security boundary.</span></span>
<span data-ttu-id="3572e-154">コマンドは慎重に選択してください。</span><span class="sxs-lookup"><span data-stu-id="3572e-154">Please be careful when selecting commands.</span></span>
<span data-ttu-id="3572e-155">たとえば、Invoke-Expression は、ユーザーがコードを無制限に実行することを可能にします。</span><span class="sxs-lookup"><span data-stu-id="3572e-155">For example, Invoke-Expression will allow users to run unrestricted code.</span></span>
<span data-ttu-id="3572e-156">このトピックの詳細については、「コマンドを制限する際の考慮事項」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3572e-156">For more discussion on this topic, check out the Considerations When Restricting Commands section.</span></span>

<span data-ttu-id="3572e-157">各コマンドを検討した後、次のように制限することを決定したとします。</span><span class="sxs-lookup"><span data-stu-id="3572e-157">After reviewing each command, you decide to restrict the following:</span></span>

1.  <span data-ttu-id="3572e-158">`Set-ADUser` は、-Title パラメーターが指定された場合のみ実行することを許可する</span><span class="sxs-lookup"><span data-stu-id="3572e-158">`Set-ADUser` should only be allowed to run with the -Title parameter</span></span>

2.  <span data-ttu-id="3572e-159">`Add-ADGroupMember` と `Remove-ADGroupMember` は、特定のグループでのみ動作する必要がある</span><span class="sxs-lookup"><span data-stu-id="3572e-159">`Add-ADGroupMember` and `Remove-ADGroupMember` should only work with certain groups</span></span>

### <a name="step-3-confirm-the-tasks-work-with-jea"></a><span data-ttu-id="3572e-160">手順 3: タスクが JEA で動作することを確認する</span><span class="sxs-lookup"><span data-stu-id="3572e-160">Step 3: Confirm the Tasks Work with JEA</span></span>
<span data-ttu-id="3572e-161">これらのコマンドレットは、制限された JEA 環境では単純に使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="3572e-161">Actually using those cmdlets may not be straightforward in the restricted JEA environment.</span></span>
<span data-ttu-id="3572e-162">JEA は *NoLanguage* モードで実行されますが、このモードは、なによりもユーザーが変数を使用することを禁止します。</span><span class="sxs-lookup"><span data-stu-id="3572e-162">JEA runs in *NoLanguage* mode which, among other things, prevents users from using variables.</span></span>
<span data-ttu-id="3572e-163">スムーズなエンド ユーザー エクスペリエンスを実現するには、いくつかの事項を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3572e-163">In order to ensure that end users have a smooth experience, it's important to check for a few things.</span></span>

<span data-ttu-id="3572e-164">例として、`Set-ADAccountPassword` を検討します。</span><span class="sxs-lookup"><span data-stu-id="3572e-164">As an example, consider `Set-ADAccountPassword`.</span></span>
<span data-ttu-id="3572e-165">-NewPassword パラメーターには、セキュリティで保護された文字列が必要です。</span><span class="sxs-lookup"><span data-stu-id="3572e-165">The -NewPassword parameter requires a secure string.</span></span>
<span data-ttu-id="3572e-166">多くの場合、ユーザーは、セキュリティで保護された文字列を作成し、それを変数として渡します (下記参照)。</span><span class="sxs-lookup"><span data-stu-id="3572e-166">Often, users create a secure string and pass it in as a variable (as below):</span></span>

```PowerShell
$newPassword = Read-Host -Prompt "Specify a new password" -AsSecureString
Set-ADAccountPassword -Identity mollyd -NewPassword $newPassword -Reset
```

<span data-ttu-id="3572e-167">ただし、*NoLanguage* モードでは、変数は使用できません。</span><span class="sxs-lookup"><span data-stu-id="3572e-167">However, *NoLanguage* mode prevents the usage of variables.</span></span>
<span data-ttu-id="3572e-168">この制限は、次の 2 つの方法で回避できます。</span><span class="sxs-lookup"><span data-stu-id="3572e-168">You can get around this restriction in two ways:</span></span>

1.  <span data-ttu-id="3572e-169">変数を割り当てずにコマンドを実行することをユーザーに要求する。</span><span class="sxs-lookup"><span data-stu-id="3572e-169">You can require users run the command without assigning variables.</span></span>
<span data-ttu-id="3572e-170">これは簡単に構成できますが、エンドポイントを使用するオペレーターにとってはわずらわしい操作になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3572e-170">This is easy to configure, but can be painful for the operators using the endpoint.</span></span>
<span data-ttu-id="3572e-171">パスワードをリセットするたびに、この文字列を入力したいと思う人がいるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="3572e-171">Who wants to type this out every time you reset a password?</span></span>
```PowerShell
Set-ADAccountPassword -Identity mollyd -NewPassword (Read-Host -Prompt "Specify a new password" -AsSecureString) -Reset
```

2.  <span data-ttu-id="3572e-172">エンド ユーザーに公開されるスクリプトまたは関数で複雑さをラップする。</span><span class="sxs-lookup"><span data-stu-id="3572e-172">You can wrap the complexity in a script or a function that you expose to end users.</span></span>
<span data-ttu-id="3572e-173">公開するスクリプトと関数が実行されるコンテキストに制限はありません。変数の使用と他のコマンドの呼び出しがある関数を問題なく記述できます。</span><span class="sxs-lookup"><span data-stu-id="3572e-173">Scripts and functions that you expose run in an unrestricted context; you can write functions that use variables and call other commands without any issue.</span></span>
<span data-ttu-id="3572e-174">この方法は、エンド ユーザー エクスペリエンスを単純化し、エラーを防止し、PowerShell の知識が少なくても実行でき、余分な機能を意図せずに公開する可能性を低下させます。</span><span class="sxs-lookup"><span data-stu-id="3572e-174">This approach simplifies the end user experience, prevents errors, reduces required PowerShell knowledge, and reduces unintentionally exposing excess functionality.</span></span>
<span data-ttu-id="3572e-175">唯一の欠点は、関数を作成して管理するコストが発生することです。</span><span class="sxs-lookup"><span data-stu-id="3572e-175">The only downside is the cost of authoring and maintaining the function.</span></span>

### <a name="aside-adding-a-function-to-your-module"></a><span data-ttu-id="3572e-176">追加情報: モジュールへの関数の追加</span><span class="sxs-lookup"><span data-stu-id="3572e-176">Aside: Adding a Function to your Module</span></span>
<span data-ttu-id="3572e-177">方法 2 を採用する場合は、`Reset-ContosoUserPassword` という名前の PowerShell 関数を記述します。</span><span class="sxs-lookup"><span data-stu-id="3572e-177">Taking approach #2, you are going to write a PowerShell function called `Reset-ContosoUserPassword`.</span></span>
<span data-ttu-id="3572e-178">この関数は、ユーザーのパスワードをリセットするときに実行する必要があるすべての操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3572e-178">This function is going to do everything that needs to happen when you reset a user's password.</span></span>
<span data-ttu-id="3572e-179">組織によっては、手の込んだ複雑な操作が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3572e-179">In your organization, this may involve doing fancy and complicated things.</span></span>
<span data-ttu-id="3572e-180">これは単なる例であるため、ここで説明するコマンドは、パスワードをリセットし、ログオン時にパスワードを変更することをユーザーに要求するだけです。</span><span class="sxs-lookup"><span data-stu-id="3572e-180">Because this is just an example, your command will just reset the password and require the user change the password at logon.</span></span>
<span data-ttu-id="3572e-181">これを、最後のセクションで作成した Contoso_AD_Module モジュールに配置します。</span><span class="sxs-lookup"><span data-stu-id="3572e-181">We will put it in the Contoso_AD_Module module you made in the last section.</span></span>

1. <span data-ttu-id="3572e-182">PowerShell ISE で Contoso_AD_Module.psm1 を開きます。</span><span class="sxs-lookup"><span data-stu-id="3572e-182">In PowerShell ISE, open "Contoso_AD_Module.psm1"</span></span>
```PowerShell
ise 'C:\Program Files\WindowsPowerShell\Modules\Contoso_AD_Module\Contoso_AD_Module.psm1'
```

2. <span data-ttu-id="3572e-183">Crtl + J キーを押して、スニペット メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="3572e-183">Press Crtl+J to open the snippets menu.</span></span>

3. <span data-ttu-id="3572e-184">"function" が見つかるまでキーを押し続けて、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3572e-184">Key down until you find "function" and press enter.</span></span>
<span data-ttu-id="3572e-185">これにより、関数の極めて基本的なスケルトンが格納されます。</span><span class="sxs-lookup"><span data-stu-id="3572e-185">This puts up a super basic skeleton of a function.</span></span>

4. <span data-ttu-id="3572e-186">関数の名前を「Reset-ContosoUserPassword」に変更します。</span><span class="sxs-lookup"><span data-stu-id="3572e-186">Rename the function "Reset-ContosoUserPassword".</span></span>  

5. <span data-ttu-id="3572e-187">いずれかのパラメーターの名前を「Identity」にし、2 つ目を削除します。</span><span class="sxs-lookup"><span data-stu-id="3572e-187">Rename one of the parameters "Identity" and delete the second.</span></span>

6. <span data-ttu-id="3572e-188">以下を関数の本文にコピーします。</span><span class="sxs-lookup"><span data-stu-id="3572e-188">Copy the following into the body of the function.</span></span>
```PowerShell
# Get the new password
$NewPassword = Read-Host -Prompt "Enter a new password" -AsSecureString
# Reset the password
Set-ADAccountPassword -Identity $Identity -NewPassword $NewPassword -Reset
# Require the user to reset at next logon
Set-ADUser -Identity $Identity -ChangePasswordAtLogon
```

7. <span data-ttu-id="3572e-189">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="3572e-189">Save the file.</span></span>
<span data-ttu-id="3572e-190">最終的に、次のようなものになります。</span><span class="sxs-lookup"><span data-stu-id="3572e-190">You should end up with something that looks like this:</span></span>
```PowerShell
function Reset-ContosoUserPassword ($Identity)
{
# Get the new password
$NewPassword = Read-Host -Prompt "Enter a new password" -AsSecureString
# Reset the password
Set-ADAccountPassword -Identity $Identity -NewPassword $NewPassword -Reset
# Require the user to reset at next logon
Set-ADUser -Identity $Identity -ChangePasswordAtLogon
}
```
<span data-ttu-id="3572e-191">これで、ユーザーは `Reset-ContosoUserPassword` を簡単に呼び出すことができ、安全なインライン文字列を作成する構文を覚えて置く必要もなくなりました。</span><span class="sxs-lookup"><span data-stu-id="3572e-191">Now, your users can simply call `Reset-ContosoUserPassword` and not have to remember the syntax to create a secure string inline.</span></span>

## <a name="step-4-edit-the-role-capability-file"></a><span data-ttu-id="3572e-192">手順 4: ロール機能ファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="3572e-192">Step 4: Edit the Role Capability File</span></span>
<span data-ttu-id="3572e-193">「[ロール機能の作成](./role-capabilities.md#role-capability-creation)」セクションで、空のロール機能ファイルを作成しました。</span><span class="sxs-lookup"><span data-stu-id="3572e-193">In the [Role Capability Creation](./role-capabilities.md#role-capability-creation) section, you created a blank Role Capability file.</span></span>
<span data-ttu-id="3572e-194">このセクションでは、このファイルに値を設定します。</span><span class="sxs-lookup"><span data-stu-id="3572e-194">In this section, you will fill in the values in that file.</span></span>

<span data-ttu-id="3572e-195">PowerShell ISE でロール機能ファイルを開いて開始します。</span><span class="sxs-lookup"><span data-stu-id="3572e-195">Start by opening the role capability file in PowerShell ISE.</span></span>
```PowerShell
ise 'C:\Program Files\WindowsPowerShell\Modules\Contoso_AD_Module\RoleCapabilities\ADHelpDesk.psrc'
```
<span data-ttu-id="3572e-196">ファイルを以下のように変更します。</span><span class="sxs-lookup"><span data-stu-id="3572e-196">Update the file with the following changes:</span></span>
```PowerShell
# OLD: VisibleCmdlets = 'Invoke-Cmdlet1', @{ Name = 'Invoke-Cmdlet2'; Parameters = @{ Name = 'Parameter1'; ValidateSet = 'Item1', 'Item2' }, @{ Name = 'Parameter2'; ValidatePattern = 'L*' } }
VisibleCmdlets =
    'Unlock-ADAccount',
    'Search-ADAccount',
    'Enable-ADAccount',
    'Disable-ADAccount',
    @{ Name = 'Set-ADUser'; Parameters = @{ Name = 'Title'; ValidateSet = 'Manager', 'Engineer' }},
    @{ Name = 'Add-ADGroupMember'; Parameters =
        @{Name = 'Identity'; ValidateSet = 'TestGroup'},
        @{Name = 'Members'}},
    @{ Name = 'Remove-ADGroupMember'; Parameters =
        @{Name = 'Identity'; ValidateSet = 'TestGroup'},
        @{Name = 'Members'}}

# OLD: VisibleFunctions = 'Invoke-Function1', @{ Name = 'Invoke-Function2'; Parameters = @{ Name = 'Parameter1'; ValidateSet = 'Item1', 'Item2' }, @{ Name = 'Parameter2'; ValidatePattern = 'L*' } }
VisibleFunctions = 'Reset-ContosoUserPassword'
```

<span data-ttu-id="3572e-197">ここで、いくつかの注意点があります。</span><span class="sxs-lookup"><span data-stu-id="3572e-197">There are a few things to note about the above:</span></span>
1.  <span data-ttu-id="3572e-198">PowerShell は、ロール機能に必要なモジュールの自動読み込みを試行します。</span><span class="sxs-lookup"><span data-stu-id="3572e-198">PowerShell will attempt to auto-load the modules needed for your Role Capability.</span></span>
<span data-ttu-id="3572e-199">モジュールが自動的に読み込まれない問題が発生した場合、ModulesToImport フィールドにモジュール名を明示的にリストする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3572e-199">You may need to explicitly list module names in the "ModulesToImport" field if you notice problems with a module not being autoloaded.</span></span>

2.  <span data-ttu-id="3572e-200">コマンドがコマンドレットまたは関数のいずれであるかわからない場合は、`Get-Command` を実行して、"CommandType" プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="3572e-200">If you aren't sure if a command is a cmdlet or a function, run `Get-Command` and look at the "CommandType" property</span></span>

3.  <span data-ttu-id="3572e-201">一連の使用可能値を簡単に定義できない場合は、ValidatePattern により、正規表現を使って、パラメーター引数を制限できます。</span><span class="sxs-lookup"><span data-stu-id="3572e-201">The ValidatePattern allows you to use a regular expression to restrict parameter arguments if it is not easy to define a set of allowable values.</span></span>
<span data-ttu-id="3572e-202">1 つのパラメーターについて ValidatePattern と ValidateSet の両方を定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="3572e-202">You cannot define both a ValidatePattern and ValidateSet for a single parameter.</span></span>

## <a name="step-5-register-a-new-session-configuration"></a><span data-ttu-id="3572e-203">手順 5: 新しいセッション構成を登録する</span><span class="sxs-lookup"><span data-stu-id="3572e-203">Step 5: Register a new Session Configuration</span></span>
<span data-ttu-id="3572e-204">次に、ロール機能を JEA_NonAdmin_HelpDesk グループのメンバーに公開する新しいセッション構成ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3572e-204">Next, you will create a new session configuration file that will expose your Role Capability to members of the "JEA_NonAdmin_HelpDesk" AD group.</span></span>

<span data-ttu-id="3572e-205">まず、PowerShell ISE に新しい空のセッション構成ファイルを作成して、開きます。</span><span class="sxs-lookup"><span data-stu-id="3572e-205">Start by creating and opening a new blank Session Configuration file in PowerShell ISE.</span></span>
```PowerShell
New-PSSessionConfigurationFile -Path "$env:ProgramData\JEAConfiguration\HelpDeskDemo.pssc"
ise "$env:ProgramData\JEAConfiguration\HelpDeskDemo.pssc"
```
<span data-ttu-id="3572e-206">PSSC ファイル内の次のフィールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="3572e-206">Modify the following fields in the PSSC file.</span></span>
<span data-ttu-id="3572e-207">独自の環境で作業している場合は、CONTOSO\JEA_NonAdmins_Helpdesk を自身の管理者以外のユーザーまたはグループに置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="3572e-207">If you are working in your own environment, you should replace "CONTOSO\JEA_NonAdmins_Helpdesk" with your own non-administrator user or group.</span></span>
```PowerShell
# OLD: Description = ''
Description = 'An endpoint for Active Directory tasks.'

# OLD: SessionType = 'Default'
SessionType = 'RestrictedRemoteServer'

# OLD: TranscriptDirectory = 'C:\Transcripts\'
TranscriptDirectory = "C:\ProgramData\JEAConfiguration\Transcripts"

# OLD: RunAsVirtualAccount = $true
RunAsVirtualAccount = $true

# OLD: RoleDefinitions = @{ 'CONTOSO\SqlAdmins' = @{ RoleCapabilities = 'SqlAdministration' }; 'CONTOSO\ServerMonitors' = @{ VisibleCmdlets = 'Get-Process' } }
RoleDefinitions = @{ 'CONTOSO\JEA_NonAdmin_HelpDesk' = @{ RoleCapabilities =  'ADHelpDesk' }}
```
<span data-ttu-id="3572e-208">セッション構成の保存と登録</span><span class="sxs-lookup"><span data-stu-id="3572e-208">Save and register the Session Configuration</span></span>
```PowerShell
Register-PSSessionConfiguration -Name ADHelpDesk -Path "$env:ProgramData\JEAConfiguration\HelpDeskDemo.pssc"
```
## <a name="test-it-out"></a><span data-ttu-id="3572e-209">テストしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="3572e-209">Test It Out!</span></span>
<span data-ttu-id="3572e-210">管理者以外のユーザー資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="3572e-210">Get your non-administrator user credentials:</span></span>
```PowerShell
$HelpDeskCred = Get-Credential
```
<span data-ttu-id="3572e-211">「[ユーザーとグループの設定](creating-a-domain-controller.md#set-up-users-and-groups)」に従っている場合、資格情報は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3572e-211">If you followed the [Set Up Users and Groups](creating-a-domain-controller.md#set-up-users-and-groups) section, the credentials will be:</span></span>
-   <span data-ttu-id="3572e-212">ユーザー名 = HelpDeskUser</span><span class="sxs-lookup"><span data-stu-id="3572e-212">Username = "HelpDeskUser"</span></span>
-   <span data-ttu-id="3572e-213">パスワード = "pa$$w0rd"</span><span class="sxs-lookup"><span data-stu-id="3572e-213">Password = "pa$$w0rd"</span></span>

<span data-ttu-id="3572e-214">管理者以外の資格情報を使用して AD ヘルプデスクのエンドポイントにリモート接続します。</span><span class="sxs-lookup"><span data-stu-id="3572e-214">Remote into the ADHelpdesk endpoint using the non-admin credential:</span></span>
```PowerShell
Enter-PSSession -ComputerName . -ConfigurationName ADHelpDesk -Credential $HelpDeskCred
```
<span data-ttu-id="3572e-215">Set-ADUser を使って、ユーザーの役職をリセットします。</span><span class="sxs-lookup"><span data-stu-id="3572e-215">Use Set-ADUser to reset a user's title.</span></span>
```PowerShell
Set-ADUser -Identity OperatorUser -Title Engineer
```
<span data-ttu-id="3572e-216">役職が変更されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3572e-216">Verify that the title has changed.</span></span>
```PowerShell
Get-ADUser -Identity OperatorUser -Property Title
```
<span data-ttu-id="3572e-217">ここで、Add-ADGroupMember を使って、ユーザーを TestGroup に追加します。</span><span class="sxs-lookup"><span data-stu-id="3572e-217">Now, use Add-ADGroupMember to add a user to the TestGroup.</span></span>
<span data-ttu-id="3572e-218">注: TestGroup は事前に作成しておいてください。</span><span class="sxs-lookup"><span data-stu-id="3572e-218">Note: make sure you've created the TestGroup beforehand.</span></span>
```PowerShell
Add-ADGroupMember TestGroup -Member OperatorUser -Verbose
```
<span data-ttu-id="3572e-219">セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="3572e-219">Exit the session:</span></span>
```PowerShell
Exit-PSSession
```
## <a name="key-concepts"></a><span data-ttu-id="3572e-220">主要概念</span><span class="sxs-lookup"><span data-stu-id="3572e-220">Key Concepts</span></span>
<span data-ttu-id="3572e-221">**NoLanguage モード**: PowerShell が NoLanguage モードの場合は、ユーザーが実行できるのはコマンドのみです。言語要素は使用できません。</span><span class="sxs-lookup"><span data-stu-id="3572e-221">**NoLanguage Mode**: When PowerShell is in "NoLanguage" mode, users may only run commands; they cannot use any language elements.</span></span>
<span data-ttu-id="3572e-222">詳細を確認するには、`Get-Help about_Language_Modes` を実行してください。</span><span class="sxs-lookup"><span data-stu-id="3572e-222">For more information, run `Get-Help about_Language_Modes`.</span></span>

<span data-ttu-id="3572e-223">**PowerShell 関数**: PowerShell 関数は、名前で呼び出すことのできる PowerShell コードのビットです。</span><span class="sxs-lookup"><span data-stu-id="3572e-223">**PowerShell Functions**: PowerShell functions are bits of PowerShell code that you can call by name.</span></span>
<span data-ttu-id="3572e-224">詳細を確認するには、`Get-Help about_Functions` を実行してください。</span><span class="sxs-lookup"><span data-stu-id="3572e-224">For more information, run `Get-Help about_Functions`.</span></span>

<span data-ttu-id="3572e-225">**ValidateSet/ValidatePattern**: コマンドの公開時に、特定のパラメーターに有効な引数を制限できます。</span><span class="sxs-lookup"><span data-stu-id="3572e-225">**ValidateSet/ValidatePattern**: When exposing a command, you can restrict valid arguments for specific parameters.</span></span>
<span data-ttu-id="3572e-226">ValidateSet は、有効な引数の特定のリストです。</span><span class="sxs-lookup"><span data-stu-id="3572e-226">A ValidateSet is a specific list of valid arguments.</span></span>
<span data-ttu-id="3572e-227">ValidatePattern は、そのパラメーターの引数が一致する必要のある正規表現です。</span><span class="sxs-lookup"><span data-stu-id="3572e-227">A ValidatePattern is a regular expression that the arguments for that parameter must match.</span></span>

