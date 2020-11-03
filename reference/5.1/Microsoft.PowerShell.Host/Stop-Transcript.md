---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/stop-transcript?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Transcript
ms.openlocfilehash: 22298a898bd45a9be5eaf98d4963b98ab1bf063b
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93208991"
---
# <span data-ttu-id="287ef-103">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="287ef-103">Stop-Transcript</span></span>

## <span data-ttu-id="287ef-104">概要</span><span class="sxs-lookup"><span data-stu-id="287ef-104">SYNOPSIS</span></span>
<span data-ttu-id="287ef-105">トランスクリプトを停止します。</span><span class="sxs-lookup"><span data-stu-id="287ef-105">Stops a transcript.</span></span>

## <span data-ttu-id="287ef-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="287ef-106">SYNTAX</span></span>

```
Stop-Transcript [<CommonParameters>]
```

## <span data-ttu-id="287ef-107">Description</span><span class="sxs-lookup"><span data-stu-id="287ef-107">DESCRIPTION</span></span>
<span data-ttu-id="287ef-108">コマンドレットでは、 `Stop-Transcript` コマンドレットによって開始されたトランスクリプトを停止し `Start-Transcript` ます。</span><span class="sxs-lookup"><span data-stu-id="287ef-108">The `Stop-Transcript` cmdlet stops a transcript that was started by the `Start-Transcript` cmdlet.</span></span>
<span data-ttu-id="287ef-109">または、セッションを終了してトランスクリプトを停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="287ef-109">Alternatively, you can end a session to stop a transcript.</span></span>

## <span data-ttu-id="287ef-110">例</span><span class="sxs-lookup"><span data-stu-id="287ef-110">EXAMPLES</span></span>

### <span data-ttu-id="287ef-111">例 1: すべてのトランスクリプトを停止する</span><span class="sxs-lookup"><span data-stu-id="287ef-111">Example 1: Stop all transcripts</span></span>

```powershell
Stop-Transcript
```

<span data-ttu-id="287ef-112">このコマンドは、すべてのトランスクリプトを停止します。</span><span class="sxs-lookup"><span data-stu-id="287ef-112">This command stops all transcripts.</span></span>

## <span data-ttu-id="287ef-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="287ef-113">PARAMETERS</span></span>

### <span data-ttu-id="287ef-114">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="287ef-114">CommonParameters</span></span>
<span data-ttu-id="287ef-115">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="287ef-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="287ef-116">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="287ef-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="287ef-117">入力</span><span class="sxs-lookup"><span data-stu-id="287ef-117">INPUTS</span></span>

### <span data-ttu-id="287ef-118">なし</span><span class="sxs-lookup"><span data-stu-id="287ef-118">None</span></span>
<span data-ttu-id="287ef-119">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="287ef-119">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="287ef-120">出力</span><span class="sxs-lookup"><span data-stu-id="287ef-120">OUTPUTS</span></span>

### <span data-ttu-id="287ef-121">System.String</span><span class="sxs-lookup"><span data-stu-id="287ef-121">System.String</span></span>
<span data-ttu-id="287ef-122">このコマンドレットは、ステータスメッセージと出力ファイルへのパスを含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="287ef-122">This cmdlet returns a string that contains a status message and the path to the output file.</span></span>

## <span data-ttu-id="287ef-123">注</span><span class="sxs-lookup"><span data-stu-id="287ef-123">NOTES</span></span>

* <span data-ttu-id="287ef-124">トランスクリプトが開始されていない場合、コマンドはエラーになります。</span><span class="sxs-lookup"><span data-stu-id="287ef-124">If a transcript has not been started, the command fails.</span></span>

*

## <span data-ttu-id="287ef-125">関連リンク</span><span class="sxs-lookup"><span data-stu-id="287ef-125">RELATED LINKS</span></span>

[<span data-ttu-id="287ef-126">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="287ef-126">Start-Transcript</span></span>](Start-Transcript.md)
