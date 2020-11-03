---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerrestorepoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerRestorePoint
ms.openlocfilehash: 73819aafee9ed1911354daf9af23eedff0a3e14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215480"
---
# <span data-ttu-id="02dfd-103">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="02dfd-103">Get-ComputerRestorePoint</span></span>

## <span data-ttu-id="02dfd-104">概要</span><span class="sxs-lookup"><span data-stu-id="02dfd-104">SYNOPSIS</span></span>
<span data-ttu-id="02dfd-105">ローカル コンピューターで復元ポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-105">Gets the restore points on the local computer.</span></span>

## <span data-ttu-id="02dfd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="02dfd-106">SYNTAX</span></span>

### <span data-ttu-id="02dfd-107">ID (既定値)</span><span class="sxs-lookup"><span data-stu-id="02dfd-107">ID (Default)</span></span>

```
Get-ComputerRestorePoint [[-RestorePoint] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="02dfd-108">LastStatus</span><span class="sxs-lookup"><span data-stu-id="02dfd-108">LastStatus</span></span>

```
Get-ComputerRestorePoint -LastStatus [<CommonParameters>]
```

## <span data-ttu-id="02dfd-109">Description</span><span class="sxs-lookup"><span data-stu-id="02dfd-109">DESCRIPTION</span></span>

<span data-ttu-id="02dfd-110">`Get-ComputerRestorePoint`コマンドレットは、ローカルコンピューターのシステムの復元ポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-110">The `Get-ComputerRestorePoint` cmdlet gets the local computer's system restore points.</span></span> <span data-ttu-id="02dfd-111">また、コンピューターを復元するための最新の試行の状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="02dfd-111">And, it can display the status of the most recent attempt to restore the computer.</span></span>

<span data-ttu-id="02dfd-112">復元ポイントを選択するには、の情報を使用し `Get-ComputerRestorePoint` ます。</span><span class="sxs-lookup"><span data-stu-id="02dfd-112">You can use the information from `Get-ComputerRestorePoint` to select a restore point.</span></span> <span data-ttu-id="02dfd-113">たとえば、コマンドレットの復元ポイントを識別するには、シーケンス番号を使用し `Restore-Computer` ます。</span><span class="sxs-lookup"><span data-stu-id="02dfd-113">For example, use a sequence number to identify a restore point for the `Restore-Computer` cmdlet.</span></span>

<span data-ttu-id="02dfd-114">システムの復元ポイントと `Get-ComputerRestorePoint` コマンドレットは、windows 10、windows 7、Windows Vista、WINDOWS XP などのクライアントオペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="02dfd-114">System restore points and the `Get-ComputerRestorePoint` cmdlet are supported only on client operating systems such as Windows 10, Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="02dfd-115">例</span><span class="sxs-lookup"><span data-stu-id="02dfd-115">EXAMPLES</span></span>

### <span data-ttu-id="02dfd-116">例 1: すべてのシステム復元ポイントを取得する</span><span class="sxs-lookup"><span data-stu-id="02dfd-116">Example 1: Get all system restore points</span></span>

<span data-ttu-id="02dfd-117">この例では、は、 `Get-ComputerRestorePoint` すべてのローカルコンピューターのシステムの復元ポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-117">In this example, `Get-ComputerRestorePoint` gets all the local computer's system restore points.</span></span>

```powershell
Get-ComputerRestorePoint
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
8/7/2019  12:56:45     Installed PowerShell 6-x64     6                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

### <span data-ttu-id="02dfd-118">例 2: 特定のシーケンス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="02dfd-118">Example 2: Get specific sequence numbers</span></span>

<span data-ttu-id="02dfd-119">この例では、特定のシーケンス番号のシステム復元ポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-119">This example gets system restore points for specific sequence numbers.</span></span>

```powershell
Get-ComputerRestorePoint -RestorePoint 4, 5
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

<span data-ttu-id="02dfd-120">`Get-ComputerRestorePoint`**Restorepoint** パラメーターを使用して、コンマで区切られたシーケンス番号の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-120">`Get-ComputerRestorePoint` uses the **RestorePoint** parameter to specify a comma-separated array of sequence numbers.</span></span>

### <span data-ttu-id="02dfd-121">例 3: システムの復元の状態を表示する</span><span class="sxs-lookup"><span data-stu-id="02dfd-121">Example 3: Display the status of a system restore</span></span>

<span data-ttu-id="02dfd-122">この例では、ローカルコンピューターでの最新のシステム復元の状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-122">This example displays the status of the most recent system restore on the local computer.</span></span>

```powershell
Get-ComputerRestorePoint -LastStatus
```

```Output
The last attempt to restore the computer failed.
```

<span data-ttu-id="02dfd-123">`Get-ComputerRestorePoint`**Laststatus** パラメーターを使用して、最新のシステム復元の結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-123">`Get-ComputerRestorePoint` uses the **LastStatus** parameter to display the result of the most recent system restore.</span></span>

### <span data-ttu-id="02dfd-124">例 4: 式を使用して、変更前の時間を変換する</span><span class="sxs-lookup"><span data-stu-id="02dfd-124">Example 4: Use an expression to convert the CreationTime</span></span>

<span data-ttu-id="02dfd-125">`Get-ComputerRestorePoint` Windows Management Instrumentation (WMI) の日付と時刻の文字列として、更新前の **時刻** を出力します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-125">`Get-ComputerRestorePoint` outputs the **CreationTime** as a Windows Management Instrumentation (WMI) date and time string.</span></span>

<span data-ttu-id="02dfd-126">この例では、変数には、日付/ **時刻** の文字列を **DateTime** オブジェクトに変換する式が格納されています。</span><span class="sxs-lookup"><span data-stu-id="02dfd-126">In this example, a variable stores an expression that converts the **CreationTime** string to a **DateTime** object.</span></span> <span data-ttu-id="02dfd-127">変換前に、変更前の **時刻** の文字列を表示するには、のようなコマンドを使用し `((Get-ComputerRestorePoint).CreationTime)` ます。</span><span class="sxs-lookup"><span data-stu-id="02dfd-127">To view **CreationTime** strings before they're converted, use a command such as `((Get-ComputerRestorePoint).CreationTime)`.</span></span> <span data-ttu-id="02dfd-128">WMI の日付と時刻の文字列の詳細については、「 [CIM_DATETIME](/windows/win32/wmisdk/cim-datetime)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02dfd-128">For more information about the WMI date and time string, see [CIM_DATETIME](/windows/win32/wmisdk/cim-datetime).</span></span>

```powershell
$date = @{Label="Date"; Expression={$_.ConvertToDateTime($_.CreationTime)}}
Get-ComputerRestorePoint | Select-Object -Property SequenceNumber, $date, Description
```

```Output
SequenceNumber   Date                 Description
--------------   ----                 -----------
             4   7/30/2019 09:17:24   Windows Update
             5   8/5/2019  08:15:37   Installed PowerShell 7-preview-x64
             6   8/7/2019  12:56:45   Installed PowerShell 6-x64
```

<span data-ttu-id="02dfd-129">変数は、 `$date` **Converttodatetime** メソッドを使用する式を使用してハッシュテーブルを格納します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-129">The `$date` variable stores a hash table with the expression that uses the **ConvertToDateTime** method.</span></span> <span data-ttu-id="02dfd-130">この式は、WMI 文字列から **DateTime** オブジェクトに対して、指定された値 **のプロパティの** 値を変換します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-130">The expression converts the **CreationTime** property's value from a WMI string to a **DateTime** object.</span></span>

<span data-ttu-id="02dfd-131">`Get-ComputerRestorePoint` システムの復元ポイントオブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-131">`Get-ComputerRestorePoint` sends the system restore point objects down the pipeline.</span></span> <span data-ttu-id="02dfd-132">`Select-Object`**Property** パラメーターを使用して、表示するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-132">`Select-Object` uses the **Property** parameter to specify the properties to display.</span></span> <span data-ttu-id="02dfd-133">パイプライン内の各オブジェクトについて、の式によって、 `$date` 更新 **後の時間** が変換され、 **Date** プロパティの結果が出力されます。</span><span class="sxs-lookup"><span data-stu-id="02dfd-133">For each object in the pipeline, the expression in `$date` converts the **CreationTime** and outputs the result in the **Date** property.</span></span>

### <span data-ttu-id="02dfd-134">例 5: プロパティを使用してシーケンス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="02dfd-134">Example 5: Use a property to get a sequence number</span></span>

<span data-ttu-id="02dfd-135">この例では、 **SequenceNumber** プロパティと配列インデックスを使用して、シーケンス番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-135">This example gets a sequence number by using the **SequenceNumber** property and an array index.</span></span> <span data-ttu-id="02dfd-136">出力には、シーケンス番号だけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="02dfd-136">The output only contains the sequence number.</span></span>

```powershell
((Get-ComputerRestorePoint).SequenceNumber)[-1]
```

```Output
6
```

<span data-ttu-id="02dfd-137">`Get-ComputerRestorePoint` 配列インデックスで **SequenceNumber** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-137">`Get-ComputerRestorePoint` uses the **SequenceNumber** property with an array index.</span></span> <span data-ttu-id="02dfd-138">の配列インデックスは、 `-1` 配列内の最新のシーケンス番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-138">The array index of `-1` gets the most recent sequence number in the array.</span></span>

## <span data-ttu-id="02dfd-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="02dfd-139">PARAMETERS</span></span>

### <span data-ttu-id="02dfd-140">-LastStatus</span><span class="sxs-lookup"><span data-stu-id="02dfd-140">-LastStatus</span></span>

<span data-ttu-id="02dfd-141">が `Get-ComputerRestorePoint` 最新のシステム復元操作の状態を取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-141">Indicates that `Get-ComputerRestorePoint` gets the status of the most recent system restore operation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LastStatus
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="02dfd-142">-RestorePoint</span><span class="sxs-lookup"><span data-stu-id="02dfd-142">-RestorePoint</span></span>

<span data-ttu-id="02dfd-143">システムの復元ポイントのシーケンス番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-143">Specifies the sequence numbers of the system restore points.</span></span> <span data-ttu-id="02dfd-144">1つのシーケンス番号を指定することも、シーケンス番号のコンマ区切りの配列を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="02dfd-144">You can specify either a single sequence number or a comma-separated array of sequence numbers.</span></span>

<span data-ttu-id="02dfd-145">**Restorepoint** パラメーターが指定されていない場合、は `Get-ComputerRestorePoint` すべてのローカルコンピューターのシステム復元ポイントを返します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-145">If the **RestorePoint** parameter isn't specified, `Get-ComputerRestorePoint` returns all the local computer's system restore points.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: ID
Aliases:

Required: False
Position: 0
Default value: All restore points
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="02dfd-146">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="02dfd-146">CommonParameters</span></span>

<span data-ttu-id="02dfd-147">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="02dfd-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="02dfd-148">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02dfd-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="02dfd-149">入力</span><span class="sxs-lookup"><span data-stu-id="02dfd-149">INPUTS</span></span>

### <span data-ttu-id="02dfd-150">なし</span><span class="sxs-lookup"><span data-stu-id="02dfd-150">None</span></span>

<span data-ttu-id="02dfd-151">オブジェクトをパイプラインからに送信することはできません `Get-ComputerRestorePoint` 。</span><span class="sxs-lookup"><span data-stu-id="02dfd-151">You can't send objects down the pipeline to `Get-ComputerRestorePoint`.</span></span>

## <span data-ttu-id="02dfd-152">出力</span><span class="sxs-lookup"><span data-stu-id="02dfd-152">OUTPUTS</span></span>

### <span data-ttu-id="02dfd-153">System.management.managementobject # root\default\SystemRestore または String</span><span class="sxs-lookup"><span data-stu-id="02dfd-153">System.Management.ManagementObject#root\default\SystemRestore or String</span></span>

<span data-ttu-id="02dfd-154">`Get-ComputerRestorePoint`**systemrestore** オブジェクトを返します。これは、WINDOWS MANAGEMENT INSTRUMENTATION (WMI) **systemrestore** クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="02dfd-154">`Get-ComputerRestorePoint` returns a **SystemRestore** object, which is an instance of the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

<span data-ttu-id="02dfd-155">**Laststatus** パラメーターを使用すると、は `Get-ComputerRestorePoint` 文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-155">When you use the **LastStatus** parameter, `Get-ComputerRestorePoint` returns a string.</span></span>

## <span data-ttu-id="02dfd-156">注</span><span class="sxs-lookup"><span data-stu-id="02dfd-156">NOTES</span></span>

<span data-ttu-id="02dfd-157">`Get-ComputerRestorePoint`Windows Vista 以降のバージョンの windows でコマンドを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="02dfd-157">To run a `Get-ComputerRestorePoint` command on Windows Vista and later versions of Windows, open PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="02dfd-158">`Get-ComputerRestorePoint` では、WMI **Systemrestore** クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="02dfd-158">`Get-ComputerRestorePoint` uses the WMI **SystemRestore** class.</span></span>

## <span data-ttu-id="02dfd-159">関連リンク</span><span class="sxs-lookup"><span data-stu-id="02dfd-159">RELATED LINKS</span></span>

[<span data-ttu-id="02dfd-160">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="02dfd-160">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="02dfd-161">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="02dfd-161">about_Arrays</span></span>](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[<span data-ttu-id="02dfd-162">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="02dfd-162">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="02dfd-163">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="02dfd-163">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="02dfd-164">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="02dfd-164">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="02dfd-165">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="02dfd-165">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="02dfd-166">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="02dfd-166">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="02dfd-167">SystemRestore</span><span class="sxs-lookup"><span data-stu-id="02dfd-167">SystemRestore</span></span>](/windows/win32/sr/systemrestore)
