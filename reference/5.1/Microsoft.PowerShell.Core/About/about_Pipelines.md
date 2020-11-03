---
description: PowerShell でコマンドをパイプラインに結合する
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pipelines?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Pipelines
ms.openlocfilehash: 651ba1f42743d83958d6711cff01fec030fa9a02
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224955"
---
# <a name="about-pipelines"></a><span data-ttu-id="f3084-104">パイプラインについて</span><span class="sxs-lookup"><span data-stu-id="f3084-104">About Pipelines</span></span>

## <a name="short-description"></a><span data-ttu-id="f3084-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="f3084-105">Short description</span></span>

<span data-ttu-id="f3084-106">PowerShell でコマンドをパイプラインに結合する</span><span class="sxs-lookup"><span data-stu-id="f3084-106">Combining commands into pipelines in the PowerShell</span></span>

## <a name="long-description"></a><span data-ttu-id="f3084-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="f3084-107">Long description</span></span>

<span data-ttu-id="f3084-108">パイプラインは、パイプライン演算子 () によって接続された一連のコマンドです ( `|` ASCII 124)。</span><span class="sxs-lookup"><span data-stu-id="f3084-108">A pipeline is a series of commands connected by pipeline operators (`|`) (ASCII 124).</span></span> <span data-ttu-id="f3084-109">各パイプライン演算子は、前のコマンドの結果を次のコマンドに送信します。</span><span class="sxs-lookup"><span data-stu-id="f3084-109">Each pipeline operator sends the results of the preceding command to the next command.</span></span>

<span data-ttu-id="f3084-110">最初のコマンドの出力は、2番目のコマンドの入力として処理のために送信できます。</span><span class="sxs-lookup"><span data-stu-id="f3084-110">The output of the first command can be sent for processing as input to the second command.</span></span> <span data-ttu-id="f3084-111">また、その出力を他のコマンドに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="f3084-111">And that output can be sent to yet another command.</span></span> <span data-ttu-id="f3084-112">結果として、一連の単純なコマンドで構成される複雑なコマンドチェーンまたは _パイプライン_ が生成されます。</span><span class="sxs-lookup"><span data-stu-id="f3084-112">The result is a complex command chain or _pipeline_ that is composed of a series of simple commands.</span></span>

<span data-ttu-id="f3084-113">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3084-113">For example,</span></span>

```powershell
Command-1 | Command-2 | Command-3
```

<span data-ttu-id="f3084-114">この例では、によって `Command-1` 出力されるオブジェクトがに送信され `Command-2` ます。</span><span class="sxs-lookup"><span data-stu-id="f3084-114">In this example, the objects that `Command-1` emits are sent to `Command-2`.</span></span>
<span data-ttu-id="f3084-115">`Command-2` オブジェクトを処理し、に送信し `Command-3` ます。</span><span class="sxs-lookup"><span data-stu-id="f3084-115">`Command-2` processes the objects and sends them to `Command-3`.</span></span> <span data-ttu-id="f3084-116">`Command-3` オブジェクトを処理し、パイプラインに送信します。</span><span class="sxs-lookup"><span data-stu-id="f3084-116">`Command-3` processes the objects and send them down the pipeline.</span></span> <span data-ttu-id="f3084-117">パイプラインにはこれ以上コマンドがないため、結果はコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3084-117">Because there are no more commands in the pipeline, the results are displayed at the console.</span></span>

<span data-ttu-id="f3084-118">パイプラインでは、コマンドは左から右に順番に処理されます。</span><span class="sxs-lookup"><span data-stu-id="f3084-118">In a pipeline, the commands are processed in order from left to right.</span></span> <span data-ttu-id="f3084-119">処理は単一の操作として処理され、生成されると出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3084-119">The processing is handled as a single operation and output is displayed as it's generated.</span></span>

<span data-ttu-id="f3084-120">単純な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f3084-120">Here is a simple example.</span></span> <span data-ttu-id="f3084-121">次のコマンドは、メモ帳のプロセスを取得し、それを停止します。</span><span class="sxs-lookup"><span data-stu-id="f3084-121">The following command gets the Notepad process and then stops it.</span></span>

<span data-ttu-id="f3084-122">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3084-122">For example,</span></span>

```powershell
Get-Process notepad | Stop-Process
```

<span data-ttu-id="f3084-123">最初のコマンドは、 `Get-Process` コマンドレットを使用して、メモ帳プロセスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="f3084-123">The first command uses the `Get-Process` cmdlet to get an object representing the Notepad process.</span></span> <span data-ttu-id="f3084-124">パイプライン演算子 () を使用して、 `|` プロセスオブジェクトをコマンドレットに送信します。これにより `Stop-Process` 、メモ帳のプロセスが停止します。</span><span class="sxs-lookup"><span data-stu-id="f3084-124">It uses a pipeline operator (`|`) to send the process object to the `Stop-Process` cmdlet, which stops the Notepad process.</span></span> <span data-ttu-id="f3084-125">`Stop-Process`指定されたプロセスはパイプラインを介して送信されるため、このコマンドには、プロセスを指定するための **名前** または **ID** パラメーターがありません。</span><span class="sxs-lookup"><span data-stu-id="f3084-125">Notice that the `Stop-Process` command doesn't have a **Name** or **ID** parameter to specify the process, because the specified process is submitted through the pipeline.</span></span>

<span data-ttu-id="f3084-126">このパイプラインの例では、現在のディレクトリ内のテキストファイルを取得し、1万バイトを超えるファイルのみを選択し、長さで並べ替え、各ファイルの名前と長さをテーブルに表示します。</span><span class="sxs-lookup"><span data-stu-id="f3084-126">This pipeline example gets the text files in the current directory, selects only the files that are more than 10,000 bytes long, sorts them by length, and displays the name and length of each file in a table.</span></span>

```powershell
Get-ChildItem -Path *.txt |
  Where-Object {$_.length -gt 10000} |
    Sort-Object -Property length |
      Format-Table -Property name, length
```

<span data-ttu-id="f3084-127">このパイプラインは、指定された順序で4つのコマンドで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f3084-127">This pipeline consists of four commands in the specified order.</span></span> <span data-ttu-id="f3084-128">次の図は、パイプラインの次のコマンドに渡される各コマンドからの出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="f3084-128">The following illustration shows the output from each command as it's passed to the next command in the pipeline.</span></span>

```
Get-ChildItem -Path *.txt
| (FileInfo objects for *.txt)
V
Where-Object {$_.length -gt 10000}
| (FileInfo objects for *.txt)
| (      Length > 10000      )
V
Sort-Object -Property Length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
V
Format-Table -Property name, length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
| (   Formatted in a table   )
V

Name                       Length
----                       ------
tmp1.txt                    82920
tmp2.txt                   114000
tmp3.txt                   114000
```

## <a name="using-pipelines"></a><span data-ttu-id="f3084-129">パイプラインの使用</span><span class="sxs-lookup"><span data-stu-id="f3084-129">Using pipelines</span></span>

<span data-ttu-id="f3084-130">ほとんどの PowerShell コマンドレットは、パイプラインをサポートするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="f3084-130">Most PowerShell cmdlets are designed to support pipelines.</span></span> <span data-ttu-id="f3084-131">ほとんどの場合、 **Get** コマンドレットの結果を同じ名詞の別のコマンドレットに _パイプ_ することができます。</span><span class="sxs-lookup"><span data-stu-id="f3084-131">In most cases, you can _pipe_ the results of a **Get** cmdlet to another cmdlet of the same noun.</span></span>
<span data-ttu-id="f3084-132">たとえば、コマンドレットの出力をコマンドレット `Get-Service` またはコマンドレットにパイプすることができ `Start-Service` `Stop-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="f3084-132">For example, you can pipe the output of the `Get-Service` cmdlet to the `Start-Service` or `Stop-Service` cmdlets.</span></span>

<span data-ttu-id="f3084-133">このパイプライン例では、コンピューター上の WMI サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="f3084-133">This example pipeline starts the WMI service on the computer:</span></span>

```powershell
Get-Service wmi | Start-Service
```

<span data-ttu-id="f3084-134">別の例として、 `Get-Item` PowerShell レジストリプロバイダー内のまたはの出力をコマンドレットにパイプすることができ `Get-ChildItem` `New-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="f3084-134">For another example, you can pipe the output of `Get-Item` or `Get-ChildItem` within the PowerShell registry provider to the `New-ItemProperty` cmdlet.</span></span> <span data-ttu-id="f3084-135">この例では、値が **8124** の新しいレジストリエントリ **Noofemployees** を **MyCompany** レジストリキーに追加します。</span><span class="sxs-lookup"><span data-stu-id="f3084-135">This example adds a new registry entry, **NoOfEmployees** , with a value of **8124** , to the **MyCompany** registry key.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany |
  New-ItemProperty -Name NoOfEmployees -Value 8124
```

<span data-ttu-id="f3084-136">、、、、などの多くのユーティリティコマンドレット `Get-Member` は、ほとんどの場合、 `Where-Object` `Sort-Object` `Group-Object` `Measure-Object` パイプラインでのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3084-136">Many of the utility cmdlets, such as `Get-Member`, `Where-Object`, `Sort-Object`, `Group-Object`, and `Measure-Object` are used almost exclusively in pipelines.</span></span> <span data-ttu-id="f3084-137">パイプを使用して、任意のオブジェクト型をこれらのコマンドレットに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="f3084-137">You can pipe any object type to these cmdlets.</span></span> <span data-ttu-id="f3084-138">この例では、コンピューター上のすべてのプロセスを、プロセスごとに開いているハンドルの数で並べ替える方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f3084-138">This example shows how to sort all the processes on the computer by the number of open handles in each process.</span></span>

```powershell
Get-Process | Sort-Object -Property handles
```

<span data-ttu-id="f3084-139">パイプを使用して、オブジェクトを書式設定、エクスポート、および出力コマンドレット (、、、、など) に送ることができ `Format-List` `Format-Table` `Export-Clixml` `Export-CSV` `Out-File` ます。</span><span class="sxs-lookup"><span data-stu-id="f3084-139">You can pipe objects to the formatting, export, and output cmdlets, such as `Format-List`, `Format-Table`, `Export-Clixml`, `Export-CSV`, and `Out-File`.</span></span>

<span data-ttu-id="f3084-140">この例では、コマンドレットを使用して、 `Format-List` プロセスオブジェクトのプロパティの一覧を表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f3084-140">This example shows how to use the `Format-List` cmdlet to display a list of properties for a process object.</span></span>

```powershell
Get-Process winlogon | Format-List -Property *
```

<span data-ttu-id="f3084-141">単純なコマンドをパイプラインにまとめると、時間と入力が節約され、スクリプトの効率が向上することがわかります。</span><span class="sxs-lookup"><span data-stu-id="f3084-141">With a bit of practice, you'll find that combining simple commands into pipelines saves time and typing, and makes your scripting more efficient.</span></span>

## <a name="how-pipelines-work"></a><span data-ttu-id="f3084-142">パイプラインのしくみ</span><span class="sxs-lookup"><span data-stu-id="f3084-142">How pipelines work</span></span>

<span data-ttu-id="f3084-143">ここでは、入力オブジェクトをコマンドレットパラメーターにバインドし、パイプラインの実行中に処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3084-143">This section explains how input objects are bound to cmdlet parameters and processed during pipeline execution.</span></span>

### <a name="accepts-pipeline-input"></a><span data-ttu-id="f3084-144">パイプライン入力の受け入れ</span><span class="sxs-lookup"><span data-stu-id="f3084-144">Accepts pipeline input</span></span>

<span data-ttu-id="f3084-145">パイプライン処理をサポートするには、受信コマンドレットにパイプライン入力を受け入れるパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="f3084-145">To support pipelining, the receiving cmdlet must have a parameter that accepts pipeline input.</span></span> <span data-ttu-id="f3084-146">コマンドを `Get-Help` **Full** または **Parameter** オプションと共に使用して、パイプライン入力を受け入れるコマンドレットのパラメーターを決定します。</span><span class="sxs-lookup"><span data-stu-id="f3084-146">Use the `Get-Help` command with the **Full** or **Parameter** options to determine which parameters of a cmdlet accept pipeline input.</span></span>

<span data-ttu-id="f3084-147">たとえば、コマンドレットのどのパラメーターがパイプライン入力を受け入れるかを決定するには、次のように `Start-Service` 入力します。</span><span class="sxs-lookup"><span data-stu-id="f3084-147">For example, to determine which of the parameters of the `Start-Service` cmdlet accepts pipeline input, type:</span></span>

```powershell
Get-Help Start-Service -Full
```

<span data-ttu-id="f3084-148">or</span><span class="sxs-lookup"><span data-stu-id="f3084-148">or</span></span>

```powershell
Get-Help Start-Service -Parameter *
```

<span data-ttu-id="f3084-149">コマンドレットのヘルプでは、 `Start-Service` **InputObject** パラメーターと **Name** パラメーターのみがパイプライン入力を受け入れることが示されています。</span><span class="sxs-lookup"><span data-stu-id="f3084-149">The help for the `Start-Service` cmdlet shows that only the **InputObject** and **Name** parameters accept pipeline input.</span></span>

```Output
-InputObject <ServiceController[]>
Specifies ServiceController objects representing the services to be started.
Enter a variable that contains the objects, or type a command or expression
that gets the objects.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByValue)
Accept wildcard characters?  false

-Name <String[]>
Specifies the service names for the service to be started.

The parameter name is optional. You can use Name or its alias, ServiceName,
or you can omit the parameter name.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByPropertyName, ByValue)
Accept wildcard characters?  false
```

<span data-ttu-id="f3084-150">パイプラインを介してオブジェクトをに送信すると `Start-Service` 、PowerShell は、オブジェクトを **InputObject** パラメーターと **Name** パラメーターに関連付けようとします。</span><span class="sxs-lookup"><span data-stu-id="f3084-150">When you send objects through the pipeline to `Start-Service`, PowerShell attempts to associate the objects with the **InputObject** and **Name** parameters.</span></span>

### <a name="methods-of-accepting-pipeline-input"></a><span data-ttu-id="f3084-151">パイプライン入力を受け入れる方法</span><span class="sxs-lookup"><span data-stu-id="f3084-151">Methods of accepting pipeline input</span></span>

<span data-ttu-id="f3084-152">コマンドレットのパラメーターは、次の2つの方法のいずれかでパイプライン入力を受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="f3084-152">Cmdlets parameters can accept pipeline input in one of two different ways:</span></span>

- <span data-ttu-id="f3084-153">**Byvalue** : パラメーターは、予期された .net 型に一致する値、またはその型に変換できる値を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="f3084-153">**ByValue** : The parameter accepts values that match the expected .NET type or that can be converted to that type.</span></span>

  <span data-ttu-id="f3084-154">たとえば、の **Name** パラメーターは、 `Start-Service` 値によってパイプライン入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="f3084-154">For example, the **Name** parameter of `Start-Service` accepts pipeline input by value.</span></span> <span data-ttu-id="f3084-155">文字列に変換できる文字列オブジェクトまたはオブジェクトを受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="f3084-155">It can accept string objects or objects that can be converted to strings.</span></span>

- <span data-ttu-id="f3084-156">**Bypropertyname** : パラメーターは、入力オブジェクトにパラメーターと同じ名前のプロパティがある場合にのみ、入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="f3084-156">**ByPropertyName** : The parameter accepts input only when the input object has a property of the same name as the parameter.</span></span>

  <span data-ttu-id="f3084-157">たとえば、の Name パラメーターは、 `Start-Service` **name** プロパティを持つオブジェクトを受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="f3084-157">For example, the Name parameter of `Start-Service` can accept objects that have a **Name** property.</span></span> <span data-ttu-id="f3084-158">オブジェクトのプロパティを一覧表示するには、をにパイプし `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="f3084-158">To list the properties of an object, pipe it to `Get-Member`.</span></span>

<span data-ttu-id="f3084-159">パラメーターによっては、値またはプロパティ名の両方でオブジェクトを受け取ることができるため、パイプラインからの入力が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="f3084-159">Some parameters can accept objects by both value or property name, making it easier to take input from the pipeline.</span></span>

### <a name="parameter-binding"></a><span data-ttu-id="f3084-160">パラメーターのバインド</span><span class="sxs-lookup"><span data-stu-id="f3084-160">Parameter binding</span></span>

<span data-ttu-id="f3084-161">パイプを使用してオブジェクトを1つのコマンドから別のコマンドにパイプすると、PowerShell は、パイプされたオブジェクトを受信側のコマンドレットのパラメーターに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="f3084-161">When you pipe objects from one command to another command, PowerShell attempts to associate the piped objects with a parameter of the receiving cmdlet.</span></span>

<span data-ttu-id="f3084-162">PowerShell のパラメーターバインドコンポーネントは、次の条件に従って、入力オブジェクトをコマンドレットパラメーターに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="f3084-162">PowerShell's parameter binding component associates the input objects with cmdlet parameters according to the following criteria:</span></span>

- <span data-ttu-id="f3084-163">パラメーターは、パイプラインからの入力を受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3084-163">The parameter must accept input from a pipeline.</span></span>
- <span data-ttu-id="f3084-164">パラメーターは、送信されるオブジェクトの型または必要な型に変換できる型を受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3084-164">The parameter must accept the type of object being sent or a type that can be converted to the expected type.</span></span>
- <span data-ttu-id="f3084-165">パラメーターがコマンドで使用されませんでした。</span><span class="sxs-lookup"><span data-stu-id="f3084-165">The parameter wasn't used in the command.</span></span>

<span data-ttu-id="f3084-166">たとえば、 `Start-Service` コマンドレットには多くのパラメーターがありますが、その **Name** うちの **InputObject** 2 つだけがパイプライン入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="f3084-166">For example, the `Start-Service` cmdlet has many parameters, but only two of them, **Name** and **InputObject** accept pipeline input.</span></span> <span data-ttu-id="f3084-167">**Name** パラメーターは文字列を受け取り、 **InputObject** パラメーターはサービスオブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f3084-167">The **Name** parameter takes strings and the **InputObject** parameter takes service objects.</span></span> <span data-ttu-id="f3084-168">したがって、文字列、サービスオブジェクト、およびオブジェクトを、文字列またはサービスオブジェクトに変換できるプロパティと共にパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="f3084-168">Therefore, you can pipe strings, service objects, and objects with properties that can be converted to string or service objects.</span></span>

<span data-ttu-id="f3084-169">PowerShell は、可能な限り効率的にパラメーターバインディングを管理します。</span><span class="sxs-lookup"><span data-stu-id="f3084-169">PowerShell manages parameter binding as efficiently as possible.</span></span> <span data-ttu-id="f3084-170">特定のパラメーターにバインドする PowerShell を提案したり、強制したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f3084-170">You can't suggest or force the PowerShell to bind to a specific parameter.</span></span> <span data-ttu-id="f3084-171">PowerShell がパイプされたオブジェクトをバインドできない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f3084-171">The command fails if PowerShell can't bind the piped objects.</span></span>

<span data-ttu-id="f3084-172">バインディングエラーのトラブルシューティングの詳細については、この記事で後述する「 [パイプラインエラーの調査](#investigating-pipeline-errors) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3084-172">For more information about troubleshooting binding errors, see [Investigating Pipeline Errors](#investigating-pipeline-errors) later in this article.</span></span>

### <a name="one-at-a-time-processing"></a><span data-ttu-id="f3084-173">1回限りの処理</span><span class="sxs-lookup"><span data-stu-id="f3084-173">One-at-a-time processing</span></span>

<span data-ttu-id="f3084-174">オブジェクトをコマンドにパイプするのは、コマンドのパラメーターを使用してオブジェクトを送信するのとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="f3084-174">Piping objects to a command is much like using a parameter of the command to submit the objects.</span></span> <span data-ttu-id="f3084-175">パイプラインの例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="f3084-175">Let's look at a pipeline example.</span></span> <span data-ttu-id="f3084-176">この例では、パイプラインを使用して、サービスオブジェクトのテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="f3084-176">In this example, we use a pipeline to display a table of service objects.</span></span>

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

<span data-ttu-id="f3084-177">機能的には、これはの **InputObject** パラメーターを使用してオブジェクトコレクションを送信するのと似てい `Format-Table` ます。</span><span class="sxs-lookup"><span data-stu-id="f3084-177">Functionally, this is like using the **InputObject** parameter of `Format-Table` to submit the object collection.</span></span>

<span data-ttu-id="f3084-178">たとえば、 **InputObject** パラメーターを使用して渡された変数にサービスのコレクションを保存できます。</span><span class="sxs-lookup"><span data-stu-id="f3084-178">For example, we can save the collection of services to a variable that is passed using the **InputObject** parameter.</span></span>

```powershell
$services = Get-Service
Format-Table -InputObject $services -Property Name, DependentServices
```

<span data-ttu-id="f3084-179">または、 **InputObject** パラメーターにコマンドを埋め込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="f3084-179">Or we can embed the command in the **InputObject** parameter.</span></span>

```powershell
Format-Table -InputObject (Get-Service) -Property Name, DependentServices
```

<span data-ttu-id="f3084-180">ただし、重要な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="f3084-180">However, there's an important difference.</span></span> <span data-ttu-id="f3084-181">パイプを使用して複数のオブジェクトをコマンドに渡した場合、PowerShell は一度に1つずつコマンドにオブジェクトを送信します。</span><span class="sxs-lookup"><span data-stu-id="f3084-181">When you pipe multiple objects to a command, PowerShell sends the objects to the command one at a time.</span></span> <span data-ttu-id="f3084-182">コマンドパラメーターを使用すると、オブジェクトは1つの配列オブジェクトとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="f3084-182">When you use a command parameter, the objects are sent as a single array object.</span></span> <span data-ttu-id="f3084-183">この軽微な違いには大きな影響があります。</span><span class="sxs-lookup"><span data-stu-id="f3084-183">This minor difference has significant consequences.</span></span>

<span data-ttu-id="f3084-184">パイプラインを実行すると、PowerShell は、インターフェイスを実装する任意の型を自動的に列挙 `IEnumerable` し、パイプラインを介して一度に1つずつメンバーを送信します。</span><span class="sxs-lookup"><span data-stu-id="f3084-184">When executing a pipeline, PowerShell automatically enumerates any type that implements the `IEnumerable` interface and sends the members through the pipeline one at a time.</span></span> <span data-ttu-id="f3084-185">例外は `[hashtable]` で、メソッドを呼び出す必要があり `GetEnumerator()` ます。</span><span class="sxs-lookup"><span data-stu-id="f3084-185">The exception is `[hashtable]`, which requires a call to the `GetEnumerator()` method.</span></span>

<span data-ttu-id="f3084-186">次の例では、配列とハッシュテーブルをコマンドレットにパイプして、 `Measure-Object` パイプラインから受信したオブジェクトの数をカウントしています。</span><span class="sxs-lookup"><span data-stu-id="f3084-186">In the following examples, an array and a hashtable are piped to the `Measure-Object` cmdlet to count the number of objects received from the pipeline.</span></span> <span data-ttu-id="f3084-187">配列に複数のメンバーがあり、ハッシュテーブルに複数のキーと値のペアが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f3084-187">The array has multiple members, and the hashtable has multiple key-value pairs.</span></span> <span data-ttu-id="f3084-188">配列は、一度に1つずつ列挙されます。</span><span class="sxs-lookup"><span data-stu-id="f3084-188">Only the array is enumerated one at a time.</span></span>

```powershell
@(1,2,3) | Measure-Object
```

```Output
Count    : 3
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

```powershell
@{"One"=1;"Two"=2} | Measure-Object
```

```Output
Count    : 1
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

<span data-ttu-id="f3084-189">同様に、コマンドレットからコマンドレットに複数のプロセスオブジェクトをパイプすると、 `Get-Process` `Get-Member` PowerShell は各プロセスオブジェクトを一度に1つずつに送信 `Get-Member` します。</span><span class="sxs-lookup"><span data-stu-id="f3084-189">Similarly, if you pipe multiple process objects from the `Get-Process` cmdlet to the `Get-Member` cmdlet, PowerShell sends each process object, one at a time, to `Get-Member`.</span></span> <span data-ttu-id="f3084-190">`Get-Member` プロセスオブジェクトの .NET クラス (型)、およびそのプロパティとメソッドを表示します。</span><span class="sxs-lookup"><span data-stu-id="f3084-190">`Get-Member` displays the .NET class (type) of the process objects, and their properties and methods.</span></span>

```powershell
Get-Process | Get-Member
```

```Output
TypeName: System.Diagnostics.Process

Name      MemberType     Definition
----      ----------     ----------
Handles   AliasProperty  Handles = Handlecount
Name      AliasProperty  Name = ProcessName
NPM       AliasProperty  NPM = NonpagedSystemMemorySize
...
```

> [!NOTE]
> <span data-ttu-id="f3084-191">`Get-Member` 重複を排除します。したがって、オブジェクトの種類がすべて同じである場合は、オブジェクトの種類が1つだけ表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3084-191">`Get-Member` eliminates duplicates, so if the objects are all of the same type, it only displays one object type.</span></span>

<span data-ttu-id="f3084-192">ただし、の **InputObject** パラメーターを使用すると、は `Get-Member` `Get-Member` 1 つの単位 **System.Diagnostics.Process** として system.string オブジェクトの配列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f3084-192">However, if you use the **InputObject** parameter of `Get-Member`, then `Get-Member` receives an array of **System.Diagnostics.Process** objects as a single unit.</span></span> <span data-ttu-id="f3084-193">オブジェクトの配列のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="f3084-193">It displays the properties of an array of objects.</span></span> <span data-ttu-id="f3084-194">( `[]` **System.object** 型名の後にある配列シンボル () に注意してください)。</span><span class="sxs-lookup"><span data-stu-id="f3084-194">(Note the array symbol (`[]`) after the **System.Object** type name.)</span></span>

<span data-ttu-id="f3084-195">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3084-195">For example,</span></span>

```powershell
Get-Member -InputObject (Get-Process)
```

```Output
TypeName: System.Object[]

Name               MemberType    Definition
----               ----------    ----------
Count              AliasProperty Count = Length
Address            Method        System.Object& Address(Int32 )
Clone              Method        System.Object Clone()
...
```

<span data-ttu-id="f3084-196">この結果は意図したものではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f3084-196">This result might not be what you intended.</span></span> <span data-ttu-id="f3084-197">しかし、理解したら、それを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f3084-197">But after you understand it, you can use it.</span></span> <span data-ttu-id="f3084-198">たとえば、すべての配列オブジェクトには **Count** プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="f3084-198">For example, all array objects have a **Count** property.</span></span> <span data-ttu-id="f3084-199">これを使用すると、コンピューター上で実行されているプロセスの数をカウントできます。</span><span class="sxs-lookup"><span data-stu-id="f3084-199">You can use that to count the number of processes running on the computer.</span></span>

<span data-ttu-id="f3084-200">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3084-200">For example,</span></span>

```powershell
(Get-Process).count
```

<span data-ttu-id="f3084-201">パイプラインを介して送信されたオブジェクトは一度に1つずつ配信されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f3084-201">It's important to remember that objects sent down the pipeline are delivered one at a time.</span></span>

## <a name="investigating-pipeline-errors"></a><span data-ttu-id="f3084-202">パイプラインエラーの調査</span><span class="sxs-lookup"><span data-stu-id="f3084-202">Investigating pipeline errors</span></span>

<span data-ttu-id="f3084-203">PowerShell がパイプ処理されたオブジェクトを受信側のコマンドレットのパラメーターに関連付けられない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f3084-203">When PowerShell can't associate the piped objects with a parameter of the receiving cmdlet, the command fails.</span></span>

<span data-ttu-id="f3084-204">次の例では、レジストリエントリをあるレジストリキーから別のレジストリキーに移動しようとしています。</span><span class="sxs-lookup"><span data-stu-id="f3084-204">In the following example, we try to move a registry entry from one registry key to another.</span></span> <span data-ttu-id="f3084-205">`Get-Item`コマンドレットは、ターゲットパスを取得します。これは、コマンドレットにパイプされ `Move-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="f3084-205">The `Get-Item` cmdlet gets the destination path, which is then piped to the `Move-ItemProperty` cmdlet.</span></span> <span data-ttu-id="f3084-206">この `Move-ItemProperty` コマンドは、移動するレジストリエントリの現在のパスと名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3084-206">The `Move-ItemProperty` command specifies the current path and name of the registry entry to be moved.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales |
Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
```

<span data-ttu-id="f3084-207">コマンドが失敗し、PowerShell によって次のエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3084-207">The command fails and PowerShell displays the following error message:</span></span>

```Output
Move-ItemProperty : The input object can't be bound to any parameters for
the command either because the command doesn't take pipeline input or the
input and its properties do not match any of the parameters that take
pipeline input.
At line:1 char:23
+ $a | Move-ItemProperty <<<<  -Path HKLM:\Software\MyCompany\design -Name p
```

<span data-ttu-id="f3084-208">調査するには、コマンドレットを使用して、 `Trace-Command` PowerShell のパラメーターバインドコンポーネントをトレースします。</span><span class="sxs-lookup"><span data-stu-id="f3084-208">To investigate, use the `Trace-Command` cmdlet to trace the parameter binding component of PowerShell.</span></span> <span data-ttu-id="f3084-209">次の例では、パイプラインの実行中にパラメーターバインドをトレースします。</span><span class="sxs-lookup"><span data-stu-id="f3084-209">The following example traces parameter binding while the pipeline is executing.</span></span> <span data-ttu-id="f3084-210">**PSHost** パラメーターは、コンソールにトレース結果を表示し、 **FilePath** パラメーターは、 `debug.txt` 後で参照するためにトレース結果をファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="f3084-210">The **PSHost** parameter displays the trace results in the console and the **FilePath** parameter send the trace results to the `debug.txt` file for later reference.</span></span>

```powershell
Trace-Command -Name ParameterBinding -PSHost -FilePath debug.txt -Expression {
  Get-Item -Path HKLM:\Software\MyCompany\sales |
    Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
}
```

<span data-ttu-id="f3084-211">トレースの結果は時間がかかりますが、コマンドレットにバインドされている値 `Get-Item` と、コマンドレットにバインドされている名前付きの値を示してい `Move-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="f3084-211">The results of the trace are lengthy, but they show the values being bound to the `Get-Item` cmdlet and then the named values being bound to the `Move-ItemProperty` cmdlet.</span></span>

```Output
...
BIND NAMED cmd line args [`Move-ItemProperty`]
BIND arg [HKLM:\Software\MyCompany\design] to parameter [Path]
...
BIND arg [product] to parameter [Name]
...
BIND POSITIONAL cmd line args [`Move-ItemProperty`]
...
```

<span data-ttu-id="f3084-212">最後に、パスを **Destination** パラメーターにバインドしようとして失敗したことを示して `Move-ItemProperty` います。</span><span class="sxs-lookup"><span data-stu-id="f3084-212">Finally, it shows that the attempt to bind the path to the **Destination** parameter of `Move-ItemProperty` failed.</span></span>

```Output
...
BIND PIPELINE object to parameters: [`Move-ItemProperty`]
PIPELINE object TYPE = [Microsoft.Win32.RegistryKey]
RESTORING pipeline parameter's original values
Parameter [Destination] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
Parameter [Credential] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
...
```

<span data-ttu-id="f3084-213">コマンドレットを使用して、 `Get-Help` **Destination** パラメーターの属性を表示します。</span><span class="sxs-lookup"><span data-stu-id="f3084-213">Use the `Get-Help` cmdlet to view the attributes of the **Destination** parameter.</span></span>

```Output
Get-Help Move-ItemProperty -Parameter Destination

-Destination <String>
    Specifies the path to the destination location.

    Required?                    true
    Position?                    1
    Default value                None
    Accept pipeline input?       True (ByPropertyName)
    Accept wildcard characters?  false
```

<span data-ttu-id="f3084-214">結果には、 **変換先** がプロパティ名によってのみパイプライン入力を受け取ることが示されています。</span><span class="sxs-lookup"><span data-stu-id="f3084-214">The results show that **Destination** takes pipeline input only "by property name".</span></span> <span data-ttu-id="f3084-215">したがって、パイプされたオブジェクトには **Destination** という名前のプロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="f3084-215">Therefore, the piped object must have a property named **Destination**.</span></span>

<span data-ttu-id="f3084-216">`Get-Member`から取得するオブジェクトのプロパティを表示するには、を使用し `Get-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="f3084-216">Use `Get-Member` to see the properties of the object coming from `Get-Item`.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales | Get-Member
```

<span data-ttu-id="f3084-217">出力には、項目が、 **変換先** のプロパティを持たない、 **Microsoft の Win32 の RegistryKey** オブジェクトであることが示されています。</span><span class="sxs-lookup"><span data-stu-id="f3084-217">The output shows that the item is a **Microsoft.Win32.RegistryKey** object that doesn't have a **Destination** property.</span></span> <span data-ttu-id="f3084-218">コマンドが失敗した理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3084-218">That explains why the command failed.</span></span>

<span data-ttu-id="f3084-219">**Path** パラメーターは、名前または値によってパイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="f3084-219">The **Path** parameter accepts pipeline input by name or by value.</span></span>

```Output
Get-Help Move-ItemProperty -Parameter Path

-Path <String[]>
    Specifies the path to the current location of the property. Wildcard
    characters are permitted.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName, ByValue)
    Accept wildcard characters?  true
```

<span data-ttu-id="f3084-220">コマンドを修正するには、コマンドレットで出力先を指定し、を使用して `Move-ItemProperty` `Get-Item` 移動する項目の **パス** を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3084-220">To fix the command, we must specify the destination in the `Move-ItemProperty` cmdlet and use `Get-Item` to get the **Path** of the item we want to move.</span></span>

<span data-ttu-id="f3084-221">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3084-221">For example,</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\design |
Move-ItemProperty -Destination HKLM:\Software\MyCompany\sales -Name product
```

## <a name="intrinsic-line-continuation"></a><span data-ttu-id="f3084-222">組み込みの行連結</span><span class="sxs-lookup"><span data-stu-id="f3084-222">Intrinsic line continuation</span></span>

<span data-ttu-id="f3084-223">既に説明したように、パイプラインはパイプライン演算子 () によって接続された一連のコマンドであり `|` 、通常は単一行に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="f3084-223">As already discussed, a pipeline is a series of commands connected by pipeline operators (`|`), usually written on a single line.</span></span> <span data-ttu-id="f3084-224">ただし、読みやすくするために、PowerShell ではパイプラインを複数の行に分割することができます。</span><span class="sxs-lookup"><span data-stu-id="f3084-224">However, for readability, PowerShell allows you to split the pipeline across multiple lines.</span></span>
<span data-ttu-id="f3084-225">パイプ演算子が行の最後のトークンである場合、PowerShell パーサーは次の行を現在のコマンドに結合して、パイプラインの構築を続行します。</span><span class="sxs-lookup"><span data-stu-id="f3084-225">When a pipe operator is the last token on the line, the PowerShell parser joins the next line to current command to continue the construction of the pipeline.</span></span>

<span data-ttu-id="f3084-226">たとえば、次の単一行パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="f3084-226">For example, the following single-line pipeline:</span></span>

```powershell
Command-1 | Command-2 | Command-3
```

<span data-ttu-id="f3084-227">次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="f3084-227">can be written as:</span></span>

```powershell
Command-1 |
  Command-2 |
    Command-3
```

<span data-ttu-id="f3084-228">後続の行の先頭のスペースは重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="f3084-228">The leading spaces on the subsequent lines are not significant.</span></span> <span data-ttu-id="f3084-229">インデントは読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="f3084-229">The indentation enhances readability.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3084-230">参照</span><span class="sxs-lookup"><span data-stu-id="f3084-230">See Also</span></span>

[<span data-ttu-id="f3084-231">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="f3084-231">about_PSReadLine</span></span>](../../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="f3084-232">about_Objects</span><span class="sxs-lookup"><span data-stu-id="f3084-232">about_Objects</span></span>](about_objects.md)

[<span data-ttu-id="f3084-233">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="f3084-233">about_Parameters</span></span>](about_parameters.md)

[<span data-ttu-id="f3084-234">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="f3084-234">about_Command_Syntax</span></span>](about_command_syntax.md)

[<span data-ttu-id="f3084-235">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="f3084-235">about_ForEach</span></span>](about_foreach.md)
