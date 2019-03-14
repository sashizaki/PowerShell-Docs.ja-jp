---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 7e87ed4bc9a86be52d4d06d3e87386a1111227c5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "55681631"
---
# <a name="software-inventory-logging-sil"></a><span data-ttu-id="d33ca-102">ソフトウェア インベントリ ログ (SIL)</span><span class="sxs-lookup"><span data-stu-id="d33ca-102">Software Inventory Logging (SIL)</span></span>

<span data-ttu-id="d33ca-103">**重要:** *SIL を既に実行している Windows Server 2012 R2 サーバーに WMF 5.0 をインストールする場合は、インストール プロセスでソフトウェア インベントリ ログ機能が誤って停止されるため、WMF をインストールした後に、Start-SilLogging コマンドレットを 1 回実行する必要があります。*</span><span class="sxs-lookup"><span data-stu-id="d33ca-103">**IMPORTANT:** *When installing WMF 5.0 on a Windows Server 2012 R2 Server that is already running SIL, it is necessary to run the Start-SilLogging cmdlet once after the WMF install, as the installation process will errantly stop the Software Inventory Logging feature.*</span></span>

<span data-ttu-id="d33ca-104">ソフトウェア インベントリ ログは、Microsoft ソフトウェアに関する正確な情報を取得するための運用コストの削減に役立ちます。この情報は、単一サーバー上にローカルにインストールされた以外のソフトウェアについても、IT 環境内の複数のサーバーをまたいで取得できます (ソフトウェアが IT 環境にインストールされ、実行されている場合)。</span><span class="sxs-lookup"><span data-stu-id="d33ca-104">Software Inventory Logging helps reduce the operational costs of getting accurate information about the Microsoft software installed locally on a server, but especially across many servers in an IT environment (assuming the software is installed and running across the IT environment).</span></span> <span data-ttu-id="d33ca-105">1 つを設定すると、集計サーバーにこのデータを転送し、均一な自動プロセスを使用して 1 か所にログ データを収集できます。</span><span class="sxs-lookup"><span data-stu-id="d33ca-105">Provided one is set up, you can forward this data to an aggregation server, and collect the log data in one place by using a uniform, automatic process.</span></span>

<span data-ttu-id="d33ca-106">各コンピューターを直接照会することでソフトウェア インベントリ データをログに記録することもできますが、ソフトウェア インベントリ ログでは、各サーバーによって起動される (ネットワーク経由での) 転送アーキテクチャを採用することによって、多数のソフトウェア インベントリおよび資産管理のシナリオで一般的なサーバー検出の課題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="d33ca-106">While you can also log software inventory data by querying each computer directly, Software Inventory Logging, by employing a forwarding (over the network) architecture initiated by each server, can overcome server discovery challenges that are typical for many software inventory and asset management scenarios.</span></span> <span data-ttu-id="d33ca-107">ソフトウェア インベントリ ログでは、SSL を使用して、HTTPS 経由で集計サーバーに転送されるデータをセキュリティ保護します。</span><span class="sxs-lookup"><span data-stu-id="d33ca-107">Software Inventory Logging uses SSL to secure data that is forwarded over HTTPS to an aggregation server.</span></span> <span data-ttu-id="d33ca-108">1 か所にデータを格納することで、必要に応じたデータの分析、操作、および共有がより簡単になります。</span><span class="sxs-lookup"><span data-stu-id="d33ca-108">Storing the data in one place makes the data easier to analyze, manipulate, and share when necessary.</span></span>

<span data-ttu-id="d33ca-109">この機能の一部として、データが Microsoft に送信されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d33ca-109">None of this data is sent to Microsoft as part of the feature functionality.</span></span> <span data-ttu-id="d33ca-110">ソフトウェア インベントリ ログのデータおよび機能は、サーバー ソフトウェアのライセンスされた所有者および管理者のみの使用が意図されています。</span><span class="sxs-lookup"><span data-stu-id="d33ca-110">Software Inventory Logging data and functionality is meant for the sole use of the server software’s licensed owner and administrators.</span></span>

<span data-ttu-id="d33ca-111">ソフトウェア インベントリ ログ コマンドレットの詳細およびドキュメントについては、Windows Server 2012 R2 のオンライン リソース (<http://technet.microsoft.com/library/dn383584.aspx>) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d33ca-111">For more information and documentation about Software Inventory Logging cmdlets, see Windows Server 2012 R2 online resources at <http://technet.microsoft.com/library/dn383584.aspx>.</span></span>
