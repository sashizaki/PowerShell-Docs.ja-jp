---
title: サポートオンラインヘルプ |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3204599c-7159-47aa-82ec-4a476f461027
caps.latest.revision: 7
ms.openlocfilehash: 5c5707d1c533e0498c6794b60f4499e530e25813
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360661"
---
# <a name="supporting-online-help"></a>オンライン ヘルプのサポート

Windows PowerShell 3.0 以降では、Windows PowerShell コマンドの @no__t 0 オンライン機能をサポートする方法が2つあります。 このトピックでは、さまざまなコマンドの種類に対してこの機能を実装する方法について説明します。

## <a name="about-online-help"></a>オンラインヘルプについて

オンラインヘルプは、常に Windows PowerShell の重要な部分でした。 @No__t-0 コマンドレットでは、ヘルプトピックがコマンドプロンプトに表示されますが、多くのユーザーは、色分け、ハイパーリンク、コミュニティコンテンツおよび wiki ベースのドキュメントでのアイデアの共有など、オンラインでの閲覧のエクスペリエンスを好むことがあります。 最も重要なのは、更新可能なヘルプが登場する前に、オンラインヘルプで最新バージョンのヘルプファイルが提供されていたことです。

Windows PowerShell 3.0 で更新可能なヘルプが登場したことにより、オンラインヘルプは依然として重要な役割を果たします。 柔軟なユーザーエクスペリエンスに加えて、オンラインヘルプでは、ヘルプトピックをダウンロードするために更新可能なヘルプを使用しない、または使用できないユーザーにヘルプを提供します。

## <a name="how-get-help--online-works"></a>Get-help-Online のしくみ

ユーザーがコマンドのオンラインヘルプトピックを検索できるように、`Get-Help` コマンドにはオンラインパラメーターがあり、ユーザーの既定のインターネットブラウザーでコマンドのヘルプトピックのオンラインバージョンを開くことができます。

たとえば、次のコマンドは、`Invoke-Command` コマンドレットのオンラインヘルプトピックを開きます。

```powershell
Get-Help Invoke-Command -Online
```

@No__t-0-Online を実装するには、`Get-Help` コマンドレットで、次の場所にあるオンラインバージョンのヘルプトピックの Uniform Resource Identifier (URI) を検索します。

- コマンドのヘルプトピックの「関連リンク」セクションの最初のリンク。 ヘルプトピックは、ユーザーのコンピューターにインストールする必要があります。 この機能は、Windows PowerShell 2.0 で導入されました。

- 任意のコマンドのプロパティ。 コマンドのヘルプトピックがユーザーのコンピューターにインストールされていない場合でも、このプロパティにアクセスできます。 この機能は、Windows PowerShell 3.0 で導入されました。

  `Get-Help` を指定すると、[関連リンク] セクションの最初のエントリにある URI が検索されます。 プロパティ値が間違っているか変更されている場合は、最初の関連リンクに別の値を入力することで上書きできます。 ただし、最初の関連リンクは、ヘルプトピックがユーザーのコンピューターにインストールされている場合にのみ機能します。

## <a name="adding-a-uri-to-the-first-related-link-of-a-command-help-topic"></a>コマンドヘルプトピックの最初の関連リンクへの URI の追加

コマンドの XML ベースのヘルプトピックの「関連リンク」セクションの最初のエントリに有効な URI を追加することで、任意のコマンドに対して `Get-Help`-Online をサポートできます。 このオプションは、XML ベースのヘルプトピックでのみ有効で、ヘルプトピックがユーザーのコンピューターにインストールされている場合にのみ機能します。 ヘルプトピックがインストールされていて、URI が設定されている場合 **、この**値はコマンドのプロパティよりも優先されます。

この機能をサポートするには、URI が `maml:relatedLinks` 要素の最初の `maml:relatedLinks/maml:navigationLink` 要素の `maml:uri` 要素に含まれている必要があります。

次の XML は、正しい URI の配置を示しています。 "オンラインバージョン:" @no__t 0 要素のテキストはベストプラクティスですが、必須ではありません。

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

## <a name="adding-the-helpuri-property-to-a-command"></a>コマンドへのプロパティの追加

このセクションでは、異なる種類のコマンドに、"コマンド" プロパティを追加する方法について説明します。

### <a name="adding-a-helpuri-property-to-a-cmdlet"></a>コマンドレットへのプロパティの追加

でC#記述さ**れたコマンド**レットの場合は、コマンドレットクラスにコマンドレットを追加します。 属性の値は、"http" または "https" で始まる URI である必要があります。

次のコードは、`Get-History` コマンドレットクラスのすべての属性を示しています。

```
[Cmdlet(VerbsCommon.Get, "History", HelpUri = "http://go.microsoft.com/fwlink/?LinkID=001122")]
```

### <a name="adding-a-helpuri-property-to-an-advanced-function"></a>高度な関数へのプロパティの追加

高度な関数の**場合は、** [属性] に [プロパティ] を**追加します**。 プロパティの値は、"http" または "https" で始まる URI である必要があります。

次のコードは、新しい Calendar 関数のすべての属性を示しています。

```powershell

function New-Calendar {
    [CmdletBinding(SupportsShouldProcess=$true,
    HelpURI="http://go.microsoft.com/fwlink/?LinkID=01122")]
```

### <a name="adding-a-helpuri-attribute-to-a-cim-command"></a>CIM コマンドへの属性の追加

CIM コマンドの**場合は、** CDXML ファイル内のコマンド**レットメタデータ**要素に、"/" 属性を追加します。 属性の値は、"http" または "https" で始まる URI である必要があります。

次のコードは、開始-デバッグ CIM コマンドのすべての属性を示しています。

```
<CmdletMetadata Verb="Debug" HelpUri="http://go.microsoft.com/fwlink/?LinkID=001122"/>
```

### <a name="adding-a-helpuri-attribute-to-a-workflow"></a>ワークフローへの属性の追加

Windows PowerShell 言語で記述されたワークフローの場合は、を追加**します。** ワークフローコードに対する ExternalHelp コメントディレクティブ。 ディレクティブの値は、"http" または "https" で始まる URI である必要があります。

> [!NOTE]
> Windows PowerShell の XAML ベースのワークフローでは、"/" プロパティはサポートされていません。

次のコードは、を示しています。ワークフローファイル内の ExternalHelp ディレクティブ。

```powershell
# .ExternalHelp "http://go.microsoft.com/fwlink/?LinkID=138338"
```