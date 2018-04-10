---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC ServiceSet リソース
ms.openlocfilehash: a7516120f0c4bc1c91031adc8aabf6a59b845246
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="dsc-serviceset-resource"></a><span data-ttu-id="0edc2-103">DSC ServiceSet リソース</span><span class="sxs-lookup"><span data-stu-id="0edc2-103">DSC ServiceSet Resource</span></span>

> <span data-ttu-id="0edc2-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="0edc2-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>


<span data-ttu-id="0edc2-105">PowerShell Desired State Configuration (DSC) の **ServiceSet** リソースは、ターゲット ノード上でサービスを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="0edc2-105">The **ServiceSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span> <span data-ttu-id="0edc2-106">このリソースは[複合リソース](authoringResourceComposite.md)であり、`Name` プロパティに指定されているサービスごとに [Service リソース](serviceResource.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0edc2-106">This resource is a [composite resource](authoringResourceComposite.md) that calls the [Service resource](serviceResource.md) for each service specified in the `Name` property.</span></span>

<span data-ttu-id="0edc2-107">サービスの数を同じ状態に構成するときにこのリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="0edc2-107">Use this resource when you want to configure a number of services to the same state.</span></span>

## <a name="syntax"></a><span data-ttu-id="0edc2-108">構文</span><span class="sxs-lookup"><span data-stu-id="0edc2-108">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="0edc2-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0edc2-109">Properties</span></span>

|  <span data-ttu-id="0edc2-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0edc2-110">Property</span></span>  |  <span data-ttu-id="0edc2-111">説明</span><span class="sxs-lookup"><span data-stu-id="0edc2-111">Description</span></span>   |
|---|---|
| <span data-ttu-id="0edc2-112">名前</span><span class="sxs-lookup"><span data-stu-id="0edc2-112">Name</span></span>| <span data-ttu-id="0edc2-113">サービス名を示します。</span><span class="sxs-lookup"><span data-stu-id="0edc2-113">Indicates the service names.</span></span> <span data-ttu-id="0edc2-114">これは表示名とは異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="0edc2-114">Note that sometimes this is different from the display names.</span></span> <span data-ttu-id="0edc2-115">[Get-Service](https://technet.microsoft.com/library/hh849804.aspx) コマンドレットを使用すると、サービスとその現在の状態の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="0edc2-115">You can get a list of the services and their current state with the [Get-Service](https://technet.microsoft.com/library/hh849804.aspx) cmdlet.</span></span>|
| <span data-ttu-id="0edc2-116">StartupType</span><span class="sxs-lookup"><span data-stu-id="0edc2-116">StartupType</span></span>| <span data-ttu-id="0edc2-117">サービスのスタートアップの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="0edc2-117">Indicates the startup type for the service.</span></span> <span data-ttu-id="0edc2-118">このプロパティに許容される値は、**Automatic**、**Disabled**、および **Manual** です。</span><span class="sxs-lookup"><span data-stu-id="0edc2-118">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**</span></span>|
| <span data-ttu-id="0edc2-119">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="0edc2-119">BuiltInAccount</span></span>| <span data-ttu-id="0edc2-120">サービスに使用するサインイン アカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="0edc2-120">Indicates the sign-in account to use for the services.</span></span> <span data-ttu-id="0edc2-121">このプロパティに許容される値は、**LocalService**、**LocalSystem**、および **NetworkService** です。</span><span class="sxs-lookup"><span data-stu-id="0edc2-121">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span>|
| <span data-ttu-id="0edc2-122">State</span><span class="sxs-lookup"><span data-stu-id="0edc2-122">State</span></span>| <span data-ttu-id="0edc2-123">サービスの状態 (**停止**または**実行中**) を示します。</span><span class="sxs-lookup"><span data-stu-id="0edc2-123">Indicates the state you want to ensure for the services: **Stopped** or **Running**.</span></span>|
| <span data-ttu-id="0edc2-124">Ensure</span><span class="sxs-lookup"><span data-stu-id="0edc2-124">Ensure</span></span>| <span data-ttu-id="0edc2-125">サービスがシステムに存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0edc2-125">Indicates whether the services exist on the system.</span></span> <span data-ttu-id="0edc2-126">サービスが存在しないようにするには、このプロパティを **[Absent]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="0edc2-126">Set this property to **Absent** to ensure that the services do not exist.</span></span> <span data-ttu-id="0edc2-127">ターゲットが存在するようにするには、**[Present]** (既定値) に設定します。</span><span class="sxs-lookup"><span data-stu-id="0edc2-127">Setting it to **Present** (the default value) ensures that target services exist.</span></span>|
| <span data-ttu-id="0edc2-128">Credential</span><span class="sxs-lookup"><span data-stu-id="0edc2-128">Credential</span></span>| <span data-ttu-id="0edc2-129">サービス リソースを実行するアカウントの資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0edc2-129">Indicates credentials for the account that the service resource will run under.</span></span> <span data-ttu-id="0edc2-130">このプロパティおよび **BuiltinAccount** プロパティを同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0edc2-130">This property and the **BuiltinAccount** property cannot be used together.</span></span>|
| <span data-ttu-id="0edc2-131">DependsOn</span><span class="sxs-lookup"><span data-stu-id="0edc2-131">DependsOn</span></span>| <span data-ttu-id="0edc2-132">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="0edc2-132">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="0edc2-133">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が *ResourceName* で、そのタイプが *ResourceType* である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="0edc2-133">For example, if the ID of the resource configuration script block that you want to run first is *ResourceName* and its type is *ResourceType*, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|



## <a name="example"></a><span data-ttu-id="0edc2-134">例</span><span class="sxs-lookup"><span data-stu-id="0edc2-134">Example</span></span>

<span data-ttu-id="0edc2-135">次の構成で "Windows オーディオ" サービスと "リモート デスクトップ サービス" サービスが開始します。</span><span class="sxs-lookup"><span data-stu-id="0edc2-135">The following configuration starts the "Windows Audio" and "Remote Desktop Services" services.</span></span>

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