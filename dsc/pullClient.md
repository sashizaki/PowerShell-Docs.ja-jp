---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC プル クライアントのセットアップ
ms.openlocfilehash: 7f8758bd7145518e30e9c28b74d0db5d74dfaab3
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="setting-up-a-dsc-pull-client"></a><span data-ttu-id="7d441-103">DSC プル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="7d441-103">Setting up a DSC pull client</span></span>

> <span data-ttu-id="7d441-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="7d441-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d441-105">プル サーバー (Windows Feature *DSC-Service*) は、Windows Server のサポート対象のコンポーネントですが、新機能が提供される予定はありません。</span><span class="sxs-lookup"><span data-stu-id="7d441-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="7d441-106">管理対象のクライアントは、(Windows Server のプル サーバー以降の機能が含まれる) [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) または、[こちら](pullserver.md#community-solutions-for-pull-service)に列挙されているコミュニティ ソリューションのいずれかに切り替えを開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7d441-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="7d441-107">各ターゲット ノードに対し、プル モードを使用するように指示する必要があります。また、プル サーバーに接続して構成とリソースを取得し、レポート データの送信先にするための URL またはファイルの場所を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d441-107">Each target node has to be told to use pull mode and given the URL or file location where it can contact the pull server to get configurations and resources, and where it should send report data.</span></span>

<span data-ttu-id="7d441-108">次のトピックでは、プル クライアントをセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d441-108">The following topics explain how to set up pull clients:</span></span>

* [<span data-ttu-id="7d441-109">構成名を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="7d441-109">Setting up a pull client using configuration names</span></span>](pullClientConfigNames.md)
* [<span data-ttu-id="7d441-110">構成 ID を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="7d441-110">Setting up a pull client using configuration ID</span></span>](pullClientConfigID.md)

> <span data-ttu-id="7d441-111">**注**: これらのトピックは、PowerShell 5.0 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7d441-111">**Note**: These topics apply to PowerShell 5.0.</span></span> <span data-ttu-id="7d441-112">PowerShell 4.0 でのプル クライアントのセットアップについては、「[PowerShell 4.0 での構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID4.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d441-112">To set up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md).</span></span>