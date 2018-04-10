---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 6356902193fc6ec651b2f7e53f8885cb59f17542
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="updates-to-fileinfo-object"></a><span data-ttu-id="6d7b3-102">FileInfo オブジェクトの更新</span><span class="sxs-lookup"><span data-stu-id="6d7b3-102">Updates to FileInfo object</span></span>
<span data-ttu-id="6d7b3-103">ファイルのバージョン情報は、特にファイルにパッチが適用された場合に、解釈を間違えやすいデータです。</span><span class="sxs-lookup"><span data-stu-id="6d7b3-103">File version information can be misleading, particularly in cases where the file was patched.</span></span> <span data-ttu-id="6d7b3-104">今回の WMF 5.0 リリースでは、FileInfo オブジェクトに新しいスクリプト プロパティとして **FileVersionRaw** および **ProductVersionRaw** が追加されました。</span><span class="sxs-lookup"><span data-stu-id="6d7b3-104">This release of WMF 5.0 adds new **FileVersionRaw** and **ProductVersionRaw** script properties to FileInfo objects.</span></span> <span data-ttu-id="6d7b3-105">powershell.exe に対して表示されるプロパティを次に示します ($pid は PowerShell プロセスの ID であるとします)。</span><span class="sxs-lookup"><span data-stu-id="6d7b3-105">Here are the properties as displayed for powershell.exe (assuming $pid is the ID of the PowerShell process):</span></span>

```powershell
PS C:\> Get-Process -Id $pid -FileVersionInfo | fl *version* -Force


FileVersionRaw    : 10.0.10586.117
ProductVersionRaw : 10.0.10586.117
FileVersion       : 10.0.10586.117 (th2_release.160212-2359)
ProductVersion    : 10.0.10586.117