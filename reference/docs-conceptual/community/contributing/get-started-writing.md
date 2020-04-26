---
title: PowerShell ドキュメントへの投稿を開始する
description: この記事では、PowerShell ドキュメントの共同作成者として作業を開始する方法の概要を説明します。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: fdf29feb75abb6592205aaf1726c07a60ce3a924
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81005518"
---
# <a name="get-started-contributing-to-powershell-documentation"></a>PowerShell ドキュメントへの投稿を開始する

この記事では、PowerShell ドキュメントの共同作成者として作業を開始する方法の概要を説明します。

## <a name="powershell-docs-structure"></a>PowerShell-Docs の構造

[PowerShell-Docs リポジトリ][psdocs]は、コンテンツの 2 つのグループに分かれています。 Git ブランチは、ドキュメントを公開する方法とタイミングを管理するために使用されます。

### <a name="reference-content"></a>リファレンス コンテンツ

リファレンス コンテンツは、PowerShell に付属するコマンドレットの PowerShell コマンドレット リファレンスです。
[リファレンス][ref]は、バージョン フォルダー (5.1、6、7.0、7.1) にまとめられています。 このコンテンツには、PowerShell に付属するモジュールのコマンドレット リファレンスだけが含まれています。 また、このコンテンツは、`Get-Help` コマンドレットによって表示されるヘルプ情報の作成にも使用されます。

> [!NOTE]
> リファレンス コンテンツの目次 (TOC) は、公開システムによって自動生成されます。 TOC を更新する必要はありません。

### <a name="conceptual-content"></a>概念コンテンツ

概念ドキュメントには、次のコンテンツが含まれます。

- リリース ノート
- セットアップ手順
- サンプル スクリプトとハウツー記事
- DSC ドキュメント
- SDK ドキュメント

[概念ドキュメント][conceptual]は、バージョン別に整理されていません。 PowerShell のすべてのバージョンのすべての記事が表示されます。 チームは、バージョン固有の記事の作成に取り組んでいます。 その機能がドキュメントで利用可能になったら、このガイドが適切な情報で更新されます。

> [!NOTE]
> 概念記事が追加、削除、または名前変更されるたびに、TOC を更新し、プル要求に含める必要があります。

## <a name="using-git-branches"></a>Git ブランチの使用

PowerShell-Docs の既定のブランチは `staging` ブランチです。 作業ブランチで行われた変更は、`staging` ブランチにマージされてから、公開されます。 週に 1 回程度、`staging` ブランチは `live` ブランチにマージされます。 `live` ブランチには、docs.microsoft.com に公開されているコンテンツが含まれています。 `live` ブランチで直接変更を加えないでください。

PowerShell のリリースされていないバージョンにのみ適用されるドキュメントの変更を送信する場合は、そのバージョンの release ブランチがあるかどうかを確認します。 将来の特定のバージョンに適用されるすべての変更は、release ブランチをターゲットにする必要があります。 release ブランチの名前のパターンは、`release-<version>` です。

変更を開始する前に、PowerShell-Docs リポジトリのローカル コピーに作業ブランチを作成します。 これは、[フォークのクローン][fork]である必要があります。 作業ブランチを作成する前に、ローカル リポジトリを必ず同期してください。 作業ブランチは、`staging` または `release` ブランチの最新のコピーから作成する必要があります。

共同作成者ガイドの「[変更を加える][making-changes]」のプロセスに従って、送信する変更を加えます。

### <a name="creating-new-articles"></a>新しい記事の作成

投稿する新しいドキュメントの GitHub イシューを作成する必要があります。 既存のイシューを調べて、作業が重複していないことを確認します。 他のユーザーに割り当てられているイシューは "進行中" と見なされます。 イシューで共同作業を行う場合は、そのイシューに割り当てられているユーザーに連絡します。

PowerShell [RFC プロセス][rfc]と同様に、コンテンツを作成する前にイシューを作成すると、PowerShell-Docs チームによって却下されたものに多くの時間と労力を費やすことがなくなります。 また、コンテンツの範囲や PowerShell ドキュメント内での適切な場所について、チームが共同作成者と話し合うことも可能になります。

### <a name="updating-existing-articles"></a>既存の記事の更新

該当する場合、コマンドレット リファレンス記事は PowerShell のすべてのバージョンで複製されます。 コマンドレット リファレンスまたは `About_` 記事に関するイシューを報告する場合は、そのイシューの影響を受けるバージョンを指定する必要があります。 GitHub のイシュー テンプレートには、バージョンのチェックリストが含まれています。 チェックボックスを使用して、影響を受けるコンテンツのバージョンを指定します。 コンテンツの複数のバージョンに影響するイシューで記事の変更を送信する場合、ファイルの各バージョンに適切な変更を適用する必要があります。

## <a name="next-steps"></a>次のステップ

[プル要求を送信する方法](pull-requests.md)を確認します。

<!--link refs-->
[conceptual]: https://github.com/MicrosoftDocs/PowerShell-Docs/tree/staging/reference/docs-conceptual
[fork]: /contribute/get-started-setup-local#fork-the-repository
[making-changes]: /contribute/how-to-write-workflows-major#making-your-changes
[psdocs]: https://github.com/MicrosoftDocs/PowerShell-Docs
[ref]: https://github.com/MicrosoftDocs/PowerShell-Docs/tree/staging/reference
[rfc]: https://github.com/PowerShell/powershell-rfc/blob/master/RFC0000-RFC-Process.md