---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/stop-transcript?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Transcript
ms.openlocfilehash: 16b41711e98276fee37d56f77f57e7372daa4cf3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601807"
---
# <span data-ttu-id="bb7d6-102">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="bb7d6-102">Stop-Transcript</span></span>

## <span data-ttu-id="bb7d6-103">概要</span><span class="sxs-lookup"><span data-stu-id="bb7d6-103">SYNOPSIS</span></span>
<span data-ttu-id="bb7d6-104">トランスクリプトを停止します。</span><span class="sxs-lookup"><span data-stu-id="bb7d6-104">Stops a transcript.</span></span>

## <span data-ttu-id="bb7d6-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bb7d6-105">SYNTAX</span></span>

```
Stop-Transcript [<CommonParameters>]
```

## <span data-ttu-id="bb7d6-106">Description</span><span class="sxs-lookup"><span data-stu-id="bb7d6-106">DESCRIPTION</span></span>

<span data-ttu-id="bb7d6-107">コマンドレットでは、 `Stop-Transcript` コマンドレットによって開始されたトランスクリプトを停止し `Start-Transcript` ます。</span><span class="sxs-lookup"><span data-stu-id="bb7d6-107">The `Stop-Transcript` cmdlet stops a transcript that was started by the `Start-Transcript` cmdlet.</span></span>
<span data-ttu-id="bb7d6-108">または、セッションを終了してトランスクリプトを停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb7d6-108">Alternatively, you can end a session to stop a transcript.</span></span>

## <span data-ttu-id="bb7d6-109">例</span><span class="sxs-lookup"><span data-stu-id="bb7d6-109">EXAMPLES</span></span>

### <span data-ttu-id="bb7d6-110">例 1: すべてのトランスクリプトを停止する</span><span class="sxs-lookup"><span data-stu-id="bb7d6-110">Example 1: Stop all transcripts</span></span>

```powershell
Stop-Transcript
```

<span data-ttu-id="bb7d6-111">このコマンドは、すべてのトランスクリプトを停止します。</span><span class="sxs-lookup"><span data-stu-id="bb7d6-111">This command stops all transcripts.</span></span>

## <span data-ttu-id="bb7d6-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bb7d6-112">PARAMETERS</span></span>

### <span data-ttu-id="bb7d6-113">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="bb7d6-113">CommonParameters</span></span>

<span data-ttu-id="bb7d6-114">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="bb7d6-114">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bb7d6-115">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb7d6-115">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bb7d6-116">入力</span><span class="sxs-lookup"><span data-stu-id="bb7d6-116">INPUTS</span></span>

### <span data-ttu-id="bb7d6-117">なし</span><span class="sxs-lookup"><span data-stu-id="bb7d6-117">None</span></span>

<span data-ttu-id="bb7d6-118">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="bb7d6-118">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="bb7d6-119">出力</span><span class="sxs-lookup"><span data-stu-id="bb7d6-119">OUTPUTS</span></span>

### <span data-ttu-id="bb7d6-120">System.String</span><span class="sxs-lookup"><span data-stu-id="bb7d6-120">System.String</span></span>

<span data-ttu-id="bb7d6-121">このコマンドレットは、ステータスメッセージと出力ファイルへのパスを含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="bb7d6-121">This cmdlet returns a string that contains a status message and the path to the output file.</span></span>

## <span data-ttu-id="bb7d6-122">注</span><span class="sxs-lookup"><span data-stu-id="bb7d6-122">NOTES</span></span>

* <span data-ttu-id="bb7d6-123">トランスクリプトが開始されていない場合、コマンドはエラーになります。</span><span class="sxs-lookup"><span data-stu-id="bb7d6-123">If a transcript has not been started, the command fails.</span></span>

*

## <span data-ttu-id="bb7d6-124">関連リンク</span><span class="sxs-lookup"><span data-stu-id="bb7d6-124">RELATED LINKS</span></span>

[<span data-ttu-id="bb7d6-125">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="bb7d6-125">Start-Transcript</span></span>](Start-Transcript.md)

