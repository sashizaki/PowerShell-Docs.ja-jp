---
title: DefaultSettings 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41c56499-ee20-4821-830a-478fdcc33f83
caps.latest.revision: 11
ms.openlocfilehash: bc95c62222eb2806f92499257a397c2e4ec5dbab
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363871"
---
# <a name="defaultsettings-element-format"></a>DefaultSettings 要素 (書式)

書式設定ファイルのすべてのビューに適用される共通設定を定義します。 一般的な設定には、エラーの表示、テーブル内のテキストの折り返し、コレクションの展開方法の定義などがあります。

Configuration 要素 (Format) DefaultSettings 要素 (形式)

## <a name="syntax"></a>構文

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、`DefaultSettings` 要素の親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[DisplayError 要素 (Format)](./displayerror-element-format.md)|省略可能な要素。<br /><br /> データの表示中にエラーが発生した場合に、文字列 #ERR が表示されることを指定します。|
|[列挙 Able展開要素 (形式)](./enumerableexpansions-element-format.md)|省略可能な要素。<br /><br /> .NET オブジェクトをビューに表示するときに展開するさまざまな方法を定義します。|
|[PropertyCountForTable (形式)](./propertycountfortable-element-format.md)|省略可能な要素。<br /><br /> オブジェクトをテーブルビューに表示するために必要なプロパティの最小数を指定します。|
|[ShowError 要素 (形式)](./showerror-element-format.md)|省略可能な要素。<br /><br /> データの一部を表示しているときにエラーが発生した場合に、完全なエラーレコードが表示されることを指定します。|
|[WrapTables 要素 (Format)](./wraptables-element-format.md)|省略可能な要素。<br /><br /> 列の幅に合わない場合に、テーブル内のデータを次の行に移動するように指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[Configuration 要素](./configuration-element-format.md)|書式設定ファイルのトップレベルの要素を表します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[Configuration 要素](./configuration-element-format.md)

[DisplayError 要素 (Format)](./displayerror-element-format.md)

[列挙 Able展開要素 (形式)](./enumerableexpansions-element-format.md)

[PropertyCountForTable (形式)](./propertycountfortable-element-format.md)

[ShowError 要素 (形式)](./showerror-element-format.md)

[WrapTables 要素 (Format)](./wraptables-element-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
