---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 DSC の nxUser リソース
ms.openlocfilehash: 6d7b52809741813af7fa80b1c6372b267aff4777
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954799"
---
# <a name="dsc-for-linux-nxuser-resource"></a><span data-ttu-id="57d65-103">Linux 用 DSC の nxUser リソース</span><span class="sxs-lookup"><span data-stu-id="57d65-103">DSC for Linux nxUser Resource</span></span>

<span data-ttu-id="57d65-104">PowerShell Desired State Configuration (DSC) の **nxUser** リソースは、Linux ノード上でローカル ユーザーを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="57d65-104">The **nxUser** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage local users on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="57d65-105">構文</span><span class="sxs-lookup"><span data-stu-id="57d65-105">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="57d65-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="57d65-106">Properties</span></span>

|<span data-ttu-id="57d65-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="57d65-107">Property</span></span> |<span data-ttu-id="57d65-108">特定の状態を保証するアカウント名を示します。</span><span class="sxs-lookup"><span data-stu-id="57d65-108">Indicates the account name for which you want to ensure a specific state.</span></span> |
|---|---|
|<span data-ttu-id="57d65-109">UserName</span><span class="sxs-lookup"><span data-stu-id="57d65-109">UserName</span></span> |<span data-ttu-id="57d65-110">ファイルまたはディレクトリの状態を保証する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="57d65-110">Specifies the location where you want to ensure the state for a file or directory.</span></span> |
|<span data-ttu-id="57d65-111">FullName</span><span class="sxs-lookup"><span data-stu-id="57d65-111">FullName</span></span> |<span data-ttu-id="57d65-112">ユーザー アカウントに使用するフルネームを表す文字列。</span><span class="sxs-lookup"><span data-stu-id="57d65-112">A string that contains the full name to use for the user account.</span></span> |
|<span data-ttu-id="57d65-113">説明</span><span class="sxs-lookup"><span data-stu-id="57d65-113">Description</span></span> |<span data-ttu-id="57d65-114">ユーザー アカウントの説明。</span><span class="sxs-lookup"><span data-stu-id="57d65-114">The description for the user account.</span></span> |
|<span data-ttu-id="57d65-115">Password</span><span class="sxs-lookup"><span data-stu-id="57d65-115">Password</span></span> |<span data-ttu-id="57d65-116">Linux コンピューターの適切な形式でのユーザー パスワードのハッシュ。</span><span class="sxs-lookup"><span data-stu-id="57d65-116">The hash of the users password in the appropriate form for the Linux computer.</span></span> <span data-ttu-id="57d65-117">通常、これはソルト化ハッシュ SHA-256 または SHA-512 です。</span><span class="sxs-lookup"><span data-stu-id="57d65-117">Typically, this is a salted SHA-256, or SHA-512 hash.</span></span> <span data-ttu-id="57d65-118">Debian および Ubuntu Linux では、この値は、`mkpasswd` コマンドを使用して生成できます。</span><span class="sxs-lookup"><span data-stu-id="57d65-118">On Debian and Ubuntu Linux, this value can be generated with the `mkpasswd` command.</span></span> <span data-ttu-id="57d65-119">他の Linux ディストリビューションの場合は、Python の暗号ライブラリの crypt メソッドを使用してハッシュを生成できます。</span><span class="sxs-lookup"><span data-stu-id="57d65-119">For other Linux distros, the crypt method of Python's Crypt library can be used to generate the hash.</span></span> |
|<span data-ttu-id="57d65-120">無効</span><span class="sxs-lookup"><span data-stu-id="57d65-120">Disabled</span></span> |<span data-ttu-id="57d65-121">アカウントが有効かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="57d65-121">Indicates whether the account is enabled.</span></span> <span data-ttu-id="57d65-122">このアカウントを無効にするには、このプロパティを `$true` に設定し、有効にするには `$false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="57d65-122">Set this property to `$true` to ensure that this account is disabled, and set it to `$false` to ensure that it is enabled.</span></span> |
|<span data-ttu-id="57d65-123">PasswordChangeRequired</span><span class="sxs-lookup"><span data-stu-id="57d65-123">PasswordChangeRequired</span></span> |<span data-ttu-id="57d65-124">ユーザーがパスワードを変更できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="57d65-124">Indicates whether the user can change the password.</span></span> <span data-ttu-id="57d65-125">ユーザーがパスワードを変更できないようにするには、このプロパティを `$true` に設定し、ユーザーがパスワードを変更できるようにするには、`$false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="57d65-125">Set this property to `$true` to ensure that the user cannot change the password, and set it to `$false` to allow the user to change the password.</span></span> <span data-ttu-id="57d65-126">既定値は `$false` です。</span><span class="sxs-lookup"><span data-stu-id="57d65-126">The default value is `$false`.</span></span> <span data-ttu-id="57d65-127">このプロパティは、以前存在しなかったユーザー アカウントを作成するときにのみ評価されます。</span><span class="sxs-lookup"><span data-stu-id="57d65-127">This property is only evaluated if the user account did not exist previously and is being created.</span></span> |
|<span data-ttu-id="57d65-128">HomeDirectory</span><span class="sxs-lookup"><span data-stu-id="57d65-128">HomeDirectory</span></span> |<span data-ttu-id="57d65-129">ユーザーのホーム ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="57d65-129">The home directory for the user.</span></span> |
|<span data-ttu-id="57d65-130">GroupID</span><span class="sxs-lookup"><span data-stu-id="57d65-130">GroupID</span></span> |<span data-ttu-id="57d65-131">ユーザーのプライマリ グループ ID。</span><span class="sxs-lookup"><span data-stu-id="57d65-131">The primary group ID for the user.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="57d65-132">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="57d65-132">Common properties</span></span>

|<span data-ttu-id="57d65-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="57d65-133">Property</span></span> |<span data-ttu-id="57d65-134">説明</span><span class="sxs-lookup"><span data-stu-id="57d65-134">Description</span></span> |
|---|---|
|<span data-ttu-id="57d65-135">DependsOn</span><span class="sxs-lookup"><span data-stu-id="57d65-135">DependsOn</span></span> |<span data-ttu-id="57d65-136">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="57d65-136">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="57d65-137">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="57d65-137">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="57d65-138">Ensure</span><span class="sxs-lookup"><span data-stu-id="57d65-138">Ensure</span></span> |<span data-ttu-id="57d65-139">アカウントが存在するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="57d65-139">Specifies whether the account exists.</span></span> <span data-ttu-id="57d65-140">このアカウントの存在を保証するには、このプロパティを **Present** に設定し、アカウントが存在しないことを保証するには、**Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="57d65-140">Set this property to **Present** to ensure that the account exists, and set it to **Absent** to ensure that the account does not exist.</span></span> |

## <a name="example"></a><span data-ttu-id="57d65-141">例</span><span class="sxs-lookup"><span data-stu-id="57d65-141">Example</span></span>

<span data-ttu-id="57d65-142">次の例は、ユーザー "monuser" が存在し、グループ "DBusers" のメンバーであることを保証しています。</span><span class="sxs-lookup"><span data-stu-id="57d65-142">The following example ensures that the user "monuser" exists and is a member of the group "DBusers".</span></span>

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