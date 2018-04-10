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
# <a name="updates-to-fileinfo-object"></a>FileInfo オブジェクトの更新
ファイルのバージョン情報は、特にファイルにパッチが適用された場合に、解釈を間違えやすいデータです。 今回の WMF 5.0 リリースでは、FileInfo オブジェクトに新しいスクリプト プロパティとして **FileVersionRaw** および **ProductVersionRaw** が追加されました。 powershell.exe に対して表示されるプロパティを次に示します ($pid は PowerShell プロセスの ID であるとします)。

```powershell
PS C:\> Get-Process -Id $pid -FileVersionInfo | fl *version* -Force


FileVersionRaw    : 10.0.10586.117
ProductVersionRaw : 10.0.10586.117
FileVersion       : 10.0.10586.117 (th2_release.160212-2359)
ProductVersion    : 10.0.10586.117