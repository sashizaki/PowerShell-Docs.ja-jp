---
title: Docker での PowerShell の使用
description: Docker イメージにプレインストールされている PowerShell の使用方法。
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/03/2020
ms.openlocfilehash: b16a31a04ca863ab55c7c9718b1a1a973e61ee46
ms.sourcegitcommit: f55da6dea4b58a2cd13c7be7c24c07341f177b71
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "80646369"
---
# <a name="using-powershell-in-docker"></a><span data-ttu-id="f5124-103">Docker での PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="f5124-103">Using PowerShell in Docker</span></span>

<span data-ttu-id="f5124-104">PowerShell がプレインストールされた Docker イメージを発行します。</span><span class="sxs-lookup"><span data-stu-id="f5124-104">We publish Docker images with PowerShell preinstalled.</span></span> <span data-ttu-id="f5124-105">この記事では、Docker コンテナーで PowerShell の使用を開始する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="f5124-105">This article shows you how to get started using PowerShell in the Docker container.</span></span>

## <a name="finding-available-images"></a><span data-ttu-id="f5124-106">使用可能なイメージの検索</span><span class="sxs-lookup"><span data-stu-id="f5124-106">Finding available images</span></span>

<span data-ttu-id="f5124-107">リリースされたイメージには、Docker 17.05 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="f5124-107">The released images require Docker 17.05 or newer.</span></span> <span data-ttu-id="f5124-108">また、`sudo` またはローカル管理者権限なしで Docker を実行できる必要もあります。</span><span class="sxs-lookup"><span data-stu-id="f5124-108">It is also expected that you are able to run Docker without `sudo` or local administrative rights.</span></span> <span data-ttu-id="f5124-109">`docker` を正しくインストールするには、Docker の公式な[手順][install]に従ってください。</span><span class="sxs-lookup"><span data-stu-id="f5124-109">Please follow Docker's official [instructions][install] to install `docker` correctly.</span></span>

<span data-ttu-id="f5124-110">リリース コンテナーは、`centos:7` などの公式のディストリビューション イメージから派生し、依存関係をインストールしてから、最後に PowerShell パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f5124-110">The release containers derive from the official distribution image, such as `centos:7`, then install dependencies, and finally install the PowerShell package.</span></span>

<span data-ttu-id="f5124-111">これらのコンテナーは [hub.docker.com/r/microsoft/powershell][docker-release] にあります。</span><span class="sxs-lookup"><span data-stu-id="f5124-111">These containers live at [hub.docker.com/r/microsoft/powershell][docker-release].</span></span>

<span data-ttu-id="f5124-112">これらの Docker イメージの詳細については、GitHub の [PowerShell-Docker][PowerShell-Docker] リポジトリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5124-112">For more information about these Docker images, visit the [PowerShell-Docker][PowerShell-Docker] repository on GitHub.</span></span>

## <a name="using-powershell-in-a-container"></a><span data-ttu-id="f5124-113">コンテナーでの PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="f5124-113">Using PowerShell in a container</span></span>

<span data-ttu-id="f5124-114">次の手順は、イメージをダウンロードし、対話型 PowerShell セッションを開始するのに必要な Docker コマンドを示しています。</span><span class="sxs-lookup"><span data-stu-id="f5124-114">The following steps show the Docker commands required to download the image and start an interactive PowerShell session.</span></span>

```console
docker run -it mcr.microsoft.com/powershell
```

### <a name="remove-the-image-when-no-longer-needed"></a><span data-ttu-id="f5124-115">不要になったイメージを削除する</span><span class="sxs-lookup"><span data-stu-id="f5124-115">Remove the image when no longer needed</span></span>

<span data-ttu-id="f5124-116">次のコマンドは、不要になった Docker イメージを削除するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="f5124-116">The following command is used to delete the Docker image when you no longer need it.</span></span>

```console
docker rmi mcr.microsoft.com/powershell
```

## <a name="legal-and-licensing"></a><span data-ttu-id="f5124-117">法律およびライセンス</span><span class="sxs-lookup"><span data-stu-id="f5124-117">Legal and Licensing</span></span>

<span data-ttu-id="f5124-118">PowerShell は、[MIT ライセンス][] に基づき使用が許諾されています。</span><span class="sxs-lookup"><span data-stu-id="f5124-118">PowerShell is licensed under the [MIT license][].</span></span>

### <a name="windows-docker-file-and-image-licenses"></a><span data-ttu-id="f5124-119">Windows Docker ファイルとイメージのライセンス</span><span class="sxs-lookup"><span data-stu-id="f5124-119">Windows Docker File and Image Licenses</span></span>

<span data-ttu-id="f5124-120">Windows コンテナー用のコンテナー OS イメージを要求して使用することで、Docker Hub で利用可能な追加ライセンス条項を確認して理解し、同意することができます。</span><span class="sxs-lookup"><span data-stu-id="f5124-120">By requesting and using the Container OS Image for Windows containers, you acknowledge, understand, and consent to the Supplemental License Terms available on Docker hub:</span></span>

- <span data-ttu-id="f5124-121">[Window Server Core][Window Server Core]</span><span class="sxs-lookup"><span data-stu-id="f5124-121">[Window Server Core][Window Server Core]</span></span>
- <span data-ttu-id="f5124-122">[Nano Server][Nano Server]</span><span class="sxs-lookup"><span data-stu-id="f5124-122">[Nano Server][Nano Server]</span></span>

### <a name="telemetry"></a><span data-ttu-id="f5124-123">テレメトリ</span><span class="sxs-lookup"><span data-stu-id="f5124-123">Telemetry</span></span>

<span data-ttu-id="f5124-124">既定では、PowerShell は、個人を特定できる情報が含まれない限られたテレメトリを収集し、将来のバージョンの PowerShell 開発に利用します。</span><span class="sxs-lookup"><span data-stu-id="f5124-124">By default, PowerShell collects limited telemetry without personally identifiable information to help aid development of future versions of PowerShell.</span></span> <span data-ttu-id="f5124-125">テレメトリを送信しないようにするには、インストール先から PowerShell を起動する前に、`POWERSHELL_TELEMETRY_OPTOUT` という環境変数を作成して値を `1` に設定します。</span><span class="sxs-lookup"><span data-stu-id="f5124-125">To opt-out of sending telemetry, create an environment variable called `POWERSHELL_TELEMETRY_OPTOUT` set to a value of `1` before starting PowerShell from the installed location.</span></span> <span data-ttu-id="f5124-126">収集するテレメトリは、[Microsoft プライバシー ステートメント][privacy]に記載されています。</span><span class="sxs-lookup"><span data-stu-id="f5124-126">The telemetry we collect falls under the [Microsoft Privacy Statement][privacy].</span></span>

<!-- link references -->
[install]: https://docs.docker.com/engine/installation/
[docker-release]: https://hub.docker.com/r/microsoft/powershell/
[appinsights]: https://azure.microsoft.com/services/application-insights/
[MIT ライセンス]: https://github.com/PowerShell/PowerShell/tree/master/LICENSE.txt
[MIT license]: https://github.com/PowerShell/PowerShell/tree/master/LICENSE.txt
[PowerShell-Docker]: https://github.com/PowerShell/PowerShell-Docker
[Window Server Core]: https://hub.docker.com/r/microsoft/windowsservercore/
[Nano Server]: https://hub.docker.com/r/microsoft/nanoserver/
[privacy]: https://privacy.microsoft.com/privacystatement/
