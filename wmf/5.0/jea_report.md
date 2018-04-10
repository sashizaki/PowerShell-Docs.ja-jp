---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 2af56be1915c148809f52cd9040c45da160ae0a2
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="reporting-on-jea"></a>JEA のレポート
JEA 構成の状態をレポートするには、次のコマンドを使用できます。
1.  **Get-PSSessionConfiguration** は、特定のコンピューター上のすべての登録済みエンドポイントの一覧を返します。
2.  **Get-PSSessionCapability** は、特定のユーザーが特定のエンドポイントで持つ機能についてレポートします。

次に、**Get-PSSessionCapability** の例を示します。
```powershell
Get-PSSessionCapability -ConfigurationName Maintenance -Username "CONTOSO\JohnDoe"

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           clear -> Clear-Host
Alias           cls -> Clear-Host
Alias           exsn -> Exit-PSSession
Alias           gcm -> Get-Command
Alias           measure -> Measure-Object
Alias           select -> Select-Object
Function        Clear-Host
Function        Exit-PSSession
Function        Get-Command
Function        Get-FormatData
Function        Get-Help
Function        Get-UserInfo
Function        Measure-Object
Function        Out-Default
Function        Select-Object
Cmdlet          Restart-Service                                    3.0.0.0 Microsof...


```

JEA セッション中にユーザーが行った_操作_についてレポートするには、次のことを行います。
1. その JEA エンドポイントの "over-the-shoulder" トランスクリプトを有効にして、トランスクリプト ディレクトリで各ユーザーの操作の完全なログを参照します。
2. PowerShell モジュールのログを有効にし、PowerShell イベント ログを調べます。