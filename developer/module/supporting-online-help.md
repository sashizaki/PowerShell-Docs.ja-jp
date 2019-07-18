---
title: オンライン ヘルプのサポート |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3204599c-7159-47aa-82ec-4a476f461027
caps.latest.revision: 7
ms.openlocfilehash: b76f45299d11dc10c8b16ed80f87c7f1fcc5ed65
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082143"
---
# <a name="supporting-online-help"></a>オンライン ヘルプのサポート

Windows PowerShell 3.0 以降でサポートするために 2 つの方法がある、`Get-Help`の Windows PowerShell コマンドのオンライン機能。 このトピックでは、さまざまなコマンドの種類に対してこの機能を実装する方法について説明します。

## <a name="about-online-help"></a>オンライン ヘルプについて

オンライン ヘルプには、Windows PowerShell の重要な部分がきました。 ですが、`Get-Help`コマンドレットは、コマンド プロンプトでヘルプ トピックを表示、多くのユーザーは、色分け、ハイパーリンク、およびコミュニティ コンテンツと wiki ベースのドキュメントのアイディアを共有などのオンラインの読み取りのエクスペリエンスを優先します。 最も重要なは、更新可能なヘルプの登場によって、前にオンライン ヘルプは、ヘルプ ファイルの最新バージョンを提供します。

Windows PowerShell 3.0 では更新可能なヘルプの登場によって、オンライン ヘルプはまだ重要な役割を果たします。 だけでなく、柔軟なユーザー エクスペリエンスは、オンライン ヘルプは、しない、またはヘルプ トピックをダウンロードする更新可能なヘルプを使用できないユーザーにヘルプを提供します。

## <a name="how-get-help--online-works"></a>どの Get-help-Online Works

コマンドについては、オンラインのヘルプ トピックを見つけられるようにする、`Get-Help`コマンドには、ユーザーの既定のインターネット ブラウザーで、コマンドのヘルプ トピックのオンライン バージョンを開き、オンライン パラメーターが含まれています。

たとえば、次のコマンドがのオンライン ヘルプ トピックが表示されます、`Invoke-Command`コマンドレット。

```powershell
Get-Help Invoke-Command -Online
```

実装する`Get-Help`-オンラインで、`Get-Help`コマンドレットは、次の場所でオンライン バージョンのヘルプ トピックの統一リソース識別子 (URI) を次になります。

- コマンドのヘルプ トピックの「関連リンク」の最初のリンク。 ヘルプ トピックでは、ユーザーのコンピューターにインストールする必要があります。 この機能は、Windows PowerShell 2.0 で導入されました。

- 任意のコマンドの HelpUri プロパティ。 HelpUri プロパティは、コマンドのヘルプ トピックがユーザーのコンピューターにインストールされていない場合でもアクセスできます。 この機能は、Windows PowerShell 3.0 で導入されました。

  `Get-Help` HelpUri プロパティの値を取得する前に、関連リンク」セクションの最初のエントリの URI を検索します。 プロパティの値が間違っているかが変更された場合は、最初の関連リンクで、別の値を入力してオーバーライドできます。 ただし、最初の関連リンクは、ヘルプ トピックは、ユーザーのコンピューターにインストールされている場合にのみ機能します。

## <a name="adding-a-uri-to-the-first-related-link-of-a-command-help-topic"></a>コマンドのヘルプ トピックの最初の関連リンクへの URI の追加

サポートできる`Get-Help`-コマンドの XML ベースのヘルプ トピックの「関連リンク」の最初のエントリを有効な URI を追加することで、任意のコマンドは、オンラインです。 このオプションは、XML ベースのヘルプ トピックでのみ有効ですが、ヘルプ トピックがユーザーのコンピューターにインストールされている場合にだけ機能します。 ヘルプ トピックがインストールされているし、URI が設定されて、この値よりも優先、 **HelpUri**コマンドのプロパティ。 コマンドの XML ベースのヘルプ トピックについては、次を参照してください。[コマンドのヘルプ トピックを Writing XML-Based](../help/writing-xml-based-help-topics-for-commands.md)します。

この機能をサポートするためには、URI に表示する必要があります、`maml:uri`最初要素`maml:relatedLinks/maml:navigationLink`内の要素、`maml:relatedLinks`要素。

次の XML は、URI の正しい位置を示しています。 "オンライン バージョン:"内のテキスト、`maml:linkText`要素は、ベスト プラクティスが、必須ではありません。

```xml

<maml:relatedLinks>
    <maml:navigationLink>
        <maml:linkText>Online version:</maml:linkText>
        <maml:uri>http://go.microsoft.com/fwlink/?LinkID=113279</maml:uri>
    </maml:navigationLink>
    <maml:navigationLink>
        <maml:linkText>about_History</maml:linkText>
        <maml:uri/>
    </maml:navigationLink>
</maml:relatedLinks>
```

## <a name="adding-the-helpuri-property-to-a-command"></a>コマンドへの HelpUri プロパティの追加

このセクションでは、さまざまな種類のコマンドに HelpUri プロパティを追加する方法を示します。

### <a name="adding-a-helpuri-property-to-a-cmdlet"></a>HelpUri プロパティをコマンドレットに追加します。

記述されたコマンドレットのC#、追加、 **HelpUri**属性をコマンドレット クラス。 属性の値は、"http"または"https"で始まる URI である必要があります。

次のコードの HelpUri 属性を示しています、`Get-History`コマンドレット クラス。

```
[Cmdlet(VerbsCommon.Get, "History", HelpUri = "http://go.microsoft.com/fwlink/?LinkID=001122")]
```

### <a name="adding-a-helpuri-property-to-an-advanced-function"></a>高度な関数の HelpUri プロパティの追加

高度な関数は、追加、 **HelpUri**プロパティを**CmdletBinding**属性。 プロパティの値は、"http"または"https"で始まる URI である必要があります。

次のコードは、新規カレンダー関数の HelpUri 属性を示しています。

```powershell

function New-Calendar {
    [CmdletBinding(SupportsShouldProcess=$true,
    HelpURI="http://go.microsoft.com/fwlink/?LinkID=01122")]
```

### <a name="adding-a-helpuri-attribute-to-a-cim-command"></a>CIM コマンドに HelpUri 属性を追加します。

CIM コマンド、追加、 **HelpUri**属性を**CmdletMetadata** CDXML ファイル内の要素。 属性の値は、"http"または"https"で始まる URI である必要があります。

次のコードは、開始デバッグ CIM コマンドの HelpUri 属性を示しています。

```
<CmdletMetadata Verb="Debug" HelpUri="http://go.microsoft.com/fwlink/?LinkID=001122"/>
```

### <a name="adding-a-helpuri-attribute-to-a-workflow"></a>ワークフローに HelpUri 属性を追加します。

Windows PowerShell 言語で記述されたワークフローでは、追加、**します。ExternalHelp**ワークフロー コードにディレクティブをコメントします。 ディレクティブの値は、"http"または"https"で始まる URI である必要があります。

> [!NOTE]
> Windows PowerShell での XAML ベースのワークフローの HelpUri プロパティはサポートされていません。

次のコードは、します。ワークフロー ファイルで ExternalHelp ディレクティブです。

```powershell
# .ExternalHelp "http://go.microsoft.com/fwlink/?LinkID=138338"
```