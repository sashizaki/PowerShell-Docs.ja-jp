---
ms.date: 08/27/2018
keywords: PowerShell, コマンドレット
title: システム管理のサンプル スクリプト
ms.openlocfilehash: 6b7e6d59bcbd8d30fd583102e326a8f394a4f9e6
ms.sourcegitcommit: a6f13c16a535acea279c0ddeca72f1f0d8a8ce4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67030795"
---
# <a name="sample-scripts-for-system-administration"></a><span data-ttu-id="674f6-103">システム管理のサンプル スクリプト</span><span class="sxs-lookup"><span data-stu-id="674f6-103">Sample scripts for system administration</span></span>

<span data-ttu-id="674f6-104">PowerShell の基本的な目標は、簡単なシステム管理を、対話型またはスクリプトで提供することです。</span><span class="sxs-lookup"><span data-stu-id="674f6-104">The fundamental goal of PowerShell is providing easy administrative control over systems, either interactively or from script.</span></span> <span data-ttu-id="674f6-105">この例のコレクションでは、PowerShell を使用してシステムを管理するシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="674f6-105">This collection of examples walks through scenarios for administering systems with PowerShell.</span></span> <span data-ttu-id="674f6-106">例は、スクリプトから使用するか、または後で関数として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="674f6-106">The examples can be used from scripts or as functions later.</span></span>

<span data-ttu-id="674f6-107">これらの例では、コマンドレットおよび外部ツールの両方を使用しています。</span><span class="sxs-lookup"><span data-stu-id="674f6-107">These examples use a mix of cmdlets and external tools.</span></span> <span data-ttu-id="674f6-108">外部ツールの使用は、PowerShell の長期的な設計方針の一環です。</span><span class="sxs-lookup"><span data-stu-id="674f6-108">Use of external tools is part of the long-term design intent of PowerShell.</span></span> <span data-ttu-id="674f6-109">システムが成長しても、利用可能なツールセットで必要とするすべてのことができるわけではないという状況にユーザーは絶えず遭遇します。</span><span class="sxs-lookup"><span data-stu-id="674f6-109">Even as the system grows, users continually encounter situations where the available toolsets don't do everything they need.</span></span> <span data-ttu-id="674f6-110">PowerShell ソリューションでは、コマンドレット実装のみに依存するのでなく、利用可能な外部ツールとの統合がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="674f6-110">Rather than foster dependency solely on cmdlet implementations, PowerShell solutions support integration with available external tools.</span></span>
