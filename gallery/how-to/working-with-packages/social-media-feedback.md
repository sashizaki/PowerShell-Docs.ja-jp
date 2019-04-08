---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: ソーシャル メディアやコメントを使用したフィードバックの提供
ms.openlocfilehash: 95e5db22b94151c3974189c30f1d4e580b47eeb5
ms.sourcegitcommit: f268dce5b5e72be669be0c6634b8db11369bbae2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58623893"
---
# <a name="providing-feedback-via-social-media-or-comments"></a><span data-ttu-id="8cbed-103">ソーシャル メディアやコメントを使用したフィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="8cbed-103">Providing Feedback via social media or comments</span></span>

<span data-ttu-id="8cbed-104">PowerShell ギャラリーでは、ユーザーがパッケージへのパブリック フィードバックを提供する 2 つの方法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8cbed-104">The PowerShell Gallery supports two approaches for users to provide public feedback on a package:</span></span>

- <span data-ttu-id="8cbed-105">左端のリンクを使用して、Facebook、LinkedIn、Twitter などのソーシャル メディア サイト内でパッケージを "共有" する。</span><span class="sxs-lookup"><span data-stu-id="8cbed-105">Use the links on the left edge to "share" a package in Facebook, LinkedIn, or Twitter social media sites;</span></span>
- <span data-ttu-id="8cbed-106">コメント機能を使用してユーザーがパッケージへのコメントを投稿し、作成者は公開しているパッケージへのコメントを確認する。</span><span class="sxs-lookup"><span data-stu-id="8cbed-106">Use the Comment feature to post comments on a package, and to allow Authors to watch for comments on packages they publish.</span></span>

## <a name="social-media-feedback"></a><span data-ttu-id="8cbed-107">ソーシャル メディア フィードバック</span><span class="sxs-lookup"><span data-stu-id="8cbed-107">Social Media Feedback</span></span>

<span data-ttu-id="8cbed-108">PowerShell ギャラリー内にある各パッケージのページの左側には、Facebook、LinkedIn、Twitter のリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="8cbed-108">On the left side of the page for each package in the PowerShell Gallery there are links for Facebook, LinkedIn, and Twitter.</span></span>
<span data-ttu-id="8cbed-109">これらのリンクをクリックすることでソーシャル メディア サイトが開き、パッケージへのリンクをすぐに共有できます。</span><span class="sxs-lookup"><span data-stu-id="8cbed-109">Clicking on these links will open the social media site, and allow quickly sharing a link to the package.</span></span>

<span data-ttu-id="8cbed-110">ユーザーが PowerShell ギャラリーのパッケージを共有するには、選択したサイトにログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cbed-110">Users must log in to the site they have chosen in order to share the PowerShell Gallery package.</span></span>

<span data-ttu-id="8cbed-111">他のユーザーに勧めたいパッケージを見つけた場合も、こうすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8cbed-111">Users are encouraged to do this if they find that a package is something they would recommend to others.</span></span>
<span data-ttu-id="8cbed-112">PowerShell ギャラリーでは、パッケージの "共有" について各ソーシャル メディア サイトを確認し、各ソーシャル メディア サイト内でパッケージが共有された回数を表示します。</span><span class="sxs-lookup"><span data-stu-id="8cbed-112">The PowerShell Gallery will check each social media site for "shares" of the package, and display how many times that package has been shared in each of the social media sites.</span></span>
<span data-ttu-id="8cbed-113">これにより、パッケージが共有された回数のみが表示されるため、他のユーザーからは "いいね!" と評価されたパッケージであると解釈されます。</span><span class="sxs-lookup"><span data-stu-id="8cbed-113">Since this shows only the count of times something has been shared, it will be interpreted other users as "liking" the package.</span></span>

## <a name="comments"></a><span data-ttu-id="8cbed-114">備考</span><span class="sxs-lookup"><span data-stu-id="8cbed-114">Comments</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cbed-115">Livefyre コメント機能はサード パーティ ベンダーによって提供され、現在はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8cbed-115">Livefyre commenting is provided by a third-party vendor and is no longer supported.</span></span>
> <span data-ttu-id="8cbed-116">Livefyre コメント機能は、2019 年 5 月 1 日以降 PowerShell ギャラリーで利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8cbed-116">Livefyre commenting will no longer be available on the PowerShell Gallery starting 05/01/2019.</span></span> 

<span data-ttu-id="8cbed-117">PowerShell ギャラリーでは LiveFyre サービスを使用しており、ユーザーはパッケージに対するコメントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="8cbed-117">The PowerShell Gallery uses the LiveFyre service to allow users to comment on packages.</span></span>
<span data-ttu-id="8cbed-118">推奨したいものやフィードバックがあるユーザーはこの機能を使用することで、パッケージ ページにアクセスした人が見ることのできるフィードバックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="8cbed-118">Users who have recommendations or feedback can use this feature to provide feedback that is visible to anyone who visits the package page.</span></span>
<span data-ttu-id="8cbed-119">パッケージ所有者はこのフィードバックをフォローして、コメントが投稿されたときに通知されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="8cbed-119">Package owners can Follow this feedback, and be notified when someone posts a comment.</span></span>

<span data-ttu-id="8cbed-120">コメント システムは LiveFyre に基づいています。このサービスは、Microsoft が管理するものではない独自サービスのため、使用には別途ログインが必要になります。</span><span class="sxs-lookup"><span data-stu-id="8cbed-120">The Comment system is based on LiveFyre, which is a separate service that is not managed by Microsoft, and requires unique login to use.</span></span>
<span data-ttu-id="8cbed-121">パッケージにコメントする、または自分のいずれかのパッケージへのコメントをフォローすることを選択する場合、初回時に LiveFyre アカウントを作成するためのダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cbed-121">The first time you choose to leave a comment or follow comments on one of your packages, you will be prompted to create a LiveFyre account.</span></span>

<span data-ttu-id="8cbed-122">LiveFyre アカウントを作成してログインすると、パッケージにフィードバックするコメントを作成できます。次に [Post comment...]\(コメントを投稿する\) をクリックします。コメントはすぐには表示されません。</span><span class="sxs-lookup"><span data-stu-id="8cbed-122">If you have created a LiveFyre account and logged in, you can craft a comment that provides feedback on the package, then click on "Post comment..." The comment will not be visible immediately.</span></span>
<span data-ttu-id="8cbed-123">ギャラリーのパッケージに関するコメントは PowerShell ギャラリーの管理者によって管理されており、すべての投稿はモデレーターによる確認の後に公開されて、他のユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cbed-123">Comments for gallery packages are moderated by the PowerShell Gallery administrators, and all posts are reviewed by the moderators before being published and visible to others.</span></span>
<span data-ttu-id="8cbed-124">コメントを管理する目的は、コメントの内容が、PowerShell ギャラリーの[使用条件](https://www.powershellgallery.com/policies/Terms)に準拠した公的な振る舞いになっているかを確認するためです。</span><span class="sxs-lookup"><span data-stu-id="8cbed-124">Our purpose in moderating the comments is to ensure that they align with public behavior consistent with the PowerShell Gallery [Terms of Use](https://www.powershellgallery.com/policies/Terms).</span></span>

<span data-ttu-id="8cbed-125">パッケージ所有者は LiveFyre に投稿されたコメントをフォローすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8cbed-125">Package owners are encouraged to Follow comments that are posted to LiveFyre.</span></span>
<span data-ttu-id="8cbed-126">LiveFyre アカウントが必要です。LiveFyre でパッケージを公開する際に用いる電子メール アドレスと同じものを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8cbed-126">A LiveFyre account is required, and it is recommended to use the same email address you use for publishing your package in LiveFyre.</span></span>
<span data-ttu-id="8cbed-127">コメントをフォローするには、LiveFyre にログインし、所有者としてリストされているパッケージのいずれかに移動します。</span><span class="sxs-lookup"><span data-stu-id="8cbed-127">To Follow comments, log into LiveFyre, and navigate to any package where you are listed as an Owner.</span></span>
<span data-ttu-id="8cbed-128">各パッケージの下部にある [コメント] ボックスの下に、[+Follow]\(+フォロー\) と表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cbed-128">Below the Comment box at the bottom of each package you will see "+Follow".</span></span>
<span data-ttu-id="8cbed-129">これをクリックすると、パッケージに新しいコメントが作成されるたびに、登録されている電子メール アドレスに LiveFyre から電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="8cbed-129">Once you click on this, LiveFyre will send an email to the registered email address any time new comments made on the package.</span></span>
