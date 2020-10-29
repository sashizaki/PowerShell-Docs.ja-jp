---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: コンピューターに関する情報の収集
description: この記事では、WMI と CIM コマンドレットを使用して、コンピューターの構成に関する情報を収集する方法を示します。
ms.openlocfilehash: 5088960ab7c049085a9d7c05ec4571b6fd7e3545
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500591"
---
# <a name="collecting-information-about-computers"></a><span data-ttu-id="684ee-104">コンピューターに関する情報の収集</span><span class="sxs-lookup"><span data-stu-id="684ee-104">Collecting Information About Computers</span></span>

<span data-ttu-id="684ee-105">**CimCmdlets** モジュールのコマンドレットは、一般的なシステム管理タスクに最も重要なコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="684ee-105">Cmdlets from **CimCmdlets** module are the most important cmdlets for general system management tasks.</span></span> <span data-ttu-id="684ee-106">サブシステムの重要なすべての設定は、WMI を介して公開されています。</span><span class="sxs-lookup"><span data-stu-id="684ee-106">All critical subsystem settings are exposed through WMI.</span></span> <span data-ttu-id="684ee-107">さらに、WMI では、データは 1 つまたは複数の項目が集まったオブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="684ee-107">Furthermore, WMI treats data as objects that are in collections of one or more items.</span></span> <span data-ttu-id="684ee-108">Windows PowerShell の操作の対象もオブジェクトです。パイプラインを使用することにより、1 つまたは複数のオブジェクトを同じ方法で処理できます。このため、一般的な WMI アクセスにより、高度なタスクを最小限の労力で実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="684ee-108">Because Windows PowerShell also works with objects and has a pipeline that allows you to treat single or multiple objects in the same way, generic WMI access allows you to perform some advanced tasks with very little work.</span></span>

## <a name="listing-desktop-settings"></a><span data-ttu-id="684ee-109">デスクトップの設定を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="684ee-109">Listing Desktop Settings</span></span>

<span data-ttu-id="684ee-110">まず、ローカル コンピューターのデスクトップに関する情報を収集するコマンドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="684ee-110">We'll begin with a command that collects information about the desktops on the local computer.</span></span>

```powershell
Get-CimInstance -ClassName Win32_Desktop
```

<span data-ttu-id="684ee-111">このコマンドを実行すると、使用中であるかどうかに関係なく、すべてのデスクトップの情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="684ee-111">This returns information for all desktops, whether they are in use or not.</span></span>

> [!NOTE]
> <span data-ttu-id="684ee-112">WMI のクラスによっては、非常に詳しい情報が返されます。その WMI クラスのメタデータが含まれる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="684ee-112">Information returned by some WMI classes can be very detailed, and often include metadata about the WMI class.</span></span>

<span data-ttu-id="684ee-113">こうしたメタデータのプロパティには、通常、 **Cim** で始まる名前が付いているため、`Select-Object` を使用することでこれらのプロパティをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="684ee-113">Because most of these metadata properties have names that begin with **Cim** , you can filter the properties using `Select-Object`.</span></span> <span data-ttu-id="684ee-114">**-ExcludeProperty** パラメーターと値に "Cim\*" を指定します。</span><span class="sxs-lookup"><span data-stu-id="684ee-114">Specify the **-ExcludeProperty** parameter with "Cim\*" as the value.</span></span> <span data-ttu-id="684ee-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="684ee-115">For example:</span></span>

```powershell
Get-CimInstance -ClassName Win32_Desktop | Select-Object -ExcludeProperty "CIM*"
```

<span data-ttu-id="684ee-116">メタデータをフィルターで除外するには、パイプライン演算子 (|) を使用して、`Get-CimInstance` コマンドの結果を `Select-Object -ExcludeProperty "CIM*"` に渡します。</span><span class="sxs-lookup"><span data-stu-id="684ee-116">To filter out the metadata, use a pipeline operator (|) to send the results of the `Get-CimInstance` command to `Select-Object -ExcludeProperty "CIM*"`.</span></span>

## <a name="listing-bios-information"></a><span data-ttu-id="684ee-117">BIOS 情報を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="684ee-117">Listing BIOS Information</span></span>

<span data-ttu-id="684ee-118">WMI **Win32_BIOS** クラスは、ローカル コンピューターのシステム BIOS について、詳細な情報を凝縮して返します。</span><span class="sxs-lookup"><span data-stu-id="684ee-118">The WMI **Win32_BIOS** class returns fairly compact and complete information about the system BIOS on the local computer:</span></span>

```powershell
Get-CimInstance -ClassName Win32_BIOS
```

## <a name="listing-processor-information"></a><span data-ttu-id="684ee-119">プロセッサ情報を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="684ee-119">Listing Processor Information</span></span>

<span data-ttu-id="684ee-120">WMI の **Win32_Processor** クラスを使用すると (通常はフィルター処理を併用)、プロセッサ全般に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="684ee-120">You can retrieve general processor information by using WMI's **Win32_Processor** class, although you will likely want to filter the information:</span></span>

```powershell
Get-CimInstance -ClassName Win32_Processor | Select-Object -ExcludeProperty "CIM*"
```

<span data-ttu-id="684ee-121">**SystemType** プロパティを返すことで、プロセッサ ファミリの一般的な説明を表示できます。</span><span class="sxs-lookup"><span data-stu-id="684ee-121">For a generic description string of the processor family, you can just return the **SystemType** property:</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem | Select-Object -Property SystemType

SystemType
----------
X86-based PC
```

## <a name="listing-computer-manufacturer-and-model"></a><span data-ttu-id="684ee-122">コンピューターの製造元および型番を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="684ee-122">Listing Computer Manufacturer and Model</span></span>

<span data-ttu-id="684ee-123">コンピューターの型番情報も **Win32_ComputerSystem** から取得できます。</span><span class="sxs-lookup"><span data-stu-id="684ee-123">Computer model information is also available from **Win32_ComputerSystem** .</span></span> <span data-ttu-id="684ee-124">OEM データを取得するのであれば、標準の表示出力で十分です。フィルター処理は不要です。</span><span class="sxs-lookup"><span data-stu-id="684ee-124">The standard displayed output will not need any filtering to provide OEM data:</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem
```

```Output
Name PrimaryOwnerName Domain    TotalPhysicalMemory Model                   Manufacturer
---- ---------------- ------    ------------------- -----                   ------------
MyPC Jane Doe         WORKGROUP 804765696           DA243A-ABA 6415cl NA910 Compaq Presario 06
```

<span data-ttu-id="684ee-125">このようなコマンドからの出力結果はハードウェアから直接情報が取得されますが、詳しい情報は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="684ee-125">Your output from commands such as this, which return information directly from some hardware, is only as good as the data you have.</span></span> <span data-ttu-id="684ee-126">ハードウェアの製造元によって正しく構成されていないために利用できない情報もあります。</span><span class="sxs-lookup"><span data-stu-id="684ee-126">Some information is not correctly configured by hardware manufacturers and may therefore be unavailable.</span></span>

## <a name="listing-installed-hotfixes"></a><span data-ttu-id="684ee-127">インストールされている修正プログラムを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="684ee-127">Listing Installed Hotfixes</span></span>

<span data-ttu-id="684ee-128">インストールされているすべての修正プログラムを一覧表示するには **Win32_QuickFixEngineering** を使用します。</span><span class="sxs-lookup"><span data-stu-id="684ee-128">You can list all installed hotfixes by using **Win32_QuickFixEngineering** :</span></span>

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering
```

<span data-ttu-id="684ee-129">このクラスからは、次のような修正プログラムの一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="684ee-129">This class returns a list of hotfixes that looks like this:</span></span>

```Output
Source Description     HotFixID  InstalledBy   InstalledOn PSComputerName
------ -----------     --------  -----------   ----------- --------------
       Security Update KB4048951 Administrator 12/16/2017  .
```

<span data-ttu-id="684ee-130">より簡潔な出力を得るには、いくつかのプロパティを除外します。</span><span class="sxs-lookup"><span data-stu-id="684ee-130">For more succinct output, you may want to exclude some properties.</span></span> <span data-ttu-id="684ee-131">`Get-CimInstance` の **Property** パラメーターを使用して **HotFixID** だけを選ぶこともできますが、その場合は非常に多くの情報が返されます。既定では、すべてのメタデータが表示されるためです。</span><span class="sxs-lookup"><span data-stu-id="684ee-131">Although you can use the `Get-CimInstance`'s **Property** parameter to choose only the **HotFixID** , doing so will actually return more information, because all the metadata is displayed by default:</span></span>

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering -Property HotFixID
```

```Output
InstalledOn           :
Caption               :
Description           :
InstallDate           :
Name                  :
Status                :
CSName                :
FixComments           :
HotFixID              : KB4533002
InstalledBy           :
ServicePackInEffect   :
PSComputerName        :
CimClass              : root/cimv2:Win32_QuickFixEngineering
CimInstanceProperties : {Caption, Description, InstallDate, Name…}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
...
```

<span data-ttu-id="684ee-132">`Get-CimInstance` の **Property** パラメーターによって制限されるのは、WMI クラスのインスタンスから返されるプロパティです。PowerShell に返されるオブジェクトが制限されるわけではありません。実際、上の例を見ると、余分なデータが返されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="684ee-132">The additional data is returned, because the **Property** parameter in `Get-CimInstance` restricts the properties returned from WMI class instances, not the object returned to PowerShell.</span></span> <span data-ttu-id="684ee-133">出力結果を減らすためには、`Select-Object` を使用します。</span><span class="sxs-lookup"><span data-stu-id="684ee-133">To reduce the output, use `Select-Object`:</span></span>

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering -Property HotFixId | Select-Object -Property HotFixId
```

```Output
HotFixId
--------
KB4048951
```

## <a name="listing-operating-system-version-information"></a><span data-ttu-id="684ee-134">オペレーティング システムのバージョン情報を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="684ee-134">Listing Operating System Version Information</span></span>

<span data-ttu-id="684ee-135">**Win32_OperatingSystem** クラスのプロパティには、バージョンおよびサービス パックの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="684ee-135">The **Win32_OperatingSystem** class properties include version and service pack information.</span></span> <span data-ttu-id="684ee-136">これらのプロパティだけを明示的に選ぶことによって、バージョン情報の概要を **Win32_OperatingSystem** から取得できます。</span><span class="sxs-lookup"><span data-stu-id="684ee-136">You can explicitly select only these properties to get a version information summary from **Win32_OperatingSystem** :</span></span>

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem |
  Select-Object -Property BuildNumber,BuildType,OSType,ServicePackMajorVersion,ServicePackMinorVersion
```

<span data-ttu-id="684ee-137">`Select-Object` の **Property** パラメーターでは、ワイルドカードも使用できます。</span><span class="sxs-lookup"><span data-stu-id="684ee-137">You can also use wildcards with the `Select-Object`'s **Property** parameter.</span></span> <span data-ttu-id="684ee-138">ここでは **Build** または **ServicePack** で始まるすべてのプロパティを使用することが重要であるため、次のように短く記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="684ee-138">Because all the properties beginning with either **Build** or **ServicePack** are important to use here, we can shorten this to the following form:</span></span>

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem | Select-Object -Property Build*,OSType,ServicePack*
```

```Output
BuildNumber             : 18362
BuildType               : Multiprocessor Free
OSType                  : 18
ServicePackMajorVersion : 0
ServicePackMinorVersion : 0
```

## <a name="listing-local-users-and-owner"></a><span data-ttu-id="684ee-139">ローカル ユーザーと所有者を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="684ee-139">Listing Local Users and Owner</span></span>

<span data-ttu-id="684ee-140">ライセンスされたユーザー数、現在のユーザー数、所有者名など、ローカル ユーザーの全般的な情報は、 **Win32_OperatingSystem** クラスのプロパティを選択することによって取得できます。</span><span class="sxs-lookup"><span data-stu-id="684ee-140">Local general user information — number of licensed users, current number of users, and owner name — can be found with a selection of **Win32_OperatingSystem** class properties.</span></span> <span data-ttu-id="684ee-141">表示するプロパティを明示的に選ぶには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="684ee-141">You can explicitly select the properties to display like this:</span></span>

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem |
  Select-Object -Property NumberOfLicensedUsers,NumberOfUsers,RegisteredUser
```

<span data-ttu-id="684ee-142">これをワイルドカードで簡潔に記述するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="684ee-142">A more succinct version using wildcards is:</span></span>

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem | Select-Object -Property *user*
```

## <a name="getting-available-disk-space"></a><span data-ttu-id="684ee-143">使用可能なディスク領域を取得する</span><span class="sxs-lookup"><span data-stu-id="684ee-143">Getting Available Disk Space</span></span>

<span data-ttu-id="684ee-144">ローカル ドライブのディスク容量と空き領域を表示するには、Win32_LogicalDisk WMI クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="684ee-144">To see the disk space and free space for local drives, you can use the Win32_LogicalDisk WMI class.</span></span>
<span data-ttu-id="684ee-145">表示する必要があるのは、DriveType が 3 (WMI が固定ハード ディスクに使用する値) のインスタンスだけです。</span><span class="sxs-lookup"><span data-stu-id="684ee-145">You need to see only instances with a DriveType of 3 — the value WMI uses for fixed hard disks.</span></span>

```powershell
Get-CimInstance -ClassName Win32_LogicalDisk -Filter "DriveType=3"
```

```Output
DeviceID DriveType ProviderName VolumeName Size         FreeSpace   PSComputerName
-------- --------- ------------ ---------- ----         ---------   --------------
C:       3                      Local Disk 203912880128 65541357568 .
Q:       3                      New Volume 122934034432 44298250240 .
```

```powershell
Get-CimInstance -ClassName Win32_LogicalDisk -Filter "DriveType=3" |
  Measure-Object -Property FreeSpace,Size -Sum |
    Select-Object -Property Property,Sum
```

```Output
Property           Sum
--------           ---
FreeSpace 109839607808
Size      326846914560
```

## <a name="getting-logon-session-information"></a><span data-ttu-id="684ee-146">ログオン セッション情報を取得する</span><span class="sxs-lookup"><span data-stu-id="684ee-146">Getting Logon Session Information</span></span>

<span data-ttu-id="684ee-147">ユーザーに関連付けられたログオン セッションの全般的な情報は、 **Win32_LogonSession** WMI クラスを使って取得できます。</span><span class="sxs-lookup"><span data-stu-id="684ee-147">You can get general information about logon sessions associated with users through the **Win32_LogonSession** WMI class:</span></span>

```powershell
Get-CimInstance -ClassName Win32_LogonSession
```

## <a name="getting-the-user-logged-on-to-a-computer"></a><span data-ttu-id="684ee-148">コンピューターにログオンしたユーザーを取得する</span><span class="sxs-lookup"><span data-stu-id="684ee-148">Getting the User Logged on to a Computer</span></span>

<span data-ttu-id="684ee-149">特定のコンピューター システムにログオンしているユーザーを表示するには、Win32_ComputerSystem を使用します。</span><span class="sxs-lookup"><span data-stu-id="684ee-149">You can display the user logged on to a particular computer system using Win32_ComputerSystem.</span></span> <span data-ttu-id="684ee-150">このコマンドで返されるのは、システムのデスクトップにログオンしているユーザーだけです。</span><span class="sxs-lookup"><span data-stu-id="684ee-150">This command returns only the user logged on to the system desktop:</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -Property UserName
```

## <a name="getting-local-time-from-a-computer"></a><span data-ttu-id="684ee-151">コンピューターのローカル時刻を取得する</span><span class="sxs-lookup"><span data-stu-id="684ee-151">Getting Local Time from a Computer</span></span>

<span data-ttu-id="684ee-152">特定のコンピューターにおける現在のローカル時刻を取得するには、 **Win32_LocalTime** WMI クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="684ee-152">You can retrieve the current local time on a specific computer by using the **Win32_LocalTime** WMI class.</span></span>

```powershell
Get-CimInstance -ClassName Win32_LocalTime
```

```Output
Day            : 23
DayOfWeek      : 1
Hour           : 8
Milliseconds   :
Minute         : 52
Month          : 12
Quarter        : 4
Second         : 55
WeekInMonth    : 4
Year           : 2019
PSComputerName :
```

## <a name="displaying-service-status"></a><span data-ttu-id="684ee-153">サービスの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="684ee-153">Displaying Service Status</span></span>

<span data-ttu-id="684ee-154">特定のコンピューターを対象にすべてのサービスの状態を表示するには、ローカルで `Get-Service` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="684ee-154">To view the status of all services on a specific computer, you can locally use the `Get-Service` cmdlet.</span></span> <span data-ttu-id="684ee-155">リモート システムの場合は、 **Win32_Service** WMI クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="684ee-155">For remote systems, you can use the **Win32_Service** WMI class.</span></span> <span data-ttu-id="684ee-156">`Select-Object` を併用して結果をフィルター処理し、 **Status** 、 **Name** 、 **DisplayName** だけを抽出した場合は、`Get-Service` を実行した場合とほぼ同じ出力形式になります。</span><span class="sxs-lookup"><span data-stu-id="684ee-156">If you also use `Select-Object` to filter the results to **Status** , **Name** , and **DisplayName** , the output format will be almost identical to that from `Get-Service`:</span></span>

```powershell
Get-CimInstance -ClassName Win32_Service | Select-Object -Property Status,Name,DisplayName
```

<span data-ttu-id="684ee-157">非常に長い名前のサービスも存在します。こうしたサービスの名前全体を表示するには、`Format-Table` に **AutoSize** パラメーターと **Wrap** パラメーターを使用します。列幅が調整され、長い名前は切り詰められるのではなく折り返されます。</span><span class="sxs-lookup"><span data-stu-id="684ee-157">To allow the complete display of names for the occasional services with extremely long names, you may want to use `Format-Table` with the **AutoSize** and **Wrap** parameters, to optimize column width and allow long names to wrap instead of being truncated:</span></span>

```powershell
Get-CimInstance -ClassName Win32_Service | Format-Table -Property Status,Name,DisplayName -AutoSize -Wrap
```
