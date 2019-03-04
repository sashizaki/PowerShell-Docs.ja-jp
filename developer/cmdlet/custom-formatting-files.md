---
title: カスタム ファイルを書式設定 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85d27545-8097-4010-9947-6d8b3ce2eac0
caps.latest.revision: 15
ms.openlocfilehash: 71c1c181058c5646c817b90d9832976a78c6c7de
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860608"
---
# <a name="custom-formatting-files"></a>ファイルにカスタム書式設定を適用する

コマンドレット、関数、およびスクリプトによって返されるオブジェクトの表示形式は、書式設定ファイル (format.ps1xml ファイル) を使用して定義されます。 これらのファイルのいくつかは、Windows PowerShell コマンドレットによって返されるこれらのオブジェクトの既定の表示形式を定義する Windows PowerShell によって提供されます。 ただし、カスタムの書式設定ファイルの既定の表示形式を上書きするか、独自のコマンドによって返されるオブジェクトの表示を定義するは、自分を作成することもできます。

Windows PowerShell では、これらの書式設定ファイルでデータを使用して、表示される内容と、データの書式設定方法を決定します。 表示されるデータには、スクリプト ブロックの値またはオブジェクトのプロパティを含めることができます。  スクリプト ブロックは、オブジェクトのプロパティから直接は使用できないいくつかの値を表示する場合に使用されます。 たとえば、オブジェクトの 2 つのプロパティの値を追加し、別のデータとして合計を表示することがあります。 独自の書式設定ファイルを作成するときに、定義する必要があります。*ビュー*を表示するオブジェクト。 オブジェクトごとに 1 つのビューを定義することができます、複数のオブジェクトの 1 つのビューを定義することができます、または同じオブジェクトに対して複数のビューを定義することができます。 定義できるビューの数に制限はありません。

> [!IMPORTANT]
> 書式設定ファイルは、パイプラインに返されるオブジェクトの要素を特定できません。 パイプラインにオブジェクトが返されると、そのオブジェクトのすべてのメンバーは使用できます。

## <a name="format-views"></a>形式のビュー

書式設定のビューは、表形式や一覧形式、ワイド形式では、カスタム書式指定オブジェクトを表示できます。 ほとんどの場合、各書式設定の定義は、一連のビューを記述する XML タグで表されます。 それぞれのビューには、ビュー、およびテーブル ビューの列と行情報など、ビューの要素を使用するオブジェクトには、ビューの名前が含まれています。

次のビューは使用できます。

テーブル ビューには、オブジェクトまたはスクリプト ブロックの値を 1 つまたは複数の列のプロパティが一覧表示します。 各列は、オブジェクトまたはスクリプト ブロックの値のプロパティを表します。 オブジェクト、オブジェクト、またはプロパティとスクリプト ブロックの値の組み合わせのプロパティのサブセットのすべてのプロパティを表示するテーブルのビューを定義することができます。 テーブルの各行は、返されたオブジェクトを表します。 このビューの詳細については、次を参照してください。[テーブル ビュー](../format/creating-a-table-view.md)します。

リスト ビューには、オブジェクトまたはスクリプト ブロックの値を 1 つの列のプロパティが一覧表示します。 リストの各行には、オプションのラベルまたはプロパティ名の後に、プロパティまたはスクリプト ブロックの値が表示されます。 このビューの詳細については、次を参照してください。[リスト ビュー](../format/creating-a-list-view.md)します。

表示幅が広いでは、オブジェクトまたはスクリプト ブロックの値を 1 つまたは複数の列内の 1 つのプロパティが一覧表示します。 ラベルまたはこのビューのヘッダーはありません。 このビューの詳細については、次を参照してください。[表示幅が広い](../format/creating-a-wide-view.md)します。

カスタム ビューには、テーブルのビュー、リスト ビュー、またはワイド ビューの厳格な構造に準拠していないオブジェクトのプロパティまたはスクリプト ブロックの値のカスタマイズ可能なビューが表示されます。 スタンドアロンのカスタム ビューを定義するまたはテーブル ビューまたはリスト ビューなどの別のビューで使用されるカスタム ビューを定義することができます。 このビューの詳細については、次を参照してください。[カスタム ビュー](../format/creating-custom-controls.md)します。

## <a name="view-xml-elements"></a>ビューの XML 要素

次の例は、2 つの列を含むテーブルのビューを定義するために使用する XML タグを示しています。 [ViewDefinitions](../format/viewdefinitions-element-format.md)要素が書式設定ファイルで定義されているすべてのビューのコンテナー要素。 [ビュー](../format/view-element-format.md)要素は、特定のテーブル、リスト、ビュー、またはカスタム ビューを定義します。 それぞれのビュー内で、[名前](../format/name-element-for-view-format.md)要素は、ビューの名前を指定します、 [ViewSelectedBy](../format/viewselectedby-element-format.md)要素は、ビュー、および別のコントロール要素を使用するオブジェクトを定義します (など、 `TableControl`要素) の表示形式を定義します。

```xml
ViewDefinitions
  <View>
    <Name>Name of View</Name>
    <ViewSelectedBy>
      <TypeName>Object to display using this view</TypeName>
      <TypeName>Object to display using this view</TypeName>
    </ViewSelectedBy>
    <TableControl>
      <TableHeaders>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
      </TableHeaders>
      <TableRowEntries>
        <TableRowEntry>
          <TableColumnItems>
            <TableColumnItem>
              <PropertyName>Header for column 1</PropertyName>
            </TableColumnItem>
            <TableColumnItem>
              <PropertyName>Header for column 2</PropertyName>
            </TableColumnItem>
          </TableColumnItems>
        </TableRowEntry>
      </TableRowEntries>
    </TableControl)
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a>参照

[テーブル ビュー](../format/creating-a-table-view.md)

[リスト ビュー](../format/creating-a-list-view.md)

[表示幅が広い](../format/creating-a-wide-view.md)

[カスタム ビュー](../format/creating-custom-controls.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
