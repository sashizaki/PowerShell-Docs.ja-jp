---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-ciminstance?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimInstance
ms.openlocfilehash: d6eab5d6fcf1c4d983f2502465d76ad5df1db9dd
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218115"
---
# <span data-ttu-id="764fb-103">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="764fb-103">New-CimInstance</span></span>

## <span data-ttu-id="764fb-104">概要</span><span class="sxs-lookup"><span data-stu-id="764fb-104">SYNOPSIS</span></span>
<span data-ttu-id="764fb-105">CIM インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="764fb-105">Creates a CIM instance.</span></span>

## <span data-ttu-id="764fb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="764fb-106">SYNTAX</span></span>

### <span data-ttu-id="764fb-107">ClassNameComputerSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="764fb-107">ClassNameComputerSet (Default)</span></span>

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="764fb-108">ClassNameSessionSet</span><span class="sxs-lookup"><span data-stu-id="764fb-108">ClassNameSessionSet</span></span>

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="764fb-109">ResourceUriSessionSet</span><span class="sxs-lookup"><span data-stu-id="764fb-109">ResourceUriSessionSet</span></span>

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="764fb-110">ResourceUriComputerSet</span><span class="sxs-lookup"><span data-stu-id="764fb-110">ResourceUriComputerSet</span></span>

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="764fb-111">CimClassSessionSet</span><span class="sxs-lookup"><span data-stu-id="764fb-111">CimClassSessionSet</span></span>

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="764fb-112">CimClassComputerSet</span><span class="sxs-lookup"><span data-stu-id="764fb-112">CimClassComputerSet</span></span>

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="764fb-113">Description</span><span class="sxs-lookup"><span data-stu-id="764fb-113">DESCRIPTION</span></span>

<span data-ttu-id="764fb-114">この `New-CimInstance` コマンドレットは、ローカルコンピューターまたはリモートコンピューターのクラス定義に基づいて、CIM クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="764fb-114">The `New-CimInstance` cmdlet creates an instance of a CIM class based on the class definition on either the local computer or a remote computer.</span></span> <span data-ttu-id="764fb-115">既定では、 `New-CimInstance` コマンドレットは、ローカルコンピューター上にインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="764fb-115">By default, the `New-CimInstance` cmdlet creates an instance on the local computer.</span></span>

## <span data-ttu-id="764fb-116">例</span><span class="sxs-lookup"><span data-stu-id="764fb-116">EXAMPLES</span></span>

### <span data-ttu-id="764fb-117">例 1: CIM クラスのインスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="764fb-117">Example 1: Create an instance of a CIM class</span></span>

<span data-ttu-id="764fb-118">この例では、コンピューターのルート/cimv2 名前空間に win32_environment という名前の CIM クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="764fb-118">This example creates an instance of a CIM Class named win32_environment in the root/cimv2 namespace on the computer.</span></span>

```powershell
New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";VariableValue="testvalue";UserName="domain\user"}
```

<span data-ttu-id="764fb-119">クラスが存在しない場合、プロパティが間違っている場合、またはサーバーが呼び出しを拒否した場合、クライアント側の検証は実行されません。</span><span class="sxs-lookup"><span data-stu-id="764fb-119">No client side validation is performed if the class does not exist, the properties are wrong, or if the server rejects the call.</span></span> <span data-ttu-id="764fb-120">インスタンスが正常に作成された場合は、新しく作成されたインスタンスがコマンドレットによって出力されます。</span><span class="sxs-lookup"><span data-stu-id="764fb-120">If the instance is created successfully, the cmdlet outputs the newly created instance.</span></span>

### <span data-ttu-id="764fb-121">例 2: クラススキーマを使用して CIM クラスのインスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="764fb-121">Example 2: Create an instance of a CIM class using a class schema</span></span>

<span data-ttu-id="764fb-122">この例では、CIM クラスオブジェクトを取得し、という名前の変数に格納し `$class` ます。</span><span class="sxs-lookup"><span data-stu-id="764fb-122">This example retrieves a CIM class object and stores it in a variable named `$class`.</span></span> <span data-ttu-id="764fb-123">次に、変数の内容がコマンドレットに渡され `New-CimInstance` ます。</span><span class="sxs-lookup"><span data-stu-id="764fb-123">The contents of the variable are then passed to the `New-CimInstance` cmdlet.</span></span>

```powershell
$class = Get-CimClass -ClassName Win32_Environment
New-CimInstance -CimClass $class -Property @{Name="testvar";VariableValue="testvalue";UserName="Contoso\User1"}
```

### <span data-ttu-id="764fb-124">例 3: クライアントで動的インスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="764fb-124">Example 3: Create a dynamic instance on the client</span></span>

<span data-ttu-id="764fb-125">この例では、サーバーからインスタンスを取得せずに、 **Win32_Process** という名前の CIM クラスの動的インスタンスをクライアントコンピューターに作成します。</span><span class="sxs-lookup"><span data-stu-id="764fb-125">This example creates a dynamic instance of a CIM class named **Win32_Process** on the client computer without getting the instance from the server.</span></span> <span data-ttu-id="764fb-126">新しいインスタンスは変数に格納され `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="764fb-126">The new instance is stored in the variable `$a`.</span></span> <span data-ttu-id="764fb-127">この動的インスタンスは、このキーを持つインスタンスがサーバー上に存在する場合に、操作を実行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="764fb-127">This dynamic instance can be used to perform operations if the instance with this key exists on the server.</span></span>

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

<span data-ttu-id="764fb-128">次に、 `Get-CimInstance` コマンドレットは、特定の単一のインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="764fb-128">The `Get-CimInstance` cmdlet then retrieves a particular single instance.</span></span> <span data-ttu-id="764fb-129">コマンドレットでは、取得した `Invoke-CimMethod` インスタンスの **GetOwner** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="764fb-129">The `Invoke-CimMethod` cmdlet calls the **GetOwner** method on the retrieved instance.</span></span>

### <span data-ttu-id="764fb-130">例 4: 特定の名前空間の CIM クラスのインスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="764fb-130">Example 4: Create an instance for a CIM class of a specific namespace</span></span>

<span data-ttu-id="764fb-131">この例では、名前空間の **ルートまたは場所** にある **MSFT_Something** という名前の CIM クラスのインスタンスを取得し、という名前の変数に格納し `$class` ます。</span><span class="sxs-lookup"><span data-stu-id="764fb-131">This example gets an instance of a CIM class named **MSFT_Something** in the namespace **root/somewhere** and stores it in a variable named `$class`.</span></span> <span data-ttu-id="764fb-132">変数は、 `New-CimInstance` 新しい CIM インスタンスを作成し、新しいインスタンスでクライアント側の検証を実行するために、コマンドレットに渡されます。</span><span class="sxs-lookup"><span data-stu-id="764fb-132">The variable is passed to the `New-CimInstance` cmdlet to create a new CIM instance and perform client side validations on the new instance.</span></span>

```powershell
$class = Get-CimClass -ClassName MSFT_Something -Namespace root/somewhere
New-CimInstance -CimClass $class -Property @{"Prop1"=1;"Prop2"="value"} -ClientOnly
```

<span data-ttu-id="764fb-133">この例では、 **ClassName** パラメーターの代わりに **CimClass** パラメーターを使用して、 **Prop1** と **Prop2** が実際に存在し、キーが正しくマークされていることを検証します。</span><span class="sxs-lookup"><span data-stu-id="764fb-133">In this example, using the **CimClass** parameter instead of the **ClassName** parameter validates that **Prop1** and **Prop2** actually exist and that the keys are marked correctly.</span></span>

<span data-ttu-id="764fb-134">**Clientonly** パラメーターと共に **ComputerName** パラメーターまたは **CimSession** パラメーターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="764fb-134">You cannot use the **ComputerName** or **CimSession** parameter with the **ClientOnly** parameter.</span></span>

## <span data-ttu-id="764fb-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="764fb-135">PARAMETERS</span></span>

### <span data-ttu-id="764fb-136">-CimClass</span><span class="sxs-lookup"><span data-stu-id="764fb-136">-CimClass</span></span>

<span data-ttu-id="764fb-137">インスタンスの型を表す CIM クラスオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="764fb-137">Specifies a CIM class object that represents the type of the instance.</span></span> <span data-ttu-id="764fb-138">コマンドレットを使用して、 `Get-CimClass` コンピューターからクラス宣言を取得します。</span><span class="sxs-lookup"><span data-stu-id="764fb-138">Use the `Get-CimClass` cmdlet to retrieve the class declaration from a computer.</span></span> <span data-ttu-id="764fb-139">このパラメーターを使用すると、クライアント側のスキーマ検証の精度が向上します。</span><span class="sxs-lookup"><span data-stu-id="764fb-139">Using this parameter results in better client side schema validations.</span></span>

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

### <span data-ttu-id="764fb-140">-CimSession</span><span class="sxs-lookup"><span data-stu-id="764fb-140">-CimSession</span></span>

<span data-ttu-id="764fb-141">指定された CIM セッションを使用してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="764fb-141">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="764fb-142">CIM セッションを含む変数、またはやコマンドレットなどの CIM セッションを作成または取得するコマンドを入力し `New-CimSession` `Get-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="764fb-142">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="764fb-143">詳細については、「 [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="764fb-143">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

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

### <span data-ttu-id="764fb-144">-ClassName</span><span class="sxs-lookup"><span data-stu-id="764fb-144">-ClassName</span></span>

<span data-ttu-id="764fb-145">操作によってインスタンスが作成される CIM クラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="764fb-145">Specifies the name of the CIM class of which the operation creates an instance.</span></span> <span data-ttu-id="764fb-146">メモ: クラス名の一覧を提供するために、PowerShell ではローカル WMI サーバーからクラスの一覧を取得するため、タブ補完を使用してクラスの一覧を参照できます。</span><span class="sxs-lookup"><span data-stu-id="764fb-146">NOTE: You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

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

### <span data-ttu-id="764fb-147">-ClientOnly</span><span class="sxs-lookup"><span data-stu-id="764fb-147">-ClientOnly</span></span>

<span data-ttu-id="764fb-148">インスタンスが、CIM サーバーに移動せずに PowerShell でのみ作成されることを示します。</span><span class="sxs-lookup"><span data-stu-id="764fb-148">Indicates that the instance is only created in PowerShell without going to the CIM server.</span></span> <span data-ttu-id="764fb-149">このパラメーターを使用すると、後続の PowerShell 操作で使用するために、メモリ内 CIM インスタンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="764fb-149">You can use this parameter to create an in-memory CIM instance for use in subsequent PowerShell operations.</span></span>

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

### <span data-ttu-id="764fb-150">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="764fb-150">-ComputerName</span></span>

<span data-ttu-id="764fb-151">CIM 操作を実行するコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="764fb-151">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="764fb-152">完全修飾ドメイン名 (FQDN)、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="764fb-152">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="764fb-153">このパラメーターを指定すると、コマンドレットは WSMan プロトコルを使用して、指定されたコンピューターへの一時的なセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="764fb-153">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WSMan protocol.</span></span>

<span data-ttu-id="764fb-154">このパラメーターを指定しない場合、コマンドレットはコンポーネントオブジェクトモデル (COM) を使用してローカルコンピューター上で操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="764fb-154">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="764fb-155">複数の操作が同じコンピューター上で実行されている場合、CIM セッションを使用して接続するとパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="764fb-155">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

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

### <span data-ttu-id="764fb-156">-キー</span><span class="sxs-lookup"><span data-stu-id="764fb-156">-Key</span></span>

<span data-ttu-id="764fb-157">キーとして使用されるプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="764fb-157">Specifies the properties that are used as keys.</span></span> <span data-ttu-id="764fb-158">**CimSession** と **ComputerName** は、 **Key** が指定されている場合は使用できません。</span><span class="sxs-lookup"><span data-stu-id="764fb-158">**CimSession** and **ComputerName** cannot be used when **Key** is specified.</span></span>

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

### <span data-ttu-id="764fb-159">-Namespace</span><span class="sxs-lookup"><span data-stu-id="764fb-159">-Namespace</span></span>

<span data-ttu-id="764fb-160">新しいインスタンスのクラスの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="764fb-160">Specifies the namespace of the class for the new instance.</span></span> <span data-ttu-id="764fb-161">既定の名前空間は **root/cimv2** です。</span><span class="sxs-lookup"><span data-stu-id="764fb-161">The default namespace is **root/cimv2**.</span></span>
<span data-ttu-id="764fb-162">タブ補完を使用して名前空間の一覧を参照することができます。これは、名前空間の一覧を提供するために、PowerShell がローカル WMI サーバーから名前空間の一覧を取得するためです。</span><span class="sxs-lookup"><span data-stu-id="764fb-162">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

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

### <span data-ttu-id="764fb-163">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="764fb-163">-OperationTimeoutSec</span></span>

<span data-ttu-id="764fb-164">コマンドレットが CIM サーバーからの応答を待機する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="764fb-164">Specifies the amount of time that the cmdlet waits for a response from the CIM server.</span></span> <span data-ttu-id="764fb-165">既定では、このパラメーターの値は0です。これは、コマンドレットがサーバーの既定のタイムアウト値を使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="764fb-165">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span> <span data-ttu-id="764fb-166">**Operationtimeoutsec** パラメーターが、堅牢な接続再試行タイムアウトの3分未満の値に設定されている場合、 **operationtimeoutsec** パラメーターの値を超えるネットワークエラーは復旧できません。これは、クライアントが再接続する前に、サーバー上の操作がタイムアウトになるためです。</span><span class="sxs-lookup"><span data-stu-id="764fb-166">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="764fb-167">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="764fb-167">-Property</span></span>

<span data-ttu-id="764fb-168">ハッシュテーブル (名前と値のペア) を使用して、CIM インスタンスのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="764fb-168">Specifies the properties of the CIM instance using a hash table (name-value pairs).</span></span>

<span data-ttu-id="764fb-169">**CimClass** パラメーターを指定した場合、 `New-CimInstance` コマンドレットは、指定されたプロパティがサーバー上のクラス宣言と一致することを確認するために、クライアントでプロパティの検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="764fb-169">If you specify the **CimClass** parameter, then the `New-CimInstance` cmdlet performs a property validation on the client to make sure that the properties specified are consistent with the class declaration on the server.</span></span> <span data-ttu-id="764fb-170">**CimClass** パラメーターが指定されていない場合、プロパティの検証はサーバーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="764fb-170">If the **CimClass** parameter is not specified, then the property validation is done on the server.</span></span>

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

### <span data-ttu-id="764fb-171">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="764fb-171">-ResourceUri</span></span>

<span data-ttu-id="764fb-172">リソースクラスまたはインスタンスのリソース URI (uniform resource identifier) を指定します。</span><span class="sxs-lookup"><span data-stu-id="764fb-172">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="764fb-173">URI は、ディスクやプロセスなど、コンピューター上の特定の種類のリソースを特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="764fb-173">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="764fb-174">URI は、プレフィックスとリソースのパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="764fb-174">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="764fb-175">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="764fb-175">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="764fb-176">既定では、このパラメーターを指定しない場合、DMTF 標準リソース URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` が使用され、クラス名が追加されます。</span><span class="sxs-lookup"><span data-stu-id="764fb-176">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="764fb-177">**ResourceURI** は、wsman プロトコルを使用して作成された cim セッションでのみ使用できます。また、wsman を使用して cim セッションを作成する **ComputerName** パラメーターを指定する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="764fb-177">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="764fb-178">**ComputerName** パラメーターを指定せずにこのパラメーターを指定した場合、または dcom プロトコルを使用して作成された CIM セッションを指定した場合は、dcom プロトコルで **ResourceURI** パラメーターがサポートされていないため、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="764fb-178">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="764fb-179">**ResourceUri** パラメーターと **filter** パラメーターの両方が指定されている場合、 **filter** パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="764fb-179">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

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

### <span data-ttu-id="764fb-180">-Confirm</span><span class="sxs-lookup"><span data-stu-id="764fb-180">-Confirm</span></span>

<span data-ttu-id="764fb-181">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="764fb-181">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="764fb-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="764fb-182">-WhatIf</span></span>

<span data-ttu-id="764fb-183">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="764fb-183">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="764fb-184">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="764fb-184">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="764fb-185">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="764fb-185">CommonParameters</span></span>

<span data-ttu-id="764fb-186">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="764fb-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="764fb-187">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="764fb-187">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="764fb-188">入力</span><span class="sxs-lookup"><span data-stu-id="764fb-188">INPUTS</span></span>

### <span data-ttu-id="764fb-189">なし</span><span class="sxs-lookup"><span data-stu-id="764fb-189">None</span></span>

<span data-ttu-id="764fb-190">このコマンドレットは、入力オブジェクトを受け入れません。</span><span class="sxs-lookup"><span data-stu-id="764fb-190">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="764fb-191">出力</span><span class="sxs-lookup"><span data-stu-id="764fb-191">OUTPUTS</span></span>

### <span data-ttu-id="764fb-192">System.Object</span><span class="sxs-lookup"><span data-stu-id="764fb-192">System.Object</span></span>

<span data-ttu-id="764fb-193">このコマンドレットは、CIM インスタンス情報を格納しているオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="764fb-193">This cmdlet returns an object that contains the CIM instance information.</span></span>

## <span data-ttu-id="764fb-194">注</span><span class="sxs-lookup"><span data-stu-id="764fb-194">NOTES</span></span>

## <span data-ttu-id="764fb-195">関連リンク</span><span class="sxs-lookup"><span data-stu-id="764fb-195">RELATED LINKS</span></span>

[<span data-ttu-id="764fb-196">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="764fb-196">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="764fb-197">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="764fb-197">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="764fb-198">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="764fb-198">Remove-CimInstance</span></span>](remove-ciminstance.md)

[<span data-ttu-id="764fb-199">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="764fb-199">Set-CimInstance</span></span>](Set-CimInstance.md)
