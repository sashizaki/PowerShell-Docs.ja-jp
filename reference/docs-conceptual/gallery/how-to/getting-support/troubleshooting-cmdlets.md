---
ms.date: 12/01/2020
title: コマンドレットのトラブルシューティング
description: この記事では、PowerShell ギャラリーを使用してエラーのトラブルシューティングを行うための情報と手順を示します
ms.openlocfilehash: 980da8ea7b8a09513f33a9939d512c437b755d8d
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913320"
---
# <a name="troubleshooting-cmdlets"></a><span data-ttu-id="c30a3-103">コマンドレットのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c30a3-103">Troubleshooting cmdlets</span></span>

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a><span data-ttu-id="c30a3-104">"警告: パッケージ 'パッケージ名' をダウンロードできませんでした" の問題を解決する方法</span><span class="sxs-lookup"><span data-stu-id="c30a3-104">How to resolve "WARNING: Package 'your package name' failed to download" issue</span></span>

<span data-ttu-id="c30a3-105">一部のマシン上で `Install-Module` または `Update-Module` が失敗する場合があることがレポートされています。</span><span class="sxs-lookup"><span data-stu-id="c30a3-105">It is reported that `Install-Module` or `Update-Module` sometimes fails on some machines.</span></span> <span data-ttu-id="c30a3-106">調査の結果、ネットワーク接続の問題であることが判明しました。</span><span class="sxs-lookup"><span data-stu-id="c30a3-106">Based on our investigation, it is something to do with the networking connection.</span></span> <span data-ttu-id="c30a3-107">最近、パッケージのダウンロードが安定するように、NuGet プロバイダーを更新しました。</span><span class="sxs-lookup"><span data-stu-id="c30a3-107">Recently we updated NuGet provider so that it can reliably download packages.</span></span> <span data-ttu-id="c30a3-108">下の指示に従い、最新版の NuGet プロバイダーをインストールし、モジュールをインストールするか、更新できます。</span><span class="sxs-lookup"><span data-stu-id="c30a3-108">You can follow the instructions below to install the latest build of NuGet provider and then install or update your module.</span></span> <span data-ttu-id="c30a3-109">以下、'Azure' モジュールをサンプルとして使用します。</span><span class="sxs-lookup"><span data-stu-id="c30a3-109">Let's use 'Azure' module as an example below.</span></span>

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

## <a name="required-network-endpoints"></a><span data-ttu-id="c30a3-110">必要なネットワーク エンドポイント</span><span class="sxs-lookup"><span data-stu-id="c30a3-110">Required network endpoints</span></span>

<span data-ttu-id="c30a3-111">Install および Update コマンドレットを使用する場合、PowerShell ギャラリーによって使用されるネットワーク エンドポイントに接続するためのインターネット アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c30a3-111">The Install and Update cmdlets require internet access to connect to the network endpoints used by by the PowerShell Gallery.</span></span> <span data-ttu-id="c30a3-112">お使いのネットワーク アクセス ポリシーで、次のエンドポイントへの接続が許可されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c30a3-112">Ensure that your network access policies allow you to connect to the following endpoints.</span></span>

- <span data-ttu-id="c30a3-113">`psg-prod-eastus.azureedge.net` - CDN ホスト名</span><span class="sxs-lookup"><span data-stu-id="c30a3-113">`psg-prod-eastus.azureedge.net` - CDN hostname</span></span>
- <span data-ttu-id="c30a3-114">`az818661.vo.msecnd.net` - CDN ホスト名</span><span class="sxs-lookup"><span data-stu-id="c30a3-114">`az818661.vo.msecnd.net` - CDN hostname</span></span>
- <span data-ttu-id="c30a3-115">`devopsgallerystorage.blob.core.windows.net` - ストレージ アカウントのホスト名</span><span class="sxs-lookup"><span data-stu-id="c30a3-115">`devopsgallerystorage.blob.core.windows.net` - storage account hostname</span></span>
- <span data-ttu-id="c30a3-116">`*.powershellgallery.com` - Web サイト</span><span class="sxs-lookup"><span data-stu-id="c30a3-116">`*.powershellgallery.com` - website</span></span>
- <span data-ttu-id="c30a3-117">`go.microsoft.com` - リダイレクト サービス</span><span class="sxs-lookup"><span data-stu-id="c30a3-117">`go.microsoft.com` - redirection service</span></span>

> [!NOTE]
> <span data-ttu-id="c30a3-118">PowerShell ギャラリー サービスが停止すると、PowerShell ギャラリーとやりとりするコマンドレットが予期しないエラーで失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="c30a3-118">Cmdlets that interact with the PowerShell Gallery can fail with unexpected errors when there is an outage of the PowerShell Gallery services.</span></span> <span data-ttu-id="c30a3-119">PowerShell ギャラリーの現在の状態を確認するには、GitHub の [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c30a3-119">To see the current status of the PowerShell Gallery, see the [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) page on GitHub.</span></span>
