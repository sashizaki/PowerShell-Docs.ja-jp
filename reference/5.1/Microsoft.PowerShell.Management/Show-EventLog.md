---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-EventLog
ms.openlocfilehash: e8dbcf1aa4280c0481714a8a9fb24f2e5ef79ffe
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214408"
---
# <span data-ttu-id="08e93-103">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="08e93-103">Show-EventLog</span></span>

## <span data-ttu-id="08e93-104">概要</span><span class="sxs-lookup"><span data-stu-id="08e93-104">SYNOPSIS</span></span>
<span data-ttu-id="08e93-105">イベント ビューアーでローカル コンピューターまたはリモート コンピューターのイベント ログを表示します。</span><span class="sxs-lookup"><span data-stu-id="08e93-105">Displays the event logs of the local or a remote computer in Event Viewer.</span></span>

## <span data-ttu-id="08e93-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="08e93-106">SYNTAX</span></span>

```
Show-EventLog [[-ComputerName] <String>] [<CommonParameters>]
```

## <span data-ttu-id="08e93-107">Description</span><span class="sxs-lookup"><span data-stu-id="08e93-107">DESCRIPTION</span></span>
<span data-ttu-id="08e93-108">イベントログの **表示** コマンドレットは、ローカルコンピューター上のイベントビューアーを開き、ローカルコンピューターまたはリモートコンピューター上のすべての従来のイベントログに表示します。</span><span class="sxs-lookup"><span data-stu-id="08e93-108">The **Show-EventLog** cmdlet opens Event Viewer on the local computer and displays in it all of the classic event logs on the local computer or a remote computer.</span></span>

<span data-ttu-id="08e93-109">Windows Vista 以降のバージョンの Windows オペレーティングシステムでイベントビューアーを開くには、現在のユーザーがローカルコンピューターの Administrators グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="08e93-109">To open Event Viewer on Windows Vista and later versions of the Windows operating system, the current user must be a member of the Administrators group on the local computer.</span></span>

<span data-ttu-id="08e93-110">**Eventlog** 名詞を含むコマンドレット ( **eventlog** コマンドレット) は、従来のイベントログでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="08e93-110">The cmdlets that contain the **EventLog** noun (the **EventLog** cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="08e93-111">Windows Vista 以降のバージョンの windows オペレーティングシステムで Windows イベントログテクノロジを使用するログからイベントを取得するには、Get-WinEvent コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="08e93-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of the Windows operating system, use the Get-WinEvent cmdlet.</span></span>

## <span data-ttu-id="08e93-112">例</span><span class="sxs-lookup"><span data-stu-id="08e93-112">EXAMPLES</span></span>

### <span data-ttu-id="08e93-113">例 1: ローカルコンピューターのイベントログを表示する</span><span class="sxs-lookup"><span data-stu-id="08e93-113">Example 1: Display event logs for the local computer</span></span>

```
PS C:\> Show-EventLog
```

<span data-ttu-id="08e93-114">このコマンドを実行すると、イベント ビューアーが開き、ローカル コンピューター上の従来のイベント ログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08e93-114">This command opens Event Viewer and displays in it the classic event logs on the local computer.</span></span>

### <span data-ttu-id="08e93-115">例 2: リモートコンピューターのイベントログを表示する</span><span class="sxs-lookup"><span data-stu-id="08e93-115">Example 2: Display event logs for a remote computer</span></span>

```
PS C:\> Show-EventLog -ComputerName "Server01"
```

<span data-ttu-id="08e93-116">このコマンドを実行すると、イベント ビューアーが開き、Server01 コンピューター上の従来のイベント ログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08e93-116">This command opens Event Viewer and displays in it the classic event logs on the Server01 computer.</span></span>

## <span data-ttu-id="08e93-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="08e93-117">PARAMETERS</span></span>

### <span data-ttu-id="08e93-118">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="08e93-118">-ComputerName</span></span>
<span data-ttu-id="08e93-119">リモート コンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="08e93-119">Specifies a remote computer.</span></span>
<span data-ttu-id="08e93-120">[イベントログの **表示]** には、ローカルコンピューター上のイベントビューアーの指定したコンピューターのイベントログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08e93-120">**Show-EventLog** displays the event logs from the specified computer in Event Viewer on the local computer.</span></span>
<span data-ttu-id="08e93-121">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="08e93-121">The default is the local computer.</span></span>

<span data-ttu-id="08e93-122">リモート コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="08e93-122">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>

<span data-ttu-id="08e93-123">このパラメーターは、Windows PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="08e93-123">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="08e93-124">コンピューターがリモート コマンドを実行するように構成されていない場合でも、 *ComputerName* パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="08e93-124">You can use the *ComputerName* parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08e93-125">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="08e93-125">CommonParameters</span></span>
<span data-ttu-id="08e93-126">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="08e93-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="08e93-127">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08e93-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="08e93-128">入力</span><span class="sxs-lookup"><span data-stu-id="08e93-128">INPUTS</span></span>

### <span data-ttu-id="08e93-129">なし</span><span class="sxs-lookup"><span data-stu-id="08e93-129">None</span></span>
<span data-ttu-id="08e93-130">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="08e93-130">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="08e93-131">出力</span><span class="sxs-lookup"><span data-stu-id="08e93-131">OUTPUTS</span></span>

### <span data-ttu-id="08e93-132">なし</span><span class="sxs-lookup"><span data-stu-id="08e93-132">None</span></span>
<span data-ttu-id="08e93-133">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="08e93-133">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="08e93-134">注</span><span class="sxs-lookup"><span data-stu-id="08e93-134">NOTES</span></span>

* <span data-ttu-id="08e93-135">イベント ビューアーが開くと、Windows PowerShell のコマンド プロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="08e93-135">The Windows PowerShell command prompt returns as soon as Event Viewer opens.</span></span> <span data-ttu-id="08e93-136">イベント ビューアーが開いている間は、現在のセッションで作業できます。</span><span class="sxs-lookup"><span data-stu-id="08e93-136">You can work in the current session while Event Viewer is open.</span></span>

  <span data-ttu-id="08e93-137">このコマンドレットにはユーザー インターフェイスが必要なので、Windows Server の Server Core インストールでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="08e93-137">Because this cmdlet requires a user interface, it does not work on Server Core installations of Windows Server.</span></span>

*

## <span data-ttu-id="08e93-138">関連リンク</span><span class="sxs-lookup"><span data-stu-id="08e93-138">RELATED LINKS</span></span>

[<span data-ttu-id="08e93-139">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="08e93-139">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="08e93-140">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="08e93-140">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="08e93-141">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="08e93-141">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="08e93-142">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="08e93-142">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="08e93-143">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="08e93-143">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="08e93-144">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="08e93-144">Write-EventLog</span></span>](Write-EventLog.md)
