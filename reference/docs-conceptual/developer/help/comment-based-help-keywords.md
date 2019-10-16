---
title: コメントベースのヘルプキーワード |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab90ec96-77f5-42e3-9c7e-2f4156ec207f
caps.latest.revision: 6
ms.openlocfilehash: 534a6c9a43326c8a01b2181c7a799286fa4d3997
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361361"
---
# <a name="comment-based-help-keywords"></a>コメント ベースのヘルプのキーワード

このトピックでは、コメントベースのヘルプのキーワードの一覧とその説明を示します。

## <a name="keywords-in-comment-based-help"></a>コメントベースのヘルプのキーワード

有効なコメントベースのヘルプキーワードを次に示します。 これらの一覧は、通常、ヘルプトピックに表示される順序で、使用目的と共に表示されます。 これらのキーワードは、コメントベースのヘルプ内で任意の順序で表示でき、大文字と小文字は区別されません。

@No__t-0 キーワードは、他のすべてのコメントベースのヘルプキーワードよりも優先されることに注意してください。 @No__t-0 が指定されている場合、キーワードの値に一致するヘルプファイルが見つからない場合でも、コマンドレットでは、コメント[ベースのヘルプ](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand)は表示されません。

`.Synopsis` 関数またはスクリプトの簡単な説明。 このキーワードは、各トピックで1回だけ使用できます。

`.Description` 関数またはスクリプトの詳細な説明。 このキーワードは、各トピックで1回だけ使用できます。

`.Parameter` *\<Parameter-Name >* パラメーターの説明を指定します。 関数またはスクリプトの各パラメーターには、@no__t 0 のキーワードを含めることができます。

@No__t 0 のキーワードは、コメントブロック内で任意の順序で表示できますが、パラメーターが @no__t のステートメントまたは関数の宣言に表示される順序によって、ヘルプトピックでパラメーターが表示される順序が決まります。 ヘルプトピックのパラメーターの順序を変更するには、`Param` ステートメントまたは関数宣言のパラメーターの順序を変更します。

パラメーターの説明を指定するには、パラメーター変数名の直前にある @no__t 0 ステートメントにコメントを配置します。 @No__t-0 ステートメントコメントと `.Parameter` キーワードの両方を使用する場合は、`.Parameter` キーワードに関連付けられている説明が使用され、`Param` ステートメントコメントは無視されます。

`.Example` 関数またはスクリプトを使用するサンプルコマンド。必要に応じて、サンプル出力と説明を続けます。 各例について、このキーワードを繰り返します。

`.Inputs` 関数またはスクリプトにパイプできるオブジェクトの Microsoft .NET Framework 型。 入力オブジェクトの説明を含めることもできます。

`.Outputs` コマンドレットが返すオブジェクトの .NET Framework 型。 返されたオブジェクトの説明を含めることもできます。

`.Notes` 関数またはスクリプトに関する追加情報。

`.Link` 関連トピックの名前。 関連する各トピックについて、このキーワードを繰り返します。 このコンテンツは、ヘルプトピックの「関連リンク」セクションに表示されます。

@No__t 0 キーワードのコンテンツには、同じヘルプトピックのオンラインバージョンの Uniform Resource Identifier (URI) を含めることもできます。 Get-help の `Online` パラメーターを使用すると、オンラインバージョンが開きます。 URI は "http" または "https" で始まる必要があります。

`.Component` 関数またはスクリプトが使用する、または関連するテクノロジまたは機能です。 このコンテンツは、get-help コマンドに Get-help の `Component` パラメーターが含まれている場合に表示されます。

`.Role` ヘルプトピックのユーザーロール。 このコンテンツは、get-help コマンドに Get-help の `Role` パラメーターが含まれている場合に表示されます。

`.Functionality` 関数を使用することを目的としています。 このコンテンツは、get-help コマンドに Get-help の `Functionality` パラメーターが含まれている場合に表示されます。

`.ForwardHelpTargetName` `<Command-Name>` は、指定されたコマンドのヘルプトピックにリダイレクトします。 関数、スクリプト、コマンドレット、またはプロバイダーのヘルプトピックを含む、任意のヘルプトピックにユーザーをリダイレクトできます。

`.ForwardHelpCategory` `<Category>` は、ForwardHelpTargetName 内の項目のヘルプカテゴリを指定します。 有効な値は、Alias、Cmdlet、HelpFile、Function、Provider、General、FAQ、グロッサリ、ScriptCommand、ExternalScript、Filter、または All です。 同じ名前のコマンドが存在する場合に競合を回避するには、このキーワードを使用します。

`.RemoteHelpRunspace` `<PSSession-variable>` は、ヘルプトピックを含むセッションを指定します。 PSSession を含む変数を入力します。 このキーワードは、エクスポートされたコマンドのヘルプトピックを検索するために、@no__t 0 のコマンドレットによって使用されます。

`.ExternalHelp` `<XML Help File>` は、スクリプトまたは関数の XML ベースのヘルプファイルのパスまたは名前を指定します。

@No__t-0 キーワードは、XML ベースのファイル内のスクリプトまたは関数のヘルプを取得するように、[コマンドレットに](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand)指示します。 **。** スクリプトまたは関数に対して XML ベースのヘルプファイルを使用する場合は、ExternalHelp キーワードが必要です。 この関数を使用しない場合、`Get-Help` を指定すると、関数またはスクリプトのヘルプファイルは検索されません。

@No__t-0 キーワードは、他のすべてのコメントベースのヘルプキーワードよりも優先されます。 @No__t-0 が指定されている場合、キーワードの値に一致するヘルプファイルが見つからない場合でも、コマンドレットでは、コメント[ベースのヘルプ](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand)は表示されません。

関数がスクリプトモジュールによってエクスポートされる場合、`.ExternalHelp` の値はパスを含まないファイル名にする必要があります。 `Get-Help` は、モジュールディレクトリのロケール固有のサブディレクトリでファイルを検索します。 ファイル名には要件はありませんが、ベストプラクティスとして、`<ScriptModule>.psm1-help.xml` というファイル名の形式を使用することをお勧めします。

関数がモジュールに関連付けられていない場合は、の値にパスとファイル名を含め**ます。ExternalHelp**キーワード。 XML ファイルへの指定したパスに UI カルチャ固有のサブディレクトリが含まれている場合、`Get-Help` は、Windows 用に設定されている言語フォールバック標準に従って、スクリプトまたは関数の名前を持つ XML ファイルを再帰的に検索します。は、すべての XML ベースのヘルプトピックに対して行うのと同じです。

コマンドレットヘルプの XML ベースのヘルプファイル形式の詳細については、「 [Windows PowerShell コマンドレットヘルプの記述](./writing-help-for-windows-powershell-cmdlets.md)」を参照してください。