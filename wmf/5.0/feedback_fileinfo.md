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
# <a name="updates-to-fileinfo-object"></a>FileInfo オブジェクトの更新
ファイルのバージョン情報は、特にファイルにパッチが適用された場合に、解釈を間違えやすいデータです。 今回の WMF 5.0 リリースでは、FileInfo オブジェクトに新しいスクリプト プロパティとして **FileVersionRaw** および **ProductVersionRaw** が追加されました。 powershell.exe に対して表示されるプロパティを次に示します ($pid は PowerShell プロセスの ID であるとします)。

```powershell
PS C:\> Get-Process -Id $pid -FileVersionInfo | fl *version* -Force


FileVersionRaw    : 10.0.10586.117
ProductVersionRaw : 10.0.10586.117
FileVersion       : 10.0.10586.117 (th2_release.160212-2359)
ProductVersion    : 10.0.10586.117
