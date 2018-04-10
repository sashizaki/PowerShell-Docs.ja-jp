---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: ada4fcc0beb3eb74b099f221762341abbf2c3b4c
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="new-temporaryfile"></a><span data-ttu-id="305dc-102">New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="305dc-102">New-TemporaryFile</span></span>
<span data-ttu-id="305dc-103">スクリプトでは、ときおり、一時ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="305dc-103">Sometimes in your scripts, you must create a temporary file.</span></span> <span data-ttu-id="305dc-104">**New-TemporaryFile** コマンドレットを使うと、簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="305dc-104">You can easily do this with the **New-TemporaryFile** cmdlet:</span></span>

<span data-ttu-id="305dc-105">PS C:\\&gt; $tempFile = New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="305dc-105">PS C:\\&gt; $tempFile = New-TemporaryFile</span></span>

<span data-ttu-id="305dc-106">PS C:\\&gt; $tempFile.FullName</span><span class="sxs-lookup"><span data-stu-id="305dc-106">PS C:\\&gt; $tempFile.FullName</span></span>

<span data-ttu-id="305dc-107">C:\\Users\\slee\\AppData\\Local\\Temp\\tmp375.tmp</span><span class="sxs-lookup"><span data-stu-id="305dc-107">C:\\Users\\slee\\AppData\\Local\\Temp\\tmp375.tmp</span></span>