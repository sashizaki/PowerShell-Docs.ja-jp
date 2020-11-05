---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSCAutomationHostEnabled レジストリ キー
description: この記事では、DSCAutomationHostEnabled レジストリ キーで設定できる値を定義します
ms.openlocfilehash: 50f752dd882e9b0787ed4a4cbc22731fc1d608f5
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656181"
---
# <a name="dscautomationhostenabled-registry-key"></a><span data-ttu-id="3170a-104">DSCAutomationHostEnabled レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="3170a-104">DSCAutomationHostEnabled registry key</span></span>

> <span data-ttu-id="3170a-105">適用対象:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="3170a-105">Applies to: Windows PowerShell 5.0</span></span>

<span data-ttu-id="3170a-106">DSC は、 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** の下の **DSCAutomationHostEnabled** というレジストリ キーを使用してコンピューターの起動時の構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3170a-106">DSC uses the **DSCAutomationHostEnabled** registry key under **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** to enable configuration of the machine at initial boot-up.</span></span> <span data-ttu-id="3170a-107">**DSCAutomationHostEnabled** は 3 つのモードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3170a-107">**DSCAutomationHostEnabled** supports three modes:</span></span>

| <span data-ttu-id="3170a-108">DSCAutomationHostEnabled の値</span><span class="sxs-lookup"><span data-stu-id="3170a-108">DSCAutomationHostEnabled Value</span></span> |                                              <span data-ttu-id="3170a-109">説明</span><span class="sxs-lookup"><span data-stu-id="3170a-109">Description</span></span>                                              |
| ------------------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="3170a-110">0</span><span class="sxs-lookup"><span data-stu-id="3170a-110">0</span></span>                              | <span data-ttu-id="3170a-111">起動時にコンピューターの構成を行いません。</span><span class="sxs-lookup"><span data-stu-id="3170a-111">Disable configuring the machine at boot-up.</span></span>                                                           |
| <span data-ttu-id="3170a-112">1</span><span class="sxs-lookup"><span data-stu-id="3170a-112">1</span></span>                              | <span data-ttu-id="3170a-113">起動時にコンピューターの構成を行います。</span><span class="sxs-lookup"><span data-stu-id="3170a-113">Enable configuring the machine at boot-up.</span></span>                                                            |
| <span data-ttu-id="3170a-114">2</span><span class="sxs-lookup"><span data-stu-id="3170a-114">2</span></span>                              | <span data-ttu-id="3170a-115">コンピューターの構成は、DSC の状態が保留中または最新の場合にのみ行います。</span><span class="sxs-lookup"><span data-stu-id="3170a-115">Enable configuring the machine only if DSC is in pending or current state.</span></span> <span data-ttu-id="3170a-116">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="3170a-116">This is the default value.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3170a-117">参照</span><span class="sxs-lookup"><span data-stu-id="3170a-117">See Also</span></span>

<span data-ttu-id="3170a-118">この機能を使用して初回起動時に構成を実行する方法の例については、「[DSC を使用した初回起動時の仮想マシンの構成](bootstrapDsc.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3170a-118">For an example of how to use this feature to run configurations at initial boot-up, see [Configure a virtual machines at initial boot-up by using DSC](bootstrapDsc.md).</span></span>
