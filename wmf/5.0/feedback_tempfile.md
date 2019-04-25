---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: aa2e9540af8b3d4c5de5e00377a84e0e5edd6e4a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057855"
---
# <a name="new-temporaryfile"></a><span data-ttu-id="b5597-102">New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="b5597-102">New-TemporaryFile</span></span>
<span data-ttu-id="b5597-103">スクリプトでは、ときおり、一時ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5597-103">Sometimes in your scripts, you must create a temporary file.</span></span> <span data-ttu-id="b5597-104">**New-TemporaryFile** コマンドレットを使うと、簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="b5597-104">You can easily do this with the **New-TemporaryFile** cmdlet:</span></span>

<span data-ttu-id="b5597-105">PS C:\\&gt; $tempFile = New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="b5597-105">PS C:\\&gt; $tempFile = New-TemporaryFile</span></span>

<span data-ttu-id="b5597-106">PS C:\\&gt; $tempFile.FullName</span><span class="sxs-lookup"><span data-stu-id="b5597-106">PS C:\\&gt; $tempFile.FullName</span></span>

<span data-ttu-id="b5597-107">C:\\Users\\slee\\AppData\\Local\\Temp\\tmp375.tmp</span><span class="sxs-lookup"><span data-stu-id="b5597-107">C:\\Users\\slee\\AppData\\Local\\Temp\\tmp375.tmp</span></span>
