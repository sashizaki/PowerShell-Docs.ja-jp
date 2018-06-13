---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: a6366e18b4b6478bfab89475bc6975e6491da9f7
ms.sourcegitcommit: 01d6985ed190a222e9da1da41596f524f607a5bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34482864"
---
# <a name="windows-management-framework-wmf-50-rtm-release-notes-overview"></a><span data-ttu-id="76235-102">Windows 管理フレームワーク (WMF) 5.0 RTM のリリース ノート概要</span><span class="sxs-lookup"><span data-stu-id="76235-102">Windows Management Framework (WMF) 5.0 RTM Release Notes Overview</span></span>

<span data-ttu-id="76235-103">**WMF 5.0 は、WMF 5.1 に優先されます。WMF 5.0 を所有するユーザーがサポートを受けるには、WMF 5.1 にアップグレードする必要があります。[WMF 5.1 のインストール指示](../5.1/install-configure.md)** に従ってください</span><span class="sxs-lookup"><span data-stu-id="76235-103">**WMF 5.0 is superceeded by WMF 5.1. Users with WMF 5.0 must upgrade to WMF 5.1 to receive support. Please follow the [installation intructions of WMF 5.1](../5.1/install-configure.md)**</span></span>

<span data-ttu-id="76235-104">Windows 管理フレームワーク (WMF) 5.0 RTM には、WMF 4.0 から更新された機能があります。</span><span class="sxs-lookup"><span data-stu-id="76235-104">Windows Management Framework (WMF) 5.0 RTM brings functionality that has been updated from WMF 4.0.</span></span> <span data-ttu-id="76235-105">WMF 5.0 RTM は **Windows Server 2012 R2**、**Windows Server 2012**、**Windows Server 2008 R2**、**Windows 8.1**、および **Windows 7 SP1** にのみインストールすることができ、次の機能の更新バージョンや導入が含まれています。</span><span class="sxs-lookup"><span data-stu-id="76235-105">WMF 5.0 RTM is available for installation only on **Windows Server 2012 R2**, **Windows Server 2012**, **Windows Server 2008 R2**, **Windows 8.1**, and **Windows 7 SP1** and contains updated versions or introduction of the following features:</span></span>

- <span data-ttu-id="76235-106">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="76235-106">Windows PowerShell</span></span>
- <span data-ttu-id="76235-107">Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="76235-107">Just Enough Administration (JEA)</span></span>
- <span data-ttu-id="76235-108">Windows PowerShell Desired State Configuration (DSC)</span><span class="sxs-lookup"><span data-stu-id="76235-108">Windows PowerShell Desired State Configuration (DSC)</span></span>
- <span data-ttu-id="76235-109">Windows PowerShell Integrated Scripting Environment (ISE)</span><span class="sxs-lookup"><span data-stu-id="76235-109">Windows PowerShell Integrated Scripting Environment (ISE)</span></span>
- <span data-ttu-id="76235-110">Windows PowerShell Web サービス (Management OData IIS 拡張機能)</span><span class="sxs-lookup"><span data-stu-id="76235-110">Windows PowerShell Web Services (Management OData IIS Extension)</span></span>
- <span data-ttu-id="76235-111">Windows リモート管理 (WinRM)</span><span class="sxs-lookup"><span data-stu-id="76235-111">Windows Remote Management (WinRM)</span></span>
- <span data-ttu-id="76235-112">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="76235-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="76235-113">[WMF 5.0 Production Preview](http://blogs.msdn.com/b/powershell/archive/2015/08/31/windows-management-framework-5-0-production-preview-is-now-available.aspx) は WMF 5.0 RTM に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="76235-113">WMF 5.0 RTM replaces the [WMF 5.0 Production Preview](http://blogs.msdn.com/b/powershell/archive/2015/08/31/windows-management-framework-5-0-production-preview-is-now-available.aspx).</span></span> <span data-ttu-id="76235-114">WMF 5.0 Production Preview をアンインストールせずに WMF 5.0 RTM をインストールできますが、WMF 5.0 RTM をインストールする前に WMF 5.0 Preview の他の古いリリースをすべてアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="76235-114">You can install WMF 5.0 RTM without uninstalling WMF 5.0 Production Preview, but you must uninstall all other older releases of WMF 5.0 previews before installing the WMF 5.0 RTM.</span></span>

<span data-ttu-id="76235-115">*注:* Windows 10 を実行している場合は、Windows 10 の 11 月の更新プログラム (バージョン 1511) に更新して、WMF 5.0 RTM で利用できる同じ機能セットを取得できます。</span><span class="sxs-lookup"><span data-stu-id="76235-115">*Note:* If you are running Windows 10, you can get the same set of functionality available in WMF 5.0 RTM by updating to the November update of Windows 10 (Version 1511).</span></span> <span data-ttu-id="76235-116">Windows 10 システムをまだ更新していない場合は、[スタート] ボタンを選択し、[設定] > [更新とセキュリティ] > [Windows Update] > [更新プログラムのチェック] を選択します。</span><span class="sxs-lookup"><span data-stu-id="76235-116">If you have not already updated your Windows 10 system, select the Start button, then select Settings > Update & security > Windows Update > Check for updates.</span></span>
