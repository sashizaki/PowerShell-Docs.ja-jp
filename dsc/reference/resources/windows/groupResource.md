---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC グループ リソース
ms.openlocfilehash: 123e09b54a923af942a15f80fa7291c555b4235f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077349"
---
# <a name="dsc-group-resource"></a><span data-ttu-id="936a1-103">DSC グループ リソース</span><span class="sxs-lookup"><span data-stu-id="936a1-103">DSC Group Resource</span></span>

> <span data-ttu-id="936a1-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="936a1-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="936a1-105">PowerShell Desired State Configuration (DSC) の Group リソースは、ターゲット ノード上でローカル グループを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="936a1-105">The Group resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="936a1-106">構文</span><span class="sxs-lookup"><span data-stu-id="936a1-106">Syntax</span></span>

```
Group [string] #ResourceName
{
    GroupName          = [string]
    [ Credential       = [PSCredential] ]
    [ Description      = [string[]] ]
    [ Ensure           = [string] { Absent | Present }  ]
    [ Members          = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ MembersToInclude = [string[]] ]
    [ DependsOn        = [string[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="936a1-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="936a1-107">Properties</span></span>

|  <span data-ttu-id="936a1-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="936a1-108">Property</span></span>  |  <span data-ttu-id="936a1-109">説明</span><span class="sxs-lookup"><span data-stu-id="936a1-109">Description</span></span>   |
|---|---|
| <span data-ttu-id="936a1-110">GroupName</span><span class="sxs-lookup"><span data-stu-id="936a1-110">GroupName</span></span>| <span data-ttu-id="936a1-111">特定の状態を保証するグループの名前です。</span><span class="sxs-lookup"><span data-stu-id="936a1-111">The name of the group for which you want to ensure a specific state.</span></span>|
| <span data-ttu-id="936a1-112">Credential</span><span class="sxs-lookup"><span data-stu-id="936a1-112">Credential</span></span>| <span data-ttu-id="936a1-113">リモート リソースにアクセスするために必要な資格情報です</span><span class="sxs-lookup"><span data-stu-id="936a1-113">The credentials required to access remote resources.</span></span> <span data-ttu-id="936a1-114">**注**:このアカウントには、ローカルではないすべてのアカウントをグループに追加できる、Active Directory への適切なアクセス許可が必要です。このアクセス許可がない場合、ターゲット ノードで構成が実行されると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="936a1-114">**Note**: This account must have the appropriate Active Directory permissions to add all non-local accounts to the group; otherwise, an error occurs when the configuration is executed on the target node.</span></span>
| <span data-ttu-id="936a1-115">説明</span><span class="sxs-lookup"><span data-stu-id="936a1-115">Description</span></span>| <span data-ttu-id="936a1-116">グループの説明です。</span><span class="sxs-lookup"><span data-stu-id="936a1-116">The description of the group.</span></span>|
| <span data-ttu-id="936a1-117">Ensure</span><span class="sxs-lookup"><span data-stu-id="936a1-117">Ensure</span></span>| <span data-ttu-id="936a1-118">グループが存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="936a1-118">Indicates if the group exists.</span></span> <span data-ttu-id="936a1-119">グループが存在しないことを保証するには、このプロパティを "Absent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="936a1-119">Set this property to "Absent" to ensure that the group does not exist.</span></span> <span data-ttu-id="936a1-120">グループが存在することを保証するには、"Present" (既定値) に設定します。</span><span class="sxs-lookup"><span data-stu-id="936a1-120">Setting it to "Present" (the default value) ensures that the group exists.</span></span>|
| <span data-ttu-id="936a1-121">[メンバー]</span><span class="sxs-lookup"><span data-stu-id="936a1-121">Members</span></span>| <span data-ttu-id="936a1-122">このプロパティは、現在のグループ メンバーシップを指定したメンバーで置き換えるために使用します。</span><span class="sxs-lookup"><span data-stu-id="936a1-122">Use this property to replace the current group membership with the specified members.</span></span> <span data-ttu-id="936a1-123">このプロパティの値は、*Domain*\\*UserName* 形式の文字列の配列です。</span><span class="sxs-lookup"><span data-stu-id="936a1-123">The value of this property is an array of strings of the form *Domain*\\*UserName*.</span></span> <span data-ttu-id="936a1-124">構成でこのプロパティを設定する場合、**MembersToExclude** プロパティおよび **MembersToInclude** プロパティは併用しないでください。</span><span class="sxs-lookup"><span data-stu-id="936a1-124">If you set this property in a configuration, do not use either the **MembersToExclude** or **MembersToInclude** property.</span></span> <span data-ttu-id="936a1-125">併用すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="936a1-125">Doing so generates an error.</span></span>|
| <span data-ttu-id="936a1-126">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="936a1-126">MembersToExclude</span></span>| <span data-ttu-id="936a1-127">このプロパティは、グループの既存のメンバーシップからメンバーを削除するために使用します。</span><span class="sxs-lookup"><span data-stu-id="936a1-127">Use this property to remove members from the existing membership of the group.</span></span> <span data-ttu-id="936a1-128">このプロパティの値は、*Domain*\\*UserName* 形式の文字列の配列です。</span><span class="sxs-lookup"><span data-stu-id="936a1-128">The value of this property is an array of strings of the form *Domain*\\*UserName*.</span></span> <span data-ttu-id="936a1-129">構成でこのプロパティを設定する場合、**Members** プロパティは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="936a1-129">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="936a1-130">併用すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="936a1-130">Doing so generates an error.</span></span>|
| <span data-ttu-id="936a1-131">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="936a1-131">MembersToInclude</span></span>| <span data-ttu-id="936a1-132">このプロパティは、グループの既存のメンバーシップにメンバーを追加するために使用します。</span><span class="sxs-lookup"><span data-stu-id="936a1-132">Use this property to add members to the existing membership of the group.</span></span> <span data-ttu-id="936a1-133">このプロパティの値は、*Domain*\\*UserName* 形式の文字列の配列です。</span><span class="sxs-lookup"><span data-stu-id="936a1-133">The value of this property is an array of strings of the form *Domain*\\*UserName*.</span></span> <span data-ttu-id="936a1-134">構成でこのプロパティを設定する場合、**Members** プロパティは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="936a1-134">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="936a1-135">併用した場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="936a1-135">Doing so will generate an error.</span></span>|
| <span data-ttu-id="936a1-136">DependsOn</span><span class="sxs-lookup"><span data-stu-id="936a1-136">DependsOn</span></span> | <span data-ttu-id="936a1-137">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="936a1-137">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="936a1-138">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は DependsOn = "[ResourceType]ResourceName" になります。</span><span class="sxs-lookup"><span data-stu-id="936a1-138">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is \`DependsOn = "[ResourceType]ResourceName"\`\`.</span></span>|

## <a name="example-1"></a><span data-ttu-id="936a1-139">例 1</span><span class="sxs-lookup"><span data-stu-id="936a1-139">Example 1</span></span>

<span data-ttu-id="936a1-140">次の例では、"TestGroup" という名前のグループが存在しないことを保証する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="936a1-140">The following example shows how to ensure that a group called "TestGroup" is absent.</span></span>

```powershell
Group GroupExample
{
    # This removes TestGroup, if present
    # To create a new group, set Ensure to "Present“
    Ensure = "Absent"
    GroupName = "TestGroup"
}
```

## <a name="example-2"></a><span data-ttu-id="936a1-141">例 2</span><span class="sxs-lookup"><span data-stu-id="936a1-141">Example 2</span></span>

<span data-ttu-id="936a1-142">次の例では、Multi-Machine Lab ビルドの一部として Active Directory ユーザーをローカルの Administrators グループに追加する方法を示します。このビルドでは、ローカル管理者アカウントの PSCredential を既に使用しています。</span><span class="sxs-lookup"><span data-stu-id="936a1-142">The following example shows how to add an Active Directory User to the local administrators group as part of a Multi-Machine Lab build where you are already using a PSCredential for the Local Administrator account.</span></span>
<span data-ttu-id="936a1-143">また、これは (ドメインの昇格後に) ドメイン管理者アカウントにも使用されるため、この既存の PSCredential はドメインで利用しやすい資格情報に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="936a1-143">As this is also used for the Domain Admin Account (after Domain promotion), we then need to convert this existing PSCredential to a Domain Friendly credential.</span></span>
<span data-ttu-id="936a1-144">その後、ドメイン ユーザーをメンバー サーバー上のローカルの Administrators グループに追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="936a1-144">Then we can add a Domain User to the Local Administrators Group on the Member server.</span></span>

```powershell
@{
    AllNodes = @(
        @{
            NodeName = '*';
            DomainName = 'SubTest.contoso.com';
         }
        @{
            NodeName = 'Box2';
            AdminAccount = 'Admin-Dave_Alexanderson'
        }
    )
}

$domain = $node.DomainName.split('.')[0]
$DCredential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList ("$domain\$($credential.Username)", $Credential.Password)

Group AddADUserToLocalAdminGroup {
    GroupName='Administrators'
    Ensure= 'Present'
    MembersToInclude= "$domain\$($Node.AdminAccount)"
    Credential = $dCredential
    PsDscRunAsCredential = $DCredential
}
```

## <a name="example-3"></a><span data-ttu-id="936a1-145">例 3</span><span class="sxs-lookup"><span data-stu-id="936a1-145">Example 3</span></span>

<span data-ttu-id="936a1-146">サーバー TigerTeamSource.Contoso.Com 上のローカル グループ TigerTeamAdmins に、特定のドメイン アカウント Contoso\JerryG が含まれないようにする例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="936a1-146">The following example shows how to ensure a local group, TigerTeamAdmins, on the server TigerTeamSource.Contoso.Com does not contain a particular domain account, Contoso\JerryG.</span></span>

```powershell
Configuration SecureTigerTeamSource {
  Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

  Node TigerTeamSource.Contoso.Com {
    Group TigerTeamAdmins {
       GroupName        = 'TigerTeamAdmins'
       Ensure           = 'Present'
       MembersToExclude = "Contoso\JerryG"
    }
  }
}
```