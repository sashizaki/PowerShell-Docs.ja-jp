---
title: イシューを管理する方法
description: この記事では、PowerShell-Docs チームがプル要求を管理する方法について説明します。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: cd7aba83d42a6a2eba1ce73910fdd34096342c21
ms.sourcegitcommit: 18d832858a7b8ea094763afa753e0f48f01372e7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2020
ms.locfileid: "79060277"
---
# <a name="how-we-manage-issues"></a>イシューを管理する方法

この記事では、PowerShell-Docs リポジトリでイシューを管理する方法について説明します。 この記事は、PowerShell-Docs チームのメンバーの作業を支援することを目的としています。 一般の共同作成者に対してプロセスを透明化するために、ここで公開されています。

## <a name="sources-of-issues"></a>イシューのソース

- コミュニティの共同作成者
- 内部の共同作成者
- ソーシャル メディア チャネルからのコメントの転記
- ドキュメント フィードバック フォームによるフィードバック

## <a name="response-time-targets"></a>目標対応時間

- トリアージ - 5 営業日
- 修正または変更 - 具体的な目標なし - ベスト エフォートのみ

### <a name="labeling--milestones"></a>ラベル付けとマイルストーン

#### <a name="label-types"></a>ラベルの種類

|Prefix  | 説明                                                         |
|------- | --------------------------------------------------------------------|
|領域    | イシューを議論する、PowerShell またはドキュメントの部分を示すために使用します。<br>機能の所有者が機能に関するイシューを見つけるのに役立ちます。|
|Pri     | イシューの優先度を示すために使用します。 値の範囲は 0 から 4 です。        |
|問題   | イシューのフィードバックの種類を分類するために使用します。                     |
|確認  | チームがさらにレビューする必要があるイシューに使用します。              |
|Status  | 作業項目の状態を示すために使用します。                        |
|待機中 | チームが何かを待機していることを示すために使用します。                   |

#### <a name="milestones"></a>Milestones

イシューと PR は、適切なマイルストーンでタグ付けする必要があります。 イシューが特定のバージョンを対象としていない場合、マイルストーンは使用されません。 PowerShell コード ベースにまだマージされていない変更に関するドキュメント PR のイシューは、**Future** マイルストーンに割り当てる必要があります。 コードの変更がマージされたら、マイルストーンを適切なバージョンに変更します。

|    マイルストーン     |                    説明                     |
| ---------------- | -------------------------------------------------- |
| 6.x              | PowerShell 6.0 から 6.2.x に関連する作業項目 |
| 7.0.0            | PowerShell 7.0 に関連する作業項目               |
| 7.1.0            | PowerShell 7.1 に関連する作業項目               |
| 予定           | 将来のバージョンの PowerShell の作業項目          |
| PSReadline-vNext | 将来のバージョンの PSReadline の作業項目          |

## <a name="triage-process"></a>トリアージ プロセス

PowerShell ドキュメント チームは、週に 1 回集まって、前回の会議以降に追加されたイシューについて話し合います。 ラベルが割り当てられたとき、または所有者が割り当てられたときに、イシューはトリアージされたと見なされます。 PowerShell ドキュメント チームのメンバーには、イシューを毎日レビューし、新たに報告されたイシューをトリアージすることが推奨されます。 必要に応じて、週 1 回のトリアージ会議を利用して、新しいイシューについてさらに詳しく話し合うこともできます。

### <a name="misplaced-product-feedback"></a>間違って送られた製品フィードバック

- その顧客に対して、製品フィードバックであることを示すコメントを入力し、適切なフィードバック チャネルへのリンクを提供します。
- 省略可能:イシューを適切な製品フィードバックの場所にコピーし、コピーした項目へのリンクを追加して、イシューを閉じます。 イシューを UserVoice にコピーしないでください。

  | ドキュメント セット    | 製品フィードバックの URL                                         |
  | --------- | ------------------------------------------------------------ |
  | developer | https://github.com/PowerShell/PowerShell/issues/new/choose   |
  | dsc       | https://windowsserver.uservoice.com/forums/301869-powershell |
  | ギャラリー   | https://github.com/powershell/powershellgallery/issues/new   |
  | jea       | https://github.com/powershell/jea/issues/new                 |
  | reference | https://github.com/PowerShell/PowerShell/issues/new/choose   |
  | wmf       | https://windowsserver.uservoice.com/forums/301869-powershell |

### <a name="support-requests"></a>サポート要求

- サポートに関する質問が単純な場合は、質問に丁寧に答えてイシューを閉じます。
- 質問が複雑な場合や、送信者からさらに多くの質問が返ってきた場合は、フォーラムおよびサポート チャネルにリダイレクトします。 フォーラムにリダイレクトする際の推奨されるテキストは次のとおりです。

    > これは、この種の質問に適したフォーラムではありません。 コミュニティ サポート フォーラムで質問を投稿してください。 コミュニティ フォーラムの一覧については、 https://docs.microsoft.com/powershell/scripting/community/community-support をご覧ください。

### <a name="code-of-conduct-violations"></a>行動規範違反

- 必要に応じて、イシューを編集し、不快感を与えるコンテンツを削除します。
- そのイシューがスパムであることを示すコメントを入力し、イシューを閉じ、それ以上コメントできないようにロックします。
- これが発生するたびに、毎週のトリアージで話し合って、さらなる措置 (GitHub または Microsoft 法務部への報告) の必要性を判断する必要があります。
