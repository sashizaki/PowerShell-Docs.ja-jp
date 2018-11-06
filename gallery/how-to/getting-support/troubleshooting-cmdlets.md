---
ms.date: 06/12/2017
contributor: manikb
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: コマンドレットのトラブルシューティング
ms.openlocfilehash: f5cd9c0cc23fef5891bf02c10b6541ab0f9d418a
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50002464"
---
# <a name="troubleshooting-cmdlets"></a><span data-ttu-id="dd75c-103">コマンドレットのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="dd75c-103">Troubleshooting cmdlets</span></span>

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a><span data-ttu-id="dd75c-104">"警告: パッケージ 'パッケージ名' をダウンロードできませんでした" 問題を解決する方法</span><span class="sxs-lookup"><span data-stu-id="dd75c-104">How to resolve "WARNING: Package 'your package name' failed to download" issue</span></span>

<span data-ttu-id="dd75c-105">一部のマシン上で `Install-Module` または `Update-Module` が失敗する場合があることがレポートされています。</span><span class="sxs-lookup"><span data-stu-id="dd75c-105">It is reported that `Install-Module` or `Update-Module` sometimes fails on some machines.</span></span>
<span data-ttu-id="dd75c-106">調査の結果、ネットワーク接続の問題であることが判明しました。</span><span class="sxs-lookup"><span data-stu-id="dd75c-106">Based on our investigation, it is something to do with the networking connection.</span></span>
<span data-ttu-id="dd75c-107">最近、パッケージのダウンロードが安定するように、NuGet プロバイダーを更新しました。</span><span class="sxs-lookup"><span data-stu-id="dd75c-107">Recently we updated NuGet provider so that it can reliably download packages.</span></span>
<span data-ttu-id="dd75c-108">下の指示に従い、最新版の NuGet プロバイダーをインストールし、モジュールをインストールするか、更新できます。</span><span class="sxs-lookup"><span data-stu-id="dd75c-108">You can follow the instructions below to install the latest build of NuGet provider and then install or update your module.</span></span>
<span data-ttu-id="dd75c-109">以下、'Azure' モジュールをサンプルとして使用します。</span><span class="sxs-lookup"><span data-stu-id="dd75c-109">Let's use 'Azure' module as an example below.</span></span>

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```
