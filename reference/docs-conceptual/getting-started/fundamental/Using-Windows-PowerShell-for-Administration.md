---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell を管理に使用する"
ms.assetid: db6334ec-ace6-436d-ab88-77aefc817511
ms.openlocfilehash: fa87745b9be04d14de37a308d870b73c5a98cf83
ms.sourcegitcommit: 74255f0b5f386a072458af058a15240140acb294
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2017
---
# <a name="using-windows-powershell-for-administration"></a><span data-ttu-id="0504b-103">Windows PowerShell を管理に使用する</span><span class="sxs-lookup"><span data-stu-id="0504b-103">Using Windows PowerShell for Administration</span></span>
<span data-ttu-id="0504b-104">Windows PowerShell の基本的目標は、より良く、より簡単なシステム管理を、対話式でもスクリプトでも提供することです。</span><span class="sxs-lookup"><span data-stu-id="0504b-104">The fundamental goal of Windows PowerShell is providing better, easier administrative control over systems, either interactively or from script.</span></span> <span data-ttu-id="0504b-105">この章では、Windows システムの管理に関する多くの問題への Windows PowerShell を使用した解決策を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="0504b-105">This chapter walks through solutions to many specific problems in administering Windows systems with Windows PowerShell.</span></span> <span data-ttu-id="0504b-106">Windows PowerShell ユーザー ガイドではスクリプトや関数について取り上げませんでしたが、後からスクリプトや関数で解決策を利用することができます。</span><span class="sxs-lookup"><span data-stu-id="0504b-106">Although we have not talked about scripts or functions in the Windows PowerShell User's Guide, the solutions can be used from scripts or as functions later.</span></span> <span data-ttu-id="0504b-107">問題の解決策の一部として、関数を含んだ例を示します。</span><span class="sxs-lookup"><span data-stu-id="0504b-107">We will show examples that include functions as part of the solution to solve problems.</span></span>

<span data-ttu-id="0504b-108">解決策の説明全体を通し、特定のコマンドレット、一般的な Get-WmiObject コマンドレット、さらには Windows および .NET Framework インフラストラクチャの一部である外部ツールを使用した解決策の組み合わせを使用します。</span><span class="sxs-lookup"><span data-stu-id="0504b-108">Throughout the solution descriptions, you will see a mix of solutions using specific cmdlets, the general Get-WmiObject cmdlet, and even external tools that are part of the Windows and .NET Framework infrastructures.</span></span> <span data-ttu-id="0504b-109">外部ツールの使用は Windows PowerShell の長期的な設計意図の一部です。</span><span class="sxs-lookup"><span data-stu-id="0504b-109">Use of external tools is part of the long-term design intent of Windows PowerShell.</span></span> <span data-ttu-id="0504b-110">システムが大きくなるにつれて、ユーザーは、使用できるツールセットでは必要なことすべてが行えない状況に絶えず直面することになります。</span><span class="sxs-lookup"><span data-stu-id="0504b-110">Even as the system grows, users will continually encounter situations in which the available toolsets do not do everything they need.</span></span> <span data-ttu-id="0504b-111">Windows PowerShell では、コマンドレットの実装だけに依存することを助長するのではなく、利用できるあらゆる代替シナリオの解決策を統合することをサポートしようとしています。</span><span class="sxs-lookup"><span data-stu-id="0504b-111">Rather than foster dependency on cmdlet implementations alone, Windows PowerShell tries to support integrating solutions from every possible alternative scenario.</span></span>

