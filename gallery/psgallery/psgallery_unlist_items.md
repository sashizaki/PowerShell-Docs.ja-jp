---
ms.date: 2017-06-12
contributor: JKeithB
ms.topic: conceptual
keywords: "ギャラリー, PowerShell, コマンドレット, PSGallery"
title: psgallery_unlist_items
ms.openlocfilehash: 8fa09c77e144f14bf0fd3493dff7650897100715
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="unlisting-items"></a><span data-ttu-id="7a45e-103">アイテムをリストから外す</span><span class="sxs-lookup"><span data-stu-id="7a45e-103">Unlisting items</span></span>

<span data-ttu-id="7a45e-104">**PowerShell ギャラリーからアイテムを削除するためのオプションが表示されません。**</span><span class="sxs-lookup"><span data-stu-id="7a45e-104">**Why is removing an item from PowerShell Gallery not exposed as an option?**</span></span>

<span data-ttu-id="7a45e-105">PowerShell ギャラリーでは、ユーザーがアイテムを完全削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="7a45e-105">The PowerShell Gallery does not support users permanently deleting their items.</span></span> <span data-ttu-id="7a45e-106">それにより、他のユーザーが既存のアイテムを活用しても、その依存性が壊されることがありません。</span><span class="sxs-lookup"><span data-stu-id="7a45e-106">This enables others to take dependencies on your items without worrying about possible breaks in the future.</span></span> <span data-ttu-id="7a45e-107">たとえば、Pester モジュールは Azure モジュールに依存しているとき、Azure モジュールをギャラリーから削除すると、Pester モジュールを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7a45e-107">For example, if the Pester module depends on the Azure module and the Azure module is removed from the gallery, then user can no longer uses the Pester module.</span></span>

<span data-ttu-id="7a45e-108">そこで、アイテムを削除する代わりに、アイテムをリストから外します。</span><span class="sxs-lookup"><span data-stu-id="7a45e-108">Instead of removing an item, however, you can unlist it instead.</span></span>

<span data-ttu-id="7a45e-109">**PowerShell ギャラリーのアイテムをリストから外すとは、どのような行為ですか。**</span><span class="sxs-lookup"><span data-stu-id="7a45e-109">**What does unlisting an item on PowerShell Gallery do?**</span></span>

<span data-ttu-id="7a45e-110">PowerShell ギャラリーでモジュールやスクリプトなどのアイテムをリストから外すと、そのアイテムは [アイテム] タブから削除されます。</span><span class="sxs-lookup"><span data-stu-id="7a45e-110">Unlisting an item such as module or script on PowerShell Gallery will remove it from the Items tab.</span></span>
<span data-ttu-id="7a45e-111">また、リストから外されたアイテムは検索バーで検索できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7a45e-111">In addition, unlisted items will not be discoverable using the search bar.</span></span>
<span data-ttu-id="7a45e-112">リストから外されたアイテムをダウンロードする唯一の方法は、アイテムの正確な名前とバージョンを指定することです。</span><span class="sxs-lookup"><span data-stu-id="7a45e-112">The only way to download an unlisted item is to specify the exact name and version of the item.</span></span>
<span data-ttu-id="7a45e-113">以上のような理由から、アイテムをリストから外しても、そのアイテムに依存する他のモジュールやスクリプトがなくなることはありません。</span><span class="sxs-lookup"><span data-stu-id="7a45e-113">Because of this, the unlisting of an item will not break other modules or scripts that depend on it.</span></span>

<span data-ttu-id="7a45e-114">アイテムをリストから外すには、アイテム詳細ページにアクセスし、'項目の削除' を選択します。</span><span class="sxs-lookup"><span data-stu-id="7a45e-114">To unlist your item, visit the item details page and select 'Delete Item'.</span></span> <span data-ttu-id="7a45e-115">'Listed' (一覧に表示する) チェックボックスのチェックを外し、[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a45e-115">Uncheck the 'Listed' checkbox, and click Save.</span></span>

<span data-ttu-id="7a45e-116">**アイテムを削除する方法**</span><span class="sxs-lookup"><span data-stu-id="7a45e-116">**How can I remove an item?**</span></span>

<span data-ttu-id="7a45e-117">アイテムを削除しなければならない場合、PowerShell ギャラリーの管理者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="7a45e-117">If you experience a scenario where item deletion is necessary, contact the PowerShell Gallery Administrators.</span></span>
<span data-ttu-id="7a45e-118">削除が必要になる場合:</span><span class="sxs-lookup"><span data-stu-id="7a45e-118">Valid deletion scenarios are:</span></span>
- <span data-ttu-id="7a45e-119">著作権侵害が問題になった。</span><span class="sxs-lookup"><span data-stu-id="7a45e-119">Issues of copyright infringement.</span></span>
- <span data-ttu-id="7a45e-120">アイテムに有害なコンテンツが含まれている。</span><span class="sxs-lookup"><span data-stu-id="7a45e-120">Item contains potentially harmful content.</span></span>
- <span data-ttu-id="7a45e-121">アイテムに機密データが含まれている。</span><span class="sxs-lookup"><span data-stu-id="7a45e-121">Item contains sensitive data.</span></span>

<span data-ttu-id="7a45e-122">PowerShell ギャラリーの管理者にアイテムの削除依頼を送信するには、アイテム詳細ページにアクセスし、[Contact Support] \(サポートに問い合わせる) を選択します。</span><span class="sxs-lookup"><span data-stu-id="7a45e-122">To submit a Delete Item Request to the PowerShell Gallery Administrators, visit your item's detail page and select Contact Support.</span></span>  


