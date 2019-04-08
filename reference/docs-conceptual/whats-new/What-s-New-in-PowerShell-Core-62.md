---
title: PowerShell Core 6.2 の新機能
description: PowerShell Core 6.2 でリリースされた新機能と変更
ms.date: 03/28/2019
ms.openlocfilehash: 2224d23a244175059a705c07001e8ad8d6ab3aa0
ms.sourcegitcommit: 8dd4394cf867005a8b9ef0bb74b744c964fbc332
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2019
ms.locfileid: "58750053"
---
# <a name="whats-new-in-powershell-core-62"></a><span data-ttu-id="cdbf9-103">PowerShell Core 6.2 の新機能</span><span class="sxs-lookup"><span data-stu-id="cdbf9-103">What's New in PowerShell Core 6.2</span></span>

<span data-ttu-id="cdbf9-104">以下では、PowerShell Core 6.2 で導入された主要な新機能と変更点からいくつか選んで説明します。</span><span class="sxs-lookup"><span data-stu-id="cdbf9-104">Below is a selection of some of the major new features and changes that have been introduced in PowerShell Core 6.2.</span></span>

<span data-ttu-id="cdbf9-105">PowerShell をさらに速く安定したものにする**数多くの** "細かな新機能と変更" (それに多数のバグ修正) が他にもあります。</span><span class="sxs-lookup"><span data-stu-id="cdbf9-105">There's also **tons** of "boring stuff" that make PowerShell faster and more stable (plus lots and lots of bug fixes)!</span></span>
<span data-ttu-id="cdbf9-106">すべての変更点のリストについては、[GitHub の変更ログ](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG.md)に関するページを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cdbf9-106">For a full list of changes, check out our [changelog on GitHub](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG.md).</span></span>

<span data-ttu-id="cdbf9-107">以下では何人かの名前を挙げていますが、このリリースを可能にしてくれた[コミュニティのすべての共同作成者](https://github.com/PowerShell/PowerShell/graphs/contributors)に感謝します。</span><span class="sxs-lookup"><span data-stu-id="cdbf9-107">And while we call out some names below, thank you to [all of the community contributors](https://github.com/PowerShell/PowerShell/graphs/contributors) that made this release possible.</span></span>

## <a name="engine-updates-and-fixes"></a><span data-ttu-id="cdbf9-108">エンジンの更新と修正</span><span class="sxs-lookup"><span data-stu-id="cdbf9-108">Engine Updates and Fixes</span></span>

- <span data-ttu-id="cdbf9-109">PowerShell リモート処理の有効/無効コマンドレットの警告メッセージを追加 ([#9203][])</span><span class="sxs-lookup"><span data-stu-id="cdbf9-109">Add PowerShell remoting enable/disable cmdlet warning messages ([#9203][])</span></span>
- <span data-ttu-id="cdbf9-110">`FormatTable` のリモート逆シリアル化の回帰を修正 ([#9116][])</span><span class="sxs-lookup"><span data-stu-id="cdbf9-110">Fix for `FormatTable` remote deserialization regression ([#9116][])</span></span>
- <span data-ttu-id="cdbf9-111">PowerShell に追加されたタスク ベースの `async` API を、直接 Task オブジェクトを返すように更新 ([#9079][])</span><span class="sxs-lookup"><span data-stu-id="cdbf9-111">Update the task-based `async` APIs added to PowerShell to return a Task object directly ([#9079][])</span></span>
- <span data-ttu-id="cdbf9-112">5 つの `InvokeAsync` オーバーロードと `StopAsync` を `PowerShell` 型に追加 ([#8056][]) (@KirkMunro に感謝)</span><span class="sxs-lookup"><span data-stu-id="cdbf9-112">Add 5 `InvokeAsync` overloads and `StopAsync` to the `PowerShell` type ([#8056][]) (Thanks @KirkMunro!)</span></span>

## <a name="general-cmdlet-updates-and-fixes"></a><span data-ttu-id="cdbf9-113">一般的なコマンドレットの更新と修正</span><span class="sxs-lookup"><span data-stu-id="cdbf9-113">General Cmdlet Updates and Fixes</span></span>

- <span data-ttu-id="cdbf9-114">プレーンテキストを格納することで非 Windows 向けに `SecureString` コマンドレットを有効化 ([#9199][])</span><span class="sxs-lookup"><span data-stu-id="cdbf9-114">Enable `SecureString` cmdlets for non-Windows by storing the plain text ([#9199][])</span></span>
- <span data-ttu-id="cdbf9-115">古いメッセージを `Send-MailMessage` に追加 ([#9178][])</span><span class="sxs-lookup"><span data-stu-id="cdbf9-115">Add Obsolete message to `Send-MailMessage` ([#9178][])</span></span>
- <span data-ttu-id="cdbf9-116">WinRM が存在しないときに `localhost` 上で動作するよう `Restart-Computer` を修正 ([#9160][])</span><span class="sxs-lookup"><span data-stu-id="cdbf9-116">Fix `Restart-Computer` to work on `localhost` when WinRM is not present ([#9160][])</span></span>
- <span data-ttu-id="cdbf9-117">PowerShell のホスト中に `Start-Job` に終了エラーをスローさせる ([#9128][])</span><span class="sxs-lookup"><span data-stu-id="cdbf9-117">Make `Start-Job` throw terminating error when PowerShell is being hosted ([#9128][])</span></span>
- <span data-ttu-id="cdbf9-118">`PowerShell.Native` の更新バージョンとテストのホスト ([#8983][])</span><span class="sxs-lookup"><span data-stu-id="cdbf9-118">Update version for `PowerShell.Native` and hosting tests ([#8983][])</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="cdbf9-119">破壊的変更</span><span class="sxs-lookup"><span data-stu-id="cdbf9-119">Breaking Changes</span></span>

<span data-ttu-id="cdbf9-120">修正 - Write-Output の NoEnumerate が Windows PowerShell と一貫性を保つように動作する ([#9069][]) (@vexx32 に感謝)</span><span class="sxs-lookup"><span data-stu-id="cdbf9-120">Fix -NoEnumerate behavior in Write-Output to be consistent with Windows PowerShell ([#9069][]) (Thanks @vexx32!)</span></span>

<!-- Link references -->
[#8056]: https://github.com/PowerShell/PowerShell/pull/8056
[#8983]: https://github.com/PowerShell/PowerShell/pull/8983
[#9069]: https://github.com/PowerShell/PowerShell/pull/9069
[#9079]: https://github.com/PowerShell/PowerShell/pull/9079
[#9116]: https://github.com/PowerShell/PowerShell/pull/9116
[#9128]: https://github.com/PowerShell/PowerShell/pull/9128
[#9160]: https://github.com/PowerShell/PowerShell/pull/9160
[#9178]: https://github.com/PowerShell/PowerShell/pull/9178
[#9199]: https://github.com/PowerShell/PowerShell/pull/9199
[#9203]: https://github.com/PowerShell/PowerShell/pull/9203
