---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: パッケージをリストから外す
ms.openlocfilehash: fb66fd23dae1d4640056a764c31426f61f56d910
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71328273"
---
# <a name="unlisting-packages"></a><span data-ttu-id="5d7b5-103">パッケージをリストから外す</span><span class="sxs-lookup"><span data-stu-id="5d7b5-103">Unlisting Packages</span></span>

<span data-ttu-id="5d7b5-104">**PowerShell ギャラリーからパッケージを削除するためのオプションが表示されません。**</span><span class="sxs-lookup"><span data-stu-id="5d7b5-104">**Why is removing a package from PowerShell Gallery not exposed as an option?**</span></span>

<span data-ttu-id="5d7b5-105">PowerShell ギャラリーでは、ユーザーがパッケージを完全に削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="5d7b5-105">The PowerShell Gallery does not support users permanently deleting their packages.</span></span>
<span data-ttu-id="5d7b5-106">これにより、他のユーザーが既存のパッケージを活用しても、その依存性が壊されることがありません。</span><span class="sxs-lookup"><span data-stu-id="5d7b5-106">This enables others to take dependencies on your packages without worrying about possible breaks in the future.</span></span>
<span data-ttu-id="5d7b5-107">たとえば、Pester モジュールは Azure モジュールに依存しているとき、Azure モジュールをギャラリーから削除すると、Pester モジュールを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5d7b5-107">For example, if the Pester module depends on the Azure module and the Azure module is removed from the gallery, then user can no longer uses the Pester module.</span></span>

<span data-ttu-id="5d7b5-108">そこで、パッケージを削除する代わりに、パッケージをリストから外します。</span><span class="sxs-lookup"><span data-stu-id="5d7b5-108">Instead of removing an package, however, you can unlist it instead.</span></span>

<span data-ttu-id="5d7b5-109">**PowerShell ギャラリーのパッケージをリストから外すとは、どのような行為ですか。**</span><span class="sxs-lookup"><span data-stu-id="5d7b5-109">**What does unlisting a package on PowerShell Gallery do?**</span></span>

<span data-ttu-id="5d7b5-110">PowerShell ギャラリーでモジュールやスクリプトなどのパッケージをリストから外すと、そのパッケージは [パッケージ] タブから削除されます。また、リストから外されたパッケージは検索バーで検索できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5d7b5-110">Unlisting a package such as module or script on PowerShell Gallery will remove it from the Packages tab. In addition, unlisted packages will not be discoverable using the search bar.</span></span>
<span data-ttu-id="5d7b5-111">リストから外されたパッケージをダウンロードする唯一の方法は、パッケージの正確な名前とバージョンを指定することです。</span><span class="sxs-lookup"><span data-stu-id="5d7b5-111">The only way to download an unlisted package is to specify the exact name and version of the package.</span></span>
<span data-ttu-id="5d7b5-112">以上のような理由から、パッケージをリストから外しても、そのパッケージに依存する他のモジュールやスクリプトがなくなることはありません。</span><span class="sxs-lookup"><span data-stu-id="5d7b5-112">Because of this, the unlisting of an package will not break other modules or scripts that depend on it.</span></span>

<span data-ttu-id="5d7b5-113">パッケージをリストから外すには、パッケージ詳細ページにアクセスし、[モジュールの削除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d7b5-113">To unlist your package, visit the package details page and select 'Delete Module'.</span></span> <span data-ttu-id="5d7b5-114">'Listed' (一覧に表示する) チェックボックスのチェックを外し、[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d7b5-114">Uncheck the 'Listed' checkbox, and click Save.</span></span>

<span data-ttu-id="5d7b5-115">**パッケージを削除する方法**</span><span class="sxs-lookup"><span data-stu-id="5d7b5-115">**How can I remove an package?**</span></span>

<span data-ttu-id="5d7b5-116">パッケージを削除しなければならない場合、PowerShell ギャラリーの管理者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5d7b5-116">If you experience a scenario where package deletion is necessary, contact the PowerShell Gallery Administrators.</span></span>
<span data-ttu-id="5d7b5-117">削除が必要になる場合:</span><span class="sxs-lookup"><span data-stu-id="5d7b5-117">Valid deletion scenarios are:</span></span>
- <span data-ttu-id="5d7b5-118">著作権侵害が問題になった。</span><span class="sxs-lookup"><span data-stu-id="5d7b5-118">Issues of copyright infringement.</span></span>
- <span data-ttu-id="5d7b5-119">パッケージに有害なコンテンツが含まれている。</span><span class="sxs-lookup"><span data-stu-id="5d7b5-119">Package contains potentially harmful content.</span></span>
- <span data-ttu-id="5d7b5-120">パッケージに機密データが含まれている。</span><span class="sxs-lookup"><span data-stu-id="5d7b5-120">Package contains sensitive data.</span></span>

<span data-ttu-id="5d7b5-121">PowerShell ギャラリーの管理者にパッケージの削除依頼を送信するには、パッケージ詳細ページにアクセスし、[Contact Support] \(サポートに問い合わせる) を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d7b5-121">To submit a Delete Package Request to the PowerShell Gallery Administrators, visit your package's detail page and select Contact Support.</span></span>
