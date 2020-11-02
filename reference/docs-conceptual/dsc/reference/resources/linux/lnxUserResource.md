---
ms.date: 07/17/2020
ms.topic: reference
title: Linux 用 DSC の nxUser リソース
description: Linux 用 DSC の nxUser リソース
ms.openlocfilehash: 298caa8f5ea6d4587f9782a02d0544147ee33e84
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92667387"
---
# <a name="dsc-for-linux-nxuser-resource"></a><span data-ttu-id="75060-103">Linux 用 DSC の nxUser リソース</span><span class="sxs-lookup"><span data-stu-id="75060-103">DSC for Linux nxUser Resource</span></span>

<span data-ttu-id="75060-104">PowerShell Desired State Configuration (DSC) の **nxUser** リソースは、Linux ノード上でローカル ユーザーを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="75060-104">The **nxUser** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage local users on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="75060-105">構文</span><span class="sxs-lookup"><span data-stu-id="75060-105">Syntax</span></span>

```Syntax
nxUser <string> #ResourceName
{
    UserName = <string>
    [ FullName = <string> ]
    [ Description = <string> ]
    [ Password = <string> ]
    [ Disabled = <bool> ]
    [ PasswordChangeRequired = <bool> ]
    [ HomeDirectory = <string> ]
    [ GroupID = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a><span data-ttu-id="75060-106">Properties</span><span class="sxs-lookup"><span data-stu-id="75060-106">Properties</span></span>

|<span data-ttu-id="75060-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="75060-107">Property</span></span> |<span data-ttu-id="75060-108">特定の状態を保証するアカウント名を示します。</span><span class="sxs-lookup"><span data-stu-id="75060-108">Indicates the account name for which you want to ensure a specific state.</span></span> |
|---|---|
|<span data-ttu-id="75060-109">UserName</span><span class="sxs-lookup"><span data-stu-id="75060-109">UserName</span></span> |<span data-ttu-id="75060-110">ファイルまたはディレクトリの状態を保証する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="75060-110">Specifies the location where you want to ensure the state for a file or directory.</span></span> |
|<span data-ttu-id="75060-111">FullName</span><span class="sxs-lookup"><span data-stu-id="75060-111">FullName</span></span> |<span data-ttu-id="75060-112">ユーザー アカウントに使用するフルネームを表す文字列。</span><span class="sxs-lookup"><span data-stu-id="75060-112">A string that contains the full name to use for the user account.</span></span> |
|<span data-ttu-id="75060-113">説明</span><span class="sxs-lookup"><span data-stu-id="75060-113">Description</span></span> |<span data-ttu-id="75060-114">ユーザー アカウントの説明。</span><span class="sxs-lookup"><span data-stu-id="75060-114">The description for the user account.</span></span> |
|<span data-ttu-id="75060-115">Password</span><span class="sxs-lookup"><span data-stu-id="75060-115">Password</span></span> |<span data-ttu-id="75060-116">Linux コンピューターの適切な形式でのユーザー パスワードのハッシュ。</span><span class="sxs-lookup"><span data-stu-id="75060-116">The hash of the users password in the appropriate form for the Linux computer.</span></span> <span data-ttu-id="75060-117">通常、これはソルト化ハッシュ SHA-256 または SHA-512 です。</span><span class="sxs-lookup"><span data-stu-id="75060-117">Typically, this is a salted SHA-256, or SHA-512 hash.</span></span> <span data-ttu-id="75060-118">Debian および Ubuntu Linux では、この値は、`mkpasswd` コマンドを使用して生成できます。</span><span class="sxs-lookup"><span data-stu-id="75060-118">On Debian and Ubuntu Linux, this value can be generated with the `mkpasswd` command.</span></span> <span data-ttu-id="75060-119">他の Linux ディストリビューションの場合は、Python の暗号ライブラリの crypt メソッドを使用してハッシュを生成できます。</span><span class="sxs-lookup"><span data-stu-id="75060-119">For other Linux distros, the crypt method of Python's Crypt library can be used to generate the hash.</span></span> |
|<span data-ttu-id="75060-120">無効</span><span class="sxs-lookup"><span data-stu-id="75060-120">Disabled</span></span> |<span data-ttu-id="75060-121">アカウントが有効かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="75060-121">Indicates whether the account is enabled.</span></span> <span data-ttu-id="75060-122">このアカウントを無効にするには、このプロパティを `$true` に設定し、有効にするには `$false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="75060-122">Set this property to `$true` to ensure that this account is disabled, and set it to `$false` to ensure that it is enabled.</span></span> |
|<span data-ttu-id="75060-123">PasswordChangeRequired</span><span class="sxs-lookup"><span data-stu-id="75060-123">PasswordChangeRequired</span></span> |<span data-ttu-id="75060-124">ユーザーがパスワードを変更できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="75060-124">Indicates whether the user can change the password.</span></span> <span data-ttu-id="75060-125">ユーザーがパスワードを変更できないようにするには、このプロパティを `$true` に設定し、ユーザーがパスワードを変更できるようにするには、`$false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="75060-125">Set this property to `$true` to ensure that the user cannot change the password, and set it to `$false` to allow the user to change the password.</span></span> <span data-ttu-id="75060-126">既定値は `$false` です。</span><span class="sxs-lookup"><span data-stu-id="75060-126">The default value is `$false`.</span></span> <span data-ttu-id="75060-127">このプロパティは、以前存在しなかったユーザー アカウントを作成するときにのみ評価されます。</span><span class="sxs-lookup"><span data-stu-id="75060-127">This property is only evaluated if the user account did not exist previously and is being created.</span></span> |
|<span data-ttu-id="75060-128">HomeDirectory</span><span class="sxs-lookup"><span data-stu-id="75060-128">HomeDirectory</span></span> |<span data-ttu-id="75060-129">ユーザーのホーム ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="75060-129">The home directory for the user.</span></span> |
|<span data-ttu-id="75060-130">GroupID</span><span class="sxs-lookup"><span data-stu-id="75060-130">GroupID</span></span> |<span data-ttu-id="75060-131">ユーザーのプライマリ グループ ID。</span><span class="sxs-lookup"><span data-stu-id="75060-131">The primary group ID for the user.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="75060-132">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="75060-132">Common properties</span></span>

|<span data-ttu-id="75060-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="75060-133">Property</span></span> |<span data-ttu-id="75060-134">説明</span><span class="sxs-lookup"><span data-stu-id="75060-134">Description</span></span> |
|---|---|
|<span data-ttu-id="75060-135">DependsOn</span><span class="sxs-lookup"><span data-stu-id="75060-135">DependsOn</span></span> |<span data-ttu-id="75060-136">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="75060-136">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="75060-137">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="75060-137">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="75060-138">Ensure</span><span class="sxs-lookup"><span data-stu-id="75060-138">Ensure</span></span> |<span data-ttu-id="75060-139">アカウントが存在するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="75060-139">Specifies whether the account exists.</span></span> <span data-ttu-id="75060-140">このアカウントの存在を保証するには、このプロパティを **Present** に設定し、アカウントが存在しないことを保証するには、 **Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="75060-140">Set this property to **Present** to ensure that the account exists, and set it to **Absent** to ensure that the account does not exist.</span></span> |

## <a name="example"></a><span data-ttu-id="75060-141">例</span><span class="sxs-lookup"><span data-stu-id="75060-141">Example</span></span>

<span data-ttu-id="75060-142">次の例は、ユーザー "monuser" が存在し、グループ "DBusers" のメンバーであることを保証しています。</span><span class="sxs-lookup"><span data-stu-id="75060-142">The following example ensures that the user "monuser" exists and is a member of the group "DBusers".</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
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
