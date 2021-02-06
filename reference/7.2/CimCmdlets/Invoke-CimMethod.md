---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 01/21/2020
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/invoke-cimmethod?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-CimMethod
ms.openlocfilehash: 1217e07d09213d7c0e223129207c085b9ba2d48d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601989"
---
# <span data-ttu-id="fb4a4-102">Invoke-CimMethod</span><span class="sxs-lookup"><span data-stu-id="fb4a4-102">Invoke-CimMethod</span></span>

## <span data-ttu-id="fb4a4-103">概要</span><span class="sxs-lookup"><span data-stu-id="fb4a4-103">SYNOPSIS</span></span>
<span data-ttu-id="fb4a4-104">CIM クラスのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-104">Invokes a method of a CIM class.</span></span>

## <span data-ttu-id="fb4a4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fb4a4-105">SYNTAX</span></span>

### <span data-ttu-id="fb4a4-106">ClassNameComputerSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="fb4a4-106">ClassNameComputerSet (Default)</span></span>

```
Invoke-CimMethod [-ClassName] <String> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="fb4a4-107">ClassNameSessionSet</span><span class="sxs-lookup"><span data-stu-id="fb4a4-107">ClassNameSessionSet</span></span>

```
Invoke-CimMethod [-ClassName] <String> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="fb4a4-108">ResourceUriComputerSet</span><span class="sxs-lookup"><span data-stu-id="fb4a4-108">ResourceUriComputerSet</span></span>

```
Invoke-CimMethod -ResourceUri <Uri> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="fb4a4-109">CimInstanceSessionSet</span><span class="sxs-lookup"><span data-stu-id="fb4a4-109">CimInstanceSessionSet</span></span>

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fb4a4-110">CimInstanceComputerSet</span><span class="sxs-lookup"><span data-stu-id="fb4a4-110">CimInstanceComputerSet</span></span>

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fb4a4-111">ResourceUriSessionSet</span><span class="sxs-lookup"><span data-stu-id="fb4a4-111">ResourceUriSessionSet</span></span>

```
Invoke-CimMethod -ResourceUri <Uri> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="fb4a4-112">CimClassComputerSet</span><span class="sxs-lookup"><span data-stu-id="fb4a4-112">CimClassComputerSet</span></span>

```
Invoke-CimMethod [-CimClass] <CimClass> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fb4a4-113">CimClassSessionSet</span><span class="sxs-lookup"><span data-stu-id="fb4a4-113">CimClassSessionSet</span></span>

```
Invoke-CimMethod [-CimClass] <CimClass> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fb4a4-114">QueryComputerSet</span><span class="sxs-lookup"><span data-stu-id="fb4a4-114">QueryComputerSet</span></span>

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fb4a4-115">QuerySessionSet</span><span class="sxs-lookup"><span data-stu-id="fb4a4-115">QuerySessionSet</span></span>

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fb4a4-116">Description</span><span class="sxs-lookup"><span data-stu-id="fb4a4-116">DESCRIPTION</span></span>

<span data-ttu-id="fb4a4-117">`Invoke-CimMethod`コマンドレットは、 **Arguments** パラメーターで指定された名前と値のペアを使用して、cim クラスまたは cim インスタンスのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-117">The `Invoke-CimMethod` cmdlet invokes a method of a CIM class or CIM instance using the name-value pairs specified by the **Arguments** parameter.</span></span>

<span data-ttu-id="fb4a4-118">**InputObject** パラメーターが指定されていない場合、コマンドレットは次のいずれかの方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-118">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="fb4a4-119">**ComputerName** パラメーターも **CimSession** パラメーターも指定しない場合、このコマンドレットはコンポーネントオブジェクトモデル (COM) セッションを使用してローカル Windows Management Instrumentation (WMI) で動作します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-119">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="fb4a4-120">**Computername** パラメーターまたは **CimSession** パラメーターを指定した場合、このコマンドレットは、 **computername** パラメーターまたは **CIMSESSION** パラメーターで指定された CIM サーバーに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-120">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="fb4a4-121">**InputObject** パラメーターが指定されている場合、コマンドレットは次のいずれかの方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-121">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="fb4a4-122">**ComputerName** パラメーターも **CimSession** パラメーターも指定しない場合、このコマンドレットは入力オブジェクトの CIM セッションまたはコンピューター名を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-122">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="fb4a4-123">**Computername** パラメーターまたは **CimSession** パラメーターのいずれかが指定されている場合、このコマンドレットは **CimSession** パラメーター値または **computername** パラメーター値を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-123">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the **CimSession** parameter value or **ComputerName** parameter value.</span></span> <span data-ttu-id="fb4a4-124">これは一般的なシナリオではありません。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-124">This is not a common scenario.</span></span>

## <span data-ttu-id="fb4a4-125">例</span><span class="sxs-lookup"><span data-stu-id="fb4a4-125">EXAMPLES</span></span>

### <span data-ttu-id="fb4a4-126">例 1: メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="fb4a4-126">Example 1: Invoke a method</span></span>

<span data-ttu-id="fb4a4-127">この例では、 **Win32_Process** クラスの **Terminate** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-127">This example invokes the **Terminate** method of the **Win32_Process** class.</span></span>

```powershell
Invoke-CimMethod -Query 'select * from Win32_Process where name like "notepad%"' -MethodName "Terminate"
```

### <span data-ttu-id="fb4a4-128">例 2: CIM インスタンスオブジェクトを使用してメソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="fb4a4-128">Example 2: Invoke a method using CIM instance object</span></span>

<span data-ttu-id="fb4a4-129">この例では、CIM インスタンスオブジェクトを取得し、 `$x` コマンドレットを使用してという名前の変数に格納し `Get-CimInstance` ます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-129">This example retrieves the CIM instance object and stores it in a variable named `$x` using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="fb4a4-130">変数の内容は、コマンドレットの **InputObject** として使用され `Invoke-CimMethod` ます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-130">The contents of the variable are then used as the **InputObject** for the `Invoke-CimMethod` cmdlet.</span></span> <span data-ttu-id="fb4a4-131">**CimInstance** に対して **GetOwner** メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-131">The **GetOwner** method is invoked for the **CimInstance**.</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Process where name like "notepad%"'
Invoke-CimMethod -InputObject $x -MethodName GetOwner
```

### <span data-ttu-id="fb4a4-132">例 3: 引数を使用して静的メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="fb4a4-132">Example 3: Invoke a static method using arguments</span></span>

<span data-ttu-id="fb4a4-133">この例では、 **Arguments** パラメーターを使用して、という名前の **Create** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-133">This example invokes the **Create** method named using the **Arguments** parameter.</span></span>

```powershell
Invoke-CimMethod -ClassName Win32_Process -MethodName "Create" -Arguments @{
  CommandLine = 'notepad.exe'; CurrentDirectory = "C:\windows\system32"
}
```

### <span data-ttu-id="fb4a4-134">例 4: クライアント側の検証</span><span class="sxs-lookup"><span data-stu-id="fb4a4-134">Example 4: Client-side validation</span></span>

<span data-ttu-id="fb4a4-135">この例では、 **CimClass** オブジェクトをに渡して、 **xyz** メソッドに対してクライアント側の検証を実行し `Invoke-CimMethod` ます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-135">This example performs client-side validation for the **xyz** method by passing a **CimClass** object to `Invoke-CimMethod`.</span></span>

```powershell
$c = Get-CimClass -ClassName Win32_Process
Invoke-CimMethod -CimClass $c -MethodName "xyz" -Arguments @{ CommandLine = 'notepad.exe' }
```

## <span data-ttu-id="fb4a4-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fb4a4-136">PARAMETERS</span></span>

### <span data-ttu-id="fb4a4-137">-Arguments</span><span class="sxs-lookup"><span data-stu-id="fb4a4-137">-Arguments</span></span>

<span data-ttu-id="fb4a4-138">呼び出したメソッドに渡すパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-138">Specifies the parameters to pass to the called method.</span></span> <span data-ttu-id="fb4a4-139">ハッシュテーブルに格納されている名前と値のペアとして、このパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-139">Specify the values for this parameter as name-value pairs, stored in a hash table.</span></span> <span data-ttu-id="fb4a4-140">入力した値の順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-140">The order of the values entered isn't important.</span></span>

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

### <span data-ttu-id="fb4a4-141">-CimClass</span><span class="sxs-lookup"><span data-stu-id="fb4a4-141">-CimClass</span></span>

<span data-ttu-id="fb4a4-142">サーバー上の CIM クラス定義を表す CIM クラスオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-142">Specifies a CIM class object that represents a CIM class definition on the server.</span></span> <span data-ttu-id="fb4a4-143">クラスの静的メソッドを呼び出すときに、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-143">Use this parameter when invoking a static method of a class.</span></span>

<span data-ttu-id="fb4a4-144">コマンドレットを使用して、 `Get-CimClass` サーバーからクラス定義を取得できます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-144">You can use the `Get-CimClass` cmdlet to retrieve a class definition from the server.</span></span>

<span data-ttu-id="fb4a4-145">このパラメーターを使用すると、クライアント側のスキーマ検証の精度が向上します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-145">Using this parameter results in better client side schema validations.</span></span>

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

### <span data-ttu-id="fb4a4-146">-CimSession</span><span class="sxs-lookup"><span data-stu-id="fb4a4-146">-CimSession</span></span>

<span data-ttu-id="fb4a4-147">指定された CIM セッションを使用してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-147">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="fb4a4-148">CIM セッションを含む変数、またはやコマンドレットなどの CIM セッションを作成または取得するコマンドを入力し `New-CimSession` `Get-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-148">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="fb4a4-149">詳細については、「 [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-149">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

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

### <span data-ttu-id="fb4a4-150">-ClassName</span><span class="sxs-lookup"><span data-stu-id="fb4a4-150">-ClassName</span></span>

<span data-ttu-id="fb4a4-151">操作を実行する CIM クラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-151">Specifies the name of the CIM class for which to perform the operation.</span></span> <span data-ttu-id="fb4a4-152">このパラメーターは、静的メソッドに対してのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-152">This parameter is only used for static methods.</span></span> <span data-ttu-id="fb4a4-153">タブ補完を使用してクラスの一覧を参照することができます。これは、クラス名の一覧を提供するために、PowerShell がローカル WMI サーバーからクラスの一覧を取得するためです。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-153">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

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

### <span data-ttu-id="fb4a4-154">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="fb4a4-154">-ComputerName</span></span>

<span data-ttu-id="fb4a4-155">CIM 操作を実行するコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-155">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="fb4a4-156">完全修飾ドメイン名 (FQDN)、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-156">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="fb4a4-157">このパラメーターを使用すると、コマンドレットは WsMan プロトコルを使用して、指定されたコンピューターへの一時的なセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-157">When using this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span> <span data-ttu-id="fb4a4-158">それ以外の場合、コマンドレットは、コンポーネントオブジェクトモデル (COM) を使用してローカルコンピューター上で操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-158">Otherwise, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="fb4a4-159">同じコンピューターで複数の操作を実行する場合は、CIM セッションを使用して接続し、パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-159">Connect using a CIM session for better performance when multiple operations are being performed on the same computer.</span></span>

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

### <span data-ttu-id="fb4a4-160">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fb4a4-160">-InputObject</span></span>

<span data-ttu-id="fb4a4-161">メソッドを呼び出すための入力として使用する CIM インスタンスオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-161">Specifies a CIM instance object to use as input to invoke a method.</span></span> <span data-ttu-id="fb4a4-162">このパラメーターは、インスタンスメソッドを呼び出すためにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-162">This parameter can only be used to invoke instance methods.</span></span> <span data-ttu-id="fb4a4-163">クラスの静的メソッドを呼び出すには、 **class** パラメーターまたは **CimClass** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-163">To invoke class static methods, use the **Class** parameter or the **CimClass** parameter.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fb4a4-164">-MethodName</span><span class="sxs-lookup"><span data-stu-id="fb4a4-164">-MethodName</span></span>

<span data-ttu-id="fb4a4-165">呼び出す CIM メソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-165">Specifies the name of the CIM method to invoke.</span></span> <span data-ttu-id="fb4a4-166">このパラメーターは必須です。Null や空にはできません。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-166">This parameter is mandatory and cannot be null or empty.</span></span> <span data-ttu-id="fb4a4-167">CIM クラスの静的メソッドを呼び出すには、 **ClassName** または **CimClass** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-167">To invoke static method of a CIM class use the **ClassName** or the **CimClass** parameter.</span></span>

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

### <span data-ttu-id="fb4a4-168">-Namespace</span><span class="sxs-lookup"><span data-stu-id="fb4a4-168">-Namespace</span></span>

<span data-ttu-id="fb4a4-169">CIM 操作の名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-169">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="fb4a4-170">既定の名前空間は **root/cimv2** です。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-170">The default namespace is **root/cimv2**.</span></span> <span data-ttu-id="fb4a4-171">タブ補完を使用して名前空間の一覧を参照することができます。これは、名前空間の一覧を提供するために、PowerShell がローカル WMI サーバーから名前空間の一覧を取得するためです。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-171">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriComputerSet, ResourceUriSessionSet, QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fb4a4-172">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="fb4a4-172">-OperationTimeoutSec</span></span>

<span data-ttu-id="fb4a4-173">コマンドレットがコンピューターからの応答を待機する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-173">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="fb4a4-174">既定値は0です。これは、コマンドレットがサーバーの既定のタイムアウト値を使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-174">By default, the value is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="fb4a4-175">**Operationtimeoutsec** パラメーターが、既定の接続再試行タイムアウトの3分未満の値に設定されている場合、 **operationtimeoutsec** パラメーターの値を超えるネットワークエラーは復旧できません。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-175">If the **OperationTimeoutSec** parameter is set to a value less than the default connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable.</span></span>

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

### <span data-ttu-id="fb4a4-176">-Query</span><span class="sxs-lookup"><span data-stu-id="fb4a4-176">-Query</span></span>

<span data-ttu-id="fb4a4-177">CIM サーバーで実行するクエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-177">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="fb4a4-178">メソッドは、クエリの結果として受信したインスタンスで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-178">A method is invoked on the instances received as a result of the query.</span></span> <span data-ttu-id="fb4a4-179">**Querydialect** パラメーターを使用して、クエリ言語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-179">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

<span data-ttu-id="fb4a4-180">指定した値に二重引用符 ( `"` )、単一引用符 ( `'` )、または円記号 () が含まれている場合は `\` 、円記号 () を付けることにより、これらの文字をエスケープする必要があり `\` ます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-180">If the value specified contains double quotes (`"`), single quotes (`'`), or a backslash (`\`), you must escape those characters by prefixing them with the backslash (`\`) character.</span></span> <span data-ttu-id="fb4a4-181">指定された値が WQL LIKE 演算子を使用する場合は、次の文字を角かっこ () で囲むことによってエスケープする必要があります `[]` : パーセント () `%` 、アンダースコア ( `_` )、または左角かっこ ( `[` )。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-181">If the value specified uses the WQL LIKE operator, then you must escape the following characters by enclosing them in square brackets (`[]`): percent (`%`), underscore (`_`), or opening square bracket (`[`).</span></span>

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

### <span data-ttu-id="fb4a4-182">-QueryDialect</span><span class="sxs-lookup"><span data-stu-id="fb4a4-182">-QueryDialect</span></span>

<span data-ttu-id="fb4a4-183">クエリパラメーターに使用するクエリ言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-183">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="fb4a4-184">このパラメーターに指定できる値は、 **WQL** または **cql** です。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-184">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span>

<span data-ttu-id="fb4a4-185">既定値は **WQL** です。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-185">The default value is **WQL**.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: WQL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fb4a4-186">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="fb4a4-186">-ResourceUri</span></span>

<span data-ttu-id="fb4a4-187">リソースクラスまたはインスタンスのリソース URI (uniform resource identifier) を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-187">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span>
<span data-ttu-id="fb4a4-188">URI は、ディスクやプロセスなど、コンピューター上の特定の種類のリソースを特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-188">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="fb4a4-189">URI は、プレフィックスとリソースのパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-189">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="fb4a4-190">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-190">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="fb4a4-191">既定では、このパラメーターを指定しない場合、DMTF 標準リソース URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` が使用され、クラス名が追加されます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-191">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="fb4a4-192">**ResourceURI** は、wsman プロトコルを使用して作成された cim セッションでのみ使用できます。また、wsman を使用して cim セッションを作成する **ComputerName** パラメーターを指定する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-192">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span>

<span data-ttu-id="fb4a4-193">**ComputerName** パラメーターを指定せずにこのパラメーターを指定するか、DCOM プロトコルを使用して作成された CIM セッションを指定すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-193">When you specify this parameter without specifying the **ComputerName** parameter, or when you specify a CIM session created using DCOM protocol, you get an error.</span></span> <span data-ttu-id="fb4a4-194">DCOM プロトコルでは、 **ResourceURI** パラメーターはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-194">The DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="fb4a4-195">**ResourceUri** パラメーターと **filter** パラメーターの両方が指定されている場合、 **filter** パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-195">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (CimInstanceSessionSet, CimInstanceComputerSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fb4a4-196">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fb4a4-196">-Confirm</span></span>

<span data-ttu-id="fb4a4-197">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-197">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fb4a4-198">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fb4a4-198">-WhatIf</span></span>

<span data-ttu-id="fb4a4-199">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-199">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="fb4a4-200">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-200">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fb4a4-201">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb4a4-201">CommonParameters</span></span>

<span data-ttu-id="fb4a4-202">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-202">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fb4a4-203">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-203">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="fb4a4-204">入力</span><span class="sxs-lookup"><span data-stu-id="fb4a4-204">INPUTS</span></span>

### <span data-ttu-id="fb4a4-205">CIM クラス</span><span class="sxs-lookup"><span data-stu-id="fb4a4-205">CIM class</span></span>

<span data-ttu-id="fb4a4-206">このコマンドレットは、入力オブジェクトとして CIM クラスを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-206">This cmdlet accepts a CIM class as an input object.</span></span>

### <span data-ttu-id="fb4a4-207">CIM インスタンス</span><span class="sxs-lookup"><span data-stu-id="fb4a4-207">CIM instance</span></span>

<span data-ttu-id="fb4a4-208">このコマンドレットは、入力オブジェクトとして CIM インスタンスを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-208">This cmdlet accepts a CIM instance as an input object.</span></span>

## <span data-ttu-id="fb4a4-209">出力</span><span class="sxs-lookup"><span data-stu-id="fb4a4-209">OUTPUTS</span></span>

### <span data-ttu-id="fb4a4-210">システムの管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="fb4a4-210">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="fb4a4-211">このコマンドレットは、オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="fb4a4-211">This cmdlet returns an object.</span></span>

## <span data-ttu-id="fb4a4-212">注</span><span class="sxs-lookup"><span data-stu-id="fb4a4-212">NOTES</span></span>

## <span data-ttu-id="fb4a4-213">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fb4a4-213">RELATED LINKS</span></span>

[<span data-ttu-id="fb4a4-214">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="fb4a4-214">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="fb4a4-215">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="fb4a4-215">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="fb4a4-216">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="fb4a4-216">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="fb4a4-217">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="fb4a4-217">New-CimSession</span></span>](New-CimSession.md)

