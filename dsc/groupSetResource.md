---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
description: ターゲット ノード上のローカル グループを管理するためのメカニズムを備えています。
title: DSC GroupSet リソース
ms.openlocfilehash: 487a76ca7703b2c57b940b4c5bd176eada6c8019
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37892428"
---
# <a name="dsc-groupset-resource"></a><span data-ttu-id="1591e-104">DSC GroupSet リソース</span><span class="sxs-lookup"><span data-stu-id="1591e-104">DSC GroupSet Resource</span></span>

> <span data-ttu-id="1591e-105">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="1591e-105">Applies To: Windows Windows PowerShell 5.0</span></span>

<span data-ttu-id="1591e-106">PowerShell Desired State Configuration (DSC) の **GroupSet** リソースは、ターゲット ノード上でローカル グループを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="1591e-106">The **GroupSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on the target node.</span></span> <span data-ttu-id="1591e-107">このリソースは[複合リソース](authoringResourceComposite.md)であり、`GroupName` パラメーターに指定されているグループごとに [Group リソース](groupResource.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1591e-107">This resource is a [composite resource](authoringResourceComposite.md) that calls the [Group resource](groupResource.md) for each group specified in the `GroupName` parameter.</span></span>

<span data-ttu-id="1591e-108">このリソースは、複数のグループに対して同じメンバー一覧の追加/削除を行うとき、複数のグループを削除するとき、同じメンバー一覧の複数のグループを追加するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="1591e-108">Use this resource when you want to add and/or remove the same list of members to more than one group, remove more than one group, or add more than one group with the same list of members.</span></span>

## <a name="syntax"></a><span data-ttu-id="1591e-109">構文</span><span class="sxs-lookup"><span data-stu-id="1591e-109">Syntax</span></span>

```
Group [string] #ResourceName
{
    GroupName = [string[]]
    [ Ensure = [string] { Absent | Present }  ]
    [ MembersToInclude = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="1591e-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1591e-110">Properties</span></span>

|  <span data-ttu-id="1591e-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1591e-111">Property</span></span>  |  <span data-ttu-id="1591e-112">説明</span><span class="sxs-lookup"><span data-stu-id="1591e-112">Description</span></span>   |
|---|---|
| <span data-ttu-id="1591e-113">GroupName</span><span class="sxs-lookup"><span data-stu-id="1591e-113">GroupName</span></span>| <span data-ttu-id="1591e-114">特定の状態を保証するグループの名前です。</span><span class="sxs-lookup"><span data-stu-id="1591e-114">The names of the groups for which you want to ensure a specific state.</span></span>|
| <span data-ttu-id="1591e-115">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="1591e-115">MembersToExclude</span></span>| <span data-ttu-id="1591e-116">このプロパティは、グループの既存のメンバーシップからメンバーを削除するために使用します。</span><span class="sxs-lookup"><span data-stu-id="1591e-116">Use this property to remove members from the existing membership of the groups.</span></span> <span data-ttu-id="1591e-117">このプロパティの値は、*Domain*\\*UserName* 形式の文字列の配列です。</span><span class="sxs-lookup"><span data-stu-id="1591e-117">The value of this property is an array of strings of the form *Domain*\\*UserName*.</span></span> <span data-ttu-id="1591e-118">構成でこのプロパティを設定する場合、**Members** プロパティは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="1591e-118">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="1591e-119">併用した場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1591e-119">Doing so will generate an error.</span></span>|
| <span data-ttu-id="1591e-120">Credential</span><span class="sxs-lookup"><span data-stu-id="1591e-120">Credential</span></span>| <span data-ttu-id="1591e-121">リモート リソースにアクセスするために必要な資格情報です</span><span class="sxs-lookup"><span data-stu-id="1591e-121">The credentials required to access remote resources.</span></span> <span data-ttu-id="1591e-122">**注**: このアカウントには、ローカル以外のすべてのアカウントをグループに追加する適切な Active Directory アクセス許可が必要です。このアクセス許可がない場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1591e-122">**Note**: This account must have the appropriate Active Directory permissions to add all non-local accounts to the group; otherwise, an error will occur.</span></span>
| <span data-ttu-id="1591e-123">Ensure</span><span class="sxs-lookup"><span data-stu-id="1591e-123">Ensure</span></span>| <span data-ttu-id="1591e-124">グループが存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="1591e-124">Indicates whether the groups exist.</span></span> <span data-ttu-id="1591e-125">グループが存在しないことを保証するには、このプロパティを "Absent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="1591e-125">Set this property to "Absent" to ensure that the groups do not exist.</span></span> <span data-ttu-id="1591e-126">グループが存在することを保証するには、"Present" (既定値) に設定します。</span><span class="sxs-lookup"><span data-stu-id="1591e-126">Setting it to "Present" (the default value) ensures that the groups exist.</span></span>|
| <span data-ttu-id="1591e-127">[メンバー]</span><span class="sxs-lookup"><span data-stu-id="1591e-127">Members</span></span>| <span data-ttu-id="1591e-128">このプロパティは、現在のグループ メンバーシップを指定したメンバーで置き換えるために使用します。</span><span class="sxs-lookup"><span data-stu-id="1591e-128">Use this property to replace the current group membership with the specified members.</span></span> <span data-ttu-id="1591e-129">このプロパティの値は、*Domain*\\*UserName* 形式の文字列の配列です。</span><span class="sxs-lookup"><span data-stu-id="1591e-129">The value of this property is an array of strings of the form *Domain*\\*UserName*.</span></span> <span data-ttu-id="1591e-130">構成でこのプロパティを設定する場合、**MembersToExclude** プロパティおよび **MembersToInclude** プロパティは併用しないでください。</span><span class="sxs-lookup"><span data-stu-id="1591e-130">If you set this property in a configuration, do not use either the **MembersToExclude** or **MembersToInclude** property.</span></span> <span data-ttu-id="1591e-131">併用した場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1591e-131">Doing so will generate an error.</span></span>|
| <span data-ttu-id="1591e-132">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="1591e-132">MembersToInclude</span></span>| <span data-ttu-id="1591e-133">このプロパティは、グループの既存のメンバーシップにメンバーを追加するために使用します。</span><span class="sxs-lookup"><span data-stu-id="1591e-133">Use this property to add members to the existing membership of the group.</span></span> <span data-ttu-id="1591e-134">このプロパティの値は、*Domain*\\*UserName* 形式の文字列の配列です。</span><span class="sxs-lookup"><span data-stu-id="1591e-134">The value of this property is an array of strings of the form *Domain*\\*UserName*.</span></span> <span data-ttu-id="1591e-135">構成でこのプロパティを設定する場合、**Members** プロパティは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="1591e-135">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="1591e-136">併用した場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1591e-136">Doing so will generate an error.</span></span>|
| <span data-ttu-id="1591e-137">DependsOn</span><span class="sxs-lookup"><span data-stu-id="1591e-137">DependsOn</span></span> | <span data-ttu-id="1591e-138">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="1591e-138">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="1591e-139">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は DependsOn = "[ResourceType]ResourceName" になります。</span><span class="sxs-lookup"><span data-stu-id="1591e-139">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is \`DependsOn = "[ResourceType]ResourceName"\`\`.</span></span>|

## <a name="example-1-ensuring-groups-are-present"></a><span data-ttu-id="1591e-140">例 1: グループが存在することを確認する</span><span class="sxs-lookup"><span data-stu-id="1591e-140">Example 1: Ensuring Groups are present</span></span>

<span data-ttu-id="1591e-141">次に、"myGroup" と "myOtherGroup" という 2 つのグループが存在することを保証する例を示します。</span><span class="sxs-lookup"><span data-stu-id="1591e-141">The following example shows how to ensure that two groups called "myGroup" and "myOtherGroup" are present.</span></span>

```powershell
configuration GroupSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {
        GroupSet GroupSetTest
        {
            GroupName        = @("myGroup", "myOtherGroup")
            Ensure           = "Present"
            MembersToInclude = @("contoso\alice", "contoso\bob")
            MembersToExclude = $("contoso\john")
            Credential       = Get-Credential
        }
    }
}
$cd = @{
    AllNodes = @(
        @{
            NodeName                    = 'localhost'
            PSDscAllowPlainTextPassword = $true
            PSDscAllowDomainUser        = $true
        }
    )
}

GroupSetTest -ConfigurationData $cd
```

> [!NOTE] 
> <span data-ttu-id="1591e-142">この例では、わかりやすくするためにプレーンテキストの資格情報を使用しています。</span><span class="sxs-lookup"><span data-stu-id="1591e-142">This example uses plaintext credentials for simplicity.</span></span> <span data-ttu-id="1591e-143">構成 MOF ファイル内の資格情報を暗号化する方法の詳細については、「[MOF ファイルのセキュリティ保護](secureMOF.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1591e-143">For information about how to encrypt credentials in the configuration MOF file, see [Securing the MOF File](secureMOF.md).</span></span>
