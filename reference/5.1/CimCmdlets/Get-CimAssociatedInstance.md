---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimassociatedinstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimAssociatedInstance
ms.openlocfilehash: 10790507b24bc4212db062589cf76d5260554b30
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218099"
---
# <span data-ttu-id="13782-103">Get-CimAssociatedInstance</span><span class="sxs-lookup"><span data-stu-id="13782-103">Get-CimAssociatedInstance</span></span>

## <span data-ttu-id="13782-104">概要</span><span class="sxs-lookup"><span data-stu-id="13782-104">SYNOPSIS</span></span>
<span data-ttu-id="13782-105">アソシエーションによって特定の CIM インスタンスに接続されている CIM インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="13782-105">Retrieves the CIM instances that are connected to a specific CIM instance by an association.</span></span>

## <span data-ttu-id="13782-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="13782-106">SYNTAX</span></span>

### <span data-ttu-id="13782-107">ComputerSet (既定)</span><span class="sxs-lookup"><span data-stu-id="13782-107">ComputerSet (Default)</span></span>

```
Get-CimAssociatedInstance [[-Association] <String>] [-ResultClassName <String>]
 [-InputObject] <CimInstance> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-ResourceUri <Uri>] [-ComputerName <String[]>] [-KeyOnly] [<CommonParameters>]
```

### <span data-ttu-id="13782-108">SessionSet</span><span class="sxs-lookup"><span data-stu-id="13782-108">SessionSet</span></span>

```
Get-CimAssociatedInstance [[-Association] <String>] [-ResultClassName <String>]
 [-InputObject] <CimInstance> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-ResourceUri <Uri>] -CimSession <CimSession[]> [-KeyOnly] [<CommonParameters>]
```

## <span data-ttu-id="13782-109">Description</span><span class="sxs-lookup"><span data-stu-id="13782-109">DESCRIPTION</span></span>

<span data-ttu-id="13782-110">この `Get-CimAssociatedInstance` コマンドレットは、関連付けによって、ソースインスタンスと呼ばれる特定の cim インスタンスに接続されている cim インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="13782-110">The `Get-CimAssociatedInstance` cmdlet retrieves the CIM instances connected to a specific CIM instance, called the source instance, by an association.</span></span>

<span data-ttu-id="13782-111">アソシエーションでは、各 CIM インスタンスに名前付きロールがあり、同じ CIM インスタンスを異なるロール内のアソシエーションに参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="13782-111">In an association, each CIM instance has a named role and the same CIM instance can participate in an association in different roles.</span></span>

<span data-ttu-id="13782-112">InputObject パラメーターが指定されていない場合、コマンドレットは次のいずれかの方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="13782-112">If the InputObject parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="13782-113">**ComputerName** パラメーターも **CimSession** パラメーターも指定しない場合、このコマンドレットはコンポーネントオブジェクトモデル (COM) セッションを使用してローカル Windows Management Instrumentation (WMI) で動作します。</span><span class="sxs-lookup"><span data-stu-id="13782-113">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="13782-114">**Computername** パラメーターまたは **CimSession** パラメーターを指定した場合、このコマンドレットは、 **computername** パラメーターまたは **CIMSESSION** パラメーターで指定された CIM サーバーに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="13782-114">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

## <span data-ttu-id="13782-115">例</span><span class="sxs-lookup"><span data-stu-id="13782-115">EXAMPLES</span></span>

### <span data-ttu-id="13782-116">例 1: 特定のインスタンスに関連付けられているすべてのインスタンスを取得する</span><span class="sxs-lookup"><span data-stu-id="13782-116">Example 1: Get all the associated instances of a specific instance</span></span>

```powershell
$disk = Get-CimInstance -ClassName Win32_LogicalDisk -KeyOnly
Get-CimAssociatedInstance -InputObject $disk[1]
```

<span data-ttu-id="13782-117">この一連のコマンドは、Win32_LogicalDisk という名前のクラスのインスタンスを取得し、 `$disk` コマンドレットを使用して、という名前の変数に情報を格納し `Get-CimInstance` ます。</span><span class="sxs-lookup"><span data-stu-id="13782-117">This set of commands retrieves the instances of the class named Win32_LogicalDisk and stores the information in a variable named `$disk` using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="13782-118">次に、変数内の最初の論理ディスクインスタンスをコマンドレットの入力オブジェクトとして使用して、 `Get-CimAssociatedInstance` 指定した cim インスタンスの関連付けられているすべての cim インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="13782-118">The first logical disk instance in the variable is then used as the input object for the `Get-CimAssociatedInstance` cmdlet to get all the associated CIM instances of the specified CIM instance.</span></span>

### <span data-ttu-id="13782-119">例 2: 特定の型のすべての関連インスタンスを取得する</span><span class="sxs-lookup"><span data-stu-id="13782-119">Example 2: Get all the associated instances of a specific type</span></span>

```powershell
$disk = Get-CimInstance -ClassName Win32_LogicalDisk -KeyOnly
Get-CimAssociatedInstance -InputObject $disk[1] -ResultClass Win32_DiskPartition
```

<span data-ttu-id="13782-120">この一連のコマンドは、 **Win32_LogicalDisk** クラスのすべてのインスタンスを取得し、という名前の変数に格納し `$disk` ます。</span><span class="sxs-lookup"><span data-stu-id="13782-120">This set of commands retrieves all the instances of the **Win32_LogicalDisk** class and stores them in a variable named `$disk`.</span></span> <span data-ttu-id="13782-121">次に、変数内の最初の論理ディスクインスタンスをコマンドレットの入力オブジェクトとして使用して、指定した `Get-CimAssociatedInstance` アソシエーションクラス **Win32_DiskPartition** に関連付けられているすべての関連するインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="13782-121">The first logical disk instance in the variable is then used as the input object for the `Get-CimAssociatedInstance` cmdlet to get all the associated instances that are associated through the specified association class **Win32_DiskPartition**.</span></span>

### <span data-ttu-id="13782-122">例 3: 特定のクラスの修飾子を使用して、関連するすべてのインスタンスを取得する</span><span class="sxs-lookup"><span data-stu-id="13782-122">Example 3: Get all the associated instances through qualifier of a specific class</span></span>

```powershell
$s = Get-CimInstance -Query "Select * from Win32_Service where name like 'Winmgmt'"
Get-CimClass -ClassName *Service* -Qualifier "Association"
$c.CimClasName
```

```Output
Win32_LoadOrderGroupServiceDependencies
Win32_DependentService
Win32_SystemServices
Win32_LoadOrderGroupServiceMembers
Win32_ServiceSpecificationService
```

```powershell
Get-CimAssociatedInstance -InputObject $s -Association Win32_DependentService
```

<span data-ttu-id="13782-123">この一連のコマンドは、WMI サービスに依存するサービスを取得し、という名前の変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="13782-123">This set of commands retrieves the services that depend on WMI service and stores them in a variable named `$s`.</span></span> <span data-ttu-id="13782-124">**Win32_DependentService** のアソシエーションクラス名は、コマンドレットを使用して取得されます `Get-CimClass` 。 **関連付け** を修飾子として指定し、コマンドレットに $s 渡して、取得した `Get-CimAssociatedInstance` association クラスのすべての関連インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="13782-124">The association class name for the **Win32_DependentService** is retrieved using the `Get-CimClass` cmdlet by specifying **Association** as the qualifier and is then passed with $s to the `Get-CimAssociatedInstance` cmdlet to get all the associated instances of the retrieved association class.</span></span>

## <span data-ttu-id="13782-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="13782-125">PARAMETERS</span></span>

### <span data-ttu-id="13782-126">-関連付け</span><span class="sxs-lookup"><span data-stu-id="13782-126">-Association</span></span>

<span data-ttu-id="13782-127">アソシエーションクラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="13782-127">Specifies the name of the association class.</span></span> <span data-ttu-id="13782-128">このパラメーターを指定しない場合、コマンドレットは任意の型のすべての既存の関連付けオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="13782-128">If you do not specify this parameter, the cmdlet returns all existing association objects of any type.</span></span>

<span data-ttu-id="13782-129">たとえば、AB1 と AB2 の2つのアソシエーションを通じてクラス A がクラス B に関連付けられている場合、このパラメーターを使用して、AB1 または AB2 のいずれかの関連付けの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="13782-129">For example, if class A is associated with class B through two associations, AB1 and AB2, then this parameter can be used to specify the type of association, either AB1 or AB2.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="13782-130">-CimSession</span><span class="sxs-lookup"><span data-stu-id="13782-130">-CimSession</span></span>

<span data-ttu-id="13782-131">指定された CIM セッションを使用してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="13782-131">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="13782-132">CIM セッションを含む変数、またはやなどの CIM セッションを作成または取得するコマンドを入力 `New-CimSession` し `Get-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="13782-132">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as `New-CimSession` or `Get-CimSession`.</span></span> <span data-ttu-id="13782-133">詳細については、「 [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13782-133">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: SessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="13782-134">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="13782-134">-ComputerName</span></span>

<span data-ttu-id="13782-135">CIM 操作を実行するコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="13782-135">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="13782-136">完全修飾ドメイン名 (FQDN) または NetBIOS 名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="13782-136">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

<span data-ttu-id="13782-137">このパラメーターを指定すると、コマンドレットは WsMan プロトコルを使用して、指定されたコンピューターへの一時的なセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="13782-137">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="13782-138">このパラメーターを指定しない場合、コマンドレットはコンポーネントオブジェクトモデル (COM) を使用してローカルコンピューター上で操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="13782-138">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="13782-139">複数の操作が同じコンピューター上で実行されている場合、CIM セッションを使用して接続するとパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="13782-139">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="13782-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="13782-140">-InputObject</span></span>

<span data-ttu-id="13782-141">このコマンドレットへの入力を指定します。</span><span class="sxs-lookup"><span data-stu-id="13782-141">Specifies the input to this cmdlet.</span></span> <span data-ttu-id="13782-142">このパラメーターを使用するか、またはこのコマンドレットへの入力をパイプで渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="13782-142">You can use this parameter, or you can pipe the input to this cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: (All)
Aliases: CimInstance

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="13782-143">-KeyOnly</span><span class="sxs-lookup"><span data-stu-id="13782-143">-KeyOnly</span></span>

<span data-ttu-id="13782-144">キープロパティのみが設定されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="13782-144">Returns objects with only key properties populated.</span></span> <span data-ttu-id="13782-145">これにより、ネットワーク経由で転送されるデータの量が減少します。</span><span class="sxs-lookup"><span data-stu-id="13782-145">This reduces the amount of data that is transferred over the network.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="13782-146">-Namespace</span><span class="sxs-lookup"><span data-stu-id="13782-146">-Namespace</span></span>

<span data-ttu-id="13782-147">CIM 操作の名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="13782-147">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="13782-148">既定の名前空間は root/cimv2 です。</span><span class="sxs-lookup"><span data-stu-id="13782-148">The default namespace is root/cimv2.</span></span>

> [!NOTE]
> <span data-ttu-id="13782-149">タブ補完を使用して名前空間の一覧を参照することができます。これは、名前空間の一覧を提供するために、PowerShell がローカル WMI サーバーから名前空間の一覧を取得するためです。</span><span class="sxs-lookup"><span data-stu-id="13782-149">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="13782-150">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="13782-150">-OperationTimeoutSec</span></span>

<span data-ttu-id="13782-151">コマンドレットがコンピューターからの応答を待機する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="13782-151">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="13782-152">既定では、このパラメーターの値は0です。これは、コマンドレットがサーバーの既定のタイムアウト値を使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="13782-152">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="13782-153">**Operationtimeoutsec** パラメーターが、堅牢な接続再試行タイムアウトの3分未満の値に設定されている場合、 **operationtimeoutsec** パラメーターの値を超えるネットワークエラーは復旧できません。これは、クライアントが再接続する前に、サーバー上の操作がタイムアウトになるためです。</span><span class="sxs-lookup"><span data-stu-id="13782-153">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="13782-154">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="13782-154">-ResourceUri</span></span>

<span data-ttu-id="13782-155">リソースクラスまたはインスタンスのリソース URI (uniform resource identifier) を指定します。</span><span class="sxs-lookup"><span data-stu-id="13782-155">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="13782-156">URI は、ディスクやプロセスなど、コンピューター上の特定の種類のリソースを特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="13782-156">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="13782-157">URI は、プレフィックスとリソースのパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="13782-157">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="13782-158">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="13782-158">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="13782-159">既定では、このパラメーターを指定しない場合、DMTF 標準リソース URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` が使用され、クラス名が追加されます。</span><span class="sxs-lookup"><span data-stu-id="13782-159">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="13782-160">**ResourceURI** は、wsman プロトコルを使用して作成された cim セッションでのみ使用できます。また、wsman を使用して cim セッションを作成する **ComputerName** パラメーターを指定する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="13782-160">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="13782-161">**ComputerName** パラメーターを指定せずにこのパラメーターを指定した場合、または dcom プロトコルを使用して作成された CIM セッションを指定した場合、dcom プロトコルでは **ResourceURI** パラメーターがサポートされないため、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="13782-161">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="13782-162">**ResourceUri** パラメーターと **filter** パラメーターの両方が指定されている場合、 **filter** パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="13782-162">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="13782-163">-ResultClassName</span><span class="sxs-lookup"><span data-stu-id="13782-163">-ResultClassName</span></span>

<span data-ttu-id="13782-164">関連付けられているインスタンスのクラス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="13782-164">Specifies the class name of the associated instances.</span></span> <span data-ttu-id="13782-165">CIM インスタンスは、1つまたは複数の CIM インスタンスに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="13782-165">A CIM instance can be associated with one or more CIM instances.</span></span> <span data-ttu-id="13782-166">結果クラス名を指定しない場合は、関連付けられているすべての CIM インスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="13782-166">All associated CIM instances are returned if you do not specify the result class name.</span></span>

<span data-ttu-id="13782-167">既定では、このパラメーターの値は null で、関連付けられているすべての CIM インスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="13782-167">By default, the value of this parameter is null, and all associated CIM instances are returned.</span></span>

<span data-ttu-id="13782-168">関連付けの結果をフィルター処理して、特定のクラス名に一致させることができます。</span><span class="sxs-lookup"><span data-stu-id="13782-168">You can filter the association results to match a specific class name.</span></span> <span data-ttu-id="13782-169">フィルター処理はサーバー上で行われます。</span><span class="sxs-lookup"><span data-stu-id="13782-169">Filtering happens on the server.</span></span> <span data-ttu-id="13782-170">このパラメーターが指定されていない場合、は `Get-CIMAssociatedInstance` 既存のすべての関連付けを返します。</span><span class="sxs-lookup"><span data-stu-id="13782-170">If this parameter is not specified, `Get-CIMAssociatedInstance` returns all existing associations.</span></span> <span data-ttu-id="13782-171">たとえば、クラス A がクラス B、C、および D に関連付けられている場合、このパラメーターを使用して、出力を特定の型 (B、C、または D) に制限できます。</span><span class="sxs-lookup"><span data-stu-id="13782-171">For example, if class A is associated with classes B, C and D, then this parameter can be used to restrict the output to a specific type (B, C or D).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="13782-172">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="13782-172">CommonParameters</span></span>

<span data-ttu-id="13782-173">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="13782-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="13782-174">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13782-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="13782-175">入力</span><span class="sxs-lookup"><span data-stu-id="13782-175">INPUTS</span></span>

### <span data-ttu-id="13782-176">なし</span><span class="sxs-lookup"><span data-stu-id="13782-176">None</span></span>

<span data-ttu-id="13782-177">このコマンドレットは、入力オブジェクトを受け入れません。</span><span class="sxs-lookup"><span data-stu-id="13782-177">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="13782-178">出力</span><span class="sxs-lookup"><span data-stu-id="13782-178">OUTPUTS</span></span>

### <span data-ttu-id="13782-179">System.Object</span><span class="sxs-lookup"><span data-stu-id="13782-179">System.Object</span></span>

<span data-ttu-id="13782-180">このコマンドレットは、オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="13782-180">This cmdlet returns an object.</span></span>

## <span data-ttu-id="13782-181">注</span><span class="sxs-lookup"><span data-stu-id="13782-181">NOTES</span></span>

## <span data-ttu-id="13782-182">関連リンク</span><span class="sxs-lookup"><span data-stu-id="13782-182">RELATED LINKS</span></span>

[<span data-ttu-id="13782-183">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="13782-183">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="13782-184">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="13782-184">Get-CimInstance</span></span>](get-ciminstance.md)
