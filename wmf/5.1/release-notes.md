---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: WMF, PowerShell, セットアップ
title: WMF 5.1 リリース ノート
ms.openlocfilehash: 5c3075eda5482cc6a43bd237fe4fca0064136753
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34219438"
---
# <a name="windows-management-framework-wmf-51-release-notes"></a><span data-ttu-id="00fae-103">Windows Management Framework (WMF) 5.1 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="00fae-103">Windows Management Framework (WMF) 5.1 Release Notes</span></span> #

<span data-ttu-id="00fae-104">WMF 5.1 には、Windows Server 2016 でリリースされた PowerShell、WMI、WinRM、ソフトウェア インベントリ ログ (SIL) のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="00fae-104">WMF 5.1 includes the PowerShell, WMI, WinRM, and Software Inventory Logging (SIL) components that were released with Windows Server 2016.</span></span>
<span data-ttu-id="00fae-105">WMF 5.1 は、Windows 7、Windows 8.1、Windows Server 2008 R2、Windows Server 2012、および Windows Server 2012 R2 にインストールすることができ、WMF 5.0 RTM と比較すると次のような機能が強化されています。</span><span class="sxs-lookup"><span data-stu-id="00fae-105">WMF 5.1 can be installed on Windows 7, Windows 8.1, Windows Server 2008 R2, 2012, and 2012 R2, and provides a number of improvements over WMF 5.0 RTM including:</span></span>

- <span data-ttu-id="00fae-106">新しいコマンドレット: ローカル ユーザーとグループ、Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="00fae-106">New cmdlets: local users and groups; Get-ComputerInfo</span></span>
- <span data-ttu-id="00fae-107">PowerShellGet では、署名付きモジュールの適用や JEA モジュールのインストールなどの機能強化が行われています。</span><span class="sxs-lookup"><span data-stu-id="00fae-107">PowerShellGet improvements include enforcing signed modules, and installing JEA modules</span></span>
- <span data-ttu-id="00fae-108">PackageManagement では、コンテナー、CBS セットアップ、EXE ベースのセットアップ、CAB パッケージをサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="00fae-108">PackageManagement added support for Containers, CBS Setup, EXE-based setup, CAB packages</span></span>
- <span data-ttu-id="00fae-109">DSC および PowerShell クラスにおけるデバッグ機能の強化</span><span class="sxs-lookup"><span data-stu-id="00fae-109">Debugging improvements for DSC and PowerShell classes</span></span>
- <span data-ttu-id="00fae-110">セキュリティの機能強化としては、プル サーバーからもたらされるカタログ署名付きモジュールの適用、PowerShellGet コマンドレットを使用するタイミングなどが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="00fae-110">Security enhancements including enforcement of catalog-signed modules coming from the Pull Server and when using PowerShellGet cmdlets</span></span>
- <span data-ttu-id="00fae-111">さまざまなユーザー要求と問題への対応</span><span class="sxs-lookup"><span data-stu-id="00fae-111">Responses to a number of user requests and issues</span></span>

<span data-ttu-id="00fae-112">**重要な注意事項:**</span><span class="sxs-lookup"><span data-stu-id="00fae-112">**Important notes:**</span></span>

- <span data-ttu-id="00fae-113">**WMF 5.1 には .NET Framework 4.5.2** (またはそれ以上) が必要です。</span><span class="sxs-lookup"><span data-stu-id="00fae-113">**WMF 5.1 requires the .NET Framework 4.5.2** (or above).</span></span> <span data-ttu-id="00fae-114">.NET 4.5.2 (またはそれ以上) がインストールされていない場合、インストールは成功しますが、主な機能は失敗します。</span><span class="sxs-lookup"><span data-stu-id="00fae-114">Installation will succeed, but key features will fail if .NET 4.5.2 (or above) is not installed.</span></span> <span data-ttu-id="00fae-115">手順については、トピック「[WMF 5.1 のインストールと構成](https://msdn.microsoft.com/powershell/wmf/5.1/install-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00fae-115">Instructions are available in the [Install and Configure WMF 5.1 ](https://msdn.microsoft.com/powershell/wmf/5.1/install-configure) topic.</span></span>
- <span data-ttu-id="00fae-116">WMF 5.1 RTM をインストールする前に、WMF 5.1 プレビューをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00fae-116">WMF 5.1 Preview must be uninstalled before installing WMF 5.1 RTM.</span></span>
- <span data-ttu-id="00fae-117">WMF 5.1 は、WMF 5.0 または WMF 4.0 の上に直接インストールできます。</span><span class="sxs-lookup"><span data-stu-id="00fae-117">WMF 5.1 may be installed directly over WMF 5.0 or WMF 4.0.</span></span>
- <span data-ttu-id="00fae-118">Windows 7 および Windows Server 2008 R2 の上に WMF 5.1 をインストールする前に、WMF 4.0 をインストールする__必要はありません__。</span><span class="sxs-lookup"><span data-stu-id="00fae-118">It is __not required__ to install WMF 4.0 prior to installing WMF 5.1 on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="00fae-119">これは WMF 5.1 プレビュー リリースでの問題でしたが、解決されました。</span><span class="sxs-lookup"><span data-stu-id="00fae-119">That was an issue for the WMF 5.1 Preview release, and has been resolved.</span></span>
