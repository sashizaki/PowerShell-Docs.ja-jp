---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC ServiceSet リソース
ms.openlocfilehash: 97c25f46940d69ed6c696e2692e29131e9a997b0
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953029"
---
# <a name="dsc-serviceset-resource"></a><span data-ttu-id="df335-103">DSC ServiceSet リソース</span><span class="sxs-lookup"><span data-stu-id="df335-103">DSC ServiceSet Resource</span></span>

> <span data-ttu-id="df335-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="df335-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="df335-105">PowerShell Desired State Configuration (DSC) の **ServiceSet** リソースは、ターゲット ノード上でサービスを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="df335-105">The **ServiceSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span> <span data-ttu-id="df335-106">このリソースは[複合リソース](../../../resources/authoringResourceComposite.md)であり、**Name** プロパティに指定されているサービスごとに [Service リソース](serviceResource.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="df335-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [Service resource](serviceResource.md) for each service specified in the **Name** property.</span></span>

<span data-ttu-id="df335-107">サービスの数を同じ状態に構成するときにこのリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="df335-107">Use this resource when you want to configure a number of services to the same state.</span></span>

## <a name="syntax"></a><span data-ttu-id="df335-108">構文</span><span class="sxs-lookup"><span data-stu-id="df335-108">Syntax</span></span>

```Syntax
ServiceSet [string] #ResourceName
{
    Name = [string[]]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="df335-109">Properties</span><span class="sxs-lookup"><span data-stu-id="df335-109">Properties</span></span>

|<span data-ttu-id="df335-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="df335-110">Property</span></span> |<span data-ttu-id="df335-111">説明</span><span class="sxs-lookup"><span data-stu-id="df335-111">Description</span></span> |
|---|---|
|<span data-ttu-id="df335-112">名前</span><span class="sxs-lookup"><span data-stu-id="df335-112">Name</span></span> |<span data-ttu-id="df335-113">サービス名を示します。</span><span class="sxs-lookup"><span data-stu-id="df335-113">Indicates the service names.</span></span> <span data-ttu-id="df335-114">これは表示名とは異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="df335-114">Note that sometimes this is different from the display names.</span></span> <span data-ttu-id="df335-115">`Get-Service` コマンドレットを使用すると、サービスとその現在の状態の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="df335-115">You can get a list of the services and their current state with the `Get-Service` cmdlet.</span></span> |
|<span data-ttu-id="df335-116">StartupType</span><span class="sxs-lookup"><span data-stu-id="df335-116">StartupType</span></span> |<span data-ttu-id="df335-117">サービスのスタートアップの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="df335-117">Indicates the startup type for the services.</span></span> <span data-ttu-id="df335-118">このプロパティで有効な値は、**Automatic**、**Disabled**、**Manual** です。</span><span class="sxs-lookup"><span data-stu-id="df335-118">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**.</span></span> |
|<span data-ttu-id="df335-119">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="df335-119">BuiltInAccount</span></span> |<span data-ttu-id="df335-120">サービスに使用するサインイン アカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="df335-120">Indicates the sign-in account to use for the services.</span></span> <span data-ttu-id="df335-121">このプロパティで有効な値は、**LocalService**、**LocalSystem**、**NetworkService** です。</span><span class="sxs-lookup"><span data-stu-id="df335-121">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span> |
|<span data-ttu-id="df335-122">State</span><span class="sxs-lookup"><span data-stu-id="df335-122">State</span></span> |<span data-ttu-id="df335-123">サービスに対して保証する状態を次のように示します。**Stopped** または **Running**。</span><span class="sxs-lookup"><span data-stu-id="df335-123">Indicates the state you want to ensure for the services: **Stopped** or **Running**.</span></span> |
|<span data-ttu-id="df335-124">資格情報</span><span class="sxs-lookup"><span data-stu-id="df335-124">Credential</span></span> |<span data-ttu-id="df335-125">サービス リソースを実行するアカウントの資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="df335-125">Indicates credentials for the account that the service resource will run under.</span></span> <span data-ttu-id="df335-126">このプロパティおよび **BuiltinAccount** プロパティを同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="df335-126">This property and the **BuiltinAccount** property cannot be used together.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="df335-127">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="df335-127">Common properties</span></span>

|<span data-ttu-id="df335-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="df335-128">Property</span></span> |<span data-ttu-id="df335-129">説明</span><span class="sxs-lookup"><span data-stu-id="df335-129">Description</span></span> |
|---|---|
|<span data-ttu-id="df335-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="df335-130">DependsOn</span></span> |<span data-ttu-id="df335-131">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="df335-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="df335-132">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="df335-132">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="df335-133">Ensure</span><span class="sxs-lookup"><span data-stu-id="df335-133">Ensure</span></span> |<span data-ttu-id="df335-134">サービスがシステムに存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="df335-134">Indicates whether the services exist on the system.</span></span> <span data-ttu-id="df335-135">サービスが存在しないようにするには、このプロパティを **[Absent]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="df335-135">Set this property to **Absent** to ensure that the services do not exist.</span></span> <span data-ttu-id="df335-136">対象サービスの存在を保証するには、これを **Present** に設定します</span><span class="sxs-lookup"><span data-stu-id="df335-136">Setting it to **Present** ensures that target services exist.</span></span> <span data-ttu-id="df335-137">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="df335-137">The default value is **Present**.</span></span> |
|<span data-ttu-id="df335-138">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="df335-138">PsDscRunAsCredential</span></span> |<span data-ttu-id="df335-139">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="df335-139">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="df335-140">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="df335-140">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="df335-141">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df335-141">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="df335-142">例</span><span class="sxs-lookup"><span data-stu-id="df335-142">Example</span></span>

<span data-ttu-id="df335-143">次の構成で "Windows オーディオ" サービスと "リモート デスクトップ サービス" サービスが開始します。</span><span class="sxs-lookup"><span data-stu-id="df335-143">The following configuration starts the "Windows Audio" and "Remote Desktop Services" services.</span></span>

```powershell
configuration ServiceSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {
        ServiceSet ServiceSetExample
        {
            Name        = @("TermService", "Audiosrv")
            StartupType = "Manual"
            State       = "Running"
        }
    }
}
```