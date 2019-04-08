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
# <a name="whats-new-in-powershell-core-62"></a>PowerShell Core 6.2 の新機能

以下では、PowerShell Core 6.2 で導入された主要な新機能と変更点からいくつか選んで説明します。

PowerShell をさらに速く安定したものにする**数多くの** "細かな新機能と変更" (それに多数のバグ修正) が他にもあります。
すべての変更点のリストについては、[GitHub の変更ログ](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG.md)に関するページを確認してください。

以下では何人かの名前を挙げていますが、このリリースを可能にしてくれた[コミュニティのすべての共同作成者](https://github.com/PowerShell/PowerShell/graphs/contributors)に感謝します。

## <a name="engine-updates-and-fixes"></a>エンジンの更新と修正

- PowerShell リモート処理の有効/無効コマンドレットの警告メッセージを追加 ([#9203][])
- `FormatTable` のリモート逆シリアル化の回帰を修正 ([#9116][])
- PowerShell に追加されたタスク ベースの `async` API を、直接 Task オブジェクトを返すように更新 ([#9079][])
- 5 つの `InvokeAsync` オーバーロードと `StopAsync` を `PowerShell` 型に追加 ([#8056][]) (@KirkMunro に感謝)

## <a name="general-cmdlet-updates-and-fixes"></a>一般的なコマンドレットの更新と修正

- プレーンテキストを格納することで非 Windows 向けに `SecureString` コマンドレットを有効化 ([#9199][])
- 古いメッセージを `Send-MailMessage` に追加 ([#9178][])
- WinRM が存在しないときに `localhost` 上で動作するよう `Restart-Computer` を修正 ([#9160][])
- PowerShell のホスト中に `Start-Job` に終了エラーをスローさせる ([#9128][])
- `PowerShell.Native` の更新バージョンとテストのホスト ([#8983][])

## <a name="breaking-changes"></a>破壊的変更

修正 - Write-Output の NoEnumerate が Windows PowerShell と一貫性を保つように動作する ([#9069][]) (@vexx32 に感謝)

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
