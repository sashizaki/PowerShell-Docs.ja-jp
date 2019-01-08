---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC User リソース
ms.openlocfilehash: 04543351df19160a2da05ccea96e5d392d8c55bf
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047888"
---
# <a name="dsc-user-resource"></a><span data-ttu-id="fb432-103">DSC User リソース</span><span class="sxs-lookup"><span data-stu-id="fb432-103">DSC User Resource</span></span>

<span data-ttu-id="fb432-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="fb432-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="fb432-105">PowerShell Desired State Configuration (DSC) の **User** リソースは、ターゲット ノード上でローカル ユーザー アカウントを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="fb432-105">The **User** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local user accounts on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="fb432-106">構文</span><span class="sxs-lookup"><span data-stu-id="fb432-106">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="fb432-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="fb432-107">Properties</span></span>

|  <span data-ttu-id="fb432-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="fb432-108">Property</span></span>  |  <span data-ttu-id="fb432-109">説明</span><span class="sxs-lookup"><span data-stu-id="fb432-109">Description</span></span>   |
|---|---|
| <span data-ttu-id="fb432-110">UserName</span><span class="sxs-lookup"><span data-stu-id="fb432-110">UserName</span></span>| <span data-ttu-id="fb432-111">特定の状態を保証するアカウント名を示します。</span><span class="sxs-lookup"><span data-stu-id="fb432-111">Indicates the account name for which you want to ensure a specific state.</span></span>|
| <span data-ttu-id="fb432-112">説明</span><span class="sxs-lookup"><span data-stu-id="fb432-112">Description</span></span>| <span data-ttu-id="fb432-113">ユーザー アカウントのために使用する説明を示します。</span><span class="sxs-lookup"><span data-stu-id="fb432-113">Indicates the description you want to use for the user account.</span></span>|
| <span data-ttu-id="fb432-114">無効</span><span class="sxs-lookup"><span data-stu-id="fb432-114">Disabled</span></span>| <span data-ttu-id="fb432-115">アカウントが有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fb432-115">Indicates if the account is enabled.</span></span> <span data-ttu-id="fb432-116">このアカウントを無効にするには、このプロパティを `$true` に設定し、有効にするには `$false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="fb432-116">Set this property to `$true` to ensure that this account is disabled, and set it to `$false` to ensure that it is enabled.</span></span>|
| <span data-ttu-id="fb432-117">Ensure</span><span class="sxs-lookup"><span data-stu-id="fb432-117">Ensure</span></span>| <span data-ttu-id="fb432-118">アカウントが存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fb432-118">Indicates if the account exists.</span></span> <span data-ttu-id="fb432-119">このアカウントが存在することを保証するには、このプロパティを "Present" に設定し、アカウントが存在しないことを保証するには、"Absent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="fb432-119">Set this property to "Present" to ensure that the account exists, and set it to "Absent" to ensure that the account does not exist.</span></span>|
| <span data-ttu-id="fb432-120">FullName</span><span class="sxs-lookup"><span data-stu-id="fb432-120">FullName</span></span>| <span data-ttu-id="fb432-121">ユーザー アカウントのために使用する完全名の文字列を表します。</span><span class="sxs-lookup"><span data-stu-id="fb432-121">Represents a string with the full name you want to use for the user account.</span></span>|
| <span data-ttu-id="fb432-122">Password</span><span class="sxs-lookup"><span data-stu-id="fb432-122">Password</span></span>| <span data-ttu-id="fb432-123">このアカウントに使用するパスワードを示します。</span><span class="sxs-lookup"><span data-stu-id="fb432-123">Indicates the password you want to use for this account.</span></span> |
| <span data-ttu-id="fb432-124">PasswordChangeNotAllowed</span><span class="sxs-lookup"><span data-stu-id="fb432-124">PasswordChangeNotAllowed</span></span>| <span data-ttu-id="fb432-125">ユーザーがパスワードを変更できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fb432-125">Indicates if the user can change the password.</span></span> <span data-ttu-id="fb432-126">ユーザーがパスワードを変更できないようにするには、このプロパティを `$true` に設定し、ユーザーがパスワードを変更できるようにするには、`$false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="fb432-126">Set this property to `$true` to ensure that the user cannot change the password, and set it to `$false` to allow the user to change the password.</span></span> <span data-ttu-id="fb432-127">既定値は `$false` です。</span><span class="sxs-lookup"><span data-stu-id="fb432-127">The default value is `$false`.</span></span>|
| <span data-ttu-id="fb432-128">PasswordChangeRequired</span><span class="sxs-lookup"><span data-stu-id="fb432-128">PasswordChangeRequired</span></span>| <span data-ttu-id="fb432-129">ユーザーが次回ログオンしたときにパスワードを変更する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fb432-129">Indicates if the user must change the password at the next sign in.</span></span> <span data-ttu-id="fb432-130">ユーザーがパスワードを変更する必要がある場合は、このプロパティを `$true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="fb432-130">Set this property to `$true` if the user must change the password.</span></span> <span data-ttu-id="fb432-131">既定値は `$true` です。</span><span class="sxs-lookup"><span data-stu-id="fb432-131">The default value is `$true`.</span></span>|
| <span data-ttu-id="fb432-132">PasswordNeverExpires</span><span class="sxs-lookup"><span data-stu-id="fb432-132">PasswordNeverExpires</span></span>| <span data-ttu-id="fb432-133">パスワードの有効期限が切れるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fb432-133">Indicates if the password will expire.</span></span> <span data-ttu-id="fb432-134">このアカウントのパスワードの有効期限が切れないようにするにはこのプロパティを `$true` に設定し、パスワードの有効期限が切れるようにする場合は `$false` を設定します。</span><span class="sxs-lookup"><span data-stu-id="fb432-134">To ensure that the password for this account will never expire, set this property to `$true`, and set it to `$false` if the password will expire.</span></span> <span data-ttu-id="fb432-135">既定値は `$false` です。</span><span class="sxs-lookup"><span data-stu-id="fb432-135">The default value is `$false`.</span></span>|
| <span data-ttu-id="fb432-136">DependsOn</span><span class="sxs-lookup"><span data-stu-id="fb432-136">DependsOn</span></span> | <span data-ttu-id="fb432-137">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="fb432-137">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="fb432-138">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="fb432-138">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="example"></a><span data-ttu-id="fb432-139">例</span><span class="sxs-lookup"><span data-stu-id="fb432-139">Example</span></span>

```powershell
User UserExample
{
    Ensure = "Present"  # To ensure the user account does not exist, set Ensure to "Absent"
    UserName = "SomeName"
    Password = $passwordCred # This needs to be a credential object
    DependsOn = "[Group]GroupExample" # Configures GroupExample first
}
```