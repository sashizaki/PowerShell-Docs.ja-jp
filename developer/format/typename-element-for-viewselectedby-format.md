---
title: ViewSelectedBy (形式) の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ad807a9-d7d8-4e96-b799-9c6a7677cc2d
caps.latest.revision: 12
ms.openlocfilehash: e2028c479103cc414295dc24a0f9bb69190bfc66
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857898"
---
# <a name="typename-element-for-viewselectedby-format"></a>ViewSelectedBy の TypeName 要素 (書式)

ビューが表示されている .NET オブジェクトを指定します。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ViewSelectedBy 要素 (形式) TypeName の構成要素 ViewSelectedBy (形式)

## <a name="syntax"></a>構文

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ViewSelectedBy 要素 (形式)](./viewselectedby-element-format.md)|ビューが表示されている .NET オブジェクトを定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。

## <a name="remarks"></a>コメント

この要素はさまざまなビューで使用する方法の詳細については、次を参照してください[テーブル ビューを作成する](./creating-a-table-view.md)、[リスト ビューを作成する](./creating-a-list-view.md)、[ワイド ビューを作成する](./creating-a-wide-view.md)、および[。カスタム ビュー コンポーネント](./creating-custom-controls.md)します。

## <a name="example"></a>例

次の例は、指定する方法を示します、 [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)のリスト ビューのオブジェクト。 テーブルの幅をカスタム ビューに同じスキーマが使用されます。

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a>参照

[リスト ビューの作成](./creating-a-list-view.md)

[テーブル ビューを作成します。](./creating-a-table-view.md)

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[カスタム コントロールの作成](./creating-custom-controls.md)

[ViewSelectedBy 要素 (形式)](./viewselectedby-element-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
