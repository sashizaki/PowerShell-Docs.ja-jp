---
author: sdwheeler
ms.author: sewhee
ms.date: 11/18/2020
ms.topic: include
ms.prod: powershell
ms.openlocfilehash: 700021715729254f5704abca16c0e18f598efaec
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "96913281"
---
> [!IMPORTANT]
> <span data-ttu-id="2aa73-101">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="2aa73-101">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="2aa73-102">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2aa73-102">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="2aa73-103">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="2aa73-103">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> ```powershell
> [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
> ```
>
> <span data-ttu-id="2aa73-104">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2aa73-104">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>
