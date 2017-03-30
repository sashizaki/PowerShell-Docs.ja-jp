## <a name="microsoft-open-source-code-of-conduct"></a>Microsoft オープン ソース倫理規定

このプロジェクトは [Microsoft オープン ソース論理規定](https://opensource.microsoft.com/codeofconduct/)を採用しています。
詳細については[論理規定についてのよくある質問](https://opensource.microsoft.com/codeofconduct/faq/)をご覧ください。また、追加の質問やコメントがある場合は[opencode@microsoft.com](mailto:opencode@microsoft.com)にお問い合わせください。

[![ビルドの状態](https://ci.appveyor.com/api/projects/status/onshefxnc4g4pv87/branch/staging?svg=true)](https://ci.appveyor.com/project/PowerShell/powershell-docs/branch/staging)

# <a name="powershell-documentation"></a>PowerShell ドキュメント

PowerShell-Docs レポジトリへようこそ。PowerShell-Docs は、公式の Windows PowerShell ドキュメントが格納されている場所です。 

## <a name="repository-structure"></a>リポジトリの構造
このリポジトリ内の各フォルダーは [MSDN](https://msdn.microsoft.com/en-us/powershell) で公開されています。 フォルダーは次の PowerShell アセットに対応しています。
* [/dsc/](https://msdn.microsoft.com/en-us/powershell/dsc/) は Desired State Configuration の機能に関するフォルダーです
* [/gallery/](https://msdn.microsoft.com/powershell/gallery) は [PowerShell ギャラリー](https://www.powershellgallery.com/)に関するフォルダーです
* [/jea/](https://msdn.microsoft.com/powershell/jea/) は Just Enough Administration の機能に関するフォルダーです
* [/reference/](https://msdn.microsoft.com/powershell/reference/)はバージョン 2.0、3.0、4.0、5.0、5.1、6.0 などの異なるバージョン間での PowerShell モジュールの参照に関するフォルダーです
  * この内容は将来、`Get-Help` コマンドレットで取得するようになります
* [/scripting/](https://msdn.microsoft.com/en-us/powershell/scripting/) は一般的なPowerShell リファレンス コンテンツに関するフォルダーです
* [/wmf](https://msdn.microsoft.com/en-us/powershell/wmf/readme) には Windows Management Framework のリリース ノートと Windows の以前のバージョンに対して PowerShell の新しいバージョンを配布するために使用されるパッケージが含まれています。 



## <a name="contributing"></a>投稿

[pull 要求](https://help.github.com/articles/using-pull-requests/)を使用して、積極的に投稿をこのリポジトリの*ステージング* ブランチに結合しています。 コミュニティが投稿を自由に使用できるように、pull 要求を送信する前に[投稿の使用許諾契約に署名](https://cla.microsoft.com/)する必要があります。
投稿の詳細については、[投稿ガイド](CONTRIBUTING.md)を参照してください。
コントリビューションを作成する前にレビューを行うドラフトの[スタイル ガイド](./style.md)があります。
異なるバージョン間で一貫性のあるドキュメントを保つため、問題とプル要求のテンプレートを使用してください。 
