---
ms.date: 07/16/2020
ms.topic: reference
title: DSC User リソース
description: DSC User リソース
ms.openlocfilehash: b14f8d434ef3e1eb220fe7b0b18a011014c9ae6c
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142602"
---
# <a name="dsc-user-resource"></a><span data-ttu-id="14637-103">DSC User リソース</span><span class="sxs-lookup"><span data-stu-id="14637-103">DSC User Resource</span></span>

> <span data-ttu-id="14637-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="14637-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="14637-105">PowerShell Desired State Configuration (DSC) の **User** リソースは、ターゲット ノード上でローカル ユーザー アカウントを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="14637-105">The **User** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local user accounts on the target node.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="14637-106">構文</span><span class="sxs-lookup"><span data-stu-id="14637-106">Syntax</span></span>

```Syntax
User [string] #ResourceName
{
    UserName = [string]
    [ Description = [string] ]
    [ Disabled = [bool] ]
    [ FullName = [string] ]
    [ Password = [PSCredential] ]
    [ PasswordChangeNotAllowed = [bool] ]
    [ PasswordChangeRequired = [bool] ]
    [ PasswordNeverExpires = [bool] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="14637-107">Properties</span><span class="sxs-lookup"><span data-stu-id="14637-107">Properties</span></span>

|<span data-ttu-id="14637-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="14637-108">Property</span></span> |<span data-ttu-id="14637-109">説明</span><span class="sxs-lookup"><span data-stu-id="14637-109">Description</span></span> |
|---|---|
|<span data-ttu-id="14637-110">UserName</span><span class="sxs-lookup"><span data-stu-id="14637-110">UserName</span></span> |<span data-ttu-id="14637-111">特定の状態を保証するアカウント名を示します。</span><span class="sxs-lookup"><span data-stu-id="14637-111">Indicates the account name for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="14637-112">説明</span><span class="sxs-lookup"><span data-stu-id="14637-112">Description</span></span> |<span data-ttu-id="14637-113">ユーザー アカウントのために使用する説明を示します。</span><span class="sxs-lookup"><span data-stu-id="14637-113">Indicates the description you want to use for the user account.</span></span> |
|<span data-ttu-id="14637-114">無効</span><span class="sxs-lookup"><span data-stu-id="14637-114">Disabled</span></span> |<span data-ttu-id="14637-115">アカウントが有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="14637-115">Indicates if the account is enabled.</span></span> <span data-ttu-id="14637-116">このアカウントを無効にするには、このプロパティを `$true` に設定し、有効にするには `$false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="14637-116">Set this property to `$true` to ensure that this account is disabled, and set it to `$false` to ensure that it is enabled.</span></span> |
|<span data-ttu-id="14637-117">FullName</span><span class="sxs-lookup"><span data-stu-id="14637-117">FullName</span></span> |<span data-ttu-id="14637-118">ユーザー アカウントのために使用する完全名の文字列を表します。</span><span class="sxs-lookup"><span data-stu-id="14637-118">Represents a string with the full name you want to use for the user account.</span></span> |
|<span data-ttu-id="14637-119">Password</span><span class="sxs-lookup"><span data-stu-id="14637-119">Password</span></span> |<span data-ttu-id="14637-120">このアカウントに使用するパスワードを示します。</span><span class="sxs-lookup"><span data-stu-id="14637-120">Indicates the password you want to use for this account.</span></span> |
|<span data-ttu-id="14637-121">PasswordChangeNotAllowed</span><span class="sxs-lookup"><span data-stu-id="14637-121">PasswordChangeNotAllowed</span></span> |<span data-ttu-id="14637-122">ユーザーがパスワードを変更できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="14637-122">Indicates if the user can change the password.</span></span> <span data-ttu-id="14637-123">ユーザーがパスワードを変更できないようにするには、このプロパティを `$true` に設定し、ユーザーがパスワードを変更できるようにするには、`$false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="14637-123">Set this property to `$true` to ensure that the user cannot change the password, and set it to `$false` to allow the user to change the password.</span></span> <span data-ttu-id="14637-124">既定値は `$false` です。</span><span class="sxs-lookup"><span data-stu-id="14637-124">The default value is `$false`.</span></span> |
|<span data-ttu-id="14637-125">PasswordChangeRequired</span><span class="sxs-lookup"><span data-stu-id="14637-125">PasswordChangeRequired</span></span> |<span data-ttu-id="14637-126">ユーザーが次回ログオンしたときにパスワードを変更する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="14637-126">Indicates if the user must change the password at the next sign in.</span></span> <span data-ttu-id="14637-127">ユーザーがパスワードを変更する必要がある場合は、このプロパティを `$true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="14637-127">Set this property to `$true` if the user must change the password.</span></span> <span data-ttu-id="14637-128">既定値は `$true` です。</span><span class="sxs-lookup"><span data-stu-id="14637-128">The default value is `$true`.</span></span> |
|<span data-ttu-id="14637-129">PasswordNeverExpires</span><span class="sxs-lookup"><span data-stu-id="14637-129">PasswordNeverExpires</span></span> |<span data-ttu-id="14637-130">パスワードの有効期限が切れるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="14637-130">Indicates if the password will expire.</span></span> <span data-ttu-id="14637-131">このアカウントのパスワードが確実に期限切れにならないようにするには、このプロパティを `$true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="14637-131">To ensure that the password for this account will never expire, set this property to `$true`.</span></span> <span data-ttu-id="14637-132">パスワードの有効期限が切れるようにするには、`$false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="14637-132">Set it to `$false` if the password will expire.</span></span> <span data-ttu-id="14637-133">既定値は `$false` です。</span><span class="sxs-lookup"><span data-stu-id="14637-133">The default value is `$false`.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="14637-134">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="14637-134">Common properties</span></span>

|<span data-ttu-id="14637-135">プロパティ</span><span class="sxs-lookup"><span data-stu-id="14637-135">Property</span></span> |<span data-ttu-id="14637-136">説明</span><span class="sxs-lookup"><span data-stu-id="14637-136">Description</span></span> |
|---|---|
|<span data-ttu-id="14637-137">DependsOn</span><span class="sxs-lookup"><span data-stu-id="14637-137">DependsOn</span></span> |<span data-ttu-id="14637-138">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="14637-138">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="14637-139">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="14637-139">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="14637-140">Ensure</span><span class="sxs-lookup"><span data-stu-id="14637-140">Ensure</span></span> |<span data-ttu-id="14637-141">アカウントが存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="14637-141">Indicates if the account exists.</span></span> <span data-ttu-id="14637-142">このアカウントの存在を保証するには、このプロパティを **Present** に設定し、アカウントが存在しないことを保証するには、 **Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="14637-142">Set this property to **Present** to ensure that the account exists, and set it to **Absent** to ensure that the account does not exist.</span></span> <span data-ttu-id="14637-143">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="14637-143">The default value is **Present** .</span></span> |
|<span data-ttu-id="14637-144">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="14637-144">PsDscRunAsCredential</span></span> |<span data-ttu-id="14637-145">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="14637-145">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="14637-146">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="14637-146">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="14637-147">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14637-147">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="14637-148">例</span><span class="sxs-lookup"><span data-stu-id="14637-148">Example</span></span>

```powershell
User UserExample
{
    Ensure = "Present"  # To ensure the user account does not exist, set Ensure to "Absent"
    UserName = "SomeName"
    Password = $passwordCred # This needs to be a credential object
    DependsOn = "[Group]GroupExample" # Configures GroupExample first
}
```
