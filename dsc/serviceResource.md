---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Service リソース
ms.openlocfilehash: 3e2db8999ab1db2964f88e1ee14c6ad6e641c5e3
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="dsc-service-resource"></a><span data-ttu-id="3f56f-103">DSC Service リソース</span><span class="sxs-lookup"><span data-stu-id="3f56f-103">DSC Service Resource</span></span>

> <span data-ttu-id="3f56f-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="3f56f-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>


<span data-ttu-id="3f56f-105">PowerShell Desired State Configuration (DSC) の **Service** リソースは、ターゲット ノード上でサービスを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="3f56f-105">The **Service** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="3f56f-106">構文</span><span class="sxs-lookup"><span data-stu-id="3f56f-106">Syntax</span></span>

```
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Description = [string] ]
    [ DisplayName = [string] ]
    [ Ensure = [string] { Absent | Present } ]
    [ Path = [string] ]
}
```

## <a name="properties"></a><span data-ttu-id="3f56f-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3f56f-107">Properties</span></span>

|  <span data-ttu-id="3f56f-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3f56f-108">Property</span></span>  |  <span data-ttu-id="3f56f-109">説明</span><span class="sxs-lookup"><span data-stu-id="3f56f-109">Description</span></span>   |
|---|---|
| <span data-ttu-id="3f56f-110">名前</span><span class="sxs-lookup"><span data-stu-id="3f56f-110">Name</span></span>| <span data-ttu-id="3f56f-111">サービス名を示します。</span><span class="sxs-lookup"><span data-stu-id="3f56f-111">Indicates the service name.</span></span> <span data-ttu-id="3f56f-112">これは、表示名とは異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="3f56f-112">Note that sometimes this is different from the display name.</span></span> <span data-ttu-id="3f56f-113">Get-Service コマンドレットを使用すると、サービスとその現在の状態の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="3f56f-113">You can get a list of the services and their current state with the Get-Service cmdlet.</span></span>|
| <span data-ttu-id="3f56f-114">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="3f56f-114">BuiltInAccount</span></span>| <span data-ttu-id="3f56f-115">サービスに使用するサインイン アカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="3f56f-115">Indicates the sign-in account to use for the service.</span></span> <span data-ttu-id="3f56f-116">このプロパティに許容される値は、**LocalService**、**LocalSystem**、および **NetworkService** です。</span><span class="sxs-lookup"><span data-stu-id="3f56f-116">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span>|
| <span data-ttu-id="3f56f-117">Credential</span><span class="sxs-lookup"><span data-stu-id="3f56f-117">Credential</span></span>| <span data-ttu-id="3f56f-118">サービスを実行するアカウントの資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="3f56f-118">Indicates credentials for the account that the service will run under.</span></span> <span data-ttu-id="3f56f-119">このプロパティおよび __BuiltinAccount__ プロパティを同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3f56f-119">This property and the __BuiltinAccount__ property cannot be used together.</span></span>|
| <span data-ttu-id="3f56f-120">DependsOn</span><span class="sxs-lookup"><span data-stu-id="3f56f-120">DependsOn</span></span>| <span data-ttu-id="3f56f-121">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="3f56f-121">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="3f56f-122">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="3f56f-122">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="3f56f-123">StartupType</span><span class="sxs-lookup"><span data-stu-id="3f56f-123">StartupType</span></span>| <span data-ttu-id="3f56f-124">サービスのスタートアップの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="3f56f-124">Indicates the startup type for the service.</span></span> <span data-ttu-id="3f56f-125">このプロパティに許容される値は、**Automatic**、**Disabled**、および **Manual** です。</span><span class="sxs-lookup"><span data-stu-id="3f56f-125">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**</span></span>|
| <span data-ttu-id="3f56f-126">State</span><span class="sxs-lookup"><span data-stu-id="3f56f-126">State</span></span>| <span data-ttu-id="3f56f-127">サービスに対して保証する状態を示します。</span><span class="sxs-lookup"><span data-stu-id="3f56f-127">Indicates the state you want to ensure for the service.</span></span>|
| <span data-ttu-id="3f56f-128">説明</span><span class="sxs-lookup"><span data-stu-id="3f56f-128">Description</span></span> | <span data-ttu-id="3f56f-129">ターゲット サービスの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="3f56f-129">Indicates the description of the target service.</span></span>|
| <span data-ttu-id="3f56f-130">表示名</span><span class="sxs-lookup"><span data-stu-id="3f56f-130">DisplayName</span></span> | <span data-ttu-id="3f56f-131">ターゲット サービスの表示名を示します。</span><span class="sxs-lookup"><span data-stu-id="3f56f-131">Indicates the display name of the target service.</span></span>|
| <span data-ttu-id="3f56f-132">Ensure</span><span class="sxs-lookup"><span data-stu-id="3f56f-132">Ensure</span></span> | <span data-ttu-id="3f56f-133">ターゲット サービスがシステムに存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3f56f-133">Indicates whether the target service exists on the system.</span></span> <span data-ttu-id="3f56f-134">ターゲット サービスが存在しないようにするには、このプロパティを **[Absent]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="3f56f-134">Set this property to **Absent** to ensure that the target service does not exist.</span></span> <span data-ttu-id="3f56f-135">ターゲットが存在するようにするには、**[Present]** (既定値) に設定します。</span><span class="sxs-lookup"><span data-stu-id="3f56f-135">Setting it to **Present** (the default value) ensures that target service exists.</span></span>|
| <span data-ttu-id="3f56f-136">パス</span><span class="sxs-lookup"><span data-stu-id="3f56f-136">Path</span></span> | <span data-ttu-id="3f56f-137">新しいサービスのバイナリ ファイルのパスを示します。</span><span class="sxs-lookup"><span data-stu-id="3f56f-137">Indicates the path to the binary file for a new service.</span></span>|

## <a name="example"></a><span data-ttu-id="3f56f-138">例</span><span class="sxs-lookup"><span data-stu-id="3f56f-138">Example</span></span>

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