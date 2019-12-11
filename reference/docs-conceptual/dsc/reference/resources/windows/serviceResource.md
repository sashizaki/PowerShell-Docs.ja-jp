---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Service リソース
ms.openlocfilehash: 0bef6aa6d3526c9d8d92187c1e738d5c46b5665a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953049"
---
# <a name="dsc-service-resource"></a><span data-ttu-id="ac133-103">DSC Service リソース</span><span class="sxs-lookup"><span data-stu-id="ac133-103">DSC Service Resource</span></span>

> <span data-ttu-id="ac133-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="ac133-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="ac133-105">PowerShell Desired State Configuration (DSC) の **Service** リソースは、ターゲット ノード上でサービスを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="ac133-105">The **Service** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="ac133-106">構文</span><span class="sxs-lookup"><span data-stu-id="ac133-106">Syntax</span></span>

```Syntax
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Description = [string] ]
    [ DisplayName = [string] ]
    [ Path = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="ac133-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ac133-107">Properties</span></span>

|<span data-ttu-id="ac133-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ac133-108">Property</span></span> |<span data-ttu-id="ac133-109">説明</span><span class="sxs-lookup"><span data-stu-id="ac133-109">Description</span></span> |
|---|---|
|<span data-ttu-id="ac133-110">名前</span><span class="sxs-lookup"><span data-stu-id="ac133-110">Name</span></span> |<span data-ttu-id="ac133-111">サービス名を示します。</span><span class="sxs-lookup"><span data-stu-id="ac133-111">Indicates the service name.</span></span> <span data-ttu-id="ac133-112">これは、表示名とは異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="ac133-112">Note that sometimes this is different from the display name.</span></span> <span data-ttu-id="ac133-113">`Get-Service` コマンドレットを使用すると、サービスとその現在の状態の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ac133-113">You can get a list of the services and their current state with the `Get-Service` cmdlet.</span></span> |
|<span data-ttu-id="ac133-114">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="ac133-114">BuiltInAccount</span></span> |<span data-ttu-id="ac133-115">サービスに使用するサインイン アカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="ac133-115">Indicates the sign-in account to use for the service.</span></span> <span data-ttu-id="ac133-116">このプロパティで有効な値は、**LocalService**、**LocalSystem**、**NetworkService** です。</span><span class="sxs-lookup"><span data-stu-id="ac133-116">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span> |
|<span data-ttu-id="ac133-117">Credential</span><span class="sxs-lookup"><span data-stu-id="ac133-117">Credential</span></span> |<span data-ttu-id="ac133-118">サービスを実行するアカウントの資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="ac133-118">Indicates credentials for the account that the service will run under.</span></span> <span data-ttu-id="ac133-119">このプロパティおよび **BuiltinAccount** プロパティを同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ac133-119">This property and the **BuiltinAccount** property cannot be used together.</span></span> |
|<span data-ttu-id="ac133-120">StartupType</span><span class="sxs-lookup"><span data-stu-id="ac133-120">StartupType</span></span> |<span data-ttu-id="ac133-121">サービスのスタートアップの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="ac133-121">Indicates the startup type for the service.</span></span> <span data-ttu-id="ac133-122">このプロパティで有効な値は、**Automatic**、**Disabled**、**Manual** です。</span><span class="sxs-lookup"><span data-stu-id="ac133-122">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**.</span></span> |
|<span data-ttu-id="ac133-123">State</span><span class="sxs-lookup"><span data-stu-id="ac133-123">State</span></span> |<span data-ttu-id="ac133-124">サービスに対して保証する状態を示します。</span><span class="sxs-lookup"><span data-stu-id="ac133-124">Indicates the state you want to ensure for the service.</span></span> <span data-ttu-id="ac133-125">値は、次のとおりです。**Running** または **Stopped**。</span><span class="sxs-lookup"><span data-stu-id="ac133-125">The values are: **Running** or **Stopped**.</span></span> |
|<span data-ttu-id="ac133-126">説明</span><span class="sxs-lookup"><span data-stu-id="ac133-126">Description</span></span> |<span data-ttu-id="ac133-127">ターゲット サービスの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="ac133-127">Indicates the description of the target service.</span></span> |
|<span data-ttu-id="ac133-128">表示名</span><span class="sxs-lookup"><span data-stu-id="ac133-128">DisplayName</span></span> |<span data-ttu-id="ac133-129">ターゲット サービスの表示名を示します。</span><span class="sxs-lookup"><span data-stu-id="ac133-129">Indicates the display name of the target service.</span></span> |
|<span data-ttu-id="ac133-130">パス</span><span class="sxs-lookup"><span data-stu-id="ac133-130">Path</span></span> |<span data-ttu-id="ac133-131">新しいサービスのバイナリ ファイルのパスを示します。</span><span class="sxs-lookup"><span data-stu-id="ac133-131">Indicates the path to the binary file for a new service.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="ac133-132">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="ac133-132">Common properties</span></span>

|<span data-ttu-id="ac133-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ac133-133">Property</span></span> |<span data-ttu-id="ac133-134">説明</span><span class="sxs-lookup"><span data-stu-id="ac133-134">Description</span></span> |
|---|---|
|<span data-ttu-id="ac133-135">DependsOn</span><span class="sxs-lookup"><span data-stu-id="ac133-135">DependsOn</span></span> |<span data-ttu-id="ac133-136">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="ac133-136">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="ac133-137">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="ac133-137">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="ac133-138">Ensure</span><span class="sxs-lookup"><span data-stu-id="ac133-138">Ensure</span></span> |<span data-ttu-id="ac133-139">ターゲット サービスがシステムに存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ac133-139">Indicates whether the target service exists on the system.</span></span> <span data-ttu-id="ac133-140">ターゲット サービスが存在しないようにするには、このプロパティを **[Absent]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="ac133-140">Set this property to **Absent** to ensure that the target service does not exist.</span></span> <span data-ttu-id="ac133-141">対象サービスの存在を保証するには、これを **Present** に設定します</span><span class="sxs-lookup"><span data-stu-id="ac133-141">Setting it to **Present** ensures that target service exists.</span></span> <span data-ttu-id="ac133-142">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="ac133-142">The default value is **Present**.</span></span> |
|<span data-ttu-id="ac133-143">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="ac133-143">PsDscRunAsCredential</span></span> |<span data-ttu-id="ac133-144">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="ac133-144">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="ac133-145">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="ac133-145">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="ac133-146">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac133-146">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="ac133-147">例</span><span class="sxs-lookup"><span data-stu-id="ac133-147">Example</span></span>

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