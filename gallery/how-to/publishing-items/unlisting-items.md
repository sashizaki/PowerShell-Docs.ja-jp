---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: アイテムをリストから外す
ms.openlocfilehash: 35dcd283ddace5aec62d692b0ede12ae0bada765
ms.sourcegitcommit: e9ad4d85fd7eb72fb5bc37f6ca3ae1282ae3c6d7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
---
# <a name="unlisting-items"></a><span data-ttu-id="a5453-103">アイテムをリストから外す</span><span class="sxs-lookup"><span data-stu-id="a5453-103">Unlisting items</span></span>

<span data-ttu-id="a5453-104">**PowerShell ギャラリーからアイテムを削除するためのオプションが表示されません。**</span><span class="sxs-lookup"><span data-stu-id="a5453-104">**Why is removing an item from PowerShell Gallery not exposed as an option?**</span></span>

<span data-ttu-id="a5453-105">PowerShell ギャラリーでは、ユーザーがアイテムを完全削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="a5453-105">The PowerShell Gallery does not support users permanently deleting their items.</span></span>
<span data-ttu-id="a5453-106">それにより、他のユーザーが既存のアイテムを活用しても、その依存性が壊されることがありません。</span><span class="sxs-lookup"><span data-stu-id="a5453-106">This enables others to take dependencies on your items without worrying about possible breaks in the future.</span></span>
<span data-ttu-id="a5453-107">たとえば、Pester モジュールは Azure モジュールに依存しているとき、Azure モジュールをギャラリーから削除すると、Pester モジュールを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a5453-107">For example, if the Pester module depends on the Azure module and the Azure module is removed from the gallery, then user can no longer uses the Pester module.</span></span>

<span data-ttu-id="a5453-108">そこで、アイテムを削除する代わりに、アイテムをリストから外します。</span><span class="sxs-lookup"><span data-stu-id="a5453-108">Instead of removing an item, however, you can unlist it instead.</span></span>

<span data-ttu-id="a5453-109">**PowerShell ギャラリーのアイテムをリストから外すとは、どのような行為ですか。**</span><span class="sxs-lookup"><span data-stu-id="a5453-109">**What does unlisting an item on PowerShell Gallery do?**</span></span>

<span data-ttu-id="a5453-110">PowerShell ギャラリーでモジュールやスクリプトなどのアイテムをリストから外すと、そのアイテムは [アイテム] タブから削除されます。また、リストから外されたアイテムは検索バーで検索できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a5453-110">Unlisting an item such as module or script on PowerShell Gallery will remove it from the Items tab. In addition, unlisted items will not be discoverable using the search bar.</span></span>
<span data-ttu-id="a5453-111">リストから外されたアイテムをダウンロードする唯一の方法は、アイテムの正確な名前とバージョンを指定することです。</span><span class="sxs-lookup"><span data-stu-id="a5453-111">The only way to download an unlisted item is to specify the exact name and version of the item.</span></span>
<span data-ttu-id="a5453-112">以上のような理由から、アイテムをリストから外しても、そのアイテムに依存する他のモジュールやスクリプトがなくなることはありません。</span><span class="sxs-lookup"><span data-stu-id="a5453-112">Because of this, the unlisting of an item will not break other modules or scripts that depend on it.</span></span>

<span data-ttu-id="a5453-113">アイテムをリストから外すには、アイテム詳細ページにアクセスし、'項目の削除' を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5453-113">To unlist your item, visit the item details page and select 'Delete Item'.</span></span> <span data-ttu-id="a5453-114">'Listed' (一覧に表示する) チェックボックスのチェックを外し、[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5453-114">Uncheck the 'Listed' checkbox, and click Save.</span></span>

<span data-ttu-id="a5453-115">**アイテムを削除する方法**</span><span class="sxs-lookup"><span data-stu-id="a5453-115">**How can I remove an item?**</span></span>

<span data-ttu-id="a5453-116">アイテムを削除しなければならない場合、PowerShell ギャラリーの管理者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="a5453-116">If you experience a scenario where item deletion is necessary, contact the PowerShell Gallery Administrators.</span></span>
<span data-ttu-id="a5453-117">削除が必要になる場合:</span><span class="sxs-lookup"><span data-stu-id="a5453-117">Valid deletion scenarios are:</span></span>
- <span data-ttu-id="a5453-118">著作権侵害が問題になった。</span><span class="sxs-lookup"><span data-stu-id="a5453-118">Issues of copyright infringement.</span></span>
- <span data-ttu-id="a5453-119">アイテムに有害なコンテンツが含まれている。</span><span class="sxs-lookup"><span data-stu-id="a5453-119">Item contains potentially harmful content.</span></span>
- <span data-ttu-id="a5453-120">アイテムに機密データが含まれている。</span><span class="sxs-lookup"><span data-stu-id="a5453-120">Item contains sensitive data.</span></span>

<span data-ttu-id="a5453-121">PowerShell ギャラリーの管理者にアイテムの削除依頼を送信するには、アイテム詳細ページにアクセスし、[Contact Support] \(サポートに問い合わせる) を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5453-121">To submit a Delete Item Request to the PowerShell Gallery Administrators, visit your item's detail page and select Contact Support.</span></span>