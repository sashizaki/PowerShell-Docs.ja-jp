---
ms.date: 06/12/2017
title: パッケージをリストから外す
description: PowerShell ギャラリーでは、ユーザーがパッケージを完全に削除することはできません。 これにより、他のユーザーが既存のパッケージを活用しても、その依存性が壊されることがありません。
ms.openlocfilehash: 738167011f64b5174df3504c8e1d06146f4c7db5
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662422"
---
# <a name="unlisting-packages"></a><span data-ttu-id="4c00d-104">パッケージをリストから外す</span><span class="sxs-lookup"><span data-stu-id="4c00d-104">Unlisting Packages</span></span>

<span data-ttu-id="4c00d-105">**PowerShell ギャラリーからパッケージを削除するためのオプションが表示されません。**</span><span class="sxs-lookup"><span data-stu-id="4c00d-105">**Why is removing a package from PowerShell Gallery not exposed as an option?**</span></span>

<span data-ttu-id="4c00d-106">PowerShell ギャラリーでは、ユーザーがパッケージを完全に削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="4c00d-106">The PowerShell Gallery does not support users permanently deleting their packages.</span></span> <span data-ttu-id="4c00d-107">これにより、他のユーザーが既存のパッケージを活用しても、その依存性が壊されることがありません。</span><span class="sxs-lookup"><span data-stu-id="4c00d-107">This enables others to take dependencies on your packages without worrying about possible breaks in the future.</span></span>
<span data-ttu-id="4c00d-108">たとえば、Pester モジュールは Azure モジュールに依存しているとき、Azure モジュールをギャラリーから削除すると、Pester モジュールを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4c00d-108">For example, if the Pester module depends on the Azure module and the Azure module is removed from the gallery, then users can no longer use the Pester module.</span></span>

<span data-ttu-id="4c00d-109">パッケージは、削除するのではなく、リストから外すことができます。</span><span class="sxs-lookup"><span data-stu-id="4c00d-109">Instead of removing a package you can unlist it.</span></span>

<span data-ttu-id="4c00d-110">**PowerShell ギャラリーのパッケージをリストから外すとは、どのような行為ですか。**</span><span class="sxs-lookup"><span data-stu-id="4c00d-110">**What does unlisting a package on PowerShell Gallery do?**</span></span>

<span data-ttu-id="4c00d-111">PowerShell ギャラリーでモジュールやスクリプトなどのパッケージをリストから外すと、そのパッケージは [パッケージ] タブから削除されます。また、リストから外されたパッケージは検索バーで検索できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4c00d-111">Unlisting a package such as a module or script in the PowerShell Gallery removes it from the Packages tab. In addition, unlisted packages will not be discoverable using the search bar.</span></span> <span data-ttu-id="4c00d-112">リストから外されたパッケージをダウンロードする唯一の方法は、パッケージの正確な名前とバージョンを指定することです。</span><span class="sxs-lookup"><span data-stu-id="4c00d-112">The only way to download an unlisted package is to specify the exact name and version of the package.</span></span> <span data-ttu-id="4c00d-113">以上のような理由から、パッケージをリストから外しても、そのパッケージに依存する他のモジュールやスクリプトがなくなることはありません。</span><span class="sxs-lookup"><span data-stu-id="4c00d-113">Because of this, the unlisting of a package will not break other modules or scripts that depend on it.</span></span>

<span data-ttu-id="4c00d-114">パッケージをリストから外すには、パッケージ詳細ページにアクセスし、[モジュールの削除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c00d-114">To unlist your package, visit the package details page and select 'Delete Module'.</span></span> <span data-ttu-id="4c00d-115">[リストしました] チェックボックスのチェックを外し、[保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c00d-115">Uncheck the 'Listed' checkbox, and select 'Save'.</span></span>

<span data-ttu-id="4c00d-116">**パッケージを削除する方法**</span><span class="sxs-lookup"><span data-stu-id="4c00d-116">**How can I remove a package?**</span></span>

<span data-ttu-id="4c00d-117">パッケージを削除しなければならない場合、PowerShell ギャラリーの管理者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="4c00d-117">If you experience a scenario where package deletion is necessary, contact the PowerShell Gallery Administrators.</span></span> <span data-ttu-id="4c00d-118">削除が必要になる場合:</span><span class="sxs-lookup"><span data-stu-id="4c00d-118">Valid deletion scenarios are:</span></span>

- <span data-ttu-id="4c00d-119">著作権侵害が問題になった。</span><span class="sxs-lookup"><span data-stu-id="4c00d-119">Issues of copyright infringement.</span></span>
- <span data-ttu-id="4c00d-120">パッケージに有害なコンテンツが含まれている。</span><span class="sxs-lookup"><span data-stu-id="4c00d-120">Package contains potentially harmful content.</span></span>
- <span data-ttu-id="4c00d-121">パッケージに機密データが含まれている。</span><span class="sxs-lookup"><span data-stu-id="4c00d-121">Package contains sensitive data.</span></span>

<span data-ttu-id="4c00d-122">PowerShell ギャラリーの管理者にパッケージの削除依頼を送信するには、パッケージ詳細ページにアクセスし、[Contact Support] \(サポートに問い合わせる) を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c00d-122">To submit a Delete Package Request to the PowerShell Gallery Administrators, visit your package's detail page and select Contact Support.</span></span>
