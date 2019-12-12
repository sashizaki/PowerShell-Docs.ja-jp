---
title: ListControl 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37beeb0b-7a81-4747-becb-e309e17278fb
caps.latest.revision: 12
ms.openlocfilehash: 7a117c25b0d117dc846ba8e060e31e838b5edd52
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362781"
---
# <a name="listcontrol-element-format"></a>ListControl 要素 (書式)

ビューのリスト形式を定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式)

## <a name="syntax"></a>構文

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`ListControl` 要素の属性、子要素、および親要素について説明します。 この要素には、1つの子要素のみを含める必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[ListEntries 要素 (書式)](./listentries-element-for-listcontrol-format.md)|必須の要素です。<br /><br /> リストビューの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[View 要素 (Format)](./view-element-format.md)|1つ以上のオブジェクトのメンバーを表示するために使用されるビューを定義します。|

## <a name="remarks"></a>コメント

リストビューの作成の詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。

## <a name="example"></a>例

この例では、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトのリストビューを示します。

```
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>...</ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a>参照

[View 要素 (Format)](./view-element-format.md)

[ListEntries 要素 (書式)](./listentries-element-for-listcontrol-format.md)

[リストビューの作成](./creating-a-list-view.md)

[Windows PowerShell のフォーマットファイルと型ファイルの作成](./writing-a-powershell-formatting-file.md)
