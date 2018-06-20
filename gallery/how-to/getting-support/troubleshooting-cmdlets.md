---
ms.date: 06/12/2017
contributor: manikb
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: コマンドレットのトラブルシューティング
ms.openlocfilehash: e8890cb6bbe661b8524d83cabf91483acbde8095
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34219829"
---
# <a name="troubleshooting-cmdlets"></a><span data-ttu-id="b5017-103">コマンドレットのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b5017-103">Troubleshooting cmdlets</span></span>

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a><span data-ttu-id="b5017-104">"警告: パッケージ 'パッケージ名' をダウンロードできませんでした" 問題を解決する方法</span><span class="sxs-lookup"><span data-stu-id="b5017-104">How to resolve "WARNING: Package 'your package name' failed to download" issue?</span></span>

<span data-ttu-id="b5017-105">Install-Module または Update-Module が一部のコンピューターで時折失敗することが報告されています。</span><span class="sxs-lookup"><span data-stu-id="b5017-105">It is reported that Install-Module or Update-Module sometimes fails on some machines.</span></span>
<span data-ttu-id="b5017-106">調査の結果、ネットワーク接続の問題であることが判明しました。</span><span class="sxs-lookup"><span data-stu-id="b5017-106">Based on our investigation, it is something to do with the networking connection.</span></span>
<span data-ttu-id="b5017-107">最近、パッケージのダウンロードが安定するように、NuGet プロバイダーを更新しました。</span><span class="sxs-lookup"><span data-stu-id="b5017-107">Recently we updated NuGet provider so that it can reliably download packages.</span></span>
<span data-ttu-id="b5017-108">下の指示に従い、最新版の NuGet プロバイダーをインストールし、モジュールをインストールするか、更新できます。</span><span class="sxs-lookup"><span data-stu-id="b5017-108">You can follow the instructions below to install the latest build of NuGet provider and then install or update your module.</span></span>
<span data-ttu-id="b5017-109">以下、'Azure' モジュールをサンプルとして使用します。</span><span class="sxs-lookup"><span data-stu-id="b5017-109">Let's use 'Azure' module as an example below.</span></span>

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```