---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC ServiceSet リソース"
ms.openlocfilehash: 2488dda5212ccb717f7fd5d59ad62ec135ad13d5
ms.sourcegitcommit: 99227f62dcf827354770eb2c3e95c5cf6a3118b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="dsc-serviceset-resource"></a><span data-ttu-id="f73df-103">DSC ServiceSet リソース</span><span class="sxs-lookup"><span data-stu-id="f73df-103">DSC ServiceSet Resource</span></span>

> <span data-ttu-id="f73df-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="f73df-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>


<span data-ttu-id="f73df-105">PowerShell Desired State Configuration (DSC) の **ServiceSet** リソースは、ターゲット ノード上でサービスを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="f73df-105">The **ServiceSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span> <span data-ttu-id="f73df-106">このリソースは[複合リソース](authoringResourceComposite.md)であり、`Name` プロパティに指定されているサービスごとに [Service リソース](serviceResource.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f73df-106">This resource is a [composite resource](authoringResourceComposite.md) that calls the [Service resource](serviceResource.md) for each service specified in the `Name` property.</span></span>

<span data-ttu-id="f73df-107">サービスの数を同じ状態に構成するときにこのリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="f73df-107">Use this resource when you want to configure a number of services to the same state.</span></span>

## <a name="syntax"></a><span data-ttu-id="f73df-108">構文</span><span class="sxs-lookup"><span data-stu-id="f73df-108">Syntax</span></span>

```
Service [string] #ResourceName
{
    Name = [string[]]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Ensure = [string] { Absent | Present }  ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    
}
```

## <a name="properties"></a><span data-ttu-id="f73df-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f73df-109">Properties</span></span>

|  <span data-ttu-id="f73df-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f73df-110">Property</span></span>  |  <span data-ttu-id="f73df-111">説明</span><span class="sxs-lookup"><span data-stu-id="f73df-111">Description</span></span>   | 
|---|---| 
| <span data-ttu-id="f73df-112">名前</span><span class="sxs-lookup"><span data-stu-id="f73df-112">Name</span></span>| <span data-ttu-id="f73df-113">サービス名を示します。</span><span class="sxs-lookup"><span data-stu-id="f73df-113">Indicates the service names.</span></span> <span data-ttu-id="f73df-114">これは表示名とは異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="f73df-114">Note that sometimes this is different from the display names.</span></span> <span data-ttu-id="f73df-115">[Get-Service](https://technet.microsoft.com/library/hh849804.aspx) コマンドレットを使用すると、サービスとその現在の状態の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="f73df-115">You can get a list of the services and their current state with the [Get-Service](https://technet.microsoft.com/library/hh849804.aspx) cmdlet.</span></span>|
| <span data-ttu-id="f73df-116">StartupType</span><span class="sxs-lookup"><span data-stu-id="f73df-116">StartupType</span></span>| <span data-ttu-id="f73df-117">サービスのスタートアップの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="f73df-117">Indicates the startup type for the service.</span></span> <span data-ttu-id="f73df-118">このプロパティに許容される値は、**Automatic**、**Disabled**、および **Manual** です。</span><span class="sxs-lookup"><span data-stu-id="f73df-118">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**</span></span>|  
| <span data-ttu-id="f73df-119">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="f73df-119">BuiltInAccount</span></span>| <span data-ttu-id="f73df-120">サービスに使用するサインイン アカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="f73df-120">Indicates the sign-in account to use for the services.</span></span> <span data-ttu-id="f73df-121">このプロパティに許容される値は、**LocalService**、**LocalSystem**、および **NetworkService** です。</span><span class="sxs-lookup"><span data-stu-id="f73df-121">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span>| 
| <span data-ttu-id="f73df-122">State</span><span class="sxs-lookup"><span data-stu-id="f73df-122">State</span></span>| <span data-ttu-id="f73df-123">サービスの状態 (**停止**または**実行中**) を示します。</span><span class="sxs-lookup"><span data-stu-id="f73df-123">Indicates the state you want to ensure for the services: **Stopped** or **Running**.</span></span>| 
| <span data-ttu-id="f73df-124">Ensure</span><span class="sxs-lookup"><span data-stu-id="f73df-124">Ensure</span></span>| <span data-ttu-id="f73df-125">サービスがシステムに存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f73df-125">Indicates whether the services exist on the system.</span></span> <span data-ttu-id="f73df-126">サービスが存在しないようにするには、このプロパティを **[Absent]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="f73df-126">Set this property to **Absent** to ensure that the services do not exist.</span></span> <span data-ttu-id="f73df-127">ターゲットが存在するようにするには、**[Present]** (既定値) に設定します。</span><span class="sxs-lookup"><span data-stu-id="f73df-127">Setting it to **Present** (the default value) ensures that target services exist.</span></span>|
| <span data-ttu-id="f73df-128">Credential</span><span class="sxs-lookup"><span data-stu-id="f73df-128">Credential</span></span>| <span data-ttu-id="f73df-129">サービス リソースを実行するアカウントの資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="f73df-129">Indicates credentials for the account that the service resource will run under.</span></span> <span data-ttu-id="f73df-130">このプロパティおよび **BuiltinAccount** プロパティを同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f73df-130">This property and the **BuiltinAccount** property cannot be used together.</span></span>| 
| <span data-ttu-id="f73df-131">DependsOn</span><span class="sxs-lookup"><span data-stu-id="f73df-131">DependsOn</span></span>| <span data-ttu-id="f73df-132">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f73df-132">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="f73df-133">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が *ResourceName* で、そのタイプが *ResourceType* である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="f73df-133">For example, if the ID of the resource configuration script block that you want to run first is *ResourceName* and its type is *ResourceType*, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>| 



## <a name="example"></a><span data-ttu-id="f73df-134">例</span><span class="sxs-lookup"><span data-stu-id="f73df-134">Example</span></span>

<span data-ttu-id="f73df-135">次の構成で "Windows オーディオ" サービスと "リモート デスクトップ サービス" サービスが開始します。</span><span class="sxs-lookup"><span data-stu-id="f73df-135">The following configuration starts the "Windows Audio" and "Remote Desktop Services" services.</span></span>

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

