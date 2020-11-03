---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/new-winevent?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WinEvent
ms.openlocfilehash: 8605782176a96fa1901af352ceda8b453d2f1af8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217275"
---
# <span data-ttu-id="2e434-103">New-WinEvent</span><span class="sxs-lookup"><span data-stu-id="2e434-103">New-WinEvent</span></span>

## <span data-ttu-id="2e434-104">概要</span><span class="sxs-lookup"><span data-stu-id="2e434-104">SYNOPSIS</span></span>
<span data-ttu-id="2e434-105">指定したイベント プロバイダーの新しい Windows イベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e434-105">Creates a new Windows event for the specified event provider.</span></span>

## <span data-ttu-id="2e434-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2e434-106">SYNTAX</span></span>

```
New-WinEvent [-ProviderName] <String> [-Id] <Int32> [-Version <Byte>] [[-Payload] <Object[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="2e434-107">Description</span><span class="sxs-lookup"><span data-stu-id="2e434-107">DESCRIPTION</span></span>

<span data-ttu-id="2e434-108">**New-WinEvent** コマンドレットは、イベント プロバイダーの Windows イベント トレーシング (ETW) イベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e434-108">The **New-WinEvent** cmdlet creates an Event Tracing for Windows (ETW) event for an event provider.</span></span>
<span data-ttu-id="2e434-109">このコマンドレットを使用すると、PowerShell から ETW チャネルにイベントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="2e434-109">You can use this cmdlet to add events to ETW channels from PowerShell.</span></span>

## <span data-ttu-id="2e434-110">例</span><span class="sxs-lookup"><span data-stu-id="2e434-110">EXAMPLES</span></span>

### <span data-ttu-id="2e434-111">例 1</span><span class="sxs-lookup"><span data-stu-id="2e434-111">Example 1</span></span>

```powershell
PS C:\> New-WinEvent -ProviderName Microsoft-Windows-PowerShell -Id 45090 -Payload @("Workflow", "Running")
```

<span data-ttu-id="2e434-112">このコマンドは、 **New-WinEvent** コマンドレットを使用して、Microsoft-Windows-PowerShell プロバイダーのイベント 45090 を作成します。</span><span class="sxs-lookup"><span data-stu-id="2e434-112">This command uses the **New-WinEvent** cmdlet to create event 45090 for the Microsoft-Windows-PowerShell provider.</span></span>

## <span data-ttu-id="2e434-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2e434-113">PARAMETERS</span></span>

### <span data-ttu-id="2e434-114">-Id</span><span class="sxs-lookup"><span data-stu-id="2e434-114">-Id</span></span>

<span data-ttu-id="2e434-115">インストルメンテーション マニフェストで登録されたイベント ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e434-115">Specifies an event id that was registered through an instrumentation manifest.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e434-116">-ペイロード</span><span class="sxs-lookup"><span data-stu-id="2e434-116">-Payload</span></span>

<span data-ttu-id="2e434-117">イベントのメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="2e434-117">Specifies the message for the event.</span></span> <span data-ttu-id="2e434-118">イベントがイベント ログに書き込まれると、ペイロードがイベント オブジェクトの **Message** プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="2e434-118">When the event is written to an event log, the payload is stored in the **Message** property of the event object.</span></span>

<span data-ttu-id="2e434-119">指定されたペイロードがイベント定義のペイロードと一致しない場合、PowerShell は警告を生成しますが、コマンドは成功します。</span><span class="sxs-lookup"><span data-stu-id="2e434-119">When the specified payload does not match the payload in the event definition, PowerShell generates a warning, but the command still succeeds.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e434-120">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="2e434-120">-ProviderName</span></span>

<span data-ttu-id="2e434-121">"Microsoft-Windows-PowerShell" など、イベント ログにイベントを書き込むイベント プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="2e434-121">Specifies the event provider that writes the event to an event log, such as "Microsoft-Windows-PowerShell".</span></span> <span data-ttu-id="2e434-122">ETW イベント プロバイダーは、イベントを ETW セッションに書き込む論理エンティティです。</span><span class="sxs-lookup"><span data-stu-id="2e434-122">An ETW event provider is a logical entity that writes events to ETW sessions.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e434-123">-Version</span><span class="sxs-lookup"><span data-stu-id="2e434-123">-Version</span></span>

<span data-ttu-id="2e434-124">イベントのバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e434-124">Specifies the version number of the event.</span></span> <span data-ttu-id="2e434-125">イベント番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="2e434-125">Type the event number.</span></span> <span data-ttu-id="2e434-126">この数値は、PowerShell によって必要なバイト型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="2e434-126">PowerShell converts the number to the required Byte type.</span></span>

<span data-ttu-id="2e434-127">このパラメーターを使用すると、同じイベントの異なるバージョンが定義されているときにイベントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2e434-127">This parameter lets you specify an event when different versions of the same event are defined.</span></span>

```yaml
Type: System.Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e434-128">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e434-128">CommonParameters</span></span>

<span data-ttu-id="2e434-129">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2e434-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2e434-130">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e434-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2e434-131">入力</span><span class="sxs-lookup"><span data-stu-id="2e434-131">INPUTS</span></span>

### <span data-ttu-id="2e434-132">なし</span><span class="sxs-lookup"><span data-stu-id="2e434-132">None</span></span>

<span data-ttu-id="2e434-133">このコマンドレットはパイプラインから入力を取得しません。</span><span class="sxs-lookup"><span data-stu-id="2e434-133">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="2e434-134">出力</span><span class="sxs-lookup"><span data-stu-id="2e434-134">OUTPUTS</span></span>

### <span data-ttu-id="2e434-135">なし</span><span class="sxs-lookup"><span data-stu-id="2e434-135">None</span></span>

<span data-ttu-id="2e434-136">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="2e434-136">This cmdlet does to generate any output.</span></span>

## <span data-ttu-id="2e434-137">注</span><span class="sxs-lookup"><span data-stu-id="2e434-137">NOTES</span></span>

* <span data-ttu-id="2e434-138">プロバイダーがを eventlog に書き込んでいる場合は、Get-WinEvent コマンドレットを使用してイベントログからイベントを取得できます。</span><span class="sxs-lookup"><span data-stu-id="2e434-138">After the provider writes the even to an eventlog, you can use the Get-WinEvent cmdlet to get the event from the event log.</span></span>

## <span data-ttu-id="2e434-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2e434-139">RELATED LINKS</span></span>

[<span data-ttu-id="2e434-140">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="2e434-140">Get-WinEvent</span></span>](Get-WinEvent.md)

