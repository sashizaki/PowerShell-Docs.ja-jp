# <a name="microsoft-open-source-code-of-conduct"></a>Microsoft オープン ソース倫理規定

このプロジェクトは [Microsoft オープン ソース論理規定](https://opensource.microsoft.com/codeofconduct/)を採用しています。
詳細については[論理規定についてのよくある質問](https://opensource.microsoft.com/codeofconduct/faq/)をご覧ください。また、追加の質問やコメントがある場合は[opencode@microsoft.com](mailto:opencode@microsoft.com)にお問い合わせください。

[![ビルドの状態](https://ci.appveyor.com/api/projects/status/onshefxnc4g4pv87/branch/staging?svg=true)](https://ci.appveyor.com/project/PowerShell/powershell-docs/branch/staging)

## <a name="powershell-documentation"></a>PowerShell ドキュメント

PowerShell-Docs リポジトリへようこそ。PowerShell-Docs は、公式の PowerShell ドキュメントが格納されている場所です。

## <a name="repository-structure"></a>リポジトリの構造

このリポジトリ内の次の各最上位フォルダーには、[Microsoft Docs](https://docs.microsoft.com/powershell) に公開されるドキュメント セットが含まれています。

- [/developer/](https://docs.microsoft.com/powershell/developer/) は、PowerShell SDK ドキュメントの今後のホームとなります
  - 現在、このコンテンツを MSDN から移行する処理を行っています
- [/dsc/](https://docs.microsoft.com/powershell/dsc/) は Desired State Configuration の機能に関するフォルダーです
- [/gallery/](https://docs.microsoft.com/powershell/gallery) は [PowerShell ギャラリー](https://www.powershellgallery.com/)に関するフォルダーです
- [/jea/](https://docs.microsoft.com/powershell/jea/) は Just Enough Administration の機能に関するフォルダーです
- [/reference/](https://docs.microsoft.com/powershell/scripting/) は、バージョン 3.0、4.0、5.0、5.1、6.0 全体での PowerShell の概念説明のトピックおよびモジュールの参照用のフォルダーです
  - また、このコンテンツは、`Get-Help` コマンドレットによって取得されたヘルプ コンテンツのソースともなります
- [/wmf](https://docs.microsoft.com/powershell/wmf/readme) には Windows Management Framework のリリース ノートと Windows の以前のバージョンに対して PowerShell の新しいバージョンを配布するために使用されるパッケージが含まれています。

## <a name="contributing"></a>投稿

[pull 要求](https://help.github.com/articles/using-pull-requests/)を使用して、積極的に投稿をこのリポジトリの*ステージング* ブランチに結合しています。
コミュニティが投稿を自由に使用できるように、pull 要求を送信する前に[投稿の使用許諾契約に署名](https://cla.microsoft.com/)する必要があります。

投稿の詳細については、[共同作成者ガイド](CONTRIBUTING.md)を参照してください。
共同作成者ガイドには、ドキュメント、お勧めのツール、スタイルや書式設定に関する要求を投稿する方法についての詳細情報が記載されています。
異なるバージョン間で一貫性のあるドキュメントを保つため、問題とプル要求のテンプレートを使用してください。

## <a name="licenses"></a>ライセンス

このプロジェクトには、2 つのライセンス ファイルがあります。
MIT ライセンスは、このリポジトリに含まれるコードに適用されます。
Creative Commons ライセンスは、ドキュメントに適用されます。