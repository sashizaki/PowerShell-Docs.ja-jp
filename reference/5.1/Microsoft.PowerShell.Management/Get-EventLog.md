---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 3/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventLog
ms.openlocfilehash: ab1a97dc3c78bbfdcc239fd573ef3b1f839e2b21
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215467"
---
# <span data-ttu-id="6b5a7-103">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="6b5a7-103">Get-EventLog</span></span>

## <span data-ttu-id="6b5a7-104">概要</span><span class="sxs-lookup"><span data-stu-id="6b5a7-104">SYNOPSIS</span></span>
<span data-ttu-id="6b5a7-105">ローカルコンピューターまたはリモートコンピューター上のイベントログまたはイベントログの一覧のイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-105">Gets the events in an event log, or a list of the event logs, on the local computer or remote computers.</span></span>

## <span data-ttu-id="6b5a7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6b5a7-106">SYNTAX</span></span>

### <span data-ttu-id="6b5a7-107">LogName (既定値)</span><span class="sxs-lookup"><span data-stu-id="6b5a7-107">LogName (Default)</span></span>

```
Get-EventLog [-LogName] <String> [-ComputerName <String[]>] [-Newest <Int32>] [-After <DateTime>]
 [-Before <DateTime>] [-UserName <String[]>] [[-InstanceId] <Int64[]>] [-Index <Int32[]>]
 [-EntryType <String[]>] [-Source <String[]>] [-Message <String>] [-AsBaseObject]
 [<CommonParameters>]
```

### <span data-ttu-id="6b5a7-108">List</span><span class="sxs-lookup"><span data-stu-id="6b5a7-108">List</span></span>

```
Get-EventLog [-ComputerName <String[]>] [-List] [-AsString] [<CommonParameters>]
```

## <span data-ttu-id="6b5a7-109">Description</span><span class="sxs-lookup"><span data-stu-id="6b5a7-109">DESCRIPTION</span></span>

<span data-ttu-id="6b5a7-110">`Get-EventLog`コマンドレットは、ローカルコンピューターとリモートコンピューターからイベントとイベントログを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-110">The `Get-EventLog` cmdlet gets events and event logs from local and remote computers.</span></span> <span data-ttu-id="6b5a7-111">既定では、は `Get-EventLog` ローカルコンピューターからログを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-111">By default, `Get-EventLog` gets logs from the local computer.</span></span> <span data-ttu-id="6b5a7-112">リモートコンピューターからログを取得するには、 **ComputerName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-112">To get logs from remote computers, use the **ComputerName** parameter.</span></span>

<span data-ttu-id="6b5a7-113">パラメーターとプロパティ値を使用して、 `Get-EventLog` イベントを検索できます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-113">You can use the `Get-EventLog` parameters and property values to search for events.</span></span> <span data-ttu-id="6b5a7-114">コマンドレットは、指定されたプロパティ値に一致するイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-114">The cmdlet gets events that match the specified property values.</span></span>

<span data-ttu-id="6b5a7-115">名詞が含まれている PowerShell コマンドレット `EventLog` は、Windows クラシックイベントログ (アプリケーション、システム、セキュリティなど) でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-115">PowerShell cmdlets that contain the `EventLog` noun work only on Windows classic event logs such as Application, System, or Security.</span></span> <span data-ttu-id="6b5a7-116">Windows Vista 以降の windows バージョンで windows イベントログテクノロジを使用するログを取得するには、を使用し `Get-WinEvent` ます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-116">To get logs that use the Windows Event Log technology in Windows Vista and later Windows versions, use `Get-WinEvent`.</span></span>

> [!NOTE]
> <span data-ttu-id="6b5a7-117">`Get-EventLog` 非推奨の Win32 API を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-117">`Get-EventLog` uses a Win32 API that is deprecated.</span></span> <span data-ttu-id="6b5a7-118">結果が正確でない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-118">The results may not be accurate.</span></span> <span data-ttu-id="6b5a7-119">`Get-WinEvent`代わりにコマンドレットを使用してください。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-119">Use the `Get-WinEvent` cmdlet instead.</span></span>

## <span data-ttu-id="6b5a7-120">例</span><span class="sxs-lookup"><span data-stu-id="6b5a7-120">EXAMPLES</span></span>

### <span data-ttu-id="6b5a7-121">例 1: ローカルコンピューター上のイベントログを取得する</span><span class="sxs-lookup"><span data-stu-id="6b5a7-121">Example 1: Get event logs on the local computer</span></span>

<span data-ttu-id="6b5a7-122">この例では、ローカルコンピューターで使用できるイベントログの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-122">This example displays the list of event logs that are available on the local computer.</span></span> <span data-ttu-id="6b5a7-123">Log 列の名前は、イベントを検索するログを指定するために、 **LogName** パラメーターと共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-123">The names in the Log column are used with the **LogName** parameter to specify which log is searched for events.</span></span>

```powershell
Get-EventLog -List
```

```Output
Max(K)   Retain   OverflowAction      Entries  Log
------   ------   --------------      -------  ---
15,168        0   OverwriteAsNeeded   20,792   Application
15,168        0   OverwriteAsNeeded   12,559   System
15,360        0   OverwriteAsNeeded   11,173   Windows PowerShell
```

<span data-ttu-id="6b5a7-124">`Get-EventLog`コマンドレットは **List** パラメーターを使用して、使用可能なログを表示します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-124">The `Get-EventLog` cmdlet uses the **List** parameter to display the available logs.</span></span>

### <span data-ttu-id="6b5a7-125">例 2: ローカルコンピューターのイベントログから最近のエントリを取得する</span><span class="sxs-lookup"><span data-stu-id="6b5a7-125">Example 2: Get recent entries from an event log on the local computer</span></span>

<span data-ttu-id="6b5a7-126">この例では、システムイベントログから最新のエントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-126">This example gets recent entries from the System event log.</span></span>

```powershell
Get-EventLog -LogName System -Newest 5
```

```Output
Index   Time          EntryType    Source              InstanceID   Message
-----   ----          ---------    ------              ----------   -------
13820   Jan 17 19:16  Error        DCOM                     10016   The description for Event...
13819   Jan 17 19:08  Error        DCOM                     10016   The description for Event...
13818   Jan 17 19:06  Information  Service Control...  1073748864   The start type of the Back...
13817   Jan 17 19:05  Error        DCOM                     10016   The description for Event...
13815   Jan 17 19:03  Information  Microsoft-Windows...        35   The time service is now sync...
```

<span data-ttu-id="6b5a7-127">`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムイベントログを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-127">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System event log.</span></span> <span data-ttu-id="6b5a7-128">最新 **のパラメーターは、最新** の5つのイベントを返します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-128">The **Newest** parameter returns the five most recent events.</span></span>

### <span data-ttu-id="6b5a7-129">例 3: イベントログ内の特定の数のエントリのすべてのソースを検索する</span><span class="sxs-lookup"><span data-stu-id="6b5a7-129">Example 3: Find all sources for a specific number of entries in an event log</span></span>

<span data-ttu-id="6b5a7-130">この例では、システムイベントログの最新のエントリ1000に含まれているすべてのソースを検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-130">This example shows how to find all of the sources that are included in the 1000 most recent entries in the System event log.</span></span>

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$Events | Group-Object -Property Source -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count   Name
-----   ----
  110   DCOM
   65   Service Control Manager
   51   Microsoft-Windows-Kern...
   14   EventLog
   14   BTHUSB
   13   Win32k
```

<span data-ttu-id="6b5a7-131">`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムログを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-131">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="6b5a7-132">最新 **のパラメーターは** 、最新の1000のイベントを選択します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-132">The **Newest** parameter selects the 1000 most recent events.</span></span> <span data-ttu-id="6b5a7-133">イベントオブジェクトは変数に格納され `$Events` ます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-133">The event objects are stored in the `$Events` variable.</span></span> <span data-ttu-id="6b5a7-134">オブジェクトは、パイプラインを介して `$Events` コマンドレットに送信され `Group-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-134">The `$Events` objects are sent down the pipeline to the `Group-Object` cmdlet.</span></span>
<span data-ttu-id="6b5a7-135">`Group-Object`**Property** パラメーターを使用して、ソースごとにオブジェクトをグループ化し、各ソースのオブジェクト数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-135">`Group-Object` uses the **Property** parameter to group the objects by source and counts the number of objects for each source.</span></span> <span data-ttu-id="6b5a7-136">**Noelement** パラメーターは、グループメンバーを出力から削除します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-136">The **NoElement** parameter removes the group members from the output.</span></span>
<span data-ttu-id="6b5a7-137">コマンドレットでは、 `Sort-Object` **Property** パラメーターを使用して、各ソース名のカウントで並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-137">The `Sort-Object` cmdlet uses the **Property** parameter to sort by the count of each source name.</span></span>
<span data-ttu-id="6b5a7-138">**降順** のパラメーターは、リストを降順で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-138">The **Descending** parameter sorts the list in order by count from highest to lowest.</span></span>

### <span data-ttu-id="6b5a7-139">例 4: 特定のイベントログからエラーイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="6b5a7-139">Example 4: Get error events from a specific event log</span></span>

<span data-ttu-id="6b5a7-140">この例では、システムイベントログからエラーイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-140">This example gets error events from the System event log.</span></span>

```powershell
Get-EventLog -LogName System -EntryType Error
```

```Output
Index Time          EntryType   Source  InstanceID Message
----- ----          ---------   ------  ---------- -------
13296 Jan 16 13:53  Error       DCOM    10016 The description for Event ID '10016' in Source...
13291 Jan 16 13:51  Error       DCOM    10016 The description for Event ID '10016' in Source...
13245 Jan 16 11:45  Error       DCOM    10016 The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error       DCOM    10016 The description for Event ID '10016' in Source...
```

<span data-ttu-id="6b5a7-141">`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムログを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-141">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="6b5a7-142">**Entrytype** パラメーターは、エラーイベントのみを表示するようにイベントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-142">The **EntryType** parameter filters the events to show only Error events.</span></span>

### <span data-ttu-id="6b5a7-143">例 5: InstanceId とソース値を使用してイベントログからイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="6b5a7-143">Example 5: Get events from an event log with an InstanceId and Source value</span></span>

<span data-ttu-id="6b5a7-144">この例では、特定の InstanceId とソースのシステムログからイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-144">This example gets events from the System log for a specific InstanceId and Source.</span></span>

```powershell
Get-EventLog -LogName System -InstanceId 10016 -Source DCOM
```

```Output
Index Time          EntryType  Source  InstanceID  Message
----- ----          ---------  ------  ----------  -------
13245 Jan 16 11:45  Error      DCOM         10016  The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error      DCOM         10016  The description for Event ID '10016' in Source...
13219 Jan 16 10:00  Error      DCOM         10016  The description for Event ID '10016' in Source...
```

<span data-ttu-id="6b5a7-145">`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムログを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-145">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="6b5a7-146">**InstanceID** パラメーターは、指定されたインスタンス ID を持つイベントを選択します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-146">The **InstanceID** parameter selects the events with the specified Instance ID.</span></span> <span data-ttu-id="6b5a7-147">**Source** パラメーターは、イベントプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-147">The **Source** parameter specifies the event property.</span></span>

### <span data-ttu-id="6b5a7-148">例 6: 複数のコンピューターからイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="6b5a7-148">Example 6: Get events from multiple computers</span></span>

<span data-ttu-id="6b5a7-149">このコマンドは、Server01、Server02、および Server03 の3台のコンピューター上のシステムイベントログからイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-149">This command gets the events from the System event log on three computers: Server01, Server02, and Server03.</span></span>

```powershell
Get-EventLog -LogName System -ComputerName Server01, Server02, Server03
```

<span data-ttu-id="6b5a7-150">`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムログを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-150">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="6b5a7-151">**ComputerName** パラメーターでは、コンマ区切りの文字列を使用して、イベントログを取得するコンピューターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-151">The **ComputerName** parameter uses a comma-separated string to list the computers from which you want to get the event logs.</span></span>

### <span data-ttu-id="6b5a7-152">例 7: メッセージ内の特定の単語を含むすべてのイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="6b5a7-152">Example 7: Get all events that include a specific word in the message</span></span>

<span data-ttu-id="6b5a7-153">このコマンドは、イベントのメッセージ内の特定の単語を含む、システムイベントログ内のすべてのイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-153">This command gets all the events in the System event log that contain a specific word in the event's message.</span></span> <span data-ttu-id="6b5a7-154">指定した **メッセージ** パラメーターの値がメッセージのコンテンツに含まれていても、PowerShell コンソールに表示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-154">It's possible that your specified **Message** parameter's value is included in the message's content but isn't displayed on the PowerShell console.</span></span>

```powershell
Get-EventLog -LogName System -Message *description*
```

```Output
Index Time          EntryType   Source       InstanceID   Message
----- ----          ---------   ------       ----------   -------
13821 Jan 17 19:17  Error       DCOM              10016   The description for Event ID '10016'...
13820 Jan 17 19:16  Error       DCOM              10016   The description for Event ID '10016'...
13819 Jan 17 19:08  Error       DCOM              10016   The description for Event ID '10016'...
```

<span data-ttu-id="6b5a7-155">`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムイベントログを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-155">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System event log.</span></span> <span data-ttu-id="6b5a7-156">**Message** パラメーターは、各イベントのメッセージフィールドで検索する単語を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-156">The **Message** parameter specifies a word to search for in the message field of each event.</span></span>

### <span data-ttu-id="6b5a7-157">例 8: イベントのプロパティ値を表示する</span><span class="sxs-lookup"><span data-stu-id="6b5a7-157">Example 8: Display the property values of an event</span></span>

<span data-ttu-id="6b5a7-158">この例では、イベントのすべてのプロパティと値を表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-158">This example shows how to display all of an event's properties and values.</span></span>

```powershell
$A = Get-EventLog -LogName System -Newest 1
$A | Select-Object -Property *
```

```Output
EventID            : 10016
MachineName        : localhost
Data               : {}
Index              : 13821
Category           : (0)
CategoryNumber     : 0
EntryType          : Error
Message            : The description for Event ID '10016' in Source 'DCOM'...
Source             : DCOM
ReplacementStrings : {Local,...}
InstanceId         : 10016
TimeGenerated      : 1/17/2019 19:17:23
TimeWritten        : 1/17/2019 19:17:23
UserName           : username
Site               :
Container          :
```

<span data-ttu-id="6b5a7-159">`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムイベントログを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-159">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System event log.</span></span> <span data-ttu-id="6b5a7-160">最新 **のパラメーターは** 、最新のイベントオブジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-160">The **Newest** parameter selects the most recent event object.</span></span> <span data-ttu-id="6b5a7-161">オブジェクトは変数に格納され `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-161">The object is stored in the `$A` variable.</span></span> <span data-ttu-id="6b5a7-162">変数内のオブジェクトは、パイプラインを介して `$A` コマンドレットに送信され `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-162">The object in the `$A` variable is sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="6b5a7-163">`Select-Object`**Property** パラメーターをアスタリスク () と共に使用して `*` 、すべてのオブジェクトのプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-163">`Select-Object` uses the **Property** parameter with an asterisk (`*`) to select all of the object's properties.</span></span>

### <span data-ttu-id="6b5a7-164">例 9: ソースとイベント ID を使用してイベントログからイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="6b5a7-164">Example 9: Get events from an event log using a source and event ID</span></span>

<span data-ttu-id="6b5a7-165">この例では、指定されたソースとイベント ID のイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-165">This example gets events for a specified Source and Event ID.</span></span>

```powershell
Get-EventLog -LogName Application -Source Outlook | Where-Object {$_.EventID -eq 63} |
              Select-Object -Property Source, EventID, InstanceId, Message
```

```Output
Source   EventID   InstanceId   Message
------   -------   ----------   -------
Outlook       63   1073741887   The Exchange web service request succeeded.
Outlook       63   1073741887   Outlook detected a change notification.
Outlook       63   1073741887   The Exchange web service request succeeded.
```

<span data-ttu-id="6b5a7-166">`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してアプリケーションイベントログを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-166">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the Application event log.</span></span> <span data-ttu-id="6b5a7-167">**Source** パラメーターは、アプリケーション名である Outlook を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-167">The **Source** parameter specifies the application name, Outlook.</span></span> <span data-ttu-id="6b5a7-168">オブジェクトは、パイプラインを介してコマンドレットに送信され `Where-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-168">The objects are sent down the pipeline to the `Where-Object` cmdlet.</span></span> <span data-ttu-id="6b5a7-169">コマンドレットは、パイプライン内の各オブジェクトに対して、変数を使用して、 `Where-Object` `$_.EventID` イベント ID プロパティを指定された値と比較します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-169">For each object in the pipeline, the `Where-Object` cmdlet uses the variable `$_.EventID` to compare the Event ID property to the specified value.</span></span> <span data-ttu-id="6b5a7-170">オブジェクトは、パイプラインを介してコマンドレットに送信され `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-170">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="6b5a7-171">`Select-Object`**プロパティ** パラメーターを使用して、PowerShell コンソールに表示するプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-171">`Select-Object` uses the **Property** parameter to select the properties to display in the PowerShell console.</span></span>

### <span data-ttu-id="6b5a7-172">例 10: イベントを取得し、プロパティでグループ化する</span><span class="sxs-lookup"><span data-stu-id="6b5a7-172">Example 10: Get events and group by a property</span></span>

```powershell
Get-EventLog -LogName System -UserName NT* | Group-Object -Property UserName -NoElement |
              Select-Object -Property Count, Name
```

```Output
Count  Name
-----  ----
6031   NT AUTHORITY\SYSTEM
  42   NT AUTHORITY\LOCAL SERVICE
   4   NT AUTHORITY\NETWORK SERVICE
```

<span data-ttu-id="6b5a7-173">`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムログを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-173">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="6b5a7-174">**UserName** パラメーターには、 `*` ユーザー名の一部を指定するためのアスタリスク () ワイルドカードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-174">The **UserName** parameter includes the asterisk (`*`) wildcard to specify a portion of the user name.</span></span> <span data-ttu-id="6b5a7-175">イベントオブジェクトは、パイプラインを介してコマンドレットに送信され `Group-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-175">The event objects are sent down the pipeline to the `Group-Object` cmdlet.</span></span> <span data-ttu-id="6b5a7-176">`Group-Object`**Property** パラメーターを使用し **て、ユーザー名プロパティを** 使用してオブジェクトをグループ化し、各ユーザー名のオブジェクトの数をカウントするように指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-176">`Group-Object` uses the **Property** parameter to specify that the **UserName** property is used to group the objects and count the number of objects for each user name.</span></span> <span data-ttu-id="6b5a7-177">**Noelement** パラメーターは、グループメンバーを出力から削除します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-177">The **NoElement** parameter removes the group members from the output.</span></span> <span data-ttu-id="6b5a7-178">オブジェクトは、パイプラインを介してコマンドレットに送信され `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-178">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="6b5a7-179">`Select-Object`**プロパティ** パラメーターを使用して、PowerShell コンソールに表示するプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-179">`Select-Object` uses the **Property** parameter to select the properties to display in the PowerShell console.</span></span>

### <span data-ttu-id="6b5a7-180">例 11: 特定の日付と時刻の範囲内に発生したイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="6b5a7-180">Example 11: Get events that occurred during a specific date and time range</span></span>

<span data-ttu-id="6b5a7-181">この例では、指定された日付と時刻の範囲について、システムイベントログからエラーイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-181">This example gets Error events from the System event log for a specified date and time range.</span></span> <span data-ttu-id="6b5a7-182">**Before** および **After** パラメーターは、日付と時刻の範囲を設定しますが、出力から除外されます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-182">The **Before** and **After** parameters set the date and time range but are excluded from the output.</span></span>

```powershell
$Begin = Get-Date -Date '1/17/2019 08:00:00'
$End = Get-Date -Date '1/17/2019 17:00:00'
Get-EventLog -LogName System -EntryType Error -After $Begin -Before $End
```

```Output
Index Time          EntryType   Source   InstanceID  Message
----- ----          ---------   ------   ----------  -------
13821 Jan 17 13:40  Error       DCOM          10016  The description for Event ID...
13820 Jan 17 13:11  Error       DCOM          10016  The description for Event ID...
...
12372 Jan 17 10:08  Error       DCOM          10016  The description for Event ID...
12371 Jan 17 09:04  Error       DCOM          10016  The description for Event ID...
```

<span data-ttu-id="6b5a7-183">この `Get-Date` コマンドレットで **は、date** パラメーターを使用して日付と時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-183">The `Get-Date` cmdlet uses the **Date** parameter to specify a date and time.</span></span> <span data-ttu-id="6b5a7-184">**DateTime** オブジェクトは、変数と変数に格納され `$Begin` `$End` ます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-184">The **DateTime** objects are stored in the `$Begin` and `$End` variables.</span></span> <span data-ttu-id="6b5a7-185">`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムログを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-185">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="6b5a7-186">**Entrytype** パラメーターは、エラーイベントの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-186">The **EntryType** parameter specifies the Error event type.</span></span> <span data-ttu-id="6b5a7-187">日付と時刻の範囲は、 **After** パラメーターと変数、および `$Begin` **Before** パラメーターと variable によって設定され `$End` ます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-187">The date and time range is set by the **After** parameter and `$Begin` variable and the **Before** parameter and `$End` variable.</span></span>

## <span data-ttu-id="6b5a7-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6b5a7-188">PARAMETERS</span></span>

### <span data-ttu-id="6b5a7-189">-After</span><span class="sxs-lookup"><span data-stu-id="6b5a7-189">-After</span></span>

<span data-ttu-id="6b5a7-190">指定した日付と時刻の後に発生したイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-190">Gets events that occurred after a specified date and time.</span></span> <span data-ttu-id="6b5a7-191">**After** パラメーターの日付と時刻は、出力から除外されます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-191">The **After** parameter date and time are excluded from the output.</span></span> <span data-ttu-id="6b5a7-192">コマンドレットによって返される値など、 **DateTime** オブジェクトを入力し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-192">Enter a **DateTime** object, such as the value returned by the `Get-Date` cmdlet.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6b5a7-193">-AsBaseObject</span><span class="sxs-lookup"><span data-stu-id="6b5a7-193">-AsBaseObject</span></span>

<span data-ttu-id="6b5a7-194">このコマンドレットが各イベントの標準 **EventLogEntry** オブジェクトを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-194">Indicates that this cmdlet returns a standard **System.Diagnostics.EventLogEntry** object for each event.</span></span> <span data-ttu-id="6b5a7-195">このパラメーターを指定しない場合、は、 `Get-EventLog` 追加 **の eventlogname** 、 **Source** 、および **InstanceId** プロパティを持つ拡張 **PSObject** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-195">Without this parameter, `Get-EventLog` returns an extended **PSObject** object with additional **EventLogName** , **Source** , and **InstanceId** properties.</span></span>

<span data-ttu-id="6b5a7-196">このパラメーターの効果を確認するには、イベントをコマンドレットにパイプ処理 `Get-Member` し、結果の **TypeName** 値を調べます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-196">To see the effect of this parameter, pipe the events to the `Get-Member` cmdlet and examine the **TypeName** value in the result.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6b5a7-197">-AsString</span><span class="sxs-lookup"><span data-stu-id="6b5a7-197">-AsString</span></span>

<span data-ttu-id="6b5a7-198">このコマンドレットが、オブジェクトではなく文字列として出力を返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-198">Indicates that this cmdlet returns the output as strings, instead of objects.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6b5a7-199">-Before</span><span class="sxs-lookup"><span data-stu-id="6b5a7-199">-Before</span></span>

<span data-ttu-id="6b5a7-200">指定した日付と時刻の前に発生したイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-200">Gets events that occurred before a specified date and time.</span></span> <span data-ttu-id="6b5a7-201">**Before** パラメーターの日付と時刻は、出力から除外されます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-201">The **Before** parameter date and time are excluded from the output.</span></span> <span data-ttu-id="6b5a7-202">コマンドレットによって返される値など、 **DateTime** オブジェクトを入力し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-202">Enter a **DateTime** object, such as the value returned by the `Get-Date` cmdlet.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6b5a7-203">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="6b5a7-203">-ComputerName</span></span>

<span data-ttu-id="6b5a7-204">このパラメーターは、リモートコンピューターの NetBIOS 名、インターネットプロトコル (IP) アドレス、または完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-204">This parameter specifies a remote computer's NetBIOS name, Internet Protocol (IP) address, or a fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="6b5a7-205">**ComputerName** パラメーターが指定されていない場合、は `Get-EventLog` 既定でローカルコンピューターになります。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-205">If the **ComputerName** parameter isn't specified, `Get-EventLog` defaults to the local computer.</span></span> <span data-ttu-id="6b5a7-206">パラメーターでは、ドット ( `.` ) を指定してローカルコンピューターを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-206">The parameter also accepts a dot (`.`) to specify the local computer.</span></span>

<span data-ttu-id="6b5a7-207">**ComputerName** パラメーターは、Windows PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-207">The **ComputerName** parameter doesn't rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="6b5a7-208">`Get-EventLog`コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターと共にを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-208">You can use `Get-EventLog` with the **ComputerName** parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6b5a7-209">-EntryType</span><span class="sxs-lookup"><span data-stu-id="6b5a7-209">-EntryType</span></span>

<span data-ttu-id="6b5a7-210">文字列配列として、このコマンドレットが取得するイベントのエントリの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-210">Specifies, as a string array, the entry type of the events that this cmdlet gets.</span></span>

<span data-ttu-id="6b5a7-211">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-211">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="6b5a7-212">エラー</span><span class="sxs-lookup"><span data-stu-id="6b5a7-212">Error</span></span>
- <span data-ttu-id="6b5a7-213">Information</span><span class="sxs-lookup"><span data-stu-id="6b5a7-213">Information</span></span>
- <span data-ttu-id="6b5a7-214">FailureAudit</span><span class="sxs-lookup"><span data-stu-id="6b5a7-214">FailureAudit</span></span>
- <span data-ttu-id="6b5a7-215">SuccessAudit</span><span class="sxs-lookup"><span data-stu-id="6b5a7-215">SuccessAudit</span></span>
- <span data-ttu-id="6b5a7-216">警告</span><span class="sxs-lookup"><span data-stu-id="6b5a7-216">Warning</span></span>

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6b5a7-217">-インデックス</span><span class="sxs-lookup"><span data-stu-id="6b5a7-217">-Index</span></span>

<span data-ttu-id="6b5a7-218">イベントログから取得するインデックス値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-218">Specifies the index values to get from the event log.</span></span> <span data-ttu-id="6b5a7-219">パラメーターは、値のコンマ区切りの文字列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-219">The parameter accepts a comma-separated string of values.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6b5a7-220">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="6b5a7-220">-InstanceId</span></span>

<span data-ttu-id="6b5a7-221">イベントログから取得するインスタンス Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-221">Specifies the Instance IDs to get from the event log.</span></span> <span data-ttu-id="6b5a7-222">パラメーターは、値のコンマ区切りの文字列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-222">The parameter accepts a comma-separated string of values.</span></span>

```yaml
Type: System.Int64[]
Parameter Sets: LogName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6b5a7-223">-List</span><span class="sxs-lookup"><span data-stu-id="6b5a7-223">-List</span></span>

<span data-ttu-id="6b5a7-224">コンピューター上のイベントログの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-224">Displays the list of event logs on the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6b5a7-225">-LogName</span><span class="sxs-lookup"><span data-stu-id="6b5a7-225">-LogName</span></span>

<span data-ttu-id="6b5a7-226">1つのイベントログの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-226">Specifies the name of one event log.</span></span> <span data-ttu-id="6b5a7-227">ログ名を検索するには、を使用 `Get-EventLog -List` します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-227">To find the log names use `Get-EventLog -List`.</span></span> <span data-ttu-id="6b5a7-228">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-228">Wildcard characters are permitted.</span></span> <span data-ttu-id="6b5a7-229">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-229">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="6b5a7-230">-メッセージ</span><span class="sxs-lookup"><span data-stu-id="6b5a7-230">-Message</span></span>

<span data-ttu-id="6b5a7-231">イベントメッセージに文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-231">Specifies a string in the event message.</span></span> <span data-ttu-id="6b5a7-232">このパラメーターを使用して、特定の単語または語句を含むメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-232">You can use this parameter to search for messages that contain certain words or phrases.</span></span> <span data-ttu-id="6b5a7-233">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-233">Wildcards are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: MSG

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="6b5a7-234">-最新</span><span class="sxs-lookup"><span data-stu-id="6b5a7-234">-Newest</span></span>

<span data-ttu-id="6b5a7-235">は、最新のイベントから開始し、指定された数のイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-235">Begins with the newest events and gets the specified number of events.</span></span> <span data-ttu-id="6b5a7-236">たとえば、イベントの数が必要です `-Newest 100` 。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-236">The number of events is required, for example `-Newest 100`.</span></span> <span data-ttu-id="6b5a7-237">返されるイベントの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-237">Specifies the maximum number of events that are returned.</span></span>

```yaml
Type: System.Int32
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6b5a7-238">-Source</span><span class="sxs-lookup"><span data-stu-id="6b5a7-238">-Source</span></span>

<span data-ttu-id="6b5a7-239">このコマンドレットが取得するログに書き込まれたソースを文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-239">Specifies, as a string array, sources that were written to the log that this cmdlet gets.</span></span> <span data-ttu-id="6b5a7-240">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-240">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ABO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="6b5a7-241">-UserName</span><span class="sxs-lookup"><span data-stu-id="6b5a7-241">-UserName</span></span>

<span data-ttu-id="6b5a7-242">イベントに関連付けられているユーザー名を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-242">Specifies, as a string array, user names that are associated with events.</span></span> <span data-ttu-id="6b5a7-243">名前または名前パターンを入力します (、、など) `User01` `User*` `Domain01\User*` 。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-243">Enter names or name patterns, such as `User01`, `User*`, or `Domain01\User*`.</span></span> <span data-ttu-id="6b5a7-244">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-244">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="6b5a7-245">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b5a7-245">CommonParameters</span></span>

<span data-ttu-id="6b5a7-246">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-246">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6b5a7-247">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-247">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6b5a7-248">入力</span><span class="sxs-lookup"><span data-stu-id="6b5a7-248">INPUTS</span></span>

### <span data-ttu-id="6b5a7-249">なし</span><span class="sxs-lookup"><span data-stu-id="6b5a7-249">None</span></span>

<span data-ttu-id="6b5a7-250">入力をにパイプすることはできません `Get-EventLog` 。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-250">You cannot pipe input to `Get-EventLog`.</span></span>

## <span data-ttu-id="6b5a7-251">出力</span><span class="sxs-lookup"><span data-stu-id="6b5a7-251">OUTPUTS</span></span>

### <span data-ttu-id="6b5a7-252">EventLogEntry。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-252">System.Diagnostics.EventLogEntry.</span></span> <span data-ttu-id="6b5a7-253">システムの診断。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-253">System.Diagnostics.EventLog.</span></span> <span data-ttu-id="6b5a7-254">System.String</span><span class="sxs-lookup"><span data-stu-id="6b5a7-254">System.String</span></span>

<span data-ttu-id="6b5a7-255">**LogName** パラメーターを指定した場合、出力は **EventLogEntry** オブジェクトのコレクションになります。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-255">If the **LogName** parameter is specified, the output is a collection of **System.Diagnostics.EventLogEntry** objects.</span></span>

<span data-ttu-id="6b5a7-256">**List** パラメーターのみを指定した場合、出力は、 **system.string オブジェクトの** コレクションになります。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-256">If only the **List** parameter is specified, the output is a collection of **System.Diagnostics.EventLog** objects.</span></span>

<span data-ttu-id="6b5a7-257">**List** パラメーターと **asstring** パラメーターの両方を指定した場合、出力は **system.string** オブジェクトのコレクションになります。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-257">If both the **List** and **AsString** parameters are specified, the output is a collection of **System.String** objects.</span></span>

## <span data-ttu-id="6b5a7-258">注</span><span class="sxs-lookup"><span data-stu-id="6b5a7-258">NOTES</span></span>

<span data-ttu-id="6b5a7-259">コマンドレット `Get-EventLog` と `Get-WinEvent` は、Windows プレインストール環境 (Windows PE) ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6b5a7-259">The cmdlets `Get-EventLog` and `Get-WinEvent` are not supported in the Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="6b5a7-260">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6b5a7-260">RELATED LINKS</span></span>

[<span data-ttu-id="6b5a7-261">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="6b5a7-261">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="6b5a7-262">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="6b5a7-262">Get-WinEvent</span></span>](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[<span data-ttu-id="6b5a7-263">Group-Object</span><span class="sxs-lookup"><span data-stu-id="6b5a7-263">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="6b5a7-264">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="6b5a7-264">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="6b5a7-265">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="6b5a7-265">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="6b5a7-266">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="6b5a7-266">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="6b5a7-267">Select-Object</span><span class="sxs-lookup"><span data-stu-id="6b5a7-267">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="6b5a7-268">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="6b5a7-268">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="6b5a7-269">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="6b5a7-269">Write-EventLog</span></span>](Write-EventLog.md)
