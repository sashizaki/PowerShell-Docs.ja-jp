---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSession
ms.openlocfilehash: c9c927ccdbc70d07ad8fa2cf13f3e2fe4a83f8c5
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218216"
---
# <span data-ttu-id="d001a-103">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="d001a-103">Get-PSSession</span></span>

## <span data-ttu-id="d001a-104">概要</span><span class="sxs-lookup"><span data-stu-id="d001a-104">SYNOPSIS</span></span>
<span data-ttu-id="d001a-105">ローカルコンピューターとリモートコンピューター上の PowerShell セッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-105">Gets the PowerShell sessions on local and remote computers.</span></span>

## <span data-ttu-id="d001a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d001a-106">SYNTAX</span></span>

### <span data-ttu-id="d001a-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="d001a-107">Name (Default)</span></span>

```
Get-PSSession [-Name <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="d001a-108">[ComputerName]</span><span class="sxs-lookup"><span data-stu-id="d001a-108">ComputerName</span></span>

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="d001a-109">ComputerInstanceId</span><span class="sxs-lookup"><span data-stu-id="d001a-109">ComputerInstanceId</span></span>

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="d001a-110">ConnectionUriInstanceId</span><span class="sxs-lookup"><span data-stu-id="d001a-110">ConnectionUriInstanceId</span></span>

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection] -InstanceId <Guid[]>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-ThrottleLimit <Int32>] [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="d001a-111">ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="d001a-111">ConnectionUri</span></span>

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-ThrottleLimit <Int32>] [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="d001a-112">ContainerId</span><span class="sxs-lookup"><span data-stu-id="d001a-112">ContainerId</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="d001a-113">ContainerIdInstanceId</span><span class="sxs-lookup"><span data-stu-id="d001a-113">ContainerIdInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="d001a-114">VMId</span><span class="sxs-lookup"><span data-stu-id="d001a-114">VMId</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>] -VMId <Guid[]>
 [<CommonParameters>]
```

### <span data-ttu-id="d001a-115">VMIdInstanceId</span><span class="sxs-lookup"><span data-stu-id="d001a-115">VMIdInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>] -VMId <Guid[]>
 [<CommonParameters>]
```

### <span data-ttu-id="d001a-116">VMName</span><span class="sxs-lookup"><span data-stu-id="d001a-116">VMName</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>] -VMName <String[]>
 [<CommonParameters>]
```

### <span data-ttu-id="d001a-117">VMNameInstanceId</span><span class="sxs-lookup"><span data-stu-id="d001a-117">VMNameInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="d001a-118">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d001a-118">InstanceId</span></span>

```
Get-PSSession [-InstanceId <Guid[]>] [<CommonParameters>]
```

### <span data-ttu-id="d001a-119">Id</span><span class="sxs-lookup"><span data-stu-id="d001a-119">Id</span></span>

```
Get-PSSession [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="d001a-120">Description</span><span class="sxs-lookup"><span data-stu-id="d001a-120">DESCRIPTION</span></span>

<span data-ttu-id="d001a-121">`Get-PSSession`コマンドレットは、ローカルコンピューターとリモートコンピューター上 **PSSessions** のユーザー管理の PowerShell セッション (pssession) を取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-121">The `Get-PSSession` cmdlet gets the user-managed PowerShell sessions ( **PSSessions** ) on local and remote computers.</span></span>

<span data-ttu-id="d001a-122">Windows PowerShell 3.0 以降では、セッションは各接続のリモートエンドのコンピューターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d001a-122">Starting in Windows PowerShell 3.0, sessions are stored on the computers at the remote end of each connection.</span></span> <span data-ttu-id="d001a-123">の **ComputerName** パラメーターまたは **connectionuri** パラメーターを使用すると、 `Get-PSSession` 現在のセッションで作成されていない場合でも、ローカルコンピューターまたはリモートコンピューターに接続するセッションを取得できます。</span><span class="sxs-lookup"><span data-stu-id="d001a-123">You can use the **ComputerName** or **ConnectionUri** parameters of `Get-PSSession` to get the sessions that connect to the local computer or remote computers, even if they were not created in the current session.</span></span>

<span data-ttu-id="d001a-124">パラメーターを指定しない場合は、 `Get-PSSession` 現在のセッションで作成されたすべてのセッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-124">Without parameters, `Get-PSSession` gets all sessions that were created in the current session.</span></span>

<span data-ttu-id="d001a-125">**名前** 、 **ID** 、 **InstanceID** 、 **State** 、 **ApplicationName** 、 **ConfigurationName** などのフィルター処理パラメーターを使用して、が返すセッションの中から選択し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-125">Use the filtering parameters, including **Name** , **ID** , **InstanceID** , **State** , **ApplicationName** , and **ConfigurationName** to select from among the sessions that `Get-PSSession` returns.</span></span>

<span data-ttu-id="d001a-126">残りのパラメーターを使用して、 `Get-PSSession` **ComputerName** パラメーターまたは **connectionuri** パラメーターを使用したときにコマンドが実行される一時的な接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="d001a-126">Use the remaining parameters to configure the temporary connection in which the `Get-PSSession` command runs when you use the **ComputerName** or **ConnectionUri** parameters.</span></span>

<span data-ttu-id="d001a-127">注: Windows PowerShell 2.0 では、パラメーターを指定しない場合、 `Get-PSSession` 現在のセッションで作成されたすべてのセッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-127">NOTE: In Windows PowerShell 2.0, without parameters, `Get-PSSession` gets all sessions that were created in the current session.</span></span> <span data-ttu-id="d001a-128">**ComputerName** パラメーターは、現在のセッションで作成されたセッションを取得し、指定されたコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="d001a-128">The **ComputerName** parameter gets sessions that were created in the current session and connect to the specified computer.</span></span>

<span data-ttu-id="d001a-129">PowerShell セッションの詳細については、「 [about_PSSessions](about/about_PSSessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d001a-129">For more information about PowerShell sessions, see [about_PSSessions](about/about_PSSessions.md).</span></span>

## <span data-ttu-id="d001a-130">例</span><span class="sxs-lookup"><span data-stu-id="d001a-130">EXAMPLES</span></span>

### <span data-ttu-id="d001a-131">例 1: 現在のセッションで作成されたセッションを取得する</span><span class="sxs-lookup"><span data-stu-id="d001a-131">Example 1: Get sessions created in the current session</span></span>

```powershell
Get-PSSession
```

<span data-ttu-id="d001a-132">このコマンド **は、現在** のセッションで作成されたすべての pssession を取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-132">This command gets all of the **PSSessions** that were created in the current session.</span></span> <span data-ttu-id="d001a-133">このコンピューターに接続している場合でも、他のセッションまたは他のコンピューターで作成さ **れた pssession は取得さ** れません。</span><span class="sxs-lookup"><span data-stu-id="d001a-133">It does not get **PSSessions** that were created in other sessions or on other computers, even if they connect to this computer.</span></span>

### <span data-ttu-id="d001a-134">例 2: ローカルコンピューターに接続されているセッションを取得する</span><span class="sxs-lookup"><span data-stu-id="d001a-134">Example 2: Get sessions connected to the local computer</span></span>

```powershell
Get-PSSession -ComputerName "localhost"
```

<span data-ttu-id="d001a-135">このコマンド **は、ローカル** コンピューターに接続されている pssession を取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-135">This command gets the **PSSessions** that are connected to the local computer.</span></span> <span data-ttu-id="d001a-136">ローカルコンピューターを指定するには、コンピューター名、localhost、またはドット (.) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d001a-136">To indicate the local computer, type the computer name, localhost, or a dot (.)</span></span>

<span data-ttu-id="d001a-137">このコマンドは、別のセッションまたは別のコンピューターで作成された場合でも、ローカル コンピューター上のセッションをすべて返します。</span><span class="sxs-lookup"><span data-stu-id="d001a-137">The command returns all of the sessions on the local computer, even if they were created in different sessions or on different computers.</span></span>

### <span data-ttu-id="d001a-138">例 3: コンピューターに接続されているセッションを取得する</span><span class="sxs-lookup"><span data-stu-id="d001a-138">Example 3: Get sessions connected to a computer</span></span>

```powershell
Get-PSSession -ComputerName "Server02"
```

```Output
 Id Name            ComputerName    State         ConfigurationName     Availability
 -- ----            ------------    -----         -----------------     ------------
  2 Session3        Server02       Disconnected  ITTasks                       Busy
  1 ScheduledJobs   Server02       Opened        Microsoft.PowerShell     Available
  3 Test            Server02       Disconnected  Microsoft.PowerShell          Busy
```

<span data-ttu-id="d001a-139">このコマンドは、Server02 コンピューターに接続され **ている pssession** を取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-139">This command gets the **PSSessions** that are connected to the Server02 computer.</span></span>

<span data-ttu-id="d001a-140">このコマンドは、別のセッションまたは別のコンピューターで作成された場合でも、Server02 上のセッションをすべて返します。</span><span class="sxs-lookup"><span data-stu-id="d001a-140">The command returns all of the sessions on Server02, even if they were created in different sessions or on different computers.</span></span>

<span data-ttu-id="d001a-141">出力は、状態が Disconnected で可用性が Busy のセッションが 2 つあることを示しています。</span><span class="sxs-lookup"><span data-stu-id="d001a-141">The output shows that two of the sessions have a Disconnected state and a Busy availability.</span></span> <span data-ttu-id="d001a-142">これらのセッション別のセッションで作成されており、現在使用されています。</span><span class="sxs-lookup"><span data-stu-id="d001a-142">They were created in different sessions and are currently in use.</span></span> <span data-ttu-id="d001a-143">開かれている ScheduledJobs セッションは、現在のセッションで作成されています。</span><span class="sxs-lookup"><span data-stu-id="d001a-143">The ScheduledJobs session, which is Opened and Available, was created in the current session.</span></span>

### <span data-ttu-id="d001a-144">例 4: このコマンドの結果を保存する</span><span class="sxs-lookup"><span data-stu-id="d001a-144">Example 4: Save results of this command</span></span>

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
$s1, $s2, $s3 = Get-PSSession
```

<span data-ttu-id="d001a-145">この例では、コマンドの結果を複数の変数に保存する方法を示し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-145">This example shows how to save the results of a `Get-PSSession` command in multiple variables.</span></span>

<span data-ttu-id="d001a-146">最初のコマンドは、 `New-PSSession` コマンドレットを使用 **して、** 3 台のリモートコンピューター上に pssession を作成します。</span><span class="sxs-lookup"><span data-stu-id="d001a-146">The first command uses the `New-PSSession` cmdlet to create **PSSessions** on three remote computers.</span></span>

<span data-ttu-id="d001a-147">2番目のコマンドは、コマンドレットを使用し `Get-PSSession` て、3つの pssession を取得 **し** ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-147">The second command uses a `Get-PSSession` cmdlet to get the three **PSSessions**.</span></span> <span data-ttu-id="d001a-148">次に、それぞれの **Pssessions** を別々の変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="d001a-148">It then saves each of the **PSSessions** in a separate variable.</span></span>

<span data-ttu-id="d001a-149">PowerShell がオブジェクトの配列を変数の配列に割り当てると、最初のオブジェクトが最初の変数に割り当てられ、2番目のオブジェクトが2番目の変数に代入されます。</span><span class="sxs-lookup"><span data-stu-id="d001a-149">When PowerShell assigns an array of objects to an array of variables, it assigns the first object to the first variable, the second object to the second variable, and so on.</span></span> <span data-ttu-id="d001a-150">オブジェクトの数が変数の数よりも多い場合、残りのオブジェクトはすべて配列の最後の変数に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d001a-150">If there are more objects than variables, it assigns all remaining objects to the last variable in the array.</span></span> <span data-ttu-id="d001a-151">変数の数がオブジェクトの数よりも多い場合、余分な変数は使用されません。</span><span class="sxs-lookup"><span data-stu-id="d001a-151">If there are more variables than objects, the extra variables are not used.</span></span>

### <span data-ttu-id="d001a-152">例 5: インスタンス ID を使用してセッションを削除する</span><span class="sxs-lookup"><span data-stu-id="d001a-152">Example 5: Delete a session by using an instance ID</span></span>

```powershell
Get-PSSession | Format-Table -Property ComputerName, InstanceID
$s = Get-PSSession -InstanceID a786be29-a6bb-40da-80fb-782c67f7db0f
Remove-PSSession -Session $s
```

<span data-ttu-id="d001a-153">この例では、インスタンス ID を使用して **pssession** を取得し、 **pssession** を削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d001a-153">This example shows how to get a **PSSession** by using its instance ID, and then to delete the **PSSession**.</span></span>

<span data-ttu-id="d001a-154">最初のコマンドは、現在のセッションで作成さ **れたすべて** の pssession を取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-154">The first command gets all of the **PSSessions** that were created in the current session.</span></span> <span data-ttu-id="d001a-155">**Pssessions** を Format-Table コマンドレットに送信します。これにより、各 **PSSession** の **ComputerName** および **InstanceID** プロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d001a-155">It sends the **PSSessions** to the Format-Table cmdlet, which displays the **ComputerName** and **InstanceID** properties of each **PSSession**.</span></span>

<span data-ttu-id="d001a-156">2番目のコマンドは、コマンドレットを使用して `Get-PSSession` 特定の **PSSession** を取得し、変数に保存し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-156">The second command uses the `Get-PSSession` cmdlet to get a particular **PSSession** and to save it in the `$s` variable.</span></span> <span data-ttu-id="d001a-157">このコマンドは、 **InstanceID** パラメーターを使用して **PSSession** を識別します。</span><span class="sxs-lookup"><span data-stu-id="d001a-157">The command uses the **InstanceID** parameter to identify the **PSSession**.</span></span>

<span data-ttu-id="d001a-158">3番目のコマンドは、Remove-PSSession コマンドレットを使用して、変数内の **PSSession** を削除し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-158">The third command uses the Remove-PSSession cmdlet to delete the **PSSession** in the `$s` variable.</span></span>

### <span data-ttu-id="d001a-159">例 6: 特定の名前を持つセッションを取得する</span><span class="sxs-lookup"><span data-stu-id="d001a-159">Example 6: Get a session that has a particular name</span></span>

<span data-ttu-id="d001a-160">この例のコマンドは、特定の名前形式に準拠し、特定のセッション構成を使用するセッションを探して接続します。</span><span class="sxs-lookup"><span data-stu-id="d001a-160">The commands in this example find a session that has a particular name format and uses a particular session configuration and then connect to the session.</span></span> <span data-ttu-id="d001a-161">このようなコマンドを使用すれば、同僚が開始したタスクのセッションを探して接続し、そのタスクを完了することができます。</span><span class="sxs-lookup"><span data-stu-id="d001a-161">You can use a command like this one to find a session in which a colleague started a task and connect to finish the task.</span></span>

```powershell
Get-PSSession -ComputerName Server02, Server12 -Name BackupJob* -ConfigurationName ITTasks -SessionOption @{OperationTimeout=240000}
```

```Output
 Id Name            ComputerName    State         ConfigurationName     Availability
 -- ----            ------------    -----         -----------------     ------------
  3 BackupJob04     Server02        Disconnected        ITTasks                  None
```

```powershell
$s = Get-PSSession -ComputerName Server02 -Name BackupJob04 -ConfigurationName ITTasks | Connect-PSSession
$s
```

```Output
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 5 BackupJob04     Server02        Opened        ITTasks                  Available
```

<span data-ttu-id="d001a-162">最初のコマンドは、Server02 および Server12 リモートコンピューター上のセッションを取得します。名前は BackupJob で始まり、ITTasks セッション構成を使用します。このコマンドは、 **name** パラメーターを使用して名前のパターンを指定し、 **ConfigurationName** パラメーターを使用してセッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="d001a-162">The first command gets sessions on the Server02 and Server12 remote computers that have names that begin with BackupJob and use the ITTasks session configuration.The command uses the **Name** parameter to specify the name pattern and the **ConfigurationName** parameter to specify the session configuration.</span></span> <span data-ttu-id="d001a-163">**SessionOption** パラメーターの値は、 **OperationTimeout** の値を 240,000 ミリ秒 (4 分) に設定するハッシュ テーブルです。</span><span class="sxs-lookup"><span data-stu-id="d001a-163">The value of the **SessionOption** parameter is a hash table that sets the value of the **OperationTimeout** to 240000 milliseconds (4 minutes).</span></span> <span data-ttu-id="d001a-164">この設定により、コマンドの完了に時間がかかるようになります。 **ConfigurationName** オプションと **sessionoption** パラメーターを使用して、 `Get-PSSession` 各コンピューターでコマンドレットが実行される一時的なセッションを構成します。出力は、コマンドが BackupJob04 セッションを返すことを示しています。</span><span class="sxs-lookup"><span data-stu-id="d001a-164">This setting gives the command more time to complete.The **ConfigurationName** and **SessionOption** parameters are used to configure the temporary sessions in which the `Get-PSSession` cmdlet runs on each computer.The output shows that the command returns the BackupJob04 session.</span></span> <span data-ttu-id="d001a-165">セッションは切断されており、 **可用性** は None であり、使用されていないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="d001a-165">The session is disconnected and the **Availability** is None, which indicates that it is not in use.</span></span>

<span data-ttu-id="d001a-166">2番目のコマンドは、コマンドレットを使用して `Get-PSSession` BackupJob04 セッションにアクセスし、Connect-PSSession コマンドレットを使用してセッションに接続します。</span><span class="sxs-lookup"><span data-stu-id="d001a-166">The second command uses the `Get-PSSession` cmdlet to get to the BackupJob04 session and the Connect-PSSession cmdlet to connect to the session.</span></span> <span data-ttu-id="d001a-167">このコマンドは、セッションを $s 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="d001a-167">The command saves the session in the $s variable.</span></span>

<span data-ttu-id="d001a-168">3 番目のコマンドは、$s 変数に保存されているセッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-168">The third command gets the session in the $s variable.</span></span> <span data-ttu-id="d001a-169">出力は、コマンドが成功したことを示して `Connect-PSSession` います。</span><span class="sxs-lookup"><span data-stu-id="d001a-169">The output shows that the `Connect-PSSession` command was successful.</span></span> <span data-ttu-id="d001a-170">このセッションは、 **Opened** 状態にあり、使用可能です。</span><span class="sxs-lookup"><span data-stu-id="d001a-170">The session is in the **Opened** state and is available for use.</span></span>

### <span data-ttu-id="d001a-171">例 7: ID を使用してセッションを取得する</span><span class="sxs-lookup"><span data-stu-id="d001a-171">Example 7: Get a session by using its ID</span></span>

```powershell
Get-PSSession -Id 2
```

<span data-ttu-id="d001a-172">このコマンドは、ID が2の **PSSession** を取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-172">This command gets the **PSSession** with ID 2.</span></span> <span data-ttu-id="d001a-173">**Id** プロパティの値は現在のセッションでのみ一意であるため、 **id** パラメーターはローカルコマンドに対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="d001a-173">Because the value of the **ID** property is unique only in the current session, the **Id** parameter is valid only for local commands.</span></span>

## <span data-ttu-id="d001a-174">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d001a-174">PARAMETERS</span></span>

### <span data-ttu-id="d001a-175">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="d001a-175">-AllowRedirection</span></span>

<span data-ttu-id="d001a-176">このコマンドレットがこの接続を代替 Uniform Resource Identifier (URI) にリダイレクトできることを示します。</span><span class="sxs-lookup"><span data-stu-id="d001a-176">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="d001a-177">既定では、PowerShell は接続をリダイレクトしません。</span><span class="sxs-lookup"><span data-stu-id="d001a-177">By default, PowerShell does not redirect connections.</span></span>

<span data-ttu-id="d001a-178">このパラメーター `Get-PSSession` は、 **connectionuri** パラメーターを使用してコマンドを実行するために作成される一時的な接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="d001a-178">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ConnectionUri** parameter.</span></span>

<span data-ttu-id="d001a-179">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d001a-179">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUri, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-180">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="d001a-180">-ApplicationName</span></span>

<span data-ttu-id="d001a-181">アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d001a-181">Specifies the name of an application.</span></span> <span data-ttu-id="d001a-182">このコマンドレットは、指定されたアプリケーションを使用するセッションにのみ接続します。</span><span class="sxs-lookup"><span data-stu-id="d001a-182">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="d001a-183">接続 URI のアプリケーション名セグメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="d001a-183">Enter the application name segment of the connection URI.</span></span> <span data-ttu-id="d001a-184">たとえば、次の接続 URI では、アプリケーション名は WSMan: `http://localhost:5985/WSMAN` です。</span><span class="sxs-lookup"><span data-stu-id="d001a-184">For example, in the following connection URI, the application name is WSMan: `http://localhost:5985/WSMAN`.</span></span> <span data-ttu-id="d001a-185">セッションのアプリケーション名は、セッションの **Runspace.ConnectionInfo.AppName** プロパティに保存されています。</span><span class="sxs-lookup"><span data-stu-id="d001a-185">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="d001a-186">このパラメーター値は、セッションを選択してフィルター処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d001a-186">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="d001a-187">セッションが使用するアプリケーションが変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d001a-187">It does not change the application that the session uses.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-188">-認証</span><span class="sxs-lookup"><span data-stu-id="d001a-188">-Authentication</span></span>

<span data-ttu-id="d001a-189">コマンドを実行するセッションの資格情報の認証に使用されるメカニズムを指定し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-189">Specifies the mechanism that is used to authenticate credentials for the session in which the `Get-PSSession` command runs.</span></span>

<span data-ttu-id="d001a-190">このパラメーターは、 `Get-PSSession` **ComputerName** パラメーターまたは **connectionuri** パラメーターを使用してコマンドを実行するために作成される一時的な接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="d001a-190">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="d001a-191">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d001a-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d001a-192">Default</span><span class="sxs-lookup"><span data-stu-id="d001a-192">Default</span></span>
- <span data-ttu-id="d001a-193">Basic</span><span class="sxs-lookup"><span data-stu-id="d001a-193">Basic</span></span>
- <span data-ttu-id="d001a-194">Credssp</span><span class="sxs-lookup"><span data-stu-id="d001a-194">Credssp</span></span>
- <span data-ttu-id="d001a-195">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="d001a-195">Digest</span></span>
- <span data-ttu-id="d001a-196">Kerberos</span><span class="sxs-lookup"><span data-stu-id="d001a-196">Kerberos</span></span>
- <span data-ttu-id="d001a-197">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="d001a-197">Negotiate</span></span>
- <span data-ttu-id="d001a-198">NegotiateWithImplicitCredential.</span><span class="sxs-lookup"><span data-stu-id="d001a-198">NegotiateWithImplicitCredential.</span></span>

<span data-ttu-id="d001a-199">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="d001a-199">The default value is Default.</span></span>

<span data-ttu-id="d001a-200">このパラメーターの値の詳細については、MSDN ライブラリの「 [Authenticationmechanism 列挙型](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d001a-200">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in the MSDN library.</span></span>

<span data-ttu-id="d001a-201">注意: ユーザーの資格情報が認証対象のリモートコンピューターに渡される Credential Security Support Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="d001a-201">CAUTION: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="d001a-202">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="d001a-202">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="d001a-203">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d001a-203">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="d001a-204">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d001a-204">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUri, ConnectionUriInstanceId
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-205">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="d001a-205">-CertificateThumbprint</span></span>

<span data-ttu-id="d001a-206">コマンドを実行するセッションを作成するアクセス許可を持つユーザーアカウントのデジタル公開キー証明書 (X509) を指定し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-206">Specifies the digital public key certificate (X509) of a user account that has permission to create the session in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="d001a-207">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="d001a-207">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="d001a-208">このパラメーターは、 `Get-PSSession` **ComputerName** パラメーターまたは **connectionuri** パラメーターを使用してコマンドを実行するために作成される一時的な接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="d001a-208">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="d001a-209">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="d001a-209">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="d001a-210">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="d001a-210">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="d001a-211">証明書の拇印を取得するには、PowerShell Cert: ドライブで Get-Item または Get-ChildItem コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d001a-211">To get a certificate thumbprint, use a Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

<span data-ttu-id="d001a-212">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d001a-212">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUri, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-213">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d001a-213">-ComputerName</span></span>

<span data-ttu-id="d001a-214">コンピューターの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="d001a-214">Specifies an array of names of computers.</span></span> <span data-ttu-id="d001a-215">指定されたコンピューターに接続しているセッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-215">Gets the sessions that connect to the specified computers.</span></span>
<span data-ttu-id="d001a-216">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="d001a-216">Wildcard characters are not permitted.</span></span> <span data-ttu-id="d001a-217">既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="d001a-217">There is no default value.</span></span>

<span data-ttu-id="d001a-218">Windows PowerShell 3.0 以降では、 **PSSession** オブジェクトは、各接続のリモート側のコンピューターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d001a-218">Beginning in Windows PowerShell 3.0, **PSSession** objects are stored on the computers at the remote end of each connection.</span></span> <span data-ttu-id="d001a-219">指定されたコンピューター上のセッションを取得するために、PowerShell は各コンピューターへの一時的な接続を作成し、コマンドを実行し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-219">To get the sessions on the specified computers, PowerShell creates a temporary connection to each computer and runs a `Get-PSSession` command.</span></span>

<span data-ttu-id="d001a-220">1 台以上のコンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d001a-220">Type the NetBIOS name, an IP address, or a fully-qualified domain name of one or more computers.</span></span> <span data-ttu-id="d001a-221">ローカルコンピューターを指定するには、コンピューター名、localhost、またはドット (.) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d001a-221">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span>

<span data-ttu-id="d001a-222">注: このパラメーターは、Windows PowerShell 3.0 以降のバージョンの PowerShell を実行しているコンピューターからのみセッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-222">Note: This parameter gets sessions only from computers that run Windows PowerShell 3.0 or later versions of PowerShell.</span></span> <span data-ttu-id="d001a-223">それ以前のバージョンではセッションが保存されません。</span><span class="sxs-lookup"><span data-stu-id="d001a-223">Earlier versions do not store sessions.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerInstanceId, ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-224">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="d001a-224">-ConfigurationName</span></span>

<span data-ttu-id="d001a-225">構成の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d001a-225">Specifies the name of a configuration.</span></span> <span data-ttu-id="d001a-226">このコマンドレットは、指定されたセッション構成を使用するセッションのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-226">This cmdlet gets only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="d001a-227">セッション構成の構成名または完全修飾リソース URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="d001a-227">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="d001a-228">構成名だけを指定した場合は、次のスキーマ URI が付加され `http://schemas.microsoft.com/powershell` ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-228">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span> <span data-ttu-id="d001a-229">セッションの構成名は、セッションの **ConfigurationName** プロパティに保存されています。</span><span class="sxs-lookup"><span data-stu-id="d001a-229">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="d001a-230">このパラメーター値は、セッションを選択してフィルター処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d001a-230">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="d001a-231">セッションが使用するセッション構成が変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d001a-231">It does not change the session configuration that the session uses.</span></span>

<span data-ttu-id="d001a-232">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d001a-232">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUri, ConnectionUriInstanceId, ContainerId, ContainerIdInstanceId, VMId, VMIdInstanceId, VMName, VMNameInstanceId
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-233">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="d001a-233">-ConnectionUri</span></span>

<span data-ttu-id="d001a-234">コマンドが実行される一時的なセッションの接続エンドポイントを定義する URI を指定し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-234">Specifies a URI that defines the connection endpoint for the temporary session in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="d001a-235">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d001a-235">The URI must be fully qualified.</span></span>

<span data-ttu-id="d001a-236">このパラメーター `Get-PSSession` は、 **connectionuri** パラメーターを使用してコマンドを実行するために作成される一時的な接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="d001a-236">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ConnectionUri** parameter.</span></span>

<span data-ttu-id="d001a-237">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d001a-237">The format of this string is:</span></span>

`<Transport>://<ComputerName>:<Port\>/<ApplicationName>`

<span data-ttu-id="d001a-238">既定値は `http://localhost:5985/WSMAN` です。</span><span class="sxs-lookup"><span data-stu-id="d001a-238">The default value is: `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="d001a-239">**Connectionuri** を指定しない場合は、 **UseSSL** 、 **ComputerName** 、 **Port** 、および **ApplicationName** パラメーターを使用して、 **connectionuri** 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d001a-239">If you do not specify a **ConnectionUri** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span> <span data-ttu-id="d001a-240">URI のトランスポート セグメントの有効な値は、HTTP および HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="d001a-240">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="d001a-241">トランスポートセグメントを使用して接続 URI を指定し、ポートを指定しない場合、セッションは標準ポート80で HTTP 用および 443 (HTTPS 用) で作成されます。</span><span class="sxs-lookup"><span data-stu-id="d001a-241">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="d001a-242">PowerShell リモート処理に既定のポートを使用するには、HTTP の場合はポート5985、HTTPS の場合は5986を指定します。</span><span class="sxs-lookup"><span data-stu-id="d001a-242">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="d001a-243">対象のコンピューターが接続を別の URI にリダイレクトする場合、コマンドで **Allowredirection** パラメーターを使用しない限り、PowerShell によってリダイレクトが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="d001a-243">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

<span data-ttu-id="d001a-244">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d001a-244">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d001a-245">このパラメーターは、Windows powershell 3.0 以降のバージョンの Windows PowerShell を実行しているコンピューターからのみセッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-245">This parameter gets sessions only from computers that run Windows PowerShell 3.0 or later versions of Windows PowerShell.</span></span> <span data-ttu-id="d001a-246">それ以前のバージョンではセッションが保存されません。</span><span class="sxs-lookup"><span data-stu-id="d001a-246">Earlier versions do not store sessions.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUri, ConnectionUriInstanceId
Aliases: URI, CU

Required: True
Position: 0
Default value: Http://localhost:5985/WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-247">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="d001a-247">-ContainerId</span></span>

<span data-ttu-id="d001a-248">コンテナーの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="d001a-248">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="d001a-249">このコマンドレットは、指定された各コンテナーとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="d001a-249">This cmdlet starts an interactive session with each of the specified containers.</span></span> <span data-ttu-id="d001a-250">`docker ps`コンテナー id の一覧を取得するには、コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d001a-250">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="d001a-251">詳細については、 [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) コマンドのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d001a-251">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId, ContainerIdInstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-252">-Credential</span><span class="sxs-lookup"><span data-stu-id="d001a-252">-Credential</span></span>

<span data-ttu-id="d001a-253">ユーザー資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="d001a-253">Specifies a user credential.</span></span> <span data-ttu-id="d001a-254">このコマンドレットは、指定したユーザーのアクセス許可を使用してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d001a-254">This cmdlet runs the command with the permissions of the specified user.</span></span> <span data-ttu-id="d001a-255">リモートコンピューターに接続してコマンドを実行するアクセス許可を持つユーザーアカウントを指定し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-255">Specify a user account that has permission to connect to the remote computer and run a `Get-PSSession` command.</span></span> <span data-ttu-id="d001a-256">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="d001a-256">The default is the current user.</span></span>

<span data-ttu-id="d001a-257">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-257">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="d001a-258">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="d001a-258">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="d001a-259">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="d001a-259">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="d001a-260">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d001a-260">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

<span data-ttu-id="d001a-261">このパラメーターは、 `Get-PSSession` **ComputerName** パラメーターまたは **connectionuri** パラメーターを使用してコマンドを実行するために作成される一時的な接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="d001a-261">This parameter configures to the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="d001a-262">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d001a-262">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUri, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-263">-Id</span><span class="sxs-lookup"><span data-stu-id="d001a-263">-Id</span></span>

<span data-ttu-id="d001a-264">セッション Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="d001a-264">Specifies an array of session IDs.</span></span> <span data-ttu-id="d001a-265">このコマンドレットは、指定された Id を持つセッションのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-265">This cmdlet gets only the sessions with the specified IDs.</span></span> <span data-ttu-id="d001a-266">1つ以上の Id をコンマで区切って入力するか、範囲演算子 (..) を使用して Id の範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="d001a-266">Type one or more IDs, separated by commas, or use the range operator (..) to specify a range of IDs.</span></span> <span data-ttu-id="d001a-267">ID パラメーターを **ComputerName** パラメーターと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d001a-267">You cannot use the ID parameter together with the **ComputerName** parameter.</span></span>

<span data-ttu-id="d001a-268">ID は、現在のセッションでユーザーが管理するセッションを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="d001a-268">An ID is an integer that uniquely identifies the user-managed sessions in the current session.</span></span> <span data-ttu-id="d001a-269">これは **InstanceId** よりも覚えやすく、入力も簡単ですが、現在のセッション内でのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="d001a-269">It is easier to remember and type than the **InstanceId** , but it is unique only within the current session.</span></span> <span data-ttu-id="d001a-270">セッションの ID は、セッションの ID プロパティに保存されています。</span><span class="sxs-lookup"><span data-stu-id="d001a-270">The ID of a session is stored in the ID property of the session.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-271">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="d001a-271">-InstanceId</span></span>

<span data-ttu-id="d001a-272">セッションのインスタンス Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="d001a-272">Specifies an array of instance IDs of sessions.</span></span> <span data-ttu-id="d001a-273">このコマンドレットは、指定されたインスタンス Id を持つセッションのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-273">This cmdlet gets only the sessions with the specified instance IDs.</span></span>

<span data-ttu-id="d001a-274">インスタンス ID は、ローカル コンピューターまたはリモート コンピューターのセッションを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="d001a-274">The instance ID is a GUID that uniquely identifies a session on a local or remote computer.</span></span> <span data-ttu-id="d001a-275">**インスタンス** id は、PowerShell で複数のセッションが実行されている場合でも一意です。</span><span class="sxs-lookup"><span data-stu-id="d001a-275">The **InstanceID** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="d001a-276">セッションのインスタンス ID は、セッションの **InstanceID** プロパティに保存されています。</span><span class="sxs-lookup"><span data-stu-id="d001a-276">The instance ID of a session is stored in the **InstanceID** property of the session.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: ComputerInstanceId, ConnectionUriInstanceId, ContainerIdInstanceId, VMIdInstanceId, VMNameInstanceId, InstanceId
Aliases:

Required: True (ComputerInstanceId, ConnectionUriInstanceId, ContainerIdInstanceId, VMIdInstanceId, VMNameInstanceId), False (InstanceId)
Position: Named
Default value: All sessions
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-277">-Name</span><span class="sxs-lookup"><span data-stu-id="d001a-277">-Name</span></span>

<span data-ttu-id="d001a-278">セッション名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="d001a-278">Specifies an array of session names.</span></span> <span data-ttu-id="d001a-279">このコマンドレットは、指定されたフレンドリ名を持つセッションのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-279">This cmdlet gets only the sessions that have the specified friendly names.</span></span> <span data-ttu-id="d001a-280">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d001a-280">Wildcard characters are permitted.</span></span>

<span data-ttu-id="d001a-281">セッションのフレンドリ名は、セッションの **Name** プロパティに保存されています。</span><span class="sxs-lookup"><span data-stu-id="d001a-281">The friendly name of a session is stored in the **Name** property of the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri, ContainerId, VMId, VMName
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="d001a-282">-Port</span><span class="sxs-lookup"><span data-stu-id="d001a-282">-Port</span></span>

<span data-ttu-id="d001a-283">コマンドを実行する一時的な接続に使用される、指定されたネットワークポートを指定し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-283">Specifies the specified network port that is used for the temporary connection in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="d001a-284">リモート コンピューターに接続するには、リモート コンピューターで、接続に使用されるポートをリッスンすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="d001a-284">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="d001a-285">既定のポートは5985で、これは HTTP 用の WinRM ポート、および HTTPS 用の WinRM ポートである5986です。</span><span class="sxs-lookup"><span data-stu-id="d001a-285">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="d001a-286">代替ポートを使用する前に、そのポートでリッスンするようにリモート コンピューター上の WinRM リスナーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d001a-286">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="d001a-287">リスナーを構成するには、PowerShell プロンプトで次の2つのコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="d001a-287">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="d001a-288">このパラメーターは、 `Get-PSSession` **ComputerName** パラメーターまたは **connectionuri** パラメーターを使用してコマンドを実行するために作成される一時的な接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="d001a-288">This parameter configures to the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="d001a-289">必要な場合を除き、 **Port** パラメーターを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="d001a-289">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="d001a-290">コマンドで設定された **ポート** は、コマンドを実行するすべてのコンピューターまたはセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d001a-290">The **Port** set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="d001a-291">代替ポートの設定によっては、コマンドがすべてのコンピューターで実行されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d001a-291">An alternate port setting might prevent the command from running on all computers.</span></span>

<span data-ttu-id="d001a-292">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d001a-292">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: 5985, 5986
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-293">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="d001a-293">-SessionOption</span></span>

<span data-ttu-id="d001a-294">セッションの詳細オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d001a-294">Specifies advanced options for the session.</span></span> <span data-ttu-id="d001a-295">New-PSSessionOption コマンドレットを使用して作成する **sessionoption** オブジェクト、またはキーがセッションオプションの名前で、値がセッションオプションの値であるハッシュテーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="d001a-295">Enter a **SessionOption** object, such as one that you create by using the New-PSSessionOption cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="d001a-296">オプションの既定値は、$PSSessionOption ユーザー設定変数が設定されている場合は、その値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="d001a-296">The default values for the options are determined by the value of the $PSSessionOption preference variable, if it is set.</span></span> <span data-ttu-id="d001a-297">それ以外の場合、既定値はセッション構成で設定されたオプションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="d001a-297">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="d001a-298">セッション オプションの値は、$PSSessionOption ユーザー設定変数およびセッション構成で設定されたセッションの既定値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="d001a-298">The session option values take precedence over default values for sessions set in the $PSSessionOption preference variable and in the session configuration.</span></span> <span data-ttu-id="d001a-299">ただし、セッション構成で設定された最大値、クォータ、または制限よりも優先されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d001a-299">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="d001a-300">既定値を含む、セッションオプションの説明については、「」を参照してください `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="d001a-300">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="d001a-301">ユーザー設定変数の詳細については `$PSSessionOption` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d001a-301">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="d001a-302">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d001a-302">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUri, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-303">-状態</span><span class="sxs-lookup"><span data-stu-id="d001a-303">-State</span></span>

<span data-ttu-id="d001a-304">セッション状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="d001a-304">Specifies a session state.</span></span> <span data-ttu-id="d001a-305">このコマンドレットは、指定された状態のセッションのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-305">This cmdlet gets only sessions in the specified state.</span></span> <span data-ttu-id="d001a-306">このパラメーターに指定できる値は、All、Opened、Disconnected、Closed、および壊れるです。</span><span class="sxs-lookup"><span data-stu-id="d001a-306">The acceptable values for this parameter are: All, Opened, Disconnected, Closed, and Broken.</span></span> <span data-ttu-id="d001a-307">既定値は All です。</span><span class="sxs-lookup"><span data-stu-id="d001a-307">The default value is All.</span></span>

<span data-ttu-id="d001a-308">セッション状態の値は、現在のセッションを基準にしています。</span><span class="sxs-lookup"><span data-stu-id="d001a-308">The session state value is relative to the current sessions.</span></span> <span data-ttu-id="d001a-309">現在のセッションで作成されておらず、現在のセッションに接続されていないセッションは、別のセッションに接続されている場合でも、状態は Disconnected になります。</span><span class="sxs-lookup"><span data-stu-id="d001a-309">Sessions that were not created in the current sessions and are not connected to the current session have a state of Disconnected even when they are connected to a different session.</span></span>

<span data-ttu-id="d001a-310">セッションの状態は、セッションの **State** プロパティに保存されています。</span><span class="sxs-lookup"><span data-stu-id="d001a-310">The state of a session is stored in the **State** property of the session.</span></span>

<span data-ttu-id="d001a-311">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d001a-311">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.SessionFilterState
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUri, ConnectionUriInstanceId, ContainerId, ContainerIdInstanceId, VMId, VMIdInstanceId, VMName, VMNameInstanceId
Aliases:
Accepted values: All, Opened, Disconnected, Closed, Broken

Required: False
Position: Named
Default value: All
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-312">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="d001a-312">-ThrottleLimit</span></span>

<span data-ttu-id="d001a-313">コマンドを実行するために確立できる同時接続の最大数を指定し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-313">Specifies the maximum number of concurrent connections that can be established to run the `Get-PSSession` command.</span></span> <span data-ttu-id="d001a-314">このパラメーターを省略した場合、または値 0 (ゼロ) を入力した場合は、既定値の 32 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d001a-314">If you omit this parameter or enter a value of 0 (zero), the default value, 32, is used.</span></span> <span data-ttu-id="d001a-315">スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="d001a-315">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

<span data-ttu-id="d001a-316">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d001a-316">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUri, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-317">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="d001a-317">-UseSSL</span></span>

<span data-ttu-id="d001a-318">このコマンドレットが Secure Sockets Layer (SSL) プロトコルを使用して、コマンドが実行される接続を確立することを示し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-318">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish the connection in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="d001a-319">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="d001a-319">By default, SSL is not used.</span></span> <span data-ttu-id="d001a-320">コマンドに使用するポートで SSL が使用できない場合に、このパラメーターを指定すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="d001a-320">If you use this parameter, but SSL is not available on the port used for the command, the command fails.</span></span>

<span data-ttu-id="d001a-321">このパラメーターは、ComputerName パラメーターを使用してコマンドを実行するために作成される一時的な接続を構成し `Get-PSSession` ます。 **ComputerName**</span><span class="sxs-lookup"><span data-stu-id="d001a-321">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** parameter.</span></span>

<span data-ttu-id="d001a-322">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d001a-322">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-323">-VMId</span><span class="sxs-lookup"><span data-stu-id="d001a-323">-VMId</span></span>

<span data-ttu-id="d001a-324">仮想マシンの ID の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="d001a-324">Specifies an array of ID of virtual machines.</span></span> <span data-ttu-id="d001a-325">このコマンドレットは、指定された各仮想マシンとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="d001a-325">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="d001a-326">使用可能な仮想マシンを表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d001a-326">To see the virtual machines that are available to you, use the following command:</span></span>

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId, VMIdInstanceId
Aliases: VMGuid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-327">-VMName</span><span class="sxs-lookup"><span data-stu-id="d001a-327">-VMName</span></span>

<span data-ttu-id="d001a-328">仮想マシンの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="d001a-328">Specifies an array of names of virtual machines.</span></span> <span data-ttu-id="d001a-329">このコマンドレットは、指定された各仮想マシンとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="d001a-329">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="d001a-330">使用可能な仮想マシンを表示するには、コマンドレットを使用し `Get-VM` ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-330">To see the virtual machines that are available to you, use the `Get-VM` cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName, VMNameInstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d001a-331">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d001a-331">CommonParameters</span></span>

<span data-ttu-id="d001a-332">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d001a-332">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d001a-333">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d001a-333">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d001a-334">入力</span><span class="sxs-lookup"><span data-stu-id="d001a-334">INPUTS</span></span>

### <span data-ttu-id="d001a-335">なし</span><span class="sxs-lookup"><span data-stu-id="d001a-335">None</span></span>

<span data-ttu-id="d001a-336">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="d001a-336">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="d001a-337">出力</span><span class="sxs-lookup"><span data-stu-id="d001a-337">OUTPUTS</span></span>

### <span data-ttu-id="d001a-338">システム管理. 実行空間</span><span class="sxs-lookup"><span data-stu-id="d001a-338">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="d001a-339">注</span><span class="sxs-lookup"><span data-stu-id="d001a-339">NOTES</span></span>

- <span data-ttu-id="d001a-340">このコマンドレットは、新しい PSSession **PSSession** 、 `Enter-PSSession` 、および Invoke-Command コマンドレットを使用して作成された、ユーザーが管理するセッション PSSession オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-340">This cmdlet gets user-managed sessions **PSSession** objects" such as those that are created by using the New-PSSession, `Enter-PSSession`, and Invoke-Command cmdlets.</span></span> <span data-ttu-id="d001a-341">PowerShell の起動時に作成されるシステム管理セッションは取得されません。</span><span class="sxs-lookup"><span data-stu-id="d001a-341">It does not get the system-managed session that is created when you start PowerShell.</span></span>
- <span data-ttu-id="d001a-342">Windows PowerShell 3.0 以降では、 **PSSession** オブジェクトは、接続のサーバー側または受信側のコンピューターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d001a-342">Starting in Windows PowerShell 3.0, **PSSession** objects are stored on the computer that is at the server-side or receiving end of a connection.</span></span> <span data-ttu-id="d001a-343">ローカルコンピューターまたはリモートコンピューターに格納されているセッションを取得するために、PowerShell は、指定されたコンピューターに一時的なセッションを確立し、セッションでクエリコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d001a-343">To get the sessions that are stored on the local computer or a remote computer, PowerShell establishes a temporary session to the specified computer and runs query commands in the session.</span></span>
- <span data-ttu-id="d001a-344">リモート コンピューターに接続しているセッションを取得するには、 **ComputerName** パラメーターまたは **ConnectionUri** パラメーターを使用してリモート コンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="d001a-344">To get sessions that connect to a remote computer, use the **ComputerName** or **ConnectionUri** parameters to specify the remote computer.</span></span> <span data-ttu-id="d001a-345">が取得するセッションをフィルター処理するには、 `Get-PSSession` **Name** 、 **ID** 、 **InstanceID** 、および **State** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d001a-345">To filter the sessions that `Get-PSSession` gets, use the **Name** , **ID** , **InstanceID** , and **State** parameters.</span></span> <span data-ttu-id="d001a-346">残りのパラメーターを使用して、で使用する一時的なセッションを構成し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="d001a-346">Use the remaining parameters to configure the temporary session that `Get-PSSession` uses.</span></span>
- <span data-ttu-id="d001a-347">**ComputerName** パラメーターまたは **connectionuri** パラメーターを使用すると、は、 `Get-PSSession` Windows powershell 3.0 以降のバージョンの powershell を実行しているコンピューターからのセッションのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="d001a-347">When you use the **ComputerName** or **ConnectionUri** parameters, `Get-PSSession` gets only sessions from computers running Windows PowerShell 3.0 and later versions of PowerShell.</span></span>
- <span data-ttu-id="d001a-348">**PSSession** の **State** プロパティの値は、現在のセッションを基準としています。</span><span class="sxs-lookup"><span data-stu-id="d001a-348">The value of the **State** property of a **PSSession** is relative to the current session.</span></span>
  <span data-ttu-id="d001a-349">したがって、値が **Disconnected** の場合は、 **PSSession** が現在のセッションに接続されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d001a-349">Therefore, a value of **Disconnected** means that the **PSSession** is not connected to the current session.</span></span> <span data-ttu-id="d001a-350">ただし、 **PSSession** がすべてのセッションから切断されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d001a-350">However, it does not mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="d001a-351">別のセッションに接続されている可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="d001a-351">It might be connected to a different session.</span></span> <span data-ttu-id="d001a-352">現在のセッションから **PSSession** に接続または再接続できるかどうかを判断するには、 **Availability** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="d001a-352">To determine whether you can connect or reconnect to the **PSSession** from the current session, use the **Availability** property.</span></span>

<span data-ttu-id="d001a-353">**Availability** の値が **None** の場合は、セッションに接続できることを示します。</span><span class="sxs-lookup"><span data-stu-id="d001a-353">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="d001a-354">値が **Busy** の場合は、PSSession が別のセッションに接続されているため、 **PSSession** に接続できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="d001a-354">A value of **Busy** indicates that you cannot connect to the **PSSession** because it is connected to another session.</span></span>

<span data-ttu-id="d001a-355">セッションの **State** プロパティの値の詳細については、「 [RunspaceState Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d001a-355">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate).</span></span>

<span data-ttu-id="d001a-356">セッションの **Availability** プロパティの値の詳細については、「 [RunspaceAvailability Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d001a-356">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="d001a-357">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d001a-357">RELATED LINKS</span></span>

[<span data-ttu-id="d001a-358">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="d001a-358">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="d001a-359">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="d001a-359">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="d001a-360">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="d001a-360">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="d001a-361">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="d001a-361">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="d001a-362">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="d001a-362">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="d001a-363">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="d001a-363">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="d001a-364">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="d001a-364">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="d001a-365">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="d001a-365">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="d001a-366">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="d001a-366">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="d001a-367">about_Remote</span><span class="sxs-lookup"><span data-stu-id="d001a-367">about_Remote</span></span>](About/about_Remote.md)
