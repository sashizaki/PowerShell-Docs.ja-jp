---
title: ViewSelectedBy (Format) の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ad807a9-d7d8-4e96-b799-9c6a7677cc2d
caps.latest.revision: 12
ms.openlocfilehash: e2028c479103cc414295dc24a0f9bb69190bfc66
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361441"
---
# <a name="typename-element-for-viewselectedby-format"></a>ViewSelectedBy の TypeName 要素 (書式)

ビューに表示される .NET オブジェクトを指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) ViewSelectedBy 要素 (Format) ViewSelectedBy (形式) の TypeName 要素

## <a name="syntax"></a>構文

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`TypeName` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ViewSelectedBy 要素 (形式)](./viewselectedby-element-format.md)|ビューに表示される .NET オブジェクトを定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名 (`System.IO.DirectoryInfo` など) を指定します。

## <a name="remarks"></a>コメント

この要素をさまざまなビューで使用する方法の詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」、「[リストビュー](./creating-a-list-view.md)の作成」、「[ワイドビューの作成](./creating-a-wide-view.md)」、および「[カスタムビューコンポーネント](./creating-custom-controls.md)」を参照してください。

## <a name="example"></a>例

リストビューの[Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトを指定する方法を次の例に示します。 テーブル、ワイド、およびカスタムビューでも同じスキーマが使用されます。

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

[リストビューの作成](./creating-a-list-view.md)

[テーブルビューの作成](./creating-a-table-view.md)

[ワイドビューの作成](./creating-a-wide-view.md)

[カスタムコントロールの作成](./creating-custom-controls.md)

[ViewSelectedBy 要素 (形式)](./viewselectedby-element-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
