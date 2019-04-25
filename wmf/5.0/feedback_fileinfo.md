---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 5280ef5ff95679dc8721be8f5f81031a4ffe796f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085248"
---
# <a name="updates-to-fileinfo-object"></a><span data-ttu-id="4f35a-102">FileInfo オブジェクトの更新</span><span class="sxs-lookup"><span data-stu-id="4f35a-102">Updates to FileInfo object</span></span>
<span data-ttu-id="4f35a-103">ファイルのバージョン情報は、特にファイルにパッチが適用された場合に、解釈を間違えやすいデータです。</span><span class="sxs-lookup"><span data-stu-id="4f35a-103">File version information can be misleading, particularly in cases where the file was patched.</span></span> <span data-ttu-id="4f35a-104">今回の WMF 5.0 リリースでは、FileInfo オブジェクトに新しいスクリプト プロパティとして **FileVersionRaw** および **ProductVersionRaw** が追加されました。</span><span class="sxs-lookup"><span data-stu-id="4f35a-104">This release of WMF 5.0 adds new **FileVersionRaw** and **ProductVersionRaw** script properties to FileInfo objects.</span></span> <span data-ttu-id="4f35a-105">powershell.exe に対して表示されるプロパティを次に示します ($pid は PowerShell プロセスの ID であるとします)。</span><span class="sxs-lookup"><span data-stu-id="4f35a-105">Here are the properties as displayed for powershell.exe (assuming $pid is the ID of the PowerShell process):</span></span>

```powershell
PS C:\> Get-Process -Id $pid -FileVersionInfo | fl *version* -Force


FileVersionRaw    : 10.0.10586.117
ProductVersionRaw : 10.0.10586.117
FileVersion       : 10.0.10586.117 (th2_release.160212-2359)
ProductVersion    : 10.0.10586.117
