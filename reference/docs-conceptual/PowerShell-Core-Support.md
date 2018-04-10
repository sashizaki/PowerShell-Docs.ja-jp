# <a name="powershell-core-support-lifecycle"></a><span data-ttu-id="2caa2-101">PowerShell Core のサポート ライフサイクル</span><span class="sxs-lookup"><span data-stu-id="2caa2-101">PowerShell Core Support Lifecycle</span></span>

<span data-ttu-id="2caa2-102">PowerShell Core は、Windows PowerShell とは別に出荷され、インストールされ、構成される別個のツール セットであり、コンポーネント セットです。</span><span class="sxs-lookup"><span data-stu-id="2caa2-102">PowerShell Core is a distinct set of tools and components that is shipped, installed, and configured separately from Windows PowerShell.</span></span>
<span data-ttu-id="2caa2-103">そのため、PowerShell Core は Windows 7/8.1/10 や Windows Server のライセンス契約には含まれていません。</span><span class="sxs-lookup"><span data-stu-id="2caa2-103">Therefore, PowerShell Core is not included in the Windows 7/8.1/10 or Windows Server licensing agreements.</span></span>

<span data-ttu-id="2caa2-104">ただし、PowerShell Core は、[Premier][]、[Microsoft Enterprise Agreements][enterprise-agreement]、[マイクロソフト ソフトウェア アシュアランス][assurance]など、従来の Microsoft サポート契約ではサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2caa2-104">However, PowerShell Core is supported under traditional Microsoft support agreements, including [Premier][], [Microsoft Enterprise Agreements][enterprise-agreement], and [Microsoft Software Assurance][assurance].</span></span>
<span data-ttu-id="2caa2-105">サポート依頼で問題を報告して PowerShell Core の[サポート][]を受け、それに対して支払うこともできます。</span><span class="sxs-lookup"><span data-stu-id="2caa2-105">You can also pay for [assisted support][] for PowerShell Core by filing a support request for your problem.</span></span>

<span data-ttu-id="2caa2-106">GitHub でも[コミュニティ サポート][]を用意しています。問題やバグを報告したり、機能を要望したりできます。</span><span class="sxs-lookup"><span data-stu-id="2caa2-106">We also offer [community support][] on GitHub where you can file an issue, bug, or feature request.</span></span>
<span data-ttu-id="2caa2-107">あるいは、一般的な [Microsoft コミュニティ][]や Microsoft [PowerShell Tech コミュニティ][]で他のコミュニティ メンバーが助けてくれることがあります。</span><span class="sxs-lookup"><span data-stu-id="2caa2-107">Alternatively, you may find help from other members of the community on the general [Microsoft Community][] or the Microsoft [PowerShell Tech Community][].</span></span>
<span data-ttu-id="2caa2-108">問題が短期間で解決されることは保証できません。</span><span class="sxs-lookup"><span data-stu-id="2caa2-108">We offer no guarantee there that your issue will be addressed or resolved in a timely manner.</span></span>
<span data-ttu-id="2caa2-109">早急な対応が必要な問題の場合、従来の有料サポートをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="2caa2-109">If you have a problem that requires immediate attention, you should use the traditional, paid support options.</span></span>

## <a name="lifecycle-of-powershell-core"></a><span data-ttu-id="2caa2-110">PowerShell Core のライフサイクル</span><span class="sxs-lookup"><span data-stu-id="2caa2-110">Lifecycle of PowerShell Core</span></span>

<span data-ttu-id="2caa2-111">PowerShell Core には、[Microsoft Modern Lifecycle Policy][modern] が導入されています。</span><span class="sxs-lookup"><span data-stu-id="2caa2-111">PowerShell Core is adopting the [Microsoft Modern Lifecycle Policy][modern].</span></span>
<span data-ttu-id="2caa2-112">このサポート ライフサイクルでは、最新バージョンで最新の機能を常に提供します。</span><span class="sxs-lookup"><span data-stu-id="2caa2-112">This support lifecycle is intended to keep customers up-to-date with the latest versions.</span></span>

<span data-ttu-id="2caa2-113">PowerShell Core のバージョン 6.x ブランチは約半年に一回更新されます (6.0、6.1、6.2 など)</span><span class="sxs-lookup"><span data-stu-id="2caa2-113">The version 6.x branch of PowerShell Core will be updated approximately once every six months (e.g. 6.0, 6.1, 6.2, etc.)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2caa2-114">引き続きサポートを受けるには、新しいマイナー バージョンの公開後、6 か月以内に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2caa2-114">You must update within six months after each new minor version release to continue receiving support.</span></span>

<span data-ttu-id="2caa2-115">たとえば、PowerShell Core 6.1 が 2018 年 7 月 1 日に公開された場合、サポートを維持するには、2019 年 1 月 1 日までに PowerShell Core 6.1 に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2caa2-115">For example, if PowerShell Core 6.1 is released on July 1st, 2018, you would be expected to update to PowerShell Core 6.1 by January 1st, 2019 to maintain support.</span></span>

![PowerShell Core のブランチ ライフサイクル][lifecycle-chart]

<span data-ttu-id="2caa2-117">Modern Lifecycle Policy では、製品 (つまり、PowerShell Core) のサポートを終了する 12 か月前にお客様に通知することをマイクロソフトの義務としています。</span><span class="sxs-lookup"><span data-stu-id="2caa2-117">The Modern Lifecycle Policy also requires that Microsoft give customers 12 months notice before discontinuing support for a product (i.e. PowerShell Core).</span></span>

<span data-ttu-id="2caa2-118">ゆくゆくは PowerShell Core に "Long Term Servicing" 手法を導入することをマイクロソフトは期待しています。この手法では、特定の 6.x ブランチ/バージョンのサポートを維持するために、サービス更新とセキュリティ更新だけが必要になります。</span><span class="sxs-lookup"><span data-stu-id="2caa2-118">Eventually, we expect PowerShell Core will adopt the "long-term servicing" approach where we would require only servicing and security updates to stay in support on a specific branch/version of 6.x.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="2caa2-119">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="2caa2-119">Supported platforms</span></span>

<span data-ttu-id="2caa2-120">PowerShell Core は次のプラットフォームで公式サポートされています。</span><span class="sxs-lookup"><span data-stu-id="2caa2-120">PowerShell Core is officially supported on the following platforms:</span></span>

* <span data-ttu-id="2caa2-121">Windows 7、8.1、10</span><span class="sxs-lookup"><span data-stu-id="2caa2-121">Windows 7, 8.1, and 10</span></span>
* <span data-ttu-id="2caa2-122">Windows Server 2008 R2、2012 R2、2016</span><span class="sxs-lookup"><span data-stu-id="2caa2-122">Windows Server 2008 R2, 2012 R2, 2016</span></span>
* <span data-ttu-id="2caa2-123">[Windows Server 半期チャネル][semi-annual]</span><span class="sxs-lookup"><span data-stu-id="2caa2-123">[Windows Server Semi-Annual Channel][semi-annual]</span></span>
* <span data-ttu-id="2caa2-124">Ubuntu 14.04、16.04、17.04</span><span class="sxs-lookup"><span data-stu-id="2caa2-124">Ubuntu 14.04, 16.04, and 17.04</span></span>
* <span data-ttu-id="2caa2-125">Debian 8.7 以降および 9</span><span class="sxs-lookup"><span data-stu-id="2caa2-125">Debian 8.7+, and 9</span></span>
* <span data-ttu-id="2caa2-126">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="2caa2-126">CentOS 7</span></span>
* <span data-ttu-id="2caa2-127">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="2caa2-127">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="2caa2-128">OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="2caa2-128">OpenSUSE 42.2</span></span>
* <span data-ttu-id="2caa2-129">Fedora 25、26</span><span class="sxs-lookup"><span data-stu-id="2caa2-129">Fedora 25, 26</span></span>
* <span data-ttu-id="2caa2-130">macOS 10.12 以降</span><span class="sxs-lookup"><span data-stu-id="2caa2-130">macOS 10.12+</span></span>

<span data-ttu-id="2caa2-131">弊社のコミュニティでは、次のプラットフォーム用のパッケージも提供していますが、正式にはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2caa2-131">Our community has also contributed packages for the following platforms, but they are not officially suppported:</span></span>

* <span data-ttu-id="2caa2-132">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="2caa2-132">Arch Linux</span></span>
* <span data-ttu-id="2caa2-133">Kali Linux</span><span class="sxs-lookup"><span data-stu-id="2caa2-133">Kali Linux</span></span>
* <span data-ttu-id="2caa2-134">AppImage (複数の Linux プラットフォームで機能)</span><span class="sxs-lookup"><span data-stu-id="2caa2-134">AppImage (works on multiple Linux platforms)</span></span>

## <a name="notes-on-licensing"></a><span data-ttu-id="2caa2-135">ライセンスに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="2caa2-135">Notes on licensing</span></span>

<span data-ttu-id="2caa2-136">PowerShell Core は [MIT ライセンス][]の下で提供されます。</span><span class="sxs-lookup"><span data-stu-id="2caa2-136">PowerShell Core is released under the [MIT license][].</span></span>
<span data-ttu-id="2caa2-137">このライセンスの下では、また、有料サポート契約がないときは、ユーザーには[コミュニティ サポート][]のみが与えられます。</span><span class="sxs-lookup"><span data-stu-id="2caa2-137">Under this license, and in the absence of a paid support agreement, users are limited to [community support][].</span></span>
<span data-ttu-id="2caa2-138">コミュニティ サポートの場合、マイクロソフトは回答や解決を保証しません。</span><span class="sxs-lookup"><span data-stu-id="2caa2-138">With community support, Microsoft makes no guarantees of responsiveness or fixes.</span></span>

## <a name="windows-powershell-module"></a><span data-ttu-id="2caa2-139">Windows PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="2caa2-139">Windows PowerShell Module</span></span>

<span data-ttu-id="2caa2-140">PowerShell Core のサポートが他の製品モジュールに適用されることは、そのモジュールが PowerShell Core 対応であることが明示されている場合を除いてありません。</span><span class="sxs-lookup"><span data-stu-id="2caa2-140">Support for PowerShell Core does not extend to other product modules unless those modules explicitly support PowerShell Core.</span></span>
<span data-ttu-id="2caa2-141">たとえば、Windows Server に付属する `ActiveDirectory` モジュールを使用することはサポートの対象外です。</span><span class="sxs-lookup"><span data-stu-id="2caa2-141">For example, using the `ActiveDirectory` module that ships as part of Windows Server is an unsupported scenario.</span></span>

<span data-ttu-id="2caa2-142">ただし、PowerShell Core 対応であることが明示されていないモジュールの場合でも、サポート対象となることがあります。</span><span class="sxs-lookup"><span data-stu-id="2caa2-142">However, modules that do not explicitly support PowerShell Core may be compatible in some cases.</span></span>
<span data-ttu-id="2caa2-143">[`WindowsPSModulePath`][] モジュールをインストールすることで、Windows PowerShell `PSModulePath` を PowerShell Core `PSModulePath` に追加できます。</span><span class="sxs-lookup"><span data-stu-id="2caa2-143">By installing the [`WindowsPSModulePath`][] module, you can append the Windows PowerShell `PSModulePath` to your PowerShell Core `PSModulePath`.</span></span>

<span data-ttu-id="2caa2-144">最初に、PowerShell ギャラリーから `WindowsPSModulePath` モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2caa2-144">First, install the `WindowsPSModulePath` module from the PowerShell Gallery:</span></span>

```powershell
# Add `-Scope CurrentUser` if you're installing as non-admin
Install-Module WindowsPSModulePath -Force
```

<span data-ttu-id="2caa2-145">このモジュールをインストールしたら、次のように `Add-WindowsPSModulePath` コマンドレットを実行して、Windows PowerShell `PSModulePath` を PowerShell Core に追加します。</span><span class="sxs-lookup"><span data-stu-id="2caa2-145">After installing this module, run the `Add-WindowsPSModulePath` cmdlet to add the Windows PowerShell `PSModulePath` to PowerShell Core:</span></span>

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