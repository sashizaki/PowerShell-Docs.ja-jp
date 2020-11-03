---
description: PowerShell プロファイルを作成して使用する方法について説明します。
keywords: powershell,コマンドレット
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Profiles
ms.openlocfilehash: d0457cf485528f675840161383aa24d0f63781fb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221363"
---
# <a name="about-profiles"></a><span data-ttu-id="0b3e1-104">プロファイルについて</span><span class="sxs-lookup"><span data-stu-id="0b3e1-104">About Profiles</span></span>

## <a name="short-description"></a><span data-ttu-id="0b3e1-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="0b3e1-105">Short Description</span></span>
<span data-ttu-id="0b3e1-106">PowerShell プロファイルを作成して使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-106">Describes how to create and use a PowerShell profile.</span></span>

## <a name="long-description"></a><span data-ttu-id="0b3e1-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="0b3e1-107">Long Description</span></span>

<span data-ttu-id="0b3e1-108">PowerShell プロファイルを作成して、環境をカスタマイズし、開始するすべての PowerShell セッションにセッション固有の要素を追加できます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-108">You can create a PowerShell profile to customize your environment and to add session-specific elements to every PowerShell session that you start.</span></span>

<span data-ttu-id="0b3e1-109">PowerShell プロファイルは、PowerShell の開始時に実行されるスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-109">A PowerShell profile is a script that runs when PowerShell starts.</span></span> <span data-ttu-id="0b3e1-110">プロファイルをログオンスクリプトとして使用して、環境をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-110">You can use the profile as a logon script to customize the environment.</span></span> <span data-ttu-id="0b3e1-111">コマンド、エイリアス、関数、変数、スナップイン、モジュール、および PowerShell ドライブを追加できます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-111">You can add commands, aliases, functions, variables, snap-ins, modules, and PowerShell drives.</span></span> <span data-ttu-id="0b3e1-112">また、セッション固有のその他の要素をプロファイルに追加することもできます。これにより、すべてのセッションでそれらをインポートまたは再作成することなく使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-112">You can also add other session-specific elements to your profile so they are available in every session without having to import or re-create them.</span></span>

<span data-ttu-id="0b3e1-113">PowerShell では、ユーザーとホストプログラムに対して複数のプロファイルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-113">PowerShell supports several profiles for users and host programs.</span></span> <span data-ttu-id="0b3e1-114">ただし、プロファイルは作成されません。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-114">However, it does not create the profiles for you.</span></span> <span data-ttu-id="0b3e1-115">このトピックでは、プロファイルについて説明し、コンピューターでプロファイルを作成および管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-115">This topic describes the profiles, and it describes how to create and maintain profiles on your computer.</span></span>

<span data-ttu-id="0b3e1-116">PowerShell コンソールの **Noprofile** パラメーター (PowerShell.exe) を使用して、プロファイルを指定せずに powershell を起動する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-116">It explains how to use the **NoProfile** parameter of the PowerShell console (PowerShell.exe) to start PowerShell without any profiles.</span></span> <span data-ttu-id="0b3e1-117">また、PowerShell の実行ポリシーがプロファイルに与える影響についても説明します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-117">And, it explains the effect of the PowerShell execution policy on profiles.</span></span>

## <a name="the-profile-files"></a><span data-ttu-id="0b3e1-118">プロファイルファイル</span><span class="sxs-lookup"><span data-stu-id="0b3e1-118">The Profile Files</span></span>

<span data-ttu-id="0b3e1-119">PowerShell では、複数のプロファイルファイルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-119">PowerShell supports several profile files.</span></span> <span data-ttu-id="0b3e1-120">また、PowerShell ホストプログラムは、独自のホスト固有のプロファイルをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-120">Also, PowerShell host programs can support their own host-specific profiles.</span></span>

<span data-ttu-id="0b3e1-121">たとえば、PowerShell コンソールでは、次の基本的なプロファイルファイルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-121">For example, the PowerShell console supports the following basic profile files.</span></span> <span data-ttu-id="0b3e1-122">プロファイルは、優先順位順に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-122">The profiles are listed in precedence order.</span></span> <span data-ttu-id="0b3e1-123">最初のプロファイルの優先順位は最も高くなります。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-123">The first profile has the highest precedence.</span></span>

|<span data-ttu-id="0b3e1-124">説明</span><span class="sxs-lookup"><span data-stu-id="0b3e1-124">Description</span></span>               | <span data-ttu-id="0b3e1-125">Path</span><span class="sxs-lookup"><span data-stu-id="0b3e1-125">Path</span></span>                                          |
|--------------------------|-----------------------------------------------|
|<span data-ttu-id="0b3e1-126">すべてのユーザー、すべてのホスト</span><span class="sxs-lookup"><span data-stu-id="0b3e1-126">All Users, All Hosts</span></span>      |<span data-ttu-id="0b3e1-127">$PSHOME \\Profile.ps1</span><span class="sxs-lookup"><span data-stu-id="0b3e1-127">$PSHOME\\Profile.ps1</span></span>                           |
|<span data-ttu-id="0b3e1-128">すべてのユーザー、現在のホスト</span><span class="sxs-lookup"><span data-stu-id="0b3e1-128">All Users, Current Host</span></span>   |<span data-ttu-id="0b3e1-129">$PSHOME \\Microsoft.PowerShell_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="0b3e1-129">$PSHOME\\Microsoft.PowerShell_profile.ps1</span></span>      |
|<span data-ttu-id="0b3e1-130">現在のユーザー、すべてのホスト</span><span class="sxs-lookup"><span data-stu-id="0b3e1-130">Current User, All Hosts</span></span>   |<span data-ttu-id="0b3e1-131">$Home \\ [My] ドキュメント \\ PowerShell \\Profile.ps1</span><span class="sxs-lookup"><span data-stu-id="0b3e1-131">$Home\\[My ]Documents\\PowerShell\\Profile.ps1</span></span> |
|<span data-ttu-id="0b3e1-132">現在のユーザー、現在のホスト</span><span class="sxs-lookup"><span data-stu-id="0b3e1-132">Current user, Current Host</span></span>|<span data-ttu-id="0b3e1-133">$Home \\ [My] ドキュメント \\ PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b3e1-133">$Home\\[My ]Documents\\PowerShell</span></span>\\<br><span data-ttu-id="0b3e1-134">Microsoft.PowerShell_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="0b3e1-134">Microsoft.PowerShell_profile.ps1</span></span> |

<span data-ttu-id="0b3e1-135">プロファイルパスには、次の変数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-135">The profile paths include the following variables:</span></span>

- <span data-ttu-id="0b3e1-136">`$PSHOME`変数。 PowerShell のインストールディレクトリを格納します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-136">The `$PSHOME` variable, which stores the installation directory for PowerShell</span></span>
- <span data-ttu-id="0b3e1-137">`$Home`現在のユーザーのホームディレクトリを格納する変数。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-137">The `$Home` variable, which stores the current user's home directory</span></span>

<span data-ttu-id="0b3e1-138">さらに、PowerShell をホストする他のプログラムは、独自のプロファイルをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-138">In addition, other programs that host PowerShell can support their own profiles.</span></span> <span data-ttu-id="0b3e1-139">たとえば、Visual Studio Code は次のホスト固有のプロファイルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-139">For example, Visual Studio Code supports the following host-specific profiles.</span></span>

|<span data-ttu-id="0b3e1-140">説明</span><span class="sxs-lookup"><span data-stu-id="0b3e1-140">Description</span></span>               | <span data-ttu-id="0b3e1-141">Path</span><span class="sxs-lookup"><span data-stu-id="0b3e1-141">Path</span></span>                                     |
|--------------------------|------------------------------------------|
|<span data-ttu-id="0b3e1-142">すべてのユーザー、現在のホスト</span><span class="sxs-lookup"><span data-stu-id="0b3e1-142">All users, Current Host</span></span>   |<span data-ttu-id="0b3e1-143">$PSHOME \\Microsoft.VSCode_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="0b3e1-143">$PSHOME\\Microsoft.VSCode_profile.ps1</span></span>|
|<span data-ttu-id="0b3e1-144">現在のユーザー、現在のホスト</span><span class="sxs-lookup"><span data-stu-id="0b3e1-144">Current user, Current Host</span></span>|<span data-ttu-id="0b3e1-145">$Home \\ [My] ドキュメント \\ PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b3e1-145">$Home\\[My ]Documents\\PowerShell</span></span>\\<br><span data-ttu-id="0b3e1-146">Microsoft.VSCode_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="0b3e1-146">Microsoft.VSCode_profile.ps1</span></span>|

<span data-ttu-id="0b3e1-147">PowerShell ヘルプでは、"CurrentUser, Current Host" プロファイルは、"お使いの PowerShell プロファイル" と呼ばれることが多いプロファイルです。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-147">In PowerShell Help, the "CurrentUser, Current Host" profile is the profile most often referred to as "your PowerShell profile".</span></span>

## <a name="the-profile-variable"></a><span data-ttu-id="0b3e1-148">$PROFILE 変数</span><span class="sxs-lookup"><span data-stu-id="0b3e1-148">The $PROFILE variable</span></span>

<span data-ttu-id="0b3e1-149">`$PROFILE`自動変数は、現在のセッションで使用可能な PowerShell プロファイルへのパスを格納します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-149">The `$PROFILE` automatic variable stores the paths to the PowerShell profiles that are available in the current session.</span></span>

<span data-ttu-id="0b3e1-150">プロファイルパスを表示するには、変数の値を表示し `$PROFILE` ます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-150">To view a profile path, display the value of the `$PROFILE` variable.</span></span> <span data-ttu-id="0b3e1-151">`$PROFILE`パスを表すために、コマンドで変数を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-151">You can also use the `$PROFILE` variable in a command to represent a path.</span></span>

<span data-ttu-id="0b3e1-152">変数には、 `$PROFILE` "現在のユーザー、現在のホスト" プロファイルへのパスが格納されます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-152">The `$PROFILE` variable stores the path to the "Current User, Current Host" profile.</span></span> <span data-ttu-id="0b3e1-153">その他のプロファイルは、変数のメモプロパティに保存され `$PROFILE` ます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-153">The other profiles are saved in note properties of the `$PROFILE` variable.</span></span>

<span data-ttu-id="0b3e1-154">たとえば、変数の `$PROFILE` 値は、Windows PowerShell コンソールで次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-154">For example, the `$PROFILE` variable has the following values in the Windows PowerShell console.</span></span>

|<span data-ttu-id="0b3e1-155">説明</span><span class="sxs-lookup"><span data-stu-id="0b3e1-155">Description</span></span>                |<span data-ttu-id="0b3e1-156">名前</span><span class="sxs-lookup"><span data-stu-id="0b3e1-156">Name</span></span>                              |
|---------------------------|----------------------------------|
|<span data-ttu-id="0b3e1-157">現在のユーザー、現在のホスト</span><span class="sxs-lookup"><span data-stu-id="0b3e1-157">Current User, Current Host</span></span> |`$PROFILE`                        |
|<span data-ttu-id="0b3e1-158">現在のユーザー、現在のホスト</span><span class="sxs-lookup"><span data-stu-id="0b3e1-158">Current User, Current Host</span></span> |`$PROFILE.CurrentUserCurrentHost` |
|<span data-ttu-id="0b3e1-159">現在のユーザー、すべてのホスト</span><span class="sxs-lookup"><span data-stu-id="0b3e1-159">Current User, All Hosts</span></span>    |`$PROFILE.CurrentUserAllHosts`    |
|<span data-ttu-id="0b3e1-160">すべてのユーザー、現在のホスト</span><span class="sxs-lookup"><span data-stu-id="0b3e1-160">All Users, Current Host</span></span>    |`$PROFILE.AllUsersCurrentHost`    |
|<span data-ttu-id="0b3e1-161">すべてのユーザー、すべてのホスト</span><span class="sxs-lookup"><span data-stu-id="0b3e1-161">All Users, All Hosts</span></span>       |`$PROFILE.AllUsersAllHosts`       |

<span data-ttu-id="0b3e1-162">変数の値は各 `$PROFILE` ユーザーと各ホストアプリケーションで変更されるため、使用する各 PowerShell ホストアプリケーションでプロファイル変数の値を表示するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-162">Because the values of the `$PROFILE` variable change for each user and in each host application, ensure that you display the values of the profile variables in each PowerShell host application that you use.</span></span>

<span data-ttu-id="0b3e1-163">変数の現在の値を表示するには `$PROFILE` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-163">To see the current values of the `$PROFILE` variable, type:</span></span>

```powershell
$PROFILE | Get-Member -Type NoteProperty
```

<span data-ttu-id="0b3e1-164">変数は、 `$PROFILE` 多くのコマンドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-164">You can use the `$PROFILE` variable in many commands.</span></span> <span data-ttu-id="0b3e1-165">たとえば、次のコマンドは、"現在のユーザー、現在のホスト" プロファイルをメモ帳で開きます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-165">For example, the following command opens the "Current User, Current Host" profile in Notepad:</span></span>

```powershell
notepad $PROFILE
```

<span data-ttu-id="0b3e1-166">次のコマンドは、"すべてのユーザー、すべてのホスト" プロファイルがローカルコンピューター上に作成されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-166">The following command determines whether an "All Users, All Hosts" profile has been created on the local computer:</span></span>

```powershell
Test-Path -Path $PROFILE.AllUsersAllHosts
```

## <a name="how-to-create-a-profile"></a><span data-ttu-id="0b3e1-167">プロファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="0b3e1-167">How to create a profile</span></span>

<span data-ttu-id="0b3e1-168">PowerShell プロファイルを作成するには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-168">To create a PowerShell profile, use the following command format:</span></span>

```powershell
if (!(Test-Path -Path <profile-name>)) {
  New-Item -ItemType File -Path <profile-name> -Force
}
```

<span data-ttu-id="0b3e1-169">たとえば、現在の PowerShell ホストアプリケーションで現在のユーザーのプロファイルを作成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-169">For example, to create a profile for the current user in the current PowerShell host application, use the following command:</span></span>

```powershell
if (!(Test-Path -Path $PROFILE)) {
  New-Item -ItemType File -Path $PROFILE -Force
}
```

<span data-ttu-id="0b3e1-170">このコマンドでは、 `If` ステートメントを使用して既存のプロファイルを上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-170">In this command, the `If` statement prevents you from overwriting an existing profile.</span></span> <span data-ttu-id="0b3e1-171">プレースホルダーの値を、 \<profile-path\> 作成するプロファイルファイルのパスに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-171">Replace the value of the \<profile-path\> placeholder with the path to the profile file that you want to create.</span></span>

> [!NOTE]
> <span data-ttu-id="0b3e1-172">Windows Vista 以降のバージョンの Windows で "すべてのユーザー" プロファイルを作成するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-172">To create "All Users" profiles in Windows Vista and later versions of Windows, start PowerShell with the **Run as administrator** option.</span></span>

## <a name="how-to-edit-a-profile"></a><span data-ttu-id="0b3e1-173">プロファイルを編集する方法</span><span class="sxs-lookup"><span data-stu-id="0b3e1-173">How to edit a profile</span></span>

<span data-ttu-id="0b3e1-174">任意の PowerShell プロファイルを、メモ帳などのテキストエディターで開くことができます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-174">You can open any PowerShell profile in a text editor, such as Notepad.</span></span>

<span data-ttu-id="0b3e1-175">現在の PowerShell ホストアプリケーションで現在のユーザーのプロファイルをメモ帳で開くには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-175">To open the profile of the current user in the current PowerShell host application in Notepad, type:</span></span>

```powershell
notepad $PROFILE
```

<span data-ttu-id="0b3e1-176">他のプロファイルを開くには、プロファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-176">To open other profiles, specify the profile name.</span></span> <span data-ttu-id="0b3e1-177">たとえば、すべてのホストアプリケーションのすべてのユーザーのプロファイルを開くには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-177">For example, to open the profile for all the users of all the host applications, type:</span></span>

```powershell
notepad $PROFILE.AllUsersAllHosts
```

<span data-ttu-id="0b3e1-178">変更を適用するには、プロファイルファイルを保存し、PowerShell を再起動します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-178">To apply the changes, save the profile file, and then restart PowerShell.</span></span>

## <a name="how-to-choose-a-profile"></a><span data-ttu-id="0b3e1-179">プロファイルを選択する方法</span><span class="sxs-lookup"><span data-stu-id="0b3e1-179">How to choose a profile</span></span>

<span data-ttu-id="0b3e1-180">複数のホストアプリケーションを使用する場合は、すべてのホストアプリケーションで使用する項目をプロファイルに配置し `$PROFILE.CurrentUserAllHosts` ます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-180">If you use multiple host applications, put the items that you use in all the host applications into your `$PROFILE.CurrentUserAllHosts` profile.</span></span> <span data-ttu-id="0b3e1-181">ホストアプリケーションに固有の項目 (ホストアプリケーションの背景色を設定するコマンドなど) を、そのホストアプリケーションに固有のプロファイルに配置します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-181">Put items that are specific to a host application, such as a command that sets the background color for a host application, in a profile that is specific to that host application.</span></span>

<span data-ttu-id="0b3e1-182">多くのユーザーに対して PowerShell をカスタマイズしている管理者は、次のガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-182">If you are an administrator who is customizing PowerShell for many users, follow these guidelines:</span></span>

- <span data-ttu-id="0b3e1-183">プロファイルに共通項目を格納する `$PROFILE.AllUsersAllHosts`</span><span class="sxs-lookup"><span data-stu-id="0b3e1-183">Store the common items in the `$PROFILE.AllUsersAllHosts` profile</span></span>
- <span data-ttu-id="0b3e1-184">ホストアプリケーションに固有の項目をホストアプリケーションに固有のプロファイルに格納する `$PROFILE.AllUsersCurrentHost`</span><span class="sxs-lookup"><span data-stu-id="0b3e1-184">Store items that are specific to a host application in `$PROFILE.AllUsersCurrentHost` profiles that are specific to the host application</span></span>
- <span data-ttu-id="0b3e1-185">ユーザー固有のプロファイルに特定のユーザーの項目を格納する</span><span class="sxs-lookup"><span data-stu-id="0b3e1-185">Store items for particular users in the user-specific profiles</span></span>

<span data-ttu-id="0b3e1-186">PowerShell プロファイルの特別な実装については、ホストアプリケーションのドキュメントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-186">Be sure to check the host application documentation for any special implementation of PowerShell profiles.</span></span>

## <a name="how-to-use-a-profile"></a><span data-ttu-id="0b3e1-187">プロファイルの使用方法</span><span class="sxs-lookup"><span data-stu-id="0b3e1-187">How to use a profile</span></span>

<span data-ttu-id="0b3e1-188">PowerShell で作成した項目の多くは、現在のセッションのみに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-188">Many of the items that you create in PowerShell and most commands that you run affect only the current session.</span></span> <span data-ttu-id="0b3e1-189">セッションを終了すると、項目が削除されます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-189">When you end the session, the items are deleted.</span></span>

<span data-ttu-id="0b3e1-190">セッション固有のコマンドと項目には、変数、ユーザー設定変数、エイリアス、関数、コマンド ( [set-executionpolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)を除く)、およびセッションに追加する PowerShell モジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-190">The session-specific commands and items include variables, preference variables, aliases, functions, commands (except for [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)), and PowerShell modules that you add to the session.</span></span>

<span data-ttu-id="0b3e1-191">これらの項目を保存して、今後のすべてのセッションで使用できるようにするには、それらを PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-191">To save these items and make them available in all future sessions, add them to a PowerShell profile.</span></span>

<span data-ttu-id="0b3e1-192">プロファイルのもう1つの一般的な用途は、頻繁に使用される関数、エイリアス、および変数を保存することです。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-192">Another common use for profiles is to save frequently-used functions, aliases, and variables.</span></span> <span data-ttu-id="0b3e1-193">プロファイルに項目を保存すると、その項目を再作成せずに、適用可能な任意のセッションで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-193">When you save the items in a profile, you can use them in any applicable session without recreating them.</span></span>

## <a name="how-to-start-a-profile"></a><span data-ttu-id="0b3e1-194">プロファイルを開始する方法</span><span class="sxs-lookup"><span data-stu-id="0b3e1-194">How to start a profile</span></span>

<span data-ttu-id="0b3e1-195">プロファイルファイルを開くと、そのファイルは空白になります。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-195">When you open the profile file, it is blank.</span></span> <span data-ttu-id="0b3e1-196">ただし、頻繁に使用する変数、エイリアス、およびコマンドを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-196">However, you can fill it with the variables, aliases, and commands that you use frequently.</span></span>

<span data-ttu-id="0b3e1-197">作業を開始するためのいくつかの推奨事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-197">Here are a few suggestions to get you started.</span></span>

### <a name="add-commands-that-make-it-easy-to-open-your-profile"></a><span data-ttu-id="0b3e1-198">プロファイルを簡単に開くためのコマンドを追加する</span><span class="sxs-lookup"><span data-stu-id="0b3e1-198">Add commands that make it easy to open your profile</span></span>

<span data-ttu-id="0b3e1-199">これは、"現在のユーザー、現在のホスト" プロファイル以外のプロファイルを使用する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-199">This is especially useful if you use a profile other than the "Current User, Current Host" profile.</span></span> <span data-ttu-id="0b3e1-200">たとえば、次のコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-200">For example, add the following command:</span></span>

```powershell
function Pro {notepad $PROFILE.CurrentUserAllHosts}
```

### <a name="add-a-function-that-lists-the-aliases-for-any-cmdlet"></a><span data-ttu-id="0b3e1-201">任意のコマンドレットのエイリアスを一覧表示する関数を追加する</span><span class="sxs-lookup"><span data-stu-id="0b3e1-201">Add a function that lists the aliases for any cmdlet</span></span>

```powershell
function Get-CmdletAlias ($cmdletname) {
  Get-Alias |
    Where-Object -FilterScript {$_.Definition -like "$cmdletname"} |
      Format-Table -Property Definition, Name -AutoSize
}
```

### <a name="customize-your-console"></a><span data-ttu-id="0b3e1-202">コンソールをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="0b3e1-202">Customize your console</span></span>

```powershell
function Color-Console {
  $Host.ui.rawui.backgroundcolor = "white"
  $Host.ui.rawui.foregroundcolor = "black"
  $hosttime = (Get-ChildItem -Path $PSHOME\PowerShell.exe).CreationTime
  $hostversion="$($Host.Version.Major)`.$($Host.Version.Minor)"
  $Host.UI.RawUI.WindowTitle = "PowerShell $hostversion ($hosttime)"
  Clear-Host
}
Color-Console
```

### <a name="add-a-customized-powershell-prompt"></a><span data-ttu-id="0b3e1-203">カスタマイズした PowerShell プロンプトを追加する</span><span class="sxs-lookup"><span data-stu-id="0b3e1-203">Add a customized PowerShell prompt</span></span>

```powershell
function Prompt
{
$env:COMPUTERNAME + "\" + (Get-Location) + "> "
}
```

<span data-ttu-id="0b3e1-204">PowerShell プロンプトの詳細については、「 [about_Prompts](about_Prompts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-204">For more information about the PowerShell prompt, see [about_Prompts](about_Prompts.md).</span></span>

## <a name="the-noprofile-parameter"></a><span data-ttu-id="0b3e1-205">NoProfile パラメーター</span><span class="sxs-lookup"><span data-stu-id="0b3e1-205">The NoProfile parameter</span></span>

<span data-ttu-id="0b3e1-206">プロファイルなしで PowerShell を開始するには、PowerShell を起動するプログラム **PowerShell.exe** の **noprofile** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-206">To start PowerShell without profiles, use the **NoProfile** parameter of **PowerShell.exe** , the program that starts PowerShell.</span></span>

<span data-ttu-id="0b3e1-207">まず、Cmd.exe や PowerShell 自体など、PowerShell を起動できるプログラムを開きます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-207">To begin, open a program that can start PowerShell, such as Cmd.exe or PowerShell itself.</span></span> <span data-ttu-id="0b3e1-208">Windows の [実行] ダイアログボックスを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-208">You can also use the Run dialog box in Windows.</span></span>

<span data-ttu-id="0b3e1-209">型:</span><span class="sxs-lookup"><span data-stu-id="0b3e1-209">Type:</span></span>

```
PowerShell -NoProfile
```

<span data-ttu-id="0b3e1-210">PowerShell.exe のパラメーターの完全な一覧を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-210">For a complete list of the parameters of PowerShell.exe, type:</span></span>

```
PowerShell -?
```

## <a name="profiles-and-execution-policy"></a><span data-ttu-id="0b3e1-211">プロファイルと実行ポリシー</span><span class="sxs-lookup"><span data-stu-id="0b3e1-211">Profiles and Execution Policy</span></span>

<span data-ttu-id="0b3e1-212">PowerShell の実行ポリシーによって、スクリプトを実行したり、構成ファイル (プロファイルを含む) を読み込むことができるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-212">The PowerShell execution policy determines, in part, whether you can run scripts and load configuration files, including the profiles.</span></span> <span data-ttu-id="0b3e1-213">**制限** された実行ポリシーが既定値です。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-213">The **Restricted** execution policy is the default.</span></span> <span data-ttu-id="0b3e1-214">プロファイルを含め、すべてのスクリプトの実行を防止します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-214">It prevents all scripts from running, including the profiles.</span></span> <span data-ttu-id="0b3e1-215">"Restricted" ポリシーを使用すると、プロファイルは実行されず、その内容は適用されません。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-215">If you use the "Restricted" policy, the profile does not run, and its contents are not applied.</span></span>

<span data-ttu-id="0b3e1-216">コマンドは、 `Set-ExecutionPolicy` 実行ポリシーを設定して変更します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-216">A `Set-ExecutionPolicy` command sets and changes your execution policy.</span></span> <span data-ttu-id="0b3e1-217">値はレジストリに保存されるため、すべての PowerShell セッションで適用されるいくつかのコマンドの1つです。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-217">It is one of the few commands that applies in all PowerShell sessions because the value is saved in the registry.</span></span> <span data-ttu-id="0b3e1-218">コンソールを開いたときに設定する必要はありません。また、プロファイルにコマンドを保存する必要もありません `Set-ExecutionPolicy` 。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-218">You do not have to set it when you open the console, and you do not have to store a `Set-ExecutionPolicy` command in your profile.</span></span>

## <a name="profiles-and-remote-sessions"></a><span data-ttu-id="0b3e1-219">プロファイルとリモートセッション</span><span class="sxs-lookup"><span data-stu-id="0b3e1-219">Profiles and remote sessions</span></span>

<span data-ttu-id="0b3e1-220">PowerShell プロファイルはリモートセッションで自動的に実行されないため、プロファイルによって追加されたコマンドはリモートセッションに存在しません。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-220">PowerShell profiles are not run automatically in remote sessions, so the commands that the profiles add are not present in the remote session.</span></span> <span data-ttu-id="0b3e1-221">また、 `$PROFILE` 自動変数は、リモートセッションでは設定されません。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-221">In addition, the `$PROFILE` automatic variable is not populated in remote sessions.</span></span>

<span data-ttu-id="0b3e1-222">セッションでプロファイルを実行するには、 [コマンド](xref:Microsoft.PowerShell.Core.Invoke-Command) レットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-222">To run a profile in a session, use the [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) cmdlet.</span></span>

<span data-ttu-id="0b3e1-223">たとえば、次のコマンドは、のセッションでローカルコンピューターから "現在のユーザー、現在のホスト" プロファイルを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-223">For example, the following command runs the "Current user, Current Host" profile from the local computer in the session in `$s`.</span></span>

```powershell
Invoke-Command -Session $s -FilePath $PROFILE
```

<span data-ttu-id="0b3e1-224">次のコマンドは、のセッションで、リモートコンピューターから "現在のユーザー、現在のホスト" プロファイルを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-224">The following command runs the "Current user, Current Host" profile from the remote computer in the session in `$s`.</span></span> <span data-ttu-id="0b3e1-225">変数が設定されていないため、この `$PROFILE` コマンドはプロファイルへの明示的なパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-225">Because the `$PROFILE` variable is not populated, the command uses the explicit path to the profile.</span></span> <span data-ttu-id="0b3e1-226">ドットソーシング演算子を使用すると、プロファイルはリモートコンピューター上の現在のスコープで実行され、それ自体のスコープ内では実行されません。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-226">We use dot sourcing operator so that the profile executes in the current scope on the remote computer and not in its own scope.</span></span>

```powershell
Invoke-Command -Session $s -ScriptBlock {
  . "$HOME\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1"
}
```

<span data-ttu-id="0b3e1-227">このコマンドを実行すると、プロファイルによってセッションに追加されたコマンドがで使用できるように `$s` なります。</span><span class="sxs-lookup"><span data-stu-id="0b3e1-227">After running this command, the commands that the profile adds to the session are available in `$s`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b3e1-228">参照</span><span class="sxs-lookup"><span data-stu-id="0b3e1-228">See Also</span></span>

[<span data-ttu-id="0b3e1-229">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="0b3e1-229">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="0b3e1-230">about_Functions</span><span class="sxs-lookup"><span data-stu-id="0b3e1-230">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="0b3e1-231">about_Prompts</span><span class="sxs-lookup"><span data-stu-id="0b3e1-231">about_Prompts</span></span>](about_Prompts.md)

[<span data-ttu-id="0b3e1-232">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="0b3e1-232">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="0b3e1-233">about_Signing</span><span class="sxs-lookup"><span data-stu-id="0b3e1-233">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="0b3e1-234">about_Remote</span><span class="sxs-lookup"><span data-stu-id="0b3e1-234">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="0b3e1-235">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="0b3e1-235">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="0b3e1-236">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="0b3e1-236">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)
