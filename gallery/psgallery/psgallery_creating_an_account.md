---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: PowerShell ギャラリー アカウントを作成する
ms.openlocfilehash: c9c263a1926957cbdf059e062326b1903c117f46
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
## <a name="creating-a-powershell-gallery-account"></a><span data-ttu-id="47e94-103">PowerShell ギャラリー アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="47e94-103">Creating a PowerShell Gallery Account</span></span>

<span data-ttu-id="47e94-104">PowerShell ギャラリー アカウントは、PowerShell ギャラリーに何らかのアイテムを公開する前に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47e94-104">A PowerShell Gallery account must be established before publishing anything to the PowerShell Gallery.</span></span>
<span data-ttu-id="47e94-105">PowerShell ギャラリー アカウントは、Azure Active Directory のメールが有効なアカウント、または Microsoft のメール アカウント (ドメインが outlook.com、hotmail.com など) に紐付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="47e94-105">The PowerShell Gallery accounts must be linked to an Azure Active Directory email-enabled account, or a Microsoft email account (with a domain of outlook.com, hotmail.com, etc.)</span></span>

<span data-ttu-id="47e94-106">PowerShell ギャラリー アカウントを作成するには、https://PowerShellGallery.com にアクセスして [Register]\(登録\) をクリックしてください (下の図をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="47e94-106">To create a PowerShell Gallery account, go to https://PowerShellGallery.com and click on "Register" (see the image below).</span></span>

![新規アカウントの作成](./images/CreatingAccount-Register.png)

<span data-ttu-id="47e94-108">Azure Active Directory アカウントを使用する場合は、次のページで [職場または学校アカウント] を選択し、ご利用のアカウントでログインします。</span><span class="sxs-lookup"><span data-stu-id="47e94-108">In the next page, to use an Azure Active Directory account, select "Work or School Account", and log in with your account.</span></span>
<span data-ttu-id="47e94-109">Microsoft アカウント (Outlook.com や Hotmail.com などのドメイン) を使用する場合、[個人アカウント] を選択してログインします。</span><span class="sxs-lookup"><span data-stu-id="47e94-109">To use a Microsoft account - such as one in a Hotmail.com or Outlook.com domain - choose "Personal Account", and log in.</span></span>

<span data-ttu-id="47e94-110">ログインすると、PowerShell ギャラリーで使用するユーザー名を入力するよう求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="47e94-110">Once you have logged in, you will be prompted to create a username for the PowerShell Gallery.</span></span>
<span data-ttu-id="47e94-111">リンクされている利用規約とプライバシー ポリシーを確認したら、ユーザー名を入力して [登録] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47e94-111">Review the Terms of Use and Privacy Policy that are linked in, enter a username, and then click Register.</span></span>

<span data-ttu-id="47e94-112">注: このアカウント名は、一度作成すると変更できません。</span><span class="sxs-lookup"><span data-stu-id="47e94-112">Note: This account name cannot be changed once it is created.</span></span>
<span data-ttu-id="47e94-113">これに関連するその他の詳細については、「[アイテムの所有者を管理する](https://msdn.microsoft.com/powershell/gallery/psgallery/managing-item-owners)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="47e94-113">See [Managing Item Owners](https://msdn.microsoft.com/powershell/gallery/psgallery/managing-item-owners) for additional details related to this.</span></span>

## <a name="recommended-practices-for-powershell-gallery-accounts"></a><span data-ttu-id="47e94-114">PowerShell ギャラリー アカウントの推奨プラクティス</span><span class="sxs-lookup"><span data-stu-id="47e94-114">Recommended Practices for PowerShell Gallery Accounts</span></span>

<span data-ttu-id="47e94-115">PowerShell ギャラリー アカウントで使用されるメール アカウントを積極的に監視することが重要です。</span><span class="sxs-lookup"><span data-stu-id="47e94-115">It is important that the email account used with your PowerShell Gallery account be actively monitored.</span></span>
<span data-ttu-id="47e94-116">PowerShell ギャラリー アイテムの所有者とのやりとりはすべて、ご利用の PowerShell ギャラリー アカウントに関連付けられたアドレスでのメールで行われます。</span><span class="sxs-lookup"><span data-stu-id="47e94-116">All communiction with owners of PowerShell Gallery items is through the email using the address associated with your PowerShell Gallery account.</span></span>
<span data-ttu-id="47e94-117">Microsoft からアイテムの所有者に連絡がとれない場合、特定の状況下では、運用チームにアイテムの削除を求めることがあります。</span><span class="sxs-lookup"><span data-stu-id="47e94-117">If we are unable to contact an item owner, the Operations team may be required to delete an item under some circumstances.</span></span>

<span data-ttu-id="47e94-118">PowerShell ギャラリーに公開を行う組織が、その目的で Outlook.com や別の Microsoft アカウントのドメインを使用して一意のアカウントを作成することは頻繁にあります。</span><span class="sxs-lookup"><span data-stu-id="47e94-118">Organizations that publish to the PowerShell Gallery often create a unique account for that purpose in Outlook.com, or another Microsoft account domain.</span></span>
<span data-ttu-id="47e94-119">多くの場合、そのアカウントは定期的に監視されません。</span><span class="sxs-lookup"><span data-stu-id="47e94-119">In many cases that account is not regularly monitored.</span></span>
<span data-ttu-id="47e94-120">こうした場合のベスト プラクティスは、Outlook の転送機能を使用して、アイテム所有者の監視対象となる別のアカウント (通常は組織内のアカウント) にメールを送信することです。</span><span class="sxs-lookup"><span data-stu-id="47e94-120">A best practice in that case is to use Outlook Forwarding to send email to another account, typically one within the organization, that will be monitored by the item owner(s).</span></span>

<span data-ttu-id="47e94-121">1 つのアイテムに複数の所有者が関連付けられている場合、PowerShell ギャラリーから発生するやりとりはすべて、すべての所有者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="47e94-121">If there are multiple owners associated with an item, all communications that come from the PowerShell Gallery will go to all owners.</span></span>
<span data-ttu-id="47e94-122">アイテムへの所有者の追加について詳しくは、「[アイテムの所有者を管理する](https://msdn.microsoft.com/powershell/gallery/psgallery/managing-item-owners)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="47e94-122">See [Managing Item Owners](https://msdn.microsoft.com/powershell/gallery/psgallery/managing-item-owners) for additional details on adding owners to an item.</span></span>