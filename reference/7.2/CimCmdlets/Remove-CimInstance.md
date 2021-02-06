---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 05/15/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/remove-ciminstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CimInstance
ms.openlocfilehash: 5a23aaa59eb10ff35ecefb7365d3294cdb06f781
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600387"
---
# <span data-ttu-id="2774d-102">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="2774d-102">Remove-CimInstance</span></span>

## <span data-ttu-id="2774d-103">概要</span><span class="sxs-lookup"><span data-stu-id="2774d-103">SYNOPSIS</span></span>
<span data-ttu-id="2774d-104">コンピューターから CIM インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="2774d-104">Removes a CIM instance from a computer.</span></span>

## <span data-ttu-id="2774d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2774d-105">SYNTAX</span></span>

### <span data-ttu-id="2774d-106">CimInstanceComputerSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="2774d-106">CimInstanceComputerSet (Default)</span></span>

```
Remove-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2774d-107">CimInstanceSessionSet</span><span class="sxs-lookup"><span data-stu-id="2774d-107">CimInstanceSessionSet</span></span>

```
Remove-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2774d-108">QuerySessionSet</span><span class="sxs-lookup"><span data-stu-id="2774d-108">QuerySessionSet</span></span>

```
Remove-CimInstance -CimSession <CimSession[]> [[-Namespace] <String>]
 [-OperationTimeoutSec <UInt32>] [-Query] <String> [-QueryDialect <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="2774d-109">QueryComputerSet</span><span class="sxs-lookup"><span data-stu-id="2774d-109">QueryComputerSet</span></span>

```
Remove-CimInstance [-ComputerName <String[]>] [[-Namespace] <String>]
 [-OperationTimeoutSec <UInt32>] [-Query] <String> [-QueryDialect <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="2774d-110">Description</span><span class="sxs-lookup"><span data-stu-id="2774d-110">DESCRIPTION</span></span>

<span data-ttu-id="2774d-111">このコマンドレットは、cim サーバーから CIM インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="2774d-111">This cmdlet removes a CIM instance from a CIM server.</span></span> <span data-ttu-id="2774d-112">削除する CIM インスタンスを指定するには、コマンドレットで取得した CIM インスタンスオブジェクトを使用するか、 `Get-CimInstance` クエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="2774d-112">You can specify the CIM instance to remove by using either a CIM instance object retrieved by the `Get-CimInstance` cmdlet, or by specifying a query.</span></span>

<span data-ttu-id="2774d-113">**InputObject** パラメーターが指定されていない場合、コマンドレットは次のいずれかの方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="2774d-113">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="2774d-114">**ComputerName** パラメーターも **CimSession** パラメーターも指定しない場合、このコマンドレットはコンポーネントオブジェクトモデル (COM) セッションを使用してローカル Windows Management Instrumentation (WMI) で動作します。</span><span class="sxs-lookup"><span data-stu-id="2774d-114">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="2774d-115">**Computername** パラメーターまたは **CimSession** パラメーターを指定した場合、このコマンドレットは、 **computername** パラメーターまたは **CIMSESSION** パラメーターで指定された CIM サーバーに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="2774d-115">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

## <span data-ttu-id="2774d-116">例</span><span class="sxs-lookup"><span data-stu-id="2774d-116">EXAMPLES</span></span>

### <span data-ttu-id="2774d-117">例 1: CIM インスタンスを削除する</span><span class="sxs-lookup"><span data-stu-id="2774d-117">Example 1: Remove the CIM instance</span></span>

<span data-ttu-id="2774d-118">この例では、**クエリ** パラメーターを使用して、文字列 **持つ testvar** で始まる **Win32_Environment** という名前のクラスから CIM インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="2774d-118">This example use the **Query** parameter to remove CIM instances from the class named **Win32_Environment** that start with the character string **testvar** .</span></span>

```powershell
Remove-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"'
```

### <span data-ttu-id="2774d-119">例 2: CIM インスタンスオブジェクトを使用して CIM インスタンスを削除する</span><span class="sxs-lookup"><span data-stu-id="2774d-119">Example 2: Remove the CIM instance using CIM instance object</span></span>

<span data-ttu-id="2774d-120">この例では、 **クエリ** パラメーターによってフィルター処理された CIM インスタンスオブジェクトを取得し、 `$var` コマンドレットを使用してという名前の変数に格納し `Get-CimInstance` ます。</span><span class="sxs-lookup"><span data-stu-id="2774d-120">This example retrieves the CIM instance objects filtered by the **Query** parameter and stores them in variable named `$var` using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="2774d-121">次に、変数の内容をコマンドレットに渡して、 `Remove-CimInstance` CIM インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="2774d-121">The contents of the variable are then passed to the `Remove-CimInstance` cmdlet, which removes the CIM instances.</span></span>

```powershell
notepad.exe
$var = Get-CimInstance -Query 'Select * from Win32_Process where name LIKE "notepad%"'
Remove-CimInstance -InputObject $var
```

## <span data-ttu-id="2774d-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2774d-122">PARAMETERS</span></span>

### <span data-ttu-id="2774d-123">-CimSession</span><span class="sxs-lookup"><span data-stu-id="2774d-123">-CimSession</span></span>

<span data-ttu-id="2774d-124">指定された CIM セッションを使用してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2774d-124">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="2774d-125">CIM セッションを含む変数、またはやコマンドレットなどの CIM セッションを作成または取得するコマンドを入力し `New-CimSession` `Get-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="2774d-125">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="2774d-126">詳細については、「 [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2774d-126">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

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

### <span data-ttu-id="2774d-127">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="2774d-127">-ComputerName</span></span>

<span data-ttu-id="2774d-128">CIM 操作を実行するコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2774d-128">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="2774d-129">完全修飾ドメイン名 (FQDN) または NetBIOS 名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2774d-129">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

<span data-ttu-id="2774d-130">このパラメーターを指定すると、コマンドレットは WsMan プロトコルを使用して、指定されたコンピューターへの一時的なセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2774d-130">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="2774d-131">このパラメーターを指定しない場合、コマンドレットはコンポーネントオブジェクトモデル (COM) を使用してローカルコンピューター上で操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2774d-131">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="2774d-132">複数の操作が同じコンピューター上で実行されている場合、CIM セッションを使用して接続するとパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="2774d-132">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

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

### <span data-ttu-id="2774d-133">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2774d-133">-InputObject</span></span>

<span data-ttu-id="2774d-134">CIM サーバーから削除する CIM インスタンスオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="2774d-134">Specifies a CIM instance object to be removed from the CIM server.</span></span> <span data-ttu-id="2774d-135">コマンドレットに渡されたオブジェクトは変更されません。 CIM サーバーのインスタンスのみが削除されます。</span><span class="sxs-lookup"><span data-stu-id="2774d-135">The object passed to the cmdlet is not changed, only the instance in the CIM server is removed.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases: CimInstance

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2774d-136">-Namespace</span><span class="sxs-lookup"><span data-stu-id="2774d-136">-Namespace</span></span>

<span data-ttu-id="2774d-137">CIM 操作の名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="2774d-137">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="2774d-138">既定の名前空間は **root/cimv2** です。</span><span class="sxs-lookup"><span data-stu-id="2774d-138">The default namespace is **root/cimv2**.</span></span> <span data-ttu-id="2774d-139">タブ補完を使用して名前空間の一覧を参照することができます。これは、名前空間の一覧を提供するために、PowerShell がローカル WMI サーバーから名前空間の一覧を取得するためです。</span><span class="sxs-lookup"><span data-stu-id="2774d-139">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2774d-140">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="2774d-140">-OperationTimeoutSec</span></span>

<span data-ttu-id="2774d-141">コマンドレットがコンピューターからの応答を待機する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="2774d-141">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="2774d-142">既定では、このパラメーターの値は0です。これは、コマンドレットがサーバーの既定のタイムアウト値を使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="2774d-142">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="2774d-143">**Operationtimeoutsec** パラメーターが、堅牢な接続再試行タイムアウトの3分未満の値に設定されている場合、 **operationtimeoutsec** パラメーターの値を超えるネットワークエラーは復旧できません。これは、クライアントが再接続する前に、サーバー上の操作がタイムアウトになるためです。</span><span class="sxs-lookup"><span data-stu-id="2774d-143">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="2774d-144">-Query</span><span class="sxs-lookup"><span data-stu-id="2774d-144">-Query</span></span>

<span data-ttu-id="2774d-145">CIM サーバーで実行するクエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="2774d-145">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="2774d-146">**Querydialect** パラメーターを使用して、クエリ言語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2774d-146">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

<span data-ttu-id="2774d-147">指定した値に二重引用符 ( `"` )、単一引用符 ( `'` )、または円記号 () が含まれている場合は `\` 、円記号 () を付けることにより、これらの文字をエスケープする必要があり `\` ます。</span><span class="sxs-lookup"><span data-stu-id="2774d-147">If the value specified contains double quotes (`"`), single quotes (`'`), or a backslash (`\`), you must escape those characters by prefixing them with the backslash (`\`) character.</span></span> <span data-ttu-id="2774d-148">指定された値が WQL LIKE 演算子を使用する場合は、次の文字を角かっこ () で囲むことによってエスケープする必要があります `[]` : パーセント () `%` 、アンダースコア ( `_` )、または左角かっこ ( `[` )。</span><span class="sxs-lookup"><span data-stu-id="2774d-148">If the value specified uses the WQL LIKE operator, then you must escape the following characters by enclosing them in square brackets (`[]`): percent (`%`), underscore (`_`), or opening square bracket (`[`).</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2774d-149">-QueryDialect</span><span class="sxs-lookup"><span data-stu-id="2774d-149">-QueryDialect</span></span>

<span data-ttu-id="2774d-150">クエリパラメーターに使用するクエリ言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="2774d-150">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="2774d-151">このパラメーターに指定できる値は、 **WQL** または **cql** です。</span><span class="sxs-lookup"><span data-stu-id="2774d-151">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span> <span data-ttu-id="2774d-152">既定値は **WQL** です。</span><span class="sxs-lookup"><span data-stu-id="2774d-152">The default value is **WQL**.</span></span>

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

### <span data-ttu-id="2774d-153">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="2774d-153">-ResourceUri</span></span>

<span data-ttu-id="2774d-154">リソースクラスまたはインスタンスのリソース URI (uniform resource identifier) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2774d-154">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="2774d-155">URI は、ディスクやプロセスなど、コンピューター上の特定の種類のリソースを特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2774d-155">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="2774d-156">URI は、プレフィックスとリソースのパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="2774d-156">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="2774d-157">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2774d-157">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="2774d-158">既定では、このパラメーターを指定しない場合、DMTF 標準リソース URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` が使用され、クラス名が追加されます。</span><span class="sxs-lookup"><span data-stu-id="2774d-158">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="2774d-159">ResourceURI は、WSMan プロトコルを使用して作成された CIM セッションでのみ使用できます。また、WSMan を使用して CIM セッションを作成する ComputerName パラメーターを指定する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2774d-159">ResourceURI can only be used with CIM sessions created using the WSMan protocol, or when specifying the ComputerName parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="2774d-160">ComputerName パラメーターを指定せずにこのパラメーターを指定した場合、または DCOM プロトコルを使用して作成された CIM セッションを指定した場合、DCOM プロトコルでは ResourceURI パラメーターがサポートされないため、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2774d-160">If you specify this parameter without specifying the ComputerName parameter, or if you specify a CIM session created using DCOM protocol, you get an error, because the DCOM protocol does not support the ResourceURI parameter.</span></span>

<span data-ttu-id="2774d-161">**ResourceUri** パラメーターと **filter** パラメーターの両方が指定されている場合、 **filter** パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="2774d-161">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

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

### <span data-ttu-id="2774d-162">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2774d-162">-Confirm</span></span>

<span data-ttu-id="2774d-163">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2774d-163">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2774d-164">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2774d-164">-WhatIf</span></span>

<span data-ttu-id="2774d-165">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="2774d-165">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2774d-166">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2774d-166">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2774d-167">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2774d-167">CommonParameters</span></span>

<span data-ttu-id="2774d-168">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2774d-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2774d-169">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2774d-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2774d-170">入力</span><span class="sxs-lookup"><span data-stu-id="2774d-170">INPUTS</span></span>

### <span data-ttu-id="2774d-171">なし</span><span class="sxs-lookup"><span data-stu-id="2774d-171">None</span></span>

<span data-ttu-id="2774d-172">このコマンドレットは、入力オブジェクトを受け入れません。</span><span class="sxs-lookup"><span data-stu-id="2774d-172">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="2774d-173">出力</span><span class="sxs-lookup"><span data-stu-id="2774d-173">OUTPUTS</span></span>

### <span data-ttu-id="2774d-174">なし</span><span class="sxs-lookup"><span data-stu-id="2774d-174">None</span></span>

<span data-ttu-id="2774d-175">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="2774d-175">This cmdlet produces no outputs.</span></span>

## <span data-ttu-id="2774d-176">注</span><span class="sxs-lookup"><span data-stu-id="2774d-176">NOTES</span></span>

## <span data-ttu-id="2774d-177">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2774d-177">RELATED LINKS</span></span>

[<span data-ttu-id="2774d-178">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="2774d-178">New-CimInstance</span></span>](New-CimInstance.md)

[<span data-ttu-id="2774d-179">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="2774d-179">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="2774d-180">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="2774d-180">Set-CimInstance</span></span>](Set-CimInstance.md)

