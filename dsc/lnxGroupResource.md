---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "Linux 用 DSC の nxGroup リソース"
ms.openlocfilehash: bc01f6ae5ed61aff63958fe55f30d82f9b81b2b9
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="dsc-for-linux-nxgroup-resource"></a><span data-ttu-id="0c290-103">Linux 用 DSC の nxGroup リソース</span><span class="sxs-lookup"><span data-stu-id="0c290-103">DSC for Linux nxGroup Resource</span></span>

<span data-ttu-id="0c290-104">PowerShell Desired State Configuration (DSC) の **nxGroup** リソースは、Linux ノード上でローカル グループを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="0c290-104">The **nxGroup** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="0c290-105">構文</span><span class="sxs-lookup"><span data-stu-id="0c290-105">Syntax</span></span>

```powershell
nxGroup <string> #ResourceName
{
    GroupName = <string>
    [ Ensure = <string> { Absent | Present }  ]
    [ Members = <string[]> ]
    [ MebersToInclude = <string[]>]
    [ MembersToExclude = <string[]> ]
    [ DependsOn = <string[]> ]
}

```

## <a name="properties"></a><span data-ttu-id="0c290-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0c290-106">Properties</span></span>

|  <span data-ttu-id="0c290-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0c290-107">Property</span></span> |  <span data-ttu-id="0c290-108">説明</span><span class="sxs-lookup"><span data-stu-id="0c290-108">Description</span></span> | 
|---|---|
| <span data-ttu-id="0c290-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="0c290-109">GroupName</span></span>| <span data-ttu-id="0c290-110">特定の状態を保証するグループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0c290-110">Specifies the name of the group for which you want to ensure a specific state.</span></span>| 
| <span data-ttu-id="0c290-111">Ensure</span><span class="sxs-lookup"><span data-stu-id="0c290-111">Ensure</span></span>| <span data-ttu-id="0c290-112">グループが存在するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="0c290-112">Determines whether to check if the group exists.</span></span> <span data-ttu-id="0c290-113">グループが存在することを保証するには、このプロパティを "Present" に設定します。</span><span class="sxs-lookup"><span data-stu-id="0c290-113">Set this property to "Present" to ensure the group exists.</span></span> <span data-ttu-id="0c290-114">グループが存在しないことを保証するには、"Absent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="0c290-114">Set it to "Absent" to ensure the group does not exist.</span></span> <span data-ttu-id="0c290-115">既定値は "Present" です。</span><span class="sxs-lookup"><span data-stu-id="0c290-115">The default value is "Present".</span></span>| 
| <span data-ttu-id="0c290-116">[メンバー]</span><span class="sxs-lookup"><span data-stu-id="0c290-116">Members</span></span>| <span data-ttu-id="0c290-117">グループを形成するメンバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c290-117">Specifies the members that form the group.</span></span>| 
| <span data-ttu-id="0c290-118">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="0c290-118">MembersToInclude</span></span>| <span data-ttu-id="0c290-119">グループのメンバーであることを保証するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c290-119">Specifies the users who you want to ensure are members of the group.</span></span>| 
| <span data-ttu-id="0c290-120">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="0c290-120">MembersToExclude</span></span>| <span data-ttu-id="0c290-121">グループのメンバーでないことを保証するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c290-121">Specifies the users who you want to ensure are not members of the group.</span></span>| 
| <span data-ttu-id="0c290-122">PreferredGroupID</span><span class="sxs-lookup"><span data-stu-id="0c290-122">PreferredGroupID</span></span>| <span data-ttu-id="0c290-123">可能であれば、グループ id を指定の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="0c290-123">Sets the group id to the provided value if possible.</span></span> <span data-ttu-id="0c290-124">そのグループ id が現在使用中である場合は、次に使用可能なグループ id が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0c290-124">If the group id is currently in use, the next available group id is used.</span></span>| 
| <span data-ttu-id="0c290-125">DependsOn</span><span class="sxs-lookup"><span data-stu-id="0c290-125">DependsOn</span></span> | <span data-ttu-id="0c290-126">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="0c290-126">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="0c290-127">たとえば、最初に実行するリソース構成スクリプト ブロックの **ID** が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="0c290-127">For example, if the **ID** of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>| 

## <a name="example"></a><span data-ttu-id="0c290-128">例</span><span class="sxs-lookup"><span data-stu-id="0c290-128">Example</span></span>

<span data-ttu-id="0c290-129">次の例では、ユーザー "monuser" が存在し、グループ "DBusers" のメンバーであることを保証しています。</span><span class="sxs-lookup"><span data-stu-id="0c290-129">The following example ensures that the user “monuser” exists and is a member of the group "DBusers".</span></span>

```
Import-DSCResource -Module nx 

Node $node {

nxUser UserExample{
   UserName = "monuser"
   Description = "Monitoring user"
   Password  =    '$6$fZAne/Qc$MZejMrOxDK0ogv9SLiBP5J5qZFBvXLnDu8HY1Oy7ycX.Y3C7mGPUfeQy3A82ev3zIabhDQnj2ayeuGn02CqE/0'
   Ensure = "Present"
   HomeDirectory = "/home/monuser"
}
 
nxGroup GroupExample{
   GroupName = "DBusers"
   Ensure = "Present"
   MembersToInclude = "monuser"
   DependsOn = "[nxUser]UserExample"            
}
}
```

