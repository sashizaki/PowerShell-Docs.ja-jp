---
ms.date: 01/25/2021
title: コマンドレットのトラブルシューティング
description: この記事では、PowerShell ギャラリーを使用してエラーのトラブルシューティングを行うための情報と手順を示します
ms.openlocfilehash: 8139147683b655b5f8532c3068387db6df12a98f
ms.sourcegitcommit: 0f003644684422e425a59b7361121e05ac772e15
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98771813"
---
# <a name="troubleshooting-cmdlets"></a><span data-ttu-id="5d135-103">コマンドレットのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5d135-103">Troubleshooting cmdlets</span></span>

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a><span data-ttu-id="5d135-104">"警告: パッケージ 'パッケージ名' をダウンロードできませんでした" の問題を解決する方法</span><span class="sxs-lookup"><span data-stu-id="5d135-104">How to resolve "WARNING: Package 'your package name' failed to download" issue</span></span>

<span data-ttu-id="5d135-105">一部のマシン上で `Install-Module` または `Update-Module` が失敗する場合があることがレポートされています。</span><span class="sxs-lookup"><span data-stu-id="5d135-105">It is reported that `Install-Module` or `Update-Module` sometimes fails on some machines.</span></span> <span data-ttu-id="5d135-106">調査の結果、ネットワーク接続の問題であることが判明しました。</span><span class="sxs-lookup"><span data-stu-id="5d135-106">Based on our investigation, it is something to do with the networking connection.</span></span> <span data-ttu-id="5d135-107">最近、パッケージのダウンロードが安定するように、NuGet プロバイダーを更新しました。</span><span class="sxs-lookup"><span data-stu-id="5d135-107">Recently we updated NuGet provider so that it can reliably download packages.</span></span> <span data-ttu-id="5d135-108">下の指示に従い、最新版の NuGet プロバイダーをインストールし、モジュールをインストールするか、更新できます。</span><span class="sxs-lookup"><span data-stu-id="5d135-108">You can follow the instructions below to install the latest build of NuGet provider and then install or update your module.</span></span> <span data-ttu-id="5d135-109">以下、'Azure' モジュールをサンプルとして使用します。</span><span class="sxs-lookup"><span data-stu-id="5d135-109">Let's use 'Azure' module as an example below.</span></span>

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

## <a name="required-network-endpoints"></a><span data-ttu-id="5d135-110">必要なネットワーク エンドポイント</span><span class="sxs-lookup"><span data-stu-id="5d135-110">Required network endpoints</span></span>

<span data-ttu-id="5d135-111">Install および Update コマンドレットを使用する場合、PowerShell ギャラリーによって使用されるネットワーク エンドポイントに接続するためのインターネット アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="5d135-111">The Install and Update cmdlets require internet access to connect to the network endpoints used by by the PowerShell Gallery.</span></span> <span data-ttu-id="5d135-112">お使いのネットワーク アクセス ポリシーで、次のエンドポイントへの接続が許可されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5d135-112">Ensure that your network access policies allow you to connect to the following endpoints.</span></span>

- <span data-ttu-id="5d135-113">`psg-prod-eastus.azureedge.net` - CDN ホスト名</span><span class="sxs-lookup"><span data-stu-id="5d135-113">`psg-prod-eastus.azureedge.net` - CDN hostname</span></span>
- <span data-ttu-id="5d135-114">`az818661.vo.msecnd.net` - CDN ホスト名</span><span class="sxs-lookup"><span data-stu-id="5d135-114">`az818661.vo.msecnd.net` - CDN hostname</span></span>
- <span data-ttu-id="5d135-115">`devopsgallerystorage.blob.core.windows.net` - ストレージ アカウントのホスト名</span><span class="sxs-lookup"><span data-stu-id="5d135-115">`devopsgallerystorage.blob.core.windows.net` - storage account hostname</span></span>
- <span data-ttu-id="5d135-116">`*.powershellgallery.com` - Web サイト</span><span class="sxs-lookup"><span data-stu-id="5d135-116">`*.powershellgallery.com` - website</span></span>
- <span data-ttu-id="5d135-117">`go.microsoft.com` - リダイレクト サービス</span><span class="sxs-lookup"><span data-stu-id="5d135-117">`go.microsoft.com` - redirection service</span></span>
- <span data-ttu-id="5d135-118">`onegetcdn.azureedge.net` - `PowerShellGet/PackageManagement` の NuGet プロバイダーのブートストラップ</span><span class="sxs-lookup"><span data-stu-id="5d135-118">`onegetcdn.azureedge.net` - bootstrap the NuGet Provider in `PowerShellGet/PackageManagement`</span></span>

> [!NOTE]
> <span data-ttu-id="5d135-119">PowerShell ギャラリー サービスが停止すると、PowerShell ギャラリーとやりとりするコマンドレットが予期しないエラーで失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="5d135-119">Cmdlets that interact with the PowerShell Gallery can fail with unexpected errors when there is an outage of the PowerShell Gallery services.</span></span> <span data-ttu-id="5d135-120">PowerShell ギャラリーの現在の状態を確認するには、GitHub の [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d135-120">To see the current status of the PowerShell Gallery, see the [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) page on GitHub.</span></span>
