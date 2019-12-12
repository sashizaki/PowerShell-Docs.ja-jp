---
title: Windows PowerShell モジュールのヘルプを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2b58fa5-01bc-426c-a043-5c700d6578e9
caps.latest.revision: 16
ms.openlocfilehash: 443bf5f693d2ab161668de25a1097347826cb5c2
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72360561"
---
# <a name="writing-help-for-windows-powershell-modules"></a>Windows PowerShell モジュールのヘルプを記述する

Windows PowerShell モジュールには、モジュールに関するヘルプトピックや、コマンドレット、プロバイダー、関数、スクリプトなどのモジュールメンバーに関するヘルプトピックを含めることができます。 `Get-Help` コマンドレットは、他の Windows PowerShell 項目のヘルプを表示するのと同じ形式のモジュールヘルプトピックを表示し、ユーザーは標準の `Get-Help` コマンドを使用してヘルプトピックを取得します。

このドキュメントでは、モジュールのヘルプトピックの形式と適切な配置について説明し、モジュールのヘルプコンテンツに関するガイドラインを示します。

## <a name="types-of-module-help"></a>モジュールのヘルプの種類

モジュールには、次の種類のヘルプを含めることができます。

- **コマンドレットのヘルプを参照**してください。 モジュール内のコマンドレットについて説明するヘルプトピックは、コマンドヘルプスキーマを使用する XML ファイルです。

- **プロバイダーのヘルプ**。 モジュール内のプロバイダーについて説明するヘルプトピックは、プロバイダーヘルプスキーマを使用する XML ファイルです。

- **関数のヘルプ**。 モジュール内の関数について説明するヘルプトピックは、関数内のコマンドヘルプスキーマまたはコメントベースのヘルプトピックを使用する XML ファイルにすることも、スクリプトまたはスクリプトモジュールで使用することもできます。

- **スクリプトのヘルプ**。 モジュール内のスクリプトを記述するヘルプトピックは、スクリプトまたはスクリプトモジュールでコマンドヘルプスキーマまたはコメントベースのヘルプトピックを使用する XML ファイルにすることができます。

- **概念 ("About") のヘルプ**。 概念 ("about") ヘルプトピックを使用して、モジュールとそのメンバーを記述したり、メンバーを組み合わせてタスクを実行する方法を説明したりできます。 概念説明ヘルプトピックは、Unicode (UTF-8) エンコードを使用したテキストファイルです。 ファイル名には、about_MyModule などの `about_<name>.help.txt` 形式を使用する必要があります。 既定では、Windows PowerShell には、次の例のように、これらの概念に関するヘルプトピックが100以上含まれています。

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

## <a name="placement-of-module-help"></a>モジュールヘルプの配置

`Get-Help` コマンドレットは、モジュールディレクトリの言語固有のサブディレクトリにあるモジュールヘルプトピックファイルを検索します。

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
> この例では、 *\<ModulePath >* プレースホルダーは `PSModulePath` 環境変数内のいずれかのパス ($home \documents\modules、$pshome \ モジュール、ユーザーが指定したカスタムパスなど) を表します。

## <a name="getting-module-help"></a>モジュールのヘルプを取得する

ユーザーがモジュールをセッションにインポートすると、そのモジュールのヘルプトピックがモジュールと共にセッションにインポートされます。 モジュールマニフェストの FileList キーの値にヘルプトピックファイルを一覧表示することはできますが、ヘルプトピックは `Export-ModuleMember` コマンドレットの影響を受けません。

さまざまな言語でモジュールのヘルプトピックを提供できます。 `Get-Help` コマンドレットは、コントロールパネルの [地域と言語のオプション] 項目で、現在のユーザーに対して指定されている言語のモジュールヘルプトピックを自動的に表示します。 Windows Vista 以降のバージョンの Windows では、`Get-Help` は、Windows 用に設定された言語フォールバック標準に従って、モジュールディレクトリの言語固有のサブディレクトリにあるヘルプトピックを検索します。

Windows PowerShell 3.0 以降では、コマンドレットまたは関数に対して `Get-Help` コマンドを実行すると、モジュールの自動インポートがトリガーされます。 `Get-Help` コマンドレットは、モジュールのヘルプトピックの内容をすぐに表示します。

モジュールにヘルプトピックが含まれておらず、ユーザーのコンピューターのモジュールのコマンドに関するヘルプトピックがない場合、`Get-Help` には自動生成されたヘルプが表示されます。 自動生成されたヘルプには、コマンドの構文、パラメーター、および入力と出力の型が含まれていますが、説明は含まれていません。 自動生成されたヘルプには、`Update-Help` コマンドレットを使用して、インターネットまたはファイル共有からコマンドのヘルプをダウンロードするように指示するテキストが含まれています。 また、`Get-Help` コマンドレットの**online**パラメーターを使用して、ヘルプトピックのオンラインバージョンを取得することをお勧めします。

## <a name="supporting-updatable-help"></a>更新可能ヘルプのサポート

Windows powershell 3.0 以降のバージョンの Windows PowerShell では、モジュールの更新されたヘルプファイルをインターネットまたはローカルファイル共有からダウンロードしてインストールすることができます。 `Update-Help` と `Save-Help` のコマンドレットにより、管理の詳細がユーザーに表示されません。 ユーザーは `Update-Help` コマンドレットを実行した後、`Get-Help` コマンドレットを使用して、Windows PowerShell コマンドプロンプトでモジュールの最新のヘルプファイルを読み取ります。 ユーザーは、Windows または Windows PowerShell を再起動する必要はありません。

ファイアウォールの背後にあるユーザーやインターネットにアクセスできないユーザーも、更新可能なヘルプを使用できます。 インターネットアクセス権を持つ管理者は、`Save-Help` コマンドレットを使用して、最新のヘルプファイルをダウンロードしてファイル共有にインストールします。 次に、`Update-Help` コマンドレットの**Path**パラメーターを使用して、ファイル共有から最新のヘルプファイルを取得します。

モジュールの作成者は、モジュールにヘルプファイルを含めたり、更新可能なヘルプを使用してヘルプファイルを更新したり、モジュールからヘルプファイルを除外したり、更新可能なヘルプを使用してインストールしたり更新したりできます。

更新可能なヘルプの詳細については、「[更新可能なヘルプのサポート](./supporting-updatable-help.md)」を参照してください。

## <a name="supporting-online-help"></a>オンライン ヘルプのサポート

更新されたヘルプファイルをコンピューターにインストールできない、またはインストールしないユーザーは、多くの場合、オンラインバージョンのモジュールヘルプトピックに依存しています。 `Get-Help` コマンドレットの**online**パラメーターは、既定のインターネットブラウザーでユーザーのコマンドレットまたは高度な関数のヘルプトピックのオンラインバージョンを開きます。

`Get-Help` コマンドレットは、コマンドレットまたは関数**の "/" プロパティの値**を使用して、ヘルプトピックのオンラインバージョンを検索します。

Windows PowerShell 3.0 以降では、コマンドレットと関数のヘルプトピックのオンラインバージョンを検索するために、コマンドレットクラスまたはコマンドレット**バインド**属性の **"/" プロパティ**を定義することができます。 属性の値は、コマンドレットまたは関数のすべて**のプロパティの**値です。

詳細については、「[オンラインヘルプのサポート](./supporting-online-help.md)」を参照してください。

## <a name="see-also"></a>参照

[Windows PowerShell モジュールの作成](./writing-a-windows-powershell-module.md)

[更新可能なヘルプのサポート](./supporting-updatable-help.md)

[オンラインヘルプのサポート](./supporting-online-help.md)