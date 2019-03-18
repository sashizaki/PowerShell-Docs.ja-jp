---
title: コマンドレットのパラメーターでのワイルドカード文字のサポート |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- wildcards [PowerShell Programmer's Guide]
- parameters [PowerShell Programmer's Guide], wildcards
ms.assetid: 9b26e1e9-9350-4a5a-aad5-ddcece658d93
caps.latest.revision: 12
ms.openlocfilehash: 6c762d3889bc4b649252390625525db4735f4c1d
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059611"
---
# <a name="supporting-wildcard-characters-in-cmdlet-parameters"></a>コマンドレット パラメーターでワイルドカード文字をサポートする

多くの場合、1 つのリソースではなく、リソースのグループに対して実行するコマンドレットを設計する必要があります。 たとえば、コマンドレットは、同じ名前または拡張機能を持つデータ ストア内ですべてのファイルを検索する必要があります。 リソースのグループに対して実行されるコマンドレットを設計する場合は、ワイルドカード文字のサポートを提供する必要があります。

> [!NOTE]
> ワイルドカード文字を使用するとも呼ば*グロビング*します。

## <a name="windows-powershell-cmdlets-that-use-wildcards"></a>ワイルドカードを使用する Windows PowerShell コマンドレット

 多くの Windows PowerShell コマンドレットは、パラメーター値をワイルドカード文字をサポートします。 たとえば、ほぼすべてのコマンドレットを持つ、`Name`または`Path`パラメーターは、これらのパラメーターにワイルドカード文字をサポートしています。 (する必要はほとんどのコマンドレット、`Path`パラメーターがあることも、`LiteralPath`パラメーターがワイルドカード文字はサポートされていない)。次のコマンドは、名前持つにはには、Get 動詞が含まれています。 現在のセッションですべてのコマンドレットを返すワイルドカード文字を使用する方法を示します。

 **PS > get コマンド get-\***

## <a name="supported-wildcard-characters"></a>サポートされているワイルドカード文字

Windows PowerShell では、次のワイルドカード文字をサポートします。

|ワイルドカード文字|説明|例|[一致する]|［次の値に一致しない］|
|------------------------|-----------------|-------------|-------------|--------------------|
|*|指定した位置から始まり、0 個以上の文字と一致|*|Apple は、可用性グループ||
|?|指定した位置に一致する任意の文字|?n|で、オン|実行|
|[ ]|文字の範囲に一致します。|[a-l] ook|書籍、cook、参照してください。|かかりました|
|[ ]|指定した文字に一致します。|[bc] ook|書籍、クック|ほら|

ワイルドカード文字をサポートするコマンドレットを設計する場合は、ワイルドカード文字の組み合わせに対して許可します。 たとえば、次のコマンドを使用して、`Get-ChildItem`コマンドレットすべての .txt ファイル c:\Techdocs フォルダー内にあるし、"a"から"l です"文字で開始されるを取得するには。

**get-childitem c:\techdocs\\[a-l]\*.txt**

前のコマンドは、範囲のワイルドカードを使用して **[、l]** ことファイル名は文字で始まる、"a"から"l です"を指定するには。 次にコマンドは、* ワイルドカード文字をファイル名の最初の文字と、.txt 拡張子の間の任意の文字のプレース ホルダーとして。

次のコードの例では、文字"d"は含まれませんが、"a"~"f"からの他のすべての文字が含まれています、範囲のワイルドカード パターン

**get-childitem c:\techdocs\\[、cef]\*.txt**

## <a name="handling-literal-characters-in-wildcard-patterns"></a>ワイルドカード パターン内のリテラル文字の処理

指定したワイルドカード パターンにリテラル文字が含まれている場合は、エスケープ文字として、アクサン グラーブ文字 (') を使用します。 リテラル文字をプログラムで指定する場合は、1 つのバッククォートを使用します。 コマンド プロンプトで、リテラル文字を指定する場合は、2 つのバッククォートを使用します。 たとえば、次のパターンには、そのまま使用する必要がありますがある 2 つの角かっこが含まれています。

"John Smith \`[*']"(プログラムで指定)

"John Smith \` \`[*\`']"(コマンド プロンプトで指定)

このパターンは、"John Smith [マーケティング]"または"John Smith [開発]"と一致します。

## <a name="cmdlet-output-and-wildcard-characters"></a>コマンドレットの出力とワイルドカード文字

コマンドレットのパラメーターは、ワイルドカード文字をサポートと、コマンドレットの操作は、通常は配列出力を生成します。 場合によっては、ユーザーは一度に 1 つの項目のみを使用する場合がありますので、出力配列をサポートするために意味がありません。 たとえば、`Set-Location`コマンドレットは、ユーザーが 1 つの場所のみを設定するため、出力配列をサポートします。 このインスタンスでは、コマンドレットには、ワイルドカード文字を引き続きサポートされますが解像度を強制的に 1 つの場所にします。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)

[WildcardPattern クラス](/dotnet/api/system.management.automation.wildcardpattern)
