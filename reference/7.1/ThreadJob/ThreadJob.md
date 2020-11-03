---
Download Help Link: https://aka.ms/powershell71-help
Help Version: 7.1.0.0
Locale: en-US
Module Guid: 0e7b895d-2fec-43f7-8cae-11e8d16f6e40
Module Name: ThreadJob
ms.date: 07/09/2019
title: ThreadJob モジュール
ms.openlocfilehash: 4a6abe107ac041f0ce5fa3e5d776bb0ac352685c
ms.sourcegitcommit: 84fcc90bd018ab76ac4e964d53e7c9c2b5a7b6c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218867"
---
# <span data-ttu-id="201cf-102">ThreadJob モジュール</span><span class="sxs-lookup"><span data-stu-id="201cf-102">ThreadJob Module</span></span>

## <span data-ttu-id="201cf-103">説明</span><span class="sxs-lookup"><span data-stu-id="201cf-103">Description</span></span>
<span data-ttu-id="201cf-104">このモジュールは、既存の PowerShell BackgroundJob を拡張して、新しいスレッドベースの **Threadjob** ジョブを含めます。</span><span class="sxs-lookup"><span data-stu-id="201cf-104">This module extends the existing PowerShell BackgroundJob to include a new thread based **ThreadJob** job.</span></span> <span data-ttu-id="201cf-105">これは、既存の PowerShell ジョブインフラストラクチャ内で動作する PowerShell スクリプトを同時に実行するための軽量ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="201cf-105">This is a lighter weight solution for running concurrent PowerShell scripts that works within the existing PowerShell job infrastructure.</span></span>

## <span data-ttu-id="201cf-106">ThreadJob コマンドレット</span><span class="sxs-lookup"><span data-stu-id="201cf-106">ThreadJob Cmdlets</span></span>

### [<span data-ttu-id="201cf-107">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="201cf-107">Start-ThreadJob</span></span>](Start-ThreadJob.md)
<span data-ttu-id="201cf-108">コマンドレットに似たバックグラウンドジョブを作成し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="201cf-108">Creates background jobs similar to the `Start-Job` cmdlet.</span></span>
