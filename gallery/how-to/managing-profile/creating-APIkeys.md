---
ms.date: 09/10/2018
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: API キーの管理
ms.openlocfilehash: 954eb27c25babdb8efe50c13caf5f2d287c6b3e3
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50002515"
---
# <a name="managing-api-keys"></a><span data-ttu-id="b4a24-103">API キーの管理</span><span class="sxs-lookup"><span data-stu-id="b4a24-103">Managing API keys</span></span>

<span data-ttu-id="b4a24-104">PowerShell ギャラリーでは、さまざまな公開要件をサポートするために複数の API キーの作成をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b4a24-104">The PowerShell Gallery supports creating multiple API keys to support a range of publishing requirements.</span></span> <span data-ttu-id="b4a24-105">1 つの API キーを 1 つ以上のパッケージに適用することができます。API キーには特定の権限を付与でき、有効期限があります。</span><span class="sxs-lookup"><span data-stu-id="b4a24-105">An API key can apply to one or more packages, grants specific privileges, and has an expiration date.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4a24-106">スコープ付き API キーの導入前に PowerShell ギャラリーに公開したユーザーは、"フル アクセス API キー" を持ちます。</span><span class="sxs-lookup"><span data-stu-id="b4a24-106">Users who published to the PowerShell Gallery prior to the introduction of scoped API keys will have a "Full access API key".</span></span> <span data-ttu-id="b4a24-107">フル アクセス キーには、スコープ付きの API キーに組み込まれているセキュリティ強化はありません。</span><span class="sxs-lookup"><span data-stu-id="b4a24-107">The full access keys do not have the security improvements built into scoped API keys.</span></span> <span data-ttu-id="b4a24-108">フル アクセス キーには有効期限はなく、ユーザーが所有するすべてのものに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b4a24-108">The full access keys never expires and apply to everything owned by the user.</span></span> <span data-ttu-id="b4a24-109">このキーを削除すると、再作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4a24-109">If you delete this key, it cannot be recreated.</span></span>

<span data-ttu-id="b4a24-110">次の図は、スコープ付き API キーを作成するときに使用できるオプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="b4a24-110">The following image shows the options available when creating a scoped API key.</span></span>

![API キーの作成](../../Images/PSGallery_KeyScoped.png)

<span data-ttu-id="b4a24-112">この例では、**AzureRMDataFactory** という名前の API キーを作成しました。</span><span class="sxs-lookup"><span data-stu-id="b4a24-112">In this example, we created an API key named **AzureRMDataFactory**.</span></span> <span data-ttu-id="b4a24-113">このキーの値は、'AzureRM.DataFactory' で始まる名前を持つパッケージをプッシュするために使用でき、365 日間有効です。</span><span class="sxs-lookup"><span data-stu-id="b4a24-113">This key value can be used to push packages with names that begin with 'AzureRM.DataFactory' and is valid for 365 days.</span></span> <span data-ttu-id="b4a24-114">これは、同じ組織内の別のチームが異なるパッケージで作業する場合の一般的なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="b4a24-114">This is a typical scenario when different teams within the same organization work on different packages.</span></span> <span data-ttu-id="b4a24-115">チームのメンバーは、作業する特定のパッケージに対する特権を付与するキーを持ちます。</span><span class="sxs-lookup"><span data-stu-id="b4a24-115">The members of the team have a key that grants them privileges for the specific package they work on.</span></span>
<span data-ttu-id="b4a24-116">有効期限の値により、古いキーや忘れられたキーの使用を防止します。</span><span class="sxs-lookup"><span data-stu-id="b4a24-116">The expiration value prevents the use of stale or forgotten keys.</span></span>

## <a name="using-glob-patterns"></a><span data-ttu-id="b4a24-117">glob パターンを使用する</span><span class="sxs-lookup"><span data-stu-id="b4a24-117">Using glob patterns</span></span>

<span data-ttu-id="b4a24-118">複数のパッケージで作業する場合、glob パターンを使用して複数のパッケージをグループとして一致させることができます。</span><span class="sxs-lookup"><span data-stu-id="b4a24-118">If you work on multiple packages, you can use globbing patterns to match multiple packages as a group.</span></span> <span data-ttu-id="b4a24-119">glob パターンに一致するすべての新しいパッケージに API キーのアクセス許可が適用されます。</span><span class="sxs-lookup"><span data-stu-id="b4a24-119">API key permissions apply to all new packages matching the glob pattern.</span></span> <span data-ttu-id="b4a24-120">たとえば、前の例では、**glob パターン** 値に 'AzureRM.DataFactory\*' を使用しています。</span><span class="sxs-lookup"><span data-stu-id="b4a24-120">For example, the previous example uses a **Glob Pattern** value of 'AzureRM.DataFactory\*'.</span></span> <span data-ttu-id="b4a24-121">パッケージが glob パターンと一致するため、このキーを使用して 'AzureRm.DataFactoryV2.Netcore' という名前のパッケージをプッシュすることができます。</span><span class="sxs-lookup"><span data-stu-id="b4a24-121">You can push a package named 'AzureRm.DataFactoryV2.Netcore' using this key since the package matches the glob pattern.</span></span>

## <a name="create-api-keys-securely"></a><span data-ttu-id="b4a24-122">API キーを安全に作成する</span><span class="sxs-lookup"><span data-stu-id="b4a24-122">Create API keys securely</span></span>

<span data-ttu-id="b4a24-123">セキュリティのため、新しく作成されたキー値は画面に表示されず、次に示すように [コピー] ボタンを使用してのみ入手できます。</span><span class="sxs-lookup"><span data-stu-id="b4a24-123">For security, a newly created key value is never shown on the screen and is only available with the Copy button, as shown below.</span></span>

![新しい API キー値を取得する](../../Images/PSGallery_CopyCreatedKey.png)

> [!IMPORTANT]
> <span data-ttu-id="b4a24-125">API キー値は、作成直後または更新直後にのみコピーできます。</span><span class="sxs-lookup"><span data-stu-id="b4a24-125">You can only copy the API key value immediately after creating or refreshing it.</span></span> <span data-ttu-id="b4a24-126">キー値は表示されず、ページを更新すると、もう一度アクセスすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="b4a24-126">It will not be displayed, and will not be accessible again after the page is refreshed.</span></span> <span data-ttu-id="b4a24-127">キー値を紛失した場合は、[再生成] を使用して、再生成された後にキーをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4a24-127">If you lose the key value, you must use Regenerate, and copy the key after it is regenerated.</span></span>

## <a name="key-permissions-and-expiration"></a><span data-ttu-id="b4a24-128">キーのアクセス許可と有効期限</span><span class="sxs-lookup"><span data-stu-id="b4a24-128">Key permissions and expiration</span></span>

<span data-ttu-id="b4a24-129">スコープ付き API キーには、次のアクセス許可のいずれかを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b4a24-129">Scoped API keys can assign any of the following permissions:</span></span>

- <span data-ttu-id="b4a24-130">新しいパッケージをプッシュする</span><span class="sxs-lookup"><span data-stu-id="b4a24-130">Push new packages</span></span>
- <span data-ttu-id="b4a24-131">新しいパッケージをプッシュまたはパッケージを更新する</span><span class="sxs-lookup"><span data-stu-id="b4a24-131">Push new or update packages</span></span>
- <span data-ttu-id="b4a24-132">パッケージを一覧から削除する</span><span class="sxs-lookup"><span data-stu-id="b4a24-132">Unlist packages</span></span>

<span data-ttu-id="b4a24-133">新しいキーにはすべて有効期限があります。</span><span class="sxs-lookup"><span data-stu-id="b4a24-133">Every new key has an expiration.</span></span> <span data-ttu-id="b4a24-134">有効期限の値の単位は日です。</span><span class="sxs-lookup"><span data-stu-id="b4a24-134">The expiration value is measured in days.</span></span> <span data-ttu-id="b4a24-135">有効期限の有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b4a24-135">The possible values for expiration are:</span></span>

- <span data-ttu-id="b4a24-136">1 日</span><span class="sxs-lookup"><span data-stu-id="b4a24-136">1 day</span></span>
- <span data-ttu-id="b4a24-137">90 日</span><span class="sxs-lookup"><span data-stu-id="b4a24-137">90 days</span></span>
- <span data-ttu-id="b4a24-138">180 日</span><span class="sxs-lookup"><span data-stu-id="b4a24-138">180 days</span></span>
- <span data-ttu-id="b4a24-139">270 日</span><span class="sxs-lookup"><span data-stu-id="b4a24-139">270 days</span></span>
- <span data-ttu-id="b4a24-140">365 日 (既定値)</span><span class="sxs-lookup"><span data-stu-id="b4a24-140">365 days (default)</span></span>

<span data-ttu-id="b4a24-141">キーが作成されたら、これらの設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4a24-141">These settings cannot be changed once the key is created.</span></span> <span data-ttu-id="b4a24-142">有効期限のない新しいキーを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4a24-142">You cannot create a new key that never expires.</span></span>

## <a name="editing-and-deleting-existing-api-keys"></a><span data-ttu-id="b4a24-143">既存の API キーの編集と削除</span><span class="sxs-lookup"><span data-stu-id="b4a24-143">Editing and deleting existing API keys</span></span>

<span data-ttu-id="b4a24-144">既存のキーの一部の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b4a24-144">You can change some settings of an existing key.</span></span> <span data-ttu-id="b4a24-145">前述したように、既存の API キーのセキュリティ スコープを変更したり、有効期限を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4a24-145">As previously noted, you cannot modify the security scope for an existing API key or change the expiration.</span></span> <span data-ttu-id="b4a24-146">変更可能なオプションは、次のスクリーンショットに示されているとおりです。</span><span class="sxs-lookup"><span data-stu-id="b4a24-146">The changeable options are shown in the following screenshot:</span></span>

![新しい API キー値を取得する](../../Images/PSGallery_EditAPIKey.png)

<span data-ttu-id="b4a24-148">キーによって制御されるパッケージを変更するには、一覧から個々のパッケージを選択するか、glob パターンを変更します。</span><span class="sxs-lookup"><span data-stu-id="b4a24-148">To change the packages controlled by a key, you can choose individual packages from the list or change the glob pattern.</span></span>

<span data-ttu-id="b4a24-149">**[再生成]** をクリックすると、新しいキー値が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b4a24-149">Clicking **Regenerate** creates a new key value.</span></span> <span data-ttu-id="b4a24-150">キーを最初に作成したときと同じく、更新後すぐにキー値を**コピー**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4a24-150">Just like when you initially created the key, you must **Copy** the key value immediately after updating it.</span></span> <span data-ttu-id="b4a24-151">このページから移動すると、**[コピー]** オプションは使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b4a24-151">The **Copy** option is not available once you leave this page.</span></span>

<span data-ttu-id="b4a24-152">**[削除]** をクリックすると、確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4a24-152">Clicking **Delete** displays a confirmation message.</span></span> <span data-ttu-id="b4a24-153">キーが削除されると、そのキーは使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b4a24-153">Once a key is deleted, it will be unusable.</span></span>

## <a name="key-expiration"></a><span data-ttu-id="b4a24-154">キーの有効期限</span><span class="sxs-lookup"><span data-stu-id="b4a24-154">Key expiration</span></span>

<span data-ttu-id="b4a24-155">有効期限の 10 日前に、PowerShell ギャラリーから警告メールが API キーのアカウント所有者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="b4a24-155">Ten days before the expiration, the PowerShell Gallery sends a warning email the account holder of the API key.</span></span> <span data-ttu-id="b4a24-156">有効期限を過ぎると、キーは使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b4a24-156">After expiration, the key is unusable.</span></span> <span data-ttu-id="b4a24-157">API キーの管理ページの上部に、キーが無効になったことを示す警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4a24-157">A warning message is displayed at the top of the API key management page showing which keys are no longer valid.</span></span> <span data-ttu-id="b4a24-158">新しいキー値を生成することができます。</span><span class="sxs-lookup"><span data-stu-id="b4a24-158">You can generate a new key value.</span></span>
