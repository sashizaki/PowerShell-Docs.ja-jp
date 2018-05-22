---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 63c3b8237a9883b147380dfe9cb173107cea9aa9
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="updates-to-fileinfo-object"></a><span data-ttu-id="2c5ba-102">FileInfo オブジェクトの更新</span><span class="sxs-lookup"><span data-stu-id="2c5ba-102">Updates to FileInfo object</span></span>
<span data-ttu-id="2c5ba-103">ファイルのバージョン情報は、特にファイルにパッチが適用された場合に、解釈を間違えやすいデータです。</span><span class="sxs-lookup"><span data-stu-id="2c5ba-103">File version information can be misleading, particularly in cases where the file was patched.</span></span> <span data-ttu-id="2c5ba-104">今回の WMF 5.0 リリースでは、FileInfo オブジェクトに新しいスクリプト プロパティとして **FileVersionRaw** および **ProductVersionRaw** が追加されました。</span><span class="sxs-lookup"><span data-stu-id="2c5ba-104">This release of WMF 5.0 adds new **FileVersionRaw** and **ProductVersionRaw** script properties to FileInfo objects.</span></span> <span data-ttu-id="2c5ba-105">powershell.exe に対して表示されるプロパティを次に示します ($pid は PowerShell プロセスの ID であるとします)。</span><span class="sxs-lookup"><span data-stu-id="2c5ba-105">Here are the properties as displayed for powershell.exe (assuming $pid is the ID of the PowerShell process):</span></span>

```powershell
PS C:\> Get-Process -Id $pid -FileVersionInfo | fl *version* -Force


FileVersionRaw    : 10.0.10586.117
ProductVersionRaw : 10.0.10586.117
FileVersion       : 10.0.10586.117 (th2_release.160212-2359)
ProductVersion    : 10.0.10586.117
