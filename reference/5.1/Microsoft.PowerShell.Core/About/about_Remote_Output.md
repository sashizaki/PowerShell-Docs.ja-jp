---
description: リモートコマンドの出力を解釈および書式設定する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_output?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Output
ms.openlocfilehash: c5636a301017111adf97b6332237e737b4bf0716
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223275"
---
# <a name="about-remote-output"></a><span data-ttu-id="7b891-104">リモート出力について</span><span class="sxs-lookup"><span data-stu-id="7b891-104">About Remote Output</span></span>

## <a name="short-description"></a><span data-ttu-id="7b891-105">概要</span><span class="sxs-lookup"><span data-stu-id="7b891-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="7b891-106">リモートコマンドの出力を解釈および書式設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b891-106">Describes how to interpret and format the output of remote commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="7b891-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="7b891-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="7b891-108">リモートコンピューター上で実行されたコマンドの出力は、ローカルコンピューターで同じコマンドを実行した場合と同じように見えますが、大きな違いがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="7b891-108">The output of a command that was run on a remote computer might look like output of the same command run on a local computer, but there are some significant differences.</span></span>

<span data-ttu-id="7b891-109">このトピックでは、リモートコンピューターで実行されるコマンドの出力を解釈、書式設定、および表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b891-109">This topic explains how to interpret, format, and display the output of commands that are run on remote computers.</span></span>

## <a name="displaying-the-computer-name"></a><span data-ttu-id="7b891-110">コンピューター名を表示しています</span><span class="sxs-lookup"><span data-stu-id="7b891-110">DISPLAYING THE COMPUTER NAME</span></span>

<span data-ttu-id="7b891-111">Invoke-Command コマンドレットを使用してリモートコンピューターでコマンドを実行すると、そのデータを生成したコンピューターの名前を含むオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="7b891-111">When you use the Invoke-Command cmdlet to run a command on a remote computer, the command returns an object that includes the name of the computer that generated the data.</span></span> <span data-ttu-id="7b891-112">リモートコンピューター名は、PSComputerName プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="7b891-112">The remote computer name is stored in the PSComputerName property.</span></span>

<span data-ttu-id="7b891-113">多くのコマンドでは、PSComputerName が既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b891-113">For many commands, the PSComputerName is displayed by default.</span></span> <span data-ttu-id="7b891-114">たとえば、次のコマンドは、Server01 と Server02 の2台のリモートコンピューターで Get-Culture コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7b891-114">For example, the following command runs a Get-Culture command on two remote computers, Server01 and Server02.</span></span> <span data-ttu-id="7b891-115">下に表示される出力には、コマンドを実行したリモートコンピューターの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b891-115">The output, which appears below, includes the names of the remote computers on which the command ran.</span></span>

```powershell
C:\PS> invoke-command -script {get-culture} -comp Server01, Server02

LCID  Name    DisplayName                PSComputerName
----  ----    -----------                --------------
1033  en-US   English (United States)    Server01
1033  es-AR   Spanish (Argentina)        Server02
```

<span data-ttu-id="7b891-116">Invoke-Command の HideComputerName パラメーターを使用して、PSComputerName プロパティを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7b891-116">You can use the HideComputerName parameter of Invoke-Command to hide the PSComputerName property.</span></span> <span data-ttu-id="7b891-117">このパラメーターは、1台のリモートコンピューターからのみデータを収集するコマンド用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="7b891-117">This parameter is designed for commands that collect data from only one remote computer.</span></span>

<span data-ttu-id="7b891-118">次のコマンドは、Server01 リモートコンピューターで Get-Culture コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7b891-118">The following command runs a Get-Culture command on the Server01 remote computer.</span></span> <span data-ttu-id="7b891-119">HideComputerName パラメーターを使用して、PSComputerName プロパティと関連するプロパティを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="7b891-119">It uses the HideComputerName parameter to hide the PSComputerName property and related properties.</span></span>

```powershell
C:\PS> invoke-command -scr {get-culture} -comp Server01 -HideComputerName

LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

<span data-ttu-id="7b891-120">PSComputerName プロパティが既定で表示されない場合は、表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="7b891-120">You can also display the PSComputerName property if it is not displayed by default.</span></span>

<span data-ttu-id="7b891-121">たとえば、次のコマンドでは、Format-Table コマンドレットを使用して、リモート Get-Date コマンドの出力に PSComputerName プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="7b891-121">For example, the following commands use the Format-Table cmdlet to add the PSComputerName property to the output of a remote Get-Date command.</span></span>

```powershell
$dates = invoke-command -script {get-date} -computername Server01, Server02
$dates | format-table DateTime, PSComputerName -auto

DateTime                            PSComputerName
--------                            --------------
Monday, July 21, 2008 7:16:58 PM    Server01
Monday, July 21, 2008 7:16:58 PM    Server02
```

## <a name="displaying-the-machinename-property"></a><span data-ttu-id="7b891-122">MACHINENAME プロパティを表示しています</span><span class="sxs-lookup"><span data-stu-id="7b891-122">DISPLAYING THE MACHINENAME PROPERTY</span></span>

<span data-ttu-id="7b891-123">Get Process、Get Service、および EventLog など、いくつかのコマンドレットには、リモートコンピューター上のオブジェクトを取得する ComputerName パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="7b891-123">Several cmdlets, including Get-Process, Get-Service, and Get-EventLog, have a ComputerName parameter that gets the objects on a remote computer.</span></span>
<span data-ttu-id="7b891-124">これらのコマンドレットは、Windows powershell リモート処理を使用しないため、Windows PowerShell のリモート処理用に構成されていないコンピューターでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b891-124">These cmdlets do not use Windows PowerShell remoting, so you can use them even on computers that are not configured for remoting in Windows PowerShell.</span></span>

<span data-ttu-id="7b891-125">これらのコマンドレットが返すオブジェクトは、MachineName プロパティにリモートコンピューターの名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="7b891-125">The objects that these cmdlets return store the name of the remote computer in the MachineName property.</span></span> <span data-ttu-id="7b891-126">(これらのオブジェクトには、PSComputerName プロパティがありません)。</span><span class="sxs-lookup"><span data-stu-id="7b891-126">(These objects do not have a PSComputerName property.)</span></span>

<span data-ttu-id="7b891-127">たとえば、次のコマンドは、Server01 および Server02 リモートコンピューター上の PowerShell プロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b891-127">For example, this command gets the PowerShell process on the Server01 and Server02 remote computers.</span></span> <span data-ttu-id="7b891-128">既定の表示には、MachineName プロパティは含まれません。</span><span class="sxs-lookup"><span data-stu-id="7b891-128">The default display does not include the MachineName property.</span></span>

```powershell
C:\PS> get-process PowerShell -computername server01, server02

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
920      38    97524     114504   575     9.66   2648 PowerShell
194       6    24256      32384   142            3020 PowerShell
352      27    63472      63520   577     3.84   4796 PowerShell
```

<span data-ttu-id="7b891-129">Format-Table コマンドレットを使用して、プロセスオブジェクトの MachineName プロパティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="7b891-129">You can use the Format-Table cmdlet to display the MachineName property of the process objects.</span></span>

<span data-ttu-id="7b891-130">たとえば、次のコマンドは、$p 変数にプロセスを保存し、パイプライン演算子 (|) を使用して $p 内のプロセスを Format-Table コマンドに送信します。</span><span class="sxs-lookup"><span data-stu-id="7b891-130">For example, the following command saves the processes in the $p variable and then uses a pipeline operator (|) to send the processes in $p to the Format-Table command.</span></span> <span data-ttu-id="7b891-131">このコマンドは、Format-Table の Property パラメーターを使用して、MachineName プロパティをディスプレイに含めます。</span><span class="sxs-lookup"><span data-stu-id="7b891-131">The command uses the Property parameter of Format-Table to include the MachineName property in the display.</span></span>

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02
C:\PS> $P | format-table -property ID, ProcessName, MachineName -auto

Id ProcessName MachineName
-- ----------- -----------
2648 PowerShell  Server02
3020 PowerShell  Server01
4796 PowerShell  Server02
```

<span data-ttu-id="7b891-132">次のより複雑なコマンドは、MachineName プロパティを既定のプロセスの表示に追加します。</span><span class="sxs-lookup"><span data-stu-id="7b891-132">The following more complex command adds the MachineName property to the default process display.</span></span> <span data-ttu-id="7b891-133">ハッシュテーブルを使用して、計算されるプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b891-133">It uses hash tables to specify calculated properties.</span></span> <span data-ttu-id="7b891-134">幸い、それを使用するために理解する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7b891-134">Fortunately, you do not have to understand it to use it.</span></span>

<span data-ttu-id="7b891-135">(バックティック ['] が継続文字であることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="7b891-135">(Note that the backtick [\`] is the continuation character.)</span></span>

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02

C:\PS> $p | format-table -property Handles, `
@{Label="NPM(K)";Expression={int}}, `
@{Label="PM(K)";Expression={int}}, `
@{Label="WS(K)";Expression={int}}, `
@{Label="VM(M)";Expression={int}}, `
@{Label="CPU(s)";Expression={if ($.CPU -ne $()){ $.CPU.ToString("N")}}}, `
Id, ProcessName, MachineName -auto

Handles NPM(K) PM(K)  WS(K) VM(M) CPU(s)   Id ProcessName MachineName
------- ------ -----  ----- ----- ------   -- ----------- -----------
920     38 97560 114532   576        2648 PowerShell  Server02
192      6 24132  32028   140        3020 PowerShell  Server01
438     26 48436  59132   565        4796 PowerShell  Server02

```

## <a name="deserialized-objects"></a><span data-ttu-id="7b891-136">逆シリアル化されたオブジェクト</span><span class="sxs-lookup"><span data-stu-id="7b891-136">DESERIALIZED OBJECTS</span></span>

<span data-ttu-id="7b891-137">出力を生成するリモートコマンドを実行すると、コマンドの出力がネットワーク経由でローカルコンピューターに転送されます。</span><span class="sxs-lookup"><span data-stu-id="7b891-137">When you run remote commands that generate output, the command output is transmitted across the network back to the local computer.</span></span>

<span data-ttu-id="7b891-138">ほとんどのライブ Microsoft .NET フレームワークオブジェクト (Windows PowerShell コマンドレットが返すオブジェクトなど) はネットワーク経由で転送できないため、ライブオブジェクトは "シリアル化" されます。</span><span class="sxs-lookup"><span data-stu-id="7b891-138">Because most live Microsoft .NET Framework objects (such as the objects that Windows PowerShell cmdlets return) cannot be transmitted over the network, the live objects are "serialized".</span></span> <span data-ttu-id="7b891-139">つまり、ライブオブジェクトは、オブジェクトとそのプロパティの XML 表現に変換されます。</span><span class="sxs-lookup"><span data-stu-id="7b891-139">In other words, the live objects are converted into XML representations of the object and its properties.</span></span> <span data-ttu-id="7b891-140">次に、XML ベースのシリアル化されたオブジェクトがネットワーク経由で転送されます。</span><span class="sxs-lookup"><span data-stu-id="7b891-140">Then, the XML-based serialized object is transmitted across the network.</span></span>

<span data-ttu-id="7b891-141">ローカルコンピューターでは、Windows PowerShell は xml ベースのシリアル化されたオブジェクトを受け取り、XML ベースのオブジェクトを標準の .NET Framework オブジェクトに変換することによって "逆シリアル化" します。</span><span class="sxs-lookup"><span data-stu-id="7b891-141">On the local computer, Windows PowerShell receives the XML-based serialized object and "deserializes" it by converting the XML-based object into a standard .NET Framework object.</span></span>

<span data-ttu-id="7b891-142">ただし、逆シリアル化されたオブジェクトはライブオブジェクトではありません。</span><span class="sxs-lookup"><span data-stu-id="7b891-142">However, the deserialized object is not a live object.</span></span> <span data-ttu-id="7b891-143">これは、シリアル化された時点のオブジェクトのスナップショットであり、プロパティは含まれていますが、メソッドは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="7b891-143">It is a snapshot of the object at the time that it was serialized, and it includes properties but no methods.</span></span> <span data-ttu-id="7b891-144">これらのオブジェクトは、Windows PowerShell で使用および管理できます。これには、パイプラインへの引き渡し、選択したプロパティの表示、書式設定などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7b891-144">You can use and manage these objects in Windows PowerShell, including passing them in pipelines, displaying selected properties, and formatting them.</span></span>

<span data-ttu-id="7b891-145">逆シリアル化されたオブジェクトのほとんどは、Types.ps1xml ファイルまたは Format.ps1xml ファイル内のエントリによって表示されるように自動的に書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="7b891-145">Most deserialized objects are automatically formatted for display by entries in the Types.ps1xml or Format.ps1xml files.</span></span> <span data-ttu-id="7b891-146">ただし、リモートコンピューター上で生成されたすべての逆シリアル化されたオブジェクトのフォーマットファイルがローカルコンピューターにない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7b891-146">However, the local computer might not have formatting files for all of the deserialized objects that were generated on a remote computer.</span></span> <span data-ttu-id="7b891-147">オブジェクトが書式設定されていない場合、各オブジェクトのプロパティはすべて、ストリーミングリストのコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b891-147">When objects are not formatted, all of the properties of each object appear in the console in a streaming list.</span></span>

<span data-ttu-id="7b891-148">オブジェクトが自動的に書式設定されない場合は、Format-Table や形式一覧などの書式設定コマンドレットを使用して、選択したプロパティを書式設定して表示できます。</span><span class="sxs-lookup"><span data-stu-id="7b891-148">When objects are not formatted automatically, you can use the formatting cmdlets, such as Format-Table or Format-List, to format and display selected properties.</span></span> <span data-ttu-id="7b891-149">または、Out-GridView コマンドレットを使用して、テーブル内のオブジェクトを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="7b891-149">Or, you can use the Out-GridView cmdlet to display the objects in a table.</span></span>

<span data-ttu-id="7b891-150">また、ローカルコンピューター上に存在しないコマンドレットを使用しているリモートコンピューターでコマンドを実行した場合、そのコマンドが返すオブジェクトは、コンピューター上のオブジェクトの書式設定ファイルを持っていないため、正しくフォーマットされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7b891-150">Also, if you run a command on a remote computer that uses cmdlets that you do not have on your local computer, the objects that the command returns might not be formatted properly because you do not have the formatting files for those objects on your computer.</span></span> <span data-ttu-id="7b891-151">別のコンピューターから書式設定データを取得するには、Get-FormatData と Export-FormatData のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7b891-151">To get formatting data from another computer, use the Get-FormatData and Export-FormatData cmdlets.</span></span>

<span data-ttu-id="7b891-152">DirectoryInfo オブジェクトや Guid など、オブジェクトの種類によっては、受信時にライブオブジェクトに変換されます。</span><span class="sxs-lookup"><span data-stu-id="7b891-152">Some object types, such as DirectoryInfo objects and GUIDs, are converted back into live objects when they are received.</span></span> <span data-ttu-id="7b891-153">これらのオブジェクトは、特別な処理や書式設定を必要としません。</span><span class="sxs-lookup"><span data-stu-id="7b891-153">These objects do not need any special handling or formatting.</span></span>

## <a name="ordering-the-results"></a><span data-ttu-id="7b891-154">結果の順序付け</span><span class="sxs-lookup"><span data-stu-id="7b891-154">ORDERING THE RESULTS</span></span>

<span data-ttu-id="7b891-155">コマンドレットの ComputerName パラメーターに指定されたコンピューター名の順序によって、Windows PowerShell がリモートコンピューターに接続する順序が決まります。</span><span class="sxs-lookup"><span data-stu-id="7b891-155">The order of the computer names in the ComputerName parameter of cmdlets determines the order in which Windows PowerShell connects to the remote computers.</span></span> <span data-ttu-id="7b891-156">ただし、結果は、ローカルコンピューターが受信した順序で表示されます。順序は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7b891-156">However, the results appear in the order in which the local computer receives them, which might be a different order.</span></span>

<span data-ttu-id="7b891-157">結果の順序を変更するには、Sort-Object コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7b891-157">To change the order of the results, use the Sort-Object cmdlet.</span></span> <span data-ttu-id="7b891-158">PSComputerName または MachineName プロパティで並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="7b891-158">You can sort on the PSComputerName or MachineName property.</span></span> <span data-ttu-id="7b891-159">また、別のコンピューターの結果が散在するように、オブジェクトの別のプロパティを並べ替えることもできます。</span><span class="sxs-lookup"><span data-stu-id="7b891-159">You can also sort on another property of the object so that the results from different computers are interspersed.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b891-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b891-160">SEE ALSO</span></span>

[<span data-ttu-id="7b891-161">about_Remote</span><span class="sxs-lookup"><span data-stu-id="7b891-161">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="7b891-162">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="7b891-162">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="7b891-163">Format-Table</span><span class="sxs-lookup"><span data-stu-id="7b891-163">Format-Table</span></span>](xref:Microsoft.PowerShell.Utility.Format-Table)

[<span data-ttu-id="7b891-164">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="7b891-164">Get-EventLog</span></span>](xref:Microsoft.PowerShell.Management.Get-EventLog)

[<span data-ttu-id="7b891-165">Get-Process</span><span class="sxs-lookup"><span data-stu-id="7b891-165">Get-Process</span></span>](xref:Microsoft.PowerShell.Management.Get-Process)

[<span data-ttu-id="7b891-166">Get-Service</span><span class="sxs-lookup"><span data-stu-id="7b891-166">Get-Service</span></span>](xref:Microsoft.PowerShell.Management.Get-Service)

[<span data-ttu-id="7b891-167">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="7b891-167">Get-WmiObject</span></span>](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[<span data-ttu-id="7b891-168">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="7b891-168">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="7b891-169">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="7b891-169">Out-GridView</span></span>](xref:Microsoft.PowerShell.Utility.Out-GridView)

[<span data-ttu-id="7b891-170">Select-Object</span><span class="sxs-lookup"><span data-stu-id="7b891-170">Select-Object</span></span>](xref:Microsoft.PowerShell.Utility.Select-Object)
