---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: アイテムの所有者を管理する
ms.openlocfilehash: 10d2a433253162847028e157b5bac47b23406469
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34222109"
---
# <a name="managing-item-owners"></a><span data-ttu-id="37624-103">アイテムの所有者を管理する</span><span class="sxs-lookup"><span data-stu-id="37624-103">Managing item owners</span></span>

<span data-ttu-id="37624-104">PowerShell ギャラリーのアイテムの所有権は、そのアイテムをギャラリーに公開した人により定義されます。</span><span class="sxs-lookup"><span data-stu-id="37624-104">Ownership of an item in the PowerShell Gallery is defined by who published the item to the gallery.</span></span>
<span data-ttu-id="37624-105">このメタデータは最初のアイテム公開の範囲を超えて管理しなければならないことがあります。つまり、アイテム自体は変更不可でも、所有者メタデータは変更可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="37624-105">Sometimes this metadata needs to be managed beyond the initial item publishing, which means the owner metadata needs to be mutable while the item itself is not.</span></span>

<span data-ttu-id="37624-106">アイテムの所有者はすべて同等です。</span><span class="sxs-lookup"><span data-stu-id="37624-106">All item owners are peers.</span></span>
<span data-ttu-id="37624-107">つまり、すべてのアイテムの所有者はアイテムの新しいバージョンを公開できます。</span><span class="sxs-lookup"><span data-stu-id="37624-107">This means any item owner can publish a new version of an item.</span></span> <span data-ttu-id="37624-108">また、すべてのアイテムの所有者は他のアイテムの所有者を削除できます。</span><span class="sxs-lookup"><span data-stu-id="37624-108">It also means that any item owner can remove any other item owner.</span></span>
<span data-ttu-id="37624-109">ある所有者に他の所有者より大きな権限が与えられることはありません。</span><span class="sxs-lookup"><span data-stu-id="37624-109">No owner has more authority than other owners.</span></span>

## <a name="setting-an-items-initial-owner"></a><span data-ttu-id="37624-110">アイテムの最初の所有者を設定する</span><span class="sxs-lookup"><span data-stu-id="37624-110">Setting an Item's Initial Owner</span></span>

<span data-ttu-id="37624-111">PowerShell ギャラリーに新しいアイテムを公開すると、そのアイテムを公開したユーザーにより最初の所有者が定義されます。</span><span class="sxs-lookup"><span data-stu-id="37624-111">When a new item is published to PowerShell Gallery, the initial owner is defined by the user that published the item.</span></span> <span data-ttu-id="37624-112">Publish-Module コマンドレットで使用された API キーの所有者によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="37624-112">This is determined by whose API key was used in the Publish-Module cmdlet.</span></span>

## <a name="adding-owners"></a><span data-ttu-id="37624-113">所有者を追加する</span><span class="sxs-lookup"><span data-stu-id="37624-113">Adding Owners</span></span>

<span data-ttu-id="37624-114">PowerShell ギャラリーにアイテムを公開した後、アイテムの所有者になるように追加のユーザーを招待することは簡単です。</span><span class="sxs-lookup"><span data-stu-id="37624-114">Once an item has been published to the PowerShell Gallery, it's easy to invite additional users to become owners of an item.</span></span>

1. <span data-ttu-id="37624-115">アイテムの現在の所有者になっているアカウントで PowerShell ギャラリーに[ログオン](https://powershellgallery.com/users/account/LogOn)します。</span><span class="sxs-lookup"><span data-stu-id="37624-115">[Log on](https://powershellgallery.com/users/account/LogOn) to the PowerShell Gallery with the account that is the current owner of an item.</span></span>
2. <span data-ttu-id="37624-116">[アイテム] タブを使用し、ユーザーを検索するかクリックして、[**[Manage My Items]**](https://www.powershellgallery.com/account/Packages) \(マイ アイテムの管理) をクリックし、アイテム ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="37624-116">Navigate to an item page using the 'Items' tab, searching, or clicking your username and then [**Manage My Items**](https://www.powershellgallery.com/account/Packages).</span></span>
3. <span data-ttu-id="37624-117">アイテムの所有者としてログオンすると、'Manage Owners' (所有者の管理) リンクが左側に表示されるのでそれをクリックします。</span><span class="sxs-lookup"><span data-stu-id="37624-117">When logged on as an item's owner, there is a 'Manage Owners' link on the left side to click.</span></span>
4. <span data-ttu-id="37624-118">所有者として追加する人のユーザー名を入力し、[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37624-118">Enter the username of the person to add as an owner and click 'Add'.</span></span>
5. <span data-ttu-id="37624-119">アイテムの所有者になるための招待として、メールが新しい共同所有者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="37624-119">An email is then sent to the new co-owner, as an invitation to become an owner of an item.</span></span>
6. <span data-ttu-id="37624-120">そのユーザーがリンクをクリックすると、アイテムを完全にコントロールできる完全共同所有者になります。所有者となっている他のユーザーを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="37624-120">Once that user clicks the link, they are a full co-owner with full control over an item, including the ability to remove other users as owners.</span></span>

<span data-ttu-id="37624-121">**注**: 新しい所有者が所有権を確定するまで、アイテムの所有者リストに追加されることは*ありません*。</span><span class="sxs-lookup"><span data-stu-id="37624-121">**NOTE**: Until the new owner confirms ownership, they *will not* be listed as an owner of an item.</span></span>
<span data-ttu-id="37624-122">**[所有者の管理]** ページを表示すると、現在の所有者のところに "pending approval" (承認保留) と表示されます。</span><span class="sxs-lookup"><span data-stu-id="37624-122">When viewing the **Manage Owners** page, you will see a "pending approval" entry in the current owners.</span></span>
<span data-ttu-id="37624-123">他の所有者を削除できるように、その招待を削除できます。</span><span class="sxs-lookup"><span data-stu-id="37624-123">That invitation can be removed; just as other owners can be removed.</span></span>
<span data-ttu-id="37624-124">この招待プロセスにより、アイテムの所有者として他のユーザーが間違って追加されることがありません。</span><span class="sxs-lookup"><span data-stu-id="37624-124">This process of invitations prevents users from falsely adding other users as owners of their items.</span></span>

<span data-ttu-id="37624-125">"Authors" メタデータは完全に自由形式のテキストです。"Owners" だけがコントロールされます。</span><span class="sxs-lookup"><span data-stu-id="37624-125">Note that the "Authors" metadata is purely freeform text; only "Owners" are controlled.</span></span>


## <a name="removing-owners"></a><span data-ttu-id="37624-126">所有者を削除する</span><span class="sxs-lookup"><span data-stu-id="37624-126">Removing Owners</span></span>

<span data-ttu-id="37624-127">アイテムに複数の所有者が設定されているとき、そのうちの 1 名を削除するプロセスは単純です。</span><span class="sxs-lookup"><span data-stu-id="37624-127">When an item has multiple owners and one needs to be removed, the process is simple:</span></span>

1. <span data-ttu-id="37624-128">アイテムの現在の所有者になっているアカウントで PowerShell ギャラリーに[ログオン](https://powershellgallery.com/users/account/LogOn)します。</span><span class="sxs-lookup"><span data-stu-id="37624-128">[Log on](https://powershellgallery.com/users/account/LogOn) to PowerShell Gallery with the account that is the current owner of an item;</span></span>
2. <span data-ttu-id="37624-129">[アイテム] タブを使用し、検索し、ユーザー名、[**[Manage My Items]**](https://www.powershellgallery.com/account/Packages) \(マイ アイテムの管理) の順にクリックし、アイテム ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="37624-129">Navigate to an item page using the Items tab, searching, or clicking your username and then [**Manage My Items**](https://www.powershellgallery.com/account/Packages).</span></span>
3. <span data-ttu-id="37624-130">アイテムの所有者としてログオンすると、「Manage Owners」 (所有者の管理) リンクが左側に表示されるのでそれをクリックします。</span><span class="sxs-lookup"><span data-stu-id="37624-130">When logged on as an item's owner, there is a 'Manage Owners' link on the left side to click;</span></span>
4. <span data-ttu-id="37624-131">削除する所有者の隣にある [削除] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="37624-131">Click the 'remove' link next to the owner to be removed.</span></span>



## <a name="transferring-item-ownership"></a><span data-ttu-id="37624-132">アイテムの所有権を譲渡する</span><span class="sxs-lookup"><span data-stu-id="37624-132">Transferring Item Ownership</span></span>

<span data-ttu-id="37624-133">ユーザー間でアイテムの所有権を移転するように求めるサポートを依頼されることがありますが、ほとんどの場合、この操作は自分で実行できます。</span><span class="sxs-lookup"><span data-stu-id="37624-133">We sometimes get support requests to transfer item ownership from one user to another, but you can almost always accomplish this yourself.</span></span>
<span data-ttu-id="37624-134">ユーザー間での所有権の移転は、単純に上記の 2 つの機能の組み合わせとなります。</span><span class="sxs-lookup"><span data-stu-id="37624-134">Transferring ownership from one user to another is simply a combination of the two features above.</span></span>

1. <span data-ttu-id="37624-135">現在の所有者が新しいユーザーに共同所有者になるように求め、新しいユーザーがその招待を了承します。</span><span class="sxs-lookup"><span data-stu-id="37624-135">The current owner invites the new user to become a co-owner and the new user accepts the invite;</span></span>
2. <span data-ttu-id="37624-136">新しいユーザーが前のユーザーを所有者リストから削除します。</span><span class="sxs-lookup"><span data-stu-id="37624-136">The new user removes the old user from the list of owners.</span></span>

<span data-ttu-id="37624-137">この要求は次のような場合に発生しますが、プロセスは同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="37624-137">This request has come in under a couple forms but the process works the same.</span></span>

- <span data-ttu-id="37624-138">アイテムの所有権が開発者間で変更される</span><span class="sxs-lookup"><span data-stu-id="37624-138">The item ownership is changing from one developer to another</span></span>
- <span data-ttu-id="37624-139">アイテムが間違ったアカウントで公開された</span><span class="sxs-lookup"><span data-stu-id="37624-139">The item was accidentally published using the wrong account</span></span>


## <a name="orphaned-items"></a><span data-ttu-id="37624-140">孤立したアイテム</span><span class="sxs-lookup"><span data-stu-id="37624-140">Orphaned Items</span></span>

<span data-ttu-id="37624-141">最後になりますが、アイテムの孤立という状況があります。ただし、これは頻繁に発生しません。</span><span class="sxs-lookup"><span data-stu-id="37624-141">One last scenario has occurred, but not many times.</span></span>
<span data-ttu-id="37624-142">アイテムが孤立し、唯一のアイテムの所有者アカウントでは新しい所有者を追加できません。</span><span class="sxs-lookup"><span data-stu-id="37624-142">Items have become orphans and the only item owner account cannot be used to add new owners.</span></span>
<span data-ttu-id="37624-143">たとえば、次のような例があります。</span><span class="sxs-lookup"><span data-stu-id="37624-143">Here are some examples of this scenario:</span></span>

- <span data-ttu-id="37624-144">所有者のアカウントがメール アドレスに関連付けられているが、そのアドレスはもう存在しないか、パスワードを思い出せない</span><span class="sxs-lookup"><span data-stu-id="37624-144">The owner's account is associated with an email address that no longer exists and the user has forgotten their password</span></span>
- <span data-ttu-id="37624-145">登録されている所有者が (アイテムを製造する) 会社を辞めており、連絡がつかないのでアイテムの所有権を更新できない</span><span class="sxs-lookup"><span data-stu-id="37624-145">The registered owner has left the company that produces the item and cannot be reached to update the item ownership</span></span>
- <span data-ttu-id="37624-146">ごく一部のアイテムにだけ影響を与えるバグが原因で、アイテムがギャラリーで所有者なしになっている</span><span class="sxs-lookup"><span data-stu-id="37624-146">Due to a bug that has only affected a handful of items, the item is somehow ownerless on the gallery</span></span>

<span data-ttu-id="37624-147">PowerShell ギャラリーの管理者はあらゆるアイテムの 「Manage Owners」 (所有者の管理) リンクにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="37624-147">The PowerShell Gallery Administrators can access the 'Manage Owners' link for any item.</span></span>
<span data-ttu-id="37624-148">アイテムの正当な所有者が現在の所有者に連絡を取れないため、所有権を取得できない場合、ギャラリーの 「Report Abuse」 (不正報告) リンクを使用し、PowerShell ギャラリーの管理者に連絡します。</span><span class="sxs-lookup"><span data-stu-id="37624-148">If you are the rightful owner of a item and cannot reach the current owner to gain ownership permissions, then use the 'Report Abuse' link on the gallery to reach the PowerShell Gallery Administrators.</span></span>
<span data-ttu-id="37624-149">Microsoft がアイテムの所有権を確認するためのプロセスを進めます。</span><span class="sxs-lookup"><span data-stu-id="37624-149">We will then follow a process to verify your ownership of the item.</span></span>
<span data-ttu-id="37624-150">アイテムの所有者であることが確認された場合、アイテムの 「Manage Owners」 (所有者の管理) リンクを使用し、所有者になるための招待を送信します。</span><span class="sxs-lookup"><span data-stu-id="37624-150">If we determine you should be an owner of the item, we will use the 'Manage Owners' link for the item ourselves and send you the invite to become an owner.</span></span>
<span data-ttu-id="37624-151">この措置は所有者であることが確認された場合にのみ行われ、そのプロセスは状況によって変わります。</span><span class="sxs-lookup"><span data-stu-id="37624-151">We will only do this after verifying that you should be an owner and the process for this varies by circumstances.</span></span>
<span data-ttu-id="37624-152">多くの場合、Microsoft はアイテムのプロジェクト URL を利用し、プロジェクトの所有者に連絡を取る方法を模索します。Twitter、メール、その他の方法を利用することもあります。</span><span class="sxs-lookup"><span data-stu-id="37624-152">Often times, we will use the item's Project URL to find a way to contact the project owner, but we may also use Twitter, Email, or other means for contacting the project owner.</span></span>