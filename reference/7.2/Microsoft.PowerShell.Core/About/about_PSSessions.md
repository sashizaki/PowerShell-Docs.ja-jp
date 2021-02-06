---
description: PowerShell セッション (PSSessions) について説明し、リモートコンピューターへの永続的な接続を確立する方法について説明します。
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssessions?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSessions
ms.openlocfilehash: edc7109f3f79376ac1d348d3c3cd65e3a8d3e69c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602751"
---
# <a name="about-pssessions"></a><span data-ttu-id="5d40e-103">PSSessions について</span><span class="sxs-lookup"><span data-stu-id="5d40e-103">About PSSessions</span></span>

## <a name="short-description"></a><span data-ttu-id="5d40e-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="5d40e-104">Short Description</span></span>
<span data-ttu-id="5d40e-105">PowerShell セッション (PSSessions) について説明し、リモートコンピューターへの永続的な接続を確立する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-105">Describes PowerShell sessions (PSSessions) and explains how to establish a persistent connection to a remote computer.</span></span>

## <a name="long-description"></a><span data-ttu-id="5d40e-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="5d40e-106">Long Description</span></span>

<span data-ttu-id="5d40e-107">リモートコンピューターで PowerShell コマンドを実行するには、コマンドレットの **ComputerName** パラメーターを使用するか、または powershell セッション (pssession) を作成し、pssession でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-107">To run PowerShell commands on a remote computer, you can use the **ComputerName** parameter of a cmdlet, or you can create a PowerShell session (PSSession) and run commands in the PSSession.</span></span>

<span data-ttu-id="5d40e-108">PSSession を作成すると、PowerShell によって、リモートコンピューターへの永続的な接続が確立されます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-108">When you create a PSSession, PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="5d40e-109">PSSession を使用して、リモートコンピューターで一連の関連コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-109">Use a PSSession to run a series of related commands on a remote computer.</span></span> <span data-ttu-id="5d40e-110">同じ PSSession で実行されるコマンドは、変数、別名、関数の値などのデータを共有できます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-110">Commands that run in the same PSSession can share data, such as the values of variables, aliases, and functions.</span></span>

<span data-ttu-id="5d40e-111">また、ローカルコンピューター上に PSSession を作成し、その中でコマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-111">You can also create a PSSession on the local computer and run commands in it.</span></span>
<span data-ttu-id="5d40e-112">ローカル PSSession は、PowerShell リモート処理インフラストラクチャを使用して PSSession を作成および維持します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-112">A local PSSession uses the PowerShell remoting infrastructure to create and maintain the PSSession.</span></span>

<span data-ttu-id="5d40e-113">Windows PowerShell 3.0 以降では、PSSessions は、そのセッションが作成されたセッションから独立しています。</span><span class="sxs-lookup"><span data-stu-id="5d40e-113">Beginning in Windows PowerShell 3.0, PSSessions are independent of the sessions in which they are created.</span></span> <span data-ttu-id="5d40e-114">アクティブな PSSessions は、リモートコンピューター (または、リモートエンドまたは接続の "サーバー側" にあるコンピューター) 上で保持されます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-114">Active PSSessions are maintained on the remote computer (or the computer at the remote end or "server-side" of the connection).</span></span> <span data-ttu-id="5d40e-115">その結果、PSSession から切断し、後で同じコンピューターまたは別のコンピューターから再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-115">As a result, you can disconnect from the PSSession and reconnect to it at a later time from the same computer or from a different computer.</span></span>

<span data-ttu-id="5d40e-116">このトピックでは、PSSessions を作成、使用、取得、および削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-116">This topic explains how to create, use, get, and delete PSSessions.</span></span> <span data-ttu-id="5d40e-117">詳細については、「 [about_PSSession_Details](about_PSSession_Details.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d40e-117">For more advanced information, see [about_PSSession_Details](about_PSSession_Details.md).</span></span>

<span data-ttu-id="5d40e-118">注: PSSessions は、PowerShell リモート処理インフラストラクチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-118">Note: PSSessions use the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="5d40e-119">PSSessions を使用するには、ローカルコンピューターとリモートコンピューターがリモート処理用に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d40e-119">To use PSSessions, the local and remote computers must be configured for remoting.</span></span>
<span data-ttu-id="5d40e-120">詳細については、「[about_Remote_Requirements](about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d40e-120">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

<span data-ttu-id="5d40e-121">Windows Vista 以降のバージョンの Windows では、ローカルコンピューター上に PSSession を作成するには、[管理者として実行] オプションを使用して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d40e-121">In Windows Vista and later versions of Windows, to create a PSSession on a local computer, you must start PowerShell with the "Run as administrator" option.</span></span>

## <a name="what-is-a-session"></a><span data-ttu-id="5d40e-122">セッションとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="5d40e-122">What Is a Session?</span></span>

<span data-ttu-id="5d40e-123">セッションとは、PowerShell が実行される環境です。</span><span class="sxs-lookup"><span data-stu-id="5d40e-123">A session is an environment in which PowerShell runs.</span></span>

<span data-ttu-id="5d40e-124">PowerShell を起動するたびに、セッションが作成され、そのセッションでコマンドを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5d40e-124">Each time you start PowerShell, a session is created for you, and you can run commands in the session.</span></span> <span data-ttu-id="5d40e-125">また、モジュールやスナップインなどの項目をセッションに追加したり、変数、関数、別名などの項目を作成したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-125">You can also add items to your session, such as modules and snap-ins, and you can create items, such as variables, functions, and aliases.</span></span> <span data-ttu-id="5d40e-126">これらの項目はセッションにのみ存在し、セッションが終了すると削除されます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-126">These items exist only in the session and are deleted when the session ends.</span></span>

<span data-ttu-id="5d40e-127">また、ローカルコンピューターまたはリモートコンピューター上で、"PowerShell セッション" または "PSSessions" と呼ばれるユーザー管理セッションを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-127">You can also create user-managed sessions, known as " PowerShell sessions" or "PSSessions," on the local computer or on a remote computer.</span></span> <span data-ttu-id="5d40e-128">既定のセッションと同様に、PSSession でコマンドを実行し、項目を追加および作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-128">Like the default session, you can run commands in a PSSession and add and create items.</span></span> <span data-ttu-id="5d40e-129">ただし、自動的に開始されるセッションとは異なり、作成する pssession を制御できます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-129">However, unlike the session that starts automatically, you can control the PSSessions that you create.</span></span> <span data-ttu-id="5d40e-130">これらの情報は、取得、作成、構成、および削除したり、接続を解除して再接続したり、同じ PSSession で複数のコマンドを実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-130">You can get, create, configure, and remove them, disconnect and reconnect to them, and run multiple commands in the same PSSession.</span></span> <span data-ttu-id="5d40e-131">PSSession は、削除するか、タイムアウトになるまで使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-131">The PSSession remains available until you delete it or it times out.</span></span>

<span data-ttu-id="5d40e-132">通常は、PSSession を作成して、リモートコンピューターで一連の関連コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-132">Typically, you create a PSSession to run a series of related commands on a remote computer.</span></span> <span data-ttu-id="5d40e-133">リモートコンピューター上に PSSession を作成すると、PowerShell は、セッションをサポートするために、リモートコンピューターへの永続的な接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-133">When you create a PSSession on a remote computer, PowerShell establishes a persistent connection to the remote computer to support the session.</span></span>

<span data-ttu-id="5d40e-134">またはコマンドレットの **ComputerName** パラメーターを使用して `Invoke-Command` `Enter-PSSession` リモートコマンドを実行したり、対話型セッションを開始したりする場合、PowerShell はリモートコンピューター上に一時的なセッションを作成し、コマンドが完了するか、対話型セッションが終了するとすぐにセッションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-134">If you use the **ComputerName** parameter of the `Invoke-Command` or `Enter-PSSession` cmdlet to run a remote command or to start an interactive session, PowerShell creates a temporary session on the remote computer and closes the session as soon as the command is complete or as soon as the interactive session ends.</span></span> <span data-ttu-id="5d40e-135">これらの一時的なセッションを制御することはできません。また、複数のコマンドや単一の対話型セッションで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="5d40e-135">You cannot control these temporary sessions, and you cannot use them for more than a single command or a single interactive session.</span></span>

<span data-ttu-id="5d40e-136">PowerShell では、"現在のセッション" は、使用しているセッションです。</span><span class="sxs-lookup"><span data-stu-id="5d40e-136">In PowerShell, the "current session" is the session that you are working in.</span></span> <span data-ttu-id="5d40e-137">"現在のセッション" は、一時的なセッションまたは PSSession を含む任意のセッションを参照できます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-137">The "current session" can refer to any session, including a temporary session or a PSSession.</span></span>

## <a name="why-use-a-pssession"></a><span data-ttu-id="5d40e-138">PSSession を使用する理由</span><span class="sxs-lookup"><span data-stu-id="5d40e-138">Why Use a PSSession?</span></span>

<span data-ttu-id="5d40e-139">リモートコンピューターへの永続的な接続が必要な場合は、PSSession を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-139">Use a PSSession when you need a persistent connection to a remote computer.</span></span>
<span data-ttu-id="5d40e-140">PSSession を使用すると、変数の値、関数の内容、エイリアスの定義など、データを共有する一連のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-140">With a PSSession, you can run a series of commands that share data, such as the value of variables, the contents of a function, or the definition of an alias.</span></span>

<span data-ttu-id="5d40e-141">PSSession を作成しなくても、リモートコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-141">You can run remote commands without creating a PSSession.</span></span> <span data-ttu-id="5d40e-142">1つまたは複数のコンピューターで1つのコマンドまたは一連の関連のないコマンドを実行するには、リモート対応のコマンドレットの **ComputerName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-142">Use the **ComputerName** parameter of remote-enabled cmdlets to run a single command or a series of unrelated commands on one or many computers.</span></span>

<span data-ttu-id="5d40e-143">またはの **ComputerName** パラメーターを使用すると、PowerShell によって `Invoke-Command` `Enter-PSSession` リモートコンピューターへの一時的な接続が確立され、コマンドが完了するとすぐに接続が閉じられます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-143">When you use the **ComputerName** parameter of `Invoke-Command` or `Enter-PSSession`, PowerShell establishes a temporary connection to the remote computer and then closes the connection as soon as the command is complete.</span></span> <span data-ttu-id="5d40e-144">作成したデータ要素は、接続が閉じられると失われます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-144">Any data elements that you create are lost when the connection is closed.</span></span>

<span data-ttu-id="5d40e-145">やなどの **ComputerName** パラメーターを持つ他のコマンド `Get-Eventlog` レット `Get-WmiObject` では、さまざまなリモート処理テクノロジを使用してデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-145">Other cmdlets that have a **ComputerName** parameter, such as `Get-Eventlog` and `Get-WmiObject`, use different remoting technologies to gather data.</span></span> <span data-ttu-id="5d40e-146">None PSSession のような永続的な接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-146">None create a persistent connection like a PSSession.</span></span>

## <a name="how-to-create-a-pssession"></a><span data-ttu-id="5d40e-147">PSSession を作成する方法</span><span class="sxs-lookup"><span data-stu-id="5d40e-147">How to Create a PSSession</span></span>

<span data-ttu-id="5d40e-148">PSSession を作成するには、 `New-PSSession` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-148">To create a PSSession, use the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="5d40e-149">リモートコンピューター上に PSSession を作成するには、コマンドレットの **ComputerName** パラメーターを使用し `New-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-149">To create the PSSession on a remote computer, use the **ComputerName** parameter of the `New-PSSession` cmdlet.</span></span>

<span data-ttu-id="5d40e-150">たとえば、次のコマンドは、Server01 コンピューター上に新しい PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-150">For example, the following command creates a new PSSession on the Server01 computer.</span></span>

```powershell
New-PSSession -ComputerName Server01
```

<span data-ttu-id="5d40e-151">コマンドを送信すると、は `New-PSSession` pssession を作成し、pssession を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-151">When you submit the command, `New-PSSession` creates the PSSession and returns an object that represents the PSSession.</span></span> <span data-ttu-id="5d40e-152">PSSession の作成時に変数にオブジェクトを保存することも、コマンドを使用して `Get-PSSession` 後で pssession を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-152">You can save the object in a variable when you create the PSSession, or you can use a `Get-PSSession` command to get the PSSession at a later time.</span></span>

<span data-ttu-id="5d40e-153">たとえば、次のコマンドは、Server01 コンピューター上に新しい PSSession を作成し、結果として生成されたオブジェクトを $ps 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-153">For example, the following command creates a new PSSession on the Server01 computer and saves the resulting object in the $ps variable.</span></span>

```powershell
$ps = New-PSSession -ComputerName Server01
```

## <a name="how-to-create-pssessions-on-multiple-computers"></a><span data-ttu-id="5d40e-154">複数のコンピューターに PSSessions を作成する方法</span><span class="sxs-lookup"><span data-stu-id="5d40e-154">How to Create PSSessions on Multiple Computers</span></span>

<span data-ttu-id="5d40e-155">複数のコンピューターで PSSessions を作成するには、コマンドレットの **ComputerName** パラメーターを使用し `New-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-155">To create PSSessions on multiple computers, use the **ComputerName** parameter of the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="5d40e-156">コンマ区切りの一覧で、リモートコンピューターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-156">Type the names of the remote computers in a comma-separated list.</span></span>

<span data-ttu-id="5d40e-157">たとえば、Server01、Server02、および Server03 コンピューターで PSSessions を作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-157">For example, to create PSSessions on the Server01, Server02, and Server03 computers, type:</span></span>

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
```

<span data-ttu-id="5d40e-158">`New-PSSession` 各リモートコンピューターに1つの PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-158">`New-PSSession` creates one PSSession on each of the remote computers.</span></span>

## <a name="how-to-get-pssessions"></a><span data-ttu-id="5d40e-159">PSSessions を取得する方法</span><span class="sxs-lookup"><span data-stu-id="5d40e-159">How to Get PSSessions</span></span>

<span data-ttu-id="5d40e-160">現在のセッションで作成された pssession を取得するには、 `Get-PSSession` **ComputerName** パラメーターを指定せずにコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-160">To get the PSSessions that were created in your current session, use the `Get-PSSession` cmdlet without the **ComputerName** parameter.</span></span> <span data-ttu-id="5d40e-161">`Get-PSSession` 返されるオブジェクトと同じ型を返し `New-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-161">`Get-PSSession` returns the same type of object that `New-PSSession` returns.</span></span>

<span data-ttu-id="5d40e-162">次のコマンドは、現在のセッションで作成されたすべての pssession を取得します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-162">The following command gets all the PSSessions that were created in the current session.</span></span>

```powershell
Get-PSSession
```

<span data-ttu-id="5d40e-163">PSSessions の既定の表示には、その ID と既定の表示名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-163">The default display of the PSSessions shows their ID and a default display name.</span></span> <span data-ttu-id="5d40e-164">セッションを作成するときに、別の表示名を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-164">You can assign an alternate display name when you create the session.</span></span>

```output
Id   Name       ComputerName    State    ConfigurationName
---  ----       ------------    -----    ---------------------
1    Session1   Server01        Opened   Microsoft.PowerShell
2    Session2   Server02        Opened   Microsoft.PowerShell
3    Session3   Server03        Opened   Microsoft.PowerShell
```

<span data-ttu-id="5d40e-165">また、PSSessions を変数に保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-165">You can also save the PSSessions in a variable.</span></span> <span data-ttu-id="5d40e-166">次のコマンドは、PSSessions を取得し、ps123 変数に保存し \$ ます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-166">The following command gets the PSSessions and saves them in the \$ps123 variable.</span></span>

```powershell
$ps123 = Get-PSSession
```

<span data-ttu-id="5d40e-167">PSSession のコマンドレットを使用する場合、PSSession はその ID、名前、またはそのインスタンス ID (GUID) で参照できます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-167">When using the PSSession cmdlets, you can refer to a PSSession by its ID, by its name, or by its instance ID (a GUID).</span></span> <span data-ttu-id="5d40e-168">次のコマンドは、その ID で PSSession を取得し、ps01 変数に保存し \$ ます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-168">The following command gets a PSSession by its ID and saves it in the \$ps01 variable.</span></span>

```powershell
$ps01 = Get-PSSession -Id 1
```

<span data-ttu-id="5d40e-169">Windows PowerShell 3.0 以降では、PSSessions はリモートコンピューター上で保持されます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-169">Beginning in Windows PowerShell 3.0, PSSessions are maintained on the remote computer.</span></span> <span data-ttu-id="5d40e-170">特定のリモートコンピューターで作成した PSSessions を取得するには、コマンドレットの **ComputerName** パラメーターを使用し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-170">To get PSSessions that you created on particular remote computers, use the **ComputerName** parameter of the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="5d40e-171">次のコマンドは、Server01 リモートコンピューター上で作成した pssession を取得します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-171">The following command gets the PSSessions that you created on the Server01 remote computer.</span></span> <span data-ttu-id="5d40e-172">これには、現在のセッションで作成された pssession と、ローカルコンピューターまたは他のコンピューター上の他のセッションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-172">This includes PSSessions created in the current session and in other sessions on the local computer or other computers.</span></span>

```powershell
Get-PSSession -ComputerName Server01
```

<span data-ttu-id="5d40e-173">Windows PowerShell 2.0 では、 `Get-PSSession` 現在のセッションで作成された pssession のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-173">In Windows PowerShell 2.0, `Get-PSSession` gets only the PSSessions that were created in the current session.</span></span> <span data-ttu-id="5d40e-174">セッションがに接続され、ローカルコンピューターでコマンドを実行している場合でも、他のセッションまたは他のコンピューターで作成された pssession は取得されません。</span><span class="sxs-lookup"><span data-stu-id="5d40e-174">It does not get PSSessions that were created in other sessions or on other computers, even if the sessions are connected to and are running commands on the local computer.</span></span>

## <a name="how-to-run-commands-in-a-pssession"></a><span data-ttu-id="5d40e-175">PSSession でコマンドを実行する方法</span><span class="sxs-lookup"><span data-stu-id="5d40e-175">How to Run Commands in a PSSession</span></span>

<span data-ttu-id="5d40e-176">1つ以上の PSSessions でコマンドを実行するには、コマンドレットを使用し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-176">To run a command in one or more PSSessions, use the `Invoke-Command` cmdlet.</span></span>
<span data-ttu-id="5d40e-177">セッションパラメーターを使用して、PSSessions と **ScriptBlock** パラメーターを指定してコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-177">Use the Session parameter to specify the PSSessions and the **ScriptBlock** parameter to specify the command.</span></span>

<span data-ttu-id="5d40e-178">たとえば、 `Get-ChildItem` $ps 123 変数に保存された3つの PSSessions のそれぞれで ("dir") コマンドを実行するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-178">For example, to run a `Get-ChildItem` ("dir") command in each of the three PSSessions saved in the $ps123 variable, type:</span></span>

```powershell
Invoke-Command -Session $ps123 -ScriptBlock { Get-ChildItem }
```

## <a name="how-to-delete-pssessions"></a><span data-ttu-id="5d40e-179">PSSessions を削除する方法</span><span class="sxs-lookup"><span data-stu-id="5d40e-179">How to Delete PSSessions</span></span>

<span data-ttu-id="5d40e-180">PSSession が終了したら、コマンドレットを使用し `Remove-PSSession` て pssession を削除し、使用していたリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-180">When you are finished with the PSSession, use the `Remove-PSSession` cmdlet to delete the PSSession and to release the resources that it was using.</span></span>

```powershell
Remove-PSSession -Session $ps
```

<span data-ttu-id="5d40e-181">または</span><span class="sxs-lookup"><span data-stu-id="5d40e-181">or</span></span>

```powershell
Remove-PSSession -Id 1
```

<span data-ttu-id="5d40e-182">リモートコンピューターから PSSession を削除するには、コマンドレットの **ComputerName** パラメーターを使用し `Remove-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-182">To remove a PSSession from a remote computer, use the **ComputerName** parameter of the `Remove-PSSession` cmdlet.</span></span>

```powershell
Remove-PSSession -ComputerName Server01 -Id 1
```

<span data-ttu-id="5d40e-183">PSSession を削除しない場合、PSSession はタイムアウトするまで使用可能な状態のままになります。</span><span class="sxs-lookup"><span data-stu-id="5d40e-183">If you do not delete the PSSession, the PSSession remains available for use until it times out.</span></span>

<span data-ttu-id="5d40e-184">コマンドレットの **IdleTimeout** パラメーターを使用して、 `New-PSSessionOption` アイドル状態の PSSession の有効期限を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d40e-184">You can also use the **IdleTimeout** parameter of the `New-PSSessionOption` cmdlet to set an expiration time for an idle PSSession.</span></span> <span data-ttu-id="5d40e-185">詳細については、「 [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d40e-185">For more information, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

## <a name="the-pssession-cmdlets"></a><span data-ttu-id="5d40e-186">PSSession のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="5d40e-186">The PSSession Cmdlets</span></span>

<span data-ttu-id="5d40e-187">PSSession のコマンドレットの一覧を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-187">For a list of PSSession cmdlets, type:</span></span>

```powershell
Get-Help *-PSSession
```

- <span data-ttu-id="5d40e-188">接続-PSSession: PSSession を現在のセッションに接続します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-188">Connect-PSSession: Connects a PSSession to the current session</span></span>
- <span data-ttu-id="5d40e-189">切断-PSSession: 現在のセッションから PSSession を切断します</span><span class="sxs-lookup"><span data-stu-id="5d40e-189">Disconnect-PSSession: Disconnects a PSSession from the current session</span></span>
- <span data-ttu-id="5d40e-190">入力-PSSession: 対話型セッションを開始します</span><span class="sxs-lookup"><span data-stu-id="5d40e-190">Enter-PSSession: Starts an interactive session</span></span>
- <span data-ttu-id="5d40e-191">終了-PSSession: 対話型セッションを終了します</span><span class="sxs-lookup"><span data-stu-id="5d40e-191">Exit-PSSession: Ends an interactive session</span></span>
- <span data-ttu-id="5d40e-192">Get-help: 現在のセッションの PSSession を取得します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-192">Get-PSSession: Gets the PSSessions in the current session</span></span>
- <span data-ttu-id="5d40e-193">新規-PSSession: ローカルコンピューターまたはリモートコンピューター上に新しい PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-193">New-PSSession: Creates a new PSSession on a local or remote computer</span></span>
- <span data-ttu-id="5d40e-194">受信-PSSession: 切断されたセッションで実行されたコマンドの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-194">Receive-PSSession: Gets the results of commands that ran in a disconnected session</span></span>
- <span data-ttu-id="5d40e-195">-PSSession の削除: 現在のセッションの PSSession を削除します。</span><span class="sxs-lookup"><span data-stu-id="5d40e-195">Remove-PSSession: Deletes the PSSessions in the current session</span></span>

## <a name="for-more-information"></a><span data-ttu-id="5d40e-196">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5d40e-196">For More Information</span></span>

<span data-ttu-id="5d40e-197">PSSessions の詳細については、「 [about_PSSession_Details](about_PSSession_Details.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d40e-197">For more information about PSSessions, see [about_PSSession_Details](about_PSSession_Details.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5d40e-198">参照</span><span class="sxs-lookup"><span data-stu-id="5d40e-198">See Also</span></span>

[<span data-ttu-id="5d40e-199">about_Remote</span><span class="sxs-lookup"><span data-stu-id="5d40e-199">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="5d40e-200">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="5d40e-200">about_Remote_Disconnected_Sessions</span></span>](about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="5d40e-201">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="5d40e-201">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="5d40e-202">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="5d40e-202">Connect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Connect-PSSession)

[<span data-ttu-id="5d40e-203">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="5d40e-203">Disconnect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Disconnect-PSSession)

[<span data-ttu-id="5d40e-204">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="5d40e-204">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="5d40e-205">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="5d40e-205">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)

[<span data-ttu-id="5d40e-206">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="5d40e-206">Get-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSession)

[<span data-ttu-id="5d40e-207">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="5d40e-207">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="5d40e-208">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="5d40e-208">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="5d40e-209">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="5d40e-209">Remove-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Remove-PSSession)

