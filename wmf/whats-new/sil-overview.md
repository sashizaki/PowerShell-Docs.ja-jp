---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
title: ソフトウェア インベントリ ログ (SIL)
ms.openlocfilehash: b12cfc4ae1e505bbc4d47596bed9352ce53a98f2
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855437"
---
# <a name="software-inventory-logging-sil"></a><span data-ttu-id="3fb5e-103">ソフトウェア インベントリ ログ (SIL)</span><span class="sxs-lookup"><span data-stu-id="3fb5e-103">Software Inventory Logging (SIL)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3fb5e-104">SIL を既に実行している Windows Server 2012 R2 サーバーに WMF 5.x をインストールする場合は、インストール プロセスでソフトウェア インベントリ ログ機能が誤って停止されるため、WMF をインストールした後に、Start-SilLogging コマンドレットを 1 回実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fb5e-104">When installing WMF 5.x on a Windows Server 2012 R2 Server that is already running SIL, it is necessary to run the Start-SilLogging cmdlet once after the WMF install, as the installation process will errantly stop the Software Inventory Logging feature.</span></span>

<span data-ttu-id="3fb5e-105">ソフトウェア インベントリ ログは、Microsoft ソフトウェアに関する正確な情報を取得するための運用コストの削減に役立ちます。この情報は、単一サーバー上にローカルにインストールされた以外のソフトウェアについても、IT 環境内の複数のサーバーをまたいで取得できます (ソフトウェアが IT 環境にインストールされ、実行されている場合)。</span><span class="sxs-lookup"><span data-stu-id="3fb5e-105">Software Inventory Logging helps reduce the operational costs of getting accurate information about the Microsoft software installed locally on a server, but especially across many servers in an IT environment (assuming the software is installed and running across the IT environment).</span></span> <span data-ttu-id="3fb5e-106">1 つを設定すると、集計サーバーにこのデータを転送し、均一な自動プロセスを使用して 1 か所にログ データを収集できます。</span><span class="sxs-lookup"><span data-stu-id="3fb5e-106">Provided one is set up, you can forward this data to an aggregation server, and collect the log data in one place by using a uniform, automatic process.</span></span>

<span data-ttu-id="3fb5e-107">各コンピューターを直接照会することでソフトウェア インベントリ データをログに記録することもできますが、ソフトウェア インベントリ ログでは、各サーバーによって起動される (ネットワーク経由での) 転送アーキテクチャを採用することによって、多数のソフトウェア インベントリおよび資産管理のシナリオで一般的なサーバー検出の課題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="3fb5e-107">While you can also log software inventory data by querying each computer directly, Software Inventory Logging, by employing a forwarding (over the network) architecture initiated by each server, can overcome server discovery challenges that are typical for many software inventory and asset management scenarios.</span></span> <span data-ttu-id="3fb5e-108">ソフトウェア インベントリ ログでは、SSL を使用して、HTTPS 経由で集計サーバーに転送されるデータをセキュリティ保護します。</span><span class="sxs-lookup"><span data-stu-id="3fb5e-108">Software Inventory Logging uses SSL to secure data that is forwarded over HTTPS to an aggregation server.</span></span> <span data-ttu-id="3fb5e-109">1 か所にデータを格納することで、必要に応じたデータの分析、操作、および共有がより簡単になります。</span><span class="sxs-lookup"><span data-stu-id="3fb5e-109">Storing the data in one place makes the data easier to analyze, manipulate, and share when necessary.</span></span>

<span data-ttu-id="3fb5e-110">この機能の一部として、データが Microsoft に送信されることはありません。</span><span class="sxs-lookup"><span data-stu-id="3fb5e-110">None of this data is sent to Microsoft as part of the feature functionality.</span></span> <span data-ttu-id="3fb5e-111">ソフトウェア インベントリ ログのデータおよび機能は、サーバー ソフトウェアのライセンスされた所有者および管理者のみの使用が意図されています。</span><span class="sxs-lookup"><span data-stu-id="3fb5e-111">Software Inventory Logging data and functionality is meant for the sole use of the server software’s licensed owner and administrators.</span></span>

<span data-ttu-id="3fb5e-112">ソフトウェア インベントリ ログ コマンドレットの詳細およびドキュメントについては、「[Manage Software Inventory Logging in Windows Server 2012 R2](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383584(v=ws.11))」(Windows Server 2012 R2 でのソフトウェア インベントリ ログの管理) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fb5e-112">For more information and documentation about Software Inventory Logging cmdlets, see [Manage Software Inventory Logging in Windows Server 2012 R2](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383584(v=ws.11)).</span></span>
