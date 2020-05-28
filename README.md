---
ms.openlocfilehash: 0d91230aa063e58106b35a4ada1d577f316f8f27
ms.sourcegitcommit: c752ae8d0fa47eaaf3c5eae2a5a770f06c63921c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "83840993"
---
# <a name="microsoft-open-source-code-of-conduct"></a>Microsoft オープン ソース倫理規定

このプロジェクトは、「[Microsoft のオープン ソースの倫理規定](https://opensource.microsoft.com/codeofconduct/)」を採用しています。 詳細については[論理規定についてのよくある質問](https://opensource.microsoft.com/codeofconduct/faq/)をご覧ください。また、追加の質問やコメントがある場合は[opencode@microsoft.com](mailto:opencode@microsoft.com)にお問い合わせください。

[live-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=live
[staging-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=staging

## <a name="build-status"></a>ビルドの状態

|          ライブ ブランチ          |           ステージング ブランチ            |
| :---------------------------- | :---------------------------------- |
| [![live-badge][]][live-badge] | [![staging-badge][]][staging-badge] |

## <a name="powershell-documentation"></a>PowerShell ドキュメント

PowerShell-Docs リポジトリへようこそ。PowerShell-Docs は、公式の PowerShell ドキュメントが格納されている場所です。

## <a name="repository-structure"></a>リポジトリの構造

このリポジトリ内の次の各最上位フォルダーには、[Microsoft Docs](https://docs.microsoft.com/powershell) に公開されるドキュメント セットが含まれています。

- [/reference/](https://docs.microsoft.com/powershell/scripting/) は、バージョン 5.1、6.0、7.0 にわたる PowerShell の概念説明のトピックおよびモジュール リファレンス用です。 また、このコンテンツは、`Get-Help` コマンドレットによって取得されるヘルプ コンテンツのソースでもあります。
  - [docs-conceptual/](https://docs.microsoft.com/powershell) - このフォルダーには、概念説明のドキュメントと次のドキュメント セットが含まれています。
    - [developer/](https://docs.microsoft.com/powershell/scripting/developer/) は PowerShell SDK のドキュメントです (MSDN から移行)
    - [dsc/](https://docs.microsoft.com/powershell/scripting/dsc/) は Desired State Configuration 機能用です
    - [gallery/](https://docs.microsoft.com/powershell/scripting/gallery) は [PowerShell ギャラリー](https://www.powershellgallery.com/)用です
    - [jea/](https://docs.microsoft.com/powershell/scripting/learn/remoting/jea/overview) は Just Enough Administration 機能用です
    - [wmf](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview) には Windows Management Framework のリリース ノートが含まれています。これは、Windows の以前のバージョンに対して PowerShell の新しいバージョンを配布するために使用するパッケージです。

## <a name="contributing"></a>寄与

[pull request](https://help.github.com/articles/using-pull-requests/) を使用したこのリポジトリへの投稿は、_ステージング_ ブランチに積極的に組み込んでいます。
pull request を送信する前に、[投稿の使用許諾契約](https://cla.microsoft.com/)に署名して、コミュニティがあなたの投稿を自由に使用できるようにしてください。

投稿の詳細については、[共同作成者ガイド](https://docs.microsoft.com/powershell/scripting/community/contributing/overview)を参照してください。
共同作成者ガイドには、ドキュメント、お勧めのツール、スタイルや書式設定に関する要求を投稿する方法についての詳細情報が記載されています。 異なるバージョン間で一貫性のあるドキュメントを保つため、問題と Pull Request のテンプレートを使用してください。

## <a name="licenses"></a>ライセンス

このプロジェクトには、2 つのライセンス ファイルがあります。 MIT ライセンスは、このリポジトリに含まれるコードに適用されます。 Creative Commons ライセンスは、ドキュメントに適用されます。
