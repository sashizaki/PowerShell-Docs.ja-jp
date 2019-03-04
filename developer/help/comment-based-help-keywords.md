---
title: コメント ベースのヘルプ キーワード |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab90ec96-77f5-42e3-9c7e-2f4156ec207f
caps.latest.revision: 6
ms.openlocfilehash: dbb6f7c4cbefeaaaec0747511f50192bcf08c20c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862658"
---
# <a name="comment-based-help-keywords"></a>コメント ベースのヘルプのキーワード

このトピックでは、コメント ベースのヘルプのキーワードの一覧です。

## <a name="keywords-in-comment-based-help"></a>コメント ベースのヘルプのキーワード

有効なコメント ベースのヘルプ キーワードを次に示します。 これらは、通常表示されるヘルプ トピックとその使用目的の順序で並んでいます。 これらのキーワードは、コメント ベースのヘルプで任意の順序で表示でき、小文字は区別されません。

なお、`.ExternalHelp`キーワードが他のすべてのコメント ベースのヘルプ キーワードより優先されます。 ときに`.ExternalHelp`が存在する、 [Microsoft.Powershell.Commands.Get ヘルプ](/dotnet/api/Microsoft.PowerShell.Commands.Get-Help)キーワードの値に一致するヘルプ ファイルを見つけられない場合でも、コマンドレットでコメント ベースのヘルプが表示されません。

`.Synopsis` 関数またはスクリプトの簡単な説明。 このキーワードは、各トピックで 1 回だけ使用できます。

`.Description` 関数またはスクリプトの詳細な説明。 このキーワードは、各トピックで 1 回だけ使用できます。

`.Parameter` *\<パラメーター名 >* パラメーターの説明。 含めることができます、`.Parameter`関数またはスクリプトでは、各パラメーターのキーワード。

`.Parameter`キーワードには、表示、コメント ブロック内の任意の順序でパラメーターが表示される順序で、`Param`ステートメントまたは関数の宣言は、パラメーター ヘルプ トピックに表示される順序を決定します。 ヘルプ トピック内のパラメーターの順序を変更するでのパラメーターの順序を変更、`Param`ステートメントまたは関数の宣言。

内のコメントを配置することで、パラメーターの説明を指定することも、`Param`パラメーター変数名の直前のステートメント。 両方を使用する場合、`Param`ステートメントのコメントと`.Parameter`キーワードに関連付けられた説明、`.Parameter`キーワードを使用して、および`Param`ステートメントのコメントは無視されます。

`.Example` 関数または出力の例と説明が続く必要に応じてスクリプトを使用するサンプル コマンド。 それぞれの例については、このキーワードを繰り返します。

`.Inputs` 関数またはスクリプトにパイプできるオブジェクトの Microsoft .NET Framework の型。 入力オブジェクトの説明を含めることもできます。

`.Outputs` このコマンドレットで返されるオブジェクトの .NET Framework 型。 返されるオブジェクトの説明を含めることもできます。

`.Notes` 関数またはスクリプトに関する追加情報。

`.Link` 関連トピックの名前。 関連トピックごとに、このキーワードを繰り返します。 このコンテンツは、ヘルプ トピックの「関連リンク」に表示されます。

`.Link`キーワードのコンテンツは、同じヘルプ トピックのオンライン バージョンを統一リソース識別子 (URI) を含めることもできます。 使用するとオンライン バージョンが開きます、`Online`パラメーターのヘルプを表示します。 URI は、"http"または"https"で始まる必要があります。

`.Component` テクノロジまたは機能または関連する関数またはスクリプトが使用します。 Get-help コマンドが含まれる場合、このコンテンツが表示されます、`Component`パラメーターのヘルプを表示します。

`.Role` ヘルプ トピックでは、ユーザー ロール。 Get-help コマンドが含まれる場合、このコンテンツが表示されます、`Role`パラメーターのヘルプを表示します。

`.Functionality` 関数の使用目的。 Get-help コマンドが含まれる場合、このコンテンツが表示されます、`Functionality`パラメーターのヘルプを表示します。

`.ForwardHelpTargetName` `<Command-Name>` 指定されたコマンドのヘルプ トピックにリダイレクトします。 関数、スクリプト、コマンドレット、またはプロバイダーのヘルプ トピックを含む、任意のヘルプ トピックには、ユーザーをリダイレクトできます。

`.ForwardHelpCategory` `<Category>` ForwardHelpTargetName で項目のヘルプのカテゴリを指定します。 有効な値は、エイリアス、コマンドレット、HelpFile、関数、プロバイダー、全般、FAQ、用語集、ScriptCommand、ExternalScript、フィルター、またはすべてには。 同じ名前のコマンドがある場合は、競合を回避するのにには、このキーワードを使用します。

`.RemoteHelpRunspace` `<PSSession-variable>` ヘルプ トピックを含むセッションを指定します。 PSSession を含む変数を入力します。 このキーワードを使用して、`Export-PSSession`コマンドレットは、エクスポートしたコマンドのヘルプ トピックが見つかりません。

`.ExternalHelp` `<XML Help File>` パス、スクリプトまたは関数に対する XML ベースのヘルプ ファイルの名前を指定します。

`.ExternalHelp`キーワードに指示、 [Microsoft.Powershell.Commands.Get ヘルプ](/dotnet/api/Microsoft.PowerShell.Commands.Get-Help)XML ベースのファイルでスクリプトまたは関数のヘルプを取得するコマンドレットです。 **します。ExternalHelp**スクリプトまたは関数を XML ベースのヘルプ ファイルを使用する場合は、キーワードが必要です。 これがない`Get-Help`関数またはスクリプトのヘルプ ファイルは見つかりません。

`.ExternalHelp`キーワードが他のすべてのコメント ベースのヘルプ キーワードより優先されます。 ときに`.ExternalHelp`が存在する、 [Microsoft.Powershell.Commands.Get ヘルプ](/dotnet/api/Microsoft.PowerShell.Commands.Get-Help)キーワードの値に一致するヘルプ ファイルを見つけられない場合でも、コマンドレットでコメント ベースのヘルプが表示されません。

スクリプト モジュールの場合の値によって関数をエクスポートするときに`.ExternalHelp`path を含まないファイル名にする必要があります。 `Get-Help` モジュール ディレクトリのロケール固有のサブディレクトリにファイルを探します。 ファイル名の要件はありませんが、ベスト プラクティスは、次のファイル名の形式を使用する:`<ScriptModule>.psm1-help.xml`します。

関数が、モジュールに関連付けられていない場合は、値にパスとファイル名を含める、**します。ExternalHelp**キーワード。 XML ファイルに指定されたパスには、UI カルチャ固有のサブディレクトリが含まれている場合`Get-Help`スクリプトまたは関数に従ってのフォールバックの標準が確立されている言語の名前を持つ XML ファイルを再帰的にサブディレクトリを検索Windows では、同じように、すべての XML ベースのヘルプ トピックは。

コマンドレットのヘルプの XML ベースのヘルプ ファイルの形式に関する詳細については、次を参照してください。[書き込み Windows PowerShell コマンドレットのヘルプ](./writing-help-for-windows-powershell-cmdlets.md)します。