---
title: Windows PowerShell モジュールのヘルプの記述 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2b58fa5-01bc-426c-a043-5c700d6578e9
caps.latest.revision: 16
ms.openlocfilehash: 443bf5f693d2ab161668de25a1097347826cb5c2
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854068"
---
# <a name="writing-help-for-windows-powershell-modules"></a>Windows PowerShell モジュールのヘルプを記述する

Windows PowerShell モジュールには、モジュールとコマンドレット、プロバイダー、関数およびスクリプトなど、モジュール メンバーについてのヘルプ トピックを含めることができます。 `Get-Help` 、他の Windows PowerShell 項目のヘルプが表示され、ユーザーが標準を使用、コマンドレットに同じ形式でモジュールのヘルプ トピックが表示されます`Get-Help`ヘルプ トピックを取得するコマンド。

このドキュメントは、形式とモジュールのヘルプ トピックの正しい配置について説明し、モジュールのヘルプ コンテンツに関するガイドラインが推奨されています。

## <a name="types-of-module-help"></a>種類のモジュールのヘルプ

モジュールは、次の種類のヘルプを含めることができます。

- **コマンドレットのヘルプ**します。 モジュールのコマンドレットを説明するヘルプ トピックは、コマンドを使用する XML ファイルのスキーマのヘルプ

- **プロバイダーのヘルプ**します。 モジュール内のプロバイダーについて説明するヘルプ トピックは、プロバイダーを使用する XML ファイルがスキーマを支援します。

- **関数のヘルプ**します。 モジュールの関数を説明するヘルプ トピックは、コマンドを使用する XML ファイルのスキーマまたは関数、または、スクリプトまたはスクリプト モジュール内のヘルプ トピックのコメント ベースのヘルプ

- **スクリプトのヘルプ**します。 モジュール内のスクリプトを説明するヘルプ トピックでは、コマンドを使用する XML ファイルのスキーマまたはスクリプトまたはスクリプト モジュールのヘルプ トピックのコメント ベースのヘルプを指定できます。

- **(「About」) ヘルプ概念**します。 モジュールとそのメンバーについて説明し、タスクを実行するメンバーを組み合わせて使用する方法について説明に (「about」) ヘルプ トピックの概念を使用できます。 します 概念説明ヘルプ トピックは、Unicode (utf-8) エンコーディングを持つテキスト ファイルです。 ファイル名を使用する必要があります、 `about_<name>.help.txt` about_MyModule.help.txt などの形式。 既定では、Windows PowerShell にはこれらの概念に関するヘルプ トピック、100 を超えると、次の例のように書式設定されます。

  ```
  TOPIC
      about_<subject or module name>

  SHORT DESCRIPTION
      A short, one-line description of the topic contents.

  LONG DESCRIPTION
      A detailed, full description of the subject or purpose of the module.

  EXAMPLES
      Examples of how to use the module or how the subject feature works in practice.

  KEYWORDS
      Terms or titles on which you might expect your users to search for the information in this topic.

  SEE ALSO
      Text-only references for further reading. Hyperlinks cannot work in the Windows PowerShell console.

  ```

## <a name="placement-of-module-help"></a>モジュールのヘルプの配置

`Get-Help`コマンドレットは、モジュール ディレクトリの言語固有のサブディレクトリでモジュールのヘルプ トピック ファイルを探します。

たとえば、次のディレクトリ構造の図は、SampleModule モジュールのヘルプ トピックの場所を示します。

```
<ModulePath>
         \SampleModule
               \<en-US>
                     \about_SampleModule.help.txt
                     \SampleModule.dll-help.xml
                     \SampleNestedModule.dll-help.xml
               \<fr-FR>
                     \about_SampleModule.help.txt
                     \SampleModule.dll-help.xml
                     \SampleNestedModule.dll-help.xml

```

> [!NOTE]
> この例で、  *\<ModulePath >* パスのいずれかを表すプレース ホルダー、 `PSModulePath` $home\Documents\Modules や $pshome \modules、ユーザーが指定したカスタム パスなどの環境変数。

## <a name="getting-module-help"></a>モジュールのヘルプの取得

ユーザーがセッションにモジュールをインポート、ときに、そのモジュールのヘルプ トピックは、モジュールとのセッションにインポートされます。 モジュール マニフェストに FileList キーの値でヘルプ トピック ファイルを一覧表示できますが、ヘルプ トピックの影響を受けない、`Export-ModuleMember`コマンドレット。

異なる言語でモジュールのヘルプ トピックを行うことができます。 `Get-Help`コマンドレットは、コントロール パネルの 地域と言語のオプション項目の現在のユーザーに対して指定されている言語でのモジュールのヘルプ トピックを自動的に表示されます。 Windows Vista および以降のバージョンの Windows、 `Get-Help` Windows 用に確立された言語フォールバック標準に従って、モジュール ディレクトリの言語固有のサブディレクトリにヘルプ トピックを検索します。

実行している Windows PowerShell 3.0 以降では、`Get-Help`コマンドレットまたは関数のコマンドは、モジュールの自動インポートをトリガーします。 `Get-Help`コマンドレットは、モジュール内のヘルプ トピックの内容をすぐに表示します。

モジュールにヘルプ トピックが含まれていないと、ユーザーのコンピューターには、モジュール内のコマンドのヘルプ トピックがない場合`Get-Help`自動生成されたヘルプを表示します。 自動生成されたヘルプは、コマンド構文、パラメーター、および入力と出力の型が含まれていますが、任意の説明には含まれません。 自動生成されたヘルプには使用しようとするユーザーを誘導するテキストが含まれています、`Update-Help`にインターネットまたはファイル共有から、コマンドのヘルプをダウンロードするコマンドレットです。 使用することをお勧めすることも、**オンライン**のパラメーター、`Get-Help`コマンドレット ヘルプ トピックのオンライン バージョンを取得します。

## <a name="supporting-updatable-help"></a>更新可能ヘルプのサポート

Windows PowerShell 3.0 のユーザーと以降のバージョンの Windows PowerShell は、ダウンロードして、モジュールの更新されたヘルプ ファイルをインターネットまたはローカルのファイル共有からインストールします。 `Update-Help`と`Save-Help`コマンドレットは、ユーザーからの管理の詳細を非表示にします。 ユーザーが実行、`Update-Help`コマンドレットしを使用して、`Get-Help`コマンドレットを Windows PowerShell コマンド プロンプトで、モジュールの最新のヘルプ ファイルを読み取る。 ユーザーは、Windows または Windows PowerShell を再起動する必要はありません。

ファイアウォールとインターネットへのアクセスなしの背後にあるユーザーも使用できます、更新可能なヘルプします。 インターネットと管理者のアクセスの使用、`Save-Help`コマンドレットをダウンロードしてファイル共有に最新のヘルプ ファイルをインストールします。 次に、ユーザーが使用して、**パス**のパラメーター、`Update-Help`ファイル共有から最新のヘルプ ファイルを取得するコマンドレットです。

モジュールの作成者は、モジュールのヘルプ ファイルを含めるし、更新可能なヘルプを使用して、ヘルプ ファイルを更新またはモジュールからヘルプ ファイルを省略し、インストールして、それらを更新する更新可能なヘルプを使用、します。

更新可能なヘルプについては、[更新可能なヘルプをサポートしている](./supporting-updatable-help.md)を参照してください。

## <a name="supporting-online-help"></a>オンライン ヘルプのサポート

インストールしないことはできません、またはユーザーには、自分のコンピューター上のファイルは、多くの場合、モジュールのヘルプ トピックのオンライン バージョンに依存のヘルプが更新されます。 **オンライン**のパラメーター、`Get-Help`コマンドレットは、既定のインターネット ブラウザーでコマンドレットまたはユーザーの高度な関数のヘルプ トピックのオンライン バージョンを開きます。

`Get-Help`コマンドレットの値を使用して、 **HelpUri**コマンドレットまたは関数には、ヘルプ トピックのオンライン バージョンの検索のプロパティ。

Windows PowerShell 3.0 以降で、コマンドレット クラスで HelpUri 属性を定義することで、コマンドレットと関数のヘルプ トピックのオンライン バージョンを検索するユーザーを支援することができます、または**HelpUri**のプロパティ、 **CmdletBinding**属性。 属性の値は、の値、 **HelpUri**コマンドレットまたは関数のプロパティ。

詳細については、[オンライン ヘルプのサポート](./supporting-online-help.md)を参照してください。

## <a name="see-also"></a>参照

[Windows PowerShell モジュールの記述](./writing-a-windows-powershell-module.md)

[更新可能なヘルプのサポート](./supporting-updatable-help.md)

[オンライン ヘルプのサポート](./supporting-online-help.md)