---
title: PowerShell モジュールのヘルプの作成
ms.date: 04/10/2020
ms.openlocfilehash: 496b7e6cadff4d2db15b6452e9d38efcdf1739ec
ms.sourcegitcommit: 8f55c0157280afa4598fe385a706faf330e723a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2020
ms.locfileid: "81219661"
---
# <a name="writing-help-for-powershell-modules"></a>PowerShell モジュールのヘルプの作成

PowerShell モジュールには、モジュールに関するヘルプトピックや、コマンドレット、プロバイダー、関数、スクリプトなどのモジュールメンバーに関するヘルプトピックを含めることができます。 コマンド`Get-Help`レットは、他の PowerShell 項目のヘルプを表示するのと同じ形式のモジュールヘルプトピックを表示し`Get-Help` 、ユーザーは標準のコマンドを使用してヘルプトピックを取得します。

このドキュメントでは、モジュールのヘルプトピックの形式と適切な配置について説明し、モジュールのヘルプコンテンツに関するガイドラインを示します。

## <a name="types-of-module-help"></a>モジュールのヘルプの種類

モジュールには、次の種類のヘルプを含めることができます。

- **コマンドレットのヘルプを参照**してください。 モジュール内のコマンドレットについて説明するヘルプトピックは、コマンドヘルプスキーマを使用する XML ファイルです。

- **プロバイダーのヘルプ**。 モジュール内のプロバイダーについて説明するヘルプトピックは、プロバイダーヘルプスキーマを使用する XML ファイルです。

- **関数のヘルプ**。 モジュール内の関数について説明するヘルプトピックは、関数内のコマンドヘルプスキーマまたはコメントベースのヘルプトピックを使用する XML ファイルにすることも、スクリプトまたはスクリプトモジュールで使用することもできます。

- **スクリプトのヘルプ**。 モジュール内のスクリプトを記述するヘルプトピックは、スクリプトまたはスクリプトモジュールでコマンドヘルプスキーマまたはコメントベースのヘルプトピックを使用する XML ファイルにすることができます。

- **概念 ("About") のヘルプ**。 概念 ("about") ヘルプトピックを使用して、モジュールとそのメンバーを記述したり、メンバーを組み合わせてタスクを実行する方法を説明したりできます。
  概念説明ヘルプトピックは、Unicode (UTF-8) エンコードを使用したテキストファイルです。 ファイル名には、の`about_<name>.help.txt`ような形式を`about_MyModule.help.txt`使用する必要があります。 既定では、PowerShell には、次の例のように、これらの概念に関するヘルプトピックが100以上含まれています。

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
      Text-only references for further reading. Hyperlinks cannot work in the PowerShell console.

  ```

すべてのスキーマファイルは、 `$PSHOME\Schemas\PSMaml`フォルダーにあります。

## <a name="placement-of-module-help"></a>モジュールヘルプの配置

この`Get-Help`コマンドレットは、モジュールディレクトリの言語固有のサブディレクトリにあるモジュールヘルプトピックファイルを検索します。

たとえば、次のディレクトリ構造の図は、SampleModule モジュールのヘルプトピックの場所を示しています。

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
> この例では、 `<ModulePath>`プレースホルダーは`$HOME\Documents\Modules`、、 `$PSHOME\Modules`、またはユーザー `PSModulePath`が指定するカスタムパスなど、環境変数内のパスの1つを表します。

## <a name="getting-module-help"></a>モジュールのヘルプを取得する

ユーザーがモジュールをセッションにインポートすると、そのモジュールのヘルプトピックがモジュールと共にセッションにインポートされます。 モジュールマニフェストの FileList キーの値にヘルプトピックファイルを一覧表示することはできますが、ヘルプトピックはコマンドレットの`Export-ModuleMember`影響を受けません。

さまざまな言語でモジュールのヘルプトピックを提供できます。 この`Get-Help`コマンドレットは、コントロールパネルの [地域と言語のオプション] 項目で、現在のユーザーに対して指定されている言語のモジュールヘルプトピックを自動的に表示します。 Windows Vista 以降のバージョンの Windows では`Get-Help` 、は、windows 用に設定された言語フォールバック標準に従って、モジュールディレクトリの言語固有のサブディレクトリにあるヘルプトピックを検索します。

PowerShell 3.0 以降では、コマンド`Get-Help`レットまたは関数に対してコマンドを実行すると、モジュールの自動インポートがトリガーされます。 この`Get-Help`コマンドレットは、モジュール内のヘルプトピックの内容をすぐに表示します。

モジュールにヘルプトピックが含まれておらず、ユーザーのコンピューターのモジュール内のコマンドに関するヘルプトピックがない場合`Get-Help`は、自動生成されたヘルプを表示します。 自動生成されたヘルプには、コマンドの構文、パラメーター、および入力と出力の型が含まれていますが、説明は含まれていません。 自動生成されたヘルプには、コマンド`Update-Help`レットを使用して、インターネットまたはファイル共有からコマンドのヘルプをダウンロードするように指示するテキストが含まれています。 また、 `Get-Help`コマンドレットの**online**パラメーターを使用して、ヘルプトピックのオンラインバージョンを取得することをお勧めします。

## <a name="supporting-updatable-help"></a>更新可能なヘルプのサポート

Powershell 3.0 およびそれ以降のバージョンの PowerShell を使用するユーザーは、モジュールの更新されたヘルプファイルをインターネットまたはローカルファイル共有からダウンロードしてインストールできます。 コマンド`Update-Help`レット`Save-Help`およびコマンドレットは、ユーザーからの管理の詳細を非表示にします。 ユーザーは`Update-Help`コマンドレットを実行し、 `Get-Help`コマンドレットを使用して、PowerShell コマンドプロンプトでモジュールの最新のヘルプファイルを読み取ります。
ユーザーは、Windows または PowerShell を再起動する必要はありません。

ファイアウォールの背後にあるユーザーやインターネットにアクセスできないユーザーも、更新可能なヘルプを使用できます。
インターネットアクセスが可能な管理`Save-Help`者は、コマンドレットを使用して、最新のヘルプファイルをダウンロードしてファイル共有にインストールします。 次に、 `Update-Help`コマンドレットの**Path**パラメーターを使用して、ファイル共有から最新のヘルプファイルを取得します。

モジュールの作成者は、モジュールにヘルプファイルを含めたり、更新可能なヘルプを使用してヘルプファイルを更新したり、モジュールからヘルプファイルを除外したり、更新可能なヘルプを使用してインストールしたり更新したりできます。

更新可能なヘルプの詳細については、「[更新可能なヘルプのサポート](./supporting-updatable-help.md)」を参照してください。

## <a name="supporting-online-help"></a>オンライン ヘルプのサポート

更新されたヘルプファイルをコンピューターにインストールできない、またはインストールしないユーザーは、多くの場合、オンラインバージョンのモジュールヘルプトピックに依存しています。 コマンドレットの Online パラメーターは、既定のインターネットブラウザーでユーザーのコマンドレットまたは高度な関数のヘルプトピックを開きます。 **Online** `Get-Help`

コマンド`Get-Help`レットでは、コマンドレットまたは関数**の "/" プロパティの値**を使用して、ヘルプトピックのオンラインバージョンを検索します。

PowerShell 3.0 以降では、コマンドレットと関数のヘルプトピックのオンラインバージョンを検索するために、コマンドレットクラスまたはコマンドレット**バインド**属性の **"/" プロパティ**を定義することができます。 属性の値は、コマンドレットまたは関数のすべて**のプロパティの**値です。

詳細については、「[オンラインヘルプのサポート](./supporting-online-help.md)」を参照してください。

## <a name="see-also"></a>関連項目

[PowerShell モジュールの作成](./writing-a-windows-powershell-module.md)

[更新可能なヘルプのサポート](./supporting-updatable-help.md)

[オンライン ヘルプのサポート](./supporting-online-help.md)
