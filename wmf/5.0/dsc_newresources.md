---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 64a00e041bbeeea117db43116b486e83dfe923b0
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085832"
---
# <a name="new-built-in-dsc-resources"></a><span data-ttu-id="17d00-102">新しい組み込み DSC リソース</span><span class="sxs-lookup"><span data-stu-id="17d00-102">New built-in DSC resources</span></span>

<span data-ttu-id="17d00-103">WMF 5.0 RTM には、4 つの新しい DSC リソースがあります。</span><span class="sxs-lookup"><span data-stu-id="17d00-103">WMF 5.0 RTM has 4 new DSC resources:</span></span>
* <span data-ttu-id="17d00-104">WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="17d00-104">WindowsFeatureSet</span></span>
* <span data-ttu-id="17d00-105">WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="17d00-105">WindowsOptionalFeatureSet</span></span>
* <span data-ttu-id="17d00-106">ServiceSet</span><span class="sxs-lookup"><span data-stu-id="17d00-106">ServiceSet</span></span>
* <span data-ttu-id="17d00-107">ProcessSet</span><span class="sxs-lookup"><span data-stu-id="17d00-107">ProcessSet</span></span>

<span data-ttu-id="17d00-108">これらのリソースは、1 つのリソース呼び出しを使って複数のインスタンスを構成する簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="17d00-108">These resources provide an easy way to configure multiple instances using a single resource call.</span></span>

## <a name="windowsfeatureset"></a><span data-ttu-id="17d00-109">WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="17d00-109">WindowsFeatureSet</span></span>

```powershell
# Get the syntax of WindowsFeatureSet resource
Get-DscResource -Module psdesiredstateconfiguration -Name WindowsFeatureSet -Syntax

WindowsFeatureSet [String] #ResourceName
{
    [DependsOn = [String[]]]
    Name = [String[]]
    [Ensure = [String]]
    [Source = [String]]
    [IncludeAllSubFeature = [Boolean]]
    [Credential = [PSCredential]]
    [LogPath = [String]]
}
```

## <a name="windowsoptionalfeatureset"></a><span data-ttu-id="17d00-110">WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="17d00-110">WindowsOptionalFeatureSet</span></span>

```powershell
# Get the syntax of WindowsOptionalFeatureSet resource
Get-DscResource -Module psdesiredstateconfiguration -Name WindowsOptionalFeatureSet -Syntax

WindowsOptionalFeatureSet [String] #ResourceName
{
    [DependsOn = [String[]]]
    Name = [String[]]
    Ensure = [String]
    [Source = [String[]]]
    [RemoveFilesOnDisable = [Boolean]]
    [LogPath = [String]]
    [NoWindowsUpdateCheck = [Boolean]]
    [LogLevel = [String]]
}
```

## <a name="serviceset"></a><span data-ttu-id="17d00-111">ServiceSet</span><span class="sxs-lookup"><span data-stu-id="17d00-111">ServiceSet</span></span>

```powershell
# Get the syntax of ServiceSet resource
Get-DscResource -Module psdesiredstateconfiguration -Name ServiceSet -Syntax

ServiceSet [String] #ResourceName
{
    [DependsOn = [String[]]]
    Name = [String[]]
    [StartupType = [String]]
    [BuiltInAccount = [String]]
    [State = [String]]
    [Ensure = [String]]
    [Credential = [PSCredential]]
}
```

## <a name="processset"></a><span data-ttu-id="17d00-112">ProcessSet</span><span class="sxs-lookup"><span data-stu-id="17d00-112">ProcessSet</span></span>

```powershell
# Get the syntax of ProcessSet resource
Get-DscResource -Module psdesiredstateconfiguration -Name ProcessSet -Syntax

ProcessSet [String] #ResourceName
{
    [DependsOn = [String[]]]
    Path = [String[]]
    [Credential = [PSCredential]]
    [Ensure = [String]]
    [StandardOutputPath = [String]]
    [StandardErrorPath = [String]]
    [StandardInputPath = [String]]
    [WorkingDirectory = [String]]
}
```
