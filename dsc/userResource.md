---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC User リソース
ms.openlocfilehash: 1c3efa8e3bf945c45834cbea7ddb0a6c3ffc5f45
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
#<a name="dsc-user-resource"></a><span data-ttu-id="afe0b-103">DSC User リソース#</span><span class="sxs-lookup"><span data-stu-id="afe0b-103">DSC User Resource#</span></span>


><span data-ttu-id="afe0b-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="afe0b-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>


<span data-ttu-id="afe0b-105">PowerShell Desired State Configuration (DSC) の __User__ リソースは、ターゲット ノード上でローカル ユーザー アカウントを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="afe0b-105">The __User__ resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local user accounts on the target node.</span></span>


##<a name="syntax"></a><span data-ttu-id="afe0b-106">Syntax##</span><span class="sxs-lookup"><span data-stu-id="afe0b-106">Syntax##</span></span>

```
User [string] #ResourceName
{
    UserName = [string]
    [ Description = [string] ]
    [ Disabled = [bool] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ FullName = [string] ]
    [ Password = [PSCredential] ]
    [ PasswordChangeNotAllowed = [bool] ]
    [ PasswordChangeRequired = [bool] ]
    [ PasswordNeverExpires = [bool] ]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="afe0b-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="afe0b-107">Properties</span></span>
|  <span data-ttu-id="afe0b-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="afe0b-108">Property</span></span>  |  <span data-ttu-id="afe0b-109">説明</span><span class="sxs-lookup"><span data-stu-id="afe0b-109">Description</span></span>   |
|---|---|
| <span data-ttu-id="afe0b-110">UserName</span><span class="sxs-lookup"><span data-stu-id="afe0b-110">UserName</span></span>| <span data-ttu-id="afe0b-111">特定の状態を保証するアカウント名を示します。</span><span class="sxs-lookup"><span data-stu-id="afe0b-111">Indicates the account name for which you want to ensure a specific state.</span></span>|
| <span data-ttu-id="afe0b-112">説明</span><span class="sxs-lookup"><span data-stu-id="afe0b-112">Description</span></span>| <span data-ttu-id="afe0b-113">ユーザー アカウントのために使用する説明を示します。</span><span class="sxs-lookup"><span data-stu-id="afe0b-113">Indicates the description you want to use for the user account.</span></span>|
| <span data-ttu-id="afe0b-114">無効</span><span class="sxs-lookup"><span data-stu-id="afe0b-114">Disabled</span></span>| <span data-ttu-id="afe0b-115">アカウントが有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="afe0b-115">Indicates if the account is enabled.</span></span> <span data-ttu-id="afe0b-116">このアカウントを無効にするには、このプロパティを __$true__ に設定し、有効にするには __$false__ に設定します。</span><span class="sxs-lookup"><span data-stu-id="afe0b-116">Set this property to __$true__ to ensure that this account is disabled, and set it to __$false__ to ensure that it is enabled.</span></span>|
| <span data-ttu-id="afe0b-117">Ensure</span><span class="sxs-lookup"><span data-stu-id="afe0b-117">Ensure</span></span>| <span data-ttu-id="afe0b-118">アカウントが存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="afe0b-118">Indicates if the account exists.</span></span> <span data-ttu-id="afe0b-119">このアカウントが存在することを保証するには、このプロパティを "Present" に設定し、アカウントが存在しないことを保証するには、"Absent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="afe0b-119">Set this property to "Present" to ensure that the account exists, and set it to "Absent" to ensure that the account does not exist.</span></span>|
| <span data-ttu-id="afe0b-120">FullName</span><span class="sxs-lookup"><span data-stu-id="afe0b-120">FullName</span></span>| <span data-ttu-id="afe0b-121">ユーザー アカウントのために使用する完全名の文字列を表します。</span><span class="sxs-lookup"><span data-stu-id="afe0b-121">Represents a string with the full name you want to use for the user account.</span></span>|
| <span data-ttu-id="afe0b-122">Password</span><span class="sxs-lookup"><span data-stu-id="afe0b-122">Password</span></span>| <span data-ttu-id="afe0b-123">このアカウントに使用するパスワードを示します。</span><span class="sxs-lookup"><span data-stu-id="afe0b-123">Indicates the password you want to use for this account.</span></span> |
| <span data-ttu-id="afe0b-124">PasswordChangeNotAllowed</span><span class="sxs-lookup"><span data-stu-id="afe0b-124">PasswordChangeNotAllowed</span></span>| <span data-ttu-id="afe0b-125">ユーザーがパスワードを変更できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="afe0b-125">Indicates if the user can change the password.</span></span> <span data-ttu-id="afe0b-126">ユーザーがパスワードを変更できないようにするには、このプロパティを __$true__ に設定し、ユーザーがパスワードを変更できるようにするには、__$false__ に設定します。</span><span class="sxs-lookup"><span data-stu-id="afe0b-126">Set this property to __$true__ to ensure that the user cannot change the password, and set it to __$false__ to allow the user to change the password.</span></span> <span data-ttu-id="afe0b-127">既定値は __$false__ です。</span><span class="sxs-lookup"><span data-stu-id="afe0b-127">The default value is __$false__.</span></span>|
| <span data-ttu-id="afe0b-128">PasswordChangeRequired</span><span class="sxs-lookup"><span data-stu-id="afe0b-128">PasswordChangeRequired</span></span>| <span data-ttu-id="afe0b-129">ユーザーが次回ログオンしたときにパスワードを変更する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="afe0b-129">Indicates if the user must change the password at the next sign in.</span></span> <span data-ttu-id="afe0b-130">ユーザーがパスワードを変更する必要がある場合は、このプロパティを __$true__ に設定します。</span><span class="sxs-lookup"><span data-stu-id="afe0b-130">Set this property to __$true__ if the user must change the password.</span></span> <span data-ttu-id="afe0b-131">既定値は __$true__ です。</span><span class="sxs-lookup"><span data-stu-id="afe0b-131">The default value is __$true__.</span></span>|
| <span data-ttu-id="afe0b-132">PasswordNeverExpires</span><span class="sxs-lookup"><span data-stu-id="afe0b-132">PasswordNeverExpires</span></span>| <span data-ttu-id="afe0b-133">パスワードの有効期限が切れるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="afe0b-133">Indicates if the password will expire.</span></span> <span data-ttu-id="afe0b-134">このアカウントのパスワードの有効期限が切れないようにするにはこのプロパティを __$true__ に設定し、パスワードの有効期限が切れるようにする場合は __$false__ を設定します。</span><span class="sxs-lookup"><span data-stu-id="afe0b-134">To ensure that the password for this account will never expire, set this property to __$true__, and set it to __$false__ if the password will expire.</span></span> <span data-ttu-id="afe0b-135">既定値は __$false__ です。</span><span class="sxs-lookup"><span data-stu-id="afe0b-135">The default value is __$false__.</span></span>|
| <span data-ttu-id="afe0b-136">DependsOn</span><span class="sxs-lookup"><span data-stu-id="afe0b-136">DependsOn</span></span> | <span data-ttu-id="afe0b-137">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="afe0b-137">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="afe0b-138">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="afe0b-138">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="example"></a><span data-ttu-id="afe0b-139">例</span><span class="sxs-lookup"><span data-stu-id="afe0b-139">Example</span></span>

```powershell
User UserExample
{
    Ensure = "Present"  # To ensure the user account does not exist, set Ensure to "Absent"
    UserName = "SomeName"
    Password = $passwordCred # This needs to be a credential object
    DependsOn = "[Group]GroupExample" # Configures GroupExample first
}
```