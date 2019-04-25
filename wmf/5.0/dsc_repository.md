---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: cc859d68491c817d641cc598513efb3208db0619
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085390"
---
# <a name="separation-of-configuration-resource-and-report-repositories"></a><span data-ttu-id="068c0-102">構成、リソース、およびレポートのリポジトリの分離</span><span class="sxs-lookup"><span data-stu-id="068c0-102">Separation of Configuration, Resource and Report Repositories</span></span>

<span data-ttu-id="068c0-103">今回のリリースでは、1 つ以上の DSC プル サーバーに対してプルおよびレポートするために必要な十分の柔軟性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="068c0-103">In this release we allow you all of the flexibility that you need to pull and report to one or more DSC Pull Servers.</span></span> <span data-ttu-id="068c0-104">各エンドポイントは別々に定義できるため、構成を 1 つの場所からプルし、リソースは別の場所からプルし、レポートはさらに別の場所に送るように定義できます。</span><span class="sxs-lookup"><span data-stu-id="068c0-104">Each endpoint can be defined separately so that you can pull configurations from one location, resources from another and report to yet another location.</span></span>

<span data-ttu-id="068c0-105">詳細については、「[構成 ID を使用したプル クライアントのセットアップ](https://msdn.microsoft.com/powershell/dsc/pullclientconfigid)」または「[構成名を使用したプル クライアントのセットアップ](https://msdn.microsoft.com/powershell/dsc/pullclientconfignames)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="068c0-105">For more information, see [Setting up a pull client using configuration ID](https://msdn.microsoft.com/powershell/dsc/pullclientconfigid) or [Setting up a pull client using configuration names](https://msdn.microsoft.com/powershell/dsc/pullclientconfignames)</span></span>
