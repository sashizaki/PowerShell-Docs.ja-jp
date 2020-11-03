---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/new-winevent?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WinEvent
ms.openlocfilehash: 202d1792769dcdcda7a156621bfc50c89a1a92ac
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211947"
---
# <span data-ttu-id="2cb3f-103">New-WinEvent</span><span class="sxs-lookup"><span data-stu-id="2cb3f-103">New-WinEvent</span></span>

## <span data-ttu-id="2cb3f-104">概要</span><span class="sxs-lookup"><span data-stu-id="2cb3f-104">SYNOPSIS</span></span>

<span data-ttu-id="2cb3f-105">指定したイベント プロバイダーの新しい Windows イベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-105">Creates a new Windows event for the specified event provider.</span></span>

## <span data-ttu-id="2cb3f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2cb3f-106">SYNTAX</span></span>

```
New-WinEvent [-ProviderName] <String> [-Id] <Int32> [-Version <Byte>] [[-Payload] <Object[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="2cb3f-107">Description</span><span class="sxs-lookup"><span data-stu-id="2cb3f-107">DESCRIPTION</span></span>

<span data-ttu-id="2cb3f-108">**New-WinEvent** コマンドレットは、イベント プロバイダーの Windows イベント トレーシング (ETW) イベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-108">The **New-WinEvent** cmdlet creates an Event Tracing for Windows (ETW) event for an event provider.</span></span>
<span data-ttu-id="2cb3f-109">このコマンドレットを使用すると、Windows PowerShell から ETW チャネルにイベントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-109">You can use this cmdlet to add events to ETW channels from Windows PowerShell.</span></span>

## <span data-ttu-id="2cb3f-110">例</span><span class="sxs-lookup"><span data-stu-id="2cb3f-110">EXAMPLES</span></span>

### <span data-ttu-id="2cb3f-111">例 1</span><span class="sxs-lookup"><span data-stu-id="2cb3f-111">Example 1</span></span>

```powershell
PS C:\> New-WinEvent -ProviderName Microsoft-Windows-PowerShell -Id 45090 -Payload @("Workflow", "Running")
```

<span data-ttu-id="2cb3f-112">このコマンドは、 **New-WinEvent** コマンドレットを使用して、Microsoft-Windows-PowerShell プロバイダーのイベント 45090 を作成します。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-112">This command uses the **New-WinEvent** cmdlet to create event 45090 for the Microsoft-Windows-PowerShell provider.</span></span>

## <span data-ttu-id="2cb3f-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2cb3f-113">PARAMETERS</span></span>

### <span data-ttu-id="2cb3f-114">-Id</span><span class="sxs-lookup"><span data-stu-id="2cb3f-114">-Id</span></span>

<span data-ttu-id="2cb3f-115">インストルメンテーション マニフェストで登録されたイベント ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-115">Specifies an event id that was registered through an instrumentation manifest.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2cb3f-116">-ペイロード</span><span class="sxs-lookup"><span data-stu-id="2cb3f-116">-Payload</span></span>

<span data-ttu-id="2cb3f-117">イベントのメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-117">Specifies the message for the event.</span></span> <span data-ttu-id="2cb3f-118">イベントがイベント ログに書き込まれると、ペイロードがイベント オブジェクトの **Message** プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-118">When the event is written to an event log, the payload is stored in the **Message** property of the event object.</span></span>

<span data-ttu-id="2cb3f-119">指定したペイロードがイベント定義のペイロードと一致しない場合、Windows PowerShell によって警告が生成されますが、コマンドは成功します。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-119">When the specified payload does not match the payload in the event definition, Windows PowerShell generates a warning, but the command still succeeds.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2cb3f-120">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="2cb3f-120">-ProviderName</span></span>

<span data-ttu-id="2cb3f-121">"Microsoft-Windows-PowerShell" など、イベント ログにイベントを書き込むイベント プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-121">Specifies the event provider that writes the event to an event log, such as "Microsoft-Windows-PowerShell".</span></span> <span data-ttu-id="2cb3f-122">ETW イベント プロバイダーは、イベントを ETW セッションに書き込む論理エンティティです。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-122">An ETW event provider is a logical entity that writes events to ETW sessions.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2cb3f-123">-Version</span><span class="sxs-lookup"><span data-stu-id="2cb3f-123">-Version</span></span>

<span data-ttu-id="2cb3f-124">イベントのバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-124">Specifies the version number of the event.</span></span> <span data-ttu-id="2cb3f-125">イベント番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-125">Type the event number.</span></span> <span data-ttu-id="2cb3f-126">Windows PowerShell によって、番号が必要なバイト型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-126">Windows PowerShell converts the number to the required Byte type.</span></span>

<span data-ttu-id="2cb3f-127">このパラメーターを使用すると、同じイベントの異なるバージョンが定義されているときにイベントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-127">This parameter lets you specify an event when different versions of the same event are defined.</span></span>

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

### <span data-ttu-id="2cb3f-128">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2cb3f-128">CommonParameters</span></span>

<span data-ttu-id="2cb3f-129">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2cb3f-130">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2cb3f-131">入力</span><span class="sxs-lookup"><span data-stu-id="2cb3f-131">INPUTS</span></span>

### <span data-ttu-id="2cb3f-132">なし</span><span class="sxs-lookup"><span data-stu-id="2cb3f-132">None</span></span>

<span data-ttu-id="2cb3f-133">このコマンドレットはパイプラインから入力を取得しません。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-133">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="2cb3f-134">出力</span><span class="sxs-lookup"><span data-stu-id="2cb3f-134">OUTPUTS</span></span>

### <span data-ttu-id="2cb3f-135">なし</span><span class="sxs-lookup"><span data-stu-id="2cb3f-135">None</span></span>

<span data-ttu-id="2cb3f-136">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-136">This cmdlet does to generate any output.</span></span>

## <span data-ttu-id="2cb3f-137">注</span><span class="sxs-lookup"><span data-stu-id="2cb3f-137">NOTES</span></span>

* <span data-ttu-id="2cb3f-138">プロバイダーがを eventlog に書き込んでいる場合は、Get-WinEvent コマンドレットを使用してイベントログからイベントを取得できます。</span><span class="sxs-lookup"><span data-stu-id="2cb3f-138">After the provider writes the even to an eventlog, you can use the Get-WinEvent cmdlet to get the event from the event log.</span></span>

## <span data-ttu-id="2cb3f-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2cb3f-139">RELATED LINKS</span></span>

[<span data-ttu-id="2cb3f-140">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="2cb3f-140">Get-WinEvent</span></span>](Get-WinEvent.md)
