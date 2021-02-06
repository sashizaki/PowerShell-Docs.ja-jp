---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 05/15/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/set-ciminstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-CimInstance
ms.openlocfilehash: 041ef2d5b5541c250b98003099fe58018df155c2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605168"
---
# <span data-ttu-id="93b73-102">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="93b73-102">Set-CimInstance</span></span>

## <span data-ttu-id="93b73-103">概要</span><span class="sxs-lookup"><span data-stu-id="93b73-103">SYNOPSIS</span></span>
<span data-ttu-id="93b73-104">Cim クラスの ModifyInstance メソッドを呼び出すことによって、cim サーバー上の CIM インスタンスを変更します。</span><span class="sxs-lookup"><span data-stu-id="93b73-104">Modifies a CIM instance on a CIM server by calling the ModifyInstance method of the CIM class.</span></span>

## <span data-ttu-id="93b73-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="93b73-105">SYNTAX</span></span>

### <span data-ttu-id="93b73-106">CimInstanceComputerSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="93b73-106">CimInstanceComputerSet (Default)</span></span>

```
Set-CimInstance [-ComputerName <String[]>] [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-Property <IDictionary>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="93b73-107">CimInstanceSessionSet</span><span class="sxs-lookup"><span data-stu-id="93b73-107">CimInstanceSessionSet</span></span>

```
Set-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-Property <IDictionary>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="93b73-108">QuerySessionSet</span><span class="sxs-lookup"><span data-stu-id="93b73-108">QuerySessionSet</span></span>

```
Set-CimInstance -CimSession <CimSession[]> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-Query] <String> [-QueryDialect <String>] -Property <IDictionary> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="93b73-109">QueryComputerSet</span><span class="sxs-lookup"><span data-stu-id="93b73-109">QueryComputerSet</span></span>

```
Set-CimInstance [-ComputerName <String[]>] [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-Query] <String> [-QueryDialect <String>] -Property <IDictionary> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="93b73-110">Description</span><span class="sxs-lookup"><span data-stu-id="93b73-110">DESCRIPTION</span></span>

<span data-ttu-id="93b73-111">このコマンドレットは、CIM サーバー上の CIM インスタンスを変更します。</span><span class="sxs-lookup"><span data-stu-id="93b73-111">This cmdlet modifies a CIM instance on a CIM server.</span></span>

<span data-ttu-id="93b73-112">**InputObject** パラメーターが指定されていない場合、コマンドレットは次のいずれかの方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="93b73-112">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="93b73-113">**ComputerName** パラメーターも **CimSession** パラメーターも指定しない場合、このコマンドレットはコンポーネントオブジェクトモデル (COM) セッションを使用してローカル Windows Management Instrumentation (WMI) で動作します。</span><span class="sxs-lookup"><span data-stu-id="93b73-113">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="93b73-114">**Computername** パラメーターまたは **CimSession** パラメーターを指定した場合、このコマンドレットは、 **computername** パラメーターまたは **CIMSESSION** パラメーターで指定された CIM サーバーに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="93b73-114">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="93b73-115">**InputObject** パラメーターが指定されている場合、コマンドレットは次のいずれかの方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="93b73-115">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="93b73-116">**ComputerName** パラメーターも **CimSession** パラメーターも指定しない場合、このコマンドレットは入力オブジェクトの CIM セッションまたはコンピューター名を使用します。</span><span class="sxs-lookup"><span data-stu-id="93b73-116">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="93b73-117">**Computername** パラメーターまたは **CimSession** パラメーターのいずれかが指定されている場合、このコマンドレットは **CimSession** パラメーター値または **computername** パラメーター値を使用します。</span><span class="sxs-lookup"><span data-stu-id="93b73-117">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the **CimSession** parameter value or **ComputerName** parameter value.</span></span> <span data-ttu-id="93b73-118">これはあまり一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="93b73-118">This is not very common.</span></span>

## <span data-ttu-id="93b73-119">例</span><span class="sxs-lookup"><span data-stu-id="93b73-119">EXAMPLES</span></span>

### <span data-ttu-id="93b73-120">例 1: CIM インスタンスを設定する</span><span class="sxs-lookup"><span data-stu-id="93b73-120">Example 1: Set the CIM instance</span></span>

<span data-ttu-id="93b73-121">この例では、**クエリ** パラメーターを使用して、[**変数の値** のプロパティの値を **abcd** に設定します。</span><span class="sxs-lookup"><span data-stu-id="93b73-121">This example sets the value of the **VariableValue** property to **abcd** using the **Query** parameter.</span></span> <span data-ttu-id="93b73-122">WQL (Windows Management Instrumentation Query Language) クエリと一致するインスタンスを変更できます。</span><span class="sxs-lookup"><span data-stu-id="93b73-122">You can modify instances matching a Windows Management Instrumentation Query Language (WQL) query.</span></span>

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"}
```

### <span data-ttu-id="93b73-123">例 2: パイプラインを使用して CIM インスタンスのプロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="93b73-123">Example 2: Set the CIM instance property using pipeline</span></span>

<span data-ttu-id="93b73-124">この例では、コマンドレットを使用して、 **クエリ** パラメーターによってフィルター処理された CIM インスタンスオブジェクトを取得し `Get-CimInstance` ます。</span><span class="sxs-lookup"><span data-stu-id="93b73-124">This example retrieves the CIM instance object filtered by the **Query** parameter using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="93b73-125">`Set-CimInstance`コマンドレットでは、[**変数** の値の値プロパティの値を **abcd** に変更します。</span><span class="sxs-lookup"><span data-stu-id="93b73-125">The `Set-CimInstance` cmdlet modifies the value of **VariableValue** property to **abcd**.</span></span>

```powershell
Get-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' |
  Set-CimInstance -Property @{VariableValue="abcd"}
```

### <span data-ttu-id="93b73-126">例 3: 入力オブジェクトを使用して CIM インスタンスのプロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="93b73-126">Example 3: Set the CIM instance property using input object</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Environment where Name="testvar"'
Set-CimInstance -InputObject $x -Property @{VariableValue="somevalue"} -PassThru
```

<span data-ttu-id="93b73-127">この例では、クエリパラメーターによってフィルター処理された CIM インスタンスオブジェクトを、を使用して変数に取得し、その `$x` `Get-CimInstance` 変数の内容を `Set-CimInstance` コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="93b73-127">This example retrieves the CIM instance objects filtered by the Query parameter in to a variable `$x` using `Get-CimInstance`, and then passes the contents of the variable to the `Set-CimInstance` cmdlet.</span></span> <span data-ttu-id="93b73-128">`Set-CimInstance` 次に、[ **変数の値** ] プロパティを **値** に変更します。</span><span class="sxs-lookup"><span data-stu-id="93b73-128">`Set-CimInstance` then modifies the **VariableValue** property to **somevalue**.</span></span> <span data-ttu-id="93b73-129">**Passthru** パラメーターが使用されているため、この例では変更された CIM インスタンスオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="93b73-129">Because the **Passthru** parameter is used, This example returns a modified CIM instance object.</span></span>

### <span data-ttu-id="93b73-130">例 4: CIM インスタンスのプロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="93b73-130">Example 4: Set the CIM instance property</span></span>

<span data-ttu-id="93b73-131">この例では、コマンドレットを使用して、 **クエリ** パラメーターに指定されている CIM インスタンスオブジェクトを変数に取得 `$x` `Get-CimInstance` し、変更するオブジェクトの変数 **値** プロパティの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="93b73-131">This example retrieves the CIM instance object that is specified in the **Query** parameter into a variable `$x` using the `Get-CimInstance` cmdlet, and changes the **VariableValue** property value of the object to change.</span></span> <span data-ttu-id="93b73-132">次に、コマンドレットを使用して CIM インスタンスオブジェクトを保存し `Set-CimInstance` ます。</span><span class="sxs-lookup"><span data-stu-id="93b73-132">The CIM instance object is then saved using the `Set-CimInstance` cmdlet.</span></span>
<span data-ttu-id="93b73-133">**Passthru** パラメーターが使用されているため、この例では変更された CIM インスタンスオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="93b73-133">Because the **Passthru** parameter is used, This example returns a modified CIM instance object.</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Environment where name="testvar"'
$x.VariableValue = "Change"
Set-CimInstance -CimInstance $x -PassThru
```

### <span data-ttu-id="93b73-134">例 5: WhatIf を使用して変更する CIM インスタンスの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="93b73-134">Example 5: Show the list of CIM instances to modify using WhatIf</span></span>

<span data-ttu-id="93b73-135">この例では、一般的なパラメーター **WhatIf** を使用して、変更を実行しないように指定していますが、実行された場合に発生することを出力します。</span><span class="sxs-lookup"><span data-stu-id="93b73-135">This example uses the common parameter **WhatIf** to specify that the modification should not be done, but only output what would happen if it were done.</span></span>

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"} -WhatIf
```

### <span data-ttu-id="93b73-136">例 6: ユーザーからの確認後に CIM インスタンスを設定する</span><span class="sxs-lookup"><span data-stu-id="93b73-136">Example 6: Set the CIM instance after confirmation from the user</span></span>

<span data-ttu-id="93b73-137">この例では、共通パラメーター **Confirm** を使用して、ユーザーからの確認後にのみ変更を行うように指定しています。</span><span class="sxs-lookup"><span data-stu-id="93b73-137">This example uses the common parameter **Confirm** to specify that the modification should be done only after confirmation from the user.</span></span>

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"} -Confirm
```

### <span data-ttu-id="93b73-138">例 7: 作成した CIM インスタンスを設定する</span><span class="sxs-lookup"><span data-stu-id="93b73-138">Example 7: Set the created CIM instance</span></span>

<span data-ttu-id="93b73-139">この例では、コマンドレットを使用して、指定したプロパティを持つ CIM インスタンスを作成 `New-CimInstance` し、その内容を変数に取得し `$x` ます。</span><span class="sxs-lookup"><span data-stu-id="93b73-139">This example creates a CIM instance with the specified properties using the `New-CimInstance` cmdlet, and retrieves its contents in to a variable `$x`.</span></span> <span data-ttu-id="93b73-140">次に、変数がコマンドレットに渡されます。これにより、変数 variable `Set-CimInstance` **value** プロパティの値が任意の **値** に変更されます。</span><span class="sxs-lookup"><span data-stu-id="93b73-140">The variable is then passed to the `Set-CimInstance` cmdlet, which modifies the value of **VariableValue** property to **somevalue**.</span></span>
<span data-ttu-id="93b73-141">**Passthru** パラメーターが使用されているため、この例では変更された CIM インスタンスオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="93b73-141">Because the **Passthru** parameter is used, This example returns a modified CIM instance object.</span></span>

```powershell
$x = New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";UserName="domain\user"} -Keys Name,UserName -ClientOnly
Set-CimInstance -CimInstance $x -Property @{VariableValue="somevalue"} -PassThru
```

## <span data-ttu-id="93b73-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="93b73-142">PARAMETERS</span></span>

### <span data-ttu-id="93b73-143">-CimSession</span><span class="sxs-lookup"><span data-stu-id="93b73-143">-CimSession</span></span>

<span data-ttu-id="93b73-144">リモートコンピューターでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="93b73-144">Runs the cmdlets on a remote computer.</span></span> <span data-ttu-id="93b73-145">またはコマンドレットの出力など、コンピューター名またはセッションオブジェクトを入力し `New-CimSession` `Get-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="93b73-145">Enter a computer name or a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimInstanceSessionSet, QuerySessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="93b73-146">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="93b73-146">-ComputerName</span></span>

<span data-ttu-id="93b73-147">CIM 操作を実行するコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="93b73-147">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="93b73-148">完全修飾ドメイン名 (FQDN) または NetBIOS 名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="93b73-148">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

<span data-ttu-id="93b73-149">このパラメーターを指定しない場合、コマンドレットはコンポーネントオブジェクトモデル (COM) を使用してローカルコンピューター上で操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="93b73-149">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="93b73-150">このパラメーターを指定すると、コマンドレットは WsMan プロトコルを使用して、指定されたコンピューターへの一時的なセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="93b73-150">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="93b73-151">複数の操作が同じコンピューター上で実行されている場合、CIM セッションを使用して接続するとパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="93b73-151">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CimInstanceComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93b73-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="93b73-152">-InputObject</span></span>

<span data-ttu-id="93b73-153">入力として使用する CIM インスタンスオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="93b73-153">Specifies a CIM instance object to use as input.</span></span>

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

### <span data-ttu-id="93b73-154">-Namespace</span><span class="sxs-lookup"><span data-stu-id="93b73-154">-Namespace</span></span>

<span data-ttu-id="93b73-155">CIM 操作の名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="93b73-155">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="93b73-156">既定の名前空間は root/cimv2 です。</span><span class="sxs-lookup"><span data-stu-id="93b73-156">The default namespace is root/cimv2.</span></span> <span data-ttu-id="93b73-157">タブ補完を使用して名前空間の一覧を参照することができます。これは、名前空間の一覧を提供するために、PowerShell がローカル WMI サーバーから名前空間の一覧を取得するためです。</span><span class="sxs-lookup"><span data-stu-id="93b73-157">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="93b73-158">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="93b73-158">-OperationTimeoutSec</span></span>

<span data-ttu-id="93b73-159">コマンドレットがコンピューターからの応答を待機する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="93b73-159">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="93b73-160">既定では、このパラメーターの値は0です。これは、コマンドレットがサーバーの既定のタイムアウト値を使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="93b73-160">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="93b73-161">**Operationtimeoutsec** パラメーターが、堅牢な接続再試行タイムアウトの3分未満の値に設定されている場合、 **operationtimeoutsec** パラメーターの値を超えるネットワークエラーは復旧できません。これは、クライアントが再接続する前に、サーバー上の操作がタイムアウトになるためです。</span><span class="sxs-lookup"><span data-stu-id="93b73-161">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="93b73-162">-PassThru</span><span class="sxs-lookup"><span data-stu-id="93b73-162">-PassThru</span></span>

<span data-ttu-id="93b73-163">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="93b73-163">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="93b73-164">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="93b73-164">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="93b73-165">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="93b73-165">-Property</span></span>

<span data-ttu-id="93b73-166">(名前と値のペアを使用して) CIM インスタンスのプロパティをハッシュテーブルとして指定します。</span><span class="sxs-lookup"><span data-stu-id="93b73-166">Specifies the properties of the CIM instance as a hash table (using name-value pairs).</span></span> <span data-ttu-id="93b73-167">このパラメーターを使用して指定されたプロパティのみが変更されます。</span><span class="sxs-lookup"><span data-stu-id="93b73-167">Only the properties specified using this parameter are changed.</span></span> <span data-ttu-id="93b73-168">CIM インスタンスのその他のプロパティは変更されません。</span><span class="sxs-lookup"><span data-stu-id="93b73-168">Other properties of the CIM instance are not changed.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet, QuerySessionSet, QueryComputerSet
Aliases: Arguments

Required: True (QuerySessionSet, QueryComputerSet), False (CimInstanceComputerSet, CimInstanceSessionSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="93b73-169">-Query</span><span class="sxs-lookup"><span data-stu-id="93b73-169">-Query</span></span>

<span data-ttu-id="93b73-170">コマンドレットを実行する CIM インスタンスを取得するために CIM サーバーで実行するクエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="93b73-170">Specifies a query to run on the CIM server to retrieve CIM instances on which to run the cmdlet.</span></span> <span data-ttu-id="93b73-171">QueryDialect パラメーターを使用して、クエリ言語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="93b73-171">You can specify the query dialect using the QueryDialect parameter.</span></span>

<span data-ttu-id="93b73-172">指定した値に二重引用符 ( `"` )、単一引用符 ( `'` )、または円記号 () が含まれている場合は `\` 、円記号 () を付けることにより、これらの文字をエスケープする必要があり `\` ます。</span><span class="sxs-lookup"><span data-stu-id="93b73-172">If the value specified contains double quotes (`"`), single quotes (`'`), or a backslash (`\`), you must escape those characters by prefixing them with the backslash (`\`) character.</span></span> <span data-ttu-id="93b73-173">指定された値が WQL **LIKE** 演算子を使用する場合は、次の文字を角かっこ () で囲むことによってエスケープする必要があります `[]` : パーセント () `%` 、アンダースコア ( `_` )、または左角かっこ ( `[` )。</span><span class="sxs-lookup"><span data-stu-id="93b73-173">If the value specified uses the WQL **LIKE** operator, then you must escape the following characters by enclosing them in square brackets (`[]`): percent (`%`), underscore (`_`), or opening square bracket (`[`).</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="93b73-174">-QueryDialect</span><span class="sxs-lookup"><span data-stu-id="93b73-174">-QueryDialect</span></span>

<span data-ttu-id="93b73-175">クエリパラメーターに使用するクエリ言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="93b73-175">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="93b73-176">このパラメーターに指定できる値は、 **WQL** または **cql** です。</span><span class="sxs-lookup"><span data-stu-id="93b73-176">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span> <span data-ttu-id="93b73-177">既定値は **WQL** です。</span><span class="sxs-lookup"><span data-stu-id="93b73-177">The default value is **WQL**.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="93b73-178">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="93b73-178">-ResourceUri</span></span>

<span data-ttu-id="93b73-179">リソースクラスまたはインスタンスのリソース URI (uniform resource identifier) を指定します。</span><span class="sxs-lookup"><span data-stu-id="93b73-179">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="93b73-180">URI は、ディスクやプロセスなど、コンピューター上の特定の種類のリソースを特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="93b73-180">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="93b73-181">URI は、プレフィックスとリソースのパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="93b73-181">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="93b73-182">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="93b73-182">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="93b73-183">既定では、このパラメーターを指定しない場合、DMTF 標準リソース URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` が使用され、クラス名が追加されます。</span><span class="sxs-lookup"><span data-stu-id="93b73-183">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="93b73-184">ResourceURI は、WSMan プロトコルを使用して作成された CIM セッションでのみ使用できます。また、WSMan を使用して CIM セッションを作成する ComputerName パラメーターを指定する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="93b73-184">ResourceURI can only be used with CIM sessions created using the WSMan protocol, or when specifying the ComputerName parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="93b73-185">ComputerName パラメーターを指定せずにこのパラメーターを指定した場合、または DCOM プロトコルを使用して作成された CIM セッションを指定した場合は、DCOM プロトコルで ResourceURI パラメーターがサポートされていないため、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="93b73-185">If you specify this parameter without specifying the ComputerName parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the ResourceURI parameter.</span></span>

<span data-ttu-id="93b73-186">**ResourceUri** パラメーターと **filter** パラメーターの両方が指定されている場合、 **filter** パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="93b73-186">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="93b73-187">-Confirm</span><span class="sxs-lookup"><span data-stu-id="93b73-187">-Confirm</span></span>

<span data-ttu-id="93b73-188">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="93b73-188">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="93b73-189">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="93b73-189">-WhatIf</span></span>

<span data-ttu-id="93b73-190">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="93b73-190">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="93b73-191">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="93b73-191">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="93b73-192">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="93b73-192">CommonParameters</span></span>

<span data-ttu-id="93b73-193">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="93b73-193">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="93b73-194">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93b73-194">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="93b73-195">入力</span><span class="sxs-lookup"><span data-stu-id="93b73-195">INPUTS</span></span>

### <span data-ttu-id="93b73-196">Microsoft.Management.Infrastructure.CimInstance</span><span class="sxs-lookup"><span data-stu-id="93b73-196">Microsoft.Management.Infrastructure.CimInstance</span></span>

## <span data-ttu-id="93b73-197">出力</span><span class="sxs-lookup"><span data-stu-id="93b73-197">OUTPUTS</span></span>

### <span data-ttu-id="93b73-198">Microsoft.Management.Infrastructure.CimInstance</span><span class="sxs-lookup"><span data-stu-id="93b73-198">Microsoft.Management.Infrastructure.CimInstance</span></span>

<span data-ttu-id="93b73-199">**Passthru** パラメーターを指定すると、このコマンドレットは、変更された CIM インスタンスオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="93b73-199">When the **Passthru** parameter is specified, this cmdlet returns a modified CIM instance object.</span></span>

## <span data-ttu-id="93b73-200">注</span><span class="sxs-lookup"><span data-stu-id="93b73-200">NOTES</span></span>

## <span data-ttu-id="93b73-201">関連リンク</span><span class="sxs-lookup"><span data-stu-id="93b73-201">RELATED LINKS</span></span>

[<span data-ttu-id="93b73-202">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="93b73-202">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="93b73-203">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="93b73-203">New-CimInstance</span></span>](New-CimInstance.md)

[<span data-ttu-id="93b73-204">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="93b73-204">Remove-CimInstance</span></span>](remove-ciminstance.md)

