---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "コンピューターに関する情報の収集"
ms.assetid: 9e7b6a2d-34f7-4731-a92c-8b3382eb51bb
ms.openlocfilehash: c0b7ec9ed7d2b07c66d2b1cf3342f971d71da481
ms.sourcegitcommit: 74255f0b5f386a072458af058a15240140acb294
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2017
---
# <a name="collecting-information-about-computers"></a><span data-ttu-id="4dd9f-103">コンピューターに関する情報の収集</span><span class="sxs-lookup"><span data-stu-id="4dd9f-103">Collecting Information About Computers</span></span>
<span data-ttu-id="4dd9f-104">**Get-WmiObject** は、システム全般の管理タスクを行うための最も重要なコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-104">**Get-WmiObject** is the most important cmdlet for general system management tasks.</span></span> <span data-ttu-id="4dd9f-105">サブシステムの重要なすべての設定は、WMI を介して公開されています。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-105">All critical subsystem settings are exposed through WMI.</span></span> <span data-ttu-id="4dd9f-106">さらに、WMI では、データは 1 つまたは複数の項目が集まったオブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-106">Furthermore, WMI treats data as objects that are in collections of one or more items.</span></span> <span data-ttu-id="4dd9f-107">Windows PowerShell の操作の対象もオブジェクトです。パイプラインを使用することにより、1 つまたは複数のオブジェクトを同じ方法で処理できます。このため、一般的な WMI アクセスにより、高度なタスクを最小限の労力で実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-107">Because Windows PowerShell also works with objects and has a pipeline that allows you to treat single or multiple objects in the same way, generic WMI access allows you to perform some advanced tasks with very little work.</span></span>

<span data-ttu-id="4dd9f-108">以降、任意のコンピューターに対して **Get-WmiObject** を使用し、特定の情報を収集する例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-108">The following examples demonstrate how to collect specific information by using **Get-WmiObject** against an arbitrary computer.</span></span> <span data-ttu-id="4dd9f-109">**ComputerName** パラメーターの値には、ローカル コンピューターを表すドット (**.**) を指定しています。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-109">We specify the **ComputerName** parameter with the dot value (**.**), which represents the local computer.</span></span> <span data-ttu-id="4dd9f-110">WMI 経由でアクセス可能なコンピューターであれば、任意のコンピューターの名前または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-110">You can specify a name or IP address associated with any computer you can reach through WMI.</span></span> <span data-ttu-id="4dd9f-111">ローカル コンピューターに関する情報を取得する場合、**-ComputerName** は省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-111">To retrieve information about the local computer, you could omit the **-ComputerName.**</span></span>

### <a name="listing-desktop-settings"></a><span data-ttu-id="4dd9f-112">デスクトップの設定を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="4dd9f-112">Listing Desktop Settings</span></span>
<span data-ttu-id="4dd9f-113">まず、ローカル コンピューターのデスクトップに関する情報を収集するコマンドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-113">We'll begin with a command that collects information about the desktops on the local computer.</span></span>

```
Get-WmiObject -Class Win32_Desktop -ComputerName .
```

<span data-ttu-id="4dd9f-114">このコマンドを実行すると、使用中であるかどうかに関係なく、すべてのデスクトップの情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-114">This returns information for all desktops, whether they are in use or not.</span></span>

> [!NOTE]
> <span data-ttu-id="4dd9f-115">WMI のクラスによっては、非常に詳しい情報が返されます。その WMI クラスのメタデータが含まれる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-115">Information returned by some WMI classes can be very detailed, and often include metadata about the WMI class.</span></span> <span data-ttu-id="4dd9f-116">こうしたメタデータのプロパティには、通常、二重アンダースコアで始まる名前が付いているため、Select-Object を使用することでこれらのプロパティをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-116">Because most of these metadata properties have names that begin with a double underscore, you can filter the properties using Select-Object.</span></span> <span data-ttu-id="4dd9f-117">アルファベット文字で始まるプロパティだけを指定するには、Property 値として **[a-z]*** を使用します。次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-117">Specify only properties that begin with alphabetic characters by using **[a-z]*** as the Property value.</span></span> <span data-ttu-id="4dd9f-118">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-118">For example:</span></span>

```
Get-WmiObject -Class Win32_Desktop -ComputerName . | Select-Object -Property [a-z]*
```

<span data-ttu-id="4dd9f-119">メタデータをフィルターで除外するには、パイプライン演算子 (|) を使用して、Get-WmiObject コマンドの結果を **Select-Object -Property [a-z]*** に渡します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-119">To filter out the metadata, use a pipeline operator (|) to send the results of the Get-WmiObject command to **Select-Object -Property [a-z]***.</span></span>

### <a name="listing-bios-information"></a><span data-ttu-id="4dd9f-120">BIOS 情報を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="4dd9f-120">Listing BIOS Information</span></span>
<span data-ttu-id="4dd9f-121">WMI Win32_BIOS クラスは、ローカル コンピューターのシステム BIOS について、詳細な情報を凝縮して返します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-121">The WMI Win32_BIOS class returns fairly compact and complete information about the system BIOS on the local computer:</span></span>

```
Get-WmiObject -Class Win32_BIOS -ComputerName .
```

### <a name="listing-processor-information"></a><span data-ttu-id="4dd9f-122">プロセッサ情報を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="4dd9f-122">Listing Processor Information</span></span>
<span data-ttu-id="4dd9f-123">WMI の **Win32_Processor** クラスを使用すると (通常はフィルター処理を併用)、プロセッサ全般に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-123">You can retrieve general processor information by using WMI's **Win32_Processor** class, although you will likely want to filter the information:</span></span>

```
Get-WmiObject -Class Win32_Processor -ComputerName . | Select-Object -Property [a-z]*
```

<span data-ttu-id="4dd9f-124">**SystemType** プロパティを返すことで、プロセッサ ファミリの一般的な説明を表示できます。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-124">For a generic description string of the processor family, you can just return the **SystemType** property:</span></span>

```
PS> Get-WmiObject -Class Win32_ComputerSystem -ComputerName . | Select-Object -Property SystemType
SystemType
----------
X86-based PC
```

### <a name="listing-computer-manufacturer-and-model"></a><span data-ttu-id="4dd9f-125">コンピューターの製造元および型番を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="4dd9f-125">Listing Computer Manufacturer and Model</span></span>
<span data-ttu-id="4dd9f-126">コンピューターの型番情報も **Win32_ComputerSystem** から取得できます。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-126">Computer model information is also available from **Win32_ComputerSystem**.</span></span> <span data-ttu-id="4dd9f-127">OEM データを取得するのであれば、標準の表示出力で十分です。フィルター処理は不要です。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-127">The standard displayed output will not need any filtering to provide OEM data:</span></span>

```
PS> Get-WmiObject -Class Win32_ComputerSystem
Domain              : WORKGROUP
Manufacturer        : Compaq Presario 06
Model               : DA243A-ABA 6415cl NA910
Name                : MyPC
PrimaryOwnerName    : Jane Doe
TotalPhysicalMemory : 804765696
```

<span data-ttu-id="4dd9f-128">このようなコマンドからの出力結果はハードウェアから直接情報が取得されますが、詳しい情報は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-128">Your output from commands such as this, which return information directly from some hardware, is only as good as the data you have.</span></span> <span data-ttu-id="4dd9f-129">ハードウェアの製造元によって正しく構成されていないために利用できない情報もあります。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-129">Some information is not correctly configured by hardware manufacturers and may therefore be unavailable.</span></span>

### <a name="listing-installed-hotfixes"></a><span data-ttu-id="4dd9f-130">インストールされている修正プログラムを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="4dd9f-130">Listing Installed Hotfixes</span></span>
<span data-ttu-id="4dd9f-131">インストールされているすべての修正プログラムを一覧表示するには **Win32_QuickFixEngineering** を使用します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-131">You can list all installed hotfixes by using **Win32_QuickFixEngineering**:</span></span>

```
Get-WmiObject -Class Win32_QuickFixEngineering -ComputerName .
```

<span data-ttu-id="4dd9f-132">このクラスからは、次のような修正プログラムの一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-132">This class returns a list of hotfixes that looks like this:</span></span>

```
Description         : Update for Windows XP (KB910437)
FixComments         : Update
HotFixID            : KB910437
Install Date        :
InstalledBy         : Administrator
InstalledOn         : 12/16/2005
Name                :
ServicePackInEffect : SP3
Status              :
```

<span data-ttu-id="4dd9f-133">より簡潔な出力を得るには、いくつかのプロパティを除外します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-133">For more succinct output, you may want to exclude some properties.</span></span> <span data-ttu-id="4dd9f-134">**Get-WmiObject Property** パラメーターを使用して **HotFixID** だけを選ぶこともできますが、その場合は非常に多くの情報が返されます。既定では、すべてのメタデータが表示されるためです。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-134">Although you can use the **Get-WmiObject's Property** parameter to choose only the **HotFixID**, doing so will actually return more information, because all the metadata is displayed by default:</span></span>

```
PS> Get-WmiObject -Class Win32_QuickFixEngineering -ComputerName . -Property HotFixID
HotFixID         : KB910437
__GENUS          : 2
__CLASS          : Win32_QuickFixEngineering
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
```

<span data-ttu-id="4dd9f-135">**Get-WmiObject** の Property パラメーターによって制限されるのは、WMI クラスのインスタンスから返されるプロパティです。Windows PowerShell に返されるオブジェクトが制限されるわけではありません。実際、上の例を見ると、余分なデータが返されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-135">The additional data is returned, because the Property parameter in **Get-WmiObject** restricts the properties returned from WMI class instances, not the object returned to Windows PowerShell.</span></span> <span data-ttu-id="4dd9f-136">出力結果を減らすためには、**Select-Object** を使用します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-136">To reduce the output, use **Select-Object**:</span></span>

```
PS> Get-WmiObject -Class Win32_QuickFixEngineering -ComputerName . -Property Hot
FixId | Select-Object -Property HotFixId
HotFixId
--------
KB910437
```

### <a name="listing-operating-system-version-information"></a><span data-ttu-id="4dd9f-137">オペレーティング システムのバージョン情報を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="4dd9f-137">Listing Operating System Version Information</span></span>
<span data-ttu-id="4dd9f-138">**Win32_OperatingSystem** クラスのプロパティには、バージョンおよびサービス パックの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-138">The **Win32_OperatingSystem** class properties include version and service pack information.</span></span> <span data-ttu-id="4dd9f-139">これらのプロパティだけを明示的に選ぶことによって、バージョン情報の概要を **Win32_OperatingSystem** から取得できます。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-139">You can explicitly select only these properties to get a version information summary from **Win32_OperatingSystem**:</span></span>

```
Get-WmiObject -Class Win32_OperatingSystem -ComputerName . | Select-Object -Property BuildNumber,BuildType,OSType,ServicePackMajorVersion,ServicePackMinorVersion
```

<span data-ttu-id="4dd9f-140">**Select-Object Property** パラメーターでは、ワイルドカードも使用できます。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-140">You can also use wildcards with the **Select-Object's Property** parameter.</span></span> <span data-ttu-id="4dd9f-141">ここでは **Build** または **ServicePack** で始まるすべてのプロパティを使用することが重要であるため、次のように短く記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-141">Because all the properties beginning with either **Build** or **ServicePack** are important to use here, we can shorten this to the following form:</span></span>

```
PS> Get-WmiObject -Class Win32_OperatingSystem -ComputerName . | Select-Object -Property Build*,OSType,ServicePack*

BuildNumber             : 2600
BuildType               : Uniprocessor Free
OSType                  : 18
ServicePackMajorVersion : 2
ServicePackMinorVersion : 0
```

### <a name="listing-local-users-and-owner"></a><span data-ttu-id="4dd9f-142">ローカル ユーザーと所有者を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="4dd9f-142">Listing Local Users and Owner</span></span>
<span data-ttu-id="4dd9f-143">ライセンスされたユーザー数、現在のユーザー数、所有者名など、ローカル ユーザーの全般的な情報は、**Win32_OperatingSystem** のプロパティを選択することによって取得できます。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-143">Local general user information—number of licensed users, current number of users, and owner name—can be found with a selection of **Win32_OperatingSystem** properties.</span></span> <span data-ttu-id="4dd9f-144">表示するプロパティを明示的に選ぶには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-144">You can explicitly select the properties to display like this:</span></span>

```
Get-WmiObject -Class Win32_OperatingSystem -ComputerName . | Select-Object -Property NumberOfLicensedUsers,NumberOfUsers,RegisteredUser
```

<span data-ttu-id="4dd9f-145">これをワイルドカードで簡潔に記述するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-145">A more succinct version using wildcards is:</span></span>

```
Get-WmiObject -Class Win32_OperatingSystem -ComputerName . | Select-Object -Property *user*
```

### <a name="getting-available-disk-space"></a><span data-ttu-id="4dd9f-146">使用可能なディスク領域を取得する</span><span class="sxs-lookup"><span data-stu-id="4dd9f-146">Getting Available Disk Space</span></span>
<span data-ttu-id="4dd9f-147">ローカル ドライブのディスク容量と空き領域を表示するには、WMI Win32_LogicalDisk クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-147">To see the disk space and free space for local drives, you can use the WMI Win32_LogicalDisk class.</span></span> <span data-ttu-id="4dd9f-148">表示する必要があるのは、DriveType が 3 (WMI が固定ハード ディスクに使用する値) のドライブだけです。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-148">You need to see only instances with a DriveType of 3—the value WMI uses for fixed hard disks.</span></span>

```
Get-WmiObject -Class Win32_LogicalDisk -Filter "DriveType=3" -ComputerName .

DeviceID     : C:
DriveType    : 3
ProviderName :
FreeSpace    : 65541357568
Size         : 203912880128
VolumeName   : Local Disk

DeviceID     : Q:
DriveType    : 3
ProviderName :
FreeSpace    : 44298250240
Size         : 122934034432
VolumeName   : New Volume

Get-WmiObject -Class Win32_LogicalDisk -Filter "DriveType=3" -ComputerName . | Measure-Object -Property FreeSpace,Size -Sum | Select-Object -Property Property,Sum
```

### <a name="getting-logon-session-information"></a><span data-ttu-id="4dd9f-149">ログオン セッション情報を取得する</span><span class="sxs-lookup"><span data-stu-id="4dd9f-149">Getting Logon Session Information</span></span>
<span data-ttu-id="4dd9f-150">ユーザーに関連付けられたログオン セッションの全般的な情報は、WMI Win32_LogonSession クラスを使って取得できます。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-150">You can get general information about logon sessions associated with users through the WMI Win32_LogonSession class:</span></span>

```
Get-WmiObject -Class Win32_LogonSession -ComputerName .
```

### <a name="getting-the-user-logged-on-to-a-computer"></a><span data-ttu-id="4dd9f-151">コンピューターにログオンしたユーザーを取得する</span><span class="sxs-lookup"><span data-stu-id="4dd9f-151">Getting the User Logged on to a Computer</span></span>
<span data-ttu-id="4dd9f-152">特定のコンピューター システムにログオンしているユーザーを表示するには、Win32_ComputerSystem を使用します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-152">You can display the user logged on to a particular computer system using Win32_ComputerSystem.</span></span> <span data-ttu-id="4dd9f-153">このコマンドで返されるのは、システムのデスクトップにログオンしているユーザーだけです。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-153">This command returns only the user logged on to the system desktop:</span></span>

```
Get-WmiObject -Class Win32_ComputerSystem -Property UserName -ComputerName .
```

### <a name="getting-local-time-from-a-computer"></a><span data-ttu-id="4dd9f-154">コンピューターのローカル時刻を取得する</span><span class="sxs-lookup"><span data-stu-id="4dd9f-154">Getting Local Time from a Computer</span></span>
<span data-ttu-id="4dd9f-155">特定のコンピューターにおける現在のローカル時刻を取得するには、WMI Win32_LocalTime クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-155">You can retrieve the current local time on a specific computer by using the WMI Win32_LocalTime class.</span></span> <span data-ttu-id="4dd9f-156">このクラスでは、すべてのメタデータが既定で表示されるため、必要に応じて、**Select-Object** を使ってフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-156">Because this class by default displays all metadata, you may want to filter it using **Select-Object**:</span></span>

```
PS> Get-WmiObject -Class Win32_LocalTime -ComputerName . | Select-Object -Property [a-z]*

Day          : 15
DayOfWeek    : 4
Hour         : 12
Milliseconds :
Minute       : 11
Month        : 6
Quarter      : 2
Second       : 52
WeekInMonth  : 3
Year         : 2006
```

### <a name="displaying-service-status"></a><span data-ttu-id="4dd9f-157">サービスの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="4dd9f-157">Displaying Service Status</span></span>
<span data-ttu-id="4dd9f-158">前述のように、特定のコンピューターを対象に、すべてのサービスの状態を表示するには、ローカルで **Get-Service** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-158">To view the status of all services on a specific computer, you can locally use the **Get-Service** cmdlet as mentioned earlier.</span></span> <span data-ttu-id="4dd9f-159">リモート システムの場合は、WMI Win32_Service クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-159">For remote systems, you can use the WMI Win32_Service class.</span></span> <span data-ttu-id="4dd9f-160">**Select-Object** を併用して結果をフィルター処理し、**Status**、**Name**、**DisplayName** だけを抽出した場合は、**Get-Service** を実行した場合とほぼ同じ出力形式になります。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-160">If you also use **Select-Object** to filter the results to **Status**, **Name**, and **DisplayName**, the output format will be almost identical to that from **Get-Service**:</span></span>

```
Get-WmiObject -Class Win32_Service -ComputerName . | Select-Object -Property Status,Name,DisplayName
```

<span data-ttu-id="4dd9f-161">非常に長い名前のサービスも存在します。こうしたサービスの名前全体を表示するには、**Format-Table** に **AutoSize** パラメーターと **Wrap** パラメーターを使用します。列幅が調整され、長い名前は切り詰められるのではなく折り返されます。</span><span class="sxs-lookup"><span data-stu-id="4dd9f-161">To allow the complete display of names for the occasional services with extremely long names, you may want to use **Format-Table** with the **AutoSize** and **Wrap** parameters, to optimize column width and allow long names to wrap instead of being truncated:</span></span>

```
Get-WmiObject -Class Win32_Service -ComputerName . | Format-Table -Property Status,Name,DisplayName -AutoSize -Wrap
```

