---
ms.date: 01/06/2021
ms.topic: reference
title: DSC Service リソース
description: DSC Service リソース
ms.openlocfilehash: bb151e11475c6e67f1fcb2d73336ff2e34b749b8
ms.sourcegitcommit: afefb3636362857036648c2fe80215bc4e81f5ac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2021
ms.locfileid: "97957038"
---
# <a name="dsc-service-resource"></a><span data-ttu-id="54781-103">DSC Service リソース</span><span class="sxs-lookup"><span data-stu-id="54781-103">DSC Service Resource</span></span>

> <span data-ttu-id="54781-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="54781-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="54781-105">PowerShell Desired State Configuration (DSC) の **Service** リソースは、ターゲット ノード上でサービスを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="54781-105">The **Service** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="54781-106">構文</span><span class="sxs-lookup"><span data-stu-id="54781-106">Syntax</span></span>

```Syntax
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Dependencies = [string[]] ]
    [ Description = [string] ]
    [ DisplayName = [string] ]
    [ Path = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="54781-107">Properties</span><span class="sxs-lookup"><span data-stu-id="54781-107">Properties</span></span>

|<span data-ttu-id="54781-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="54781-108">Property</span></span> |<span data-ttu-id="54781-109">説明</span><span class="sxs-lookup"><span data-stu-id="54781-109">Description</span></span> |
|---|---|
|<span data-ttu-id="54781-110">名前</span><span class="sxs-lookup"><span data-stu-id="54781-110">Name</span></span> |<span data-ttu-id="54781-111">サービス名を示します。</span><span class="sxs-lookup"><span data-stu-id="54781-111">Indicates the service name.</span></span> <span data-ttu-id="54781-112">これは、表示名とは異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="54781-112">Note that sometimes this is different from the display name.</span></span> <span data-ttu-id="54781-113">`Get-Service` コマンドレットを使用すると、サービスとその現在の状態の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="54781-113">You can get a list of the services and their current state with the `Get-Service` cmdlet.</span></span> |
|<span data-ttu-id="54781-114">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="54781-114">BuiltInAccount</span></span> |<span data-ttu-id="54781-115">サービスに使用するサインイン アカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="54781-115">Indicates the sign-in account to use for the service.</span></span> <span data-ttu-id="54781-116">このプロパティで有効な値は、**LocalService**、**LocalSystem**、**NetworkService** です。</span><span class="sxs-lookup"><span data-stu-id="54781-116">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span> |
|<span data-ttu-id="54781-117">資格情報</span><span class="sxs-lookup"><span data-stu-id="54781-117">Credential</span></span> |<span data-ttu-id="54781-118">サービスを実行するアカウントの資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="54781-118">Indicates credentials for the account that the service will run under.</span></span> <span data-ttu-id="54781-119">このプロパティおよび **BuiltinAccount** プロパティを同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="54781-119">This property and the **BuiltinAccount** property cannot be used together.</span></span> |
|<span data-ttu-id="54781-120">StartupType</span><span class="sxs-lookup"><span data-stu-id="54781-120">StartupType</span></span> |<span data-ttu-id="54781-121">サービスのスタートアップの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="54781-121">Indicates the startup type for the service.</span></span> <span data-ttu-id="54781-122">このプロパティで有効な値は、**Automatic**、**Disabled**、**Manual** です。</span><span class="sxs-lookup"><span data-stu-id="54781-122">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**.</span></span> |
|<span data-ttu-id="54781-123">State</span><span class="sxs-lookup"><span data-stu-id="54781-123">State</span></span> |<span data-ttu-id="54781-124">サービスに対して保証する状態を示します。</span><span class="sxs-lookup"><span data-stu-id="54781-124">Indicates the state you want to ensure for the service.</span></span> <span data-ttu-id="54781-125">値は次のとおりです。**Running** または **Stopped**。</span><span class="sxs-lookup"><span data-stu-id="54781-125">The values are: **Running** or **Stopped**.</span></span> |
|<span data-ttu-id="54781-126">依存関係</span><span class="sxs-lookup"><span data-stu-id="54781-126">Dependencies</span></span> | <span data-ttu-id="54781-127">サービスに含まれる依存関係の名前の配列。</span><span class="sxs-lookup"><span data-stu-id="54781-127">An array of the names of the dependencies the service should have.</span></span> |
|<span data-ttu-id="54781-128">説明</span><span class="sxs-lookup"><span data-stu-id="54781-128">Description</span></span> |<span data-ttu-id="54781-129">ターゲット サービスの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="54781-129">Indicates the description of the target service.</span></span> |
|<span data-ttu-id="54781-130">DisplayName</span><span class="sxs-lookup"><span data-stu-id="54781-130">DisplayName</span></span> |<span data-ttu-id="54781-131">ターゲット サービスの表示名を示します。</span><span class="sxs-lookup"><span data-stu-id="54781-131">Indicates the display name of the target service.</span></span> |
|<span data-ttu-id="54781-132">Path</span><span class="sxs-lookup"><span data-stu-id="54781-132">Path</span></span> |<span data-ttu-id="54781-133">新しいサービスのバイナリ ファイルのパスを示します。</span><span class="sxs-lookup"><span data-stu-id="54781-133">Indicates the path to the binary file for a new service.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="54781-134">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="54781-134">Common properties</span></span>

|<span data-ttu-id="54781-135">プロパティ</span><span class="sxs-lookup"><span data-stu-id="54781-135">Property</span></span> |<span data-ttu-id="54781-136">説明</span><span class="sxs-lookup"><span data-stu-id="54781-136">Description</span></span> |
|---|---|
|<span data-ttu-id="54781-137">DependsOn</span><span class="sxs-lookup"><span data-stu-id="54781-137">DependsOn</span></span> |<span data-ttu-id="54781-138">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="54781-138">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="54781-139">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="54781-139">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="54781-140">Ensure</span><span class="sxs-lookup"><span data-stu-id="54781-140">Ensure</span></span> |<span data-ttu-id="54781-141">ターゲット サービスがシステムに存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="54781-141">Indicates whether the target service exists on the system.</span></span> <span data-ttu-id="54781-142">ターゲット サービスが存在しないようにするには、このプロパティを **[Absent]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="54781-142">Set this property to **Absent** to ensure that the target service does not exist.</span></span> <span data-ttu-id="54781-143">対象サービスの存在を保証するには、これを **Present** に設定します</span><span class="sxs-lookup"><span data-stu-id="54781-143">Setting it to **Present** ensures that target service exists.</span></span> <span data-ttu-id="54781-144">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="54781-144">The default value is **Present**.</span></span> |
|<span data-ttu-id="54781-145">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="54781-145">PsDscRunAsCredential</span></span> |<span data-ttu-id="54781-146">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="54781-146">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="54781-147">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="54781-147">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="54781-148">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54781-148">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="54781-149">例</span><span class="sxs-lookup"><span data-stu-id="54781-149">Example</span></span>

```powershell
configuration ServiceTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        Service ServiceExample
        {
            Name        = "TermService"
            StartupType = "Manual"
            State       = "Running"
        }
    }
}
```
