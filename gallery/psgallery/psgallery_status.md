---
ms.date: 2017-06-12
contributor: JKeithB
ms.topic: conceptual
keywords: "ギャラリー, PowerShell, コマンドレット, PSGallery"
title: psgallery_status
ms.openlocfilehash: 8c325ce1c665181cff646eef6c5e7d55e9081e5e
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a name="powershell-gallery-status"></a><span data-ttu-id="792f2-103">PowerShell ギャラリーの状態</span><span class="sxs-lookup"><span data-stu-id="792f2-103">PowerShell Gallery Status</span></span>
=========================
## <a name="06012017---deploy-to-azure-automation-currently-unavailable"></a><span data-ttu-id="792f2-104">2017/06/01 - Azure Automation へのデプロイが現在使用できない</span><span class="sxs-lookup"><span data-stu-id="792f2-104">06/01/2017 - Deploy to Azure Automation Currently Unavailable</span></span>

<span data-ttu-id="792f2-105">__影響の概要__: PowerShell ギャラリーからの Azure Automation に関係する項目のデプロイは現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="792f2-105">__Summary of Impact__: Deploying items with dependencies to Azure Automation from the PowerShell Gallery is currently unavailable.</span></span>  <span data-ttu-id="792f2-106">Azure Automation 内の PowerShell ギャラリーからのアイテムのインポートは引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="792f2-106">Importing items from the PowerShell Gallery from inside Azure Automation is still available.</span></span>  
 
<span data-ttu-id="792f2-107">__根本原因__: 他のアイテムに依存関係があり、Azure Automation に以前にデプロイされているアイテムは、Azure Automation にはデプロイされません。</span><span class="sxs-lookup"><span data-stu-id="792f2-107">__Root Cause__: Items that have dependencies on others, and have been previously deployed to Azure Automation, will not be deployed to Azure Automation.</span></span> <span data-ttu-id="792f2-108">エンジニアは、Azure Automation への機能的なデプロイに関係するアイテムのために ARM テンプレートを生成する方法の問題点を確認しました。</span><span class="sxs-lookup"><span data-stu-id="792f2-108">Engineers have identified an issue with how ARM templates are generated for items with dependencies for the Deploy to Azure Automation functionality.</span></span>

<span data-ttu-id="792f2-109">__解決策__: エンジニアが問題の解決に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="792f2-109">__Resolution__: Engineers are working to resolve issue.</span></span>  <span data-ttu-id="792f2-110">現在のユーザーの回避策は、Azure Automation 内の PowerShell ギャラリーからアイテムをインポートすることです。</span><span class="sxs-lookup"><span data-stu-id="792f2-110">The current workaround for users is to import the item from the PowerShell Gallery from inside Azure Automation.</span></span> 

<span data-ttu-id="792f2-111">__次のステップ__: エンジニアは、まもなく修正プログラムをリリースします。</span><span class="sxs-lookup"><span data-stu-id="792f2-111">__Next Steps__: Engineers will release the fix shortly.</span></span>  <span data-ttu-id="792f2-112">それまでは、お勧めした回避策をご使用ください。</span><span class="sxs-lookup"><span data-stu-id="792f2-112">In the meantime, please use the recommended workaround.</span></span> 


## <a name="04112017---users-unable-to-log-in-with-azure-active-directory-aad-accounts"></a><span data-ttu-id="792f2-113">2017/04/11 - ユーザーが Azure Active Directory (AAD) アカウントでログインできません</span><span class="sxs-lookup"><span data-stu-id="792f2-113">04/11/2017 - Users unable to log in with Azure Active Directory (AAD) accounts</span></span>

<span data-ttu-id="792f2-114">__影響の概要__: 一部のユーザーが Azure AD アカウントを使用して PowerShell ギャラリーにログインすることできませんでした。</span><span class="sxs-lookup"><span data-stu-id="792f2-114">__Summary of Impact__: Some users were unable to log in to the PowerShell Gallery using Azure AD Accounts.</span></span> 
 
<span data-ttu-id="792f2-115">__根本的な原因__: AAD とより安全にやりとりするために更新している途中で、変更できなかった設定がありました。</span><span class="sxs-lookup"><span data-stu-id="792f2-115">__Root Cause__: During an update to interact more securely with AAD, a setting change was missed.</span></span> <span data-ttu-id="792f2-116">変更を検証するために行われたテストに特定の種類の AAD アカウントが含まれておらず、そのような状態で展開が進みました。</span><span class="sxs-lookup"><span data-stu-id="792f2-116">The testing done to validate the change did not include certain types of AAD accounts, so the deployment proceeded.</span></span>

<span data-ttu-id="792f2-117">__解決__: 不足している設定をエンジニアが特定し、問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="792f2-117">__Resolution__: Engineers identified the missing setting and corrected the problem.</span></span> 

<span data-ttu-id="792f2-118">__次の手順__: 幅広い AAD アカウントの種類が含まれるようにテストを修正する予定です。</span><span class="sxs-lookup"><span data-stu-id="792f2-118">__Next Steps__: We will be modifying our testing to include a broader set of AAD account types.</span></span>

## <a name="03272017---resolved-unable-to-see-individual-module-and-script-pages"></a><span data-ttu-id="792f2-119">2017/03/27 - 解決済み - 個々のモジュールとスクリプトのページを表示できません</span><span class="sxs-lookup"><span data-stu-id="792f2-119">03/27/2017 - RESOLVED: Unable to see individual module and script pages</span></span>

<span data-ttu-id="792f2-120">__影響の概要__: https://www.powershellgallery.com の個々のモジュールとスクリプト ページへのダイレクト リンクが破損していました。</span><span class="sxs-lookup"><span data-stu-id="792f2-120">__Summary of Impact__: Direct links to individual module and script pages on https://www.powershellgallery.com were broken.</span></span> <span data-ttu-id="792f2-121">この問題はすべての地域で報告されていました。</span><span class="sxs-lookup"><span data-stu-id="792f2-121">This was being reported across all the regions.</span></span> <span data-ttu-id="792f2-122">この問題は、どの PowerShellGet コマンドレットにも影響を与えていませんでした。すなわち、Install-Module、Install-Script、Update-Module、Update-Script、Publish-Module、Publish-Script は引き続き動作していました。</span><span class="sxs-lookup"><span data-stu-id="792f2-122">This did not impact any of the PowerShellGet cmdlets ie., Install-Module, Install-Script, Update-Module, Update-Script, Publish-Module, Publish-Scirpt continued to work.</span></span>

<span data-ttu-id="792f2-123">__根本的な原因__: エンジニアは、ページ上にある Facebook などのソーシャル メディア ボタンの表示が原因であることが確認されています。</span><span class="sxs-lookup"><span data-stu-id="792f2-123">__Root Cause__: Engineers identified the cause as an issue bringing up social media buttons like Facebook onto the page.</span></span>  

<span data-ttu-id="792f2-124">__解決策__: エンジニアは、Facebook のカウント情報を無効にして問題を解決しました。</span><span class="sxs-lookup"><span data-stu-id="792f2-124">__Resolution__: Engineers fixed the problem by disabling the Facebook count information.</span></span>

<span data-ttu-id="792f2-125">__次のステップ__: 内部的な追跡の問題をオープンにし、Facebook API の使用内容を修正しました。</span><span class="sxs-lookup"><span data-stu-id="792f2-125">__Next Steps__: We opened an internal tracking issue to fix our usage of Facebook API.</span></span>

## <a name="12152016---unable-to-send-emails-via-powershellgallery-website"></a><span data-ttu-id="792f2-126">2016 年 12 月 15 日 - PowerShellGallery Web サイトからメールを送信できない</span><span class="sxs-lookup"><span data-stu-id="792f2-126">12/15/2016 - Unable to send emails via PowerShellGallery website</span></span>

<span data-ttu-id="792f2-127">__影響の概要__: 2016 年 12 月 13 日と 2016 年 12 月 15 日に、[Contact Owners (所有者に連絡)]、[Manage Owners (所有者の管理)]、[サポートに連絡]、または [不正使用を報告] から送信されたメッセージが、PowerShell ギャラリーの管理者に届きませんでした。</span><span class="sxs-lookup"><span data-stu-id="792f2-127">__Summary of Impact__: Between 12/13/2016 and 12/15/2016, any messages sent via Contact Owners, Manage Owners, Contact Support, or Report Abuse were not received by the PowerShell Gallery Administrators.</span></span>  
<span data-ttu-id="792f2-128">__根本的な原因__: SMTP サーバーでの認証の問題でした。</span><span class="sxs-lookup"><span data-stu-id="792f2-128">__Root Cause__: Engineers identified the cause as an authentication issue with the SMTP server.</span></span>  
<span data-ttu-id="792f2-129">__解決策__: 認証の問題を解決し、SMTP サーバーへの接続を復元しました。</span><span class="sxs-lookup"><span data-stu-id="792f2-129">__Resolution__: Engineers were able to resolve the authentication issue and restore connection to the SMTP server.</span></span>  
<span data-ttu-id="792f2-130">__次の手順__: この間に [Contact Owners (所有者に連絡)]、[Manage Owners (所有者の管理)]、[サポートに連絡]、または [不正使用を報告] のリンクを使って cgadmin@microsoft.com にメールを送り、返信がない場合は、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="792f2-130">__Next Steps__: If you used the Contact Owners, Manage Owners, Contact Support, or Report Abuse links to send mail to cgadmin@microsoft.com during this time and we have not responded, please try again.</span></span> <span data-ttu-id="792f2-131">ご不便をおかけして申し訳ございませんでした。</span><span class="sxs-lookup"><span data-stu-id="792f2-131">We apologize for the inconvenience.</span></span>  



## <a name="8102016---resolved-unable-to-send-emails-to-cgadminmicrosoftcom"></a><span data-ttu-id="792f2-132">2016 年 8 月 10 日 - 解決: 電子メールを cgadmin@microsoft.com に送信できない</span><span class="sxs-lookup"><span data-stu-id="792f2-132">8/10/2016 - Resolved: Unable to send emails to cgadmin@microsoft.com</span></span>

<span data-ttu-id="792f2-133">__影響の概要__: 2016 年 8 月 5 日から 2016 年 8 月 10 日までの期間中、お客様による cgadmin@microsoft.com に電子メールの送信、または [お問い合わせ先] 機能の使用ができませんでした。</span><span class="sxs-lookup"><span data-stu-id="792f2-133">__Summary of Impact__: Between 8/5/2016 and 8/10/2016, customers were unable to send emails to cgadmin@microsoft.com, or use the Contact Us feature.</span></span>  
<span data-ttu-id="792f2-134">__根本的な原因__: エンジニアは、電子メール アカウントの構成の変更に原因があることを突き止めました。</span><span class="sxs-lookup"><span data-stu-id="792f2-134">__Root Cause__: Engineers identified the cause as a configuration change of the email account.</span></span>  
<span data-ttu-id="792f2-135">__解決策__: エンジニアは、構成の問題を解決するための作業を行いました。</span><span class="sxs-lookup"><span data-stu-id="792f2-135">__Resolution__: Engineers worked to resolve the configuration issue.</span></span>  
<span data-ttu-id="792f2-136">__次の手順__: この期間中に [お問い合わせ先] リンクを使用、または cgadmin@microsoft.com にメールを送信したお客様には応答できていませんので、やり直してください。</span><span class="sxs-lookup"><span data-stu-id="792f2-136">__Next Steps__: If you used the Contact Us link or sent mail to cgadmin@microsoft.com during this time and we have not responded, please try again.</span></span> <span data-ttu-id="792f2-137">ご不便をおかけして申し訳ございませんでした。</span><span class="sxs-lookup"><span data-stu-id="792f2-137">Thank you for your patience.</span></span>



## <a name="7132016---download-items-failed"></a><span data-ttu-id="792f2-138">2016 年 7 月 13 日 - アイテムのダウンロードに失敗しました</span><span class="sxs-lookup"><span data-stu-id="792f2-138">7/13/2016 - Download Items Failed</span></span>

<span data-ttu-id="792f2-139">__影響の概要__: 2016 年 7 月 11 日から 2016 年 7 月 13 日までの期間中に一部のお客様で、PowerShell ギャラリーからアイテムをダウンロードする際に問題が発生しました。</span><span class="sxs-lookup"><span data-stu-id="792f2-139">__Summary of Impact__: Between 7/11/2016 and 7/13/2016, a subset of customers experienced issues downloading items from the PowerShell Gallery.</span></span> <span data-ttu-id="792f2-140">この問題は、Install-Module/Install-Script および Save-Module/Save-Script から返された次のエラー メッセージに示されていたようです。</span><span class="sxs-lookup"><span data-stu-id="792f2-140">The issue likely manifested itself in the following error message returned from Install-Module/Install-Script and Save-Module/Save-Script:</span></span>

```PowerShell
PS C:\> Install-Module xStorage 
PackageManagement\Install-Package : Package 'xStorage' failed to be installed because: 
End of Central Directory record could not be found. At C:\Program 
Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PSModule.psm1:1375 char:21 + ... 
$null = PackageManagement\Install-Package @PSBoundParameters + 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ + CategoryInfo : InvalidResult: 
(xStorage:String) [Install-Package], Exception + FullyQualifiedErrorId : Package '{0}' 
failed to be installed because: {1},Microsoft.PowerShell.PackageManagement.Cmdlets.InstallPackage 
```

<span data-ttu-id="792f2-141">__暫定的な根本原因__: エンジニアは、2016 年 7 月 11 日に PowerShell ギャラリーに展開した Azure コンテンツ配信ネットワーク (CDN) に関係する問題であることを突き止めました。</span><span class="sxs-lookup"><span data-stu-id="792f2-141">__Preliminary root cause__: Engineers identified an issue with Azure Content Deliver Network (CDN), which was deployed to the PowerShell Gallery on 7/11/2016.</span></span>  
<span data-ttu-id="792f2-142">__対応策__: エンジニアは、PowerShell ギャラリーで Azure CDN を無効にしました。</span><span class="sxs-lookup"><span data-stu-id="792f2-142">__Mitigation__: Engineers disabled Azure CDN in the PowerShell Gallery.</span></span>  
<span data-ttu-id="792f2-143">__次の手順__: 根本原因を調査し、今後の問題発生を防止するためのソリューションを開発します。</span><span class="sxs-lookup"><span data-stu-id="792f2-143">__Next Steps__: Investigate the underlying root cause and developing a solution to prevent future occurrences.</span></span>


## <a name="5192016---download-items-failed"></a><span data-ttu-id="792f2-144">2016 年 5 月 19 日 - アイテムのダウンロードに失敗しました</span><span class="sxs-lookup"><span data-stu-id="792f2-144">5/19/2016 - Download Items Failed</span></span>
<span data-ttu-id="792f2-145">__影響の概要__: 2016 年 5 月 17 日から 2016 年 5 月 19 日までの期間中に一部のお客様で、PowerShell ギャラリーからアイテムをダウンロードする際に問題が発生しました。</span><span class="sxs-lookup"><span data-stu-id="792f2-145">__Summary of Impact__: Between 5/17/2016 and 5/19/2016, a subset of customers experienced issues downloading items from the PowerShell Gallery.</span></span> <span data-ttu-id="792f2-146">この問題は、Install-Module/Install-Script および Save-Module/Save-Script から返された次のエラー メッセージに示されていたようです。</span><span class="sxs-lookup"><span data-stu-id="792f2-146">The issue likely manifested itself in the following error message returned from Install-Module/Install-Script and Save-Module/Save-Script:</span></span>

```PowerShell
VERBOSE: Hash for package 'AzureRM.OperationalInsights' does not match hash provided from the server.
VERBOSE: InstallPackageLocal' - name='AzureRM.OperationalInsights', version='1.0.8',
destination='C:\Users\jbritt\AppData\Local\Temp\2\1741355729'
WARNING: Package 'AzureRM.OperationalInsights' failed to be installed because: 
End of Central Directory record could not be found. 
WARNING: Dependent Package 'AzureRM.OperationalInsights' failed to install. 
WARNING: Package 'AzureRM' failed to install. 
VERBOSE: Module 'AzureRM.Network' was saved successfully. 
VERBOSE: Saving the dependency module 'AzureRM.NotificationHubs' with version '1.0.8' for the 
module 'AzureRM'. 
VERBOSE: Module 'AzureRM.NotificationHubs' was saved successfully. 
PackageManagement\Save-Package : Unable to save the module 'AzureRM'. At C:\Program 
Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PSModule.psm1:1187 char:21 + 
$null = PackageManagement\Save-Package @PSBoundParameters + 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ + 
CategoryInfo : InvalidOperation: (Microsoft.Power...ets.SavePackage:SavePackage) 
[Save-Package], Exception + FullyQualifiedErrorId : ProviderFailToDownloadFile,
Microsoft.PowerShell.PackageManagement.Cmdlets.SavePackage 
```

<span data-ttu-id="792f2-147">__暫定的な根本原因__: エンジニアは、2016 年 5 月 17 日に PowerShell ギャラリーに展開した Azure コンテンツ配信ネットワーク (CDN) の基になるプロバイダーで障害が発生したことを突き止めました。</span><span class="sxs-lookup"><span data-stu-id="792f2-147">__Preliminary root cause__: Engineers identified an outage in the underlying provider of Azure Content Deliver Network (CDN), which was deployed to the PowerShell Gallery on 5/17/2016.</span></span>  
<span data-ttu-id="792f2-148">__対応策__: エンジニアは、PowerShell ギャラリーで Azure CDN を無効にしました。</span><span class="sxs-lookup"><span data-stu-id="792f2-148">__Mitigation__: Engineers disabled Azure CDN in the PowerShell Gallery.</span></span>  
<span data-ttu-id="792f2-149">__次の手順__: 根本原因を調査し、今後の問題発生を防止するためのソリューションを開発します。</span><span class="sxs-lookup"><span data-stu-id="792f2-149">__Next Steps__: Investigate the underlying root cause and developing a solution to prevent future occurrences.</span></span>

