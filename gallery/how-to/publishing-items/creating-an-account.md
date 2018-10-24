---
ms.date: 09/11/2018
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: PowerShell ギャラリー アカウントを作成する
ms.openlocfilehash: 08d18310d9e18b00bd9e22efcc552dfd29f8982c
ms.sourcegitcommit: e46b868f56f359909ff7c8230b1d1770935cce0e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "45522838"
---
# <a name="creating-a-powershell-gallery-account"></a><span data-ttu-id="1a3a6-103">PowerShell ギャラリー アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="1a3a6-103">Creating a PowerShell Gallery account</span></span>

<span data-ttu-id="1a3a6-104">PowerShell ギャラリーに何らかのアイテムを公開する前に、PowerShell ギャラリー アカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-104">You must create a PowerShell Gallery account before publishing anything to the PowerShell Gallery.</span></span>
<span data-ttu-id="1a3a6-105">PowerShell ギャラリー アカウントは、電子メール対応のログイン アカウントにリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-105">PowerShell Gallery accounts must be linked to an email-enabled login account.</span></span> <span data-ttu-id="1a3a6-106">このアカウントには、Azure Active Directory アカウントまたは outlook.com や hotmail.com の電子メール アカウントのような Microsoft ID を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-106">This account can be an Azure Active Directory account or a Microsoft ID, like an email account from outlook.com or hotmail.com.</span></span>

<span data-ttu-id="1a3a6-107">PowerShell ギャラリー アカウントを作成するには、[https://PowerShellGallery.com](https://PowerShellGallery.com) にアクセスして、次の図のように、**[サインイン]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-107">To create a PowerShell Gallery account, go to [https://PowerShellGallery.com](https://PowerShellGallery.com) and click on **Sign in** as shown in the following image.</span></span>

![新規アカウントの作成](../../Images/CreateAccount-Register.png)

<span data-ttu-id="1a3a6-109">Azure Active Directory アカウントを使用するには、**[職場または学校アカウント]** を選択し、ご利用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-109">To use an Azure Active Directory account, select **Work or School Account**, and sign in with your account.</span></span> <span data-ttu-id="1a3a6-110">Microsoft ID を使用するには、**[個人用アカウント]** を選択してサインインします。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-110">To use a Microsoft ID, choose **Personal Account** and sign in.</span></span>

<span data-ttu-id="1a3a6-111">次に、PowerShell ギャラリーで使用するユーザー名を作成するように求められます。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-111">Next, you are prompted to create a username for the PowerShell Gallery.</span></span> <span data-ttu-id="1a3a6-112">利用規約とプライバシー ポリシーを確認したら、ユーザー名を入力して **[登録]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-112">Review the Terms of Use and Privacy Policy, enter a username, and then click **Register**.</span></span>

> [!NOTE]
> <span data-ttu-id="1a3a6-113">アカウント名は、一度作成すると変更できません。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-113">The account name cannot be changed once it is created.</span></span> <span data-ttu-id="1a3a6-114">詳細については、「[アイテムの所有者を管理する](managing-item-owners.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-114">For more information, see [Managing Item Owners](managing-item-owners.md).</span></span>

## <a name="recommended-practices-for-powershell-gallery-accounts"></a><span data-ttu-id="1a3a6-115">PowerShell ギャラリー アカウントの推奨プラクティス</span><span class="sxs-lookup"><span data-stu-id="1a3a6-115">Recommended practices for PowerShell Gallery accounts</span></span>

<span data-ttu-id="1a3a6-116">PowerShell ギャラリー アカウントで使用される電子メール アカウントを積極的に監視することが重要です。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-116">It's important to actively monitor the email account used with your PowerShell Gallery account.</span></span> <span data-ttu-id="1a3a6-117">この電子メール アドレスは、PowerShell ギャラリー アイテムの所有者とのすべての通信で使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-117">All communication with owners of PowerShell Gallery items is through this email address.</span></span> <span data-ttu-id="1a3a6-118">PowerShell ギャラリーの運用チームがアイテムの所有者に連絡がとれない場合、アイテムを削除するよう求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-118">If the PowerShell Gallery Operations team is unable to contact an item owner, we may be required to delete an item.</span></span>

<span data-ttu-id="1a3a6-119">PowerShell ギャラリーに公開を行う組織が、その目的で一意の外部アカウントを作成することは頻繁にあります。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-119">Organizations that publish to the PowerShell Gallery often create a unique external account for that purpose.</span></span> <span data-ttu-id="1a3a6-120">電子メールの転送を使用して、組織内のアドレスに通知を転送することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-120">We recommend you use email forwarding to forward notifications to an address within your organization.</span></span>

<span data-ttu-id="1a3a6-121">1 つのアイテムに複数の所有者が関連付けられている場合は、PowerShell ギャラリーのすべての通知がすべての所有者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-121">When multiple owners are associated with an item, all PowerShell Gallery notifications are sent to all owners.</span></span> <span data-ttu-id="1a3a6-122">詳細については、「[アイテムの所有者を管理する](managing-item-owners.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a3a6-122">For more information, see [Managing Item Owners](managing-item-owners.md).</span></span>
