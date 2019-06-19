---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: WMI オブジェクトの取得 (Get-WmiObject)
ms.openlocfilehash: 93276ce12135342af2d6f238976e65e5d8bdde7a
ms.sourcegitcommit: a6f13c16a535acea279c0ddeca72f1f0d8a8ce4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67030217"
---
# <a name="getting-wmi-objects-get-wmiobject"></a><span data-ttu-id="9ef4b-103">WMI オブジェクトの取得 (Get-WmiObject)</span><span class="sxs-lookup"><span data-stu-id="9ef4b-103">Getting WMI Objects (Get-WmiObject)</span></span>

## <a name="getting-wmi-objects-get-wmiobject"></a><span data-ttu-id="9ef4b-104">WMI オブジェクトの取得 (Get-WmiObject)</span><span class="sxs-lookup"><span data-stu-id="9ef4b-104">Getting WMI Objects (Get-WmiObject)</span></span>

<span data-ttu-id="9ef4b-105">Windows Management Instrumentation (WMI) は、Windows システム管理のための中核となるテクノロジであり、幅広い種類の情報を一貫した方法で公開します。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-105">Windows Management Instrumentation (WMI) is a core technology for Windows system administration because it exposes a wide range of information in a uniform manner.</span></span> <span data-ttu-id="9ef4b-106">WMI によって可能になるタスクが非常に多いことから、WMI オブジェクトにアクセスするための Windows PowerShell コマンドレットである **Get-WmiObject** は、実際の作業を行うための最も便利なコマンドレットの 1 つと言えます。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-106">Because of how much WMI makes possible, the Windows PowerShell cmdlet for accessing WMI objects, **Get-WmiObject**, is one of the most useful for doing real work.</span></span> <span data-ttu-id="9ef4b-107">ここでは、Get-WmiObject を使って WMI オブジェクトにアクセスする方法と、WMI オブジェクトを使って特定の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-107">We are going to discuss how to use Get-WmiObject to access WMI objects and then how to use WMI objects to do specific things.</span></span>

### <a name="listing-wmi-classes"></a><span data-ttu-id="9ef4b-108">WMI クラスの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="9ef4b-108">Listing WMI Classes</span></span>

<span data-ttu-id="9ef4b-109">WMI のほとんどのユーザーが直面する最初の問題は、WMI で何ができるかを調べることです。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-109">The first problem most WMI users encounter is trying to find out what can be done with WMI.</span></span> <span data-ttu-id="9ef4b-110">WMI クラスは、管理できるリソースを記述しています。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-110">WMI classes describe the resources that can be managed.</span></span> <span data-ttu-id="9ef4b-111">何百もの WMI クラスがあり、その中には数十個のプロパティを持つクラスもあります。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-111">There are hundreds of WMI classes, some of which contain dozens of properties.</span></span>

<span data-ttu-id="9ef4b-112">この問題に対処するため、**Get-WmiObject** では WMI を探索可能にしました。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-112">**Get-WmiObject** addresses this problem by making WMI discoverable.</span></span> <span data-ttu-id="9ef4b-113">ローカル コンピューター上で使える WMI クラスの一覧を取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-113">You can get a list of the WMI classes available on the local computer by typing:</span></span>

```
PS> Get-WmiObject -List

__SecurityRelatedClass                  __NTLMUser9X
__PARAMETERS                            __SystemSecurity
__NotifyStatus                          __ExtendedStatus
Win32_PrivilegesStatus                  Win32_TSNetworkAdapterSettingError
Win32_TSRemoteControlSettingError       Win32_TSEnvironmentSettingError
...
```

<span data-ttu-id="9ef4b-114">同じ情報をリモート コンピューターから取得するには、次のように、ComputerName パラメーターにコンピューター名や IP アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-114">You can retrieve the same information from a remote computer by using the ComputerName parameter, specifying a computer name or IP address:</span></span>

```
PS> Get-WmiObject -List -ComputerName 192.168.1.29

__SystemClass                           __NAMESPACE
__Provider                              __Win32Provider
__ProviderRegistration                  __ObjectProviderRegistration
...
```

<span data-ttu-id="9ef4b-115">リモート コンピューターから返されるクラスの一覧は、そのコンピューターで実行されている特定のオペレーティング システムや、インストールされているアプリケーションによって追加された特定の WMI 拡張機能に応じて異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-115">The class listing returned by remote computers may vary due to the specific operating system the computer is running and the particular WMI extensions added by installed applications.</span></span>

> [!NOTE]
> <span data-ttu-id="9ef4b-116">Get-WmiObject を使ってリモート コンピューターに接続するときは、リモート コンピューターで WMI が実行されている必要があり、既定の構成の場合、接続に使うアカウントがリモート コンピューターのローカル管理者グループに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-116">When using Get-WmiObject to connect to a remote computer, the remote computer must be running WMI and, under the default configuration, the account you are using must be in the local administrators group on the remote computer.</span></span> <span data-ttu-id="9ef4b-117">リモート システムに Windows PowerShell をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-117">The remote system does not need to have Windows PowerShell installed.</span></span> <span data-ttu-id="9ef4b-118">そのため、WMI が利用可能であれば、Windows PowerShell を実行していないオペレーティング システムであっても管理できます。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-118">This allows you to administer operating systems that are not running Windows PowerShell, but do have WMI available.</span></span>

<span data-ttu-id="9ef4b-119">また、ローカル システムに接続するときに、コンピューター名を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-119">You can even include the ComputerName when connecting to the local system.</span></span> <span data-ttu-id="9ef4b-120">ローカル コンピューターの名前、IP アドレス (またはループバック アドレス 127.0.0.1)、WMI スタイル '.' をコンピューター名として使うことができます。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-120">You can use the local computer's name, its IP address (or the loopback address 127.0.0.1), or the WMI-style '.' as the computer name.</span></span> <span data-ttu-id="9ef4b-121">IP アドレスが 192.168.1.90 で、Admin01 という名前のコンピューターで Windows PowerShell を実行している場合、次のコマンドはそのコンピューターのすべての WMI クラスの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-121">If you are running Windows PowerShell on a computer named Admin01 with IP address 192.168.1.90, the following commands will all return the WMI class listing for that computer:</span></span>

```powershell
Get-WmiObject -List
Get-WmiObject -List -ComputerName .
Get-WmiObject -List -ComputerName Admin01
Get-WmiObject -List -ComputerName 192.168.1.90
Get-WmiObject -List -ComputerName 127.0.0.1
Get-WmiObject -List -ComputerName localhost
```

<span data-ttu-id="9ef4b-122">Get-WmiObject は、既定では root/cimv2 名前空間を使います。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-122">Get-WmiObject uses the root/cimv2 namespace by default.</span></span> <span data-ttu-id="9ef4b-123">別の WMI 名前空間を指定する場合は、**Namespace** パラメーターを使って、対応する名前空間のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-123">If you want to specify another WMI namespace, use the **Namespace** parameter and specify the corresponding namespace path:</span></span>

```
PS> Get-WmiObject -List -ComputerName 192.168.1.29 -Namespace root

__SystemClass                           __NAMESPACE
__Provider                              __Win32Provider
...
```

### <a name="displaying-wmi-class-details"></a><span data-ttu-id="9ef4b-124">WMI クラスの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="9ef4b-124">Displaying WMI Class Details</span></span>

<span data-ttu-id="9ef4b-125">WMI クラスの名前がわかっている場合は、その名前を使って情報をすぐに取得できます。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-125">If you already know the name of a WMI class, you can use it to get information immediately.</span></span> <span data-ttu-id="9ef4b-126">たとえば、コンピューターに関する情報を取得するためによく使われる WMI クラスの 1 つに、**Win32_OperatingSystem** があります。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-126">For example, one of the WMI classes commonly used for retrieving information about a computer is **Win32_OperatingSystem**.</span></span>

```
PS> Get-WmiObject -Class Win32_OperatingSystem -Namespace root/cimv2 -ComputerName .

SystemDirectory : C:\WINDOWS\system32
Organization    : Global Network Solutions
BuildNumber     : 2600
RegisteredUser  : Oliver W. Jones
SerialNumber    : 12345-678-9012345-67890
Version         : 5.1.2600
```

<span data-ttu-id="9ef4b-127">ここでは、すべてのパラメーターを示しましたが、このコマンドはもっと簡潔に表現できます。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-127">Although we are showing all of the parameters, the command can be expressed in a more succinct way.</span></span> <span data-ttu-id="9ef4b-128">**ComputerName** パラメーターは、ローカル システムに接続するときには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-128">The **ComputerName** parameter is not necessary when connecting to the local system.</span></span> <span data-ttu-id="9ef4b-129">最も一般的なケースを示し、このパラメーターを思い出してもらうために使いました。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-129">We show it to demonstrate the most general case and remind you about the parameter.</span></span> <span data-ttu-id="9ef4b-130">**Namespace** の既定値は root/cimv2 であるため、これも省略できます。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-130">The **Namespace** defaults to root/cimv2, and can be omitted as well.</span></span> <span data-ttu-id="9ef4b-131">最後に、ほとんどのコマンドレットでは、共通のパラメーターの名前を省略できます。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-131">Finally, most cmdlets allow you to omit the name of common parameters.</span></span> <span data-ttu-id="9ef4b-132">Get-WmiObject の場合、最初のパラメーターに名前が指定されていないときには、Windows PowerShell はそれを **Class** パラメーターとして扱います。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-132">With Get-WmiObject, if no name is specified for the first parameter, Windows PowerShell treats it as the **Class** parameter.</span></span> <span data-ttu-id="9ef4b-133">したがって、先ほどのコマンドは、次のように入力することもできました。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-133">This means the last command could have been issued by typing:</span></span>

```powershell
Get-WmiObject Win32_OperatingSystem
```

<span data-ttu-id="9ef4b-134">**Win32_OperatingSystem** クラスには、ここで紹介した以外にも多数のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-134">The **Win32_OperatingSystem** class has many more properties than those displayed here.</span></span> <span data-ttu-id="9ef4b-135">Get-Member を使うと、すべてのプロパティを参照できます。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-135">You can use Get-Member to see all the properties.</span></span> <span data-ttu-id="9ef4b-136">WMI クラスのプロパティは、他のオブジェクト プロパティと同じように自動的に取得できます。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-136">The properties of a WMI class are automatically available like other object properties:</span></span>

```
PS> Get-WmiObject -Class Win32_OperatingSystem -Namespace root/cimv2 -ComputerName . | Get-Member -MemberType Property

   TypeName: System.Management.ManagementObject#root\cimv2\Win32_OperatingSyste
m

Name                                      MemberType Definition
----                                      ---------- ----------
__CLASS                                   Property   System.String __CLASS {...
...
BootDevice                                Property   System.String BootDevic...
BuildNumber                               Property   System.String BuildNumb...
...
```

#### <a name="displaying-non-default-properties-with-format-cmdlets"></a><span data-ttu-id="9ef4b-137">既定以外のプロパティを Format コマンドレットで表示する</span><span class="sxs-lookup"><span data-stu-id="9ef4b-137">Displaying Non-Default Properties with Format Cmdlets</span></span>

<span data-ttu-id="9ef4b-138">**Win32_OperatingSystem** クラスに含まれている情報のうち、既定では表示されない情報を表示するには、**Format** コマンドレットを使います。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-138">If you want information contained in the **Win32_OperatingSystem** class that is not displayed by default, you can display it by using the **Format** cmdlets.</span></span> <span data-ttu-id="9ef4b-139">たとえば、利用可能なメモリのデータを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-139">For example, if you want to display available memory data, type:</span></span>

```
PS> Get-WmiObject -Class Win32_OperatingSystem -Namespace root/cimv2 -ComputerName . | Format-Table -Property TotalVirtualMemorySize,TotalVisibleMemorySize,FreePhysicalMemory,FreeVirtualMemory,FreeSpaceInPagingFiles

TotalVirtualMemorySize TotalVisibleMemory FreePhysicalMemory FreeVirtualMemory FreeSpaceInPagingFiles
---------------------- ---------------    ------------------ -==--------------------- ---------------
               2097024          785904                305808           2056724                1558232
```

> [!NOTE]
> <span data-ttu-id="9ef4b-140">**Format-Table** のプロパティ名にはワイルドカードを指定できるので、最後のパイプライン要素は `Format-Table -Property Total,Free` のように省略できます</span><span class="sxs-lookup"><span data-stu-id="9ef4b-140">Wildcards work with property names in **Format-Table**, so the final pipeline element can be reduced to `Format-Table -Property Total,Free`</span></span>

<span data-ttu-id="9ef4b-141">メモリのデータは、次のように入力して一覧の形式にすると、さらに読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="9ef4b-141">The memory data might be more readable if you format it as a list by typing:</span></span>

```
PS> Get-WmiObject -Class Win32_OperatingSystem -Namespace root/cimv2 -ComputerName . | Format-List TotalVirtualMemorySize,TotalVisibleMemorySize,FreePhysicalMemory,FreeVirtualMemory,FreeSpaceInPagingFiles

TotalVirtualMemorySize : 2097024
TotalVisibleMemorySize : 785904
FreePhysicalMemory     : 301876
FreeVirtualMemory      : 2056724
FreeSpaceInPagingFiles : 1556644
```
