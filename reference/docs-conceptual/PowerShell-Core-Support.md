# <a name="powershell-core-support-lifecycle"></a><span data-ttu-id="12c27-101">PowerShell Core のサポート ライフサイクル</span><span class="sxs-lookup"><span data-stu-id="12c27-101">PowerShell Core Support Lifecycle</span></span>

<span data-ttu-id="12c27-102">PowerShell Core は、Windows PowerShell とは別に出荷され、インストールされ、構成される別個のツール セットであり、コンポーネント セットです。</span><span class="sxs-lookup"><span data-stu-id="12c27-102">PowerShell Core is a distinct set of tools and components that is shipped, installed, and configured separately from Windows PowerShell.</span></span>
<span data-ttu-id="12c27-103">そのため、PowerShell Core は Windows 7/8.1/10 や Windows Server のライセンス契約には含まれていません。</span><span class="sxs-lookup"><span data-stu-id="12c27-103">Therefore, PowerShell Core is not included in the Windows 7/8.1/10 or Windows Server licensing agreements.</span></span>

<span data-ttu-id="12c27-104">ただし、PowerShell Core は、[Premier][]、[Microsoft Enterprise Agreements][enterprise-agreement]、[マイクロソフト ソフトウェア アシュアランス][assurance]など、従来の Microsoft サポート契約ではサポートされています。</span><span class="sxs-lookup"><span data-stu-id="12c27-104">However, PowerShell Core is supported under traditional Microsoft support agreements, including [Premier][], [Microsoft Enterprise Agreements][enterprise-agreement], and [Microsoft Software Assurance][assurance].</span></span>
<span data-ttu-id="12c27-105">サポート依頼で問題を報告して PowerShell Core の[サポート][]を受け、それに対して支払うこともできます。</span><span class="sxs-lookup"><span data-stu-id="12c27-105">You can also pay for [assisted support][] for PowerShell Core by filing a support request for your problem.</span></span>

<span data-ttu-id="12c27-106">GitHub でも[コミュニティ サポート][]を用意しています。問題やバグを報告したり、機能を要望したりできます。</span><span class="sxs-lookup"><span data-stu-id="12c27-106">We also offer [community support][] on GitHub where you can file an issue, bug, or feature request.</span></span>
<span data-ttu-id="12c27-107">あるいは、一般的な [Microsoft コミュニティ][]や Microsoft [PowerShell Tech コミュニティ][]で他のコミュニティ メンバーが助けてくれることがあります。</span><span class="sxs-lookup"><span data-stu-id="12c27-107">Alternatively, you may find help from other members of the community on the general [Microsoft Community][] or the Microsoft [PowerShell Tech Community][].</span></span>
<span data-ttu-id="12c27-108">問題が短期間で解決されることは保証できません。</span><span class="sxs-lookup"><span data-stu-id="12c27-108">We offer no guarantee there that your issue will be addressed or resolved in a timely manner.</span></span>
<span data-ttu-id="12c27-109">早急な対応が必要な問題の場合、従来の有料サポートをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="12c27-109">If you have a problem that requires immediate attention, you should use the traditional, paid support options.</span></span>

## <a name="lifecycle-of-powershell-core"></a><span data-ttu-id="12c27-110">PowerShell Core のライフサイクル</span><span class="sxs-lookup"><span data-stu-id="12c27-110">Lifecycle of PowerShell Core</span></span>

<span data-ttu-id="12c27-111">PowerShell Core には、[Microsoft Modern Lifecycle Policy][modern] が導入されています。</span><span class="sxs-lookup"><span data-stu-id="12c27-111">PowerShell Core is adopting the [Microsoft Modern Lifecycle Policy][modern].</span></span>
<span data-ttu-id="12c27-112">このサポート ライフサイクルでは、最新バージョンで最新の機能を常に提供します。</span><span class="sxs-lookup"><span data-stu-id="12c27-112">This support lifecycle is intended to keep customers up-to-date with the latest versions.</span></span>

<span data-ttu-id="12c27-113">PowerShell Core のバージョン 6.x ブランチは約半年に一回更新されます (6.0、6.1、6.2 など)</span><span class="sxs-lookup"><span data-stu-id="12c27-113">The version 6.x branch of PowerShell Core will be updated approximately once every six months (e.g. 6.0, 6.1, 6.2, etc.)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="12c27-114">引き続きサポートを受けるには、新しいマイナー バージョンの公開後、6 か月以内に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12c27-114">You must update within six months after each new minor version release to continue receiving support.</span></span>

<span data-ttu-id="12c27-115">たとえば、PowerShell Core 6.1 が 2018 年 7 月 1 日に公開された場合、サポートを維持するには、2019 年 1 月 1 日までに PowerShell Core 6.1 に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12c27-115">For example, if PowerShell Core 6.1 is released on July 1st, 2018, you would be expected to update to PowerShell Core 6.1 by January 1st, 2019 to maintain support.</span></span>

![PowerShell Core のブランチ ライフサイクル][lifecycle-chart]

<span data-ttu-id="12c27-117">Modern Lifecycle Policy では、製品 (つまり、PowerShell Core) のサポートを終了する 12 か月前にお客様に通知することをマイクロソフトの義務としています。</span><span class="sxs-lookup"><span data-stu-id="12c27-117">The Modern Lifecycle Policy also requires that Microsoft give customers 12 months notice before discontinuing support for a product (i.e. PowerShell Core).</span></span>

<span data-ttu-id="12c27-118">ゆくゆくは PowerShell Core に "Long Term Servicing" 手法を導入することをマイクロソフトは期待しています。この手法では、特定の 6.x ブランチ/バージョンのサポートを維持するために、サービス更新とセキュリティ更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="12c27-118">Eventually, we expect PowerShell Core will adopt the "long-term servicing" approach where we would require only servicing and security updates to stay in support on a specific branch/version of 6.x.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="12c27-119">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="12c27-119">Supported platforms</span></span>

<span data-ttu-id="12c27-120">お使いの PowerShell Core のバージョンが公式にサポートされているプラットフォームを確認するには、次の表をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="12c27-120">Please see the following table to see what platform the version of PowerShell Core you are using is officially supported.</span></span>

<span data-ttu-id="12c27-121">また、弊社のコミュニティでも一部のプラットフォームに向けたパッケージを提供していますが、これらは正式にはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="12c27-121">Our community has also contributed packages for some platforms, but they are not officially supported.</span></span>
<span data-ttu-id="12c27-122">これらのパッケージは、表の中で `Community` とマークされています。</span><span class="sxs-lookup"><span data-stu-id="12c27-122">These packages are marked as `Community` in the table.</span></span>

<span data-ttu-id="12c27-123">`Experimental` としてリストされているプラットフォームは、正式にはサポートされていませんが、実験とフィードバックのために使用することができます。</span><span class="sxs-lookup"><span data-stu-id="12c27-123">Platforms listed as `Experimental` are not officially supported, but are available for experimentation and feedback.</span></span>

|                                                   | <span data-ttu-id="12c27-124">6.0</span><span class="sxs-lookup"><span data-stu-id="12c27-124">6.0</span></span>         | <span data-ttu-id="12c27-125">6.1</span><span class="sxs-lookup"><span data-stu-id="12c27-125">6.1</span></span>         |
|---------------------------------------------------|:-----------:|:-----------:|
| <span data-ttu-id="12c27-126">Windows 7、8.1、10</span><span class="sxs-lookup"><span data-stu-id="12c27-126">Windows 7, 8.1, and 10</span></span>                            | <span data-ttu-id="12c27-127">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-127">Supported</span></span>   | <span data-ttu-id="12c27-128">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-128">Supported</span></span>   |
| <span data-ttu-id="12c27-129">Windows Server 2008 R2、2012 R2、2016</span><span class="sxs-lookup"><span data-stu-id="12c27-129">Windows Server 2008 R2, 2012 R2, 2016</span></span>             | <span data-ttu-id="12c27-130">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-130">Supported</span></span>   | <span data-ttu-id="12c27-131">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-131">Supported</span></span>   |
| <span data-ttu-id="12c27-132">[Windows Server 半期チャネル][semi-annual]</span><span class="sxs-lookup"><span data-stu-id="12c27-132">[Windows Server Semi-Annual Channel][semi-annual]</span></span> | <span data-ttu-id="12c27-133">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-133">Supported</span></span>   | <span data-ttu-id="12c27-134">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-134">Supported</span></span>   |
| <span data-ttu-id="12c27-135">Ubuntu 14.04 および 16.04</span><span class="sxs-lookup"><span data-stu-id="12c27-135">Ubuntu 14.04 and, 16.04</span></span>                           | <span data-ttu-id="12c27-136">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-136">Supported</span></span>   | <span data-ttu-id="12c27-137">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-137">Supported</span></span>   |
| <span data-ttu-id="12c27-138">Ubuntu 17.10、および 18.04</span><span class="sxs-lookup"><span data-stu-id="12c27-138">Ubuntu 17.10, and 18.04</span></span>                           |             | <span data-ttu-id="12c27-139">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-139">Supported</span></span>   |
| <span data-ttu-id="12c27-140">Debian 8.7 以降および 9</span><span class="sxs-lookup"><span data-stu-id="12c27-140">Debian 8.7+, and 9</span></span>                                | <span data-ttu-id="12c27-141">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-141">Supported</span></span>   | <span data-ttu-id="12c27-142">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-142">Supported</span></span>   |
| <span data-ttu-id="12c27-143">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="12c27-143">CentOS 7</span></span>                                          | <span data-ttu-id="12c27-144">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-144">Supported</span></span>   | <span data-ttu-id="12c27-145">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-145">Supported</span></span>   |
| <span data-ttu-id="12c27-146">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="12c27-146">Red Hat Enterprise Linux 7</span></span>                        | <span data-ttu-id="12c27-147">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-147">Supported</span></span>   | <span data-ttu-id="12c27-148">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-148">Supported</span></span>   |
| <span data-ttu-id="12c27-149">OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="12c27-149">OpenSUSE 42.3</span></span>                                     | <span data-ttu-id="12c27-150">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-150">Supported</span></span>   | <span data-ttu-id="12c27-151">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-151">Supported</span></span>   |
| <span data-ttu-id="12c27-152">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="12c27-152">Fedora 27</span></span>                                         | <span data-ttu-id="12c27-153">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-153">Supported</span></span>   | <span data-ttu-id="12c27-154">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-154">Supported</span></span>   |
| <span data-ttu-id="12c27-155">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="12c27-155">Fedora 28</span></span>                                         |             | <span data-ttu-id="12c27-156">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-156">Supported</span></span>   |
| <span data-ttu-id="12c27-157">macOS 10.12 以降</span><span class="sxs-lookup"><span data-stu-id="12c27-157">macOS 10.12+</span></span>                                      | <span data-ttu-id="12c27-158">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-158">Supported</span></span>   | <span data-ttu-id="12c27-159">サポート</span><span class="sxs-lookup"><span data-stu-id="12c27-159">Supported</span></span>   |
| <span data-ttu-id="12c27-160">Arch</span><span class="sxs-lookup"><span data-stu-id="12c27-160">Arch</span></span>                                              | <span data-ttu-id="12c27-161">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="12c27-161">Community</span></span>   | <span data-ttu-id="12c27-162">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="12c27-162">Community</span></span>   |
| <span data-ttu-id="12c27-163">Raspbian</span><span class="sxs-lookup"><span data-stu-id="12c27-163">Raspbian</span></span>                                          | <span data-ttu-id="12c27-164">Experimental</span><span class="sxs-lookup"><span data-stu-id="12c27-164">Experimental</span></span>| <span data-ttu-id="12c27-165">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="12c27-165">Community</span></span>   |
| <span data-ttu-id="12c27-166">Kali</span><span class="sxs-lookup"><span data-stu-id="12c27-166">Kali</span></span>                                              | <span data-ttu-id="12c27-167">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="12c27-167">Community</span></span>   | <span data-ttu-id="12c27-168">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="12c27-168">Community</span></span>   |
| <span data-ttu-id="12c27-169">AppImage (複数の Linux プラットフォームで機能)</span><span class="sxs-lookup"><span data-stu-id="12c27-169">AppImage  (works on multiple Linux platforms)</span></span>     | <span data-ttu-id="12c27-170">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="12c27-170">Community</span></span>   | <span data-ttu-id="12c27-171">コミュニティ</span><span class="sxs-lookup"><span data-stu-id="12c27-171">Community</span></span>   |

## <a name="platform-which-are-out-of-support"></a><span data-ttu-id="12c27-172">サポート対象外のプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="12c27-172">Platform which are out of support</span></span>

<span data-ttu-id="12c27-173">プラットフォームのバージョンが、プラットフォームの所有者によって定義された有効期限を迎えると、PowerShell Core もまたそのプラットフォームのバージョンをサポートしなくなります。</span><span class="sxs-lookup"><span data-stu-id="12c27-173">When a platform version reaches end-of-life as defined by the platform owner, PowerShell Core will also cease to provide support for that platform version.</span></span> <span data-ttu-id="12c27-174">アクセスする必要があるユーザーは引き続き以前にリリースされたパッケージを利用できますが、公式のサポートと更新プログラムはどんな種類のものも提供されなくなります。</span><span class="sxs-lookup"><span data-stu-id="12c27-174">Previously released packages will remain available for customers needing access but formal support and updates of any kind will no longer be provided.</span></span>

<span data-ttu-id="12c27-175">そのため、次のバージョンのサポートはディストリビューションの所有者によって終了され、現在はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="12c27-175">Therefore, support for the following versions was ended by the distribution owners and are not supported.</span></span>

| <span data-ttu-id="12c27-176">OS</span><span class="sxs-lookup"><span data-stu-id="12c27-176">OS</span></span>       | <span data-ttu-id="12c27-177">バージョン</span><span class="sxs-lookup"><span data-stu-id="12c27-177">Version</span></span> | <span data-ttu-id="12c27-178">有効期限切れ</span><span class="sxs-lookup"><span data-stu-id="12c27-178">End of Life</span></span>                                                                                 |
|----------|---------|---------------------------------------------------------------------------------------------|
| <span data-ttu-id="12c27-179">Fedora</span><span class="sxs-lookup"><span data-stu-id="12c27-179">Fedora</span></span>   | <span data-ttu-id="12c27-180">26</span><span class="sxs-lookup"><span data-stu-id="12c27-180">26</span></span>      | [<span data-ttu-id="12c27-181">2018 年 5 月</span><span class="sxs-lookup"><span data-stu-id="12c27-181">May 2018</span></span>](https://fedoramagazine.org/fedora-26-end-life/)                                  |
| <span data-ttu-id="12c27-182">Fedora</span><span class="sxs-lookup"><span data-stu-id="12c27-182">Fedora</span></span>   | <span data-ttu-id="12c27-183">25</span><span class="sxs-lookup"><span data-stu-id="12c27-183">25</span></span>      | [<span data-ttu-id="12c27-184">2017 年 12 月</span><span class="sxs-lookup"><span data-stu-id="12c27-184">December 2017</span></span>](https://fedoramagazine.org/fedora-25-end-life/)                             |
| <span data-ttu-id="12c27-185">Fedora</span><span class="sxs-lookup"><span data-stu-id="12c27-185">Fedora</span></span>   | <span data-ttu-id="12c27-186">24</span><span class="sxs-lookup"><span data-stu-id="12c27-186">24</span></span>      | [<span data-ttu-id="12c27-187">2017 年 8 月</span><span class="sxs-lookup"><span data-stu-id="12c27-187">August 2017</span></span>](https://fedoramagazine.org/fedora-24-eol/)                                    |
| <span data-ttu-id="12c27-188">openSUSE</span><span class="sxs-lookup"><span data-stu-id="12c27-188">openSUSE</span></span> | <span data-ttu-id="12c27-189">42.2</span><span class="sxs-lookup"><span data-stu-id="12c27-189">42.2</span></span>    | [<span data-ttu-id="12c27-190">2018 年 1 月</span><span class="sxs-lookup"><span data-stu-id="12c27-190">January 2018</span></span>](https://lists.opensuse.org/opensuse-security-announce/2017-11/msg00066.html) |
| <span data-ttu-id="12c27-191">openSUSE</span><span class="sxs-lookup"><span data-stu-id="12c27-191">openSUSE</span></span> | <span data-ttu-id="12c27-192">42.1</span><span class="sxs-lookup"><span data-stu-id="12c27-192">42.1</span></span>    | [<span data-ttu-id="12c27-193">2017 年 5 月</span><span class="sxs-lookup"><span data-stu-id="12c27-193">May 2017</span></span>](https://lists.opensuse.org/opensuse-security-announce/2017-05/msg00053.html)     |
| <span data-ttu-id="12c27-194">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="12c27-194">Ubuntu</span></span>   | <span data-ttu-id="12c27-195">17.04</span><span class="sxs-lookup"><span data-stu-id="12c27-195">17.04</span></span>   | [<span data-ttu-id="12c27-196">2018 年 1 月</span><span class="sxs-lookup"><span data-stu-id="12c27-196">January 2018</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2018-January.txt)          |
| <span data-ttu-id="12c27-197">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="12c27-197">Ubuntu</span></span>   | <span data-ttu-id="12c27-198">16.10</span><span class="sxs-lookup"><span data-stu-id="12c27-198">16.10</span></span>   | [<span data-ttu-id="12c27-199">2017 年 7 月</span><span class="sxs-lookup"><span data-stu-id="12c27-199">July 2017</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2017-July/000223.html)        |

## <a name="notes-on-licensing"></a><span data-ttu-id="12c27-200">ライセンスに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="12c27-200">Notes on licensing</span></span>

<span data-ttu-id="12c27-201">PowerShell Core は [MIT ライセンス][]の下で提供されます。</span><span class="sxs-lookup"><span data-stu-id="12c27-201">PowerShell Core is released under the [MIT license][].</span></span>
<span data-ttu-id="12c27-202">このライセンスの下では、また、有料サポート契約がないときは、ユーザーには[コミュニティ サポート][]のみが与えられます。</span><span class="sxs-lookup"><span data-stu-id="12c27-202">Under this license, and in the absence of a paid support agreement, users are limited to [community support][].</span></span>
<span data-ttu-id="12c27-203">コミュニティ サポートの場合、マイクロソフトは回答や解決を保証しません。</span><span class="sxs-lookup"><span data-stu-id="12c27-203">With community support, Microsoft makes no guarantees of responsiveness or fixes.</span></span>

## <a name="windows-powershell-module"></a><span data-ttu-id="12c27-204">Windows PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="12c27-204">Windows PowerShell Module</span></span>

<span data-ttu-id="12c27-205">PowerShell Core のサポートが他の製品モジュールに適用されることは、そのモジュールが PowerShell Core 対応であることが明示されている場合を除いてありません。</span><span class="sxs-lookup"><span data-stu-id="12c27-205">Support for PowerShell Core does not extend to other product modules unless those modules explicitly support PowerShell Core.</span></span>
<span data-ttu-id="12c27-206">たとえば、Windows Server に付属する `ActiveDirectory` モジュールを使用することはサポートの対象外です。</span><span class="sxs-lookup"><span data-stu-id="12c27-206">For example, using the `ActiveDirectory` module that ships as part of Windows Server is an unsupported scenario.</span></span>

<span data-ttu-id="12c27-207">ただし、PowerShell Core 対応であることが明示されていないモジュールの場合でも、サポート対象となることがあります。</span><span class="sxs-lookup"><span data-stu-id="12c27-207">However, modules that do not explicitly support PowerShell Core may be compatible in some cases.</span></span>
<span data-ttu-id="12c27-208">[`WindowsPSModulePath`][] モジュールをインストールすることで、Windows PowerShell `PSModulePath` を PowerShell Core `PSModulePath` に追加できます。</span><span class="sxs-lookup"><span data-stu-id="12c27-208">By installing the [`WindowsPSModulePath`][] module, you can append the Windows PowerShell `PSModulePath` to your PowerShell Core `PSModulePath`.</span></span>

<span data-ttu-id="12c27-209">最初に、PowerShell ギャラリーから `WindowsPSModulePath` モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="12c27-209">First, install the `WindowsPSModulePath` module from the PowerShell Gallery:</span></span>

```powershell
# Add `-Scope CurrentUser` if you're installing as non-admin
Install-Module WindowsPSModulePath -Force
```

<span data-ttu-id="12c27-210">このモジュールをインストールしたら、次のように `Add-WindowsPSModulePath` コマンドレットを実行して、Windows PowerShell `PSModulePath` を PowerShell Core に追加します。</span><span class="sxs-lookup"><span data-stu-id="12c27-210">After installing this module, run the `Add-WindowsPSModulePath` cmdlet to add the Windows PowerShell `PSModulePath` to PowerShell Core:</span></span>

```powershell
# Add this line to your profile if you always want Windows PowerShell PSModulePath
Add-WindowsPSModulePath
```

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
