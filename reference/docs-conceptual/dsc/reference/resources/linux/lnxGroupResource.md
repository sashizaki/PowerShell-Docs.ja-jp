---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 DSC の nxGroup リソース
ms.openlocfilehash: 098ae2e8ab183934ec3c185c0fd237731b1353dc
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953209"
---
# <a name="dsc-for-linux-nxgroup-resource"></a><span data-ttu-id="e50b4-103">Linux 用 DSC の nxGroup リソース</span><span class="sxs-lookup"><span data-stu-id="e50b4-103">DSC for Linux nxGroup Resource</span></span>

<span data-ttu-id="e50b4-104">PowerShell Desired State Configuration (DSC) の **nxGroup** リソースは、Linux ノード上でローカル グループを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="e50b4-104">The **nxGroup** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="e50b4-105">構文</span><span class="sxs-lookup"><span data-stu-id="e50b4-105">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="e50b4-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e50b4-106">Properties</span></span>

|<span data-ttu-id="e50b4-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e50b4-107">Property</span></span> |<span data-ttu-id="e50b4-108">説明</span><span class="sxs-lookup"><span data-stu-id="e50b4-108">Description</span></span> |
|---|---|
|<span data-ttu-id="e50b4-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="e50b4-109">GroupName</span></span> |<span data-ttu-id="e50b4-110">特定の状態を保証するグループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e50b4-110">Specifies the name of the group for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="e50b4-111">[メンバー]</span><span class="sxs-lookup"><span data-stu-id="e50b4-111">Members</span></span> |<span data-ttu-id="e50b4-112">グループを形成するメンバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e50b4-112">Specifies the members that form the group.</span></span> |
|<span data-ttu-id="e50b4-113">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="e50b4-113">MembersToInclude</span></span> |<span data-ttu-id="e50b4-114">グループのメンバーであることを保証するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e50b4-114">Specifies the users who you want to ensure are members of the group.</span></span> |
|<span data-ttu-id="e50b4-115">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="e50b4-115">MembersToExclude</span></span> |<span data-ttu-id="e50b4-116">グループのメンバーでないことを保証するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e50b4-116">Specifies the users who you want to ensure are not members of the group.</span></span> |
|<span data-ttu-id="e50b4-117">PreferredGroupID</span><span class="sxs-lookup"><span data-stu-id="e50b4-117">PreferredGroupID</span></span> |<span data-ttu-id="e50b4-118">可能であれば、グループ id を指定の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="e50b4-118">Sets the group id to the provided value if possible.</span></span> <span data-ttu-id="e50b4-119">そのグループ id が現在使用中である場合は、次に使用可能なグループ id が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e50b4-119">If the group id is currently in use, the next available group id is used.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="e50b4-120">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="e50b4-120">Common properties</span></span>

|<span data-ttu-id="e50b4-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e50b4-121">Property</span></span> |<span data-ttu-id="e50b4-122">説明</span><span class="sxs-lookup"><span data-stu-id="e50b4-122">Description</span></span> |
|---|---|
|<span data-ttu-id="e50b4-123">DependsOn</span><span class="sxs-lookup"><span data-stu-id="e50b4-123">DependsOn</span></span> |<span data-ttu-id="e50b4-124">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="e50b4-124">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="e50b4-125">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="e50b4-125">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="e50b4-126">Ensure</span><span class="sxs-lookup"><span data-stu-id="e50b4-126">Ensure</span></span> |<span data-ttu-id="e50b4-127">グループが存在するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e50b4-127">Determines whether to check if the group exists.</span></span> <span data-ttu-id="e50b4-128">グループの存在を保証するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e50b4-128">Set this property to **Present** to ensure the group exists.</span></span> <span data-ttu-id="e50b4-129">グループが存在しないことを保証するには、**Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e50b4-129">Set it to **Absent** to ensure the group does not exist.</span></span> <span data-ttu-id="e50b4-130">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="e50b4-130">The default value is **Present**.</span></span> |

## <a name="example"></a><span data-ttu-id="e50b4-131">例</span><span class="sxs-lookup"><span data-stu-id="e50b4-131">Example</span></span>

<span data-ttu-id="e50b4-132">次の例では、ユーザー 'monuser' が存在し、グループ 'DBusers' のメンバーであることを保証しています。</span><span class="sxs-lookup"><span data-stu-id="e50b4-132">The following example ensures that the user 'monuser' exists and is a member of the group 'DBusers'.</span></span>

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