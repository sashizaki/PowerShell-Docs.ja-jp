---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/stop-transcript?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Transcript
ms.openlocfilehash: 86903ca648ff3ee58ec939143b7881741827f453
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209342"
---
# <span data-ttu-id="8b216-103">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="8b216-103">Stop-Transcript</span></span>

## <span data-ttu-id="8b216-104">概要</span><span class="sxs-lookup"><span data-stu-id="8b216-104">SYNOPSIS</span></span>
<span data-ttu-id="8b216-105">トランスクリプトを停止します。</span><span class="sxs-lookup"><span data-stu-id="8b216-105">Stops a transcript.</span></span>

## <span data-ttu-id="8b216-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8b216-106">SYNTAX</span></span>

```
Stop-Transcript [<CommonParameters>]
```

## <span data-ttu-id="8b216-107">Description</span><span class="sxs-lookup"><span data-stu-id="8b216-107">DESCRIPTION</span></span>

<span data-ttu-id="8b216-108">コマンドレットでは、 `Stop-Transcript` コマンドレットによって開始されたトランスクリプトを停止し `Start-Transcript` ます。</span><span class="sxs-lookup"><span data-stu-id="8b216-108">The `Stop-Transcript` cmdlet stops a transcript that was started by the `Start-Transcript` cmdlet.</span></span>
<span data-ttu-id="8b216-109">または、セッションを終了してトランスクリプトを停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="8b216-109">Alternatively, you can end a session to stop a transcript.</span></span>

## <span data-ttu-id="8b216-110">例</span><span class="sxs-lookup"><span data-stu-id="8b216-110">EXAMPLES</span></span>

### <span data-ttu-id="8b216-111">例 1: すべてのトランスクリプトを停止する</span><span class="sxs-lookup"><span data-stu-id="8b216-111">Example 1: Stop all transcripts</span></span>

```powershell
Stop-Transcript
```

<span data-ttu-id="8b216-112">このコマンドは、すべてのトランスクリプトを停止します。</span><span class="sxs-lookup"><span data-stu-id="8b216-112">This command stops all transcripts.</span></span>

## <span data-ttu-id="8b216-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8b216-113">PARAMETERS</span></span>

### <span data-ttu-id="8b216-114">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8b216-114">CommonParameters</span></span>

<span data-ttu-id="8b216-115">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8b216-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8b216-116">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b216-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8b216-117">入力</span><span class="sxs-lookup"><span data-stu-id="8b216-117">INPUTS</span></span>

### <span data-ttu-id="8b216-118">なし</span><span class="sxs-lookup"><span data-stu-id="8b216-118">None</span></span>

<span data-ttu-id="8b216-119">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="8b216-119">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="8b216-120">出力</span><span class="sxs-lookup"><span data-stu-id="8b216-120">OUTPUTS</span></span>

### <span data-ttu-id="8b216-121">System.String</span><span class="sxs-lookup"><span data-stu-id="8b216-121">System.String</span></span>

<span data-ttu-id="8b216-122">このコマンドレットは、ステータスメッセージと出力ファイルへのパスを含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="8b216-122">This cmdlet returns a string that contains a status message and the path to the output file.</span></span>

## <span data-ttu-id="8b216-123">注</span><span class="sxs-lookup"><span data-stu-id="8b216-123">NOTES</span></span>

* <span data-ttu-id="8b216-124">トランスクリプトが開始されていない場合、コマンドはエラーになります。</span><span class="sxs-lookup"><span data-stu-id="8b216-124">If a transcript has not been started, the command fails.</span></span>

*

## <span data-ttu-id="8b216-125">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8b216-125">RELATED LINKS</span></span>

[<span data-ttu-id="8b216-126">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="8b216-126">Start-Transcript</span></span>](Start-Transcript.md)

