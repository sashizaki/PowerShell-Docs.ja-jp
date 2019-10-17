---
title: PowerShell Core のサポート ライフサイクル
description: PowerShell Core のサポートを管理するポリシー
ms.date: 08/06/2018
ms.openlocfilehash: fbbda0a5f8460e5625625adcc50c631729df53f1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72351812"
---
# <a name="powershell-core-support-lifecycle"></a><span data-ttu-id="4ac63-103">PowerShell Core のサポート ライフサイクル</span><span class="sxs-lookup"><span data-stu-id="4ac63-103">PowerShell Core Support Lifecycle</span></span>

<span data-ttu-id="4ac63-104">PowerShell Core は、Windows PowerShell とは別に出荷され、インストールされ、構成される別個のツール セットであり、コンポーネント セットです。</span><span class="sxs-lookup"><span data-stu-id="4ac63-104">PowerShell Core is a distinct set of tools and components that is shipped, installed, and configured separately from Windows PowerShell.</span></span> <span data-ttu-id="4ac63-105">そのため、PowerShell Core は Windows 7/8.1/10 や Windows Server のライセンス契約には含まれていません。</span><span class="sxs-lookup"><span data-stu-id="4ac63-105">So, PowerShell Core isn't included in the Windows 7/8.1/10 or Windows Server licensing agreements.</span></span>

<span data-ttu-id="4ac63-106">ただし、PowerShell Core は、[Premier][]、[Microsoft Enterprise Agreements][enterprise-agreement]、[マイクロソフト ソフトウェア アシュアランス][assurance]など、従来の Microsoft サポート契約ではサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4ac63-106">However, PowerShell Core is supported under traditional Microsoft support agreements, including [Premier][], [Microsoft Enterprise Agreements][enterprise-agreement], and [Microsoft Software Assurance][assurance].</span></span>
<span data-ttu-id="4ac63-107">サポート依頼で問題を報告して PowerShell Core の[サポート][]を受け、それに対して支払うこともできます。</span><span class="sxs-lookup"><span data-stu-id="4ac63-107">You can also pay for [assisted support][] for PowerShell Core by filing a support request for your problem.</span></span>

## <a name="community-support"></a><span data-ttu-id="4ac63-108">コミュニティ サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-108">Community Support</span></span>

<span data-ttu-id="4ac63-109">GitHub でも[コミュニティ サポート][]を用意しています。問題やバグを報告したり、機能を要望したりできます。</span><span class="sxs-lookup"><span data-stu-id="4ac63-109">We also offer [community support][] on GitHub where you can file an issue, bug, or feature request.</span></span>
<span data-ttu-id="4ac63-110">また、一般的な [Microsoft コミュニティ][]や Microsoft [PowerShell Tech コミュニティ][]で他のコミュニティ メンバーがサポートしてくれる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="4ac63-110">Also, you may find help from other members of the community on the general [Microsoft Community][] or the Microsoft [PowerShell Tech Community][].</span></span> <span data-ttu-id="4ac63-111">コミュニティによりご自身の問題が短期間で対処または解決されることは保証できません。</span><span class="sxs-lookup"><span data-stu-id="4ac63-111">We offer no guarantee there that the community will address or resolve your issue in a timely manner.</span></span> <span data-ttu-id="4ac63-112">早急な対応が必要な問題の場合、従来の有料サポートをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="4ac63-112">If you have a problem that requires immediate attention, you should use the traditional, paid support options.</span></span>

## <a name="lifecycle-of-powershell-core"></a><span data-ttu-id="4ac63-113">PowerShell Core のライフサイクル</span><span class="sxs-lookup"><span data-stu-id="4ac63-113">Lifecycle of PowerShell Core</span></span>

<span data-ttu-id="4ac63-114">PowerShell Core には、[Microsoft モダン ライフサイクル ポリシー][modern]が採用されています。</span><span class="sxs-lookup"><span data-stu-id="4ac63-114">PowerShell Core is adopting the [Microsoft Modern Lifecycle Policy][modern].</span></span> <span data-ttu-id="4ac63-115">このサポート ライフサイクルでは、最新バージョンで最新の機能を常に提供します。</span><span class="sxs-lookup"><span data-stu-id="4ac63-115">This support lifecycle is intended to keep customers up-to-date with the latest versions.</span></span>

<span data-ttu-id="4ac63-116">PowerShell Core のバージョン 6.x ブランチは約半年に一回更新されます (例:6.0、6.1、6.2 など。)</span><span class="sxs-lookup"><span data-stu-id="4ac63-116">The version 6.x branch of PowerShell Core will be updated approximately once every six months (examples: 6.0, 6.1, 6.2, etc.)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ac63-117">引き続きサポートを受けるには、新しいマイナー バージョンの公開後、6 か月以内に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ac63-117">You must update within six months after each new minor version release to continue receiving support.</span></span>

<span data-ttu-id="4ac63-118">たとえば、PowerShell Core 6.1 が 2018 年 7 月 1 日に公開された場合、サポートを維持するには、2019 年 1 月 1 日までに PowerShell Core 6.1 に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ac63-118">For example, if PowerShell Core 6.1 is released on July 1, 2018, you would be expected to update to PowerShell Core 6.1 by January 1, 2019 to maintain support.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ac63-119">サポートを受け続けるには、それぞれの新しいパッチ バージョンのリリース後 30 日以内に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ac63-119">You must update within 30 days after each new patch version release to continue receiving support.</span></span>

<span data-ttu-id="4ac63-120">たとえば、PowerShell Core 6.1 を実行していて 2019 年 2 月 19 日に 6.1.3 がリリースされた場合、サポートを維持するには、リリースの 30 日後である 2019 年 3 月 21 日までに PowerShell Core 6.1.3 に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ac63-120">For example, If you're running PowerShell Core 6.1 and 6.1.3 was released on February 19, 2019, you would be expected to update to PowerShell Core 6.1.3 by March 21, 2019, which is 30 days after the release to maintain support.</span></span> <span data-ttu-id="4ac63-121">必要な修正プログラムが見つかった場合、その修正プログラムは次の累積的な更新プログラムでリリースされます。</span><span class="sxs-lookup"><span data-stu-id="4ac63-121">If any fixes are found to be required, the fixes will be released in our next cumulative update.</span></span>

<span data-ttu-id="4ac63-122">Modern Lifecycle Policy では、製品 (つまり、PowerShell Core) のサポートを終了する 12 か月前にお客様に通知することを Microsoft の義務としています。</span><span class="sxs-lookup"><span data-stu-id="4ac63-122">The Modern Lifecycle Policy also requires that Microsoft give customers 12 months notice before discontinuing support for a product (that is, PowerShell Core).</span></span>

<span data-ttu-id="4ac63-123">最終的に、PowerShell Core では長期サービスのアプローチを採用する予定です。</span><span class="sxs-lookup"><span data-stu-id="4ac63-123">Eventually, we expect PowerShell Core will adopt the long-term servicing approach.</span></span> <span data-ttu-id="4ac63-124">このサービスのアプローチでは、特定のブランチ/バージョン の 6.x のサポートを維持するために、サービスとセキュリティの更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="4ac63-124">In this servicing approach, we would require only servicing and security updates to stay in support on a specific branch/version of 6.x.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="4ac63-125">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="4ac63-125">Supported platforms</span></span>

<span data-ttu-id="4ac63-126">お使いのプラットフォームと PowerShell Core のバージョンが正式にサポートされているかどうかを確認するには、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ac63-126">To confirm if your platform and version of PowerShell Core are officially supported, see the following table.</span></span>

<span data-ttu-id="4ac63-127">また、弊社のコミュニティでも一部のプラットフォームに向けたパッケージを提供していますが、これらは正式にはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4ac63-127">Our community has also contributed packages for some platforms, but they aren't officially supported.</span></span> <span data-ttu-id="4ac63-128">これらのパッケージは、表の中で `Community` とマークされています。</span><span class="sxs-lookup"><span data-stu-id="4ac63-128">These packages are marked as `Community` in the table.</span></span>

<span data-ttu-id="4ac63-129">`Experimental` としてリストされているプラットフォームは、正式にはサポートされていませんが、実験とフィードバックのために使用することができます。</span><span class="sxs-lookup"><span data-stu-id="4ac63-129">Platforms listed as `Experimental` aren't officially supported, but are available for experimentation and feedback.</span></span>

| <span data-ttu-id="4ac63-130">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="4ac63-130">Platform</span></span>                                          |      <span data-ttu-id="4ac63-131">6.2</span><span class="sxs-lookup"><span data-stu-id="4ac63-131">6.2</span></span>      |    <span data-ttu-id="4ac63-132">7.0</span><span class="sxs-lookup"><span data-stu-id="4ac63-132">7.0</span></span>    |
|---------------------------------------------------|:-------------:|:---------:|
| <span data-ttu-id="4ac63-133">Windows 7、8.1、10</span><span class="sxs-lookup"><span data-stu-id="4ac63-133">Windows 7, 8.1, and 10</span></span>                            |   <span data-ttu-id="4ac63-134">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-134">Supported</span></span>   | <span data-ttu-id="4ac63-135">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-135">Supported</span></span> |
| <span data-ttu-id="4ac63-136">Windows Server 2008 R2、2012 R2、2016</span><span class="sxs-lookup"><span data-stu-id="4ac63-136">Windows Server 2008 R2, 2012 R2, 2016</span></span>             |   <span data-ttu-id="4ac63-137">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-137">Supported</span></span>   | <span data-ttu-id="4ac63-138">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-138">Supported</span></span> |
| <span data-ttu-id="4ac63-139">[Windows Server 半期チャネル][semi-annual]</span><span class="sxs-lookup"><span data-stu-id="4ac63-139">[Windows Server Semi-Annual Channel][semi-annual]</span></span> |   <span data-ttu-id="4ac63-140">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-140">Supported</span></span>   | <span data-ttu-id="4ac63-141">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-141">Supported</span></span> |
| <span data-ttu-id="4ac63-142">Ubuntu 16.04 および 18.04</span><span class="sxs-lookup"><span data-stu-id="4ac63-142">Ubuntu 16.04 and 18.04</span></span>                            |   <span data-ttu-id="4ac63-143">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-143">Supported</span></span>   | <span data-ttu-id="4ac63-144">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-144">Supported</span></span> |
| <span data-ttu-id="4ac63-145">Ubuntu 18.10 (Snap パッケージを使用)</span><span class="sxs-lookup"><span data-stu-id="4ac63-145">Ubuntu 18.10 (via Snap Package)</span></span>                   |   <span data-ttu-id="4ac63-146">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="4ac63-146">Community</span></span>   | <span data-ttu-id="4ac63-147">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="4ac63-147">Community</span></span> |
| <span data-ttu-id="4ac63-148">Ubuntu 19.04 (Snap パッケージを使用)</span><span class="sxs-lookup"><span data-stu-id="4ac63-148">Ubuntu 19.04 (via Snap Package)</span></span>                   |   <span data-ttu-id="4ac63-149">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="4ac63-149">Community</span></span>   | <span data-ttu-id="4ac63-150">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="4ac63-150">Community</span></span> |
| <span data-ttu-id="4ac63-151">Debian 9</span><span class="sxs-lookup"><span data-stu-id="4ac63-151">Debian 9</span></span>                                          |   <span data-ttu-id="4ac63-152">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-152">Supported</span></span>   | <span data-ttu-id="4ac63-153">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-153">Supported</span></span> |
| <span data-ttu-id="4ac63-154">Debian 10</span><span class="sxs-lookup"><span data-stu-id="4ac63-154">Debian 10</span></span>                                         | <span data-ttu-id="4ac63-155">サポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4ac63-155">Not Supported</span></span> | <span data-ttu-id="4ac63-156">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-156">Supported</span></span> |
| <span data-ttu-id="4ac63-157">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="4ac63-157">CentOS 7</span></span>                                          |   <span data-ttu-id="4ac63-158">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-158">Supported</span></span>   | <span data-ttu-id="4ac63-159">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-159">Supported</span></span> |
| <span data-ttu-id="4ac63-160">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="4ac63-160">Red Hat Enterprise Linux 7</span></span>                        |   <span data-ttu-id="4ac63-161">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-161">Supported</span></span>   | <span data-ttu-id="4ac63-162">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-162">Supported</span></span> |
| <span data-ttu-id="4ac63-163">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="4ac63-163">openSUSE 42.3</span></span>                                     |   <span data-ttu-id="4ac63-164">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-164">Supported</span></span>   | <span data-ttu-id="4ac63-165">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-165">Supported</span></span> |
| <span data-ttu-id="4ac63-166">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="4ac63-166">Fedora 28</span></span>                                         |   <span data-ttu-id="4ac63-167">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-167">Supported</span></span>   | <span data-ttu-id="4ac63-168">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-168">Supported</span></span> |
| <span data-ttu-id="4ac63-169">Fedora 29、30</span><span class="sxs-lookup"><span data-stu-id="4ac63-169">Fedora 29, 30</span></span>                                     | <span data-ttu-id="4ac63-170">サポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4ac63-170">Not Supported</span></span> | <span data-ttu-id="4ac63-171">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-171">Supported</span></span> |
| <span data-ttu-id="4ac63-172">Alpine 3.8</span><span class="sxs-lookup"><span data-stu-id="4ac63-172">Alpine 3.8</span></span>                                        |   <span data-ttu-id="4ac63-173">注を参照</span><span class="sxs-lookup"><span data-stu-id="4ac63-173">See Note</span></span>    | <span data-ttu-id="4ac63-174">注を参照</span><span class="sxs-lookup"><span data-stu-id="4ac63-174">See Note</span></span>  |
| <span data-ttu-id="4ac63-175">Alpine 3.9 および 3.10</span><span class="sxs-lookup"><span data-stu-id="4ac63-175">Alpine 3.9 and 3.10</span></span>                               | <span data-ttu-id="4ac63-176">サポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4ac63-176">Not Supported</span></span> | <span data-ttu-id="4ac63-177">注を参照</span><span class="sxs-lookup"><span data-stu-id="4ac63-177">See Note</span></span>  |
| <span data-ttu-id="4ac63-178">macOS 10.12 以降</span><span class="sxs-lookup"><span data-stu-id="4ac63-178">macOS 10.12+</span></span>                                      |   <span data-ttu-id="4ac63-179">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-179">Supported</span></span>   | <span data-ttu-id="4ac63-180">サポート</span><span class="sxs-lookup"><span data-stu-id="4ac63-180">Supported</span></span> |
| <span data-ttu-id="4ac63-181">Arch</span><span class="sxs-lookup"><span data-stu-id="4ac63-181">Arch</span></span>                                              |   <span data-ttu-id="4ac63-182">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="4ac63-182">Community</span></span>   | <span data-ttu-id="4ac63-183">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="4ac63-183">Community</span></span> |
| <span data-ttu-id="4ac63-184">Raspbian</span><span class="sxs-lookup"><span data-stu-id="4ac63-184">Raspbian</span></span>                                          |   <span data-ttu-id="4ac63-185">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="4ac63-185">Community</span></span>   | <span data-ttu-id="4ac63-186">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="4ac63-186">Community</span></span> |
| <span data-ttu-id="4ac63-187">Kali</span><span class="sxs-lookup"><span data-stu-id="4ac63-187">Kali</span></span>                                              |   <span data-ttu-id="4ac63-188">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="4ac63-188">Community</span></span>   | <span data-ttu-id="4ac63-189">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="4ac63-189">Community</span></span> |
| <span data-ttu-id="4ac63-190">AppImage (複数の Linux プラットフォームで機能)</span><span class="sxs-lookup"><span data-stu-id="4ac63-190">AppImage (works on multiple Linux platforms)</span></span>      |   <span data-ttu-id="4ac63-191">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="4ac63-191">Community</span></span>   | <span data-ttu-id="4ac63-192">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="4ac63-192">Community</span></span> |
| [<span data-ttu-id="4ac63-193">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="4ac63-193">Snap Package</span></span>](https://snapcraft.io/powershell)   |   <span data-ttu-id="4ac63-194">注を参照</span><span class="sxs-lookup"><span data-stu-id="4ac63-194">See note</span></span>    | <span data-ttu-id="4ac63-195">注を参照</span><span class="sxs-lookup"><span data-stu-id="4ac63-195">See note</span></span>  |

> [!NOTE]
> <span data-ttu-id="4ac63-196">パッケージを実行しているディストリビューションと同様に、Snap パッケージがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4ac63-196">Snap packages are supported the same as the distribution you're running the package on.</span></span>

> [!NOTE]
> <span data-ttu-id="4ac63-197">Alpine では、CIM、PowerShell リモート処理、および DSC はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4ac63-197">CIM, PowerShell Remoting, and DSC are not supported on Alpine.</span></span>

## <a name="powershell-releases-end-of-life"></a><span data-ttu-id="4ac63-198">PowerShell リリースのサポート終了</span><span class="sxs-lookup"><span data-stu-id="4ac63-198">PowerShell releases end-of-life</span></span>

<span data-ttu-id="4ac63-199">[PowerShell Core のライフサイクル](#lifecycle-of-powershell-core)に基づき、さまざまなリリースがサポートされなくなる日付を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="4ac63-199">Based on [Lifecycle of PowerShell Core](#lifecycle-of-powershell-core), the following table lists the dates when various releases will no longer be supported.</span></span>

| <span data-ttu-id="4ac63-200">バージョン</span><span class="sxs-lookup"><span data-stu-id="4ac63-200">Version</span></span> | <span data-ttu-id="4ac63-201">サポート終了</span><span class="sxs-lookup"><span data-stu-id="4ac63-201">End-of-life</span></span>                   |
|---------|-------------------------------|
| <span data-ttu-id="4ac63-202">6.0</span><span class="sxs-lookup"><span data-stu-id="4ac63-202">6.0</span></span>     | <span data-ttu-id="4ac63-203">2019 年 2 月 13 日</span><span class="sxs-lookup"><span data-stu-id="4ac63-203">February 13, 2019</span></span>             |
| <span data-ttu-id="4ac63-204">6.1</span><span class="sxs-lookup"><span data-stu-id="4ac63-204">6.1</span></span>     | <span data-ttu-id="4ac63-205">2019 年 9 月 28 日</span><span class="sxs-lookup"><span data-stu-id="4ac63-205">September 28, 2019</span></span>            |
| <span data-ttu-id="4ac63-206">6.2</span><span class="sxs-lookup"><span data-stu-id="4ac63-206">6.2</span></span>     | <span data-ttu-id="4ac63-207">7 のリリースから 6 か月後</span><span class="sxs-lookup"><span data-stu-id="4ac63-207">6 months after 7 releases</span></span>     |

## <a name="unsupported-platforms"></a><span data-ttu-id="4ac63-208">サポートされないプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="4ac63-208">Unsupported platforms</span></span>

<span data-ttu-id="4ac63-209">プラットフォームのバージョンが、プラットフォームの所有者によって定義された有効期限を迎えると、PowerShell Core でもそのプラットフォームのバージョンがサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="4ac63-209">When a platform version reaches end-of-life as defined by the platform owner, PowerShell Core will also cease to support that platform version.</span></span> <span data-ttu-id="4ac63-210">アクセスする必要があるユーザーは引き続き以前にリリースされたパッケージを利用できますが、公式のサポートと更新プログラムはどんな種類のものも提供されなくなります。</span><span class="sxs-lookup"><span data-stu-id="4ac63-210">Previously released packages will remain available for customers needing access but formal support and updates of any kind will no longer be provided.</span></span>

<span data-ttu-id="4ac63-211">そのため、ディストリビューションの所有者によって次のバージョンのサポートは終了され、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4ac63-211">So, the distribution owners ended support for the following versions and aren't supported.</span></span>

| <span data-ttu-id="4ac63-212">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="4ac63-212">Platform</span></span> | <span data-ttu-id="4ac63-213">バージョン</span><span class="sxs-lookup"><span data-stu-id="4ac63-213">Version</span></span> | <span data-ttu-id="4ac63-214">有効期限切れ</span><span class="sxs-lookup"><span data-stu-id="4ac63-214">End of Life</span></span>                                                                                 |
|----------|---------|---------------------------------------------------------------------------------------------|
| <span data-ttu-id="4ac63-215">Fedora</span><span class="sxs-lookup"><span data-stu-id="4ac63-215">Fedora</span></span>   | <span data-ttu-id="4ac63-216">24</span><span class="sxs-lookup"><span data-stu-id="4ac63-216">24</span></span>      | [<span data-ttu-id="4ac63-217">2017 年 8 月</span><span class="sxs-lookup"><span data-stu-id="4ac63-217">August 2017</span></span>](https://fedoramagazine.org/fedora-24-eol/)                                    |
| <span data-ttu-id="4ac63-218">Fedora</span><span class="sxs-lookup"><span data-stu-id="4ac63-218">Fedora</span></span>   | <span data-ttu-id="4ac63-219">25</span><span class="sxs-lookup"><span data-stu-id="4ac63-219">25</span></span>      | [<span data-ttu-id="4ac63-220">2017 年 12 月</span><span class="sxs-lookup"><span data-stu-id="4ac63-220">December 2017</span></span>](https://fedoramagazine.org/fedora-25-end-life/)                             |
| <span data-ttu-id="4ac63-221">Fedora</span><span class="sxs-lookup"><span data-stu-id="4ac63-221">Fedora</span></span>   | <span data-ttu-id="4ac63-222">26</span><span class="sxs-lookup"><span data-stu-id="4ac63-222">26</span></span>      | [<span data-ttu-id="4ac63-223">2018 年 5 月</span><span class="sxs-lookup"><span data-stu-id="4ac63-223">May 2018</span></span>](https://fedoramagazine.org/fedora-26-end-life/)                                  |
| <span data-ttu-id="4ac63-224">openSUSE</span><span class="sxs-lookup"><span data-stu-id="4ac63-224">openSUSE</span></span> | <span data-ttu-id="4ac63-225">42.1</span><span class="sxs-lookup"><span data-stu-id="4ac63-225">42.1</span></span>    | [<span data-ttu-id="4ac63-226">2017 年 5 月</span><span class="sxs-lookup"><span data-stu-id="4ac63-226">May 2017</span></span>](https://lists.opensuse.org/opensuse-security-announce/2017-05/msg00053.html)     |
| <span data-ttu-id="4ac63-227">openSUSE</span><span class="sxs-lookup"><span data-stu-id="4ac63-227">openSUSE</span></span> | <span data-ttu-id="4ac63-228">42.2</span><span class="sxs-lookup"><span data-stu-id="4ac63-228">42.2</span></span>    | [<span data-ttu-id="4ac63-229">2018 年 1 月</span><span class="sxs-lookup"><span data-stu-id="4ac63-229">January 2018</span></span>](https://lists.opensuse.org/opensuse-security-announce/2017-11/msg00066.html) |
| <span data-ttu-id="4ac63-230">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="4ac63-230">Ubuntu</span></span>   | <span data-ttu-id="4ac63-231">16.10</span><span class="sxs-lookup"><span data-stu-id="4ac63-231">16.10</span></span>   | [<span data-ttu-id="4ac63-232">2017 年 7 月</span><span class="sxs-lookup"><span data-stu-id="4ac63-232">July 2017</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2017-July/000223.html)        |
| <span data-ttu-id="4ac63-233">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="4ac63-233">Ubuntu</span></span>   | <span data-ttu-id="4ac63-234">17.04</span><span class="sxs-lookup"><span data-stu-id="4ac63-234">17.04</span></span>   | [<span data-ttu-id="4ac63-235">2018 年 1 月</span><span class="sxs-lookup"><span data-stu-id="4ac63-235">January 2018</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2018-January.txt)          |
| <span data-ttu-id="4ac63-236">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="4ac63-236">Ubuntu</span></span>   | <span data-ttu-id="4ac63-237">17.10</span><span class="sxs-lookup"><span data-stu-id="4ac63-237">17.10</span></span>   | [<span data-ttu-id="4ac63-238">2018 年 7 月</span><span class="sxs-lookup"><span data-stu-id="4ac63-238">July 2018</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2018-July/000232.html)        |
| <span data-ttu-id="4ac63-239">Debian</span><span class="sxs-lookup"><span data-stu-id="4ac63-239">Debian</span></span>   | <span data-ttu-id="4ac63-240">8</span><span class="sxs-lookup"><span data-stu-id="4ac63-240">8</span></span>       | [<span data-ttu-id="4ac63-241">2018 年 6 月</span><span class="sxs-lookup"><span data-stu-id="4ac63-241">June 2018</span></span>](https://lists.debian.org/debian-security-announce/2018/msg00132.html)           |
| <span data-ttu-id="4ac63-242">Fedora</span><span class="sxs-lookup"><span data-stu-id="4ac63-242">Fedora</span></span>   | <span data-ttu-id="4ac63-243">27</span><span class="sxs-lookup"><span data-stu-id="4ac63-243">27</span></span>      | [<span data-ttu-id="4ac63-244">2018 年 11 月</span><span class="sxs-lookup"><span data-stu-id="4ac63-244">November 2018</span></span>](https://fedoramagazine.org/fedora-27-end-of-life/)                          |
| <span data-ttu-id="4ac63-245">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="4ac63-245">Ubuntu</span></span>   | <span data-ttu-id="4ac63-246">14.04</span><span class="sxs-lookup"><span data-stu-id="4ac63-246">14.04</span></span>   | [<span data-ttu-id="4ac63-247">2019 年 4 月</span><span class="sxs-lookup"><span data-stu-id="4ac63-247">April 2019</span></span>](https://wiki.ubuntu.com/Releases)                                              |

## <a name="notes-on-licensing"></a><span data-ttu-id="4ac63-248">ライセンスに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="4ac63-248">Notes on licensing</span></span>

<span data-ttu-id="4ac63-249">PowerShell Core は [MIT ライセンス][]の下で提供されます。</span><span class="sxs-lookup"><span data-stu-id="4ac63-249">PowerShell Core is released under the [MIT license][].</span></span> <span data-ttu-id="4ac63-250">このライセンスの下で、有料サポート契約がないときは、ユーザーには[コミュニティ サポート][]のみが与えられます。</span><span class="sxs-lookup"><span data-stu-id="4ac63-250">Under this license, and without a paid support agreement, users are limited to [community support][].</span></span> <span data-ttu-id="4ac63-251">コミュニティ サポートの場合、マイクロソフトは回答や解決を保証しません。</span><span class="sxs-lookup"><span data-stu-id="4ac63-251">With community support, Microsoft makes no guarantees of responsiveness or fixes.</span></span>

## <a name="windows-powershell-module"></a><span data-ttu-id="4ac63-252">Windows PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="4ac63-252">Windows PowerShell Module</span></span>

<span data-ttu-id="4ac63-253">PowerShell Core のサポートに製品モジュールが含まれることは、そのモジュールで明示的に PowerShell Core をサポートしている場合を除いて、ありません。</span><span class="sxs-lookup"><span data-stu-id="4ac63-253">Support for PowerShell Core doesn't include product modules, unless those modules explicitly support PowerShell Core.</span></span> <span data-ttu-id="4ac63-254">たとえば、Windows Server に付属する `ActiveDirectory` モジュールを使用することはサポートの対象外です。</span><span class="sxs-lookup"><span data-stu-id="4ac63-254">For example, using the `ActiveDirectory` module that ships as part of Windows Server is an unsupported scenario.</span></span>

<span data-ttu-id="4ac63-255">ただし、明示的に PowerShell Core をサポートしていないモジュールの場合でも、場合によっては互換性があることがあります。</span><span class="sxs-lookup"><span data-stu-id="4ac63-255">However, modules that don't explicitly support PowerShell Core may be compatible in some cases.</span></span> <span data-ttu-id="4ac63-256">[`WindowsPSModulePath`][] モジュールをインストールすることで、Windows PowerShell `PSModulePath` を PowerShell Core `PSModulePath` に追加できます。</span><span class="sxs-lookup"><span data-stu-id="4ac63-256">By installing the [`WindowsPSModulePath`][] module, you can add the Windows PowerShell `PSModulePath` to your PowerShell Core `PSModulePath`.</span></span>

<span data-ttu-id="4ac63-257">最初に、PowerShell ギャラリーから `WindowsPSModulePath` モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4ac63-257">First, install the `WindowsPSModulePath` module from the PowerShell Gallery:</span></span>

```powershell
# Add `-Scope CurrentUser` if you're installing as non-admin
Install-Module WindowsPSModulePath -Force
```

<span data-ttu-id="4ac63-258">このモジュールをインストールしたら、次のように `Add-WindowsPSModulePath` コマンドレットを実行して、Windows PowerShell `PSModulePath` を PowerShell Core に追加します。</span><span class="sxs-lookup"><span data-stu-id="4ac63-258">After installing this module, run the `Add-WindowsPSModulePath` cmdlet to add the Windows PowerShell `PSModulePath` to PowerShell Core:</span></span>

```powershell
# Add this line to your profile if you always want Windows PowerShell PSModulePath
Add-WindowsPSModulePath
```

## <a name="experimental-features"></a><span data-ttu-id="4ac63-259">試験的な機能</span><span class="sxs-lookup"><span data-stu-id="4ac63-259">Experimental features</span></span>

<span data-ttu-id="4ac63-260">[試験的な機能][]には[コミュニティ サポート](#community-support)のみが与えられます。</span><span class="sxs-lookup"><span data-stu-id="4ac63-260">[Experimental features][] are limited to [community support](#community-support).</span></span>

[Premier]: https://www.microsoft.com/en-us/microsoftservices/support.aspx
[enterprise-agreement]: https://www.microsoft.com/en-us/licensing/licensing-programs/enterprise.aspx
[assurance]: https://www.microsoft.com/en-us/licensing/licensing-programs/software-assurance-default.aspx
[コミュニティ サポート]: https://github.com/powershell/powershell/issues
[community support]: https://github.com/powershell/powershell/issues
[Microsoft コミュニティ]: https://answers.microsoft.com/
[Microsoft Community]: https://answers.microsoft.com/
[PowerShell Tech コミュニティ]: https://techcommunity.microsoft.com/t5/PowerShell/ct-p/WindowsPowerShell
[PowerShell Tech Community]: https://techcommunity.microsoft.com/t5/PowerShell/ct-p/WindowsPowerShell
[サポート]: https://support.microsoft.com/assistedsupportproducts
[assisted support]: https://support.microsoft.com/assistedsupportproducts
[modern]: https://support.microsoft.com/help/30881/modern-lifecycle-policy
[lifecycle-chart]: ./images/modern-lifecycle.png
[semi-annual]: https://docs.microsoft.com/windows-server/get-started/semi-annual-channel-overview
[MIT ライセンス]: https://github.com/PowerShell/PowerShell/blob/master/LICENSE.txt
[MIT license]: https://github.com/PowerShell/PowerShell/blob/master/LICENSE.txt
[`WindowsPSModulePath`]: https://www.powershellgallery.com/packages/WindowsPSModulePath/
[試験的な機能]: /powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-6#experimentalfeatures
[Experimental features]: /powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-6#experimentalfeatures
