---
ms.date: 06/12/2017
contributor: manikb
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: コマンドレットのトラブルシューティング
ms.openlocfilehash: d87c680472c2588efbfe8b3c4d6f2dbee6883a0c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72352112"
---
# <a name="troubleshooting-cmdlets"></a><span data-ttu-id="803f4-103">コマンドレットのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="803f4-103">Troubleshooting cmdlets</span></span>

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a><span data-ttu-id="803f4-104">"警告: パッケージ 'パッケージ名' をダウンロードできませんでした" の問題を解決する方法</span><span class="sxs-lookup"><span data-stu-id="803f4-104">How to resolve "WARNING: Package 'your package name' failed to download" issue</span></span>

<span data-ttu-id="803f4-105">一部のマシン上で `Install-Module` または `Update-Module` が失敗する場合があることがレポートされています。</span><span class="sxs-lookup"><span data-stu-id="803f4-105">It is reported that `Install-Module` or `Update-Module` sometimes fails on some machines.</span></span> <span data-ttu-id="803f4-106">調査の結果、ネットワーク接続の問題であることが判明しました。</span><span class="sxs-lookup"><span data-stu-id="803f4-106">Based on our investigation, it is something to do with the networking connection.</span></span> <span data-ttu-id="803f4-107">最近、パッケージのダウンロードが安定するように、NuGet プロバイダーを更新しました。</span><span class="sxs-lookup"><span data-stu-id="803f4-107">Recently we updated NuGet provider so that it can reliably download packages.</span></span> <span data-ttu-id="803f4-108">下の指示に従い、最新版の NuGet プロバイダーをインストールし、モジュールをインストールするか、更新できます。</span><span class="sxs-lookup"><span data-stu-id="803f4-108">You can follow the instructions below to install the latest build of NuGet provider and then install or update your module.</span></span> <span data-ttu-id="803f4-109">以下、'Azure' モジュールをサンプルとして使用します。</span><span class="sxs-lookup"><span data-stu-id="803f4-109">Let's use 'Azure' module as an example below.</span></span>

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

### <a name="required-network-endpoints"></a><span data-ttu-id="803f4-110">必要なネットワーク エンドポイント</span><span class="sxs-lookup"><span data-stu-id="803f4-110">Required network endpoints</span></span>

<span data-ttu-id="803f4-111">Install および Update コマンドレットを使用する場合、PowerShell ギャラリーによって使用されるネットワーク エンドポイントに接続するためのインターネット アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="803f4-111">The Install and Update cmdlets require internet access to connect to the network endpoints used by by the PowerShell Gallery.</span></span> <span data-ttu-id="803f4-112">お使いのネットワーク アクセス ポリシーで、次のエンドポイントへの接続が許可されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="803f4-112">Ensure that your network access policies allow you to connect to the following endpoints.</span></span>

- <span data-ttu-id="803f4-113">oneget.org</span><span class="sxs-lookup"><span data-stu-id="803f4-113">oneget.org</span></span>
- <span data-ttu-id="803f4-114">go.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="803f4-114">go.microsoft.com</span></span>
- <span data-ttu-id="803f4-115">az818661.vo.msecnd.net</span><span class="sxs-lookup"><span data-stu-id="803f4-115">az818661.vo.msecnd.net</span></span>
- <span data-ttu-id="803f4-116">[www.powershellgallery.com](www.powershellgallery.com)</span><span class="sxs-lookup"><span data-stu-id="803f4-116">www.powershellgallery.com</span></span>
- <span data-ttu-id="803f4-117">devopsgallerystorage.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="803f4-117">devopsgallerystorage.blob.core.windows.net</span></span>
