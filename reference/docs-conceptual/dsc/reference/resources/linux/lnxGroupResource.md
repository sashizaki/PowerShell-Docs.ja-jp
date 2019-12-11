---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 DSC の nxGroup リソース
ms.openlocfilehash: 098ae2e8ab183934ec3c185c0fd237731b1353dc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953209"
---
# <a name="dsc-for-linux-nxgroup-resource"></a><span data-ttu-id="41c5f-103">Linux 用 DSC の nxGroup リソース</span><span class="sxs-lookup"><span data-stu-id="41c5f-103">DSC for Linux nxGroup Resource</span></span>

<span data-ttu-id="41c5f-104">PowerShell Desired State Configuration (DSC) の **nxGroup** リソースは、Linux ノード上でローカル グループを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="41c5f-104">The **nxGroup** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="41c5f-105">構文</span><span class="sxs-lookup"><span data-stu-id="41c5f-105">Syntax</span></span>

```Syntax
nxGroup <string> #ResourceName
{
    GroupName = <string>
    [ Members = <string[]> ]
    [ MembersToInclude = <string[]> ]
    [ MembersToExclude = <string[]> ]
    [ PreferredGroupID = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present } ]
}
```

## <a name="properties"></a><span data-ttu-id="41c5f-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="41c5f-106">Properties</span></span>

|<span data-ttu-id="41c5f-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="41c5f-107">Property</span></span> |<span data-ttu-id="41c5f-108">説明</span><span class="sxs-lookup"><span data-stu-id="41c5f-108">Description</span></span> |
|---|---|
|<span data-ttu-id="41c5f-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="41c5f-109">GroupName</span></span> |<span data-ttu-id="41c5f-110">特定の状態を保証するグループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="41c5f-110">Specifies the name of the group for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="41c5f-111">[メンバー]</span><span class="sxs-lookup"><span data-stu-id="41c5f-111">Members</span></span> |<span data-ttu-id="41c5f-112">グループを形成するメンバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="41c5f-112">Specifies the members that form the group.</span></span> |
|<span data-ttu-id="41c5f-113">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="41c5f-113">MembersToInclude</span></span> |<span data-ttu-id="41c5f-114">グループのメンバーであることを保証するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="41c5f-114">Specifies the users who you want to ensure are members of the group.</span></span> |
|<span data-ttu-id="41c5f-115">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="41c5f-115">MembersToExclude</span></span> |<span data-ttu-id="41c5f-116">グループのメンバーでないことを保証するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="41c5f-116">Specifies the users who you want to ensure are not members of the group.</span></span> |
|<span data-ttu-id="41c5f-117">PreferredGroupID</span><span class="sxs-lookup"><span data-stu-id="41c5f-117">PreferredGroupID</span></span> |<span data-ttu-id="41c5f-118">可能であれば、グループ id を指定の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="41c5f-118">Sets the group id to the provided value if possible.</span></span> <span data-ttu-id="41c5f-119">そのグループ id が現在使用中である場合は、次に使用可能なグループ id が使用されます。</span><span class="sxs-lookup"><span data-stu-id="41c5f-119">If the group id is currently in use, the next available group id is used.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="41c5f-120">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="41c5f-120">Common properties</span></span>

|<span data-ttu-id="41c5f-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="41c5f-121">Property</span></span> |<span data-ttu-id="41c5f-122">説明</span><span class="sxs-lookup"><span data-stu-id="41c5f-122">Description</span></span> |
|---|---|
|<span data-ttu-id="41c5f-123">DependsOn</span><span class="sxs-lookup"><span data-stu-id="41c5f-123">DependsOn</span></span> |<span data-ttu-id="41c5f-124">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="41c5f-124">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="41c5f-125">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="41c5f-125">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="41c5f-126">Ensure</span><span class="sxs-lookup"><span data-stu-id="41c5f-126">Ensure</span></span> |<span data-ttu-id="41c5f-127">グループが存在するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="41c5f-127">Determines whether to check if the group exists.</span></span> <span data-ttu-id="41c5f-128">グループの存在を保証するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="41c5f-128">Set this property to **Present** to ensure the group exists.</span></span> <span data-ttu-id="41c5f-129">グループが存在しないことを保証するには、**Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="41c5f-129">Set it to **Absent** to ensure the group does not exist.</span></span> <span data-ttu-id="41c5f-130">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="41c5f-130">The default value is **Present**.</span></span> |

## <a name="example"></a><span data-ttu-id="41c5f-131">例</span><span class="sxs-lookup"><span data-stu-id="41c5f-131">Example</span></span>

<span data-ttu-id="41c5f-132">次の例では、ユーザー 'monuser' が存在し、グループ 'DBusers' のメンバーであることを保証しています。</span><span class="sxs-lookup"><span data-stu-id="41c5f-132">The following example ensures that the user 'monuser' exists and is a member of the group 'DBusers'.</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxUser UserExample {
       UserName = 'monuser'
       Description = 'Monitoring user'
       Password = '$6$fZAne/Qc$MZejMrOxDK0ogv9SLiBP5J5qZFBvXLnDu8HY1Oy7ycX.Y3C7mGPUfeQy3A82ev3zIabhDQnj2ayeuGn02CqE/0'
       Ensure = 'Present'
       HomeDirectory = '/home/monuser'
    }

    nxGroup GroupExample {
       GroupName = 'DBusers'
       Ensure = 'Present'
       MembersToInclude = 'monuser'
       DependsOn = '[nxUser]UserExample'
    }
}
```