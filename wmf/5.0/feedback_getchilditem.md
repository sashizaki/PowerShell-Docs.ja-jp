---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: d9f1ca10c948b06b234e17f688b8f899ed41c5d6
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="get-childitem-has--depth-parameter"></a><span data-ttu-id="93862-102">Get-ChildItem の -Depth パラメーター</span><span class="sxs-lookup"><span data-stu-id="93862-102">Get-ChildItem has -Depth parameter</span></span>
<span data-ttu-id="93862-103">**Get-ChildItem** に追加された **–Depth** パラメーターを **–Recurse** と一緒に使うと、再帰を制限できます。</span><span class="sxs-lookup"><span data-stu-id="93862-103">**Get-ChildItem** now has a **–Depth** parameter you use with **–Recurse** to limit the recursion:</span></span>

<span data-ttu-id="93862-104">PS C:\\Users\\slee\\Downloads\\Example&gt; Get-ChildItem -Recurse -Depth 0</span><span class="sxs-lookup"><span data-stu-id="93862-104">PS C:\\Users\\slee\\Downloads\\Example&gt; Get-ChildItem -Recurse -Depth 0</span></span>

<span data-ttu-id="93862-105">Directory: C:\\Users\\slee\\Downloads\\Example</span><span class="sxs-lookup"><span data-stu-id="93862-105">Directory: C:\\Users\\slee\\Downloads\\Example</span></span>

<span data-ttu-id="93862-106">Mode LastWriteTime Length Name</span><span class="sxs-lookup"><span data-stu-id="93862-106">Mode LastWriteTime Length Name</span></span>

---- ------------- ------ ----

<span data-ttu-id="93862-107">d----- 4/14/2015 5:36 PM Depth0</span><span class="sxs-lookup"><span data-stu-id="93862-107">d----- 4/14/2015 5:36 PM Depth0</span></span>

<span data-ttu-id="93862-108">-a---- 4/14/2015 1:19 PM 0 File1.txt</span><span class="sxs-lookup"><span data-stu-id="93862-108">-a---- 4/14/2015 1:19 PM 0 File1.txt</span></span>

<span data-ttu-id="93862-109">-a---- 4/14/2015 1:19 PM 0 File2.txt</span><span class="sxs-lookup"><span data-stu-id="93862-109">-a---- 4/14/2015 1:19 PM 0 File2.txt</span></span>

<span data-ttu-id="93862-110">-a---- 4/14/2015 1:19 PM 0 File3.txt</span><span class="sxs-lookup"><span data-stu-id="93862-110">-a---- 4/14/2015 1:19 PM 0 File3.txt</span></span>

<span data-ttu-id="93862-111">PS C:\\Users\\slee\\Downloads\\Example&gt; Get-ChildItem -Recurse -Depth 1</span><span class="sxs-lookup"><span data-stu-id="93862-111">PS C:\\Users\\slee\\Downloads\\Example&gt; Get-ChildItem -Recurse -Depth 1</span></span>

<span data-ttu-id="93862-112">Directory: C:\\Users\\slee\\Downloads\\Example</span><span class="sxs-lookup"><span data-stu-id="93862-112">Directory: C:\\Users\\slee\\Downloads\\Example</span></span>

<span data-ttu-id="93862-113">Mode LastWriteTime Length Name</span><span class="sxs-lookup"><span data-stu-id="93862-113">Mode LastWriteTime Length Name</span></span>

---- ------------- ------ ----

<span data-ttu-id="93862-114">d----- 4/14/2015 5:36 PM Depth0</span><span class="sxs-lookup"><span data-stu-id="93862-114">d----- 4/14/2015 5:36 PM Depth0</span></span>

<span data-ttu-id="93862-115">-a---- 4/14/2015 1:19 PM 0 File1.txt</span><span class="sxs-lookup"><span data-stu-id="93862-115">-a---- 4/14/2015 1:19 PM 0 File1.txt</span></span>

<span data-ttu-id="93862-116">-a---- 4/14/2015 1:19 PM 0 File2.txt</span><span class="sxs-lookup"><span data-stu-id="93862-116">-a---- 4/14/2015 1:19 PM 0 File2.txt</span></span>

<span data-ttu-id="93862-117">-a---- 4/14/2015 1:19 PM 0 File3.txt</span><span class="sxs-lookup"><span data-stu-id="93862-117">-a---- 4/14/2015 1:19 PM 0 File3.txt</span></span>

<span data-ttu-id="93862-118">Directory: C:\\Users\\slee\\Downloads\\Example\\Depth0</span><span class="sxs-lookup"><span data-stu-id="93862-118">Directory: C:\\Users\\slee\\Downloads\\Example\\Depth0</span></span>

<span data-ttu-id="93862-119">Mode LastWriteTime Length Name</span><span class="sxs-lookup"><span data-stu-id="93862-119">Mode LastWriteTime Length Name</span></span>

---- ------------- ------ ----

<span data-ttu-id="93862-120">d----- 4/14/2015 5:33 PM Depth1</span><span class="sxs-lookup"><span data-stu-id="93862-120">d----- 4/14/2015 5:33 PM Depth1</span></span>
