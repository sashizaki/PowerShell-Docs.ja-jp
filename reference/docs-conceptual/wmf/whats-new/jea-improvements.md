---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
title: Just Enough Administration (JEA) の強化
ms.openlocfilehash: 847ae92a6225023bcd0ee3dfe7c7058bdc356836
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71147602"
---
# <a name="improvements-to-just-enough-administration-jea"></a><span data-ttu-id="92a87-103">Just Enough Administration (JEA) の強化</span><span class="sxs-lookup"><span data-stu-id="92a87-103">Improvements to Just Enough Administration (JEA)</span></span>

<span data-ttu-id="92a87-104">Just Enough Administration は、PowerShell のリモート処理によるロールベースの管理を可能にする WMF 5.0 の新機能です。</span><span class="sxs-lookup"><span data-stu-id="92a87-104">Just Enough Administration is a new feature in WMF 5.0 that enables role-based administration through PowerShell remoting.</span></span> <span data-ttu-id="92a87-105">非管理者が特定のコマンド、スクリプト、および実行可能ファイルを管理者として実行できるようにすることで、既存の制約付きエンドポイント インフラストラクチャを拡張します。</span><span class="sxs-lookup"><span data-stu-id="92a87-105">It extends the existing constrained endpoint infrastructure by allowing non-administrators to run specific commands, scripts, and executables as an administrator.</span></span> <span data-ttu-id="92a87-106">これにより、環境における完全な権限を持つ管理者の数を削減し、セキュリティを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="92a87-106">This enables you to reduce the number of full administrators in your environment and improve security.</span></span>

## <a name="constrained-file-copy-tofrom-jea-endpoints"></a><span data-ttu-id="92a87-107">JEA エンドポイントとの間の制約付きのファイル コピー</span><span class="sxs-lookup"><span data-stu-id="92a87-107">Constrained file copy to/from JEA endpoints</span></span>

<span data-ttu-id="92a87-108">JEA エンドポイントとの間でファイルをリモートでコピーできるようになりました。接続ユーザーはシステム上のファイルを "*どれでも*" コピーできるわけではないので安心することができます。</span><span class="sxs-lookup"><span data-stu-id="92a87-108">You can now remotely copy files to/from a JEA endpoint and be assured that the connecting user can't copy just *any* file on your system.</span></span> <span data-ttu-id="92a87-109">これは、接続ユーザー用のユーザー ドライブをマウントするよう PSSC ファイルを構成することによって可能になります。</span><span class="sxs-lookup"><span data-stu-id="92a87-109">This is possible by configuring your PSSC file to mount a user drive for connecting users.</span></span> <span data-ttu-id="92a87-110">ユーザー ドライブは、各接続ユーザーに固有の新しい PSDrive であり、複数のセッションにわたって保持されます。</span><span class="sxs-lookup"><span data-stu-id="92a87-110">The user drive is a new PSDrive that is unique to each connecting user and persists across sessions.</span></span> <span data-ttu-id="92a87-111">`Copy-Item` を使用して JEA セッションとの間でファイルのコピーを行うと、該当するユーザー ドライブへのアクセスしか許可しないように制約が課せられます。</span><span class="sxs-lookup"><span data-stu-id="92a87-111">When `Copy-Item` is used to copy files to or from a JEA session, it is constrained to only allow access to the user drive.</span></span> <span data-ttu-id="92a87-112">その他の PSDrive ファイルへのコピーを試みると失敗します。</span><span class="sxs-lookup"><span data-stu-id="92a87-112">Attempts to copy files to any other PSDrive will fail.</span></span>

<span data-ttu-id="92a87-113">JEA セッションの構成ファイルで、ユーザー ドライブを設定するには、次の新しいフィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="92a87-113">To set up the user drive in your JEA session configuration file, use the following new fields:</span></span>

```powershell
MountUserDrive = $true
UserDriveMaximumSize = 10485760    # 10 MB
```

<span data-ttu-id="92a87-114">ユーザー ドライブをバッキングするフォルダーが "`$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\DOMAIN_USER`" に作成されます。</span><span class="sxs-lookup"><span data-stu-id="92a87-114">The folder backing the user drive will be created at `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\DOMAIN_USER`</span></span>

<span data-ttu-id="92a87-115">ユーザー ドライブを公開するように構成された JEA エンドポイントとの間で、ユーザー ドライブを使用してファイルのコピーを行うには、`-ToSession` で `-FromSession` および `Copy-Item` パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="92a87-115">To utilize the user drive and copy files to/from a JEA endpoint configured to expose the User drive, use the `-ToSession` and `-FromSession` parameters on `Copy-Item`.</span></span>

```powershell
# Connect to the JEA endpoint
$jeasession = New-PSSession -ComputerName 'srv01' -ConfigurationName 'UserDemo'

# Copy a file in the local folder to the remote machine.
# Note: you cannot specify the file name or subfolder on the remote machine.
# You must exactly type "User:"
Copy-Item -Path .\SampleFile.txt -Destination User: -ToSession $jeasession

# Copy the file back from the remote machine to your local machine
Copy-Item -Path User:\SampleFile.txt -Destination . -FromSession $jeasession
```

<span data-ttu-id="92a87-116">ユーザー ドライブに格納されたデータを処理して、ロール機能ファイル内のユーザーがそれらを使用できるようにするためのカスタム関数を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="92a87-116">You can then write custom functions to process the data stored in the user drive and make those available to users in your Role Capability file.</span></span>

## <a name="support-for-group-managed-service-accounts"></a><span data-ttu-id="92a87-117">グループの管理されたサービス アカウントのサポート</span><span class="sxs-lookup"><span data-stu-id="92a87-117">Support for Group Managed Service Accounts</span></span>

<span data-ttu-id="92a87-118">場合によって、JEA セッションでユーザーが実行する必要があるタスクは、ローカル コンピューター以外のリソースにアクセスすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="92a87-118">In some cases, a task a user needs to perform in a JEA session may need to access resources beyond the local machine.</span></span> <span data-ttu-id="92a87-119">JEA セッションが仮想アカウントを使用するように構成されている場合、そのようなリソースへのアクセスの試みは、仮想アカウントまたは接続ユーザーからではなく、ローカル コンピューターの ID からのアクセスのように見えます。</span><span class="sxs-lookup"><span data-stu-id="92a87-119">When a JEA session is configured to use a virtual account, any attempt to reach such resources will appear to come from the local machine's identity, not the virtual account or connected user.</span></span> <span data-ttu-id="92a87-120">TP5 では、[[グループの管理されたサービス アカウント]](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj128431\(v=ws.11\)) というコンテキストの下で JEA の実行をサポートするようにしたことで、ドメイン ID を使ってネットワーク リソースにアクセスすることがずっと簡単になりました。</span><span class="sxs-lookup"><span data-stu-id="92a87-120">In TP5, we have enabled support for running JEA under the context of a [Group Managed Service Account](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj128431\(v=ws.11\)), making it much easier to access network resources by using a domain identity.</span></span>

<span data-ttu-id="92a87-121">JEA セッションを、gMSA アカウントの下で実行されるように構成するには、PSSC ファイルで次の新しいキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="92a87-121">To configure a JEA session to run under a gMSA account, use the following new key in your PSSC file:</span></span>

```powershell
# Provide the name of your gMSA account here (don't include a trailing $)
# The local machine must be privileged to use this gMSA in Active Directory
GroupManagedServiceAccount = 'myGMSAforJEA'

# You cannot configure a JEA endpoint to use both a gMSA and virtual account
# You can leave the RunAsVirtualAccount field commented out or explicitly set it to false
RunAsVirtualAccount = $false
```

> [!NOTE]
> <span data-ttu-id="92a87-122">グループの管理されたサービス アカウントでは、仮想アカウントの分離または限定的な範囲を許容していません。</span><span class="sxs-lookup"><span data-stu-id="92a87-122">Group Managed Service Accounts do not afford the isolation or limited scope of virtual accounts.</span></span>
> <span data-ttu-id="92a87-123">接続ユーザーはすべて同じ gMSA ID を共有することになります。この ID は企業全体を対象とするアクセス許可を持つ場合もあります。</span><span class="sxs-lookup"><span data-stu-id="92a87-123">Every connecting user will share the same gMSA identity, which may have permissions across your entire enterprise.</span></span> <span data-ttu-id="92a87-124">gMSA の使用を選択する場合は細心の注意を払ってください。可能であればローカル コンピューターに限定された仮想アカウントを常に優先してください。</span><span class="sxs-lookup"><span data-stu-id="92a87-124">Be very careful when selecting to use a gMSA, and always prefer virtual accounts which are limited to the local machine when possible.</span></span>

## <a name="conditional-access-policies"></a><span data-ttu-id="92a87-125">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="92a87-125">Conditional access policies</span></span>

<span data-ttu-id="92a87-126">あるユーザーがシステムの管理を目的としてシステムに接続したときにその人が実行できる操作を制限する場合に JEA は便利です。しかし、だれかが JEA を使用できる*タイミング*を制限したい場合はどうするのですか?</span><span class="sxs-lookup"><span data-stu-id="92a87-126">JEA is great at limiting what someone can do when they've connected to a system to manage it, but what if you also want to limit *when* someone can use JEA?</span></span> <span data-ttu-id="92a87-127">ユーザーが JEA セッションを確立するときに属する必要があるセキュリティ グループを指定できるように、セッション構成ファイル (.pssc) に構成オプションを追加しました。</span><span class="sxs-lookup"><span data-stu-id="92a87-127">We have added configuration options into the session configuration files (.pssc) to let you specify security groups to which a user must belong in order to establish a JEA session.</span></span> <span data-ttu-id="92a87-128">環境内にジャスト イン タイム (JIT) システムが搭載されていて、高い権限を持つ JEA エンドポイントにアクセスする前にユーザーに自分の権限を昇格させる必要があるとき、このオプションは特に有用です。</span><span class="sxs-lookup"><span data-stu-id="92a87-128">This is especially helpful if you have a Just In Time (JIT) system in your environment, and want to make your users elevate their privileges before accessing a highly-privileged JEA endpoint.</span></span>

<span data-ttu-id="92a87-129">PSSC ファイル内の新しい *RequiredGroups* フィールドを使用すると、ユーザーが JEA に接続できるかどうかを判断するロジックを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="92a87-129">The new *RequiredGroups* field in the PSSC file allows you to specify the logic to determine if a user can connect to JEA.</span></span> <span data-ttu-id="92a87-130">このロジックでは、ルールを構築するために "And" キーと "Or" キーを使用するハッシュ テーブル (必要に応じて入れ子になっている) を指定します。</span><span class="sxs-lookup"><span data-stu-id="92a87-130">It consists of specifying a hashtable (optionally nested) that uses the 'And' and 'Or' keys to construct your rules.</span></span> <span data-ttu-id="92a87-131">このフィールドの使用方法について、次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="92a87-131">Here are some examples of how to use this field:</span></span>

```powershell
# Example 1: Connecting users must belong to a security group called "elevated-jea"
RequiredGroups = @{ And = 'elevated-jea' }

# Example 2: Connecting users must have signed on with 2 factor authentication or a smart card
# The 2 factor authentication group name is "2FA-logon" and the smart card group name is "smartcard-logon"
RequiredGroups = @{ Or = '2FA-logon', 'smartcard-logon' }

# Example 3: Connecting users must elevate into "elevated-jea" with their JIT system and have logged on with 2FA or a smart card
RequiredGroups = @{ And = 'elevated-jea', @{ Or = '2FA-logon', 'smartcard-logon' }}
```

## <a name="fixed-virtual-accounts-are-now-supported-on-windows-server-2008-r2"></a><span data-ttu-id="92a87-132">固定: Windows Server 2008 R2 で仮想アカウントがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="92a87-132">Fixed: Virtual accounts are now supported on Windows Server 2008 R2</span></span>

<span data-ttu-id="92a87-133">WMF 5.1 では、Windows Server 2008 R2 で仮想アカウントを使用できるようになりました。これにより、Windows Server 2008 R2 - 2016 にわたり一貫した構成と機能の類似性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="92a87-133">In WMF 5.1, you are now able to use virtual accounts on Windows Server 2008 R2, enabling consistent configurations and feature parity across Windows Server 2008 R2 - 2016.</span></span> <span data-ttu-id="92a87-134">Windows 7 で JEA を使用する場合、仮想アカウントはまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="92a87-134">Virtual accounts remain unsupported when using JEA on Windows 7.</span></span>