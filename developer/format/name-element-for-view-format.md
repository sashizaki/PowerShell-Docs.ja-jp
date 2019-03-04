---
title: 要素の名前を表示 (形式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a31010d-1db9-44ae-a7f3-6ed32cb641cb
caps.latest.revision: 16
ms.openlocfilehash: 097d20cb6a04635124d1f96823248df6095ca1af
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859508"
---
# <a name="name-element-for-view-format"></a>View の Name 要素 (書式)

ビューを識別するために使用される名前を指定します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) Name 要素 (形式)

## <a name="syntax"></a>構文

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`Name`要素。 1 つだけ`Name`要素は、それぞれのビューを使用します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビュー要素 (形式)](./view-element-format.md)|1 つまたは複数の .NET オブジェクトのメンバーを表示するために使用するビューを定義します。|

## <a name="text-value"></a>テキスト値

ビューの一意のフレンドリ名を指定します。 この名前は、どのようなコマンドは、オブジェクト、またはこれらの組み合わせを返します、ビューを使用するオブジェクトまたは一連のオブジェクト (テーブル ビューやリスト ビュー)、ビューの種類への参照を含めることができます。

## <a name="remarks"></a>コメント

ビューのさまざまな種類の詳細については、次のトピックを参照してください。[テーブル ビュー](./creating-a-table-view.md)、[リスト ビュー](./creating-a-list-view.md)、[表示幅が広い](./creating-a-wide-view.md)、および[カスタム ビュー](./creating-custom-controls.md)します。

## <a name="example"></a>例

次の例は、`View`のテーブル ビューを定義する要素、 [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。 ビューの名前は、"service"です。

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a>参照

[リスト ビューの作成](./creating-a-list-view.md)

[テーブル ビューを作成します。](./creating-a-table-view.md)

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[カスタム コントロールの作成](./creating-custom-controls.md)

[ビュー要素 (形式)](./view-element-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
