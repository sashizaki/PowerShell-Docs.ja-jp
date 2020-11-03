---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: CimCmdlets
ms.date: 01/21/2020
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/invoke-cimmethod?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-CimMethod
ms.openlocfilehash: 2f6e7bac8cd460b9eb9fa74d9e1aa931d33108d1
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218123"
---
# <span data-ttu-id="af18c-103">Invoke-CimMethod</span><span class="sxs-lookup"><span data-stu-id="af18c-103">Invoke-CimMethod</span></span>

## <span data-ttu-id="af18c-104">概要</span><span class="sxs-lookup"><span data-stu-id="af18c-104">SYNOPSIS</span></span>
<span data-ttu-id="af18c-105">CIM クラスのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="af18c-105">Invokes a method of a CIM class.</span></span>

## <span data-ttu-id="af18c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="af18c-106">SYNTAX</span></span>

### <span data-ttu-id="af18c-107">ClassNameComputerSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="af18c-107">ClassNameComputerSet (Default)</span></span>

```
Invoke-CimMethod [-ClassName] <String> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="af18c-108">ClassNameSessionSet</span><span class="sxs-lookup"><span data-stu-id="af18c-108">ClassNameSessionSet</span></span>

```
Invoke-CimMethod [-ClassName] <String> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="af18c-109">ResourceUriComputerSet</span><span class="sxs-lookup"><span data-stu-id="af18c-109">ResourceUriComputerSet</span></span>

```
Invoke-CimMethod -ResourceUri <Uri> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="af18c-110">CimInstanceSessionSet</span><span class="sxs-lookup"><span data-stu-id="af18c-110">CimInstanceSessionSet</span></span>

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="af18c-111">CimInstanceComputerSet</span><span class="sxs-lookup"><span data-stu-id="af18c-111">CimInstanceComputerSet</span></span>

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="af18c-112">ResourceUriSessionSet</span><span class="sxs-lookup"><span data-stu-id="af18c-112">ResourceUriSessionSet</span></span>

```
Invoke-CimMethod -ResourceUri <Uri> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="af18c-113">CimClassComputerSet</span><span class="sxs-lookup"><span data-stu-id="af18c-113">CimClassComputerSet</span></span>

```
Invoke-CimMethod [-CimClass] <CimClass> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="af18c-114">CimClassSessionSet</span><span class="sxs-lookup"><span data-stu-id="af18c-114">CimClassSessionSet</span></span>

```
Invoke-CimMethod [-CimClass] <CimClass> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="af18c-115">QueryComputerSet</span><span class="sxs-lookup"><span data-stu-id="af18c-115">QueryComputerSet</span></span>

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="af18c-116">QuerySessionSet</span><span class="sxs-lookup"><span data-stu-id="af18c-116">QuerySessionSet</span></span>

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="af18c-117">Description</span><span class="sxs-lookup"><span data-stu-id="af18c-117">DESCRIPTION</span></span>

<span data-ttu-id="af18c-118">`Invoke-CimMethod`コマンドレットは、 **Arguments** パラメーターで指定された名前と値のペアを使用して、cim クラスまたは cim インスタンスのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="af18c-118">The `Invoke-CimMethod` cmdlet invokes a method of a CIM class or CIM instance using the name-value pairs specified by the **Arguments** parameter.</span></span>

<span data-ttu-id="af18c-119">**InputObject** パラメーターが指定されていない場合、コマンドレットは次のいずれかの方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="af18c-119">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="af18c-120">**ComputerName** パラメーターも **CimSession** パラメーターも指定しない場合、このコマンドレットはコンポーネントオブジェクトモデル (COM) セッションを使用してローカル Windows Management Instrumentation (WMI) で動作します。</span><span class="sxs-lookup"><span data-stu-id="af18c-120">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="af18c-121">**Computername** パラメーターまたは **CimSession** パラメーターを指定した場合、このコマンドレットは、 **computername** パラメーターまたは **CIMSESSION** パラメーターで指定された CIM サーバーに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="af18c-121">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="af18c-122">**InputObject** パラメーターが指定されている場合、コマンドレットは次のいずれかの方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="af18c-122">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="af18c-123">**ComputerName** パラメーターも **CimSession** パラメーターも指定しない場合、このコマンドレットは入力オブジェクトの CIM セッションまたはコンピューター名を使用します。</span><span class="sxs-lookup"><span data-stu-id="af18c-123">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="af18c-124">**Computername** パラメーターまたは **CimSession** パラメーターのいずれかが指定されている場合、このコマンドレットは **CimSession** パラメーター値または **computername** パラメーター値を使用します。</span><span class="sxs-lookup"><span data-stu-id="af18c-124">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the **CimSession** parameter value or **ComputerName** parameter value.</span></span> <span data-ttu-id="af18c-125">これは一般的なシナリオではありません。</span><span class="sxs-lookup"><span data-stu-id="af18c-125">This is not a common scenario.</span></span>

## <span data-ttu-id="af18c-126">例</span><span class="sxs-lookup"><span data-stu-id="af18c-126">EXAMPLES</span></span>

### <span data-ttu-id="af18c-127">例 1: メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="af18c-127">Example 1: Invoke a method</span></span>

<span data-ttu-id="af18c-128">この例では、 **Win32_Process** クラスの **Terminate** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="af18c-128">This example invokes the **Terminate** method of the **Win32_Process** class.</span></span>

```powershell
Invoke-CimMethod -Query 'select * from Win32_Process where name like "notepad%"' -MethodName "Terminate"
```

### <span data-ttu-id="af18c-129">例 2: CIM インスタンスオブジェクトを使用してメソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="af18c-129">Example 2: Invoke a method using CIM instance object</span></span>

<span data-ttu-id="af18c-130">この例では、CIM インスタンスオブジェクトを取得し、 `$x` コマンドレットを使用してという名前の変数に格納し `Get-CimInstance` ます。</span><span class="sxs-lookup"><span data-stu-id="af18c-130">This example retrieves the CIM instance object and stores it in a variable named `$x` using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="af18c-131">変数の内容は、コマンドレットの **InputObject** として使用され `Invoke-CimMethod` ます。</span><span class="sxs-lookup"><span data-stu-id="af18c-131">The contents of the variable are then used as the **InputObject** for the `Invoke-CimMethod` cmdlet.</span></span> <span data-ttu-id="af18c-132">**CimInstance** に対して **GetOwner** メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="af18c-132">The **GetOwner** method is invoked for the **CimInstance**.</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Process where name like "notepad%"'
Invoke-CimMethod -InputObject $x -MethodName GetOwner
```

### <span data-ttu-id="af18c-133">例 3: 引数を使用して静的メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="af18c-133">Example 3: Invoke a static method using arguments</span></span>

<span data-ttu-id="af18c-134">この例では、 **Arguments** パラメーターを使用して、という名前の **Create** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="af18c-134">This example invokes the **Create** method named using the **Arguments** parameter.</span></span>

```powershell
Invoke-CimMethod -ClassName Win32_Process -MethodName "Create" -Arguments @{
  CommandLine = 'notepad.exe'; CurrentDirectory = "C:\windows\system32"
}
```

### <span data-ttu-id="af18c-135">例 4: クライアント側の検証</span><span class="sxs-lookup"><span data-stu-id="af18c-135">Example 4: Client-side validation</span></span>

<span data-ttu-id="af18c-136">この例では、 **CimClass** オブジェクトをに渡して、 **xyz** メソッドに対してクライアント側の検証を実行し `Invoke-CimMethod` ます。</span><span class="sxs-lookup"><span data-stu-id="af18c-136">This example performs client-side validation for the **xyz** method by passing a **CimClass** object to `Invoke-CimMethod`.</span></span>

```powershell
$c = Get-CimClass -ClassName Win32_Process
Invoke-CimMethod -CimClass $c -MethodName "xyz" -Arguments @{ CommandLine = 'notepad.exe' }
```

## <span data-ttu-id="af18c-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="af18c-137">PARAMETERS</span></span>

### <span data-ttu-id="af18c-138">-Arguments</span><span class="sxs-lookup"><span data-stu-id="af18c-138">-Arguments</span></span>

<span data-ttu-id="af18c-139">呼び出したメソッドに渡すパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="af18c-139">Specifies the parameters to pass to the called method.</span></span> <span data-ttu-id="af18c-140">ハッシュテーブルに格納されている名前と値のペアとして、このパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="af18c-140">Specify the values for this parameter as name-value pairs, stored in a hash table.</span></span> <span data-ttu-id="af18c-141">入力した値の順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="af18c-141">The order of the values entered isn't important.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="af18c-142">-CimClass</span><span class="sxs-lookup"><span data-stu-id="af18c-142">-CimClass</span></span>

<span data-ttu-id="af18c-143">サーバー上の CIM クラス定義を表す CIM クラスオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="af18c-143">Specifies a CIM class object that represents a CIM class definition on the server.</span></span> <span data-ttu-id="af18c-144">クラスの静的メソッドを呼び出すときに、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="af18c-144">Use this parameter when invoking a static method of a class.</span></span>

<span data-ttu-id="af18c-145">コマンドレットを使用して、 `Get-CimClass` サーバーからクラス定義を取得できます。</span><span class="sxs-lookup"><span data-stu-id="af18c-145">You can use the `Get-CimClass` cmdlet to retrieve a class definition from the server.</span></span>

<span data-ttu-id="af18c-146">このパラメーターを使用すると、クライアント側のスキーマ検証の精度が向上します。</span><span class="sxs-lookup"><span data-stu-id="af18c-146">Using this parameter results in better client side schema validations.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimClass
Parameter Sets: CimClassComputerSet, CimClassSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="af18c-147">-CimSession</span><span class="sxs-lookup"><span data-stu-id="af18c-147">-CimSession</span></span>

<span data-ttu-id="af18c-148">指定された CIM セッションを使用してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="af18c-148">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="af18c-149">CIM セッションを含む変数、またはやコマンドレットなどの CIM セッションを作成または取得するコマンドを入力し `New-CimSession` `Get-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="af18c-149">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="af18c-150">詳細については、「 [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af18c-150">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ClassNameSessionSet, CimInstanceSessionSet, CimClassSessionSet, QuerySessionSet, ResourceUriSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="af18c-151">-ClassName</span><span class="sxs-lookup"><span data-stu-id="af18c-151">-ClassName</span></span>

<span data-ttu-id="af18c-152">操作を実行する CIM クラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="af18c-152">Specifies the name of the CIM class for which to perform the operation.</span></span> <span data-ttu-id="af18c-153">このパラメーターは、静的メソッドに対してのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="af18c-153">This parameter is only used for static methods.</span></span> <span data-ttu-id="af18c-154">タブ補完を使用してクラスの一覧を参照することができます。これは、クラス名の一覧を提供するために、PowerShell がローカル WMI サーバーからクラスの一覧を取得するためです。</span><span class="sxs-lookup"><span data-stu-id="af18c-154">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases: Class

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="af18c-155">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="af18c-155">-ComputerName</span></span>

<span data-ttu-id="af18c-156">CIM 操作を実行するコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="af18c-156">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="af18c-157">完全修飾ドメイン名 (FQDN)、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="af18c-157">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="af18c-158">このパラメーターを使用すると、コマンドレットは WsMan プロトコルを使用して、指定されたコンピューターへの一時的なセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="af18c-158">When using this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span> <span data-ttu-id="af18c-159">それ以外の場合、コマンドレットは、コンポーネントオブジェクトモデル (COM) を使用してローカルコンピューター上で操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="af18c-159">Otherwise, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="af18c-160">同じコンピューターで複数の操作を実行する場合は、CIM セッションを使用して接続し、パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="af18c-160">Connect using a CIM session for better performance when multiple operations are being performed on the same computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriComputerSet, CimClassComputerSet, CimInstanceComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="af18c-161">-InputObject</span><span class="sxs-lookup"><span data-stu-id="af18c-161">-InputObject</span></span>

<span data-ttu-id="af18c-162">メソッドを呼び出すための入力として使用する CIM インスタンスオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="af18c-162">Specifies a CIM instance object to use as input to invoke a method.</span></span> <span data-ttu-id="af18c-163">このパラメーターは、インスタンスメソッドを呼び出すためにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="af18c-163">This parameter can only be used to invoke instance methods.</span></span> <span data-ttu-id="af18c-164">クラスの静的メソッドを呼び出すには、 **class** パラメーターまたは **CimClass** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="af18c-164">To invoke class static methods, use the **Class** parameter or the **CimClass** parameter.</span></span>

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

### <span data-ttu-id="af18c-165">-MethodName</span><span class="sxs-lookup"><span data-stu-id="af18c-165">-MethodName</span></span>

<span data-ttu-id="af18c-166">呼び出す CIM メソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="af18c-166">Specifies the name of the CIM method to invoke.</span></span> <span data-ttu-id="af18c-167">このパラメーターは必須です。Null や空にはできません。</span><span class="sxs-lookup"><span data-stu-id="af18c-167">This parameter is mandatory and cannot be null or empty.</span></span> <span data-ttu-id="af18c-168">CIM クラスの静的メソッドを呼び出すには、 **ClassName** または **CimClass** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="af18c-168">To invoke static method of a CIM class use the **ClassName** or the **CimClass** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="af18c-169">-Namespace</span><span class="sxs-lookup"><span data-stu-id="af18c-169">-Namespace</span></span>

<span data-ttu-id="af18c-170">CIM 操作の名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="af18c-170">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="af18c-171">既定の名前空間は **root/cimv2** です。</span><span class="sxs-lookup"><span data-stu-id="af18c-171">The default namespace is **root/cimv2**.</span></span> <span data-ttu-id="af18c-172">タブ補完を使用して名前空間の一覧を参照することができます。これは、名前空間の一覧を提供するために、PowerShell がローカル WMI サーバーから名前空間の一覧を取得するためです。</span><span class="sxs-lookup"><span data-stu-id="af18c-172">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriComputerSet, ResourceUriSessionSet, QueryComputerSet, QuerySessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="af18c-173">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="af18c-173">-OperationTimeoutSec</span></span>

<span data-ttu-id="af18c-174">コマンドレットがコンピューターからの応答を待機する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="af18c-174">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="af18c-175">既定値は0です。これは、コマンドレットがサーバーの既定のタイムアウト値を使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="af18c-175">By default, the value is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="af18c-176">**Operationtimeoutsec** パラメーターが、既定の接続再試行タイムアウトの3分未満の値に設定されている場合、 **operationtimeoutsec** パラメーターの値を超えるネットワークエラーは復旧できません。</span><span class="sxs-lookup"><span data-stu-id="af18c-176">If the **OperationTimeoutSec** parameter is set to a value less than the default connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable.</span></span>

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

### <span data-ttu-id="af18c-177">-Query</span><span class="sxs-lookup"><span data-stu-id="af18c-177">-Query</span></span>

<span data-ttu-id="af18c-178">CIM サーバーで実行するクエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="af18c-178">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="af18c-179">メソッドは、クエリの結果として受信したインスタンスで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="af18c-179">A method is invoked on the instances received as a result of the query.</span></span> <span data-ttu-id="af18c-180">**Querydialect** パラメーターを使用して、クエリ言語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="af18c-180">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

<span data-ttu-id="af18c-181">指定した値に二重引用符 ( `"` )、単一引用符 ( `'` )、または円記号 () が含まれている場合は `\` 、円記号 () を付けることにより、これらの文字をエスケープする必要があり `\` ます。</span><span class="sxs-lookup"><span data-stu-id="af18c-181">If the value specified contains double quotes (`"`), single quotes (`'`), or a backslash (`\`), you must escape those characters by prefixing them with the backslash (`\`) character.</span></span> <span data-ttu-id="af18c-182">指定された値が WQL LIKE 演算子を使用する場合は、次の文字を角かっこ () で囲むことによってエスケープする必要があります `[]` : パーセント () `%` 、アンダースコア ( `_` )、または左角かっこ ( `[` )。</span><span class="sxs-lookup"><span data-stu-id="af18c-182">If the value specified uses the WQL LIKE operator, then you must escape the following characters by enclosing them in square brackets (`[]`): percent (`%`), underscore (`_`), or opening square bracket (`[`).</span></span>

```yaml
Type: System.String
Parameter Sets: QueryComputerSet, QuerySessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="af18c-183">-QueryDialect</span><span class="sxs-lookup"><span data-stu-id="af18c-183">-QueryDialect</span></span>

<span data-ttu-id="af18c-184">クエリパラメーターに使用するクエリ言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="af18c-184">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="af18c-185">このパラメーターに指定できる値は、 **WQL** または **cql** です。</span><span class="sxs-lookup"><span data-stu-id="af18c-185">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span>

<span data-ttu-id="af18c-186">既定値は **WQL** です。</span><span class="sxs-lookup"><span data-stu-id="af18c-186">The default value is **WQL**.</span></span>

```yaml
Type: System.String
Parameter Sets: QueryComputerSet, QuerySessionSet
Aliases:

Required: False
Position: Named
Default value: WQL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="af18c-187">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="af18c-187">-ResourceUri</span></span>

<span data-ttu-id="af18c-188">リソースクラスまたはインスタンスのリソース URI (uniform resource identifier) を指定します。</span><span class="sxs-lookup"><span data-stu-id="af18c-188">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span>
<span data-ttu-id="af18c-189">URI は、ディスクやプロセスなど、コンピューター上の特定の種類のリソースを特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="af18c-189">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="af18c-190">URI は、プレフィックスとリソースのパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="af18c-190">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="af18c-191">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="af18c-191">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="af18c-192">既定では、このパラメーターを指定しない場合、DMTF 標準リソース URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` が使用され、クラス名が追加されます。</span><span class="sxs-lookup"><span data-stu-id="af18c-192">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="af18c-193">**ResourceURI** は、wsman プロトコルを使用して作成された cim セッションでのみ使用できます。また、wsman を使用して cim セッションを作成する **ComputerName** パラメーターを指定する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="af18c-193">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span>

<span data-ttu-id="af18c-194">**ComputerName** パラメーターを指定せずにこのパラメーターを指定するか、DCOM プロトコルを使用して作成された CIM セッションを指定すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="af18c-194">When you specify this parameter without specifying the **ComputerName** parameter, or when you specify a CIM session created using DCOM protocol, you get an error.</span></span> <span data-ttu-id="af18c-195">DCOM プロトコルでは、 **ResourceURI** パラメーターはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="af18c-195">The DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="af18c-196">**ResourceUri** パラメーターと **filter** パラメーターの両方が指定されている場合、 **filter** パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="af18c-196">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet, CimInstanceSessionSet, CimInstanceComputerSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (CimInstanceSessionSet, CimInstanceComputerSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="af18c-197">-Confirm</span><span class="sxs-lookup"><span data-stu-id="af18c-197">-Confirm</span></span>

<span data-ttu-id="af18c-198">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="af18c-198">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af18c-199">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="af18c-199">-WhatIf</span></span>

<span data-ttu-id="af18c-200">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="af18c-200">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="af18c-201">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="af18c-201">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af18c-202">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="af18c-202">CommonParameters</span></span>

<span data-ttu-id="af18c-203">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="af18c-203">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="af18c-204">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af18c-204">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="af18c-205">入力</span><span class="sxs-lookup"><span data-stu-id="af18c-205">INPUTS</span></span>

### <span data-ttu-id="af18c-206">CIM クラス</span><span class="sxs-lookup"><span data-stu-id="af18c-206">CIM class</span></span>

<span data-ttu-id="af18c-207">このコマンドレットは、入力オブジェクトとして CIM クラスを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="af18c-207">This cmdlet accepts a CIM class as an input object.</span></span>

### <span data-ttu-id="af18c-208">CIM インスタンス</span><span class="sxs-lookup"><span data-stu-id="af18c-208">CIM instance</span></span>

<span data-ttu-id="af18c-209">このコマンドレットは、入力オブジェクトとして CIM インスタンスを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="af18c-209">This cmdlet accepts a CIM instance as an input object.</span></span>

## <span data-ttu-id="af18c-210">出力</span><span class="sxs-lookup"><span data-stu-id="af18c-210">OUTPUTS</span></span>

### <span data-ttu-id="af18c-211">システムの管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="af18c-211">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="af18c-212">このコマンドレットは、オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="af18c-212">This cmdlet returns an object.</span></span>

## <span data-ttu-id="af18c-213">注</span><span class="sxs-lookup"><span data-stu-id="af18c-213">NOTES</span></span>

## <span data-ttu-id="af18c-214">関連リンク</span><span class="sxs-lookup"><span data-stu-id="af18c-214">RELATED LINKS</span></span>

[<span data-ttu-id="af18c-215">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="af18c-215">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="af18c-216">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="af18c-216">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="af18c-217">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="af18c-217">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="af18c-218">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="af18c-218">New-CimSession</span></span>](New-CimSession.md)
