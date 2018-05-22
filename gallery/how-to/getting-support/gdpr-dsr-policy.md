---
ms.date: 03/27/2018
contributor: JKeithB
keywords: ギャラリー, PowerShell, PSGallery, GDPR
title: PowerShell ギャラリー GDPR コンプライアンス
ms.openlocfilehash: dca1a82952c284980a84caafa13b2807e47e25a0
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="powershell-gallery-gdpr-compliance"></a><span data-ttu-id="1343c-103">PowerShell ギャラリー GDPR コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="1343c-103">PowerShell Gallery GDPR compliance</span></span>

## <a name="overview"></a><span data-ttu-id="1343c-104">概要</span><span class="sxs-lookup"><span data-stu-id="1343c-104">Overview</span></span>

<span data-ttu-id="1343c-105">2018 年 5 月より、ヨーロッパの個人情報保護法、一般データ保護規制 (GDPR) が有効になります。</span><span class="sxs-lookup"><span data-stu-id="1343c-105">In May 2018, a European privacy law, the General Data Protection Regulation (GDPR), takes effect.</span></span>
<span data-ttu-id="1343c-106">GDPR により、商品やサービスを欧州連合 (EU) 内で提供したり、EU の居住者に関連するデータを収集および分析したりする企業、政府機関、非営利団体などの組織に対し、新しい規則が課されます。</span><span class="sxs-lookup"><span data-stu-id="1343c-106">The GDPR imposes new rules on companies, government agencies, non-profits, and other organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data tied to EU residents.</span></span>
<span data-ttu-id="1343c-107">GDPR は現住所に関わらず適用されます。</span><span class="sxs-lookup"><span data-stu-id="1343c-107">The GDPR applies no matter where you are located.</span></span>

> [!NOTE]
> <span data-ttu-id="1343c-108">この記事は、PowerShell ギャラリーから個人データを削除する手順を提供するため、GDPR の下での義務の遂行に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1343c-108">This article provides steps for how to delete personal data from the PowerShell Gallery and can be used to support your obligations under the GDPR.</span></span> <span data-ttu-id="1343c-109">GDPR に関する一般的な情報をお探しの場合は、[Service Trust portal の GDPR に関するセクション](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1343c-109">If you’re looking for general info about GDPR, see the [GDPR section of the Service Trust portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).</span></span>

## <a name="personally-identifiable-data"></a><span data-ttu-id="1343c-110">個人を特定できるデータ</span><span class="sxs-lookup"><span data-stu-id="1343c-110">Personally identifiable data</span></span>

<span data-ttu-id="1343c-111">PowerShell ギャラリーには、ユーザーから提供され、個人情報が含まれる可能性がある、次の情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="1343c-111">The PowerShell Gallery stores the following information that may be provided by users, which may contain personal information:</span></span>

* <span data-ttu-id="1343c-112">PowerShell ギャラリーのアカウント</span><span class="sxs-lookup"><span data-stu-id="1343c-112">PowerShell Gallery account</span></span>
* <span data-ttu-id="1343c-113">PowerShell ギャラリーで公開されるアイテム</span><span class="sxs-lookup"><span data-stu-id="1343c-113">Items published to the PowerShell Gallery</span></span>
* <span data-ttu-id="1343c-114">PowerShell ギャラリー チームとの電子メールのやり取り</span><span class="sxs-lookup"><span data-stu-id="1343c-114">Email correspondence with the PowerShell Gallery team</span></span>

<span data-ttu-id="1343c-115">ほとんどのユーザーは、PowerShell ギャラリーのアカウントを作成しません。</span><span class="sxs-lookup"><span data-stu-id="1343c-115">Most users do not create a PowerShell Gallery account.</span></span>
<span data-ttu-id="1343c-116">アイテムを公開する予定がない場合や、PowerShell ギャラリーで "所有者に連絡" の機能を使用しない場合は、アカウントは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1343c-116">An account is not required unless you are going to publish an item or use the "Contact Owner" feature in the PowerShell Gallery.</span></span>
<span data-ttu-id="1343c-117">ユーザーから開始された電子メールのやり取りを除き、PowerShell ギャラリーにはアカウントを作成していないユーザーの個人を特定できるデータは格納されません。</span><span class="sxs-lookup"><span data-stu-id="1343c-117">Other than email correspondence initiated by the user, the PowerShell Gallery does not store personally identifiable data for users who have not created an account.</span></span>

<span data-ttu-id="1343c-118">PowerShell ギャラリーのアカウントを作成したユーザーは、PowerShell ギャラリーにアイテムを公開することができます。</span><span class="sxs-lookup"><span data-stu-id="1343c-118">Users who create a PowerShell Gallery account can publish items to the PowerShell Gallery.</span></span>
<span data-ttu-id="1343c-119">このアイテムは、PowerShell コードになると予想されますが、個人情報を含むその他の情報が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="1343c-119">Those items are expected to be PowerShell code, but may contain other information including personal information.</span></span>
<span data-ttu-id="1343c-120">次の情報は、PowerShell ギャラリーに公開されたすべてのアイテムを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1343c-120">The information below will show how you can get all the items you have published to the PowerShell Gallery.</span></span>

## <a name="dsr-export-of-powershell-gallery-data"></a><span data-ttu-id="1343c-121">PowerShell ギャラリー データの DSR エクスポート</span><span class="sxs-lookup"><span data-stu-id="1343c-121">DSR Export of PowerShell Gallery Data</span></span>

<span data-ttu-id="1343c-122">次のセクションは、PowerShell ギャラリーがデータ サブジェクト要求 (DSR) をどのようにサポートするかを、PowerShell ギャラリーに格納された情報をエクスポートする方法や、この情報の削除を依頼する方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="1343c-122">The following sections describe how the PowerShell Gallery supports data subject requests (DSR), by explaining how to export information stored in the PowerShell Gallery, and how to request deletion of this information.</span></span>

### <a name="email"></a><span data-ttu-id="1343c-123">電子メール</span><span class="sxs-lookup"><span data-stu-id="1343c-123">Email</span></span>

<span data-ttu-id="1343c-124">電子メールのやり取りには、次のいずれかが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1343c-124">Email correspondence may include any of the following:</span></span>

* <span data-ttu-id="1343c-125">コード分析のスキャンで PowerShell ギャラリーに公開されたアイテムに問題が検出された場合に、PowerShell ギャラリーのアイテムの所有者に送信された電子メール</span><span class="sxs-lookup"><span data-stu-id="1343c-125">Email sent to the owners of PowerShell Gallery items if the code analysis scans detected an issue with any item they have published to the PowerShell Gallery</span></span>
* <span data-ttu-id="1343c-126">"お問い合わせ先" ページの電子メール アドレス (cgadmin@microsoft.com) を使用して PowerShell ギャラリー チームのいずれかのユーザーに送信された電子メール</span><span class="sxs-lookup"><span data-stu-id="1343c-126">Email sent by anyone to the PowerShell Gallery team using the email address in the "Contact Us" page (cgadmin@microsoft.com)</span></span>
* <span data-ttu-id="1343c-127">PowerShell ギャラリーの "所有者に連絡" 機能を使用して PowerShell ギャラリーのアイテムの所有者に電子メールを送信する登録済みユーザー</span><span class="sxs-lookup"><span data-stu-id="1343c-127">Registered users who use the "Contact Owner" feature in the PowerShell Gallery to send email to the owner of an item in the PowerShell Gallery</span></span>

<span data-ttu-id="1343c-128">悪意のあるコードが PowerShell ギャラリーで検出された場合に想定されるセキュリティ調査をサポートするため、PowerShell ギャラリーとの間で送受信された電子メールには、90 日間のアイテム保持ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="1343c-128">Emails sent by or to the PowerShell Gallery have a retention policy of 90 days to support possible security investigations should malicious code be discovered on the PowerShell Gallery.</span></span>
<span data-ttu-id="1343c-129">このポリシーにより、電子メールは 90 日後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="1343c-129">Emails are deleted by policy after 90 days.</span></span>

<span data-ttu-id="1343c-130">90 日以内であれば、ご自分の電子メール アドレスと PowerShell ギャラリーとの間で送受信されたすべてのメールのコピーを要求することができます。</span><span class="sxs-lookup"><span data-stu-id="1343c-130">You may request copies of all emails sent to or from your email address and the PowerShell Gallery within the previous 90 days.</span></span>
<span data-ttu-id="1343c-131">このやり取りを要求するには、"DSR Request for emails relating to this account" という件名のメールを cgadmin@microsoft.com に送信します。</span><span class="sxs-lookup"><span data-stu-id="1343c-131">To request this correspondence, send an email to cgadmin@microsoft.com, with the title: "DSR Request for emails relating to this account".</span></span>
<span data-ttu-id="1343c-132">メッセージの本文には、要求する内容を記述してください (例: この電子メール アドレスとの間で送受信されたすべてのメールを送ってください)。ご自分の電子メール アドレスに関する、要求から 90 日以内のすべてのメールが 7 営業日以内に送信されます。</span><span class="sxs-lookup"><span data-stu-id="1343c-132">In the body of the message, state what information you are requesting (for example: Please send all emails sent to or received from this email address.) All emails involving your email address within 90 days of the request will be sent within 7 business days.</span></span>

### <a name="powershell-gallery-account-information"></a><span data-ttu-id="1343c-133">PowerShell ギャラリーのアカウント情報</span><span class="sxs-lookup"><span data-stu-id="1343c-133">PowerShell Gallery Account Information</span></span>

<span data-ttu-id="1343c-134">PowerShell ギャラリーのアカウントを作成している場合、次の手順を実行すると PowerShell ギャラリーに格納されているすべての個人情報を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="1343c-134">If you have created a PowerShell Gallery account, you can find all personal information that has been stored in PowerShell Gallery by taking the following steps:</span></span>

1. <span data-ttu-id="1343c-135">PowerShell ギャラリーにサインインし、ユーザー名をクリックします</span><span class="sxs-lookup"><span data-stu-id="1343c-135">Sign in to the PowerShell Gallery, then click on your username</span></span>
2. <span data-ttu-id="1343c-136">PowerShell ギャラリーのアカウントで使用される電子メール アドレスを示す [アカウント] ページが表示されます</span><span class="sxs-lookup"><span data-stu-id="1343c-136">The next page displayed is the Account page, which shows the email address used for the PowerShell Gallery account</span></span>

<span data-ttu-id="1343c-137">PowerShell ギャラリーで複数のアカウントを作成した場合は、アカウントごとにこの手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="1343c-137">If you have created more than one account in the PowerShell Gallery, you will need to repeat these steps for each account.</span></span>

### <a name="items-in-the-powershell-gallery"></a><span data-ttu-id="1343c-138">PowerShell ギャラリーのアイテム</span><span class="sxs-lookup"><span data-stu-id="1343c-138">Items in the PowerShell Gallery</span></span>

<span data-ttu-id="1343c-139">PowerShell ギャラリーに公開されたアイテムのエクスポートを迅速に行うため、PowerShell ギャラリーに "GetPSGalleryItemsForAuthor" のスクリプトを公開しました。</span><span class="sxs-lookup"><span data-stu-id="1343c-139">To facilitate exporting items published to the PowerShell Gallery, we have published the script "GetPSGalleryItemsForAuthor" to the PowerShell Gallery.</span></span>
<span data-ttu-id="1343c-140">このスクリプトにより、アイテムに格納された作成者情報に基づき、PowerShell ギャラリーに配置されたすべてのアイテムのすべてのバージョンのコピーがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="1343c-140">This script exports a copy of every version of every item put into the PowerShell Gallery based on the author information stored in the item.</span></span>

> [!NOTE]
> <span data-ttu-id="1343c-141">作成者は、自分のアイテムを公開するときに、アイテム マニフェストに格納されます。</span><span class="sxs-lookup"><span data-stu-id="1343c-141">The Author is stored in the item manifest when you publish your item.</span></span>
> <span data-ttu-id="1343c-142">作成者が PowerShell ギャラリーで使用するアカウントと同じ ID である保証はありません。</span><span class="sxs-lookup"><span data-stu-id="1343c-142">There is no guarantee that the Author is the same identity as the account you use in the PowerShell Gallery.</span></span>
> <span data-ttu-id="1343c-143">[作成者] フィールドで他の値を使用する場合は、このスクリプトを使用するときに、その値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1343c-143">If you use some other value in the Author field, you will need to supply that value when using this script.</span></span>

<span data-ttu-id="1343c-144">スクリプトは次の PowerShell コマンドを使用してダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="1343c-144">You may download the script by using the following PowerShell command:</span></span>

```powershell
Save-Script GetPSGalleryItemsForAuthor -path <local folder location> -repository psgallery
```

<span data-ttu-id="1343c-145">これで、次の PowerShell コマンドを実行してスクリプトを直接実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1343c-145">You can then run the script directly, by running the following PowerShell commands:</span></span>

```powershell
cd <local folder location >
.\GetPSGalleryItemsForAuthor.ps1
```

<span data-ttu-id="1343c-146">作成者と、自分のシステム上でアイテムを保存するフォルダーを指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="1343c-146">You will be prompted to supply the Author and a folder on your system where you want the items to be saved.</span></span>

## <a name="deleting-personal-data-from-the-powershell-gallery"></a><span data-ttu-id="1343c-147">PowerShell ギャラリーから個人データを削除する</span><span class="sxs-lookup"><span data-stu-id="1343c-147">Deleting Personal Data From The PowerShell Gallery</span></span>

<span data-ttu-id="1343c-148">ご自分の PowerShell ギャラリーのアカウント、または PowerShell ギャラリーで所有しているアイテムを削除するには、"GDPR Request for items relating to this account" という件名のメールを cgadmin@microsoft.com に送信します。</span><span class="sxs-lookup"><span data-stu-id="1343c-148">To delete your PowerShell Gallery account or any item you own in the PowerShell Gallery, send email to cgadmin@microsoft.com with the title: "GDPR Request for items relating to this account".</span></span>
<span data-ttu-id="1343c-149">メッセージの本文には、削除を依頼する情報を記述します。</span><span class="sxs-lookup"><span data-stu-id="1343c-149">In the body of the message state what information you want deleted.</span></span> <span data-ttu-id="1343c-150">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1343c-150">For example:</span></span>

* <span data-ttu-id="1343c-151">アイテム "アイテム名" のバージョン x.y.z を削除してください</span><span class="sxs-lookup"><span data-stu-id="1343c-151">Please delete version x.y.z of my item "item name"</span></span>
* <span data-ttu-id="1343c-152">アイテム "アイテム名" のすべてのバージョンを削除してください</span><span class="sxs-lookup"><span data-stu-id="1343c-152">Please delete all versions of my item "item name"</span></span>
* <span data-ttu-id="1343c-153">私の PowerShell ギャラリー アカウントを削除してください</span><span class="sxs-lookup"><span data-stu-id="1343c-153">Please delete my PowerShell Gallery account</span></span>

<span data-ttu-id="1343c-154">PowerShell ギャラリーの管理者が 7 営業日以内に返信します。</span><span class="sxs-lookup"><span data-stu-id="1343c-154">The PowerShell Gallery administrators will reply within 7 business days.</span></span>
<span data-ttu-id="1343c-155">指定したアイテムは、要求が送信された後、30 日以内に削除されます。</span><span class="sxs-lookup"><span data-stu-id="1343c-155">The items specified will be deleted within 30 days after the request is sent.</span></span>
