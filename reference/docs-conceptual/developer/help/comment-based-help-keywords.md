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
ms.openlocfilehash: 3c5736be7066a749744482cb79edad2f53705f07
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564107"
---
# <a name="comment-based-help-keywords"></a>コメント ベースのヘルプのキーワード

このトピックでは、コメントベースのヘルプのキーワードの一覧とその説明を示します。

## <a name="keywords-in-comment-based-help"></a>コメントベースのヘルプのキーワード

有効なコメントベースのヘルプキーワードを次に示します。 これらの一覧は、通常、ヘルプトピックに表示される順序で、使用目的と共に表示されます。 これらのキーワードは、コメントベースのヘルプ内で任意の順序で表示でき、大文字と小文字は区別されません。

キーワードは、 `.ExternalHelp` 他のすべてのコメントベースのヘルプキーワードよりも優先されることに注意してください。 が指定されている場合、 `.ExternalHelp` キーワードの値に一致するヘルプファイルが見つからない場合でも、このコマンドレット[では](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand)、コメントベースのヘルプは表示されません。

`.Synopsis`関数またはスクリプトの簡単な説明。 このキーワードは、各トピックで1回だけ使用できます。

`.Description`関数またはスクリプトの詳細な説明。 このキーワードは、各トピックで1回だけ使用できます。

`.Parameter`パラメーター * \< 名>* パラメーターの説明を指定します。 `.Parameter`関数またはスクリプトの各パラメーターにキーワードを含めることができます。

キーワードは、 `.Parameter` コメントブロック内で任意の順序で表示できますが、パラメーターがステートメントまたは関数の宣言に表示される順序によって、 `Param` ヘルプトピックでパラメーターが表示される順序が決まります。 ヘルプトピックのパラメーターの順序を変更するに `Param` は、ステートメントまたは関数の宣言でパラメーターの順序を変更します。

パラメーターの説明を指定するには、パラメーター変数名の直前のステートメントにコメントを配置し `Param` ます。 ステートメントコメントとキーワードの両方を使用する場合 `Param` `.Parameter` は、キーワードに関連付けられている説明 `.Parameter` が使用され、 `Param` ステートメントコメントは無視されます。

`.Example`関数またはスクリプトを使用するサンプルコマンド。必要に応じて、サンプル出力と説明が続きます。 各例について、このキーワードを繰り返します。

`.Inputs`関数またはスクリプトにパイプできるオブジェクトの Microsoft .NET Framework 型。 入力オブジェクトの説明を含めることもできます。

`.Outputs`コマンドレットが返すオブジェクトの .NET Framework 型。 返されたオブジェクトの説明を含めることもできます。

`.Notes`関数またはスクリプトに関する追加情報。

`.Link`関連するトピックの名前。 関連する各トピックについて、このキーワードを繰り返します。 このコンテンツは、ヘルプトピックの「関連リンク」セクションに表示されます。

キーワードの内容には、 `.Link` 同じヘルプトピックのオンラインバージョンの Uniform Resource Identifier (URI) を含めることもできます。 Get-help のパラメーターを使用すると、オンラインバージョンが開きます `Online` 。 URI は "http" または "https" で始まる必要があります。

`.Component`関数またはスクリプトが使用する、またはそれに関連するテクノロジまたは機能。 このコンテンツは、get-help コマンドに Get-help のパラメーターが含まれている場合に表示され `Component` ます。

`.Role`ヘルプトピックのユーザーロール。 このコンテンツは、get-help コマンドに Get-help のパラメーターが含まれている場合に表示され `Role` ます。

`.Functionality`関数の使用目的。 このコンテンツは、get-help コマンドに Get-help のパラメーターが含まれている場合に表示され `Functionality` ます。

`.ForwardHelpTargetName``<Command-Name>`指定されたコマンドのヘルプトピックにリダイレクトします。 関数、スクリプト、コマンドレット、またはプロバイダーのヘルプトピックを含む、任意のヘルプトピックにユーザーをリダイレクトできます。

`.ForwardHelpCategory``<Category>`ForwardHelpTargetName の項目のヘルプカテゴリを指定します。 有効な値は、Alias、Cmdlet、HelpFile、Function、Provider、General、FAQ、グロッサリ、ScriptCommand、ExternalScript、Filter、または All です。 同じ名前のコマンドが存在する場合に競合を回避するには、このキーワードを使用します。

`.RemoteHelpRunspace``<PSSession-variable>`ヘルプトピックを含むセッションを指定します。 PSSession を含む変数を入力します。 このキーワードは、エクスポートされ `Export-PSSession` たコマンドのヘルプトピックを検索するために、コマンドレットによって使用されます。

`.ExternalHelp``<XML Help File>`スクリプトまたは関数の XML ベースのヘルプファイルのパスと名前の両方またはいずれかを指定します。

キーワードは、 `.ExternalHelp` XML ベースのファイル内のスクリプトまたは関数のヘルプを取得するように[、コマンド](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand)レットに指示します。 **。** スクリプトまたは関数に対して XML ベースのヘルプファイルを使用する場合は、ExternalHelp キーワードが必要です。 使用しない場合、 `Get-Help` 関数またはスクリプトのヘルプファイルは検索されません。

キーワードは、 `.ExternalHelp` 他のすべてのコメントベースのヘルプキーワードよりも優先されます。 が指定されている場合、 `.ExternalHelp` キーワードの値に一致するヘルプファイルが見つからない場合でも、このコマンドレット[では](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand)、コメントベースのヘルプは表示されません。

関数がスクリプトモジュールによってエクスポートされる場合、の値は `.ExternalHelp` パスを含まないファイル名にする必要があります。 `Get-Help`は、モジュールディレクトリのロケール固有のサブディレクトリでファイルを検索します。 ファイル名には要件はありませんが、というファイル名の形式を使用することをお勧めし `<ScriptModule>.psm1-help.xml` ます。

関数がモジュールに関連付けられていない場合は、の値にパスとファイル名を含め**ます。ExternalHelp**キーワード。 XML ファイルへの指定したパスに UI カルチャ固有のサブディレクトリが含まれている場合、は、 `Get-Help` すべての xml ベースのヘルプトピックと同様に、Windows 用に設定された言語フォールバック標準に従って、スクリプトまたは関数の名前を持つ xml ファイルを再帰的に検索します。

コマンドレットヘルプの XML ベースのヘルプファイル形式の詳細については、「 [Windows PowerShell コマンドレットヘルプの記述](./writing-help-for-windows-powershell-cmdlets.md)」を参照してください。
