---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 2fb2e4b0c40322b5ec78fabede22a7e3ecbbd2aa
ms.sourcegitcommit: 77f62a55cac8c13d69d51eef5fade18f71d66955
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2018
ms.locfileid: "39093764"
---
# <a name="reporting-on-jea"></a><span data-ttu-id="bf97c-102">JEA のレポート</span><span class="sxs-lookup"><span data-stu-id="bf97c-102">Reporting on JEA</span></span>

<span data-ttu-id="bf97c-103">JEA 構成の状態をレポートするには、次のコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf97c-103">In order to report on the state of your JEA configuration, you can use:</span></span>

1. <span data-ttu-id="bf97c-104">**Get-PSSessionConfiguration** は、特定のコンピューター上のすべての登録済みエンドポイントの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="bf97c-104">**Get-PSSessionConfiguration** to return a list of all registered endpoints on a given machine.</span></span>
1. <span data-ttu-id="bf97c-105">**Get-PSSessionCapability** は、特定のユーザーが特定のエンドポイントで持つ機能についてレポートします。</span><span class="sxs-lookup"><span data-stu-id="bf97c-105">**Get-PSSessionCapability** to report on the capabilities any given user has on a specific endpoint.</span></span>

<span data-ttu-id="bf97c-106">次に、**Get-PSSessionCapability** の例を示します。</span><span class="sxs-lookup"><span data-stu-id="bf97c-106">Here's an example of **Get-PSSessionCapability**:</span></span>

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

<span data-ttu-id="bf97c-107">JEA セッション中にユーザーが行った_操作_についてレポートするには、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="bf97c-107">To report on the _actions_ users took during a JEA session, you can:</span></span>
1. <span data-ttu-id="bf97c-108">その JEA エンドポイントの "over-the-shoulder" トランスクリプトを有効にして、トランスクリプト ディレクトリで各ユーザーの操作の完全なログを参照します。</span><span class="sxs-lookup"><span data-stu-id="bf97c-108">Enable the "over-the-shoulder" transcripts for that JEA endpoint and consult the transcript directory for a full log of each user's actions</span></span>
2. <span data-ttu-id="bf97c-109">PowerShell モジュールのログを有効にし、PowerShell イベント ログを調べます。</span><span class="sxs-lookup"><span data-stu-id="bf97c-109">Turn on PowerShell module logging and inspect the PowerShell event logs.</span></span>
