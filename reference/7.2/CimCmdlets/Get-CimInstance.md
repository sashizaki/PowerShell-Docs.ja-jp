---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/21/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-ciminstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimInstance
ms.openlocfilehash: 0e4a148601f3ef2212f9c97128c54258906106d7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601206"
---
# <span data-ttu-id="893ed-102">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="893ed-102">Get-CimInstance</span></span>

## <span data-ttu-id="893ed-103">概要</span><span class="sxs-lookup"><span data-stu-id="893ed-103">SYNOPSIS</span></span>
<span data-ttu-id="893ed-104">CIM サーバーからクラスの CIM インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="893ed-104">Gets the CIM instances of a class from a CIM server.</span></span>

## <span data-ttu-id="893ed-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="893ed-105">SYNTAX</span></span>

### <span data-ttu-id="893ed-106">ClassNameComputerSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="893ed-106">ClassNameComputerSet (Default)</span></span>

```
Get-CimInstance [-ClassName] <String> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="893ed-107">ResourceUriSessionSet</span><span class="sxs-lookup"><span data-stu-id="893ed-107">ResourceUriSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> -ResourceUri <Uri> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="893ed-108">QuerySessionSet</span><span class="sxs-lookup"><span data-stu-id="893ed-108">QuerySessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

### <span data-ttu-id="893ed-109">ClassNameSessionSet</span><span class="sxs-lookup"><span data-stu-id="893ed-109">ClassNameSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ClassName] <String> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="893ed-110">CimInstanceSessionSet</span><span class="sxs-lookup"><span data-stu-id="893ed-110">CimInstanceSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### <span data-ttu-id="893ed-111">CimInstanceComputerSet</span><span class="sxs-lookup"><span data-stu-id="893ed-111">CimInstanceComputerSet</span></span>

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### <span data-ttu-id="893ed-112">ResourceUriComputerSet</span><span class="sxs-lookup"><span data-stu-id="893ed-112">ResourceUriComputerSet</span></span>

```
Get-CimInstance -ResourceUri <Uri> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="893ed-113">QueryComputerSet</span><span class="sxs-lookup"><span data-stu-id="893ed-113">QueryComputerSet</span></span>

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

## <span data-ttu-id="893ed-114">Description</span><span class="sxs-lookup"><span data-stu-id="893ed-114">DESCRIPTION</span></span>

<span data-ttu-id="893ed-115">コマンドレットでは、 `Get-CimInstance` cim サーバーからクラスの cim インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="893ed-115">The `Get-CimInstance` cmdlet gets the CIM instances of a class from a CIM server.</span></span> <span data-ttu-id="893ed-116">クラス名またはこのコマンドレットのクエリのいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="893ed-116">You can specify either the class name or a query for this cmdlet.</span></span> <span data-ttu-id="893ed-117">このコマンドレットは、CIM サーバー上に存在する CIM インスタンスのスナップショットを表す1つ以上の CIM インスタンスオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="893ed-117">This cmdlet returns one or more CIM instance objects representing a snapshot of the CIM instances present on the CIM server.</span></span>

<span data-ttu-id="893ed-118">**InputObject** パラメーターが指定されていない場合、コマンドレットは次のいずれかの方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="893ed-118">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="893ed-119">**ComputerName** パラメーターも **CimSession** パラメーターも指定しない場合、このコマンドレットはコンポーネントオブジェクトモデル (COM) セッションを使用してローカル Windows Management Instrumentation (WMI) で動作します。</span><span class="sxs-lookup"><span data-stu-id="893ed-119">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="893ed-120">**Computername** パラメーターまたは **CimSession** パラメーターを指定した場合、このコマンドレットは、 **computername** パラメーターまたは **CIMSESSION** パラメーターで指定された CIM サーバーに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="893ed-120">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="893ed-121">**InputObject** パラメーターが指定されている場合、コマンドレットは次のいずれかの方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="893ed-121">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="893ed-122">**ComputerName** パラメーターも **CimSession** パラメーターも指定しない場合、このコマンドレットは入力オブジェクトの CIM セッションまたはコンピューター名を使用します。</span><span class="sxs-lookup"><span data-stu-id="893ed-122">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="893ed-123">**Computername** パラメーターまたは **CimSession** パラメーターのいずれかが指定されている場合、このコマンドレットは CimSession パラメーター値または **computername** パラメーター値を使用します。</span><span class="sxs-lookup"><span data-stu-id="893ed-123">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the CimSession parameter value or **ComputerName** parameter value.</span></span>

## <span data-ttu-id="893ed-124">例</span><span class="sxs-lookup"><span data-stu-id="893ed-124">EXAMPLES</span></span>

### <span data-ttu-id="893ed-125">例 1: 指定したクラスの CIM インスタンスを取得する</span><span class="sxs-lookup"><span data-stu-id="893ed-125">Example 1: Get the CIM instances of a specified class</span></span>

<span data-ttu-id="893ed-126">この例では、 **Win32_Process** という名前のクラスの CIM インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="893ed-126">This example retrieves the CIM instances of a class named **Win32_Process**.</span></span>

```powershell
Get-CimInstance -ClassName Win32_Process
```

### <span data-ttu-id="893ed-127">例 2: WMI サーバーから名前空間の一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="893ed-127">Example 2: Get a list of namespaces from a WMI server</span></span>

<span data-ttu-id="893ed-128">この例では、WMI サーバーの **ルート** 名前空間の下にある名前空間の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="893ed-128">This example retrieves a list of namespaces under the **Root** namespace on a WMI server.</span></span>

```powershell
Get-CimInstance -Namespace root -ClassName __Namespace
```

### <span data-ttu-id="893ed-129">例 3: クエリを使用してフィルター処理されたクラスのインスタンスを取得する</span><span class="sxs-lookup"><span data-stu-id="893ed-129">Example 3: Get instances of a class filtered by using a query</span></span>

<span data-ttu-id="893ed-130">この例では、**クエリ** パラメーターによって指定されたクエリを使用して、 **Win32_Process** という名前のクラスの文字 **P** で始まるすべての CIM インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="893ed-130">This example retrieves all the CIM instances that start with the letter **P** of a class named **Win32_Process** using the query specified by a **Query** parameter.</span></span>

```powershell
Get-CimInstance -Query "SELECT * from Win32_Process WHERE name LIKE 'P%'"
```

### <span data-ttu-id="893ed-131">例 4: クラス名とフィルター式を使用してフィルター処理されたクラスのインスタンスを取得する</span><span class="sxs-lookup"><span data-stu-id="893ed-131">Example 4: Get instances of a class filtered by using a class name and a filter expression</span></span>

<span data-ttu-id="893ed-132">この例では、Filter パラメーターを使用して、 **Win32_Process** という名前のクラスの文字 **P** で始まるすべての CIM インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="893ed-132">This example retrieves all the CIM instances that start with the letter **P** of a class named **Win32_Process** using the Filter parameter.</span></span>

```powershell
Get-CimInstance -ClassName Win32_Process -Filter "Name like 'P%'"
```

### <span data-ttu-id="893ed-133">例 5: キープロパティが入力されている CIM インスタンスを取得する</span><span class="sxs-lookup"><span data-stu-id="893ed-133">Example 5: Get the CIM instances with only key properties filled in</span></span>

<span data-ttu-id="893ed-134">この例では、キープロパティを使用して **Win32_Process** という名前のクラスの新しい CIM インスタンスをメモリに作成し、と `@{ "Handle"=0 }` いう名前の変数に格納し `$x` ます。</span><span class="sxs-lookup"><span data-stu-id="893ed-134">This example creates a new CIM instance in memory for a class named **Win32_Process** with the key property `@{ "Handle"=0 }` and stores it in a variable named `$x`.</span></span> <span data-ttu-id="893ed-135">変数は、 `Get-CimInstance` 特定のインスタンスを取得するために、CIM インスタンスとしてコマンドレットに渡されます。</span><span class="sxs-lookup"><span data-stu-id="893ed-135">The variable is passed as a CIM instance to the `Get-CimInstance` cmdlet to get a particular instance.</span></span>

```powershell
$x = New-CimInstance -ClassName Win32_Process -Namespace root\cimv2 -Property @{ "Handle"=0 } -Key Handle -ClientOnly
Get-CimInstance -CimInstance $x
```

### <span data-ttu-id="893ed-136">例 6: CIM インスタンスを取得して再利用する</span><span class="sxs-lookup"><span data-stu-id="893ed-136">Example 6: Retrieve CIM instances and reuse them</span></span>

<span data-ttu-id="893ed-137">この例では、 **Win32_Process** という名前のクラスの CIM インスタンスを取得し、それらを変数およびに格納し `$x` `$y` ます。</span><span class="sxs-lookup"><span data-stu-id="893ed-137">This example gets the CIM instances of a class named **Win32_Process** and stores them in the variables `$x` and `$y`.</span></span> <span data-ttu-id="893ed-138">この変数は、 `$x` **名前** と値が **AutoSize** に設定され **ている** テーブルでフォーマットされます。</span><span class="sxs-lookup"><span data-stu-id="893ed-138">The variable `$x` is then formatted in a table containing only the **Name** and **KernelModeTime** properties, the table set to **AutoSize**.</span></span>

```powershell
$x,$y = Get-CimInstance -ClassName Win32_Process
$x | Format-Table -Property Name,KernelModeTime -AutoSize
```

```Output
Name                 KernelModeTime
----                 --------------
System Idle Process 157238797968750
```

### <span data-ttu-id="893ed-139">例 7: リモートコンピューターから CIM インスタンスを取得する</span><span class="sxs-lookup"><span data-stu-id="893ed-139">Example 7: Get CIM instances from remote computer</span></span>

<span data-ttu-id="893ed-140">この例では、 **Server01** と **Server02** という名前のリモートコンピューターから、 **Win32_ComputerSystem** という名前のクラスの CIM インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="893ed-140">This example retrieves the CIM instances of a class named **Win32_ComputerSystem** from the remote computers named **Server01** and **Server02**.</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -ComputerName Server01,Server02
```

### <span data-ttu-id="893ed-141">例 8: すべてのプロパティではなく、キープロパティのみを取得する</span><span class="sxs-lookup"><span data-stu-id="893ed-141">Example 8: Getting only the key properties, instead of all properties</span></span>

<span data-ttu-id="893ed-142">この例では、キープロパティのみを取得します。これにより、オブジェクトとネットワークトラフィックのサイズが縮小されます。</span><span class="sxs-lookup"><span data-stu-id="893ed-142">This example retrieves only the key properties, which reduces the size of the object and network traffic.</span></span>

```powershell
$x = Get-CimInstance -Class Win32_Process -KeyOnly
$x | Invoke-CimMethod -MethodName GetOwner
```

### <span data-ttu-id="893ed-143">例 9: すべてのプロパティではなく、プロパティのサブセットのみを取得する</span><span class="sxs-lookup"><span data-stu-id="893ed-143">Example 9: Getting only a subset of properties, instead of all properties</span></span>

<span data-ttu-id="893ed-144">この例では、プロパティのサブセットのみを取得するため、オブジェクトとネットワークトラフィックのサイズが縮小されます。</span><span class="sxs-lookup"><span data-stu-id="893ed-144">This example retrieves only a subset of properties, which reduces the size of the object and network traffic.</span></span>

```powershell
Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x = Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x | Invoke-CimMethod -MethodName GetOwner
```

<span data-ttu-id="893ed-145">**プロパティ** パラメーターを使用して取得したインスタンスは、他の CIM 操作 (やなど) を実行するために使用でき `Set-CimInstance` `Invoke-CimMethod` ます。</span><span class="sxs-lookup"><span data-stu-id="893ed-145">The instance retrieved with the **Property** parameter can be used to perform other CIM operations, for example `Set-CimInstance` or `Invoke-CimMethod`.</span></span>

### <span data-ttu-id="893ed-146">例 10: CIM セッションを使用して CIM インスタンスを取得する</span><span class="sxs-lookup"><span data-stu-id="893ed-146">Example 10: Get the CIM instance using CIM session</span></span>

<span data-ttu-id="893ed-147">この例では、コマンドレットを使用して **Server01** と **Server02** という名前のコンピューターに CIM セッションを作成 `New-CimSession` し、という名前の変数にセッション情報を格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="893ed-147">This example creates a CIM session on the computers named **Server01** and **Server02** using the `New-CimSession` cmdlet and stores the session information in a variable named `$s`.</span></span> <span data-ttu-id="893ed-148">次に、CimSession パラメーターを使用して変数の内容をに渡し、 `Get-CimInstance` **Win32_ComputerSystem** という名前のクラスの CIM インスタンスを取得します。 </span><span class="sxs-lookup"><span data-stu-id="893ed-148">The contents of the variable are then passed to `Get-CimInstance` by using the **CimSession** parameter, to get the CIM instances of the class named **Win32_ComputerSystem**.</span></span>

```powershell
$s = New-CimSession -ComputerName Server01,Server02
Get-CimInstance -ClassName Win32_ComputerSystem -CimSession $s
```

## <span data-ttu-id="893ed-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="893ed-149">PARAMETERS</span></span>

### <span data-ttu-id="893ed-150">-CimSession</span><span class="sxs-lookup"><span data-stu-id="893ed-150">-CimSession</span></span>

<span data-ttu-id="893ed-151">このコマンドレットに使用する CIM セッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="893ed-151">Specifies the CIM session to use for this cmdlet.</span></span> <span data-ttu-id="893ed-152">Cim セッションを含む変数、またはやコマンドレットなどの CIM セッションを作成または取得するコマンドを入力し `New-CimSession` `Get-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="893ed-152">Enter a variable that contains the CIM session or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="893ed-153">詳細については、「 [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="893ed-153">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, CimInstanceSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="893ed-154">-ClassName</span><span class="sxs-lookup"><span data-stu-id="893ed-154">-ClassName</span></span>

<span data-ttu-id="893ed-155">CIM インスタンスを取得する CIM クラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="893ed-155">Specifies the name of the CIM class for which to retrieve the CIM instances.</span></span> <span data-ttu-id="893ed-156">タブ補完を使用してクラスの一覧を参照することができます。これは、クラス名の一覧を提供するために、PowerShell がローカル WMI サーバーからクラスの一覧を取得するためです。</span><span class="sxs-lookup"><span data-stu-id="893ed-156">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="893ed-157">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="893ed-157">-ComputerName</span></span>

<span data-ttu-id="893ed-158">CIM 操作を実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="893ed-158">Specifies computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="893ed-159">完全修飾ドメイン名 (FQDN)、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="893ed-159">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="893ed-160">このパラメーターを指定しない場合、コマンドレットはコンポーネントオブジェクトモデル (COM) を使用してローカルコンピューター上で操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="893ed-160">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="893ed-161">このパラメーターを指定すると、コマンドレットは WsMan プロトコルを使用して、指定されたコンピューターへの一時的なセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="893ed-161">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="893ed-162">同じコンピューターで複数の操作を実行する場合は、パフォーマンスを向上させるために CIM セッションを使用して接続します。</span><span class="sxs-lookup"><span data-stu-id="893ed-162">If multiple operations are being performed on the same computer, connect using a CIM session for better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, CimInstanceComputerSet, ResourceUriComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="893ed-163">-Filter</span><span class="sxs-lookup"><span data-stu-id="893ed-163">-Filter</span></span>

<span data-ttu-id="893ed-164">フィルターとして使用する where 句を指定します。</span><span class="sxs-lookup"><span data-stu-id="893ed-164">Specifies a where clause to use as a filter.</span></span> <span data-ttu-id="893ed-165">**WQL** または **cql** クエリ言語で句を指定します。</span><span class="sxs-lookup"><span data-stu-id="893ed-165">Specify the clause in either the **WQL** or the **CQL** query language.</span></span> <span data-ttu-id="893ed-166">`WHERE`パラメーターの値にキーワードを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="893ed-166">Do not include the `WHERE` keyword in the value of the parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="893ed-167">-InputObject</span><span class="sxs-lookup"><span data-stu-id="893ed-167">-InputObject</span></span>

<span data-ttu-id="893ed-168">入力として使用する CIM インスタンスオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="893ed-168">Specifies a CIM instance object to use as input.</span></span>

<span data-ttu-id="893ed-169">Cim インスタンスオブジェクトを既に使用している場合は、cim サーバーから最新のスナップショットを取得するために、このパラメーターを使用して CIM インスタンスオブジェクトを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="893ed-169">If you are already working with a CIM instance object, you can use this parameter to pass the CIM instance object in order to get the latest snapshot from the CIM server.</span></span> <span data-ttu-id="893ed-170">CIM インスタンスオブジェクトを入力として渡すと、は、 `Get-CimInstance` 列挙またはクエリ操作ではなく、GET cim 操作を使用してサーバーからオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="893ed-170">When you pass a CIM instance object as an input, `Get-CimInstance` returns the object from server using a get CIM operation, instead of an enumerate or query operation.</span></span> <span data-ttu-id="893ed-171">Get CIM 操作の使用は、すべてのインスタンスを取得してからフィルター処理するよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="893ed-171">Using a get CIM operation is more efficient than retrieving all instances and then filtering them.</span></span>

<span data-ttu-id="893ed-172">CIM クラスで get 操作が実装されていない場合、 **InputObject** パラメーターを指定するとエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="893ed-172">If the CIM class does not implement the get operation, then specifying the **InputObject** parameter returns an error.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceSessionSet, CimInstanceComputerSet
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="893ed-173">-KeyOnly</span><span class="sxs-lookup"><span data-stu-id="893ed-173">-KeyOnly</span></span>

<span data-ttu-id="893ed-174">キープロパティが設定されたオブジェクトのみが返されることを示します。</span><span class="sxs-lookup"><span data-stu-id="893ed-174">Indicates that only objects with key properties populated are returned.</span></span> <span data-ttu-id="893ed-175">**Keyonly** パラメーターを指定すると、ネットワーク経由で転送されるデータの量が減少します。</span><span class="sxs-lookup"><span data-stu-id="893ed-175">Specifying the **KeyOnly** parameter reduces the amount of data transferred over the network.</span></span>

<span data-ttu-id="893ed-176">**Keyonly** パラメーターを使用して、オブジェクトのごく一部のみを返します。これは、やコマンドレットなど、他の操作に使用でき `Set-CimInstance` `Get-CimAssociatedInstance` ます。</span><span class="sxs-lookup"><span data-stu-id="893ed-176">Use the **KeyOnly** parameter to return only a small portion of the object, which can be used for other operations, such as the `Set-CimInstance` or `Get-CimAssociatedInstance` cmdlets.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="893ed-177">-Namespace</span><span class="sxs-lookup"><span data-stu-id="893ed-177">-Namespace</span></span>

<span data-ttu-id="893ed-178">CIM クラスの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="893ed-178">Specifies the namespace of CIM class.</span></span>

<span data-ttu-id="893ed-179">既定の名前空間は **root/cimv2** です。</span><span class="sxs-lookup"><span data-stu-id="893ed-179">The default namespace is **root/cimv2**.</span></span> <span data-ttu-id="893ed-180">タブ補完を使用して名前空間の一覧を参照することができます。これは、名前空間の一覧を提供するために、PowerShell がローカル WMI サーバーから名前空間の一覧を取得するためです。</span><span class="sxs-lookup"><span data-stu-id="893ed-180">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, ResourceUriComputerSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="893ed-181">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="893ed-181">-OperationTimeoutSec</span></span>

<span data-ttu-id="893ed-182">コマンドレットがコンピューターからの応答を待機する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="893ed-182">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="893ed-183">既定では、このパラメーターの値は0です。これは、コマンドレットがサーバーの既定のタイムアウト値を使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="893ed-183">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="893ed-184">**Operationtimeoutsec** パラメーターが、堅牢な接続再試行タイムアウトの3分未満の値に設定されている場合、 **operationtimeoutsec** パラメーターの値を超えるネットワークエラーは復旧できません。これは、クライアントが再接続する前に、サーバー上の操作がタイムアウトになるためです。</span><span class="sxs-lookup"><span data-stu-id="893ed-184">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="893ed-185">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="893ed-185">-Property</span></span>

<span data-ttu-id="893ed-186">取得するインスタンスプロパティのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="893ed-186">Specifies a set of instance properties to retrieve.</span></span> <span data-ttu-id="893ed-187">メモリまたはネットワーク上で返されるオブジェクトのサイズを小さくする必要がある場合は、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="893ed-187">Use this parameter when you need to reduce the size of the object returned, either in memory or over the network.</span></span> <span data-ttu-id="893ed-188">返されたオブジェクトには、 **プロパティ** パラメーターを使用して一覧表示していない場合でも、キープロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="893ed-188">The object returned also contains the key properties even if you have not listed them using the **Property** parameter.</span></span> <span data-ttu-id="893ed-189">クラスのその他のプロパティは存在しますが、値は設定されません。</span><span class="sxs-lookup"><span data-stu-id="893ed-189">Other properties of the class are present but they are not populated.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases: SelectProperties

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="893ed-190">-Query</span><span class="sxs-lookup"><span data-stu-id="893ed-190">-Query</span></span>

<span data-ttu-id="893ed-191">CIM サーバーで実行するクエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="893ed-191">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="893ed-192">指定した値に二重引用符 `"` 、単一引用符、または円記号が含まれている場合は `'` `\` 、円記号を付けることによってこれらの文字をエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="893ed-192">If the value specified contains double quotes `"`, single quotes `'`, or a backslash `\`, you must escape those characters by prefixing them with the backslash character.</span></span> <span data-ttu-id="893ed-193">指定された値が WQL **LIKE** 演算子を使用する場合は、次の文字を角かっこで囲むことによってエスケープする必要があります `[]` : パーセント `%` 、アンダースコア `_` 、または左角かっこ `[` 。</span><span class="sxs-lookup"><span data-stu-id="893ed-193">If the value specified uses the WQL **LIKE** operator, then you must escape the following characters by enclosing them in square brackets `[]`: percent `%`, underscore `_`, or opening square bracket `[`.</span></span>

<span data-ttu-id="893ed-194">メタデータクエリを使用して、クラスの一覧またはイベントクエリを取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="893ed-194">You cannot use a metadata query to retrieve a list of classes or an event query.</span></span> <span data-ttu-id="893ed-195">クラスの一覧を取得するには、 `Get-CimClass` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="893ed-195">To retrieve a list of classes, use the `Get-CimClass` cmdlet.</span></span> <span data-ttu-id="893ed-196">イベントクエリを取得するには、 `Register-CimIndicationEvent` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="893ed-196">To retrieve an event query, use the `Register-CimIndicationEvent` cmdlet.</span></span>

<span data-ttu-id="893ed-197">**Querydialect** パラメーターを使用して、クエリ言語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="893ed-197">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="893ed-198">-QueryDialect</span><span class="sxs-lookup"><span data-stu-id="893ed-198">-QueryDialect</span></span>

<span data-ttu-id="893ed-199">クエリパラメーターに使用するクエリ言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="893ed-199">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="893ed-200">このパラメーターに指定できる値は、 **WQL** または **cql** です。</span><span class="sxs-lookup"><span data-stu-id="893ed-200">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span> <span data-ttu-id="893ed-201">既定値は **WQL** です。</span><span class="sxs-lookup"><span data-stu-id="893ed-201">The default value is **WQL**.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, QuerySessionSet, ClassNameSessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="893ed-202">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="893ed-202">-ResourceUri</span></span>

<span data-ttu-id="893ed-203">リソースクラスまたはインスタンスのリソース URI (uniform resource identifier) を指定します。</span><span class="sxs-lookup"><span data-stu-id="893ed-203">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="893ed-204">URI は、ディスクやプロセスなど、コンピューター上の特定の種類のリソースを特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="893ed-204">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="893ed-205">URI は、プレフィックスとリソースのパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="893ed-205">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="893ed-206">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="893ed-206">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="893ed-207">既定では、このパラメーターを指定しない場合、DMTF 標準リソース URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` が使用され、クラス名が追加されます。</span><span class="sxs-lookup"><span data-stu-id="893ed-207">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="893ed-208">**ResourceURI** は、wsman プロトコルを使用して作成された cim セッションでのみ使用できます。また、wsman を使用して cim セッションを作成する **ComputerName** パラメーターを指定する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="893ed-208">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="893ed-209">**ComputerName** パラメーターを指定せずにこのパラメーターを指定した場合、または dcom プロトコルを使用して作成された CIM セッションを指定した場合は、dcom プロトコルで **ResourceURI** パラメーターがサポートされていないため、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="893ed-209">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="893ed-210">**ResourceUri** パラメーターと **filter** パラメーターの両方が指定されている場合、 **filter** パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="893ed-210">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet, QuerySessionSet, QueryComputerSet, CimInstanceSessionSet, CimInstanceComputerSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (QuerySessionSet, QueryComputerSet, CimInstanceSessionSet, CimInstanceComputerSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="893ed-211">-浅い</span><span class="sxs-lookup"><span data-stu-id="893ed-211">-Shallow</span></span>

<span data-ttu-id="893ed-212">子クラスのインスタンスを含めずに、クラスのインスタンスが返されることを示します。</span><span class="sxs-lookup"><span data-stu-id="893ed-212">Indicates that the instances of a class are returned without including the instances of any child classes.</span></span> <span data-ttu-id="893ed-213">既定では、コマンドレットは、クラスとその子クラスのインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="893ed-213">By default, the cmdlet returns the instances of a class and its child classes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, ResourceUriComputerSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="893ed-214">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="893ed-214">CommonParameters</span></span>

<span data-ttu-id="893ed-215">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="893ed-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="893ed-216">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="893ed-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="893ed-217">入力</span><span class="sxs-lookup"><span data-stu-id="893ed-217">INPUTS</span></span>

### <span data-ttu-id="893ed-218">CIM インスタンス</span><span class="sxs-lookup"><span data-stu-id="893ed-218">CIM Instance</span></span>

<span data-ttu-id="893ed-219">このコマンドレットは、InputObject パラメーターで指定された入力オブジェクトを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="893ed-219">This cmdlet accepts an input objects specified with the InputObject parameter.</span></span>

## <span data-ttu-id="893ed-220">出力</span><span class="sxs-lookup"><span data-stu-id="893ed-220">OUTPUTS</span></span>

### <span data-ttu-id="893ed-221">CIM インスタンス</span><span class="sxs-lookup"><span data-stu-id="893ed-221">CIM Instance</span></span>

<span data-ttu-id="893ed-222">このコマンドレットは、cim サーバー上の CIM インスタンスのスナップショットを表す1つ以上の CIM インスタンスオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="893ed-222">This cmdlet returns one or more CIM instance objects representing a snapshot of the CIM instances on the CIM server.</span></span>

## <span data-ttu-id="893ed-223">注</span><span class="sxs-lookup"><span data-stu-id="893ed-223">NOTES</span></span>

## <span data-ttu-id="893ed-224">関連リンク</span><span class="sxs-lookup"><span data-stu-id="893ed-224">RELATED LINKS</span></span>

[<span data-ttu-id="893ed-225">Format-Table</span><span class="sxs-lookup"><span data-stu-id="893ed-225">Format-Table</span></span>](../microsoft.powershell.utility/format-table.md)

[<span data-ttu-id="893ed-226">Get-CimAssociatedInstance</span><span class="sxs-lookup"><span data-stu-id="893ed-226">Get-CimAssociatedInstance</span></span>](Get-CimAssociatedInstance.md)

[<span data-ttu-id="893ed-227">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="893ed-227">Get-CimClass</span></span>](Get-CimClass.md)

[<span data-ttu-id="893ed-228">Invoke-CimMethod</span><span class="sxs-lookup"><span data-stu-id="893ed-228">Invoke-CimMethod</span></span>](invoke-cimmethod.md)

[<span data-ttu-id="893ed-229">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="893ed-229">New-CimInstance</span></span>](New-CimInstance.md)

[<span data-ttu-id="893ed-230">Register-CimIndicationEvent</span><span class="sxs-lookup"><span data-stu-id="893ed-230">Register-CimIndicationEvent</span></span>](Register-CimIndicationEvent.md)

[<span data-ttu-id="893ed-231">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="893ed-231">Remove-CimInstance</span></span>](remove-ciminstance.md)

[<span data-ttu-id="893ed-232">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="893ed-232">Set-CimInstance</span></span>](Set-CimInstance.md)

