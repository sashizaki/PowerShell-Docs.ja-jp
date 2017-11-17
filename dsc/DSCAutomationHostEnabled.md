---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSCAutomationHostEnabled レジストリ キー"
ms.openlocfilehash: e47c929b366f93738343eabc431aab5a4428352d
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
><span data-ttu-id="56779-103">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="56779-103">Applies to: Windows PowerShell 5.0</span></span>

# <a name="dscautomationhostenabled-registry-key"></a><span data-ttu-id="56779-104">DSCAutomationHostEnabled レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="56779-104">DSCAutomationHostEnabled registry key</span></span>

<span data-ttu-id="56779-105">DSC は、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies** の下の **DSCAutomationHostEnabled** というレジストリ キーを使用してコンピューターの起動時の構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="56779-105">DSC uses the **DSCAutomationHostEnabled** registry key under **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies** to enable configuration of the machine at initial boot-up.</span></span>
<span data-ttu-id="56779-106">DSCAutomationHostEnabled では、次の 3 つのモードがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="56779-106">DSCAutomationHostEnabled supports three modes:</span></span>

|  <span data-ttu-id="56779-107">DSCAutomationHostEnabled の値</span><span class="sxs-lookup"><span data-stu-id="56779-107">DSCAutomationHostEnabled Value</span></span>  |  <span data-ttu-id="56779-108">説明</span><span class="sxs-lookup"><span data-stu-id="56779-108">Description</span></span>   | 
|---|---| 
<span data-ttu-id="56779-109">0</span><span class="sxs-lookup"><span data-stu-id="56779-109">0</span></span> | <span data-ttu-id="56779-110">起動時にコンピューターの構成を行いません。</span><span class="sxs-lookup"><span data-stu-id="56779-110">Disable configuring the machine at boot-up.</span></span> |
<span data-ttu-id="56779-111">1 で保護されたプロセスとして起動されました</span><span class="sxs-lookup"><span data-stu-id="56779-111">1</span></span> | <span data-ttu-id="56779-112">起動時にコンピューターの構成を行います。</span><span class="sxs-lookup"><span data-stu-id="56779-112">Enable configuring the machine at boot-up.</span></span> |
<span data-ttu-id="56779-113">2</span><span class="sxs-lookup"><span data-stu-id="56779-113">2</span></span> | <span data-ttu-id="56779-114">コンピューターの構成は、DSC の状態が保留中または最新の場合にのみ行います。</span><span class="sxs-lookup"><span data-stu-id="56779-114">Enable configuring the machine only if DSC is in pending or current state.</span></span> <span data-ttu-id="56779-115">これは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="56779-115">This is the default value.</span></span> |

## <a name="see-also"></a><span data-ttu-id="56779-116">参照</span><span class="sxs-lookup"><span data-stu-id="56779-116">See Also</span></span>

<span data-ttu-id="56779-117">この機能を使用して初回起動時に構成を実行する方法の例については、「[DSC を使用した初回起動時の仮想マシンの構成](bootstrapDsc.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="56779-117">For an example of how to use this feature to run configurations at initial boot-up, see [Configure a virtual machines at initial boot-up by using DSC](bootstrapDsc.md).</span></span>


