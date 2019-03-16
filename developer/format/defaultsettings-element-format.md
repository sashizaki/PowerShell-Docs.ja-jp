---
title: DefaultSettings 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41c56499-ee20-4821-830a-478fdcc33f83
caps.latest.revision: 11
ms.openlocfilehash: bc95c62222eb2806f92499257a397c2e4ec5dbab
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059067"
---
# <a name="defaultsettings-element-format"></a>DefaultSettings 要素 (書式)

書式設定ファイルのすべてのビューに適用される一般的な設定を定義します。 一般的な設定に含めるコレクションを展開する方法を定義するテーブル内のテキストの折り返し、エラーを表示します。

構成要素 (形式) DefaultSettings 要素 (形式)

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

次のセクションでは、属性、子要素、およびの親要素について説明します、`DefaultSettings`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[DisplayError 要素 (形式)](./displayerror-element-format.md)|省略可能な要素です。<br /><br /> データの一部を表示中にエラーが発生したときに、文字列 #ERR が表示されることを指定します。|
|[EnumerableExpansions 要素 (形式)](./enumerableexpansions-element-format.md)|省略可能な要素です。<br /><br /> .NET オブジェクトをビューに表示されているときに展開するさまざまな方法を定義します。|
|[PropertyCountForTable (形式)](./propertycountfortable-element-format.md)|省略可能な要素です。<br /><br /> テーブル ビューでオブジェクトを表示するオブジェクトが必要なプロパティの最小数を指定します。|
|[ShowError 要素 (形式)](./showerror-element-format.md)|省略可能な要素です。<br /><br /> データの一部を表示中にエラーが発生したときに、完全なエラー レコードが表示されることを指定します。|
|[WrapTables 要素 (形式)](./wraptables-element-format.md)|省略可能な要素です。<br /><br /> 列の幅に収まらない場合、次の行にテーブル内のデータを移動することを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[構成要素](./configuration-element-format.md)|書式設定ファイルの最上位の要素を表します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[構成要素](./configuration-element-format.md)

[DisplayError 要素 (形式)](./displayerror-element-format.md)

[EnumerableExpansions 要素 (形式)](./enumerableexpansions-element-format.md)

[PropertyCountForTable (形式)](./propertycountfortable-element-format.md)

[ShowError 要素 (形式)](./showerror-element-format.md)

[WrapTables 要素 (形式)](./wraptables-element-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
