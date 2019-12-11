---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: パッケージの所有者を管理する
ms.openlocfilehash: 5cf26a7195ac446177cbb7f3a055e8e0a78569cc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71328263"
---
# <a name="managing-package-owners"></a><span data-ttu-id="4cac6-103">パッケージの所有者を管理する</span><span class="sxs-lookup"><span data-stu-id="4cac6-103">Managing package owners</span></span>

<span data-ttu-id="4cac6-104">PowerShell ギャラリーのパッケージの所有権は、そのパッケージをギャラリーに公開した人により定義されます。</span><span class="sxs-lookup"><span data-stu-id="4cac6-104">Ownership of a package in the PowerShell Gallery is defined by who published the package to the gallery.</span></span>
<span data-ttu-id="4cac6-105">このメタデータは最初のパッケージ公開の範囲を超えて管理しなければならないことがあります。つまり、パッケージ自体は変更不可でも、所有者メタデータは変更可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cac6-105">Sometimes this metadata needs to be managed beyond the initial package publishing, which means the owner metadata needs to be mutable while the package itself is not.</span></span>

<span data-ttu-id="4cac6-106">パッケージの所有者はすべて同等です。</span><span class="sxs-lookup"><span data-stu-id="4cac6-106">All package owners are peers.</span></span>
<span data-ttu-id="4cac6-107">つまり、すべてのパッケージの所有者はパッケージの新しいバージョンを公開できます。</span><span class="sxs-lookup"><span data-stu-id="4cac6-107">This means any package owner can publish a new version of an package.</span></span> <span data-ttu-id="4cac6-108">また、すべてのパッケージの所有者は他のパッケージの所有者を削除できます。</span><span class="sxs-lookup"><span data-stu-id="4cac6-108">It also means that any package owner can remove any other package owner.</span></span>
<span data-ttu-id="4cac6-109">ある所有者に他の所有者より大きな権限が与えられることはありません。</span><span class="sxs-lookup"><span data-stu-id="4cac6-109">No owner has more authority than other owners.</span></span>

## <a name="setting-a-packages-initial-owner"></a><span data-ttu-id="4cac6-110">パッケージの最初の所有者を設定する</span><span class="sxs-lookup"><span data-stu-id="4cac6-110">Setting a Package's Initial Owner</span></span>

<span data-ttu-id="4cac6-111">PowerShell ギャラリーに新しいパッケージを公開すると、そのパッケージを公開したユーザーにより最初の所有者が定義されます。</span><span class="sxs-lookup"><span data-stu-id="4cac6-111">When a new package is published to PowerShell Gallery, the initial owner is defined by the user that published the package.</span></span> <span data-ttu-id="4cac6-112">Publish-Module コマンドレットで使用された API キーの所有者によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="4cac6-112">This is determined by whose API key was used in the Publish-Module cmdlet.</span></span>

## <a name="adding-owners"></a><span data-ttu-id="4cac6-113">所有者を追加する</span><span class="sxs-lookup"><span data-stu-id="4cac6-113">Adding Owners</span></span>

<span data-ttu-id="4cac6-114">PowerShell ギャラリーにパッケージを公開した後、パッケージの所有者になるように追加のユーザーを招待することは簡単です。</span><span class="sxs-lookup"><span data-stu-id="4cac6-114">Once a package has been published to the PowerShell Gallery, it's easy to invite additional users to become owners of a package.</span></span>

1. <span data-ttu-id="4cac6-115">パッケージの現在の所有者になっているアカウントで PowerShell ギャラリーに[ログオン](https://powershellgallery.com/users/account/LogOn)します。</span><span class="sxs-lookup"><span data-stu-id="4cac6-115">[Log on](https://powershellgallery.com/users/account/LogOn) to the PowerShell Gallery with the account that is the current owner of a package.</span></span>
2. <span data-ttu-id="4cac6-116">[項目] タブを使用するか、ユーザー名を検索するかクリックしてパッケージ ページに移動し、[ **[Manage My Packages]** ](https://www.powershellgallery.com/account/Packages) \(マイ パッケージの管理) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cac6-116">Navigate to a package page using the 'Items' tab, searching, or clicking your username and then [**Manage My Packages**](https://www.powershellgallery.com/account/Packages).</span></span>
3. <span data-ttu-id="4cac6-117">パッケージの所有者としてログオンすると、'Manage Owners' (所有者の管理) リンクが左側に表示されるのでそれをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cac6-117">When logged on as an package's owner, there is a 'Manage Owners' link on the left side to click.</span></span>
4. <span data-ttu-id="4cac6-118">所有者として追加する人のユーザー名を入力し、[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cac6-118">Enter the username of the person to add as an owner and click 'Add'.</span></span>
5. <span data-ttu-id="4cac6-119">パッケージの所有者になるための招待として、メールが新しい共同所有者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="4cac6-119">An email is then sent to the new co-owner, as an invitation to become an owner of a package.</span></span>
6. <span data-ttu-id="4cac6-120">そのユーザーがリンクをクリックすると、パッケージを完全にコントロールできる完全共同所有者になります。所有者となっている他のユーザーを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="4cac6-120">Once that user clicks the link, they are a full co-owner with full control over a package, including the ability to remove other users as owners.</span></span>

<span data-ttu-id="4cac6-121">**注意**:新しい所有者が所有権を確定するまで、パッケージの所有者リストに追加されることは "*ありません*"。</span><span class="sxs-lookup"><span data-stu-id="4cac6-121">**NOTE**: Until the new owner confirms ownership, they *will not* be listed as an owner of a package.</span></span>
<span data-ttu-id="4cac6-122">**[所有者の管理]** ページを表示すると、現在の所有者のところに "pending approval" (承認保留) と表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cac6-122">When viewing the **Manage Owners** page, you will see a "pending approval" entry in the current owners.</span></span>
<span data-ttu-id="4cac6-123">他の所有者を削除できるように、その招待を削除できます。</span><span class="sxs-lookup"><span data-stu-id="4cac6-123">That invitation can be removed; just as other owners can be removed.</span></span>
<span data-ttu-id="4cac6-124">この招待プロセスにより、パッケージの所有者として他のユーザーが間違って追加されることがありません。</span><span class="sxs-lookup"><span data-stu-id="4cac6-124">This process of invitations prevents users from falsely adding other users as owners of their packages.</span></span>

<span data-ttu-id="4cac6-125">"Authors" メタデータは完全に自由形式のテキストです。"Owners" だけがコントロールされます。</span><span class="sxs-lookup"><span data-stu-id="4cac6-125">Note that the "Authors" metadata is purely freeform text; only "Owners" are controlled.</span></span>


## <a name="removing-owners"></a><span data-ttu-id="4cac6-126">所有者を削除する</span><span class="sxs-lookup"><span data-stu-id="4cac6-126">Removing Owners</span></span>

<span data-ttu-id="4cac6-127">パッケージに複数の所有者が設定されているとき、そのうちの 1 名を削除するプロセスは単純です。</span><span class="sxs-lookup"><span data-stu-id="4cac6-127">When a package has multiple owners and one needs to be removed, the process is simple:</span></span>

1. <span data-ttu-id="4cac6-128">パッケージの現在の所有者になっているアカウントで PowerShell ギャラリーに[ログオン](https://powershellgallery.com/users/account/LogOn)します。</span><span class="sxs-lookup"><span data-stu-id="4cac6-128">[Log on](https://powershellgallery.com/users/account/LogOn) to PowerShell Gallery with the account that is the current owner of a package;</span></span>
2. <span data-ttu-id="4cac6-129">[パッケージ] タブを使用するか、ユーザー名を検索するかクリックしてパッケージ ページに移動し、[ **[Manage My Packages]** ](https://www.powershellgallery.com/account/Packages) \(マイ パッケージの管理) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cac6-129">Navigate to a package page using the Packages tab, searching, or clicking your username and then [**Manage My Packages**](https://www.powershellgallery.com/account/Packages).</span></span>
3. <span data-ttu-id="4cac6-130">パッケージの所有者としてログオンすると、'Manage Owners' (所有者の管理) リンクが左側に表示されるのでそれをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cac6-130">When logged on as a package's owner, there is a 'Manage Owners' link on the left side to click;</span></span>
4. <span data-ttu-id="4cac6-131">削除する所有者の隣にある [削除] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cac6-131">Click the 'remove' link next to the owner to be removed.</span></span>



## <a name="transferring-package-ownership"></a><span data-ttu-id="4cac6-132">パッケージの所有権を譲渡する</span><span class="sxs-lookup"><span data-stu-id="4cac6-132">Transferring Package Ownership</span></span>

<span data-ttu-id="4cac6-133">ユーザー間でパッケージの所有権を移転するように求めるサポートを依頼されることがありますが、ほとんどの場合、この操作は自分で実行できます。</span><span class="sxs-lookup"><span data-stu-id="4cac6-133">We sometimes get support requests to transfer package ownership from one user to another, but you can almost always accomplish this yourself.</span></span>
<span data-ttu-id="4cac6-134">ユーザー間での所有権の移転は、単純に上記の 2 つの機能の組み合わせとなります。</span><span class="sxs-lookup"><span data-stu-id="4cac6-134">Transferring ownership from one user to another is simply a combination of the two features above.</span></span>

1. <span data-ttu-id="4cac6-135">現在の所有者が新しいユーザーに共同所有者になるように求め、新しいユーザーがその招待を了承します。</span><span class="sxs-lookup"><span data-stu-id="4cac6-135">The current owner invites the new user to become a co-owner and the new user accepts the invite;</span></span>
2. <span data-ttu-id="4cac6-136">新しいユーザーが前のユーザーを所有者リストから削除します。</span><span class="sxs-lookup"><span data-stu-id="4cac6-136">The new user removes the old user from the list of owners.</span></span>

<span data-ttu-id="4cac6-137">この要求は次のような場合に発生しますが、プロセスは同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="4cac6-137">This request has come in under a couple forms but the process works the same.</span></span>

- <span data-ttu-id="4cac6-138">パッケージの所有権が開発者間で変更される</span><span class="sxs-lookup"><span data-stu-id="4cac6-138">The package ownership is changing from one developer to another</span></span>
- <span data-ttu-id="4cac6-139">パッケージが間違ったアカウントで公開された</span><span class="sxs-lookup"><span data-stu-id="4cac6-139">The package was accidentally published using the wrong account</span></span>


## <a name="orphaned-packages"></a><span data-ttu-id="4cac6-140">孤立したパッケージ</span><span class="sxs-lookup"><span data-stu-id="4cac6-140">Orphaned Packages</span></span>

<span data-ttu-id="4cac6-141">最後になりますが、アイテムの孤立という状況があります。ただし、これは頻繁に発生しません。</span><span class="sxs-lookup"><span data-stu-id="4cac6-141">One last scenario has occurred, but not many times.</span></span>
<span data-ttu-id="4cac6-142">パッケージが孤立し、唯一のパッケージの所有者アカウントでは新しい所有者を追加できません。</span><span class="sxs-lookup"><span data-stu-id="4cac6-142">Packages have become orphans and the only package owner account cannot be used to add new owners.</span></span>
<span data-ttu-id="4cac6-143">たとえば、次のような例があります。</span><span class="sxs-lookup"><span data-stu-id="4cac6-143">Here are some examples of this scenario:</span></span>

- <span data-ttu-id="4cac6-144">所有者のアカウントがメール アドレスに関連付けられているが、そのアドレスはもう存在しないか、パスワードを思い出せない</span><span class="sxs-lookup"><span data-stu-id="4cac6-144">The owner's account is associated with an email address that no longer exists and the user has forgotten their password</span></span>
- <span data-ttu-id="4cac6-145">登録されている所有者が (パッケージを製造する) 会社を辞めており、連絡がつかないのでパッケージの所有権を更新できない</span><span class="sxs-lookup"><span data-stu-id="4cac6-145">The registered owner has left the company that produces the package and cannot be reached to update the package ownership</span></span>
- <span data-ttu-id="4cac6-146">ごく一部のパッケージにだけ影響を与えるバグが原因で、パッケージがギャラリーで所有者なしになっている</span><span class="sxs-lookup"><span data-stu-id="4cac6-146">Due to a bug that has only affected a handful of packages, the package is somehow ownerless on the gallery</span></span>

<span data-ttu-id="4cac6-147">PowerShell ギャラリーの管理者はあらゆるパッケージの 'Manage Owners' (所有者の管理) リンクにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4cac6-147">The PowerShell Gallery Administrators can access the 'Manage Owners' link for any package.</span></span>
<span data-ttu-id="4cac6-148">パッケージの正当な所有者が現在の所有者に連絡を取れないため、所有権を取得できない場合、ギャラリーの 'Report Abuse' (不正報告) リンクを使用し、PowerShell ギャラリーの管理者に連絡します。</span><span class="sxs-lookup"><span data-stu-id="4cac6-148">If you are the rightful owner of a package and cannot reach the current owner to gain ownership permissions, then use the 'Report Abuse' link on the gallery to reach the PowerShell Gallery Administrators.</span></span>
<span data-ttu-id="4cac6-149">Microsoft がパッケージの所有権を確認するためのプロセスを進めます。</span><span class="sxs-lookup"><span data-stu-id="4cac6-149">We will then follow a process to verify your ownership of the package.</span></span>
<span data-ttu-id="4cac6-150">パッケージの所有者であることが確認された場合、パッケージの 'Manage Owners' (所有者の管理) リンクを使用し、所有者になるための招待を送信します。</span><span class="sxs-lookup"><span data-stu-id="4cac6-150">If we determine you should be an owner of the package, we will use the 'Manage Owners' link for the package ourselves and send you the invite to become an owner.</span></span>
<span data-ttu-id="4cac6-151">この措置は所有者であることが確認された場合にのみ行われ、そのプロセスは状況によって変わります。</span><span class="sxs-lookup"><span data-stu-id="4cac6-151">We will only do this after verifying that you should be an owner and the process for this varies by circumstances.</span></span>
<span data-ttu-id="4cac6-152">多くの場合、Microsoft はパッケージのプロジェクト URL を利用し、プロジェクトの所有者に連絡を取る方法を模索します。Twitter、メール、その他の方法を利用することもあります。</span><span class="sxs-lookup"><span data-stu-id="4cac6-152">Often times, we will use the package's Project URL to find a way to contact the project owner, but we may also use Twitter, Email, or other means for contacting the project owner.</span></span>
