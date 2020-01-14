---
ms.date: 01/02/2020
keywords: powershell,コマンドレット
title: Windows PowerShell ISE でプロファイルを使用する方法
ms.openlocfilehash: da7dc2f234ad0c2968fbb213e9e57da875f456e4
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736251"
---
# <a name="how-to-use-profiles-in-windows-powershell-ise"></a><span data-ttu-id="59f34-103">Windows PowerShell ISE でプロファイルを使用する方法</span><span class="sxs-lookup"><span data-stu-id="59f34-103">How to Use Profiles in Windows PowerShell ISE</span></span>

<span data-ttu-id="59f34-104">このトピックでは、Windows PowerShell® Integrated Scripting Environment (ISE) でプロファイルを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="59f34-104">This topic explains how to use Profiles in Windows PowerShell® Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="59f34-105">このセクションのタスクを実行する前に、[about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles) を確認するか、またはコンソール ウィンドウに「`Get-Help about_Profiles`」と入力して <kbd>Enter</kbd> キーを押すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="59f34-105">We recommend that before performing the tasks in this section, you review [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles), or in the Console Pane, type, `Get-Help about_Profiles` and press <kbd>ENTER</kbd>.</span></span>

<span data-ttu-id="59f34-106">プロファイルは、新しいセッションを開始するときに自動的に実行される Windows PowerShell ISE スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="59f34-106">A profile is a Windows PowerShell ISE script that runs automatically when you start a new session.</span></span>
<span data-ttu-id="59f34-107">Windows PowerShell ISE 用に 1 つ以上の Windows PowerShell プロファイルを作成すると、Windows PowerShell または Windows PowerShell ISE 環境の構成に、自分の用途に合わせて変数、エイリアス、関数、色やフォントの設定などを追加するために利用できます。</span><span class="sxs-lookup"><span data-stu-id="59f34-107">You can create one or more Windows PowerShell profiles for Windows PowerShell ISE and use them to add the configure the Windows PowerShell or Windows PowerShell ISE environment, preparing it for your use, with variables, aliases, functions, and color and font preferences that you want available.</span></span> <span data-ttu-id="59f34-108">プロファイルは、開始するすべての Windows PowerShell ISE セッションに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="59f34-108">A profile affects every Windows PowerShell ISE session that you start.</span></span>

> [!NOTE]
> <span data-ttu-id="59f34-109">スクリプトの実行やプロファイルの読み込みが可能かどうかは、Windows PowerShell の実行ポリシーによって決まります。</span><span class="sxs-lookup"><span data-stu-id="59f34-109">The Windows PowerShell execution policy determines whether you can run scripts and load a profile.</span></span>
> <span data-ttu-id="59f34-110">既定の実行ポリシーは "Restricted" で、プロファイルを含め、すべてのスクリプトが実行されないようにします。</span><span class="sxs-lookup"><span data-stu-id="59f34-110">The default execution policy, “Restricted,” prevents all scripts from running, including profiles.</span></span>
> <span data-ttu-id="59f34-111">"Restricted" ポリシーを使う場合は、プロファイルを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="59f34-111">If you use the “Restricted” policy, the profile cannot load.</span></span> <span data-ttu-id="59f34-112">実行ポリシーの詳細については、「[about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59f34-112">For more information about execution policy, see [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>

## <a name="selecting-a-profile-to-use-in-the-windows-powershell-ise"></a><span data-ttu-id="59f34-113">Windows PowerShell ISE で使うプロファイルの選択</span><span class="sxs-lookup"><span data-stu-id="59f34-113">Selecting a profile to use in the Windows PowerShell ISE</span></span>

<span data-ttu-id="59f34-114">Windows PowerShell ISE は、現在のユーザーとすべてのユーザーのプロファイルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="59f34-114">Windows PowerShell ISE supports profiles for the current user and all users.</span></span> <span data-ttu-id="59f34-115">また、すべてのホストに適用される Windows PowerShell プロファイルもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="59f34-115">It also supports the Windows PowerShell profiles that apply to all hosts.</span></span>

<span data-ttu-id="59f34-116">使用するプロファイルは、Windows PowerShell と Windows PowerShell ISE の使用方法によって決まります。</span><span class="sxs-lookup"><span data-stu-id="59f34-116">The profile that you use is determined by how you use Windows PowerShell and Windows PowerShell ISE.</span></span>

- <span data-ttu-id="59f34-117">Windows PowerShell を実行するために Windows PowerShell ISE のみを使う場合は、すべての項目を ISE 固有のプロファイルの 1 つに保存します。たとえば、Windows PowerShell ISE 用の **CurrentUserCurrentHost** プロファイルや、Windows PowerShell ISE 用の **AllUsersCurrentHost** プロファイルです。</span><span class="sxs-lookup"><span data-stu-id="59f34-117">If you use only Windows PowerShell ISE to run Windows PowerShell, then save all your items in one of the ISE-specific profiles, such as the **CurrentUserCurrentHost** profile for Windows PowerShell ISE or the **AllUsersCurrentHost** profile for Windows PowerShell ISE.</span></span>

- <span data-ttu-id="59f34-118">Windows PowerShell を実行するために複数のホスト プログラムを使う場合は、関数、エイリアス、変数、コマンドをすべてのホスト プログラムに影響を与えるプロファイルに保存します。たとえば、CurrentUserAllHosts プロファイルや、**AllUsersAllHosts** プロファイルです。また、色やフォントのカスタマイズのような ISE 固有の機能は、Windows PowerShell ISE 用の **CurrentUserCurrentHost** プロファイルか、Windows PowerShell ISE 用の **AllUsersCurrentHost** プロファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="59f34-118">If you use multiple host programs to run Windows PowerShell, save your functions, aliases, variables, and commands in a profile that affects all host programs, such as the CurrentUserAllHosts or the **AllUsersAllHosts** profile, and save ISE-specific features, like color and font customization in the **CurrentUserCurrentHost** profile for Windows PowerShell ISE profile or the **AllUsersCurrentHost** profile for Windows PowerShell ISE.</span></span>

<span data-ttu-id="59f34-119">Windows PowerShell ISE で作成して利用できるプロファイルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="59f34-119">The following are profiles that can be created and used in Windows PowerShell ISE.</span></span> <span data-ttu-id="59f34-120">各プロファイルは、それぞれ特定のパスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="59f34-120">Each profile is saved to its own specific path.</span></span>

|           <span data-ttu-id="59f34-121">プロファイルの種類</span><span class="sxs-lookup"><span data-stu-id="59f34-121">Profile Type</span></span>           |                   <span data-ttu-id="59f34-122">プロファイルのパス</span><span class="sxs-lookup"><span data-stu-id="59f34-122">Profile Path</span></span>                   |
| -------------------------------- | ------------------------------------------------ |
| <span data-ttu-id="59f34-123">**現在のユーザー、PowerShell ISE**</span><span class="sxs-lookup"><span data-stu-id="59f34-123">**Current user, PowerShell ISE**</span></span> | <span data-ttu-id="59f34-124">`$PROFILE.CurrentUserCurrentHost` または `$PROFILE`</span><span class="sxs-lookup"><span data-stu-id="59f34-124">`$PROFILE.CurrentUserCurrentHost`, or `$PROFILE`</span></span> |
| <span data-ttu-id="59f34-125">**すべてのユーザー、PowerShell ISE**</span><span class="sxs-lookup"><span data-stu-id="59f34-125">**All users, PowerShell ISE**</span></span>    | `$PROFILE.AllUsersCurrentHost`                   |
| <span data-ttu-id="59f34-126">**現在のユーザー、すべてのホスト**</span><span class="sxs-lookup"><span data-stu-id="59f34-126">**Current user, All hosts**</span></span>      | `$PROFILE.CurrentUserAllHosts`                   |
| <span data-ttu-id="59f34-127">**すべてのユーザー、すべてのホスト**</span><span class="sxs-lookup"><span data-stu-id="59f34-127">**All users, All hosts**</span></span>         | `$PROFILE.AllUsersAllHosts`                      |

## <a name="to-create-a-new-profile"></a><span data-ttu-id="59f34-128">新しいプロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="59f34-128">To create a new profile</span></span>

<span data-ttu-id="59f34-129">"現在のユーザー、Windows PowerShell ISE" の新しいプロファイルを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="59f34-129">To create a new “Current user, Windows PowerShell ISE” profile, run this command:</span></span>

```powershell
if (!(Test-Path -Path $PROFILE ))
{ New-Item -Type File -Path $PROFILE -Force }
```

<span data-ttu-id="59f34-130">"すべてのユーザー、Windows PowerShell ISE" の新しいプロファイルを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="59f34-130">To create a new “All users, Windows PowerShell ISE” profile, run this command:</span></span>

```powershell
if (!(Test-Path -Path $PROFILE.AllUsersCurrentHost))
{ New-Item -Type File -Path $PROFILE.AllUsersCurrentHost -Force }
```

<span data-ttu-id="59f34-131">"現在のユーザー、すべてのホスト" の新しいプロファイルを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="59f34-131">To create a new “Current user, All Hosts” profile, run this command:</span></span>

```powershell
if (!(Test-Path -Path $PROFILE.CurrentUserAllHosts))
{ New-Item -Type File -Path $PROFILE.CurrentUserAllHosts -Force }
```

<span data-ttu-id="59f34-132">"すべてのユーザー、すべてのホスト" の新しいプロファイルを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="59f34-132">To create a new “All users, All Hosts” profile, type:</span></span>

```powershell
if (!(Test-Path -Path $PROFILE.AllUsersAllHosts))
{ New-Item -Type File -Path $PROFILE.AllUsersAllHosts -Force }
```

## <a name="to-edit-a-profile"></a><span data-ttu-id="59f34-133">プロファイルを編集するには</span><span class="sxs-lookup"><span data-stu-id="59f34-133">To edit a profile</span></span>

1. <span data-ttu-id="59f34-134">プロファイルを開くには、編集するプロファイルを設定した変数を指定してコマンド `psEdit` を実行します。</span><span class="sxs-lookup"><span data-stu-id="59f34-134">To open the profile, run the command `psEdit` with the variable that specifies the profile you want to edit.</span></span> <span data-ttu-id="59f34-135">たとえば、"現在のユーザー、Windows PowerShell ISE" のプロファイルを開くには、「`psEdit $PROFILE`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="59f34-135">For example, to open the “Current user, Windows PowerShell ISE” profile, type: `psEdit $PROFILE`</span></span>

2. <span data-ttu-id="59f34-136">プロファイルに、いくつかの項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="59f34-136">Add some items to your profile.</span></span> <span data-ttu-id="59f34-137">たとえば、次の例のように入力します。</span><span class="sxs-lookup"><span data-stu-id="59f34-137">The following are a few examples to get you started:</span></span>

   - <span data-ttu-id="59f34-138">コンソール ウィンドウの既定の背景色を青に変更するには、プロファイル ファイルに「`$psISE.Options.OutputPaneBackground = 'blue'`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="59f34-138">To change the default background color of the Console Pane to blue, in the profile file type: `$psISE.Options.OutputPaneBackground = 'blue'` .</span></span> <span data-ttu-id="59f34-139">`$psISE` 変数について詳しくは、「[Windows PowerShell ISE オブジェクト モデル リファレンス](object-model/The-ISE-Object-Model-Hierarchy.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="59f34-139">For more information about the `$psISE` variable, see [Windows PowerShell ISE Object Model Reference](object-model/The-ISE-Object-Model-Hierarchy.md).</span></span>

   - <span data-ttu-id="59f34-140">フォント サイズを 20 に変更するには、プロファイル ファイルに「`$psISE.Options.FontSize =20`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="59f34-140">To change font size to 20, in the profile file type: `$psISE.Options.FontSize =20`</span></span>

3. <span data-ttu-id="59f34-141">プロファイル ファイルを保存するには、 **[ファイル]** メニューの **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59f34-141">To save your profile file, on the **File** menu, click **Save**.</span></span> <span data-ttu-id="59f34-142">Windows PowerShell ISE を次に開いた時点で、カスタマイズの内容が適用されます。</span><span class="sxs-lookup"><span data-stu-id="59f34-142">Next time you open the Windows PowerShell ISE, your customizations are applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="59f34-143">参照</span><span class="sxs-lookup"><span data-stu-id="59f34-143">See Also</span></span>

- [<span data-ttu-id="59f34-144">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="59f34-144">about_Profiles</span></span>](/powershell/module/microsoft.powershell.core/about/about_profiles)
- [<span data-ttu-id="59f34-145">Windows PowerShell ISE の紹介</span><span class="sxs-lookup"><span data-stu-id="59f34-145">Introducing the Windows PowerShell ISE</span></span>](Introducing-the-Windows-PowerShell-ISE.md)
