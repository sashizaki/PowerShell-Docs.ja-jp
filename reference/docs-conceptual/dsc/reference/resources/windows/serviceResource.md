---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Service リソース
ms.openlocfilehash: f936f58ffd00f84d8c6d5d41d93378eaa8db5879
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463586"
---
# <a name="dsc-service-resource"></a><span data-ttu-id="bef4c-103">DSC Service リソース</span><span class="sxs-lookup"><span data-stu-id="bef4c-103">DSC Service Resource</span></span>

> <span data-ttu-id="bef4c-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="bef4c-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="bef4c-105">PowerShell Desired State Configuration (DSC) の **Service** リソースは、ターゲット ノード上でサービスを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="bef4c-105">The **Service** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="bef4c-106">構文</span><span class="sxs-lookup"><span data-stu-id="bef4c-106">Syntax</span></span>

```Syntax
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ StartupTimeout = [uint32]]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Ignore | Running | Stopped }  ]
    [ Dependencies = [string[]] ]
    [ Description = [string] ]
    [ DesktopInteract = [boolean]]
    [ DisplayName = [string] ]
    [ Path = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
    [ TerminateTimeout = [uint32] ]
}
```

## <a name="properties"></a><span data-ttu-id="bef4c-107">Properties</span><span class="sxs-lookup"><span data-stu-id="bef4c-107">Properties</span></span>

|<span data-ttu-id="bef4c-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bef4c-108">Property</span></span> |<span data-ttu-id="bef4c-109">説明</span><span class="sxs-lookup"><span data-stu-id="bef4c-109">Description</span></span> |
|---|---|
|<span data-ttu-id="bef4c-110">名前</span><span class="sxs-lookup"><span data-stu-id="bef4c-110">Name</span></span> |<span data-ttu-id="bef4c-111">サービス名を示します。</span><span class="sxs-lookup"><span data-stu-id="bef4c-111">Indicates the service name.</span></span> <span data-ttu-id="bef4c-112">これは、表示名とは異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="bef4c-112">Note that sometimes this is different from the display name.</span></span> <span data-ttu-id="bef4c-113">`Get-Service` コマンドレットを使用すると、サービスとその現在の状態の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="bef4c-113">You can get a list of the services and their current state with the `Get-Service` cmdlet.</span></span> |
|<span data-ttu-id="bef4c-114">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="bef4c-114">BuiltInAccount</span></span> |<span data-ttu-id="bef4c-115">サービスに使用するサインイン アカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="bef4c-115">Indicates the sign-in account to use for the service.</span></span> <span data-ttu-id="bef4c-116">このプロパティで有効な値は、**LocalService**、**LocalSystem**、**NetworkService** です。</span><span class="sxs-lookup"><span data-stu-id="bef4c-116">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span> |
|<span data-ttu-id="bef4c-117">資格情報</span><span class="sxs-lookup"><span data-stu-id="bef4c-117">Credential</span></span> |<span data-ttu-id="bef4c-118">サービスを実行するアカウントの資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="bef4c-118">Indicates credentials for the account that the service will run under.</span></span> <span data-ttu-id="bef4c-119">このプロパティおよび **BuiltinAccount** プロパティを同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bef4c-119">This property and the **BuiltinAccount** property cannot be used together.</span></span> |
|<span data-ttu-id="bef4c-120">StartupTimeout</span><span class="sxs-lookup"><span data-stu-id="bef4c-120">StartupTimeout</span></span> | <span data-ttu-id="bef4c-121">サービスが実行されるまで待機する時間 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="bef4c-121">The time to wait for the service to be running in milliseconds.</span></span>|
|<span data-ttu-id="bef4c-122">StartupType</span><span class="sxs-lookup"><span data-stu-id="bef4c-122">StartupType</span></span> |<span data-ttu-id="bef4c-123">サービスのスタートアップの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="bef4c-123">Indicates the startup type for the service.</span></span> <span data-ttu-id="bef4c-124">このプロパティで有効な値は、**Automatic**、**Disabled**、**Manual** です。</span><span class="sxs-lookup"><span data-stu-id="bef4c-124">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**.</span></span> |
|<span data-ttu-id="bef4c-125">State</span><span class="sxs-lookup"><span data-stu-id="bef4c-125">State</span></span> |<span data-ttu-id="bef4c-126">サービスに対して保証する状態を示します。</span><span class="sxs-lookup"><span data-stu-id="bef4c-126">Indicates the state you want to ensure for the service.</span></span> <span data-ttu-id="bef4c-127">値は次のとおりです。**Running** または **Stopped**。</span><span class="sxs-lookup"><span data-stu-id="bef4c-127">The values are: **Running** or **Stopped**.</span></span> |
|<span data-ttu-id="bef4c-128">TerminateTimeout</span><span class="sxs-lookup"><span data-stu-id="bef4c-128">TerminateTimeout</span></span> |<span data-ttu-id="bef4c-129">サービスが停止されるまで待機する時間 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="bef4c-129">The time to wait for the service to be stopped in milliseconds.</span></span>|
|<span data-ttu-id="bef4c-130">依存関係</span><span class="sxs-lookup"><span data-stu-id="bef4c-130">Dependencies</span></span> | <span data-ttu-id="bef4c-131">サービスに含まれる依存関係の名前の配列。</span><span class="sxs-lookup"><span data-stu-id="bef4c-131">An array of the names of the dependencies the service should have.</span></span> |
|<span data-ttu-id="bef4c-132">説明</span><span class="sxs-lookup"><span data-stu-id="bef4c-132">Description</span></span> |<span data-ttu-id="bef4c-133">ターゲット サービスの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="bef4c-133">Indicates the description of the target service.</span></span> |
|<span data-ttu-id="bef4c-134">DesktopInteract</span><span class="sxs-lookup"><span data-stu-id="bef4c-134">DesktopInteract</span></span> | <span data-ttu-id="bef4c-135">サービスがデスクトップ上のウィンドウと通信できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="bef4c-135">Indicates whether or not the service should be able to communicate with a window on the desktop.</span></span> <span data-ttu-id="bef4c-136">LocalSystem として実行されていないサービスの場合は、false にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bef4c-136">Must be false for services not running as LocalSystem.</span></span>|
|<span data-ttu-id="bef4c-137">DisplayName</span><span class="sxs-lookup"><span data-stu-id="bef4c-137">DisplayName</span></span> |<span data-ttu-id="bef4c-138">ターゲット サービスの表示名を示します。</span><span class="sxs-lookup"><span data-stu-id="bef4c-138">Indicates the display name of the target service.</span></span> |
|<span data-ttu-id="bef4c-139">Path</span><span class="sxs-lookup"><span data-stu-id="bef4c-139">Path</span></span> |<span data-ttu-id="bef4c-140">新しいサービスのバイナリ ファイルのパスを示します。</span><span class="sxs-lookup"><span data-stu-id="bef4c-140">Indicates the path to the binary file for a new service.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="bef4c-141">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="bef4c-141">Common properties</span></span>

|<span data-ttu-id="bef4c-142">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bef4c-142">Property</span></span> |<span data-ttu-id="bef4c-143">説明</span><span class="sxs-lookup"><span data-stu-id="bef4c-143">Description</span></span> |
|---|---|
|<span data-ttu-id="bef4c-144">DependsOn</span><span class="sxs-lookup"><span data-stu-id="bef4c-144">DependsOn</span></span> |<span data-ttu-id="bef4c-145">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="bef4c-145">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="bef4c-146">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="bef4c-146">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="bef4c-147">Ensure</span><span class="sxs-lookup"><span data-stu-id="bef4c-147">Ensure</span></span> |<span data-ttu-id="bef4c-148">ターゲット サービスがシステムに存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="bef4c-148">Indicates whether the target service exists on the system.</span></span> <span data-ttu-id="bef4c-149">ターゲット サービスが存在しないようにするには、このプロパティを **[Absent]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="bef4c-149">Set this property to **Absent** to ensure that the target service does not exist.</span></span> <span data-ttu-id="bef4c-150">対象サービスの存在を保証するには、これを **Present** に設定します</span><span class="sxs-lookup"><span data-stu-id="bef4c-150">Setting it to **Present** ensures that target service exists.</span></span> <span data-ttu-id="bef4c-151">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="bef4c-151">The default value is **Present**.</span></span> |
|<span data-ttu-id="bef4c-152">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="bef4c-152">PsDscRunAsCredential</span></span> |<span data-ttu-id="bef4c-153">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="bef4c-153">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="bef4c-154">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="bef4c-154">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="bef4c-155">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bef4c-155">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="bef4c-156">例</span><span class="sxs-lookup"><span data-stu-id="bef4c-156">Example</span></span>

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
