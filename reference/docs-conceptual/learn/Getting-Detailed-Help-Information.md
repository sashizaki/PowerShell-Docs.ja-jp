---
ms.date: 08/27/2018
keywords: PowerShell, コマンドレット
title: 詳しいヘルプ情報の取得
ms.assetid: 6fb4daf7-8607-4a3e-b692-f77631adc1b9
ms.openlocfilehash: e58814f512aa2c5914f92f942cf2a4a76956ee20
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794571"
---
# <a name="getting-detailed-help-information"></a>詳しいヘルプ情報の取得

PowerShell には、PowerShell の概念と言語について説明した詳しいヘルプ記事があります。 また、各コマンドレットおよびプロバイダーに関するヘルプ記事や、多くの関数およびスクリプトに関するヘルプ記事もあります。

これらのヘルプ記事はコマンド プロンプトで表示でき、[PowerShell](/powershell/scripting/overview) ドキュメント オンラインでこれらの記事の最新版を確認することもできます。

## <a name="getting-help-for-cmdlets"></a>コマンドレットのヘルプの表示

PowerShell のコマンドレットに関するヘルプを表示するには、[Get-Help](/powershell/module/microsoft.powershell.core/Get-Help) コマンドレットを使用します。 たとえば、`Get-ChildItem` コマンドレットのヘルプを表示するには、次のように入力します。

```powershell
Get-Help Get-ChildItem
```

または

```powershell
Get-ChildItem -?
```

Get-Help コマンドレットに関するヘルプも表示できます。 たとえば、次のように入力します。

```powershell
Get-Help Get-Help
```

セッションのすべてのコマンドレットのヘルプ記事の一覧を表示するには、次のように入力します。

```powershell
Get-Help -Category Cmdlet
```

各ヘルプ記事を 1 ページずつ表示するには、`help` 関数またはそのエイリアスである `man` を使用します。
たとえば、`Get-ChildItem` コマンドレットのヘルプを表示するには、次のように入力します。

```powershell
man Get-ChildItem
```

または

```powershell
help Get-ChildItem
```

詳細な情報を表示するには、`Get-Help` コマンドレットの **Detailed** パラメーターを使用します。 たとえば、`Get-ChildItem` コマンドレットに関する詳細情報を表示するには、次のように入力します。

```powershell
Get-Help Get-ChildItem -Detailed
```

ヘルプ記事のすべての内容を表示するには、`Get-Help` コマンドレットの **Full** パラメーターを使用します。 たとえば、`Get-ChildItem` コマンドレットのヘルプ記事の内容をすべて表示するには、次のように入力します。

```powershell
Get-Help Get-ChildItem -Full
```

コマンドレットのパラメーターに関する詳しいヘルプを表示するには、`Get-Help` コマンドレットの **Parameter** パラメーターを使用します。 たとえば、`Get-ChildItem` コマンドレットのすべてのパラメーターの詳しいヘルプを表示するには、次のように入力します。

```powershell
Get-Help Get-ChildItem -Parameter *
```

ヘルプ記事内の例だけを表示するには、`Get-Help` の **Example** パラメーターを使用します。
たとえば、`Get-ChildItem` コマンドレットのヘルプ記事の例だけを表示するには、次のように入力します。

```powershell
Get-Help Get-ChildItem -Examples
```

作成したコマンドレットに関するヘルプ記事を記述する方法については、「[How to Write Cmdlet Help](/powershell/developer/help/writing-help-for-windows-powershell-cmdlets)」(コマンドレット ヘルプの記述方法) を参照してください。

## <a name="getting-conceptual-help"></a>概念説明のヘルプの表示

`Get-Help` コマンドレットでは、PowerShell 言語に関する記事など、PowerShell の概念説明の記事の情報も表示されます。 概念説明のヘルプ記事には、"about_" というプレフィックスが付きます (about_line_editing など)。 概念説明の記事の名前は、英語バージョン以外の PowerShell でも英語で入力する必要があります。

概念説明の記事を一覧表示するには、次のように入力します。

```powershell
Get-Help about_*
```

特定のヘルプ記事を表示するには、次のように記事の名前を入力します。

```powershell
Get-Help about_command_syntax
```

**Detailed**、**Parameter**、**Examples** などの `Get-Help` のパラメーターは、概念説明のヘルプ記事の表示には効果がありません。

## <a name="getting-help-about-providers"></a>プロバイダーに関するヘルプの表示

`Get-Help` コマンドレットでは、PowerShell プロバイダーに関する情報を表示できます。 プロバイダーのヘルプを取得するには、`Get-Help` に続けてプロバイダー名を入力します。 たとえば、Registry プロバイダーのヘルプを取得するには、次のように入力します。

```powershell
Get-Help registry
```

セッションのすべてのプロバイダーのヘルプ記事の一覧を表示するには、次のように入力します。

```powershell
Get-Help -Category provider
```

**Detailed**、**Parameter**、**Examples** などの `Get-Help` のパラメーターは、プロバイダー ヘルプ記事の表示には効果がありません。

## <a name="getting-help-about-scripts-and-functions"></a>スクリプトおよび関数に関するヘルプの表示

PowerShell の多くのスクリプトおよび関数には、ヘルプ記事が用意されています。 `Get-Help` コマンドレットを使用して、スクリプトや関数のヘルプ記事を表示します。

関数のヘルプを表示するには、`Get-Help` に続けて関数名を入力します。 たとえば、`Disable-PSRemoting` 関数のヘルプを表示するには、次のように入力します。

```powershell
Get-Help Disable-PSRemoting
```

スクリプトのヘルプを表示するには、スクリプト ファイルへのパスを入力します。 スクリプトが Path 環境変数に一覧表示されたパスにない場合は、完全修飾パスを使用する必要があります。

たとえば、"TestScript.ps1" という名前のスクリプトが C:\\PS-Test ディレクトリに格納されている場合、このスクリプトのヘルプ記事を表示するには、次のように入力します。

```powershell
Get-Help c:\ps-test\TestScript.ps1
```

コマンドレットのヘルプを表示するように設計されたパラメーターは、スクリプトと関数のヘルプにも有効です。 ただし、`Get-Help *` を実行している場合、スクリプトと関数のヘルプは表示されません。

関数とスクリプトのヘルプ記事の記述については、次の記事を参照してください。

- [about_Functions](/powershell/module/microsoft.powershell.core/about/about_functions)
- [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts)
- [about_Comment_Based_Help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)

## <a name="getting-help-online"></a>オンラインでのヘルプの表示

オンラインでのヘルプ記事の表示は、ヘルプを表示するための最善の方法の 1 つです。 オンラインの記事は、より簡単に最新のコンテンツに更新して提供できます。

オンライン ヘルプを表示するには、`Get-Help` コマンドレットの **Online** パラメーターを使用します。 プロバイダー ヘルプや概念説明 (About) のヘルプ記事など、PowerShell に付属しているすべてのヘルプ記事は、[PowerShell](/powershell/scripting/powershell-scripting) ドキュメントでオンラインから利用できます。

> [!NOTE]
> 概念説明の記事 (about_\*) やプロバイダー ヘルプの記事では、**Online** パラメーターを使用できません。
> オンライン ヘルプはオプションであるため、すべてのコマンドレット、関数、またはスクリプトで有効なわけではありません。

たとえば、`Get-ChildItem` コマンドレットのヘルプ記事のオンライン バージョンを表示するには、次のように入力します。

```powershell
Get-Help Get-ChildItem -Online
```

PowerShell では、既定のブラウザーで記事を開きます。 あるへルプ記事のオンライン ヘルプがサポートされている場合は、そのヘルプ記事の URL を表示することもできます。 URL は、ヘルプ記事の「関連リンク」セクションに表示されます。

たとえば、Add-Computer コマンドレットのオンライン ヘルプ トピックの URL を表示するには、次のように入力します。

```powershell
Get-Help Add-Computer
```

記事の「関連リンク」セクションの最初の行を次に示します。

```Output
Online version: http://go.microsoft.com/fwlink/?LinkId=821564
```

ヘルプ記事のオンライン サポートを提供する方法については、[about_Comment_Based_Help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) を参照してください。

## <a name="see-also"></a>関連項目

- [about_Functions](/powershell/module/microsoft.powershell.core/about/about_functions)
- [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts)
- [about_Comment_Based_Help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)
- [Get-Help](/powershell/module/microsoft.powershell.core/get-help)
