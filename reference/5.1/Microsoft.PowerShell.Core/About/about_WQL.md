---
description: WMI Query Language (WQL) について説明します。これは Windows PowerShell で WMI オブジェクトを取得するために使用できます。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wql?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WQL
ms.openlocfilehash: c6fd523864d419fb400b7041e92ec8f0733724b7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223187"
---
# <a name="about-wql"></a><span data-ttu-id="1ada9-104">WQL の概要</span><span class="sxs-lookup"><span data-stu-id="1ada9-104">About WQL</span></span>

## <a name="short-description"></a><span data-ttu-id="1ada9-105">概要</span><span class="sxs-lookup"><span data-stu-id="1ada9-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="1ada9-106">WMI Query Language (WQL) について説明します。これは Windows PowerShell で WMI オブジェクトを取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-106">Describes WMI Query Language (WQL), which can be used to get WMI objects in Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="1ada9-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="1ada9-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="1ada9-108">WQL は Windows Management Instrumentation (WMI) クエリ言語であり、WMI から情報を取得するために使用される言語です。</span><span class="sxs-lookup"><span data-stu-id="1ada9-108">WQL is the Windows Management Instrumentation (WMI) query language, which is the language used to get information from WMI.</span></span>

<span data-ttu-id="1ada9-109">Windows PowerShell で WMI クエリを実行するために WQL を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1ada9-109">You are not required to use WQL to perform a WMI query in Windows PowerShell.</span></span>
<span data-ttu-id="1ada9-110">代わりに、Get-WmiObject または Get-CimInstance コマンドレットのパラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-110">Instead, you can use the parameters of the Get-WmiObject or Get-CimInstance cmdlets.</span></span> <span data-ttu-id="1ada9-111">WQL クエリは、標準 Get-WmiObject コマンドよりも少し高速で、コマンドが何百ものシステムで実行された場合にパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-111">WQL queries are somewhat faster than standard Get-WmiObject commands and the improved performance is evident when the commands run on hundreds of systems.</span></span> <span data-ttu-id="1ada9-112">ただし、正常に実行された WQL クエリを作成するのにかかる時間は、パフォーマンスの向上を上回ることはありません。</span><span class="sxs-lookup"><span data-stu-id="1ada9-112">However, be sure that the time you spend to write a successful WQL query doesn't outweigh the performance improvement.</span></span>

<span data-ttu-id="1ada9-113">WQL を使用するために必要な基本的な WQL ステートメントは、Select、Where、From です。</span><span class="sxs-lookup"><span data-stu-id="1ada9-113">The basic WQL statements you need to use WQL are Select, Where, and From.</span></span>

## <a name="when-to-use-wql"></a><span data-ttu-id="1ada9-114">WQL を使用する場合</span><span class="sxs-lookup"><span data-stu-id="1ada9-114">WHEN TO USE WQL</span></span>

<span data-ttu-id="1ada9-115">WMI を使用する場合、特に WQL を使用する場合は、Windows PowerShell も使用していることを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="1ada9-115">When working with WMI, and especially with WQL, do not forget that you are also using Windows PowerShell.</span></span> <span data-ttu-id="1ada9-116">多くの場合、WQL クエリが想定どおりに動作しない場合は、WQL クエリをデバッグするよりも、標準の Windows PowerShell コマンドを使用する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="1ada9-116">Often, if a WQL query does not work as expected, it's easier to use a standard Windows PowerShell command than to debug the WQL query.</span></span>

<span data-ttu-id="1ada9-117">帯域幅が制限されたリモートシステムから膨大な量のデータを返す場合を除き、同じことを実行する Windows コマンドレットが非常に遅い場合は、時間をかけて複雑で複雑な WQL クエリを作成することはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="1ada9-117">Unless you are returning massive amounts of data from across bandwidth-constrained remote systems, it is rarely productive to spend hours trying to perfect a complicated and convoluted WQL query when there is a perfectly acceptable Windows cmdlet that does the same thing, if a bit more slowly.</span></span>

## <a name="using-the-select-statement"></a><span data-ttu-id="1ada9-118">SELECT ステートメントの使用</span><span class="sxs-lookup"><span data-stu-id="1ada9-118">USING THE SELECT STATEMENT</span></span>

<span data-ttu-id="1ada9-119">一般的な WMI クエリは、WMI クラスのすべてのプロパティまたは特定のプロパティを取得する Select ステートメントで始まります。</span><span class="sxs-lookup"><span data-stu-id="1ada9-119">A typical WMI query begins with a Select statement that gets all properties or particular properties of a WMI class.</span></span> <span data-ttu-id="1ada9-120">WMI クラスのすべてのプロパティを選択するには、アスタリスク () を使用し \* ます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-120">To select all properties of a WMI class, use an asterisk (\*).</span></span> <span data-ttu-id="1ada9-121">From キーワードは、WMI クラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-121">The From keyword specifies the WMI class.</span></span>

<span data-ttu-id="1ada9-122">Select ステートメントの形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1ada9-122">A Select statement has the following format:</span></span>

```
Select <property> from <WMI-class>
```

<span data-ttu-id="1ada9-123">たとえば、次の Select ステートメントでは、Win32_Bios WMI クラスのインスタンスからすべてのプロパティ (\*) を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-123">For example, the following Select statement selects all properties (\*) from the instances of the Win32_Bios WMI class.</span></span>

```
Select * from Win32_Bios
```

<span data-ttu-id="1ada9-124">WMI クラスの特定のプロパティを選択するには、Select キーワードと From キーワードの間にプロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-124">To select a particular property of a WMI class, place the property name between the Select and From keywords.</span></span>

<span data-ttu-id="1ada9-125">次のクエリでは、Win32_Bios WMI クラスから BIOS の名前のみを選択します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-125">The following query selects only the name of the BIOS from the Win32_Bios WMI class.</span></span> <span data-ttu-id="1ada9-126">このコマンドは、クエリを $queryName 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-126">The command saves the query in the $queryName variable.</span></span>

```
Select Name from Win32_Bios
```

<span data-ttu-id="1ada9-127">複数のプロパティを選択するには、コンマを使用してプロパティ名を区切ります。</span><span class="sxs-lookup"><span data-stu-id="1ada9-127">To select more than one property, use commas to separate the property names.</span></span>
<span data-ttu-id="1ada9-128">次の WMI クエリでは、Win32_Bios WMI クラスの名前とバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-128">The following WMI query selects the name and the version of the Win32_Bios WMI class.</span></span> <span data-ttu-id="1ada9-129">このコマンドは、クエリを $queryNameVersion 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-129">The command saves the query in the $queryNameVersion variable.</span></span>

```
Select name, version from Win32_Bios
```

## <a name="using-the-wql-query"></a><span data-ttu-id="1ada9-130">WQL クエリの使用</span><span class="sxs-lookup"><span data-stu-id="1ada9-130">USING THE WQL QUERY</span></span>

<span data-ttu-id="1ada9-131">Windows PowerShell コマンドで WQL クエリを使用するには、次の3つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="1ada9-131">There are three ways to use WQL query in Windows PowerShell command.</span></span>

- <span data-ttu-id="1ada9-132">Get-WmiObject コマンドレットを使用する</span><span class="sxs-lookup"><span data-stu-id="1ada9-132">Use the Get-WmiObject cmdlet</span></span>
- <span data-ttu-id="1ada9-133">Get-CimInstance コマンドレットを使用する</span><span class="sxs-lookup"><span data-stu-id="1ada9-133">Use the Get-CimInstance cmdlet</span></span>
- <span data-ttu-id="1ada9-134">[Wmisearcher] 型アクセラレータを使用します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-134">Use the [wmisearcher] type accelerator.</span></span>

## <a name="using-the-get-wmiobject-cmdlet"></a><span data-ttu-id="1ada9-135">GET-WMIOBJECT コマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="1ada9-135">USING THE GET-WMIOBJECT CMDLET</span></span>

<span data-ttu-id="1ada9-136">WQL クエリを使用する最も基本的な方法は、次の例に示すように、引用符で囲んで (文字列として) 引用符で囲み、Get-WmiObject コマンドレットのクエリパラメーターの値としてクエリ文字列を使用することです。</span><span class="sxs-lookup"><span data-stu-id="1ada9-136">The most basic way to use the WQL query is to enclose it in quotation marks (as a string) and then use the query string as the value of the Query parameter of the Get-WmiObject cmdlet, as shown in the following example.</span></span>

```powershell
Get-WmiObject -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="1ada9-137">次のコマンドに示すように、WQL ステートメントを変数に保存し、その変数をクエリパラメーターの値として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-137">You can also save the WQL statement in a variable and then use the variable as the value of the Query parameter, as shown in the following command.</span></span>

```powershell
$query = "Select * from Win32_Bios"
Get-WmiObject -Query $query
```

<span data-ttu-id="1ada9-138">どちらの形式でも、任意の WQL ステートメントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-138">You can use either format with any WQL statement.</span></span> <span data-ttu-id="1ada9-139">次のコマンドでは、$queryName 変数のクエリを使用して、システム BIOS の name および version プロパティのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-139">The following command uses the query in the $queryName variable to get only the name and version properties of the system BIOS.</span></span>

```powershell
$queryNameVersion = "Select Name, Version from Win32_Bios"
Get-WmiObject -Query $queryNameVersion
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

<span data-ttu-id="1ada9-140">Get-WmiObject コマンドレットのパラメーターを使用して、同じ結果を得ることができることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1ada9-140">Remember that you can use the parameters of the Get-WmiObject cmdlet to get the same result.</span></span> <span data-ttu-id="1ada9-141">たとえば、次のコマンドは、Win32_Bios WMI クラスのインスタンスの名前とバージョンプロパティの値も取得します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-141">For example, the following command also gets the values of the Name and Version properties of instances of the Win32_Bios WMI class.</span></span>

```powershell
Get-WmiObject -Class Win32_Bios -Property Name, Version
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

## <a name="using-the-get-ciminstance-cmdlet"></a><span data-ttu-id="1ada9-142">CIMINSTANCE コマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="1ada9-142">USING THE GET-CIMINSTANCE CMDLET</span></span>

<span data-ttu-id="1ada9-143">Windows PowerShell 3.0 以降では、Get-CimInstance コマンドレットを使用して WQL クエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-143">Beginning in Windows PowerShell 3.0, you can use the Get-CimInstance cmdlet to run WQL queries.</span></span>

<span data-ttu-id="1ada9-144">Get-CimInstance は、WMI クラスを含む CIM 準拠クラスのインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-144">Get-CimInstance gets instances of CIM-compliant classes, including WMI classes.</span></span> <span data-ttu-id="1ada9-145">Windows PowerShell 3.0 で導入された CIM コマンドレットは、WMI コマンドレットと同じタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-145">The CIM cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span> <span data-ttu-id="1ada9-146">CIM コマンドレットは、WS-Management (WSMan) 標準と Common Information Model (CIM) 標準に準拠しています。これにより、コマンドレットは、同じ手法を使用して、他のオペレーティングシステムを実行している Windows コンピューターとコンピューターを管理できます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-146">The CIM cmdlets comply with WS-Management (WSMan) standards and with the Common Information Model (CIM) standard, which enables the cmdlets to use the same techniques to manage Windows computers and computers that are running other operating systems.</span></span>

<span data-ttu-id="1ada9-147">次のコマンドでは、Get-CimInstance コマンドレットを使用して、WQL クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-147">The following command uses the Get-CimInstance cmdlet to run a WQL query.</span></span>

<span data-ttu-id="1ada9-148">Get-WmiObject で使用できる WQL クエリは、CimInstance でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-148">Any WQL query that can be used with Get-WmiObject can also be used with Get-CimInstance.</span></span>

```powershell
Get-CimInstance -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="1ada9-149">Get-CimInstance によって返さ Get-WmiObject れる System.management.managementobject ではなく、CimInstance オブジェクトが返されますが、オブジェクトは非常に似ています。</span><span class="sxs-lookup"><span data-stu-id="1ada9-149">Get-CimInstance returns a CimInstance object, instead of the ManagementObject that Get-WmiObject returns, but the objects are quite similar.</span></span>

```
(Get-CimInstance -Query "Select * from Win32_Bios").GetType().FullName
Microsoft.Management.Infrastructure.CimInstance
(Get-WmiObject -Query "Select * from Win32_Bios").GetType().FullName
System.Management.ManagementObject
```

## <a name="using-the-wmisearcher-type-accelerator"></a><span data-ttu-id="1ada9-150">[Wmisearcher] 型アクセラレータを使用する</span><span class="sxs-lookup"><span data-stu-id="1ada9-150">USING THE [wmisearcher] TYPE ACCELERATOR</span></span>

<span data-ttu-id="1ada9-151">[Wmisearcher] 型アクセラレータは、WQL ステートメント文字列から ManagementObjectSearcher オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-151">The [wmisearcher] type accelerator creates a ManagementObjectSearcher object from a WQL statement string.</span></span> <span data-ttu-id="1ada9-152">ManagementObjectSearcher オブジェクトには多くのプロパティとメソッドがありますが、最も基本的な方法は Get メソッドです。このメソッドは、指定された WMI クエリを呼び出し、結果として得られるオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-152">The ManagementObjectSearcher object has many properties and methods, but the most basic method is the Get method, which invokes the specified WMI query and returns the resulting objects.</span></span>

<span data-ttu-id="1ada9-153">[Wmisearcher] を使用すると、ManagementObjectSearcher .NET Framework クラスに簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-153">By using the [wmisearcher], you gain easy access to the ManagementObjectSearcher .NET Framework class.</span></span> <span data-ttu-id="1ada9-154">これにより、WMI に対してクエリを実行し、クエリの実行方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-154">This lets you query WMI and to configure the way the query is conducted.</span></span>

<span data-ttu-id="1ada9-155">[Wmisearcher] 型アクセラレータを使用するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-155">To use the [wmisearcher] type accelerator:</span></span>

1. <span data-ttu-id="1ada9-156">WQL 文字列を ManagementObjectSearcher オブジェクトにキャストします。</span><span class="sxs-lookup"><span data-stu-id="1ada9-156">Cast the  WQL string into a ManagementObjectSearcher object.</span></span>
2. <span data-ttu-id="1ada9-157">ManagementObjectSearcher オブジェクトの Get メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-157">Call the Get method of the ManagementObjectSearcher object.</span></span>

<span data-ttu-id="1ada9-158">たとえば、次のコマンドは、"select all" クエリをキャストし、その結果を $bios 変数に保存してから、$bios 変数で ManagementObjectSearcher オブジェクトの Get メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-158">For example, the following command casts the "select all" query, saves the result in the $bios variable, and then calls the Get method of the ManagementObjectSearcher object in the $bios variable.</span></span>

```powershell
$bios = [wmisearcher]"Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="1ada9-159">注: 既定では、選択したオブジェクトのプロパティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-159">NOTE: Only selected object properties are displayed by default.</span></span> <span data-ttu-id="1ada9-160">これらのプロパティは、Types.ps1xml ファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="1ada9-160">These properties are defined in the Types.ps1xml file.</span></span>

<span data-ttu-id="1ada9-161">[Wmisearcher] 型アクセラレータを使用して、クエリまたは変数をキャストできます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-161">You can use the [wmisearcher] type accelerator to cast the query or the variable.</span></span> <span data-ttu-id="1ada9-162">次の例では、変数をキャストするために、[wmisearcher] 型 accelerator が使用されています。</span><span class="sxs-lookup"><span data-stu-id="1ada9-162">In the following example, the [wmisearcher] type accelerator is used to cast the variable.</span></span> <span data-ttu-id="1ada9-163">結果は同じです。</span><span class="sxs-lookup"><span data-stu-id="1ada9-163">The result is the same.</span></span>

```powershell
[wmisearcher]$bios = "Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="1ada9-164">次のコマンドに示すように、[wmisearcher] 型アクセラレータを使用すると、クエリ文字列が ManagementObjectSearcher オブジェクトに変更されます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-164">When you use the [wmisearcher] type accelerator, it changes the query string into a ManagementObjectSearcher object, as shown in the following commands.</span></span>

```
$a = "Select * from Win32_Bios"
$a.GetType().FullName
System.String

$a = [wmisearcher]"Select * from Win32_Bios"
$a.GetType().FullName
System.Management.ManagementObjectSearcher
```

<span data-ttu-id="1ada9-165">このコマンド形式は、任意のクエリで動作します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-165">This command format works on any query.</span></span> <span data-ttu-id="1ada9-166">次のコマンドは、Win32_Bios WMI クラスの Name プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-166">The following command gets the value of the Name property of the Win32_Bios WMI class.</span></span>

```powershell
$biosname = [wmisearcher]"Select Name from Win32_Bios"
$biosname.Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

<span data-ttu-id="1ada9-167">この操作は1つのコマンドで実行できますが、コマンドの解釈は少し難しくなります。</span><span class="sxs-lookup"><span data-stu-id="1ada9-167">You can perform this operation in a single command, although the command is a bit more difficult to interpret.</span></span>

<span data-ttu-id="1ada9-168">この形式では、[wmisearcher] 型アクセラレータを使用して WQL クエリ文字列を ManagementObjectSearcher にキャストし、オブジェクトの Get メソッドを1つのコマンドで呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-168">In this format, you use the [wmisearcher] type accelerator to cast the WQL query string to a ManagementObjectSearcher, and then call the Get method on the object -- all in a single command.</span></span> <span data-ttu-id="1ada9-169">キャストされた文字列を囲むかっこ () は、メソッドを呼び出す前に文字列をキャストするように指示します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-169">The parentheses () that enclose the casted string direct Windows PowerShell to cast the string before calling the method.</span></span>

```powershell
([wmisearcher]"Select name from Win32_Bios").Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

## <a name="using-the-basic-wql-where-statement"></a><span data-ttu-id="1ada9-170">基本的な WQL WHERE ステートメントの使用</span><span class="sxs-lookup"><span data-stu-id="1ada9-170">USING THE BASIC WQL WHERE STATEMENT</span></span>

<span data-ttu-id="1ada9-171">Where ステートメントは、Select ステートメントによって返されるデータの条件を確立します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-171">A Where statement establishes conditions for the data that a Select statement returns.</span></span>

<span data-ttu-id="1ada9-172">Where ステートメントの形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1ada9-172">The Where statement has the following format:</span></span>

```
where <property> <operator> <value>
```

<span data-ttu-id="1ada9-173">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-173">For example:</span></span>

```
where Name = 'Notepad.exe'
```

<span data-ttu-id="1ada9-174">Where ステートメントは、次の例に示すように、Select ステートメントと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-174">The Where statement is used with the Select statement, as shown in the following example.</span></span>

```
Select * from Win32_Process where Name = 'Notepad.exe'
```

<span data-ttu-id="1ada9-175">Where ステートメントを使用する場合は、プロパティの名前と値が正確である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ada9-175">When using the Where statement, the property name and value must be accurate.</span></span>

<span data-ttu-id="1ada9-176">たとえば、次のコマンドは、ローカルコンピューター上のメモ帳プロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-176">For example, the following command gets the Notepad processes on the local computer.</span></span>

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad.exe'"
```

<span data-ttu-id="1ada9-177">ただし、次のコマンドは失敗します。これは、プロセス名に ".exe" ファイル名拡張子が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="1ada9-177">However, the following command fails, because the process name includes the ".exe" file name extension.</span></span>

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad'"
```

## <a name="where-statement-comparison-operators"></a><span data-ttu-id="1ada9-178">WHERE ステートメントの比較演算子</span><span class="sxs-lookup"><span data-stu-id="1ada9-178">WHERE STATEMENT COMPARISON OPERATORS</span></span>

<span data-ttu-id="1ada9-179">次の演算子は、WQL の Where ステートメントで有効です。</span><span class="sxs-lookup"><span data-stu-id="1ada9-179">The following operators are valid in a WQL Where statement.</span></span>

```
Operator    Description
-----------------------
=           Equal
!=          Not equal
<>          Not equal
<           Less than
>           Greater than
<=          Less than or equal
>=          Greater than or equal
LIKE        Wildcard match
IS          Evaluates null
ISNOT       Evaluates not null
ISA         Evaluates a member of a WMI class
```

<span data-ttu-id="1ada9-180">他にも演算子はありますが、これらは比較を行うために使用されるものです。</span><span class="sxs-lookup"><span data-stu-id="1ada9-180">There are other operators, but these are the ones used for making comparisons.</span></span>

<span data-ttu-id="1ada9-181">たとえば、次のクエリでは、Win32_Process クラスのプロセスから、プロセスの優先度が11以上の名前と優先度のプロパティが選択されます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-181">For example, the following query selects the Name and Priority properties from processes in the Win32_Process class where the process priority is greater than or equal to 11.</span></span> <span data-ttu-id="1ada9-182">Get-WmiObject コマンドレットは、クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-182">The Get-WmiObject cmdlet runs the query.</span></span>

```powershell
$highPriority = "Select Name, Priority from Win32_Process " +
  "where Priority >= 11"
Get-WmiObject -Query $highPriority
```

## <a name="using-the-wql-operators-in-the-filter-parameter"></a><span data-ttu-id="1ada9-183">FILTER パラメーターでの WQL 演算子の使用</span><span class="sxs-lookup"><span data-stu-id="1ada9-183">USING THE WQL OPERATORS IN THE FILTER PARAMETER</span></span>

<span data-ttu-id="1ada9-184">WQL 演算子は、これらのコマンドレットのクエリパラメーターの値に加えて、Get-WmiObject または Get-CimInstance コマンドレットの Filter パラメーターの値で使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-184">The WQL operators can also be used in the value of the Filter parameter of the Get-WmiObject or Get-CimInstance cmdlets, as well as in the value of the Query parameters of these cmdlets.</span></span>

<span data-ttu-id="1ada9-185">たとえば、次のコマンドは、ProcessID 値が1004より大きい最後の5つのプロセスの名前と ProcessID プロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-185">For example, the following command gets the Name and ProcessID properties of the last five processes that have ProcessID values greater than 1004.</span></span> <span data-ttu-id="1ada9-186">このコマンドは、Filter パラメーターを使用して、ProcessID 条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-186">The command uses the Filter parameter to specify the ProcessID condition.</span></span>

```powershell
Get-WmiObject -Class Win32_Process `
-Property Name, ProcessID -Filter "ProcessID >= 1004" |
Sort ProcessID | Select Name, ProcessID -Last 5
```

```output
Name                                 ProcessID
----                                 ---------
SROSVC.exe                                4220
WINWORD.EXE                               4664
TscHelp.exe                               4744
SnagIt32.exe                              4748
WmiPrvSE.exe                              5056
```

## <a name="using-the-like-operator"></a><span data-ttu-id="1ada9-187">LIKE 演算子の使用</span><span class="sxs-lookup"><span data-stu-id="1ada9-187">USING THE LIKE OPERATOR</span></span>

<span data-ttu-id="1ada9-188">Like 演算子を使用すると、ワイルドカード文字を使用して WQL クエリの結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-188">The Like operator lets you use wildcard characters to filter the results of a WQL query.</span></span>

```
Like Operator  Description
--------------------------------------------------
[]             Character in a range [a-f] or a set
               of characters [abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

^              Character not in a range [^a-f] or
               not in a set [^abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

%              A string of zero or more characters

_              One character.
(underscore)   NOTE: To use a literal underscore
               in a query string, enclose it in
               square brackets [_].
```

<span data-ttu-id="1ada9-189">Like 演算子をワイルドカード文字または範囲演算子なしで使用すると、等値演算子 (=) と同様に動作し、パターンと完全に一致する場合にのみオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-189">When the Like operator is used without any wildcard characters or range operators, it behaves like the equality operator (=) and returns objects only when they are an exact match for the pattern.</span></span>

<span data-ttu-id="1ada9-190">範囲演算とパーセントワイルドカード文字を組み合わせて、シンプルで、かつ強力なフィルターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-190">You can combine the range operation with the percent wildcard character to create simple, yet powerful filters.</span></span>

### <a name="like-operator-examples"></a><span data-ttu-id="1ada9-191">LIKE 演算子の例</span><span class="sxs-lookup"><span data-stu-id="1ada9-191">LIKE OPERATOR EXAMPLES</span></span>

#### <a name="example-1-range"></a><span data-ttu-id="1ada9-192">例 1: [ \<range> ]</span><span class="sxs-lookup"><span data-stu-id="1ada9-192">EXAMPLE 1: [\<range>]</span></span>

<span data-ttu-id="1ada9-193">次のコマンドは、メモ帳を起動してから、"H" から "N" までの文字で始まる名前を持つ Win32_Process クラスのインスタンスを検索します (大文字と小文字は区別されません)。</span><span class="sxs-lookup"><span data-stu-id="1ada9-193">The following commands start Notepad and then search for an instance of the Win32_Process class that has a name that starts with a letter between "H" and "N" (case-insensitive).</span></span>

<span data-ttu-id="1ada9-194">クエリは、Hotpad.exe から Notepad.exe までのプロセスを返します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-194">The query should return any process from Hotpad.exe through Notepad.exe.</span></span>

```powershell
Notepad   # Starts Notepad
$query = "Select * from win32_Process where Name LIKE '[H-N]otepad.exe'"
Get-WmiObject -Query $query | Select Name, ProcessID
```

```output
Name                                ProcessID
----                                ---------
notepad.exe                              1740
```

#### <a name="example-2-range-and-"></a><span data-ttu-id="1ada9-195">例 2: [ \<range> ] および%</span><span class="sxs-lookup"><span data-stu-id="1ada9-195">EXAMPLE 2: [\<range>] and %</span></span>

<span data-ttu-id="1ada9-196">次のコマンドでは、A と P (大文字と小文字は区別されません) の間に文字で始まる名前を持つすべてのプロセスを選択し、その後に任意の組み合わせで0個以上の文字を続けます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-196">The following commands select all process that have a name that begins with a letter between A and P (case-insensitive) followed by zero or more letters in any combination.</span></span>

<span data-ttu-id="1ada9-197">Get-WmiObject コマンドレットはクエリを実行し、Select-Object コマンドレットは Name および ProcessID プロパティを取得します。 Sort-Object コマンドレットは、結果を名前順にアルファベット順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-197">The Get-WmiObject cmdlet runs the query, the Select-Object cmdlet gets the Name and ProcessID properties, and the Sort-Object cmdlet sorts the results in alphabetical order by name.</span></span>

```powershell
$query = "Select * from win32_Process where name LIKE '[A-P]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-3-not-in-range-"></a><span data-ttu-id="1ada9-198">例 3: 範囲内にありません (^)</span><span class="sxs-lookup"><span data-stu-id="1ada9-198">EXAMPLE 3: Not in Range (^)</span></span>

<span data-ttu-id="1ada9-199">次のコマンドは、名前の先頭に次の文字が含まれていないプロセスを取得します。 A、S、W、P、R、C、U、N</span><span class="sxs-lookup"><span data-stu-id="1ada9-199">The following command gets processes whose names do not begin with any of the following letters: A, S, W, P, R, C, U, N</span></span>

<span data-ttu-id="1ada9-200">の後に0個以上の文字が続きます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-200">and followed zero or more letters.</span></span>

```powershell
$query = "Select * from win32_Process where name LIKE '[^ASWPRCUN]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-4-any-characters----or-none-"></a><span data-ttu-id="1ada9-201">例 4: 任意の文字--または none (%)</span><span class="sxs-lookup"><span data-stu-id="1ada9-201">EXAMPLE 4: Any characters -- or none (%)</span></span>

<span data-ttu-id="1ada9-202">次のコマンドは、名前が "calc" で始まるプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-202">The following commands get processes that have names that begin with "calc".</span></span>
<span data-ttu-id="1ada9-203">WQL の% 記号は、 \* 正規表現のアスタリスク () 記号に相当します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-203">The % symbol in WQL is equivalent to the asterisk (\*) symbol in regular expressions.</span></span>

```powershell
$query = "Select * from win32_Process where Name LIKE 'calc%'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                               ProcessID
----                               ---------
calc.exe                                4424
```

#### <a name="example-5-one-character-_"></a><span data-ttu-id="1ada9-204">例 5: 1 文字 (_)</span><span class="sxs-lookup"><span data-stu-id="1ada9-204">EXAMPLE 5: One character (_)</span></span>

<span data-ttu-id="1ada9-205">次のコマンドは、"c_lc.exe" というパターンの名前を持つプロセスを取得します。この場合、アンダースコア文字は任意の1文字を表します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-205">The following commands get processes that have names that have the following pattern, "c_lc.exe" where the underscore character represents any one character.</span></span> <span data-ttu-id="1ada9-206">このパターンは、calc.exe から czlc.exe または c9lc.exe の任意の名前と一致しますが、"c" と "l" が複数の文字で区切られている名前とは一致しません。</span><span class="sxs-lookup"><span data-stu-id="1ada9-206">This pattern matches any name from calc.exe through czlc.exe, or c9lc.exe, but does not match names in which the "c" and "l" are separated by more than one character.</span></span>

```powershell
$query = "Select * from Win32_Process where Name LIKE 'c_lc.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                                 ProcessID
----                                 ---------
calc.exe                                  4424
```

#### <a name="example-6-exact-match"></a><span data-ttu-id="1ada9-207">例 6: 完全一致</span><span class="sxs-lookup"><span data-stu-id="1ada9-207">EXAMPLE 6: Exact match</span></span>

<span data-ttu-id="1ada9-208">次のコマンドは、WLIDSVC.exe という名前のプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-208">The following commands get processes named WLIDSVC.exe.</span></span> <span data-ttu-id="1ada9-209">クエリで Like キーワードを使用している場合でも、値にはワイルドカード文字が含まれないため、完全一致が必要です。</span><span class="sxs-lookup"><span data-stu-id="1ada9-209">Even though the query uses the Like keyword, it requires an exact match, because the value does not include any wildcard characters.</span></span>

```powershell
$query = "Select * from win32_Process where name LIKE 'WLIDSVC.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```powershell

```output
Name                                 ProcessID
----                                 ---------
WLIDSVC.exe                                84
```

## <a name="using-the-or-operator"></a><span data-ttu-id="1ada9-210">OR 演算子の使用</span><span class="sxs-lookup"><span data-stu-id="1ada9-210">USING THE OR OPERATOR</span></span>

<span data-ttu-id="1ada9-211">複数の独立した条件を指定するには、またはキーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-211">To specify multiple independent conditions, use the Or keyword.</span></span> <span data-ttu-id="1ada9-212">Where 句にまたはキーワードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-212">The Or keyword appears in the Where clause.</span></span> <span data-ttu-id="1ada9-213">2つ (以上) の条件に対して包括的 OR 演算を実行し、任意の条件を満たす項目を返します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-213">It performs an inclusive OR operation on two (or more) conditions and returns items that meet any of the conditions.</span></span>

<span data-ttu-id="1ada9-214">Or 演算子の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1ada9-214">The Or operator has the following format:</span></span>

```
Where <property> <operator> <value> or <property> <operator> <value> ...
```

<span data-ttu-id="1ada9-215">たとえば、次のコマンドは、Win32_Process WMI クラスのすべてのインスタンスを取得しますが、プロセス名が winword.exe または excel.exe の場合にのみそれらを返します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-215">For example, the following commands get all instances of the Win32_Process WMI class but returns them only if the process name is winword.exe or excel.exe.</span></span>

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe'"
Get-WmiObject -Query $q
```

<span data-ttu-id="1ada9-216">ステートメントまたはステートメントは、3つ以上の条件で使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-216">The Or statement can be used with more than two conditions.</span></span> <span data-ttu-id="1ada9-217">次のクエリでは、またはステートメントが Winword.exe、Excel.exe、または Powershell.exe を取得します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-217">In the following query, the Or statement gets Winword.exe, Excel.exe, or Powershell.exe.</span></span>

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe' or Name='powershell.exe'"
```

## <a name="using-the-and-operator"></a><span data-ttu-id="1ada9-218">AND 演算子の使用</span><span class="sxs-lookup"><span data-stu-id="1ada9-218">USING THE AND OPERATOR</span></span>

<span data-ttu-id="1ada9-219">複数の関連する条件を指定するには、キーワードとキーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-219">To specify multiple related conditions, use the And keyword.</span></span> <span data-ttu-id="1ada9-220">Where 句にとキーワードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-220">The And keyword appears in the Where clause.</span></span> <span data-ttu-id="1ada9-221">すべての条件を満たす項目が返されます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-221">It returns items that meet all of the conditions.</span></span>

<span data-ttu-id="1ada9-222">And 演算子の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1ada9-222">The And operator has the following format:</span></span>

```
Where <property> <operator> <value> and <property> <operator> <value> ...
```

<span data-ttu-id="1ada9-223">たとえば、次のコマンドは、名前が "Winword.exe" でプロセス ID が6512のプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-223">For example, the following commands get processes that have a name of "Winword.exe" and the process ID of 6512.</span></span>

<span data-ttu-id="1ada9-224">コマンドは Get-CimInstance コマンドレットを使用することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1ada9-224">Note that the commands use the Get-CimInstance cmdlet.</span></span>

```powershell
$q = "Select * from Win32_Process where Name = 'winword.exe' " +
  "and ProcessID =6512"
Get-CimInstance -Query $q
```

```output
ProcessId   Name             HandleCount      WorkingSetSize   VirtualSize
---------   ----             -----------      --------------   -----------
# 6512      WINWORD.EXE      768              117170176        633028608
```

<span data-ttu-id="1ada9-225">Like 演算子を含むすべての演算子は、Or 演算子および And 演算子と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-225">All operators, including the Like operators are valid with the Or and And operators.</span></span> <span data-ttu-id="1ada9-226">また、Or 演算子と And 演算子は、1つのクエリでは、最初に処理する句を Windows PowerShell に指示するかっこを使用して組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-226">And, you can combine the Or and And operators in a single query with parentheses that tell Windows PowerShell which clauses to process first.</span></span>

<span data-ttu-id="1ada9-227">このコマンドは、Windows PowerShell の継続文字 (') を使用して、コマンドを2行に分割します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-227">This command uses the Windows PowerShell continuation character (\`) divide the command into two lines.</span></span>

```powershell
$q = "Select * from Win32_Process `
where (Name = 'winword.exe' or Name = 'excel.exe') and HandleCount > 700"
Get-CimInstance -Query $q
```

```output
ProcessId    Name             HandleCount      WorkingSetSize   VirtualSize
---------    ----             -----------      --------------   -----------
     6512    WINWORD.EXE      797              117268480        634425344
     9610    EXCEL.EXE        727               38858752        323227648
```

## <a name="searching-for-null-values"></a><span data-ttu-id="1ada9-228">NULL 値の検索</span><span class="sxs-lookup"><span data-stu-id="1ada9-228">SEARCHING FOR NULL VALUES</span></span>

<span data-ttu-id="1ada9-229">WMI で null 値を検索することは困難です。これは、予期しない結果につながる可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="1ada9-229">Searching for null values in WMI is challenging, because it can lead to unpredictable results.</span></span> <span data-ttu-id="1ada9-230">Null が0ではなく、または空の文字列でもありません。</span><span class="sxs-lookup"><span data-stu-id="1ada9-230">Null is not zero and it is not equivalent or to an empty string.</span></span> <span data-ttu-id="1ada9-231">一部の WMI クラスプロパティは初期化されていますが、そうでない場合、null を検索すると、すべてのプロパティに対して機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ada9-231">Some WMI class properties are initialized and others are not, so a search for null might not work for all properties.</span></span>

<span data-ttu-id="1ada9-232">Null 値を検索するには、値が "null" の Is 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-232">To search for null values, use the Is operator with a value of "null".</span></span>

<span data-ttu-id="1ada9-233">たとえば、次のコマンドは、IntallDate プロパティに null 値を持つプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-233">For example, the following commands get processes that have a null value for the IntallDate property.</span></span> <span data-ttu-id="1ada9-234">コマンドは多数のプロセスを返します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-234">The commands return many processes.</span></span>

```powershell
$q = "Select * from Win32_Process where InstallDate is null"
Get-WmiObject -Query $q
```

<span data-ttu-id="1ada9-235">これに対し、次のコマンドは、Description プロパティに null 値を持つユーザーアカウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-235">In contrast, the following command, gets user accounts that have a null value for the Description property.</span></span> <span data-ttu-id="1ada9-236">このコマンドは、ほとんどのユーザーアカウントが Description プロパティの値を持たない場合でも、ユーザーアカウントを返しません。</span><span class="sxs-lookup"><span data-stu-id="1ada9-236">This command does not return any user accounts, even though most user accounts do not have any value for the Description property.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Description is null"
Get-WmiObject -Query $q
```

<span data-ttu-id="1ada9-237">Description プロパティの値がないユーザーアカウントを検索するには、等値演算子を使用して空の文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-237">To find the user accounts that have no value for the Description property, use the equality operator to get an empty string.</span></span> <span data-ttu-id="1ada9-238">空の文字列を表すには、2つの連続する単一引用符を使用します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-238">To represent the empty string, use two consecutive single quotation marks.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Description = '' "
```

## <a name="using-true-or-false"></a><span data-ttu-id="1ada9-239">TRUE または FALSE を使用する</span><span class="sxs-lookup"><span data-stu-id="1ada9-239">USING TRUE OR FALSE</span></span>

<span data-ttu-id="1ada9-240">WMI オブジェクトのプロパティでブール値を取得するには、True と False を使用します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-240">To get Boolean values in the properties of WMI objects, use True and False.</span></span>
<span data-ttu-id="1ada9-241">大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="1ada9-241">They are not case sensitive.</span></span>

<span data-ttu-id="1ada9-242">次の WQL クエリでは、ドメインに参加しているコンピューターからローカルユーザーアカウントのみが返されます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-242">The following WQL query returns only local user accounts from a domain joined computer.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = True"
Get-CimInstance -Query $q
```

<span data-ttu-id="1ada9-243">ドメインアカウントを検索するには、次の例に示すように、False の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-243">To find domain accounts, use a value of False, as shown in the following example.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = False"
Get-CimInstance -Query $q
```

## <a name="using-the-escape-character"></a><span data-ttu-id="1ada9-244">エスケープ文字の使用</span><span class="sxs-lookup"><span data-stu-id="1ada9-244">USING THE ESCAPE CHARACTER</span></span>

<span data-ttu-id="1ada9-245">WQL では、 \) エスケープ文字として円記号を使用します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-245">WQL uses the backslash (\) as its escape character.</span></span> <span data-ttu-id="1ada9-246">これは、バックティック文字 (') を使用する Windows PowerShell とは異なります。</span><span class="sxs-lookup"><span data-stu-id="1ada9-246">This is different from Windows PowerShell, which uses the backtick character (\`).</span></span>

<span data-ttu-id="1ada9-247">引用符や引用符に使用する文字は、誤って解釈されないようにエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ada9-247">Quotation marks, and the characters used for quotation marks, often need to be escaped so that they are not misinterpreted.</span></span>

<span data-ttu-id="1ada9-248">名前に単一引用符が含まれているユーザーを検索するには、次のコマンドに示すように、円記号を使用して単一引用符をエスケープします。</span><span class="sxs-lookup"><span data-stu-id="1ada9-248">To find a user whose name includes a single quotation mark, use a backslash to escape the single quotation mark, as shown in the following command.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Name = 'Tim O\'Brian'"
Get-CimInstance -Query $q
```

```output
Name             Caption          AccountType      SID              Domain
----             -------          -----------      ---              ------
Tim O'Brian      FABRIKAM\TimO    512              S-1-5-21-1457... FABRIKAM
```

<span data-ttu-id="1ada9-249">場合によっては、円記号もエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ada9-249">In some case, the backslash also needs to be escaped.</span></span> <span data-ttu-id="1ada9-250">たとえば、次のコマンドでは、キャプション値に円記号が含まれているため、無効なクエリエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1ada9-250">For example, the following commands generate an Invalid Query error due to the backslash in the Caption value.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\TimO'"
Get-CimInstance -Query $q
```

```output
Get-CimInstance : Invalid query
At line:1 char:1
+ Get-CimInstance -Query $q
+ ~~~~~~~~~~~
  + CategoryInfo          : InvalidArgument: (:) [Get-CimInstance], CimExcep
  + FullyQualifiedErrorId : HRESULT 0x80041017,Microsoft.Management.Infrastr
```

<span data-ttu-id="1ada9-251">バックスラッシュをエスケープするには、次のコマンドに示すように、2つ目の円記号を使用します。</span><span class="sxs-lookup"><span data-stu-id="1ada9-251">To escape the backslash, use a second backslash character, as shown in the following command.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\\TimO'"
Get-CimInstance -Query $q
```

## <a name="see-also"></a><span data-ttu-id="1ada9-252">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ada9-252">SEE ALSO</span></span>

[<span data-ttu-id="1ada9-253">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="1ada9-253">about_Special_Characters</span></span>](about_Special_Characters.md)

[<span data-ttu-id="1ada9-254">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="1ada9-254">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="1ada9-255">about_WMI</span><span class="sxs-lookup"><span data-stu-id="1ada9-255">about_WMI</span></span>](about_WMI.md)

[<span data-ttu-id="1ada9-256">about_WMI_Cmdlets</span><span class="sxs-lookup"><span data-stu-id="1ada9-256">about_WMI_Cmdlets</span></span>](about_WMI_Cmdlets.md)
