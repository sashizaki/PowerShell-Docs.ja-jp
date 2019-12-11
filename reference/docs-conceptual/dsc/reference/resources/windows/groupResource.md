---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC グループ リソース
ms.openlocfilehash: 695a914683c6daff44dd2a6c94b6353acf881030
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71954659"
---
# <a name="dsc-group-resource"></a><span data-ttu-id="93642-103">DSC グループ リソース</span><span class="sxs-lookup"><span data-stu-id="93642-103">DSC Group Resource</span></span>

> <span data-ttu-id="93642-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="93642-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="93642-105">Windows PowerShell Desired State Configuration (DSC) の **Group** リソースは、ターゲット ノード上でローカル グループを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="93642-105">The **Group** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="93642-106">構文</span><span class="sxs-lookup"><span data-stu-id="93642-106">Syntax</span></span>

```Syntax
Group [string] #ResourceName
{
    GroupName = [string]
    [ Credential = [PSCredential] ]
    [ Description = [string[]] ]
    [ Members = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ MembersToInclude = [string[]] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="93642-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="93642-107">Properties</span></span>

|<span data-ttu-id="93642-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="93642-108">Property</span></span> |<span data-ttu-id="93642-109">説明</span><span class="sxs-lookup"><span data-stu-id="93642-109">Description</span></span> |
|---|---|
|<span data-ttu-id="93642-110">GroupName</span><span class="sxs-lookup"><span data-stu-id="93642-110">GroupName</span></span> |<span data-ttu-id="93642-111">特定の状態を保証するグループの名前です。</span><span class="sxs-lookup"><span data-stu-id="93642-111">The name of the group for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="93642-112">Credential</span><span class="sxs-lookup"><span data-stu-id="93642-112">Credential</span></span> |<span data-ttu-id="93642-113">リモート リソースにアクセスするために必要な資格情報です</span><span class="sxs-lookup"><span data-stu-id="93642-113">The credentials required to access remote resources.</span></span> <span data-ttu-id="93642-114">このアカウントには、ローカルではないすべてのアカウントをグループに追加できる、Active Directory への適切なアクセス許可が必要です。このアクセス許可がない場合、ターゲット ノードで構成が実行されると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="93642-114">This account must have the appropriate Active Directory permissions to add all non-local accounts to the group; otherwise, an error occurs when the configuration is executed on the target node.</span></span>
|<span data-ttu-id="93642-115">説明</span><span class="sxs-lookup"><span data-stu-id="93642-115">Description</span></span> |<span data-ttu-id="93642-116">グループの説明です。</span><span class="sxs-lookup"><span data-stu-id="93642-116">The description of the group.</span></span> |
|<span data-ttu-id="93642-117">[メンバー]</span><span class="sxs-lookup"><span data-stu-id="93642-117">Members</span></span> |<span data-ttu-id="93642-118">このプロパティは、現在のグループ メンバーシップを指定したメンバーで置き換えるために使用します。</span><span class="sxs-lookup"><span data-stu-id="93642-118">Use this property to replace the current group membership with the specified members.</span></span> <span data-ttu-id="93642-119">このプロパティの値は、`Domain\UserName` 形式の文字列の配列です。</span><span class="sxs-lookup"><span data-stu-id="93642-119">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="93642-120">構成でこのプロパティを設定する場合、**MembersToExclude** プロパティおよび **MembersToInclude** プロパティは併用しないでください。</span><span class="sxs-lookup"><span data-stu-id="93642-120">If you set this property in a configuration, do not use either the **MembersToExclude** or **MembersToInclude** property.</span></span> <span data-ttu-id="93642-121">併用すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="93642-121">Doing so generates an error.</span></span> |
|<span data-ttu-id="93642-122">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="93642-122">MembersToExclude</span></span> |<span data-ttu-id="93642-123">このプロパティは、グループの既存のメンバーシップからメンバーを削除するために使用します。</span><span class="sxs-lookup"><span data-stu-id="93642-123">Use this property to remove members from the existing membership of the group.</span></span> <span data-ttu-id="93642-124">このプロパティの値は、`Domain\UserName` 形式の文字列の配列です。</span><span class="sxs-lookup"><span data-stu-id="93642-124">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="93642-125">構成でこのプロパティを設定する場合、**Members** プロパティは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="93642-125">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="93642-126">併用すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="93642-126">Doing so generates an error.</span></span> |
|<span data-ttu-id="93642-127">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="93642-127">MembersToInclude</span></span> |<span data-ttu-id="93642-128">このプロパティは、グループの既存のメンバーシップにメンバーを追加するために使用します。</span><span class="sxs-lookup"><span data-stu-id="93642-128">Use this property to add members to the existing membership of the group.</span></span> <span data-ttu-id="93642-129">このプロパティの値は、`Domain\UserName` 形式の文字列の配列です。</span><span class="sxs-lookup"><span data-stu-id="93642-129">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="93642-130">構成でこのプロパティを設定する場合、**Members** プロパティは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="93642-130">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="93642-131">併用した場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="93642-131">Doing so will generate an error.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="93642-132">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="93642-132">Common properties</span></span>

|<span data-ttu-id="93642-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="93642-133">Property</span></span> |<span data-ttu-id="93642-134">説明</span><span class="sxs-lookup"><span data-stu-id="93642-134">Description</span></span> |
|---|---|
|<span data-ttu-id="93642-135">DependsOn</span><span class="sxs-lookup"><span data-stu-id="93642-135">DependsOn</span></span> |<span data-ttu-id="93642-136">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="93642-136">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="93642-137">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="93642-137">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="93642-138">Ensure</span><span class="sxs-lookup"><span data-stu-id="93642-138">Ensure</span></span> |<span data-ttu-id="93642-139">グループが存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="93642-139">Indicates if the group exists.</span></span> <span data-ttu-id="93642-140">グループが存在しないことを保証するには、このプロパティを **Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="93642-140">Set this property to **Absent** to ensure that the group does not exist.</span></span> <span data-ttu-id="93642-141">グループが存在することを保証するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="93642-141">Setting it to **Present** ensures that the group exists.</span></span> <span data-ttu-id="93642-142">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="93642-142">The default value is **Present**.</span></span> |
|<span data-ttu-id="93642-143">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="93642-143">PsDscRunAsCredential</span></span> |<span data-ttu-id="93642-144">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="93642-144">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="93642-145">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="93642-145">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="93642-146">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93642-146">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example-1-ensure-group-is-not-present"></a><span data-ttu-id="93642-147">例 1:グループが存在しないことを保証する</span><span class="sxs-lookup"><span data-stu-id="93642-147">Example 1: Ensure group is not present</span></span>

<span data-ttu-id="93642-148">次の例では、"TestGroup" という名前のグループが存在しないことを保証する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="93642-148">The following example shows how to ensure that a group called "TestGroup" is absent.</span></span>

```powershell
Group GroupExample
{
    # This removes TestGroup, if present
    # To create a new group, set Ensure to "Present"
    Ensure = "Absent"
    GroupName = "TestGroup"
}
```

## <a name="example-2-add-domain-user-to-local-group"></a><span data-ttu-id="93642-149">例 2:ローカル グループにドメイン ユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="93642-149">Example 2: Add domain user to local group</span></span>

<span data-ttu-id="93642-150">次の例では、Multi-Machine Lab ビルドの一部として Active Directory ユーザーをローカルの Administrators グループに追加する方法を示します。このビルドでは、ローカル管理者アカウントの PSCredential を既に使用しています。</span><span class="sxs-lookup"><span data-stu-id="93642-150">The following example shows how to add an Active Directory User to the local administrators group as part of a Multi-Machine Lab build where you are already using a PSCredential for the Local Administrator account.</span></span> <span data-ttu-id="93642-151">また、これは (ドメインの昇格後に) ドメイン管理者アカウントにも使用されるため、この既存の PSCredential はドメインで利用しやすい資格情報に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93642-151">As this is also used for the Domain Admin Account (after Domain promotion), we then need to convert this existing PSCredential to a Domain Friendly credential.</span></span> <span data-ttu-id="93642-152">その後、ドメイン ユーザーをメンバー サーバー上のローカルの Administrators グループに追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="93642-152">Then we can add a Domain User to the Local Administrators Group on the Member server.</span></span>

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

## <a name="example-3"></a><span data-ttu-id="93642-153">例 3</span><span class="sxs-lookup"><span data-stu-id="93642-153">Example 3</span></span>

<span data-ttu-id="93642-154">サーバー TigerTeamSource.Contoso.Com 上のローカル グループ TigerTeamAdmins に、特定のドメイン アカウント Contoso\JerryG が含まれないようにする例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="93642-154">The following example shows how to ensure a local group, TigerTeamAdmins, on the server TigerTeamSource.Contoso.Com does not contain a particular domain account, Contoso\JerryG.</span></span>

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