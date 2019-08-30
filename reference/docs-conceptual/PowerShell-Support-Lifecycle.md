---
title: PowerShell Core のサポート ライフサイクル
description: PowerShell Core のサポートを管理するポリシー
ms.date: 08/06/2018
ms.openlocfilehash: 60999ed54ca3be15232ffee3ab0c49cb94873a8f
ms.sourcegitcommit: 5a004064f33acc0145ccd414535763e95f998c89
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2019
ms.locfileid: "69986742"
---
# <a name="powershell-core-support-lifecycle"></a><span data-ttu-id="2be2d-103">PowerShell Core のサポート ライフサイクル</span><span class="sxs-lookup"><span data-stu-id="2be2d-103">PowerShell Core Support Lifecycle</span></span>

<span data-ttu-id="2be2d-104">PowerShell Core は、Windows PowerShell とは別に出荷され、インストールされ、構成される別個のツール セットであり、コンポーネント セットです。</span><span class="sxs-lookup"><span data-stu-id="2be2d-104">PowerShell Core is a distinct set of tools and components that is shipped, installed, and configured separately from Windows PowerShell.</span></span> <span data-ttu-id="2be2d-105">そのため、PowerShell Core は Windows 7/8.1/10 や Windows Server のライセンス契約には含まれていません。</span><span class="sxs-lookup"><span data-stu-id="2be2d-105">So, PowerShell Core isn't included in the Windows 7/8.1/10 or Windows Server licensing agreements.</span></span>

<span data-ttu-id="2be2d-106">ただし、PowerShell Core は、[Premier][]、[Microsoft Enterprise Agreements][enterprise-agreement]、[マイクロソフト ソフトウェア アシュアランス][assurance]など、従来の Microsoft サポート契約ではサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2be2d-106">However, PowerShell Core is supported under traditional Microsoft support agreements, including [Premier][], [Microsoft Enterprise Agreements][enterprise-agreement], and [Microsoft Software Assurance][assurance].</span></span>
<span data-ttu-id="2be2d-107">サポート依頼で問題を報告して PowerShell Core の[サポート][]を受け、それに対して支払うこともできます。</span><span class="sxs-lookup"><span data-stu-id="2be2d-107">You can also pay for [assisted support][] for PowerShell Core by filing a support request for your problem.</span></span>

## <a name="community-support"></a><span data-ttu-id="2be2d-108">コミュニティ サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-108">Community Support</span></span>

<span data-ttu-id="2be2d-109">GitHub でも[コミュニティ サポート][]を用意しています。問題やバグを報告したり、機能を要望したりできます。</span><span class="sxs-lookup"><span data-stu-id="2be2d-109">We also offer [community support][] on GitHub where you can file an issue, bug, or feature request.</span></span>
<span data-ttu-id="2be2d-110">また、一般的な [Microsoft コミュニティ][]や Microsoft [PowerShell Tech コミュニティ][]で他のコミュニティ メンバーがサポートしてくれる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="2be2d-110">Also, you may find help from other members of the community on the general [Microsoft Community][] or the Microsoft [PowerShell Tech Community][].</span></span> <span data-ttu-id="2be2d-111">コミュニティによりご自身の問題が短期間で対処または解決されることは保証できません。</span><span class="sxs-lookup"><span data-stu-id="2be2d-111">We offer no guarantee there that the community will address or resolve your issue in a timely manner.</span></span> <span data-ttu-id="2be2d-112">早急な対応が必要な問題の場合、従来の有料サポートをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="2be2d-112">If you have a problem that requires immediate attention, you should use the traditional, paid support options.</span></span>

## <a name="lifecycle-of-powershell-core"></a><span data-ttu-id="2be2d-113">PowerShell Core のライフサイクル</span><span class="sxs-lookup"><span data-stu-id="2be2d-113">Lifecycle of PowerShell Core</span></span>

<span data-ttu-id="2be2d-114">PowerShell Core には、[Microsoft モダン ライフサイクル ポリシー][modern]が採用されています。</span><span class="sxs-lookup"><span data-stu-id="2be2d-114">PowerShell Core is adopting the [Microsoft Modern Lifecycle Policy][modern].</span></span> <span data-ttu-id="2be2d-115">このサポート ライフサイクルでは、最新バージョンで最新の機能を常に提供します。</span><span class="sxs-lookup"><span data-stu-id="2be2d-115">This support lifecycle is intended to keep customers up-to-date with the latest versions.</span></span>

<span data-ttu-id="2be2d-116">PowerShell Core のバージョン 6.x ブランチは約半年に一回更新されます (例:6.0、6.1、6.2 など。)</span><span class="sxs-lookup"><span data-stu-id="2be2d-116">The version 6.x branch of PowerShell Core will be updated approximately once every six months (examples: 6.0, 6.1, 6.2, etc.)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2be2d-117">引き続きサポートを受けるには、新しいマイナー バージョンの公開後、6 か月以内に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2be2d-117">You must update within six months after each new minor version release to continue receiving support.</span></span>

<span data-ttu-id="2be2d-118">たとえば、PowerShell Core 6.1 が 2018 年 7 月 1 日に公開された場合、サポートを維持するには、2019 年 1 月 1 日までに PowerShell Core 6.1 に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2be2d-118">For example, if PowerShell Core 6.1 is released on July 1, 2018, you would be expected to update to PowerShell Core 6.1 by January 1, 2019 to maintain support.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2be2d-119">サポートを受け続けるには、それぞれの新しいパッチ バージョンのリリース後 30 日以内に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2be2d-119">You must update within 30 days after each new patch version release to continue receiving support.</span></span>

<span data-ttu-id="2be2d-120">たとえば、PowerShell Core 6.1 を実行していて 2019 年 2 月 19 日に 6.1.3 がリリースされた場合、サポートを維持するには、リリースの 30 日後である 2019 年 3 月 21 日までに PowerShell Core 6.1.3 に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2be2d-120">For example, If you're running PowerShell Core 6.1 and 6.1.3 was released on February 19, 2019, you would be expected to update to PowerShell Core 6.1.3 by March 21, 2019, which is 30 days after the release to maintain support.</span></span> <span data-ttu-id="2be2d-121">必要な修正プログラムが見つかった場合、その修正プログラムは次の累積的な更新プログラムでリリースされます。</span><span class="sxs-lookup"><span data-stu-id="2be2d-121">If any fixes are found to be required, the fixes will be released in our next cumulative update.</span></span>

<span data-ttu-id="2be2d-122">Modern Lifecycle Policy では、製品 (つまり、PowerShell Core) のサポートを終了する 12 か月前にお客様に通知することを Microsoft の義務としています。</span><span class="sxs-lookup"><span data-stu-id="2be2d-122">The Modern Lifecycle Policy also requires that Microsoft give customers 12 months notice before discontinuing support for a product (that is, PowerShell Core).</span></span>

<span data-ttu-id="2be2d-123">最終的に、PowerShell Core では長期サービスのアプローチを採用する予定です。</span><span class="sxs-lookup"><span data-stu-id="2be2d-123">Eventually, we expect PowerShell Core will adopt the long-term servicing approach.</span></span> <span data-ttu-id="2be2d-124">このサービスのアプローチでは、特定のブランチ/バージョン の 6.x のサポートを維持するために、サービスとセキュリティの更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="2be2d-124">In this servicing approach, we would require only servicing and security updates to stay in support on a specific branch/version of 6.x.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="2be2d-125">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="2be2d-125">Supported platforms</span></span>

<span data-ttu-id="2be2d-126">お使いのプラットフォームと PowerShell Core のバージョンが正式にサポートされているかどうかを確認するには、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2be2d-126">To confirm if your platform and version of PowerShell Core are officially supported, see the following table.</span></span>

<span data-ttu-id="2be2d-127">また、弊社のコミュニティでも一部のプラットフォームに向けたパッケージを提供していますが、これらは正式にはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2be2d-127">Our community has also contributed packages for some platforms, but they aren't officially supported.</span></span> <span data-ttu-id="2be2d-128">これらのパッケージは、表の中で `Community` とマークされています。</span><span class="sxs-lookup"><span data-stu-id="2be2d-128">These packages are marked as `Community` in the table.</span></span>

<span data-ttu-id="2be2d-129">`Experimental` としてリストされているプラットフォームは、正式にはサポートされていませんが、実験とフィードバックのために使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2be2d-129">Platforms listed as `Experimental` aren't officially supported, but are available for experimentation and feedback.</span></span>

| <span data-ttu-id="2be2d-130">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="2be2d-130">Platform</span></span>                                          | <span data-ttu-id="2be2d-131">6.1</span><span class="sxs-lookup"><span data-stu-id="2be2d-131">6.1</span></span>         | <span data-ttu-id="2be2d-132">6.2</span><span class="sxs-lookup"><span data-stu-id="2be2d-132">6.2</span></span>         |
|---------------------------------------------------|:-----------:|:-----------:|
| <span data-ttu-id="2be2d-133">Windows 7、8.1、10</span><span class="sxs-lookup"><span data-stu-id="2be2d-133">Windows 7, 8.1, and 10</span></span>                            | <span data-ttu-id="2be2d-134">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-134">Supported</span></span>   | <span data-ttu-id="2be2d-135">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-135">Supported</span></span>   |
| <span data-ttu-id="2be2d-136">Windows Server 2008 R2、2012 R2、2016</span><span class="sxs-lookup"><span data-stu-id="2be2d-136">Windows Server 2008 R2, 2012 R2, 2016</span></span>             | <span data-ttu-id="2be2d-137">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-137">Supported</span></span>   | <span data-ttu-id="2be2d-138">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-138">Supported</span></span>   |
| <span data-ttu-id="2be2d-139">[Windows Server 半期チャネル][semi-annual]</span><span class="sxs-lookup"><span data-stu-id="2be2d-139">[Windows Server Semi-Annual Channel][semi-annual]</span></span> | <span data-ttu-id="2be2d-140">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-140">Supported</span></span>   | <span data-ttu-id="2be2d-141">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-141">Supported</span></span>   |
| <span data-ttu-id="2be2d-142">Ubuntu 16.04 および 18.04</span><span class="sxs-lookup"><span data-stu-id="2be2d-142">Ubuntu 16.04 and 18.04</span></span>                            | <span data-ttu-id="2be2d-143">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-143">Supported</span></span>   | <span data-ttu-id="2be2d-144">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-144">Supported</span></span>   |
| <span data-ttu-id="2be2d-145">Ubuntu 18.10 (Snap パッケージを使用)</span><span class="sxs-lookup"><span data-stu-id="2be2d-145">Ubuntu 18.10 (via Snap Package)</span></span>                   | <span data-ttu-id="2be2d-146">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="2be2d-146">Community</span></span>   | <span data-ttu-id="2be2d-147">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="2be2d-147">Community</span></span>   |
| <span data-ttu-id="2be2d-148">Ubuntu 19.04 (Snap パッケージを使用)</span><span class="sxs-lookup"><span data-stu-id="2be2d-148">Ubuntu 19.04 (via Snap Package)</span></span>                   | <span data-ttu-id="2be2d-149">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="2be2d-149">Community</span></span>   | <span data-ttu-id="2be2d-150">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="2be2d-150">Community</span></span>   |
| <span data-ttu-id="2be2d-151">Debian 9</span><span class="sxs-lookup"><span data-stu-id="2be2d-151">Debian 9</span></span>                                          | <span data-ttu-id="2be2d-152">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-152">Supported</span></span>   | <span data-ttu-id="2be2d-153">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-153">Supported</span></span>   |
| <span data-ttu-id="2be2d-154">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="2be2d-154">CentOS 7</span></span>                                          | <span data-ttu-id="2be2d-155">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-155">Supported</span></span>   | <span data-ttu-id="2be2d-156">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-156">Supported</span></span>   |
| <span data-ttu-id="2be2d-157">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="2be2d-157">Red Hat Enterprise Linux 7</span></span>                        | <span data-ttu-id="2be2d-158">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-158">Supported</span></span>   | <span data-ttu-id="2be2d-159">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-159">Supported</span></span>   |
| <span data-ttu-id="2be2d-160">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="2be2d-160">openSUSE 42.3</span></span>                                     | <span data-ttu-id="2be2d-161">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-161">Supported</span></span>   | <span data-ttu-id="2be2d-162">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-162">Supported</span></span>   |
| <span data-ttu-id="2be2d-163">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="2be2d-163">Fedora 28</span></span>                                         | <span data-ttu-id="2be2d-164">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-164">Supported</span></span>   | <span data-ttu-id="2be2d-165">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-165">Supported</span></span>   |
| <span data-ttu-id="2be2d-166">macOS 10.12 以降</span><span class="sxs-lookup"><span data-stu-id="2be2d-166">macOS 10.12+</span></span>                                      | <span data-ttu-id="2be2d-167">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-167">Supported</span></span>   | <span data-ttu-id="2be2d-168">サポート</span><span class="sxs-lookup"><span data-stu-id="2be2d-168">Supported</span></span>   |
| <span data-ttu-id="2be2d-169">Arch</span><span class="sxs-lookup"><span data-stu-id="2be2d-169">Arch</span></span>                                              | <span data-ttu-id="2be2d-170">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="2be2d-170">Community</span></span>   | <span data-ttu-id="2be2d-171">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="2be2d-171">Community</span></span>   |
| <span data-ttu-id="2be2d-172">Raspbian</span><span class="sxs-lookup"><span data-stu-id="2be2d-172">Raspbian</span></span>                                          | <span data-ttu-id="2be2d-173">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="2be2d-173">Community</span></span>   | <span data-ttu-id="2be2d-174">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="2be2d-174">Community</span></span>   |
| <span data-ttu-id="2be2d-175">Kali</span><span class="sxs-lookup"><span data-stu-id="2be2d-175">Kali</span></span>                                              | <span data-ttu-id="2be2d-176">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="2be2d-176">Community</span></span>   | <span data-ttu-id="2be2d-177">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="2be2d-177">Community</span></span>   |
| <span data-ttu-id="2be2d-178">AppImage (複数の Linux プラットフォームで機能)</span><span class="sxs-lookup"><span data-stu-id="2be2d-178">AppImage (works on multiple Linux platforms)</span></span>      | <span data-ttu-id="2be2d-179">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="2be2d-179">Community</span></span>   | <span data-ttu-id="2be2d-180">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="2be2d-180">Community</span></span>   |
| [<span data-ttu-id="2be2d-181">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="2be2d-181">Snap Package</span></span>](https://snapcraft.io/powershell)   | <span data-ttu-id="2be2d-182">注を参照</span><span class="sxs-lookup"><span data-stu-id="2be2d-182">See note</span></span>    | <span data-ttu-id="2be2d-183">注を参照</span><span class="sxs-lookup"><span data-stu-id="2be2d-183">See note</span></span>    |

> [!NOTE]
> <span data-ttu-id="2be2d-184">パッケージを実行しているディストリビューションと同様に、Snap パッケージがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2be2d-184">Snap packages are supported the same as the distribution you're running the package on.</span></span>

## <a name="powershell-releases-end-of-life"></a><span data-ttu-id="2be2d-185">PowerShell リリースのサポート終了</span><span class="sxs-lookup"><span data-stu-id="2be2d-185">PowerShell releases end-of-life</span></span>

<span data-ttu-id="2be2d-186">[PowerShell Core のライフサイクル](#lifecycle-of-powershell-core)に基づき、さまざまなリリースがサポートされなくなる日付を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="2be2d-186">Based on [Lifecycle of PowerShell Core](#lifecycle-of-powershell-core), the following table lists the dates when various releases will no longer be supported.</span></span>

| <span data-ttu-id="2be2d-187">バージョン</span><span class="sxs-lookup"><span data-stu-id="2be2d-187">Version</span></span> | <span data-ttu-id="2be2d-188">サポート終了</span><span class="sxs-lookup"><span data-stu-id="2be2d-188">End-of-life</span></span>                   |
|---------|-------------------------------|
| <span data-ttu-id="2be2d-189">6.0</span><span class="sxs-lookup"><span data-stu-id="2be2d-189">6.0</span></span>     | <span data-ttu-id="2be2d-190">2019 年 2 月 13 日</span><span class="sxs-lookup"><span data-stu-id="2be2d-190">February 13, 2019</span></span>             |
| <span data-ttu-id="2be2d-191">6.1</span><span class="sxs-lookup"><span data-stu-id="2be2d-191">6.1</span></span>     | <span data-ttu-id="2be2d-192">2019 年 9 月 28 日</span><span class="sxs-lookup"><span data-stu-id="2be2d-192">September 28, 2019</span></span>            |
| <span data-ttu-id="2be2d-193">6.2</span><span class="sxs-lookup"><span data-stu-id="2be2d-193">6.2</span></span>     | <span data-ttu-id="2be2d-194">7 のリリースから 6 か月後</span><span class="sxs-lookup"><span data-stu-id="2be2d-194">6 months after 7 releases</span></span>     |

## <a name="unsupported-platforms"></a><span data-ttu-id="2be2d-195">サポートされないプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="2be2d-195">Unsupported platforms</span></span>

<span data-ttu-id="2be2d-196">プラットフォームのバージョンが、プラットフォームの所有者によって定義された有効期限を迎えると、PowerShell Core でもそのプラットフォームのバージョンがサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="2be2d-196">When a platform version reaches end-of-life as defined by the platform owner, PowerShell Core will also cease to support that platform version.</span></span> <span data-ttu-id="2be2d-197">アクセスする必要があるユーザーは引き続き以前にリリースされたパッケージを利用できますが、公式のサポートと更新プログラムはどんな種類のものも提供されなくなります。</span><span class="sxs-lookup"><span data-stu-id="2be2d-197">Previously released packages will remain available for customers needing access but formal support and updates of any kind will no longer be provided.</span></span>

<span data-ttu-id="2be2d-198">そのため、ディストリビューションの所有者によって次のバージョンのサポートは終了され、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2be2d-198">So, the distribution owners ended support for the following versions and aren't supported.</span></span>

| <span data-ttu-id="2be2d-199">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="2be2d-199">Platform</span></span> | <span data-ttu-id="2be2d-200">バージョン</span><span class="sxs-lookup"><span data-stu-id="2be2d-200">Version</span></span> | <span data-ttu-id="2be2d-201">有効期限切れ</span><span class="sxs-lookup"><span data-stu-id="2be2d-201">End of Life</span></span>                                                                                 |
|----------|---------|---------------------------------------------------------------------------------------------|
| <span data-ttu-id="2be2d-202">Fedora</span><span class="sxs-lookup"><span data-stu-id="2be2d-202">Fedora</span></span>   | <span data-ttu-id="2be2d-203">24</span><span class="sxs-lookup"><span data-stu-id="2be2d-203">24</span></span>      | [<span data-ttu-id="2be2d-204">2017 年 8 月</span><span class="sxs-lookup"><span data-stu-id="2be2d-204">August 2017</span></span>](https://fedoramagazine.org/fedora-24-eol/)                                    |
| <span data-ttu-id="2be2d-205">Fedora</span><span class="sxs-lookup"><span data-stu-id="2be2d-205">Fedora</span></span>   | <span data-ttu-id="2be2d-206">25</span><span class="sxs-lookup"><span data-stu-id="2be2d-206">25</span></span>      | [<span data-ttu-id="2be2d-207">2017 年 12 月</span><span class="sxs-lookup"><span data-stu-id="2be2d-207">December 2017</span></span>](https://fedoramagazine.org/fedora-25-end-life/)                             |
| <span data-ttu-id="2be2d-208">Fedora</span><span class="sxs-lookup"><span data-stu-id="2be2d-208">Fedora</span></span>   | <span data-ttu-id="2be2d-209">26</span><span class="sxs-lookup"><span data-stu-id="2be2d-209">26</span></span>      | [<span data-ttu-id="2be2d-210">2018 年 5 月</span><span class="sxs-lookup"><span data-stu-id="2be2d-210">May 2018</span></span>](https://fedoramagazine.org/fedora-26-end-life/)                                  |
| <span data-ttu-id="2be2d-211">openSUSE</span><span class="sxs-lookup"><span data-stu-id="2be2d-211">openSUSE</span></span> | <span data-ttu-id="2be2d-212">42.1</span><span class="sxs-lookup"><span data-stu-id="2be2d-212">42.1</span></span>    | [<span data-ttu-id="2be2d-213">2017 年 5 月</span><span class="sxs-lookup"><span data-stu-id="2be2d-213">May 2017</span></span>](https://lists.opensuse.org/opensuse-security-announce/2017-05/msg00053.html)     |
| <span data-ttu-id="2be2d-214">openSUSE</span><span class="sxs-lookup"><span data-stu-id="2be2d-214">openSUSE</span></span> | <span data-ttu-id="2be2d-215">42.2</span><span class="sxs-lookup"><span data-stu-id="2be2d-215">42.2</span></span>    | [<span data-ttu-id="2be2d-216">2018 年 1 月</span><span class="sxs-lookup"><span data-stu-id="2be2d-216">January 2018</span></span>](https://lists.opensuse.org/opensuse-security-announce/2017-11/msg00066.html) |
| <span data-ttu-id="2be2d-217">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="2be2d-217">Ubuntu</span></span>   | <span data-ttu-id="2be2d-218">16.10</span><span class="sxs-lookup"><span data-stu-id="2be2d-218">16.10</span></span>   | [<span data-ttu-id="2be2d-219">2017 年 7 月</span><span class="sxs-lookup"><span data-stu-id="2be2d-219">July 2017</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2017-July/000223.html)        |
| <span data-ttu-id="2be2d-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="2be2d-220">Ubuntu</span></span>   | <span data-ttu-id="2be2d-221">17.04</span><span class="sxs-lookup"><span data-stu-id="2be2d-221">17.04</span></span>   | [<span data-ttu-id="2be2d-222">2018 年 1 月</span><span class="sxs-lookup"><span data-stu-id="2be2d-222">January 2018</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2018-January.txt)          |
| <span data-ttu-id="2be2d-223">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="2be2d-223">Ubuntu</span></span>   | <span data-ttu-id="2be2d-224">17.10</span><span class="sxs-lookup"><span data-stu-id="2be2d-224">17.10</span></span>   | [<span data-ttu-id="2be2d-225">2018 年 7 月</span><span class="sxs-lookup"><span data-stu-id="2be2d-225">July 2018</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2018-July/000232.html)        |
| <span data-ttu-id="2be2d-226">Debian</span><span class="sxs-lookup"><span data-stu-id="2be2d-226">Debian</span></span>   | <span data-ttu-id="2be2d-227">8</span><span class="sxs-lookup"><span data-stu-id="2be2d-227">8</span></span>       | [<span data-ttu-id="2be2d-228">2018 年 6 月</span><span class="sxs-lookup"><span data-stu-id="2be2d-228">June 2018</span></span>](https://lists.debian.org/debian-security-announce/2018/msg00132.html)           |
| <span data-ttu-id="2be2d-229">Fedora</span><span class="sxs-lookup"><span data-stu-id="2be2d-229">Fedora</span></span>   | <span data-ttu-id="2be2d-230">27</span><span class="sxs-lookup"><span data-stu-id="2be2d-230">27</span></span>      | [<span data-ttu-id="2be2d-231">2018 年 11 月</span><span class="sxs-lookup"><span data-stu-id="2be2d-231">November 2018</span></span>](https://fedoramagazine.org/fedora-27-end-of-life/)                          |
| <span data-ttu-id="2be2d-232">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="2be2d-232">Ubuntu</span></span>   | <span data-ttu-id="2be2d-233">14.04</span><span class="sxs-lookup"><span data-stu-id="2be2d-233">14.04</span></span>   | [<span data-ttu-id="2be2d-234">2019 年 4 月</span><span class="sxs-lookup"><span data-stu-id="2be2d-234">April 2019</span></span>](https://wiki.ubuntu.com/Releases)                                              |

## <a name="notes-on-licensing"></a><span data-ttu-id="2be2d-235">ライセンスに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="2be2d-235">Notes on licensing</span></span>

<span data-ttu-id="2be2d-236">PowerShell Core は [MIT ライセンス][]の下で提供されます。</span><span class="sxs-lookup"><span data-stu-id="2be2d-236">PowerShell Core is released under the [MIT license][].</span></span> <span data-ttu-id="2be2d-237">このライセンスの下で、有料サポート契約がないときは、ユーザーには[コミュニティ サポート][]のみが与えられます。</span><span class="sxs-lookup"><span data-stu-id="2be2d-237">Under this license, and without a paid support agreement, users are limited to [community support][].</span></span> <span data-ttu-id="2be2d-238">コミュニティ サポートの場合、マイクロソフトは回答や解決を保証しません。</span><span class="sxs-lookup"><span data-stu-id="2be2d-238">With community support, Microsoft makes no guarantees of responsiveness or fixes.</span></span>

## <a name="windows-powershell-module"></a><span data-ttu-id="2be2d-239">Windows PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="2be2d-239">Windows PowerShell Module</span></span>

<span data-ttu-id="2be2d-240">PowerShell Core のサポートに製品モジュールが含まれることは、そのモジュールで明示的に PowerShell Core をサポートしている場合を除いて、ありません。</span><span class="sxs-lookup"><span data-stu-id="2be2d-240">Support for PowerShell Core doesn't include product modules, unless those modules explicitly support PowerShell Core.</span></span> <span data-ttu-id="2be2d-241">たとえば、Windows Server に付属する `ActiveDirectory` モジュールを使用することはサポートの対象外です。</span><span class="sxs-lookup"><span data-stu-id="2be2d-241">For example, using the `ActiveDirectory` module that ships as part of Windows Server is an unsupported scenario.</span></span>

<span data-ttu-id="2be2d-242">ただし、明示的に PowerShell Core をサポートしていないモジュールの場合でも、場合によっては互換性があることがあります。</span><span class="sxs-lookup"><span data-stu-id="2be2d-242">However, modules that don't explicitly support PowerShell Core may be compatible in some cases.</span></span> <span data-ttu-id="2be2d-243">[`WindowsPSModulePath`][] モジュールをインストールすることで、Windows PowerShell `PSModulePath` を PowerShell Core `PSModulePath` に追加できます。</span><span class="sxs-lookup"><span data-stu-id="2be2d-243">By installing the [`WindowsPSModulePath`][] module, you can add the Windows PowerShell `PSModulePath` to your PowerShell Core `PSModulePath`.</span></span>

<span data-ttu-id="2be2d-244">最初に、PowerShell ギャラリーから `WindowsPSModulePath` モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2be2d-244">First, install the `WindowsPSModulePath` module from the PowerShell Gallery:</span></span>

```powershell
# Add `-Scope CurrentUser` if you're installing as non-admin
Install-Module WindowsPSModulePath -Force
```

<span data-ttu-id="2be2d-245">このモジュールをインストールしたら、次のように `Add-WindowsPSModulePath` コマンドレットを実行して、Windows PowerShell `PSModulePath` を PowerShell Core に追加します。</span><span class="sxs-lookup"><span data-stu-id="2be2d-245">After installing this module, run the `Add-WindowsPSModulePath` cmdlet to add the Windows PowerShell `PSModulePath` to PowerShell Core:</span></span>

```powershell
# Add this line to your profile if you always want Windows PowerShell PSModulePath
Add-WindowsPSModulePath
```

## <a name="experimental-features"></a><span data-ttu-id="2be2d-246">試験的な機能</span><span class="sxs-lookup"><span data-stu-id="2be2d-246">Experimental features</span></span>

<span data-ttu-id="2be2d-247">[試験的な機能][]には[コミュニティ サポート](#community-support)のみが与えられます。</span><span class="sxs-lookup"><span data-stu-id="2be2d-247">[Experimental features][] are limited to [community support](#community-support).</span></span>

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
