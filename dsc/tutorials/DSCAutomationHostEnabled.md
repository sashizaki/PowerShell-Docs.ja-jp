---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSCAutomationHostEnabled レジストリ キー
ms.openlocfilehash: 2bccd2738b9f61efd656fdf0f98cf71affdbe781
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076490"
---
><span data-ttu-id="25cfd-103">適用先:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="25cfd-103">Applies to: Windows PowerShell 5.0</span></span>

# <a name="dscautomationhostenabled-registry-key"></a><span data-ttu-id="25cfd-104">DSCAutomationHostEnabled レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="25cfd-104">DSCAutomationHostEnabled registry key</span></span>

<span data-ttu-id="25cfd-105">DSC は、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** の下の **DSCAutomationHostEnabled** というレジストリ キーを使用してコンピューターの起動時の構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="25cfd-105">DSC uses the **DSCAutomationHostEnabled** registry key under **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** to enable configuration of the machine at initial boot-up.</span></span>
<span data-ttu-id="25cfd-106">**DSCAutomationHostEnabled** は 3 つのモードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="25cfd-106">**DSCAutomationHostEnabled** supports three modes:</span></span>

|  <span data-ttu-id="25cfd-107">DSCAutomationHostEnabled の値</span><span class="sxs-lookup"><span data-stu-id="25cfd-107">DSCAutomationHostEnabled Value</span></span>  |  <span data-ttu-id="25cfd-108">説明</span><span class="sxs-lookup"><span data-stu-id="25cfd-108">Description</span></span>   |
|---|---|
<span data-ttu-id="25cfd-109">0</span><span class="sxs-lookup"><span data-stu-id="25cfd-109">0</span></span> | <span data-ttu-id="25cfd-110">起動時にコンピューターの構成を行いません。</span><span class="sxs-lookup"><span data-stu-id="25cfd-110">Disable configuring the machine at boot-up.</span></span> |
<span data-ttu-id="25cfd-111">1 で保護されたプロセスとして起動されました</span><span class="sxs-lookup"><span data-stu-id="25cfd-111">1</span></span> | <span data-ttu-id="25cfd-112">起動時にコンピューターの構成を行います。</span><span class="sxs-lookup"><span data-stu-id="25cfd-112">Enable configuring the machine at boot-up.</span></span> |
<span data-ttu-id="25cfd-113">2</span><span class="sxs-lookup"><span data-stu-id="25cfd-113">2</span></span> | <span data-ttu-id="25cfd-114">コンピューターの構成は、DSC の状態が保留中または最新の場合にのみ行います。</span><span class="sxs-lookup"><span data-stu-id="25cfd-114">Enable configuring the machine only if DSC is in pending or current state.</span></span> <span data-ttu-id="25cfd-115">これは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="25cfd-115">This is the default value.</span></span> |

## <a name="see-also"></a><span data-ttu-id="25cfd-116">参照</span><span class="sxs-lookup"><span data-stu-id="25cfd-116">See Also</span></span>

<span data-ttu-id="25cfd-117">この機能を使用して初回起動時に構成を実行する方法の例については、「[DSC を使用した初回起動時の仮想マシンの構成](bootstrapDsc.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="25cfd-117">For an example of how to use this feature to run configurations at initial boot-up, see [Configure a virtual machines at initial boot-up by using DSC](bootstrapDsc.md).</span></span>
