---
ms.date: 08/23/2018
keywords: PowerShell, コマンドレット
title: PowerShell パイプラインの概要
ms.openlocfilehash: 3033a4fe1a704fbbfa76e6d38662c8b22c3dbd9b
ms.sourcegitcommit: a6f13c16a535acea279c0ddeca72f1f0d8a8ce4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67030378"
---
# <a name="understanding-pipelines"></a><span data-ttu-id="dd503-103">パイプラインの概要</span><span class="sxs-lookup"><span data-stu-id="dd503-103">Understanding pipelines</span></span>

<span data-ttu-id="dd503-104">パイプラインは、複数の管を 1 つに継ぎ合わせた管路のような役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="dd503-104">Pipelines act like a series of connected segments of pipe.</span></span> <span data-ttu-id="dd503-105">パイプラインに沿って移動する項目は、個々の管を通過します。</span><span class="sxs-lookup"><span data-stu-id="dd503-105">Items moving along the pipeline pass through each segment.</span></span> <span data-ttu-id="dd503-106">PowerShell でパイプラインを作成するには、パイプ演算子 (|) を使ってコマンドを接続します。</span><span class="sxs-lookup"><span data-stu-id="dd503-106">To create a pipeline in PowerShell, you connect commands together with the pipe operator "|".</span></span> <span data-ttu-id="dd503-107">接続すると、各コマンドの出力が、次のコマンドの入力として使用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="dd503-107">The output of each command is used as input to the next command.</span></span>

<span data-ttu-id="dd503-108">パイプラインで使用される表記は、他のシェルで使用される表記とほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="dd503-108">The notation used for pipelines is similar to the notation used in other shells.</span></span> <span data-ttu-id="dd503-109">PowerShell でのパイプラインの違いは、一目見ただけではわかりにくいかもしれません。</span><span class="sxs-lookup"><span data-stu-id="dd503-109">At first glance, it may not be apparent how pipelines are different in PowerShell.</span></span> <span data-ttu-id="dd503-110">画面にはテキストが表示されますが、PowerShell は、コマンド間ではテキストではなくオブジェクトを受け渡します。</span><span class="sxs-lookup"><span data-stu-id="dd503-110">Although you see text on the screen, PowerShell pipes objects, not text, between commands.</span></span>

## <a name="the-powershell-pipeline"></a><span data-ttu-id="dd503-111">PowerShell のパイプライン</span><span class="sxs-lookup"><span data-stu-id="dd503-111">The PowerShell pipeline</span></span>

<span data-ttu-id="dd503-112">パイプラインは、コマンドライン インターフェイスで使用される最も重要な概念と言っても過言ではありません。</span><span class="sxs-lookup"><span data-stu-id="dd503-112">Pipelines are arguably the most valuable concept used in command-line interfaces.</span></span> <span data-ttu-id="dd503-113">適切に利用すれば、パイプラインによって複雑なコマンドを使用する負荷が軽減され、より簡単にコマンドのワークフローを確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="dd503-113">When used properly, pipelines reduce the effort of using complex commands and make it easier to see the flow of work for the commands.</span></span> <span data-ttu-id="dd503-114">パイプラインの各コマンド (パイプライン要素と呼ばれる) は、出力をパイプライン内の次のコマンドに項目単位で渡します。</span><span class="sxs-lookup"><span data-stu-id="dd503-114">Each command in a pipeline (called a pipeline element) passes its output to the next command in the pipeline, item-by-item.</span></span> <span data-ttu-id="dd503-115">コマンドでは、一度に複数の項目を処理する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="dd503-115">Commands don't have to handle more than one item at a time.</span></span> <span data-ttu-id="dd503-116">結果として、リソース使用量が低下すると共に、出力の取得をすぐに開始できるようになります。</span><span class="sxs-lookup"><span data-stu-id="dd503-116">The result is reduced resource consumption and the ability to begin getting the output immediately.</span></span>

<span data-ttu-id="dd503-117">たとえば、`Out-Host` コマンドレットを使用して、別のコマンドからの出力をページ単位で表示させると、通常のテキストがページごとに分割されて画面上に表示されているだけのように見えます。</span><span class="sxs-lookup"><span data-stu-id="dd503-117">For example, if you use the `Out-Host` cmdlet to force a page-by-page display of output from another command, the output looks just like the normal text displayed on the screen, broken up into pages:</span></span>

```powershell
Get-ChildItem -Path C:\WINDOWS\System32 | Out-Host -Paging
```

```Output
    Directory: C:\WINDOWS\system32

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        4/12/2018   2:15 AM                0409
d-----        5/13/2018  11:31 PM                1033
d-----        4/11/2018   4:38 PM                AdvancedInstallers
d-----        5/13/2018  11:13 PM                af-ZA
d-----        5/13/2018  11:13 PM                am-et
d-----        4/11/2018   4:38 PM                AppLocker
d-----        5/13/2018  11:31 PM                appmgmt
d-----        7/11/2018   2:05 AM                appraiser
d---s-        4/12/2018   2:20 AM                AppV
d-----        5/13/2018  11:10 PM                ar-SA
d-----        5/13/2018  11:13 PM                as-IN
d-----        8/14/2018   9:03 PM                az-Latn-AZ
d-----        5/13/2018  11:13 PM                be-BY
d-----        5/13/2018  11:10 PM                BestPractices
d-----        5/13/2018  11:10 PM                bg-BG
d-----        5/13/2018  11:13 PM                bn-BD
d-----        5/13/2018  11:13 PM                bn-IN
d-----        8/14/2018   9:03 PM                Boot
d-----        8/14/2018   9:03 PM                bs-Latn-BA
d-----        4/11/2018   4:38 PM                Bthprops
d-----        4/12/2018   2:19 AM                ca-ES
d-----        8/14/2018   9:03 PM                ca-ES-valencia
d-----        5/13/2018  10:46 PM                CatRoot
d-----        8/23/2018   5:07 PM                catroot2
<SPACE> next page; <CR> next line; Q quit
...
```

<span data-ttu-id="dd503-118">また、表示する完全なページが準備できると、`Out-Host` コマンドレットに処理が転送されるため、ページングによって CPU 使用率が低下します。</span><span class="sxs-lookup"><span data-stu-id="dd503-118">Paging also reduces CPU utilization because processing transfers to the `Out-Host` cmdlet when it has a complete page ready to display.</span></span> <span data-ttu-id="dd503-119">パイプライン内で先行するコマンドレットは、次のページの出力が利用可能になるまで、実行を一時停止します。</span><span class="sxs-lookup"><span data-stu-id="dd503-119">The cmdlets that precede it in the pipeline pause execution until the next page of output is available.</span></span>

<span data-ttu-id="dd503-120">Windows タスク マネージャーで次のコマンドを比較することにより、パイプによる CPU とメモリの使用量への影響を確認できます。</span><span class="sxs-lookup"><span data-stu-id="dd503-120">You can see how piping impacts CPU and memory usage in the Windows Task Manager by comparing the following commands:</span></span>

- `Get-ChildItem C:\Windows -Recurse`
- `Get-ChildItem C:\Windows -Recurse | Out-Host -Paging`

> [!NOTE]
> <span data-ttu-id="dd503-121">**Paging** パラメーターは、すべての PowerShell ホストでサポートされているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="dd503-121">The **Paging** parameter is not supported by all PowerShell hosts.</span></span> <span data-ttu-id="dd503-122">たとえば、PowerShell ISE で **Paging** パラメーターを使おうとすると、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd503-122">For example, when you try to use the **Paging** parameter in the PowerShell ISE, you see the following error:</span></span>
>
> ```Output
> out-lineoutput : The method or operation is not implemented.
> At line:1 char:1
> + Get-ChildItem C:\Windows -Recurse | Out-Host -Paging
> + ~~~~~~~~~~~~~~~~~~~~~~~~~~~
>     + CategoryInfo          : NotSpecified: (:) [out-lineoutput], NotImplementedException
>     + FullyQualifiedErrorId : System.NotImplementedException,Microsoft.PowerShell.Commands.OutLineOutputCommand
> ```

## <a name="objects-in-the-pipeline"></a><span data-ttu-id="dd503-123">パイプライン内のオブジェクト</span><span class="sxs-lookup"><span data-stu-id="dd503-123">Objects in the pipeline</span></span>

<span data-ttu-id="dd503-124">PowerShell でコマンドレットを実行した場合、コンソール ウィンドウではオブジェクトをテキストで表す必要があるため、テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd503-124">When you run a cmdlet in PowerShell, you see text output because it is necessary to represent objects as text in a console window.</span></span> <span data-ttu-id="dd503-125">テキスト出力では、出力されるオブジェクトのすべてのプロパティが必ず表示されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="dd503-125">The text output may not display all of the properties of the object being output.</span></span>

<span data-ttu-id="dd503-126">たとえば、`Get-Location` コマンドレットについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="dd503-126">For example, consider the `Get-Location` cmdlet.</span></span> <span data-ttu-id="dd503-127">現在の場所が C ドライブのルートである場合に `Get-Location` を実行すると、次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd503-127">If you run `Get-Location` while your current location is the root of the C drive, you see the following output:</span></span>

```
PS> Get-Location

Path
----
C:\
```

<span data-ttu-id="dd503-128">テキストの出力は情報の要約であり、`Get-Location` から返されたオブジェクトの完全な表現ではありません。</span><span class="sxs-lookup"><span data-stu-id="dd503-128">The text output is a summary of information, not a complete representation of the object returned by `Get-Location`.</span></span> <span data-ttu-id="dd503-129">出力の見出しは、画面の表示用にデータを書式設定する処理によって、追加されます。</span><span class="sxs-lookup"><span data-stu-id="dd503-129">The heading in the output is added by the process that formats the data for onscreen display.</span></span>

<span data-ttu-id="dd503-130">出力を `Get-Member` コマンドレットにパイプ処理するときに、`Get-Location` から返されたオブジェクトに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="dd503-130">When you pipe the output to the `Get-Member` cmdlet you get information about the object returned by `Get-Location`.</span></span>

```powershell
Get-Location | Get-Member
```

```Output
   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Equals       Method     bool Equals(System.Object obj)
GetHashCode  Method     int GetHashCode()
GetType      Method     type GetType()
ToString     Method     string ToString()
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   string Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {get;}
ProviderPath Property   string ProviderPath {get;}
```

<span data-ttu-id="dd503-131">`Get-Location` は、現在のパスとその他の情報を含む **PathInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="dd503-131">`Get-Location` returns a **PathInfo** object that contains the current path and other information.</span></span>
