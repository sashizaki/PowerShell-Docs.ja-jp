---
title: PowerShell Core のサポート ライフサイクル
description: PowerShell Core のサポートを管理するポリシー
ms.date: 08/06/2018
ms.openlocfilehash: 178e5c43520f9a392ca219b9f785eb18b1ec5436
ms.sourcegitcommit: f268dce5b5e72be669be0c6634b8db11369bbae2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58623860"
---
# <a name="powershell-core-support-lifecycle"></a><span data-ttu-id="d887b-103">PowerShell Core のサポート ライフサイクル</span><span class="sxs-lookup"><span data-stu-id="d887b-103">PowerShell Core Support Lifecycle</span></span>

<span data-ttu-id="d887b-104">PowerShell Core は、Windows PowerShell とは別に出荷され、インストールされ、構成される別個のツール セットであり、コンポーネント セットです。</span><span class="sxs-lookup"><span data-stu-id="d887b-104">PowerShell Core is a distinct set of tools and components that is shipped, installed, and configured separately from Windows PowerShell.</span></span>
<span data-ttu-id="d887b-105">そのため、PowerShell Core は Windows 7/8.1/10 や Windows Server のライセンス契約には含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d887b-105">So, PowerShell Core is not included in the Windows 7/8.1/10 or Windows Server licensing agreements.</span></span>

<span data-ttu-id="d887b-106">ただし、PowerShell Core は、[Premier][]、[Microsoft Enterprise Agreements][enterprise-agreement]、[マイクロソフト ソフトウェア アシュアランス][assurance]など、従来の Microsoft サポート契約ではサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d887b-106">However, PowerShell Core is supported under traditional Microsoft support agreements, including [Premier][], [Microsoft Enterprise Agreements][enterprise-agreement], and [Microsoft Software Assurance][assurance].</span></span>
<span data-ttu-id="d887b-107">サポート依頼で問題を報告して PowerShell Core の[サポート][]を受け、それに対して支払うこともできます。</span><span class="sxs-lookup"><span data-stu-id="d887b-107">You can also pay for [assisted support][] for PowerShell Core by filing a support request for your problem.</span></span>

## <a name="community-support"></a><span data-ttu-id="d887b-108">コミュニティ サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-108">Community Support</span></span>

<span data-ttu-id="d887b-109">GitHub でも[コミュニティ サポート][]を用意しています。問題やバグを報告したり、機能を要望したりできます。</span><span class="sxs-lookup"><span data-stu-id="d887b-109">We also offer [community support][] on GitHub where you can file an issue, bug, or feature request.</span></span>
<span data-ttu-id="d887b-110">また、一般的な [Microsoft コミュニティ][]や Microsoft [PowerShell Tech コミュニティ][]で他のコミュニティ メンバーがサポートしてくれる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d887b-110">Also, you may find help from other members of the community on the general [Microsoft Community][] or the Microsoft [PowerShell Tech Community][].</span></span>
<span data-ttu-id="d887b-111">コミュニティによりご自身の問題が短期間で対処または解決されることは保証できません。</span><span class="sxs-lookup"><span data-stu-id="d887b-111">We offer no guarantee there that the community will address or resolve your issue in a timely manner.</span></span>
<span data-ttu-id="d887b-112">早急な対応が必要な問題の場合、従来の有料サポートをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="d887b-112">If you have a problem that requires immediate attention, you should use the traditional, paid support options.</span></span>

## <a name="lifecycle-of-powershell-core"></a><span data-ttu-id="d887b-113">PowerShell Core のライフサイクル</span><span class="sxs-lookup"><span data-stu-id="d887b-113">Lifecycle of PowerShell Core</span></span>

<span data-ttu-id="d887b-114">PowerShell Core には、[Microsoft Modern Lifecycle Policy][modern] が導入されています。</span><span class="sxs-lookup"><span data-stu-id="d887b-114">PowerShell Core is adopting the [Microsoft Modern Lifecycle Policy][modern].</span></span>
<span data-ttu-id="d887b-115">このサポート ライフサイクルでは、最新バージョンで最新の機能を常に提供します。</span><span class="sxs-lookup"><span data-stu-id="d887b-115">This support lifecycle is intended to keep customers up-to-date with the latest versions.</span></span>

<span data-ttu-id="d887b-116">PowerShell Core のバージョン 6.x ブランチは約半年に一回更新されます (例:6.0、6.1、6.2 など。)</span><span class="sxs-lookup"><span data-stu-id="d887b-116">The version 6.x branch of PowerShell Core will be updated approximately once every six months (examples: 6.0, 6.1, 6.2, etc.)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d887b-117">引き続きサポートを受けるには、新しいマイナー バージョンの公開後、6 か月以内に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d887b-117">You must update within six months after each new minor version release to continue receiving support.</span></span>

<span data-ttu-id="d887b-118">たとえば、PowerShell Core 6.1 が 2018 年 7 月 1 日に公開された場合、サポートを維持するには、2019 年 1 月 1 日までに PowerShell Core 6.1 に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d887b-118">For example, if PowerShell Core 6.1 is released on July 1, 2018, you would be expected to update to PowerShell Core 6.1 by January 1, 2019 to maintain support.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d887b-119">サポートを受け続けるには、それぞれの新しいパッチ バージョンのリリース後 30 日以内に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d887b-119">You must update within 30 days after each new patch version release to continue receiving support.</span></span>

<span data-ttu-id="d887b-120">たとえば、PowerShell Core 6.1 を実行していて 2019 年 2 月 19 日に 6.1.3 がリリースされた場合、サポートを維持するには、リリースの 30 日後である 2019 年 3 月 21 日までに PowerShell Core 6.1.3 に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d887b-120">For example, If you are running PowerShell Core 6.1 and 6.1.3 was released on February 19, 2019, you would be expected to update to PowerShell Core 6.1.3 by March 21, 2019, which is 30 days after the release to maintain support.</span></span>
<span data-ttu-id="d887b-121">必要な修正プログラムが見つかった場合、その修正プログラムは次の累積的な更新プログラムでリリースされます。</span><span class="sxs-lookup"><span data-stu-id="d887b-121">If any fixes are found to be required, the fixes will be released in our next cumulative update.</span></span>

![PowerShell Core のブランチ ライフサイクル][lifecycle-chart]

<span data-ttu-id="d887b-123">Modern Lifecycle Policy では、製品 (つまり、PowerShell Core) のサポートを終了する 12 か月前にお客様に通知することを Microsoft の義務としています。</span><span class="sxs-lookup"><span data-stu-id="d887b-123">The Modern Lifecycle Policy also requires that Microsoft give customers 12 months notice before discontinuing support for a product (that is, PowerShell Core).</span></span>

<span data-ttu-id="d887b-124">最終的に、PowerShell Core では "長期サービス" のアプローチを採用する予定です。</span><span class="sxs-lookup"><span data-stu-id="d887b-124">Eventually, we expect PowerShell Core will adopt the "long-term servicing" approach.</span></span>
<span data-ttu-id="d887b-125">このサービスのアプローチでは、特定のブランチ/バージョン の 6.x のサポートを維持するために、サービスとセキュリティの更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d887b-125">In this servicing approach, we would require only servicing and security updates to stay in support on a specific branch/version of 6.x.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="d887b-126">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="d887b-126">Supported platforms</span></span>

<span data-ttu-id="d887b-127">お使いの PowerShell Core のバージョンが公式にサポートされているプラットフォームについては、次の表をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d887b-127">The following table to see what platform the version of PowerShell Core you are using is officially supported.</span></span>

<span data-ttu-id="d887b-128">また、弊社のコミュニティでも一部のプラットフォームに向けたパッケージを提供していますが、これらは正式にはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d887b-128">Our community has also contributed packages for some platforms, but they are not officially supported.</span></span>
<span data-ttu-id="d887b-129">これらのパッケージは、表の中で `Community` とマークされています。</span><span class="sxs-lookup"><span data-stu-id="d887b-129">These packages are marked as `Community` in the table.</span></span>

<span data-ttu-id="d887b-130">`Experimental` としてリストされているプラットフォームは、正式にはサポートされていませんが、実験とフィードバックのために使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d887b-130">Platforms listed as `Experimental` are not officially supported, but are available for experimentation and feedback.</span></span>

|                                                   | <span data-ttu-id="d887b-131">6.1</span><span class="sxs-lookup"><span data-stu-id="d887b-131">6.1</span></span>         | <span data-ttu-id="d887b-132">6.2</span><span class="sxs-lookup"><span data-stu-id="d887b-132">6.2</span></span>         |
|---------------------------------------------------|:-----------:|:-----------:|
| <span data-ttu-id="d887b-133">Windows 7、8.1、10</span><span class="sxs-lookup"><span data-stu-id="d887b-133">Windows 7, 8.1, and 10</span></span>                            | <span data-ttu-id="d887b-134">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-134">Supported</span></span>   | <span data-ttu-id="d887b-135">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-135">Supported</span></span>   |
| <span data-ttu-id="d887b-136">Windows Server 2008 R2、2012 R2、2016</span><span class="sxs-lookup"><span data-stu-id="d887b-136">Windows Server 2008 R2, 2012 R2, 2016</span></span>             | <span data-ttu-id="d887b-137">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-137">Supported</span></span>   | <span data-ttu-id="d887b-138">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-138">Supported</span></span>   |
| <span data-ttu-id="d887b-139">[Windows Server 半期チャネル][semi-annual]</span><span class="sxs-lookup"><span data-stu-id="d887b-139">[Windows Server Semi-Annual Channel][semi-annual]</span></span> | <span data-ttu-id="d887b-140">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-140">Supported</span></span>   | <span data-ttu-id="d887b-141">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-141">Supported</span></span>   |
| <span data-ttu-id="d887b-142">Ubuntu 16.04 および 18.04</span><span class="sxs-lookup"><span data-stu-id="d887b-142">Ubuntu 16.04 and 18.04</span></span>                            | <span data-ttu-id="d887b-143">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-143">Supported</span></span>   | <span data-ttu-id="d887b-144">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-144">Supported</span></span>   |
| <span data-ttu-id="d887b-145">Ubuntu 18.10 (Snap パッケージを使用)</span><span class="sxs-lookup"><span data-stu-id="d887b-145">Ubuntu 18.10 (via Snap Package)</span></span>                   | <span data-ttu-id="d887b-146">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="d887b-146">Community</span></span>   | <span data-ttu-id="d887b-147">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="d887b-147">Community</span></span>   |
| <span data-ttu-id="d887b-148">Debian 9</span><span class="sxs-lookup"><span data-stu-id="d887b-148">Debian 9</span></span>                                          | <span data-ttu-id="d887b-149">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-149">Supported</span></span>   | <span data-ttu-id="d887b-150">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-150">Supported</span></span>   |
| <span data-ttu-id="d887b-151">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="d887b-151">CentOS 7</span></span>                                          | <span data-ttu-id="d887b-152">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-152">Supported</span></span>   | <span data-ttu-id="d887b-153">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-153">Supported</span></span>   |
| <span data-ttu-id="d887b-154">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="d887b-154">Red Hat Enterprise Linux 7</span></span>                        | <span data-ttu-id="d887b-155">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-155">Supported</span></span>   | <span data-ttu-id="d887b-156">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-156">Supported</span></span>   |
| <span data-ttu-id="d887b-157">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="d887b-157">openSUSE 42.3</span></span>                                     | <span data-ttu-id="d887b-158">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-158">Supported</span></span>   | <span data-ttu-id="d887b-159">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-159">Supported</span></span>   |
| <span data-ttu-id="d887b-160">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="d887b-160">Fedora 28</span></span>                                         | <span data-ttu-id="d887b-161">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-161">Supported</span></span>   | <span data-ttu-id="d887b-162">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-162">Supported</span></span>   |
| <span data-ttu-id="d887b-163">macOS 10.12 以降</span><span class="sxs-lookup"><span data-stu-id="d887b-163">macOS 10.12+</span></span>                                      | <span data-ttu-id="d887b-164">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-164">Supported</span></span>   | <span data-ttu-id="d887b-165">サポート</span><span class="sxs-lookup"><span data-stu-id="d887b-165">Supported</span></span>   |
| <span data-ttu-id="d887b-166">Arch</span><span class="sxs-lookup"><span data-stu-id="d887b-166">Arch</span></span>                                              | <span data-ttu-id="d887b-167">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="d887b-167">Community</span></span>   | <span data-ttu-id="d887b-168">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="d887b-168">Community</span></span>   |
| <span data-ttu-id="d887b-169">Raspbian</span><span class="sxs-lookup"><span data-stu-id="d887b-169">Raspbian</span></span>                                          | <span data-ttu-id="d887b-170">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="d887b-170">Community</span></span>   | <span data-ttu-id="d887b-171">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="d887b-171">Community</span></span>   |
| <span data-ttu-id="d887b-172">Kali</span><span class="sxs-lookup"><span data-stu-id="d887b-172">Kali</span></span>                                              | <span data-ttu-id="d887b-173">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="d887b-173">Community</span></span>   | <span data-ttu-id="d887b-174">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="d887b-174">Community</span></span>   |
| <span data-ttu-id="d887b-175">AppImage (複数の Linux プラットフォームで機能)</span><span class="sxs-lookup"><span data-stu-id="d887b-175">AppImage  (works on multiple Linux platforms)</span></span>     | <span data-ttu-id="d887b-176">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="d887b-176">Community</span></span>   | <span data-ttu-id="d887b-177">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="d887b-177">Community</span></span>   |
| [<span data-ttu-id="d887b-178">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="d887b-178">Snap Package</span></span>](https://snapcraft.io/powershell)   | <span data-ttu-id="d887b-179">注を参照</span><span class="sxs-lookup"><span data-stu-id="d887b-179">See note</span></span>    | <span data-ttu-id="d887b-180">注を参照</span><span class="sxs-lookup"><span data-stu-id="d887b-180">See note</span></span>    |

> [!NOTE]
> <span data-ttu-id="d887b-181">パッケージを実行しているディストリビューションと同様に、スナップ パッケージがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d887b-181">Snap packages are supported the same as the distribution you are running the package on.</span></span>

## <a name="powershell-release-end-of-life"></a><span data-ttu-id="d887b-182">PowerShell リリースのサポート終了</span><span class="sxs-lookup"><span data-stu-id="d887b-182">PowerShell release end of life</span></span>

<span data-ttu-id="d887b-183">[PowerShell Core のライフサイクル](#lifecycle-of-powershell-core)に基づき、さまざまなリリースがサポートされなくなる日付を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="d887b-183">Based on [Lifecycle of PowerShell Core](#lifecycle-of-powershell-core), the following table lists the dates when various release will no longer be supported.</span></span>

| <span data-ttu-id="d887b-184">バージョン</span><span class="sxs-lookup"><span data-stu-id="d887b-184">Version</span></span> | <span data-ttu-id="d887b-185">サポート終了</span><span class="sxs-lookup"><span data-stu-id="d887b-185">End Of Life</span></span>                   |
|---------|-------------------------------|
| <span data-ttu-id="d887b-186">6.0</span><span class="sxs-lookup"><span data-stu-id="d887b-186">6.0</span></span>     | <span data-ttu-id="d887b-187">2019 年 2 月 13 日</span><span class="sxs-lookup"><span data-stu-id="d887b-187">February 13, 2019</span></span>             |
| <span data-ttu-id="d887b-188">6.1</span><span class="sxs-lookup"><span data-stu-id="d887b-188">6.1</span></span>     | <span data-ttu-id="d887b-189">2019 年 9 月 28 日</span><span class="sxs-lookup"><span data-stu-id="d887b-189">September 28, 2019</span></span>            |
| <span data-ttu-id="d887b-190">6.2</span><span class="sxs-lookup"><span data-stu-id="d887b-190">6.2</span></span>     | <span data-ttu-id="d887b-191">6.3 のリリースから 6 か月後</span><span class="sxs-lookup"><span data-stu-id="d887b-191">6 months after 6.3 releases</span></span>   |

## <a name="platforms-which-are-out-of-support"></a><span data-ttu-id="d887b-192">サポート対象外のプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="d887b-192">Platforms, which are out of support</span></span>

<span data-ttu-id="d887b-193">プラットフォームのバージョンが、プラットフォームの所有者によって定義された有効期限を迎えると、PowerShell Core でもそのプラットフォームのバージョンがサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="d887b-193">When a platform version reaches end-of-life as defined by the platform owner, PowerShell Core will also cease to support that platform version.</span></span>
<span data-ttu-id="d887b-194">アクセスする必要があるユーザーは引き続き以前にリリースされたパッケージを利用できますが、公式のサポートと更新プログラムはどんな種類のものも提供されなくなります。</span><span class="sxs-lookup"><span data-stu-id="d887b-194">Previously released packages will remain available for customers needing access but formal support and updates of any kind will no longer be provided.</span></span>

<span data-ttu-id="d887b-195">そのため、ディストリビューションの所有者によって次のバージョンのサポートは終了され、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d887b-195">So, the distribution owners ended support for the following versions and are not supported.</span></span>

| <span data-ttu-id="d887b-196">OS</span><span class="sxs-lookup"><span data-stu-id="d887b-196">OS</span></span>       | <span data-ttu-id="d887b-197">バージョン</span><span class="sxs-lookup"><span data-stu-id="d887b-197">Version</span></span> | <span data-ttu-id="d887b-198">有効期限切れ</span><span class="sxs-lookup"><span data-stu-id="d887b-198">End of Life</span></span>                                                                                 |
|----------|---------|---------------------------------------------------------------------------------------------|
| <span data-ttu-id="d887b-199">Fedora</span><span class="sxs-lookup"><span data-stu-id="d887b-199">Fedora</span></span>   | <span data-ttu-id="d887b-200">24</span><span class="sxs-lookup"><span data-stu-id="d887b-200">24</span></span>      | [<span data-ttu-id="d887b-201">2017 年 8 月</span><span class="sxs-lookup"><span data-stu-id="d887b-201">August 2017</span></span>](https://fedoramagazine.org/fedora-24-eol/)                                    |
| <span data-ttu-id="d887b-202">Fedora</span><span class="sxs-lookup"><span data-stu-id="d887b-202">Fedora</span></span>   | <span data-ttu-id="d887b-203">25</span><span class="sxs-lookup"><span data-stu-id="d887b-203">25</span></span>      | [<span data-ttu-id="d887b-204">2017 年 12 月</span><span class="sxs-lookup"><span data-stu-id="d887b-204">December 2017</span></span>](https://fedoramagazine.org/fedora-25-end-life/)                             |
| <span data-ttu-id="d887b-205">Fedora</span><span class="sxs-lookup"><span data-stu-id="d887b-205">Fedora</span></span>   | <span data-ttu-id="d887b-206">26</span><span class="sxs-lookup"><span data-stu-id="d887b-206">26</span></span>      | [<span data-ttu-id="d887b-207">2018 年 5 月</span><span class="sxs-lookup"><span data-stu-id="d887b-207">May 2018</span></span>](https://fedoramagazine.org/fedora-26-end-life/)                                  |
| <span data-ttu-id="d887b-208">openSUSE</span><span class="sxs-lookup"><span data-stu-id="d887b-208">openSUSE</span></span> | <span data-ttu-id="d887b-209">42.1</span><span class="sxs-lookup"><span data-stu-id="d887b-209">42.1</span></span>    | [<span data-ttu-id="d887b-210">2017 年 5 月</span><span class="sxs-lookup"><span data-stu-id="d887b-210">May 2017</span></span>](https://lists.opensuse.org/opensuse-security-announce/2017-05/msg00053.html)     |
| <span data-ttu-id="d887b-211">openSUSE</span><span class="sxs-lookup"><span data-stu-id="d887b-211">openSUSE</span></span> | <span data-ttu-id="d887b-212">42.2</span><span class="sxs-lookup"><span data-stu-id="d887b-212">42.2</span></span>    | [<span data-ttu-id="d887b-213">2018 年 1 月</span><span class="sxs-lookup"><span data-stu-id="d887b-213">January 2018</span></span>](https://lists.opensuse.org/opensuse-security-announce/2017-11/msg00066.html) |
| <span data-ttu-id="d887b-214">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d887b-214">Ubuntu</span></span>   | <span data-ttu-id="d887b-215">16.10</span><span class="sxs-lookup"><span data-stu-id="d887b-215">16.10</span></span>   | [<span data-ttu-id="d887b-216">2017 年 7 月</span><span class="sxs-lookup"><span data-stu-id="d887b-216">July 2017</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2017-July/000223.html)        |
| <span data-ttu-id="d887b-217">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d887b-217">Ubuntu</span></span>   | <span data-ttu-id="d887b-218">17.04</span><span class="sxs-lookup"><span data-stu-id="d887b-218">17.04</span></span>   | [<span data-ttu-id="d887b-219">2018 年 1 月</span><span class="sxs-lookup"><span data-stu-id="d887b-219">January 2018</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2018-January.txt)          |
| <span data-ttu-id="d887b-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d887b-220">Ubuntu</span></span>   | <span data-ttu-id="d887b-221">17.10</span><span class="sxs-lookup"><span data-stu-id="d887b-221">17.10</span></span>   | [<span data-ttu-id="d887b-222">2018 年 7 月</span><span class="sxs-lookup"><span data-stu-id="d887b-222">July 2018</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2018-July/000232.html)        |
| <span data-ttu-id="d887b-223">Debian</span><span class="sxs-lookup"><span data-stu-id="d887b-223">Debian</span></span>   | <span data-ttu-id="d887b-224">8</span><span class="sxs-lookup"><span data-stu-id="d887b-224">8</span></span>       | [<span data-ttu-id="d887b-225">2018 年 6 月</span><span class="sxs-lookup"><span data-stu-id="d887b-225">June 2018</span></span>](https://lists.debian.org/debian-security-announce/2018/msg00132.html)           |
| <span data-ttu-id="d887b-226">Fedora</span><span class="sxs-lookup"><span data-stu-id="d887b-226">Fedora</span></span>   | <span data-ttu-id="d887b-227">27</span><span class="sxs-lookup"><span data-stu-id="d887b-227">27</span></span>      | [<span data-ttu-id="d887b-228">2018 年 11 月</span><span class="sxs-lookup"><span data-stu-id="d887b-228">November 2018</span></span>](https://fedoramagazine.org/fedora-27-end-of-life/)                          |
| <span data-ttu-id="d887b-229">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d887b-229">Ubuntu</span></span>   | <span data-ttu-id="d887b-230">14.04</span><span class="sxs-lookup"><span data-stu-id="d887b-230">14.04</span></span>   | [<span data-ttu-id="d887b-231">2019 年 4 月</span><span class="sxs-lookup"><span data-stu-id="d887b-231">April 2019</span></span>](https://wiki.ubuntu.com/Releases)                                              |

## <a name="notes-on-licensing"></a><span data-ttu-id="d887b-232">ライセンスに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="d887b-232">Notes on licensing</span></span>

<span data-ttu-id="d887b-233">PowerShell Core は [MIT ライセンス][]の下で提供されます。</span><span class="sxs-lookup"><span data-stu-id="d887b-233">PowerShell Core is released under the [MIT license][].</span></span>
<span data-ttu-id="d887b-234">このライセンスの下で、有料サポート契約がないときは、ユーザーには[コミュニティ サポート][]のみが与えられます。</span><span class="sxs-lookup"><span data-stu-id="d887b-234">Under this license, and without a paid support agreement, users are limited to [community support][].</span></span>
<span data-ttu-id="d887b-235">コミュニティ サポートの場合、マイクロソフトは回答や解決を保証しません。</span><span class="sxs-lookup"><span data-stu-id="d887b-235">With community support, Microsoft makes no guarantees of responsiveness or fixes.</span></span>

## <a name="windows-powershell-module"></a><span data-ttu-id="d887b-236">Windows PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="d887b-236">Windows PowerShell Module</span></span>

<span data-ttu-id="d887b-237">PowerShell Core のサポートに製品モジュールが含まれることは、そのモジュールで明示的に PowerShell Core をサポートしている場合を除いて、ありません。</span><span class="sxs-lookup"><span data-stu-id="d887b-237">Support for PowerShell Core does not include product modules, unless those modules explicitly support PowerShell Core.</span></span>
<span data-ttu-id="d887b-238">たとえば、Windows Server に付属する `ActiveDirectory` モジュールを使用することはサポートの対象外です。</span><span class="sxs-lookup"><span data-stu-id="d887b-238">For example, using the `ActiveDirectory` module that ships as part of Windows Server is an unsupported scenario.</span></span>

<span data-ttu-id="d887b-239">ただし、PowerShell Core 対応であることが明示されていないモジュールの場合でも、サポート対象となることがあります。</span><span class="sxs-lookup"><span data-stu-id="d887b-239">However, modules that do not explicitly support PowerShell Core may be compatible in some cases.</span></span>
<span data-ttu-id="d887b-240">[`WindowsPSModulePath`][] モジュールをインストールすることで、Windows PowerShell `PSModulePath` を PowerShell Core `PSModulePath` に追加できます。</span><span class="sxs-lookup"><span data-stu-id="d887b-240">By installing the [`WindowsPSModulePath`][] module, you can add the Windows PowerShell `PSModulePath` to your PowerShell Core `PSModulePath`.</span></span>

<span data-ttu-id="d887b-241">最初に、PowerShell ギャラリーから `WindowsPSModulePath` モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d887b-241">First, install the `WindowsPSModulePath` module from the PowerShell Gallery:</span></span>

```powershell
# Add `-Scope CurrentUser` if you're installing as non-admin
Install-Module WindowsPSModulePath -Force
```

<span data-ttu-id="d887b-242">このモジュールをインストールしたら、次のように `Add-WindowsPSModulePath` コマンドレットを実行して、Windows PowerShell `PSModulePath` を PowerShell Core に追加します。</span><span class="sxs-lookup"><span data-stu-id="d887b-242">After installing this module, run the `Add-WindowsPSModulePath` cmdlet to add the Windows PowerShell `PSModulePath` to PowerShell Core:</span></span>

```powershell
# Add this line to your profile if you always want Windows PowerShell PSModulePath
Add-WindowsPSModulePath
```

## <a name="experimental-features"></a><span data-ttu-id="d887b-243">試験的な機能</span><span class="sxs-lookup"><span data-stu-id="d887b-243">Experimental features</span></span>

<span data-ttu-id="d887b-244">[試験的な機能][]には[コミュニティ サポート](#community-support)のみが与えられます。</span><span class="sxs-lookup"><span data-stu-id="d887b-244">[Experimental features][] are limited to [community support](#community-support).</span></span>

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
