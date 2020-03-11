---
ms.date: 09/05/2018
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: PowerShell ギャラリーのアカウント設定
ms.openlocfilehash: db61c3fd8c73048b51f3411a8c1dab52fb03d08a
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78278108"
---
# <a name="powershell-gallery-account-settings"></a><span data-ttu-id="97dfb-103">PowerShell ギャラリーのアカウント設定</span><span class="sxs-lookup"><span data-stu-id="97dfb-103">PowerShell Gallery Account Settings</span></span>

<span data-ttu-id="97dfb-104">PowerShell ギャラリー アカウントは、ID にリンクされている公開されている名前です。</span><span class="sxs-lookup"><span data-stu-id="97dfb-104">Your PowerShell Gallery account is a publicly visible name that is linked to an identity.</span></span> <span data-ttu-id="97dfb-105">その ID は、`user@hotmail.com` または `user@outlook.com` のような Microsoft ID か、Azure Active Directory (AAD) アカウントのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="97dfb-105">That identity is either a Microsoft ID, like `user@hotmail.com` or `user@outlook.com`, or an Azure Active Directory (AAD) account.</span></span>

<span data-ttu-id="97dfb-106">PowerShell ギャラリーには、次のアカウント設定が用意されています。</span><span class="sxs-lookup"><span data-stu-id="97dfb-106">The PowerShell Gallery provides the following account settings:</span></span>

- <span data-ttu-id="97dfb-107">PowerShell ギャラリー アカウントに関連付けられている電子メール アカウント</span><span class="sxs-lookup"><span data-stu-id="97dfb-107">The email account associated with your PowerShell Gallery account</span></span>
- <span data-ttu-id="97dfb-108">PowerShell ギャラリーから送信された電子メール通知のオプション</span><span class="sxs-lookup"><span data-stu-id="97dfb-108">Options for email notifications sent from the PowerShell Gallery</span></span>
- <span data-ttu-id="97dfb-109">PowerShell ギャラリー アカウントに関連付けられているユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="97dfb-109">The user account associated with your PowerShell Gallery account</span></span>
- <span data-ttu-id="97dfb-110">PowerShell ギャラリー アカウントに関連付けられている画像</span><span class="sxs-lookup"><span data-stu-id="97dfb-110">The picture associated with your PowerShell Gallery account</span></span>

## <a name="email-address"></a><span data-ttu-id="97dfb-111">電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="97dfb-111">Email address</span></span>

<span data-ttu-id="97dfb-112">電子メール アドレスは、PowerShell ギャラリーの通知の送信先です。</span><span class="sxs-lookup"><span data-stu-id="97dfb-112">The email address is the destination for PowerShell Gallery notifications.</span></span> <span data-ttu-id="97dfb-113">ログイン アカウントと一致している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="97dfb-113">It does not have to match the login account.</span></span> <span data-ttu-id="97dfb-114">アクセス権がある任意の電子メール アカウントを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="97dfb-114">You may use any email account you have access to.</span></span> <span data-ttu-id="97dfb-115">PowerShell ギャラリーから直接、電子メール アドレスが他のユーザーに提供されることはありません。</span><span class="sxs-lookup"><span data-stu-id="97dfb-115">Your email address is never directly provided by the PowerShell Gallery to other users.</span></span>

![電子メール アドレスの変更](media/managing-account/PSGallery_AcccountEmailAddress.png)

<span data-ttu-id="97dfb-117">新しい電子メール アドレスを入力すると、PowerShell ギャラリーによって確認メールがそのアドレスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="97dfb-117">When you enter a new email address, the PowerShell Gallery sends a verification mail to that address.</span></span> <span data-ttu-id="97dfb-118">確認メールには、PowerShell ギャラリーに戻って変更プロセスを完了するためのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="97dfb-118">The verification mail contains a link back to the PowerShell Gallery to complete the change process.</span></span> <span data-ttu-id="97dfb-119">確認プロセスを完了するまで、すべての通知が変更前のアドレスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="97dfb-119">Until you complete the verification process, all notifications are sent to the previous address.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="97dfb-120">メール通知</span><span class="sxs-lookup"><span data-stu-id="97dfb-120">Email notifications</span></span>

<span data-ttu-id="97dfb-121">PowerShell ギャラリーには、次の通知オプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="97dfb-121">PowerShell Gallery provides the following notification options:</span></span>

- <span data-ttu-id="97dfb-122">Users can contact me through the PowerShell Gallery\(ユーザーが PowerShell ギャラリーを通じて連絡できるようにする\)</span><span class="sxs-lookup"><span data-stu-id="97dfb-122">Users can contact me through the PowerShell Gallery</span></span>
- <span data-ttu-id="97dfb-123">Notify me when an item is pushed to the PowerShell Gallery using my account\(自分のアカウントを使用して PowerShell ギャラリーにパッケージがプッシュされたときに通知を受け取る\)</span><span class="sxs-lookup"><span data-stu-id="97dfb-123">Notify me when an package is pushed to the PowerShell Gallery using my account</span></span>

![電子メール アドレスの変更](media/managing-account/PSGallery_AccountEmailOptions.png)

<span data-ttu-id="97dfb-125">このページで説明したように、PowerShell ギャラリーからの重要な通知を無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="97dfb-125">As noted on the page, critical notifications from the PowerShell Gallery can't be disabled.</span></span>
<span data-ttu-id="97dfb-126">チェックの内容は次のとおりです</span><span class="sxs-lookup"><span data-stu-id="97dfb-126">These include:</span></span>

- <span data-ttu-id="97dfb-127">セキュリティ通知</span><span class="sxs-lookup"><span data-stu-id="97dfb-127">Security notifications</span></span>
- <span data-ttu-id="97dfb-128">PowerShell ギャラリー管理者からのアカウント管理の通知</span><span class="sxs-lookup"><span data-stu-id="97dfb-128">Account management notifications from PowerShell Gallery administrators</span></span>
- <span data-ttu-id="97dfb-129">送信したものに対して PowerShell ギャラリーで実行されたテストに関する通知</span><span class="sxs-lookup"><span data-stu-id="97dfb-129">Notifications about the tests run by the PowerShell Gallery for submissions you have made</span></span>

## <a name="change-your-login-account"></a><span data-ttu-id="97dfb-130">ログイン アカウントの変更</span><span class="sxs-lookup"><span data-stu-id="97dfb-130">Change your login account</span></span>

<span data-ttu-id="97dfb-131">ログイン アカウントを変更するには、現在のアカウントでサインインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="97dfb-131">To change the login account, you must be signed in with the current account.</span></span> <span data-ttu-id="97dfb-132">変更を完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="97dfb-132">Use the following steps to complete the change.</span></span>

![ログイン アカウントの設定](media/managing-account/PSGallery_LoginAccountSettings.png)

1. <span data-ttu-id="97dfb-134">**[アカウントの変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97dfb-134">Click on **Change Account**.</span></span> <span data-ttu-id="97dfb-135">ログイン アカウントの変更が PowerShell ギャラリーでのそのアカウントのすべての使用に適用されることを説明するポップアップ ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97dfb-135">A pop-up window explains that changing the login account applies to all uses of that account in the PowerShell Gallery.</span></span> <span data-ttu-id="97dfb-136">情報を確認して、 **[OK]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="97dfb-136">Review the information, then click **OK** to continue.</span></span>

   ![ログイン アカウントの設定](media/managing-account/PSGallery_LoginAccountChange-1.png)

2. <span data-ttu-id="97dfb-138">_新しいアカウント_を使用してサインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="97dfb-138">You are then prompted to sign in using the _new account_.</span></span>

   ![ログイン アカウントの設定](media/managing-account/PSGallery_LoginAccountChange-2.png)

3. <span data-ttu-id="97dfb-140">**[次へ]** をクリックすると、現在のアカウントを使用してサインインしていることを知らせるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97dfb-140">When you click **Next**, you see a message that you are signed in using the current account.</span></span>
   <span data-ttu-id="97dfb-141">**[Sign out and sign in with a different account]\(サインアウトして別のアカウントでサインインする\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97dfb-141">Click **Sign out and sign in with a different account**.</span></span>

   ![ログイン アカウントの設定](media/managing-account/PSGallery_LoginAccountChange-3.png)

4. <span data-ttu-id="97dfb-143">新しいアカウントのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="97dfb-143">Enter the password of the new account.</span></span> <span data-ttu-id="97dfb-144">パスワードを入力すると、ログイン アカウントが更新されたことを示す [アカウント設定] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="97dfb-144">After entering the password, you are returned to the Account Settings page showing you that the login account has been updated.</span></span>


## <a name="enable-two-factor-authentication-2fa"></a><span data-ttu-id="97dfb-145">2 要素認証 (2FA) の有効化</span><span class="sxs-lookup"><span data-stu-id="97dfb-145">Enable Two-Factor Authentication (2FA)</span></span>

<span data-ttu-id="97dfb-146">PowerShell ギャラリーに手動で公開するすべてのユーザーには、2 要素認証を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="97dfb-146">Two-factor authentication is recommended for all users who publish manually to the PowerShell Gallery.</span></span> <span data-ttu-id="97dfb-147">2 要素認証を有効にするには、ログイン アカウントに少なくとも 2 つの認証形式が登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="97dfb-147">To enable two-factor authentication, the login account must have at least two forms of authentication registered.</span></span> <span data-ttu-id="97dfb-148">1 つはパスワードで、他の形式には以下を指定できます。</span><span class="sxs-lookup"><span data-stu-id="97dfb-148">One is a password and the other forms can be:</span></span>

- <span data-ttu-id="97dfb-149">テキスト メッセージを受信できる電話番号</span><span class="sxs-lookup"><span data-stu-id="97dfb-149">A phone number that can receive text messages</span></span>
- <span data-ttu-id="97dfb-150">携帯電話の Microsoft Authenticator などの登録済みの認証子アプリケーション</span><span class="sxs-lookup"><span data-stu-id="97dfb-150">A registered authenticator application, such as Microsoft Authenticator for your mobile phone</span></span>

<span data-ttu-id="97dfb-151">これらの認証形式は、ご自分の AAD アカウント情報または Microsoft ID アカウントのセキュリティ設定で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97dfb-151">These forms of authentication must be configured in your AAD account information or in your Microsoft ID Account Security settings.</span></span>

<span data-ttu-id="97dfb-152">2FA を有効にすると、PowerShell ギャラリーにサインインするたびに、構成済みの認証形式を使用した認証を求められます。</span><span class="sxs-lookup"><span data-stu-id="97dfb-152">Once 2FA is enabled, you are required to authenticate using the configured forms of authentication every time you sign in to the PowerShell Gallery.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97dfb-153">PowerShell ギャラリー サイトで 2 要素認証を有効にした場合、ログイン アカウントのすべての使用に対して 2FA を有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="97dfb-153">Enabling two-factor authentication for the PowerShell Gallery site does not require you to enable 2FA for all uses of your login account.</span></span> <span data-ttu-id="97dfb-154">詳細については、「[2 段階認証について](https://support.microsoft.com/help/12408/microsoft-account-about-two-step-verification)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97dfb-154">For more information, see [About two-step verification](https://support.microsoft.com/help/12408/microsoft-account-about-two-step-verification).</span></span>

## <a name="change-your-profile-picture"></a><span data-ttu-id="97dfb-155">プロファイル写真の変更</span><span class="sxs-lookup"><span data-stu-id="97dfb-155">Change your profile picture</span></span>

<span data-ttu-id="97dfb-156">PowerShell ギャラリーでは、プロファイルに関連付けられている画像の保存および表示を Gravatar に依存しています。</span><span class="sxs-lookup"><span data-stu-id="97dfb-156">The PowerShell Gallery relies on Gravatar to store and display the picture associated with your profile.</span></span> <span data-ttu-id="97dfb-157">プロファイル画像を更新するには、[Gravatar.com](http://www.gravatar.com/) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="97dfb-157">To update your profile image, visit [Gravatar.com](http://www.gravatar.com/).</span></span>
