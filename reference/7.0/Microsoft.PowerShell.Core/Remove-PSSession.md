---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSession
ms.openlocfilehash: aa6965b3a21c145ecccb284d43c6d0913bb31027
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209880"
---
# <span data-ttu-id="48ae6-103">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="48ae6-103">Remove-PSSession</span></span>

## <span data-ttu-id="48ae6-104">概要</span><span class="sxs-lookup"><span data-stu-id="48ae6-104">SYNOPSIS</span></span>
<span data-ttu-id="48ae6-105">1つ以上の PowerShell セッション (pssession) を閉じます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-105">Closes one or more PowerShell sessions (PSSessions).</span></span>

## <span data-ttu-id="48ae6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="48ae6-106">SYNTAX</span></span>

### <span data-ttu-id="48ae6-107">Id (既定値)</span><span class="sxs-lookup"><span data-stu-id="48ae6-107">Id (Default)</span></span>

```
Remove-PSSession [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="48ae6-108">Session</span><span class="sxs-lookup"><span data-stu-id="48ae6-108">Session</span></span>

```
Remove-PSSession [-Session] <PSSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="48ae6-109">ContainerId</span><span class="sxs-lookup"><span data-stu-id="48ae6-109">ContainerId</span></span>

```
Remove-PSSession -ContainerId <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="48ae6-110">VMId</span><span class="sxs-lookup"><span data-stu-id="48ae6-110">VMId</span></span>

```
Remove-PSSession -VMId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="48ae6-111">VMName</span><span class="sxs-lookup"><span data-stu-id="48ae6-111">VMName</span></span>

```
Remove-PSSession -VMName <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="48ae6-112">InstanceId</span><span class="sxs-lookup"><span data-stu-id="48ae6-112">InstanceId</span></span>

```
Remove-PSSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="48ae6-113">Name</span><span class="sxs-lookup"><span data-stu-id="48ae6-113">Name</span></span>

```
Remove-PSSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="48ae6-114">[ComputerName]</span><span class="sxs-lookup"><span data-stu-id="48ae6-114">ComputerName</span></span>

```
Remove-PSSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="48ae6-115">Description</span><span class="sxs-lookup"><span data-stu-id="48ae6-115">DESCRIPTION</span></span>

<span data-ttu-id="48ae6-116">削除コマンドレットは、現在のセッションの PowerShell **セッション (** **PSSession** ) を閉じます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-116">The **Remove-PSSession** cmdlet closes PowerShell sessions ( **PSSessions** ) in the current session.</span></span>
<span data-ttu-id="48ae6-117">このメソッドは、pssession で実行されている **すべてのコマンドを停止** し、 **pssession** を終了して、 **pssession** が使用していたリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-117">It stops any commands that are running in the **PSSessions** , ends the **PSSession** , and releases the resources that the **PSSession** was using.</span></span>
<span data-ttu-id="48ae6-118">**PSSession** がリモートコンピューターに接続されている場合は、このコマンドレットによって、ローカルコンピューターとリモートコンピューター間の接続も切断されます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-118">If the **PSSession** is connected to a remote computer, this cmdlet also closes the connection between the local and remote computers.</span></span>

<span data-ttu-id="48ae6-119">**PSSession** を削除するには、セッションの *名前* 、 *ComputerName* 、 *ID* 、または *InstanceID* を入力します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-119">To remove a **PSSession** , enter the *Name* , *ComputerName* , *ID* , or *InstanceID* of the session.</span></span>

<span data-ttu-id="48ae6-120">*Pssession* を変数に保存した場合、セッションオブジェクトは変数に残りますが、 *pssession* の状態は閉じられます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-120">If you have saved the *PSSession* in a variable, the session object remains in the variable, but the state of the *PSSession* is Closed.</span></span>

## <span data-ttu-id="48ae6-121">例</span><span class="sxs-lookup"><span data-stu-id="48ae6-121">EXAMPLES</span></span>

### <span data-ttu-id="48ae6-122">例 1: Id を使用してセッションを削除する</span><span class="sxs-lookup"><span data-stu-id="48ae6-122">Example 1: Remove sessions by using IDs</span></span>

```powershell
Remove-PSSession -Id 1, 2
```

<span data-ttu-id="48ae6-123">このコマンドは、Id が1および2の **pssession を削除** します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-123">This command removes the **PSSessions** that have IDs 1 and 2.</span></span>

### <span data-ttu-id="48ae6-124">例 2: 現在のセッションのすべてのセッションを削除する</span><span class="sxs-lookup"><span data-stu-id="48ae6-124">Example 2: Remove all the sessions in the current session</span></span>

```powershell
Get-PSSession | Remove-PSSession
Remove-PSSession -Session (Get-PSSession)
$s = Get-PSSession
Remove-PSSession -Session $s
```

<span data-ttu-id="48ae6-125">これらのコマンド **は、現在** のセッションのすべての pssession を削除します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-125">These commands remove all of the **PSSessions** in the current session.</span></span>
<span data-ttu-id="48ae6-126">これらの 3 つのコマンドの形式は異なっていますが、効果は同じです。</span><span class="sxs-lookup"><span data-stu-id="48ae6-126">Although the three command formats look different, they have the same effect.</span></span>

### <span data-ttu-id="48ae6-127">例 3: 名前を使用してセッションを閉じる</span><span class="sxs-lookup"><span data-stu-id="48ae6-127">Example 3: Close sessions by using names</span></span>

```powershell
$r = Get-PSSession -ComputerName Serv*
$r | Remove-PSSession
```

<span data-ttu-id="48ae6-128">これらのコマンドは **、名前** が Serv で始まるコンピューターに接続されている pssession を閉じます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-128">These commands close the **PSSessions** that are connected to computers that have names that begin with Serv.</span></span>

### <span data-ttu-id="48ae6-129">例 4: ポートに接続されているセッションを閉じる</span><span class="sxs-lookup"><span data-stu-id="48ae6-129">Example 4: Close sessions connected to a port</span></span>

```powershell
Get-PSSession | where {$_.port -eq 90} | Remove-PSSession
```

<span data-ttu-id="48ae6-130">このコマンドは、ポート90に接続され **ている pssession** を閉じます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-130">This command closes the **PSSessions** that are connected to port 90.</span></span>
<span data-ttu-id="48ae6-131">このコマンド形式を使用すると、 *ComputerName* 、 *Name* 、 *InstanceID* 、および *ID* 以外のプロパティで **pssessions** を識別できます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-131">You can use this command format to identify **PSSessions** by properties other than *ComputerName* , *Name* , *InstanceID* , and *ID* .</span></span>

### <span data-ttu-id="48ae6-132">例 5: インスタンス ID に基づいてセッションを閉じる</span><span class="sxs-lookup"><span data-stu-id="48ae6-132">Example 5: Close a session based on instance ID</span></span>

```powershell
Get-PSSession | Format-Table ComputerName, InstanceID  -AutoSize
```

```Output
ComputerName InstanceId
------------ ----------------
Server01     875d231b-2788-4f36-9f67-2e50d63bb82a
localhost    c065ffa0-02c4-406e-84a3-dacb0d677868
Server02     4699cdbc-61d5-4e0d-b916-84f82ebede1f
Server03     4e5a3245-4c63-43e4-88d0-a7798bfc2414
TX-TEST-01   fc4e9dfa-f246-452d-9fa3-1adbdd64ae85 PS C:\> Remove-PSSession -InstanceID fc4e9dfa-f246-452d-9fa3-1adbdd64ae85
```

<span data-ttu-id="48ae6-133">これらのコマンドは、インスタンス ID または **Remoterunspace ID** に基づいて **PSSession** を閉じる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="48ae6-133">These commands show how to close a **PSSession** based on its instance ID, or **RemoteRunspaceID** .</span></span>

<span data-ttu-id="48ae6-134">最初のコマンドは、 **Get PSSession** コマンドレットを使用して、現在の **セッションの** PSSession を取得します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-134">The first command uses the **Get-PSSession** cmdlet to get the **PSSessions** in the current session.</span></span>
<span data-ttu-id="48ae6-135">この例では、パイプライン演算子 (|) を使用して、pssession を Format-Table コマンド **レットに送信します** 。このコマンドレットは、テーブル内の **ComputerName** プロパティと **InstanceID** プロパティを書式設定します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-135">It uses a pipeline operator (|) to send the **PSSessions** to the Format-Table cmdlet, which formats their **ComputerName** and **InstanceID** properties in a table.</span></span>
<span data-ttu-id="48ae6-136">*AutoSize* パラメーターは、表示する列を圧縮します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-136">The *AutoSize* parameter compresses the columns for display.</span></span>

<span data-ttu-id="48ae6-137">結果の表示から、閉じる **pssession** を特定し、その **pssession** の *InstanceID* をコピーして2番目のコマンドに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-137">From the resulting display, you can identify the **PSSession** to be closed, and copy and paste the *InstanceID* of that **PSSession** into the second command.</span></span>

<span data-ttu-id="48ae6-138">2番目のコマンドは、 **削除 pssession** コマンドレットを使用して、指定されたインスタンス ID を持つ *pssession* を削除します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-138">The second command uses the **Remove-PSSession** cmdlet to remove the *PSSession* with the specified instance ID.</span></span>

### <span data-ttu-id="48ae6-139">例 6: 現在のセッションのすべてのセッションを削除する関数を作成する</span><span class="sxs-lookup"><span data-stu-id="48ae6-139">Example 6: Create a function that deletes all sessions in the current session</span></span>

```powershell
Function EndPSS { Get-PSSession | Remove-PSSession }
```

<span data-ttu-id="48ae6-140">この関数 **は、現在** のセッションのすべての pssession を削除します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-140">This function deletes all of the **PSSessions** in the current session.</span></span>
<span data-ttu-id="48ae6-141">この関数を PowerShell プロファイルに追加した後、すべてのセッションを削除するには、「」と入力 `EndPSS` します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-141">After you add this function to your PowerShell profile, to delete all sessions, type `EndPSS`.</span></span>

## <span data-ttu-id="48ae6-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="48ae6-142">PARAMETERS</span></span>

### <span data-ttu-id="48ae6-143">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="48ae6-143">-ComputerName</span></span>

<span data-ttu-id="48ae6-144">コンピューターの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-144">Specifies an array of names of computers.</span></span>
<span data-ttu-id="48ae6-145">このコマンドレットは、指定されたコンピューターに接続され **ている pssession** を閉じます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-145">This cmdlet closes the **PSSessions** that are connected to the specified computers.</span></span>
<span data-ttu-id="48ae6-146">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-146">Wildcard characters are permitted.</span></span>

<span data-ttu-id="48ae6-147">1 台または複数のリモート コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-147">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span>
<span data-ttu-id="48ae6-148">ローカルコンピューターを指定するには、コンピューター名、localhost、またはドット (.) を入力します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-148">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="48ae6-149">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="48ae6-149">-ContainerId</span></span>

<span data-ttu-id="48ae6-150">コンテナーの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-150">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="48ae6-151">このコマンドレットは、指定された各コンテナーのセッションを削除します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-151">This cmdlet removes sessions for each of the specified containers.</span></span> <span data-ttu-id="48ae6-152">`docker ps`コンテナー id の一覧を取得するには、コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-152">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="48ae6-153">詳細については、 [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) コマンドのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="48ae6-153">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="48ae6-154">-Id</span><span class="sxs-lookup"><span data-stu-id="48ae6-154">-Id</span></span>

<span data-ttu-id="48ae6-155">セッションの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-155">Specifies an array of IDs of sessions.</span></span>
<span data-ttu-id="48ae6-156">このコマンドレットは、指定された Id *を持つ pssession を閉じ* ます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-156">This cmdlet closes the *PSSessions* with the specified IDs.</span></span>
<span data-ttu-id="48ae6-157">1つ以上の Id をコンマで区切って入力するか、範囲演算子 (..) を使用して Id の範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-157">Type one or more IDs, separated by commas, or use the range operator (..) to specify a range of IDs.</span></span>

<span data-ttu-id="48ae6-158">ID は、現在のセッションの **PSSession** を一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="48ae6-158">An ID is an integer that uniquely identifies the **PSSession** in the current session.</span></span>
<span data-ttu-id="48ae6-159">これは *InstanceId* よりも覚えやすく、入力も簡単ですが、現在のセッションでのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="48ae6-159">It is easier to remember and type than the *InstanceId* , but it is unique only in the current session.</span></span>
<span data-ttu-id="48ae6-160">**PSSession** の ID を検索するには、パラメーターを指定せずに Get-PSSession コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-160">To find the ID of a **PSSession** , run the Get-PSSession cmdlet without parameters.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="48ae6-161">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="48ae6-161">-InstanceId</span></span>

<span data-ttu-id="48ae6-162">インスタンス Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-162">Specifies an array of instance IDs.</span></span>
<span data-ttu-id="48ae6-163">このコマンドレットは、指定されたインスタンス Id を持つ **pssession を閉じ** ます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-163">This cmdlet closes the **PSSessions** that have the specified instance IDs.</span></span>

<span data-ttu-id="48ae6-164">インスタンス ID は、現在のセッションの **PSSession** を一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="48ae6-164">The instance ID is a GUID that uniquely identifies a **PSSession** in the current session.</span></span>
<span data-ttu-id="48ae6-165">1台のコンピューターで複数のセッションが実行されている場合でも、インスタンス ID は一意です。</span><span class="sxs-lookup"><span data-stu-id="48ae6-165">The instance ID is unique, even when you have multiple sessions running on a single computer.</span></span>

<span data-ttu-id="48ae6-166">インスタンス ID は、 **PSSession** を表すオブジェクトの **InstanceID** プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-166">The instance ID is stored in the **InstanceID** property of the object that represents a **PSSession** .</span></span>
<span data-ttu-id="48ae6-167">現在 **のセッション** の Pssession の **InstanceID** を検索するには、「」と入力 `Get-PSSession | Format-Table Name, ComputerName, InstanceId` します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-167">To find the **InstanceID** of the **PSSessions** in the current session, type `Get-PSSession | Format-Table Name, ComputerName, InstanceId`.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="48ae6-168">-Name</span><span class="sxs-lookup"><span data-stu-id="48ae6-168">-Name</span></span>

<span data-ttu-id="48ae6-169">セッションのフレンドリ名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-169">Specifies an array of friendly names of sessions.</span></span>
<span data-ttu-id="48ae6-170">このコマンド **レットは、** 指定されたフレンドリ名を持つ pssession を閉じます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-170">This cmdlet closes the **PSSessions** that have the specified friendly names.</span></span>
<span data-ttu-id="48ae6-171">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-171">Wildcard characters are permitted.</span></span>

<span data-ttu-id="48ae6-172">**Pssession** のフレンドリ名は一意ではない可能性があるため、 *name* パラメーターを使用する場合は、 **Pssession の削除** コマンドで *WhatIf* または *Confirm* パラメーターも使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="48ae6-172">Because the friendly name of a **PSSession** might not be unique, when you use the *Name* parameter, consider also using the *WhatIf* or *Confirm* parameter in the **Remove-PSSession** command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="48ae6-173">-セッション</span><span class="sxs-lookup"><span data-stu-id="48ae6-173">-Session</span></span>

<span data-ttu-id="48ae6-174">閉じる **pssession のセッション** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-174">Specifies the session objects of the **PSSessions** to close.</span></span>
<span data-ttu-id="48ae6-175">**Pssessions** を含む変数、または PSSession **を作成** または取得するコマンドを入力します (New-PSSession や、 **PSSession** コマンドなど)。</span><span class="sxs-lookup"><span data-stu-id="48ae6-175">Enter a variable that contains the **PSSessions** or a command that creates or gets the **PSSessions** , such as a New-PSSession or **Get-PSSession** command.</span></span>
<span data-ttu-id="48ae6-176">パイプを使用して1つ以上のセッションオブジェクトを **削除** することもできます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-176">You can also pipe one or more session objects to **Remove-PSSession** .</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="48ae6-177">-VMId</span><span class="sxs-lookup"><span data-stu-id="48ae6-177">-VMId</span></span>

<span data-ttu-id="48ae6-178">仮想マシンの ID の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-178">Specifies an array of ID of virtual machines.</span></span>
<span data-ttu-id="48ae6-179">このコマンドレットは、指定された各仮想マシンとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-179">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span>
<span data-ttu-id="48ae6-180">使用可能な仮想マシンを表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-180">To see the virtual machines that are available to you, use the following command:</span></span>

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="48ae6-181">-VMName</span><span class="sxs-lookup"><span data-stu-id="48ae6-181">-VMName</span></span>

<span data-ttu-id="48ae6-182">仮想マシンの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-182">Specifies an array of names of virtual machines.</span></span>
<span data-ttu-id="48ae6-183">このコマンドレットは、指定された各仮想マシンとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-183">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span>
<span data-ttu-id="48ae6-184">使用可能な仮想マシンを表示するには、 **GET VM** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-184">To see the virtual machines that are available to you, use the **Get-VM** cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="48ae6-185">-Confirm</span><span class="sxs-lookup"><span data-stu-id="48ae6-185">-Confirm</span></span>

<span data-ttu-id="48ae6-186">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-186">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="48ae6-187">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="48ae6-187">-WhatIf</span></span>

<span data-ttu-id="48ae6-188">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-188">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="48ae6-189">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="48ae6-189">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="48ae6-190">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="48ae6-190">CommonParameters</span></span>

<span data-ttu-id="48ae6-191">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="48ae6-191">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="48ae6-192">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48ae6-192">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="48ae6-193">入力</span><span class="sxs-lookup"><span data-stu-id="48ae6-193">INPUTS</span></span>

### <span data-ttu-id="48ae6-194">システム管理. 実行空間</span><span class="sxs-lookup"><span data-stu-id="48ae6-194">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="48ae6-195">このコマンドレットには、セッションオブジェクトをパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-195">You can pipe a session object to this cmdlet.</span></span>

## <span data-ttu-id="48ae6-196">出力</span><span class="sxs-lookup"><span data-stu-id="48ae6-196">OUTPUTS</span></span>

### <span data-ttu-id="48ae6-197">なし</span><span class="sxs-lookup"><span data-stu-id="48ae6-197">None</span></span>

<span data-ttu-id="48ae6-198">このコマンドレットはオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="48ae6-198">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="48ae6-199">注</span><span class="sxs-lookup"><span data-stu-id="48ae6-199">NOTES</span></span>

* <span data-ttu-id="48ae6-200">*Id* パラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="48ae6-200">The *Id* parameter is mandatory.</span></span> <span data-ttu-id="48ae6-201">現在の **セッションのすべての pssession** を削除するには、「」と入力 `Get-PSSession | Remove-PSSession` します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-201">To delete all the **PSSessions** in the current session, type `Get-PSSession | Remove-PSSession`.</span></span>
* <span data-ttu-id="48ae6-202">**PSSession** は、リモートコンピューターへの永続的な接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-202">A **PSSession** uses a persistent connection to a remote computer.</span></span> <span data-ttu-id="48ae6-203">**PSSession** を作成して、データを共有する一連のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-203">Create a **PSSession** to run a series of commands that share data.</span></span> <span data-ttu-id="48ae6-204">詳細を表示するには「`Get-Help about_PSSessions`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="48ae6-204">For more information, type `Get-Help about_PSSessions`.</span></span>
* <span data-ttu-id="48ae6-205">**Pssessions** は、現在のセッションに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="48ae6-205">**PSSessions** are specific to the current session.</span></span> <span data-ttu-id="48ae6-206">セッションを終了すると、そのセッションで作成 **した pssession** が強制的に閉じられます。</span><span class="sxs-lookup"><span data-stu-id="48ae6-206">When you end a session, the **PSSessions** that you created in that session are forcibly closed.</span></span>

## <span data-ttu-id="48ae6-207">関連リンク</span><span class="sxs-lookup"><span data-stu-id="48ae6-207">RELATED LINKS</span></span>

[<span data-ttu-id="48ae6-208">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="48ae6-208">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="48ae6-209">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="48ae6-209">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="48ae6-210">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="48ae6-210">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="48ae6-211">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="48ae6-211">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="48ae6-212">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="48ae6-212">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="48ae6-213">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="48ae6-213">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="48ae6-214">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="48ae6-214">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="48ae6-215">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="48ae6-215">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="48ae6-216">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="48ae6-216">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="48ae6-217">about_Remote</span><span class="sxs-lookup"><span data-stu-id="48ae6-217">about_Remote</span></span>](About/about_Remote.md)
