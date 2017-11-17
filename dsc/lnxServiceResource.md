---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "Linux 用 DSC の nxService リソース"
ms.openlocfilehash: be9f1f090eacc38bcdb77e53020d559bab72c156
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="dsc-for-linux-nxservice-resource"></a><span data-ttu-id="7d520-103">Linux 用 DSC の nxService リソース</span><span class="sxs-lookup"><span data-stu-id="7d520-103">DSC for Linux nxService Resource</span></span>

<span data-ttu-id="7d520-104">PowerShell Desired State Configuration (DSC) の **nxService** リソースは、Linux ノード上でサービスを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="7d520-104">The **nxService** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d520-105">構文</span><span class="sxs-lookup"><span data-stu-id="7d520-105">Syntax</span></span>

```
nxService <string> #ResourceName
{
    Name = <string>
    [ Controller = <string> { init | upstart | systemd }  ]
    [ Enabled = <bool> ]
    [ State = <string> { Running | Stopped } ]
    [ DependsOn = <string[]> ]

}
```

## <a name="properties"></a><span data-ttu-id="7d520-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7d520-106">Properties</span></span>
|  <span data-ttu-id="7d520-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7d520-107">Property</span></span> |  <span data-ttu-id="7d520-108">説明</span><span class="sxs-lookup"><span data-stu-id="7d520-108">Description</span></span> | 
|---|---|
| <span data-ttu-id="7d520-109">名前</span><span class="sxs-lookup"><span data-stu-id="7d520-109">Name</span></span>| <span data-ttu-id="7d520-110">構成するサービス/デーモンの名前。</span><span class="sxs-lookup"><span data-stu-id="7d520-110">The name of the service/daemon to configure.</span></span>| 
| <span data-ttu-id="7d520-111">コントローラー</span><span class="sxs-lookup"><span data-stu-id="7d520-111">Controller</span></span>| <span data-ttu-id="7d520-112">サービスを構成するときに使用するサービス コントローラーの種類。</span><span class="sxs-lookup"><span data-stu-id="7d520-112">The type of service controller to use when configuring the service.</span></span>| 
| <span data-ttu-id="7d520-113">Enabled</span><span class="sxs-lookup"><span data-stu-id="7d520-113">Enabled</span></span>| <span data-ttu-id="7d520-114">ブート時にサービスを開始するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7d520-114">Indicates whether the service starts on boot.</span></span>| 
| <span data-ttu-id="7d520-115">State</span><span class="sxs-lookup"><span data-stu-id="7d520-115">State</span></span>| <span data-ttu-id="7d520-116">サービスが実行されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7d520-116">Indicates whether the service is running.</span></span> <span data-ttu-id="7d520-117">サービスが実行されないようにするには、このプロパティを "Stopped" に設定します。</span><span class="sxs-lookup"><span data-stu-id="7d520-117">Set this property to "Stopped" to ensure that the service is not running.</span></span> <span data-ttu-id="7d520-118">サービスが実行されないようにするには、このプロパティを "Running" に設定します。</span><span class="sxs-lookup"><span data-stu-id="7d520-118">Set it to "Running" to ensure that the service is not running.</span></span>| 
| <span data-ttu-id="7d520-119">DependsOn</span><span class="sxs-lookup"><span data-stu-id="7d520-119">DependsOn</span></span> | <span data-ttu-id="7d520-120">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="7d520-120">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="7d520-121">たとえば、最初に実行するリソース構成スクリプト ブロックの **ID** が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="7d520-121">For example, if the **ID** of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>| 


## <a name="additional-information"></a><span data-ttu-id="7d520-122">追加情報</span><span class="sxs-lookup"><span data-stu-id="7d520-122">Additional Information</span></span>

<span data-ttu-id="7d520-123">**nxService** リソースでは、サービス定義やサービスのスクリプトが存在しない場合、これらは作成されません。</span><span class="sxs-lookup"><span data-stu-id="7d520-123">The **nxService** resource will not create a service definition or script for the service if it does not exist.</span></span> <span data-ttu-id="7d520-124">PowerShell Desired State Configuration の **nxFile** リソースを使用して、サービス定義ファイルやスクリプトの存在または内容を管理できます。</span><span class="sxs-lookup"><span data-stu-id="7d520-124">You can use the PowerShell Desired State Configuration **nxFile** Resource resource to manage the existence or contents of the service definition file or script.</span></span>

## <a name="example"></a><span data-ttu-id="7d520-125">例</span><span class="sxs-lookup"><span data-stu-id="7d520-125">Example</span></span>

<span data-ttu-id="7d520-126">次の例では、**SystemD** サービス コントローラーを使用して登録された "httpd" サービス (Apache HTTP Server の場合) の構成を示します。</span><span class="sxs-lookup"><span data-stu-id="7d520-126">The following example shows configuration of the “httpd” service (for Apache HTTP Server), registered with the **SystemD** service controller.</span></span>

```
Import-DSCResource -Module nx 

Node $node {
#Apache Service
nxService ApacheService 
{
Name = "httpd"
State = "running"
Enabled = $true
Controller = "systemd"
}
}
```

