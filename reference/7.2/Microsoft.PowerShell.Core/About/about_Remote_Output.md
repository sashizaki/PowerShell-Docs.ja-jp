---
description: リモートコマンドの出力を解釈および書式設定する方法について説明します。
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_output?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Output
ms.openlocfilehash: 476afc62089795d22002ece05c7ce2bf53994237
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601389"
---
# <a name="about-remote-output"></a><span data-ttu-id="2ab7c-103">リモート出力について</span><span class="sxs-lookup"><span data-stu-id="2ab7c-103">About Remote Output</span></span>

## <a name="short-description"></a><span data-ttu-id="2ab7c-104">概要</span><span class="sxs-lookup"><span data-stu-id="2ab7c-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="2ab7c-105">リモートコマンドの出力を解釈および書式設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-105">Describes how to interpret and format the output of remote commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="2ab7c-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="2ab7c-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="2ab7c-107">リモートコンピューター上で実行されたコマンドの出力は、ローカルコンピューターで同じコマンドを実行した場合と同じように見えますが、大きな違いがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-107">The output of a command that was run on a remote computer might look like output of the same command run on a local computer, but there are some significant differences.</span></span>

<span data-ttu-id="2ab7c-108">このトピックでは、リモートコンピューターで実行されるコマンドの出力を解釈、書式設定、および表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-108">This topic explains how to interpret, format, and display the output of commands that are run on remote computers.</span></span>

## <a name="displaying-the-computer-name"></a><span data-ttu-id="2ab7c-109">コンピューター名を表示しています</span><span class="sxs-lookup"><span data-stu-id="2ab7c-109">DISPLAYING THE COMPUTER NAME</span></span>

<span data-ttu-id="2ab7c-110">Invoke-Command コマンドレットを使用してリモートコンピューターでコマンドを実行すると、そのデータを生成したコンピューターの名前を含むオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-110">When you use the Invoke-Command cmdlet to run a command on a remote computer, the command returns an object that includes the name of the computer that generated the data.</span></span> <span data-ttu-id="2ab7c-111">リモートコンピューター名は、PSComputerName プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-111">The remote computer name is stored in the PSComputerName property.</span></span>

<span data-ttu-id="2ab7c-112">多くのコマンドでは、PSComputerName が既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-112">For many commands, the PSComputerName is displayed by default.</span></span> <span data-ttu-id="2ab7c-113">たとえば、次のコマンドは、Server01 と Server02 の2台のリモートコンピューターで Get-Culture コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-113">For example, the following command runs a Get-Culture command on two remote computers, Server01 and Server02.</span></span> <span data-ttu-id="2ab7c-114">下に表示される出力には、コマンドを実行したリモートコンピューターの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-114">The output, which appears below, includes the names of the remote computers on which the command ran.</span></span>

```powershell
C:\PS> invoke-command -script {get-culture} -comp Server01, Server02

LCID  Name    DisplayName                PSComputerName
----  ----    -----------                --------------
1033  en-US   English (United States)    Server01
1033  es-AR   Spanish (Argentina)        Server02
```

<span data-ttu-id="2ab7c-115">Invoke-Command の HideComputerName パラメーターを使用して、PSComputerName プロパティを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-115">You can use the HideComputerName parameter of Invoke-Command to hide the PSComputerName property.</span></span> <span data-ttu-id="2ab7c-116">このパラメーターは、1台のリモートコンピューターからのみデータを収集するコマンド用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-116">This parameter is designed for commands that collect data from only one remote computer.</span></span>

<span data-ttu-id="2ab7c-117">次のコマンドは、Server01 リモートコンピューターで Get-Culture コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-117">The following command runs a Get-Culture command on the Server01 remote computer.</span></span> <span data-ttu-id="2ab7c-118">HideComputerName パラメーターを使用して、PSComputerName プロパティと関連するプロパティを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-118">It uses the HideComputerName parameter to hide the PSComputerName property and related properties.</span></span>

```powershell
C:\PS> invoke-command -scr {get-culture} -comp Server01 -HideComputerName

LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

<span data-ttu-id="2ab7c-119">PSComputerName プロパティが既定で表示されない場合は、表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-119">You can also display the PSComputerName property if it is not displayed by default.</span></span>

<span data-ttu-id="2ab7c-120">たとえば、次のコマンドでは、Format-Table コマンドレットを使用して、リモート Get-Date コマンドの出力に PSComputerName プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-120">For example, the following commands use the Format-Table cmdlet to add the PSComputerName property to the output of a remote Get-Date command.</span></span>

```powershell
$dates = invoke-command -script {get-date} -computername Server01, Server02
$dates | format-table DateTime, PSComputerName -auto

DateTime                            PSComputerName
--------                            --------------
Monday, July 21, 2008 7:16:58 PM    Server01
Monday, July 21, 2008 7:16:58 PM    Server02
```

## <a name="displaying-the-machinename-property"></a><span data-ttu-id="2ab7c-121">MACHINENAME プロパティを表示しています</span><span class="sxs-lookup"><span data-stu-id="2ab7c-121">DISPLAYING THE MACHINENAME PROPERTY</span></span>

<span data-ttu-id="2ab7c-122">Get Process、Get Service、および EventLog など、いくつかのコマンドレットには、リモートコンピューター上のオブジェクトを取得する ComputerName パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-122">Several cmdlets, including Get-Process, Get-Service, and Get-EventLog, have a ComputerName parameter that gets the objects on a remote computer.</span></span>
<span data-ttu-id="2ab7c-123">これらのコマンドレットは、PowerShell リモート処理を使用しないため、Windows PowerShell のリモート処理用に構成されていないコンピューターでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-123">These cmdlets do not use PowerShell remoting, so you can use them even on computers that are not configured for remoting in Windows PowerShell.</span></span>

<span data-ttu-id="2ab7c-124">これらのコマンドレットが返すオブジェクトは、MachineName プロパティにリモートコンピューターの名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-124">The objects that these cmdlets return store the name of the remote computer in the MachineName property.</span></span> <span data-ttu-id="2ab7c-125">(これらのオブジェクトには、PSComputerName プロパティがありません)。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-125">(These objects do not have a PSComputerName property.)</span></span>

<span data-ttu-id="2ab7c-126">たとえば、次のコマンドは、Server01 および Server02 リモートコンピューター上の PowerShell プロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-126">For example, this command gets the PowerShell process on the Server01 and Server02 remote computers.</span></span> <span data-ttu-id="2ab7c-127">既定の表示には、MachineName プロパティは含まれません。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-127">The default display does not include the MachineName property.</span></span>

```powershell
C:\PS> get-process PowerShell -computername server01, server02

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
920      38    97524     114504   575     9.66   2648 PowerShell
194       6    24256      32384   142            3020 PowerShell
352      27    63472      63520   577     3.84   4796 PowerShell
```

<span data-ttu-id="2ab7c-128">Format-Table コマンドレットを使用して、プロセスオブジェクトの MachineName プロパティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-128">You can use the Format-Table cmdlet to display the MachineName property of the process objects.</span></span>

<span data-ttu-id="2ab7c-129">たとえば、次のコマンドは、$p 変数にプロセスを保存し、パイプライン演算子 (|) を使用して $p 内のプロセスを Format-Table コマンドに送信します。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-129">For example, the following command saves the processes in the $p variable and then uses a pipeline operator (|) to send the processes in $p to the Format-Table command.</span></span> <span data-ttu-id="2ab7c-130">このコマンドは、Format-Table の Property パラメーターを使用して、MachineName プロパティをディスプレイに含めます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-130">The command uses the Property parameter of Format-Table to include the MachineName property in the display.</span></span>

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02
C:\PS> $P | format-table -property ID, ProcessName, MachineName -auto

Id ProcessName MachineName
-- ----------- -----------
2648 PowerShell  Server02
3020 PowerShell  Server01
4796 PowerShell  Server02
```

<span data-ttu-id="2ab7c-131">次のより複雑なコマンドは、MachineName プロパティを既定のプロセスの表示に追加します。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-131">The following more complex command adds the MachineName property to the default process display.</span></span> <span data-ttu-id="2ab7c-132">ハッシュテーブルを使用して、計算されるプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-132">It uses hash tables to specify calculated properties.</span></span> <span data-ttu-id="2ab7c-133">幸い、それを使用するために理解する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-133">Fortunately, you do not have to understand it to use it.</span></span>

<span data-ttu-id="2ab7c-134">(バックティック ['] が継続文字であることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-134">(Note that the backtick [\`] is the continuation character.)</span></span>

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

## <a name="deserialized-objects"></a><span data-ttu-id="2ab7c-135">逆シリアル化されたオブジェクト</span><span class="sxs-lookup"><span data-stu-id="2ab7c-135">DESERIALIZED OBJECTS</span></span>

<span data-ttu-id="2ab7c-136">出力を生成するリモートコマンドを実行すると、コマンドの出力がネットワーク経由でローカルコンピューターに転送されます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-136">When you run remote commands that generate output, the command output is transmitted across the network back to the local computer.</span></span>

<span data-ttu-id="2ab7c-137">ほとんどのライブ Microsoft .NET フレームワークオブジェクト (PowerShell コマンドレットが返すオブジェクトなど) はネットワーク経由で転送できないため、ライブオブジェクトは "シリアル化" されます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-137">Because most live Microsoft .NET Framework objects (such as the objects that PowerShell cmdlets return) cannot be transmitted over the network, the live objects are "serialized".</span></span> <span data-ttu-id="2ab7c-138">つまり、ライブオブジェクトは、オブジェクトとそのプロパティの XML 表現に変換されます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-138">In other words, the live objects are converted into XML representations of the object and its properties.</span></span> <span data-ttu-id="2ab7c-139">次に、XML ベースのシリアル化されたオブジェクトがネットワーク経由で転送されます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-139">Then, the XML-based serialized object is transmitted across the network.</span></span>

<span data-ttu-id="2ab7c-140">ローカルコンピューターでは、PowerShell は xml ベースのシリアル化されたオブジェクトを受け取り、XML ベースのオブジェクトを標準の .NET Framework オブジェクトに変換することによって "逆シリアル化" します。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-140">On the local computer, PowerShell receives the XML-based serialized object and "deserializes" it by converting the XML-based object into a standard .NET Framework object.</span></span>

<span data-ttu-id="2ab7c-141">ただし、逆シリアル化されたオブジェクトはライブオブジェクトではありません。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-141">However, the deserialized object is not a live object.</span></span> <span data-ttu-id="2ab7c-142">これは、シリアル化された時点のオブジェクトのスナップショットであり、プロパティは含まれていますが、メソッドは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-142">It is a snapshot of the object at the time that it was serialized, and it includes properties but no methods.</span></span> <span data-ttu-id="2ab7c-143">これらのオブジェクトは、パイプラインで渡す、選択したプロパティを表示する、書式設定するなど、PowerShell で使用および管理できます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-143">You can use and manage these objects in PowerShell, including passing them in pipelines, displaying selected properties, and formatting them.</span></span>

<span data-ttu-id="2ab7c-144">逆シリアル化されたオブジェクトのほとんどは、Types.ps1xml ファイルまたは Format.ps1xml ファイル内のエントリによって表示されるように自動的に書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-144">Most deserialized objects are automatically formatted for display by entries in the Types.ps1xml or Format.ps1xml files.</span></span> <span data-ttu-id="2ab7c-145">ただし、リモートコンピューター上で生成されたすべての逆シリアル化されたオブジェクトのフォーマットファイルがローカルコンピューターにない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-145">However, the local computer might not have formatting files for all of the deserialized objects that were generated on a remote computer.</span></span> <span data-ttu-id="2ab7c-146">オブジェクトが書式設定されていない場合、各オブジェクトのプロパティはすべて、ストリーミングリストのコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-146">When objects are not formatted, all of the properties of each object appear in the console in a streaming list.</span></span>

<span data-ttu-id="2ab7c-147">オブジェクトが自動的に書式設定されない場合は、Format-Table や形式一覧などの書式設定コマンドレットを使用して、選択したプロパティを書式設定して表示できます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-147">When objects are not formatted automatically, you can use the formatting cmdlets, such as Format-Table or Format-List, to format and display selected properties.</span></span> <span data-ttu-id="2ab7c-148">または、Out-GridView コマンドレットを使用して、テーブル内のオブジェクトを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-148">Or, you can use the Out-GridView cmdlet to display the objects in a table.</span></span>

<span data-ttu-id="2ab7c-149">また、ローカルコンピューター上に存在しないコマンドレットを使用しているリモートコンピューターでコマンドを実行した場合、そのコマンドが返すオブジェクトは、コンピューター上のオブジェクトの書式設定ファイルを持っていないため、正しくフォーマットされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-149">Also, if you run a command on a remote computer that uses cmdlets that you do not have on your local computer, the objects that the command returns might not be formatted properly because you do not have the formatting files for those objects on your computer.</span></span> <span data-ttu-id="2ab7c-150">別のコンピューターから書式設定データを取得するには、Get-FormatData と Export-FormatData のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-150">To get formatting data from another computer, use the Get-FormatData and Export-FormatData cmdlets.</span></span>

<span data-ttu-id="2ab7c-151">DirectoryInfo オブジェクトや Guid など、オブジェクトの種類によっては、受信時にライブオブジェクトに変換されます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-151">Some object types, such as DirectoryInfo objects and GUIDs, are converted back into live objects when they are received.</span></span> <span data-ttu-id="2ab7c-152">これらのオブジェクトは、特別な処理や書式設定を必要としません。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-152">These objects do not need any special handling or formatting.</span></span>

## <a name="ordering-the-results"></a><span data-ttu-id="2ab7c-153">結果の順序付け</span><span class="sxs-lookup"><span data-stu-id="2ab7c-153">ORDERING THE RESULTS</span></span>

<span data-ttu-id="2ab7c-154">コマンドレットの ComputerName パラメーターに指定されたコンピューター名の順序によって、PowerShell がリモートコンピューターに接続する順序が決まります。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-154">The order of the computer names in the ComputerName parameter of cmdlets determines the order in which PowerShell connects to the remote computers.</span></span> <span data-ttu-id="2ab7c-155">ただし、結果は、ローカルコンピューターが受信した順序で表示されます。順序は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-155">However, the results appear in the order in which the local computer receives them, which might be a different order.</span></span>

<span data-ttu-id="2ab7c-156">結果の順序を変更するには、Sort-Object コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-156">To change the order of the results, use the Sort-Object cmdlet.</span></span> <span data-ttu-id="2ab7c-157">PSComputerName または MachineName プロパティで並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-157">You can sort on the PSComputerName or MachineName property.</span></span> <span data-ttu-id="2ab7c-158">また、別のコンピューターの結果が散在するように、オブジェクトの別のプロパティを並べ替えることもできます。</span><span class="sxs-lookup"><span data-stu-id="2ab7c-158">You can also sort on another property of the object so that the results from different computers are interspersed.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ab7c-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ab7c-159">SEE ALSO</span></span>

[<span data-ttu-id="2ab7c-160">about_Remote</span><span class="sxs-lookup"><span data-stu-id="2ab7c-160">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="2ab7c-161">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="2ab7c-161">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="2ab7c-162">Format-Table</span><span class="sxs-lookup"><span data-stu-id="2ab7c-162">Format-Table</span></span>](xref:Microsoft.PowerShell.Utility.Format-Table)

[<span data-ttu-id="2ab7c-163">Get-Process</span><span class="sxs-lookup"><span data-stu-id="2ab7c-163">Get-Process</span></span>](xref:Microsoft.PowerShell.Management.Get-Process)

[<span data-ttu-id="2ab7c-164">Get-Service</span><span class="sxs-lookup"><span data-stu-id="2ab7c-164">Get-Service</span></span>](xref:Microsoft.PowerShell.Management.Get-Service)

[<span data-ttu-id="2ab7c-165">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="2ab7c-165">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="2ab7c-166">Select-Object</span><span class="sxs-lookup"><span data-stu-id="2ab7c-166">Select-Object</span></span>](xref:Microsoft.PowerShell.Utility.Select-Object)

