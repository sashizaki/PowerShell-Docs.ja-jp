---
ms.date: 08/12/2017
ms.topic: conceptual
keywords: WMF, PowerShell, セットアップ
title: WMF 5.1 リリース ノート
ms.openlocfilehash: 3512d2e80501a596e1fd6d7b33d4d75286cef1b9
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
ms.locfileid: "34189790"
---
# <a name="windows-management-framework-wmf-51"></a><span data-ttu-id="1e4fa-103">Windows Management Framework (WMF) 5.1</span><span class="sxs-lookup"><span data-stu-id="1e4fa-103">Windows Management Framework (WMF) 5.1</span></span> #

<span data-ttu-id="1e4fa-104">WMF は、既存の Windows システムを、Windows Server 2016 でリリースされた PowerShell、WMI、WinRM、およびソフトウェア インベントリ ログ (SIL) のコンポーネントのバージョンに更新する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1e4fa-104">WMF provides users with the ability to update existing Windows systems to the versions of PowerShell, WMI, WinRM, and Software Inventory Logging (SIL) components that were released with Windows Server 2016.</span></span>

<span data-ttu-id="1e4fa-105">WMF 5.1 は、Windows 7、Windows 8.1、Windows Server 2008 R2、Windows Server 2012、および Windows Server 2012 R2 にインストールすることができ、WMF 5.0 RTM と比較すると次のような機能が強化されています。</span><span class="sxs-lookup"><span data-stu-id="1e4fa-105">WMF 5.1 can be installed on Windows 7, Windows 8.1, Windows Server 2008 R2, 2012, and 2012 R2, and provides a number of improvements over WMF 5.0 RTM including:</span></span>

- <span data-ttu-id="1e4fa-106">新しいコマンドレット: ローカル ユーザーとグループ、Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="1e4fa-106">New cmdlets: local users and groups; Get-ComputerInfo</span></span>
- <span data-ttu-id="1e4fa-107">PowerShellGet では、署名付きモジュールの適用や JEA モジュールのインストールなどの機能強化が行われています。</span><span class="sxs-lookup"><span data-stu-id="1e4fa-107">PowerShellGet improvements include enforcing signed modules, and installing JEA modules</span></span>
- <span data-ttu-id="1e4fa-108">PackageManagement では、コンテナー、CBS セットアップ、EXE ベースのセットアップ、CAB パッケージをサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="1e4fa-108">PackageManagement added support for Containers, CBS Setup, EXE-based setup, CAB packages</span></span>
- <span data-ttu-id="1e4fa-109">DSC および PowerShell クラスにおけるデバッグ機能の強化</span><span class="sxs-lookup"><span data-stu-id="1e4fa-109">Debugging improvements for DSC and PowerShell classes</span></span>
- <span data-ttu-id="1e4fa-110">セキュリティの機能強化としては、プル サーバーからもたらされるカタログ署名付きモジュールの適用、PowerShellGet コマンドレットを使用するタイミングなどが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="1e4fa-110">Security enhancements including enforcement of catalog-signed modules coming from the Pull Server and when using PowerShellGet cmdlets</span></span>
- <span data-ttu-id="1e4fa-111">さまざまなユーザー要求と問題への対応</span><span class="sxs-lookup"><span data-stu-id="1e4fa-111">Responses to a number of user requests and issues</span></span>

<span data-ttu-id="1e4fa-112">このリリースの新機能については、「[新しいシナリオと機能](https://docs.microsoft.com/en-us/powershell/wmf/5.1/scenarios-features)」の下の各トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e4fa-112">To learn about what is new in this release, browse the topics listed under [New Scenarios and Features](https://docs.microsoft.com/en-us/powershell/wmf/5.1/scenarios-features).</span></span>

<span data-ttu-id="1e4fa-113">「[インストールと構成](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure)」トピックは要件を一覧表示し、WMF のインストール手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e4fa-113">The [Install and Configure](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure) topic lists the requirements and provides installation instructions for WMF.</span></span>

<span data-ttu-id="1e4fa-114">「[互換性](https://docs.microsoft.com/en-us/powershell/wmf/5.1/compatibility)」トピックは、どのWindows リリースにどの WMF のバージョンがインストールされているのかを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="1e4fa-114">The [Compatibility](https://docs.microsoft.com/en-us/powershell/wmf/5.1/compatibility) topic lists which versions of WMF may be installed on which Windows releases.</span></span>

<span data-ttu-id="1e4fa-115">「[製品の互換性](https://docs.microsoft.com/en-us/powershell/wmf/5.1/productincompat)」は、現時点で WMF 5.1 を承認していない Microsoft アプリケーションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="1e4fa-115">[Product Compatibility](https://docs.microsoft.com/en-us/powershell/wmf/5.1/productincompat) lists the Microsoft applications that have not approved WMF 5.1 for use at this time.</span></span>

<span data-ttu-id="1e4fa-116">WMF の各コンポーネントの詳細については、MSDN のドキュメントに記載されています。</span><span class="sxs-lookup"><span data-stu-id="1e4fa-116">Details for the components of WMF will be found in MSDN documentation:</span></span>

- [<span data-ttu-id="1e4fa-117">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="1e4fa-117">PowerShell 5.1</span></span>](https://docs.microsoft.com/en-us/powershell/)
- <span data-ttu-id="1e4fa-118">[WMI](https://msdn.microsoft.com/en-us/library/jj152383(v=vs.85).aspx)</span><span class="sxs-lookup"><span data-stu-id="1e4fa-118">[WMI](https://msdn.microsoft.com/en-us/library/jj152383(v=vs.85).aspx)</span></span>
- <span data-ttu-id="1e4fa-119">[WinRM](https://msdn.microsoft.com/en-us/library/aa384426(v=vs.85).aspx)</span><span class="sxs-lookup"><span data-stu-id="1e4fa-119">[WinRM](https://msdn.microsoft.com/en-us/library/aa384426(v=vs.85).aspx)</span></span>
- <span data-ttu-id="1e4fa-120">[ソフトウェア インベントリ ログ](https://technet.microsoft.com/en-us/library/dn383584(v=ws.11).aspx)</span><span class="sxs-lookup"><span data-stu-id="1e4fa-120">[Software Inventory Logging](https://technet.microsoft.com/en-us/library/dn383584(v=ws.11).aspx)</span></span>
