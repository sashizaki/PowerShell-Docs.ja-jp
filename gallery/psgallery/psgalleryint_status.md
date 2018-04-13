---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: psgalleryint_status
ms.openlocfilehash: 4f7d300bb07fcbdb100c2fb029f8f66ab260fe7a
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
<a name="powershell-gallery-status"></a><span data-ttu-id="eca4a-103">PowerShell ギャラリーの状態</span><span class="sxs-lookup"><span data-stu-id="eca4a-103">PowerShell Gallery Status</span></span>
=========================

## <a name="03272017---resolved-unable-to-see-individual-module-and-script-pages"></a><span data-ttu-id="eca4a-104">2017/03/27 - 解決済み - 個々のモジュールとスクリプトのページを表示できません</span><span class="sxs-lookup"><span data-stu-id="eca4a-104">03/27/2017 - RESOLVED: Unable to see individual module and script pages</span></span>

<span data-ttu-id="eca4a-105">__影響の概要__: https://www.powershellgallery.com の個々のモジュールとスクリプト ページへのダイレクト リンクが破損していました。</span><span class="sxs-lookup"><span data-stu-id="eca4a-105">__Summary of Impact__: Direct links to individual module and script pages on https://www.powershellgallery.com were broken.</span></span> <span data-ttu-id="eca4a-106">この問題はすべての地域で報告されていました。</span><span class="sxs-lookup"><span data-stu-id="eca4a-106">This was being reported across all the regions.</span></span> <span data-ttu-id="eca4a-107">この問題は、どの PowerShellGet コマンドレットにも影響を与えていませんでした。すなわち、Install-Module、Install-Script、Update-Module、Update-Script、Publish-Module、Publish-Script は引き続き動作していました。</span><span class="sxs-lookup"><span data-stu-id="eca4a-107">This did not impact any of the PowerShellGet cmdlets ie., Install-Module, Install-Script, Update-Module, Update-Script, Publish-Module, Publish-Script continued to work.</span></span>

<span data-ttu-id="eca4a-108">__根本的な原因__: エンジニアは、ページ上にある Facebook などのソーシャル メディア ボタンの表示が原因であることが確認されています。</span><span class="sxs-lookup"><span data-stu-id="eca4a-108">__Root Cause__: Engineers identified the cause as an issue bringing up social media buttons like Facebook onto the page.</span></span>

<span data-ttu-id="eca4a-109">__解決策__: エンジニアは、Facebook のカウント情報を無効にして問題を解決しました。</span><span class="sxs-lookup"><span data-stu-id="eca4a-109">__Resolution__: Engineers fixed the problem by disabling the Facebook count information.</span></span>

<span data-ttu-id="eca4a-110">__次のステップ__: 内部的な追跡の問題をオープンにし、Facebook API の使用内容を修正しました。</span><span class="sxs-lookup"><span data-stu-id="eca4a-110">__Next Steps__: We opened an internal tracking issue to fix our usage of Facebook API.</span></span>

## <a name="12152016---unable-to-send-emails-via-powershellgallery-website"></a><span data-ttu-id="eca4a-111">2016 年 12 月 15 日 - PowerShellGallery Web サイトからメールを送信できない</span><span class="sxs-lookup"><span data-stu-id="eca4a-111">12/15/2016 - Unable to send emails via PowerShellGallery website</span></span>

<span data-ttu-id="eca4a-112">__影響の概要__: 2016 年 12 月 13 日と 2016 年 12 月 15 日に、[Contact Owners (所有者に連絡)]、[Manage Owners (所有者の管理)]、[サポートに連絡]、または [不正使用を報告] から送信されたメッセージが、PowerShell ギャラリーの管理者に届きませんでした。</span><span class="sxs-lookup"><span data-stu-id="eca4a-112">__Summary of Impact__: Between 12/13/2016 and 12/15/2016, any messages sent via Contact Owners, Manage Owners, Contact Support, or Report Abuse were not received by the PowerShell Gallery Administrators.</span></span>
<span data-ttu-id="eca4a-113">__根本的な原因__: SMTP サーバーでの認証の問題でした。</span><span class="sxs-lookup"><span data-stu-id="eca4a-113">__Root Cause__: Engineers identified the cause as an authentication issue with the SMTP server.</span></span>
<span data-ttu-id="eca4a-114">__解決策__: 認証の問題を解決し、SMTP サーバーへの接続を復元しました。</span><span class="sxs-lookup"><span data-stu-id="eca4a-114">__Resolution__: Engineers were able to resolve the authentication issue and restore connection to the SMTP server.</span></span>
<span data-ttu-id="eca4a-115">__次の手順__: この間に [Contact Owners (所有者に連絡)]、[Manage Owners (所有者の管理)]、[サポートに連絡]、または [不正使用を報告] のリンクを使って cgadmin@microsoft.com にメールを送り、返信がない場合は、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="eca4a-115">__Next Steps__: If you used the Contact Owners, Manage Owners, Contact Support, or Report Abuse links to send mail to cgadmin@microsoft.com during this time and we have not responded, please try again.</span></span> <span data-ttu-id="eca4a-116">ご不便をおかけして申し訳ございませんでした。</span><span class="sxs-lookup"><span data-stu-id="eca4a-116">We apologize for the inconvenience.</span></span>


## <a name="8102016---resolved-unable-to-send-emails-to-cgadminmicrosoftcom"></a><span data-ttu-id="eca4a-117">2016 年 8 月 10 日 - 解決: 電子メールを cgadmin@microsoft.com に送信できない</span><span class="sxs-lookup"><span data-stu-id="eca4a-117">8/10/2016 - Resolved: Unable to send emails to cgadmin@microsoft.com</span></span>
<span data-ttu-id="eca4a-118">__影響の概要__: 2016 年 8 月 5 日から 2016 年 8 月 10 日までの期間中、お客様による cgadmin@microsoft.com に電子メールの送信、または [お問い合わせ先] 機能の使用ができませんでした。</span><span class="sxs-lookup"><span data-stu-id="eca4a-118">__Summary of Impact__: Between 8/5/2016 and 8/10/2016, customers were unable to send emails to cgadmin@microsoft.com, or use the Contact Us feature.</span></span>
<span data-ttu-id="eca4a-119">__根本的な原因__: エンジニアは、電子メール アカウントの構成の変更に原因があることを突き止めました。</span><span class="sxs-lookup"><span data-stu-id="eca4a-119">__Root Cause__: Engineers identified the cause as a configuration change of the email account.</span></span>
<span data-ttu-id="eca4a-120">__解決策__: エンジニアは、構成の問題を解決するための作業を行いました。</span><span class="sxs-lookup"><span data-stu-id="eca4a-120">__Resolution__: Engineers worked to resolve the configuration issue.</span></span>
<span data-ttu-id="eca4a-121">__次の手順__: この期間中に [お問い合わせ先] リンクを使用、または cgadmin@microsoft.com にメールを送信したお客様には応答できていませんので、やり直してください。</span><span class="sxs-lookup"><span data-stu-id="eca4a-121">__Next Steps__: If you used the Contact Us link or sent mail to cgadmin@microsoft.com during this time and we have not responded, please try again.</span></span> <span data-ttu-id="eca4a-122">ご不便をおかけして申し訳ございませんでした。</span><span class="sxs-lookup"><span data-stu-id="eca4a-122">Thank you for your patience.</span></span>