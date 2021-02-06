---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-ciminstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimInstance
ms.openlocfilehash: d81117ad6885d660e31f031bd8134096db91b7da
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602174"
---
# <span data-ttu-id="9379a-102">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="9379a-102">New-CimInstance</span></span>

## <span data-ttu-id="9379a-103">概要</span><span class="sxs-lookup"><span data-stu-id="9379a-103">SYNOPSIS</span></span>
<span data-ttu-id="9379a-104">CIM インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9379a-104">Creates a CIM instance.</span></span>

## <span data-ttu-id="9379a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9379a-105">SYNTAX</span></span>

### <span data-ttu-id="9379a-106">ClassNameComputerSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="9379a-106">ClassNameComputerSet (Default)</span></span>

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9379a-107">ClassNameSessionSet</span><span class="sxs-lookup"><span data-stu-id="9379a-107">ClassNameSessionSet</span></span>

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9379a-108">ResourceUriSessionSet</span><span class="sxs-lookup"><span data-stu-id="9379a-108">ResourceUriSessionSet</span></span>

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9379a-109">ResourceUriComputerSet</span><span class="sxs-lookup"><span data-stu-id="9379a-109">ResourceUriComputerSet</span></span>

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9379a-110">CimClassSessionSet</span><span class="sxs-lookup"><span data-stu-id="9379a-110">CimClassSessionSet</span></span>

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9379a-111">CimClassComputerSet</span><span class="sxs-lookup"><span data-stu-id="9379a-111">CimClassComputerSet</span></span>

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9379a-112">Description</span><span class="sxs-lookup"><span data-stu-id="9379a-112">DESCRIPTION</span></span>

<span data-ttu-id="9379a-113">この `New-CimInstance` コマンドレットは、ローカルコンピューターまたはリモートコンピューターのクラス定義に基づいて、CIM クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9379a-113">The `New-CimInstance` cmdlet creates an instance of a CIM class based on the class definition on either the local computer or a remote computer.</span></span> <span data-ttu-id="9379a-114">既定では、 `New-CimInstance` コマンドレットは、ローカルコンピューター上にインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9379a-114">By default, the `New-CimInstance` cmdlet creates an instance on the local computer.</span></span>

## <span data-ttu-id="9379a-115">例</span><span class="sxs-lookup"><span data-stu-id="9379a-115">EXAMPLES</span></span>

### <span data-ttu-id="9379a-116">例 1: CIM クラスのインスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="9379a-116">Example 1: Create an instance of a CIM class</span></span>

<span data-ttu-id="9379a-117">この例では、コンピューターのルート/cimv2 名前空間に win32_environment という名前の CIM クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9379a-117">This example creates an instance of a CIM Class named win32_environment in the root/cimv2 namespace on the computer.</span></span>

```powershell
New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";VariableValue="testvalue";UserName="domain\user"}
```

<span data-ttu-id="9379a-118">クラスが存在しない場合、プロパティが間違っている場合、またはサーバーが呼び出しを拒否した場合、クライアント側の検証は実行されません。</span><span class="sxs-lookup"><span data-stu-id="9379a-118">No client side validation is performed if the class does not exist, the properties are wrong, or if the server rejects the call.</span></span> <span data-ttu-id="9379a-119">インスタンスが正常に作成された場合は、新しく作成されたインスタンスがコマンドレットによって出力されます。</span><span class="sxs-lookup"><span data-stu-id="9379a-119">If the instance is created successfully, the cmdlet outputs the newly created instance.</span></span>

### <span data-ttu-id="9379a-120">例 2: クラススキーマを使用して CIM クラスのインスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="9379a-120">Example 2: Create an instance of a CIM class using a class schema</span></span>

<span data-ttu-id="9379a-121">この例では、CIM クラスオブジェクトを取得し、という名前の変数に格納し `$class` ます。</span><span class="sxs-lookup"><span data-stu-id="9379a-121">This example retrieves a CIM class object and stores it in a variable named `$class`.</span></span> <span data-ttu-id="9379a-122">次に、変数の内容がコマンドレットに渡され `New-CimInstance` ます。</span><span class="sxs-lookup"><span data-stu-id="9379a-122">The contents of the variable are then passed to the `New-CimInstance` cmdlet.</span></span>

```powershell
$class = Get-CimClass -ClassName Win32_Environment
New-CimInstance -CimClass $class -Property @{Name="testvar";VariableValue="testvalue";UserName="Contoso\User1"}
```

### <span data-ttu-id="9379a-123">例 3: クライアントで動的インスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="9379a-123">Example 3: Create a dynamic instance on the client</span></span>

<span data-ttu-id="9379a-124">この例では、サーバーからインスタンスを取得せずに、 **Win32_Process** という名前の CIM クラスの動的インスタンスをクライアントコンピューターに作成します。</span><span class="sxs-lookup"><span data-stu-id="9379a-124">This example creates a dynamic instance of a CIM class named **Win32_Process** on the client computer without getting the instance from the server.</span></span> <span data-ttu-id="9379a-125">新しいインスタンスは変数に格納され `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="9379a-125">The new instance is stored in the variable `$a`.</span></span> <span data-ttu-id="9379a-126">この動的インスタンスは、このキーを持つインスタンスがサーバー上に存在する場合に、操作を実行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="9379a-126">This dynamic instance can be used to perform operations if the instance with this key exists on the server.</span></span>

```powershell
$a = New-CimInstance -ClassName Win32_Process -Property @{Handle=0} -Key Handle -ClientOnly
Get-CimInstance -CimInstance $a
Invoke-CimMethod -CimInstance $a -MethodName GetOwner
```

```Output
ProcessId Name                HandleCount WorkingSetSize VirtualSize
--------- ----                ----------- -------------- -----------
0         System Idle Process 0           8192           8192

Domain         :
ReturnValue    : 2
User           :
PSComputerName :
```

<span data-ttu-id="9379a-127">次に、 `Get-CimInstance` コマンドレットは、特定の単一のインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9379a-127">The `Get-CimInstance` cmdlet then retrieves a particular single instance.</span></span> <span data-ttu-id="9379a-128">コマンドレットでは、取得した `Invoke-CimMethod` インスタンスの **GetOwner** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9379a-128">The `Invoke-CimMethod` cmdlet calls the **GetOwner** method on the retrieved instance.</span></span>

### <span data-ttu-id="9379a-129">例 4: 特定の名前空間の CIM クラスのインスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="9379a-129">Example 4: Create an instance for a CIM class of a specific namespace</span></span>

<span data-ttu-id="9379a-130">この例では、名前空間の **ルートまたは場所** にある **MSFT_Something** という名前の CIM クラスのインスタンスを取得し、という名前の変数に格納し `$class` ます。</span><span class="sxs-lookup"><span data-stu-id="9379a-130">This example gets an instance of a CIM class named **MSFT_Something** in the namespace **root/somewhere** and stores it in a variable named `$class`.</span></span> <span data-ttu-id="9379a-131">変数は、 `New-CimInstance` 新しい CIM インスタンスを作成し、新しいインスタンスでクライアント側の検証を実行するために、コマンドレットに渡されます。</span><span class="sxs-lookup"><span data-stu-id="9379a-131">The variable is passed to the `New-CimInstance` cmdlet to create a new CIM instance and perform client side validations on the new instance.</span></span>

```powershell
$class = Get-CimClass -ClassName MSFT_Something -Namespace root/somewhere
New-CimInstance -CimClass $class -Property @{"Prop1"=1;"Prop2"="value"} -ClientOnly
```

<span data-ttu-id="9379a-132">この例では、 **ClassName** パラメーターの代わりに **CimClass** パラメーターを使用して、 **Prop1** と **Prop2** が実際に存在し、キーが正しくマークされていることを検証します。</span><span class="sxs-lookup"><span data-stu-id="9379a-132">In this example, using the **CimClass** parameter instead of the **ClassName** parameter validates that **Prop1** and **Prop2** actually exist and that the keys are marked correctly.</span></span>

<span data-ttu-id="9379a-133">**Clientonly** パラメーターと共に **ComputerName** パラメーターまたは **CimSession** パラメーターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9379a-133">You cannot use the **ComputerName** or **CimSession** parameter with the **ClientOnly** parameter.</span></span>

## <span data-ttu-id="9379a-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9379a-134">PARAMETERS</span></span>

### <span data-ttu-id="9379a-135">-CimClass</span><span class="sxs-lookup"><span data-stu-id="9379a-135">-CimClass</span></span>

<span data-ttu-id="9379a-136">インスタンスの型を表す CIM クラスオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="9379a-136">Specifies a CIM class object that represents the type of the instance.</span></span> <span data-ttu-id="9379a-137">コマンドレットを使用して、 `Get-CimClass` コンピューターからクラス宣言を取得します。</span><span class="sxs-lookup"><span data-stu-id="9379a-137">Use the `Get-CimClass` cmdlet to retrieve the class declaration from a computer.</span></span> <span data-ttu-id="9379a-138">このパラメーターを使用すると、クライアント側のスキーマ検証の精度が向上します。</span><span class="sxs-lookup"><span data-stu-id="9379a-138">Using this parameter results in better client side schema validations.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimClass
Parameter Sets: CimClassSessionSet, CimClassComputerSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9379a-139">-CimSession</span><span class="sxs-lookup"><span data-stu-id="9379a-139">-CimSession</span></span>

<span data-ttu-id="9379a-140">指定された CIM セッションを使用してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9379a-140">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="9379a-141">CIM セッションを含む変数、またはやコマンドレットなどの CIM セッションを作成または取得するコマンドを入力し `New-CimSession` `Get-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="9379a-141">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="9379a-142">詳細については、「 [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9379a-142">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ClassNameSessionSet, ResourceUriSessionSet, CimClassSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9379a-143">-ClassName</span><span class="sxs-lookup"><span data-stu-id="9379a-143">-ClassName</span></span>

<span data-ttu-id="9379a-144">操作によってインスタンスが作成される CIM クラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9379a-144">Specifies the name of the CIM class of which the operation creates an instance.</span></span> <span data-ttu-id="9379a-145">メモ: クラス名の一覧を提供するために、PowerShell ではローカル WMI サーバーからクラスの一覧を取得するため、タブ補完を使用してクラスの一覧を参照できます。</span><span class="sxs-lookup"><span data-stu-id="9379a-145">NOTE: You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

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

### <span data-ttu-id="9379a-146">-ClientOnly</span><span class="sxs-lookup"><span data-stu-id="9379a-146">-ClientOnly</span></span>

<span data-ttu-id="9379a-147">インスタンスが、CIM サーバーに移動せずに PowerShell でのみ作成されることを示します。</span><span class="sxs-lookup"><span data-stu-id="9379a-147">Indicates that the instance is only created in PowerShell without going to the CIM server.</span></span> <span data-ttu-id="9379a-148">このパラメーターを使用すると、後続の PowerShell 操作で使用するために、メモリ内 CIM インスタンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9379a-148">You can use this parameter to create an in-memory CIM instance for use in subsequent PowerShell operations.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, CimClassSessionSet, CimClassComputerSet
Aliases: Local

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9379a-149">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="9379a-149">-ComputerName</span></span>

<span data-ttu-id="9379a-150">CIM 操作を実行するコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9379a-150">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="9379a-151">完全修飾ドメイン名 (FQDN)、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9379a-151">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="9379a-152">このパラメーターを指定すると、コマンドレットは WSMan プロトコルを使用して、指定されたコンピューターへの一時的なセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="9379a-152">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WSMan protocol.</span></span>

<span data-ttu-id="9379a-153">このパラメーターを指定しない場合、コマンドレットはコンポーネントオブジェクトモデル (COM) を使用してローカルコンピューター上で操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9379a-153">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="9379a-154">複数の操作が同じコンピューター上で実行されている場合、CIM セッションを使用して接続するとパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="9379a-154">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriComputerSet, CimClassComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9379a-155">-Key</span><span class="sxs-lookup"><span data-stu-id="9379a-155">-Key</span></span>

<span data-ttu-id="9379a-156">キーとして使用されるプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="9379a-156">Specifies the properties that are used as keys.</span></span> <span data-ttu-id="9379a-157">**CimSession** と **ComputerName** は、 **Key** が指定されている場合は使用できません。</span><span class="sxs-lookup"><span data-stu-id="9379a-157">**CimSession** and **ComputerName** cannot be used when **Key** is specified.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9379a-158">-Namespace</span><span class="sxs-lookup"><span data-stu-id="9379a-158">-Namespace</span></span>

<span data-ttu-id="9379a-159">新しいインスタンスのクラスの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="9379a-159">Specifies the namespace of the class for the new instance.</span></span> <span data-ttu-id="9379a-160">既定の名前空間は **root/cimv2** です。</span><span class="sxs-lookup"><span data-stu-id="9379a-160">The default namespace is **root/cimv2**.</span></span>
<span data-ttu-id="9379a-161">タブ補完を使用して名前空間の一覧を参照することができます。これは、名前空間の一覧を提供するために、PowerShell がローカル WMI サーバーから名前空間の一覧を取得するためです。</span><span class="sxs-lookup"><span data-stu-id="9379a-161">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9379a-162">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="9379a-162">-OperationTimeoutSec</span></span>

<span data-ttu-id="9379a-163">コマンドレットが CIM サーバーからの応答を待機する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="9379a-163">Specifies the amount of time that the cmdlet waits for a response from the CIM server.</span></span> <span data-ttu-id="9379a-164">既定では、このパラメーターの値は0です。これは、コマンドレットがサーバーの既定のタイムアウト値を使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="9379a-164">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span> <span data-ttu-id="9379a-165">**Operationtimeoutsec** パラメーターが、堅牢な接続再試行タイムアウトの3分未満の値に設定されている場合、 **operationtimeoutsec** パラメーターの値を超えるネットワークエラーは復旧できません。これは、クライアントが再接続する前に、サーバー上の操作がタイムアウトになるためです。</span><span class="sxs-lookup"><span data-stu-id="9379a-165">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="9379a-166">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="9379a-166">-Property</span></span>

<span data-ttu-id="9379a-167">ハッシュテーブル (名前と値のペア) を使用して、CIM インスタンスのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="9379a-167">Specifies the properties of the CIM instance using a hash table (name-value pairs).</span></span>

<span data-ttu-id="9379a-168">**CimClass** パラメーターを指定した場合、 `New-CimInstance` コマンドレットは、指定されたプロパティがサーバー上のクラス宣言と一致することを確認するために、クライアントでプロパティの検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="9379a-168">If you specify the **CimClass** parameter, then the `New-CimInstance` cmdlet performs a property validation on the client to make sure that the properties specified are consistent with the class declaration on the server.</span></span> <span data-ttu-id="9379a-169">**CimClass** パラメーターが指定されていない場合、プロパティの検証はサーバーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="9379a-169">If the **CimClass** parameter is not specified, then the property validation is done on the server.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases: Arguments

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9379a-170">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="9379a-170">-ResourceUri</span></span>

<span data-ttu-id="9379a-171">リソースクラスまたはインスタンスのリソース URI (uniform resource identifier) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9379a-171">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="9379a-172">URI は、ディスクやプロセスなど、コンピューター上の特定の種類のリソースを特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9379a-172">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="9379a-173">URI は、プレフィックスとリソースのパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="9379a-173">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="9379a-174">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9379a-174">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="9379a-175">既定では、このパラメーターを指定しない場合、DMTF 標準リソース URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` が使用され、クラス名が追加されます。</span><span class="sxs-lookup"><span data-stu-id="9379a-175">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="9379a-176">**ResourceURI** は、wsman プロトコルを使用して作成された cim セッションでのみ使用できます。また、wsman を使用して cim セッションを作成する **ComputerName** パラメーターを指定する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9379a-176">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="9379a-177">**ComputerName** パラメーターを指定せずにこのパラメーターを指定した場合、または dcom プロトコルを使用して作成された CIM セッションを指定した場合は、dcom プロトコルで **ResourceURI** パラメーターがサポートされていないため、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="9379a-177">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="9379a-178">**ResourceUri** パラメーターと **filter** パラメーターの両方が指定されている場合、 **filter** パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="9379a-178">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9379a-179">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9379a-179">-Confirm</span></span>

<span data-ttu-id="9379a-180">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9379a-180">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9379a-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9379a-181">-WhatIf</span></span>

<span data-ttu-id="9379a-182">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="9379a-182">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9379a-183">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="9379a-183">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9379a-184">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9379a-184">CommonParameters</span></span>

<span data-ttu-id="9379a-185">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9379a-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9379a-186">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9379a-186">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9379a-187">入力</span><span class="sxs-lookup"><span data-stu-id="9379a-187">INPUTS</span></span>

### <span data-ttu-id="9379a-188">なし</span><span class="sxs-lookup"><span data-stu-id="9379a-188">None</span></span>

<span data-ttu-id="9379a-189">このコマンドレットは、入力オブジェクトを受け入れません。</span><span class="sxs-lookup"><span data-stu-id="9379a-189">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="9379a-190">出力</span><span class="sxs-lookup"><span data-stu-id="9379a-190">OUTPUTS</span></span>

### <span data-ttu-id="9379a-191">System.Object</span><span class="sxs-lookup"><span data-stu-id="9379a-191">System.Object</span></span>

<span data-ttu-id="9379a-192">このコマンドレットは、CIM インスタンス情報を格納しているオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="9379a-192">This cmdlet returns an object that contains the CIM instance information.</span></span>

## <span data-ttu-id="9379a-193">注</span><span class="sxs-lookup"><span data-stu-id="9379a-193">NOTES</span></span>

## <span data-ttu-id="9379a-194">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9379a-194">RELATED LINKS</span></span>

[<span data-ttu-id="9379a-195">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="9379a-195">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="9379a-196">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="9379a-196">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="9379a-197">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="9379a-197">Remove-CimInstance</span></span>](remove-ciminstance.md)

[<span data-ttu-id="9379a-198">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="9379a-198">Set-CimInstance</span></span>](Set-CimInstance.md)

