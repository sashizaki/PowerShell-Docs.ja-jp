---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 62cccabd7c63c6ba928fc2bf8addd3d11483e90f
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="get-childitem-has--depth-parameter"></a><span data-ttu-id="ea104-102">Get-ChildItem の -Depth パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea104-102">Get-ChildItem has -Depth parameter</span></span>
<span data-ttu-id="ea104-103">**Get-ChildItem** に追加された **–Depth** パラメーターを **–Recurse** と一緒に使うと、再帰を制限できます。</span><span class="sxs-lookup"><span data-stu-id="ea104-103">**Get-ChildItem** now has a **–Depth** parameter you use with **–Recurse** to limit the recursion:</span></span>

<span data-ttu-id="ea104-104">PS C:\\Users\\slee\\Downloads\\Example&gt; Get-ChildItem -Recurse -Depth 0</span><span class="sxs-lookup"><span data-stu-id="ea104-104">PS C:\\Users\\slee\\Downloads\\Example&gt; Get-ChildItem -Recurse -Depth 0</span></span>

<span data-ttu-id="ea104-105">Directory: C:\\Users\\slee\\Downloads\\Example</span><span class="sxs-lookup"><span data-stu-id="ea104-105">Directory: C:\\Users\\slee\\Downloads\\Example</span></span>

<span data-ttu-id="ea104-106">Mode LastWriteTime Length Name</span><span class="sxs-lookup"><span data-stu-id="ea104-106">Mode LastWriteTime Length Name</span></span>

---- ------------- ------ ----

<span data-ttu-id="ea104-107">d----- 4/14/2015 5:36 PM Depth0</span><span class="sxs-lookup"><span data-stu-id="ea104-107">d----- 4/14/2015 5:36 PM Depth0</span></span>

<span data-ttu-id="ea104-108">-a---- 4/14/2015 1:19 PM 0 File1.txt</span><span class="sxs-lookup"><span data-stu-id="ea104-108">-a---- 4/14/2015 1:19 PM 0 File1.txt</span></span>

<span data-ttu-id="ea104-109">-a---- 4/14/2015 1:19 PM 0 File2.txt</span><span class="sxs-lookup"><span data-stu-id="ea104-109">-a---- 4/14/2015 1:19 PM 0 File2.txt</span></span>

<span data-ttu-id="ea104-110">-a---- 4/14/2015 1:19 PM 0 File3.txt</span><span class="sxs-lookup"><span data-stu-id="ea104-110">-a---- 4/14/2015 1:19 PM 0 File3.txt</span></span>

<span data-ttu-id="ea104-111">PS C:\\Users\\slee\\Downloads\\Example&gt; Get-ChildItem -Recurse -Depth 1</span><span class="sxs-lookup"><span data-stu-id="ea104-111">PS C:\\Users\\slee\\Downloads\\Example&gt; Get-ChildItem -Recurse -Depth 1</span></span>

<span data-ttu-id="ea104-112">Directory: C:\\Users\\slee\\Downloads\\Example</span><span class="sxs-lookup"><span data-stu-id="ea104-112">Directory: C:\\Users\\slee\\Downloads\\Example</span></span>

<span data-ttu-id="ea104-113">Mode LastWriteTime Length Name</span><span class="sxs-lookup"><span data-stu-id="ea104-113">Mode LastWriteTime Length Name</span></span>

---- ------------- ------ ----

<span data-ttu-id="ea104-114">d----- 4/14/2015 5:36 PM Depth0</span><span class="sxs-lookup"><span data-stu-id="ea104-114">d----- 4/14/2015 5:36 PM Depth0</span></span>

<span data-ttu-id="ea104-115">-a---- 4/14/2015 1:19 PM 0 File1.txt</span><span class="sxs-lookup"><span data-stu-id="ea104-115">-a---- 4/14/2015 1:19 PM 0 File1.txt</span></span>

<span data-ttu-id="ea104-116">-a---- 4/14/2015 1:19 PM 0 File2.txt</span><span class="sxs-lookup"><span data-stu-id="ea104-116">-a---- 4/14/2015 1:19 PM 0 File2.txt</span></span>

<span data-ttu-id="ea104-117">-a---- 4/14/2015 1:19 PM 0 File3.txt</span><span class="sxs-lookup"><span data-stu-id="ea104-117">-a---- 4/14/2015 1:19 PM 0 File3.txt</span></span>

<span data-ttu-id="ea104-118">Directory: C:\\Users\\slee\\Downloads\\Example\\Depth0</span><span class="sxs-lookup"><span data-stu-id="ea104-118">Directory: C:\\Users\\slee\\Downloads\\Example\\Depth0</span></span>

<span data-ttu-id="ea104-119">Mode LastWriteTime Length Name</span><span class="sxs-lookup"><span data-stu-id="ea104-119">Mode LastWriteTime Length Name</span></span>

---- ------------- ------ ----

<span data-ttu-id="ea104-120">d----- 4/14/2015 5:33 PM Depth1</span><span class="sxs-lookup"><span data-stu-id="ea104-120">d----- 4/14/2015 5:33 PM Depth1</span></span>