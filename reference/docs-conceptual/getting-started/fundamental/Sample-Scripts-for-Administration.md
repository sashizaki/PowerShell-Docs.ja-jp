---
ms.date: 08/27/2018
keywords: PowerShell, コマンドレット
title: システム管理のサンプル スクリプト
ms.assetid: db6334ec-ace6-436d-ab88-77aefc817511
ms.openlocfilehash: 3c771c9568f40ec3a4bb7061c122f33bba7d0382
ms.sourcegitcommit: 59727f71dc204785a1bcdedc02716d8340a77aeb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "43134117"
---
# <a name="sample-scripts-for-system-administration"></a><span data-ttu-id="53526-103">システム管理のサンプル スクリプト</span><span class="sxs-lookup"><span data-stu-id="53526-103">Sample scripts for system administration</span></span>

<span data-ttu-id="53526-104">PowerShell の基本的な目標は、簡単なシステム管理を、対話型またはスクリプトで提供することです。</span><span class="sxs-lookup"><span data-stu-id="53526-104">The fundamental goal of PowerShell is providing easy administrative control over systems, either interactively or from script.</span></span> <span data-ttu-id="53526-105">この例のコレクションでは、PowerShell を使用してシステムを管理するシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="53526-105">This collection of examples walks through scenarios for administering systems with PowerShell.</span></span> <span data-ttu-id="53526-106">例は、スクリプトから使用するか、または後で関数として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="53526-106">The examples can be used from scripts or as functions later.</span></span>

<span data-ttu-id="53526-107">これらの例では、コマンドレットおよび外部ツールの両方を使用しています。</span><span class="sxs-lookup"><span data-stu-id="53526-107">These examples use a mix of cmdlets and external tools.</span></span> <span data-ttu-id="53526-108">外部ツールの使用は、PowerShell の長期的な設計方針の一環です。</span><span class="sxs-lookup"><span data-stu-id="53526-108">Use of external tools is part of the long-term design intent of PowerShell.</span></span> <span data-ttu-id="53526-109">システムが大きくなるにつれて、ユーザーは、利用可能なツールセットでは必要なことすべてが行えない状況に絶えず直面することになります。</span><span class="sxs-lookup"><span data-stu-id="53526-109">Even as the system grows, users continually encounter situations where the available toolsets do not do everything they need.</span></span> <span data-ttu-id="53526-110">PowerShell では、コマンドレットの実装のみに依存していく方針ではなく、利用可能なすべてのツールとソリューションの統合をサポートします。</span><span class="sxs-lookup"><span data-stu-id="53526-110">Rather than foster dependency solely on cmdlet implementations, PowerShell support integrating solutions all available tools.</span></span>