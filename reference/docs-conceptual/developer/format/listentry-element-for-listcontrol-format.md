---
title: ListControl の ListEntry 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d16bca8-d025-432d-aa84-8b607b8af3ae
caps.latest.revision: 12
ms.openlocfilehash: 1a3bafd4ca94aee70e869c699f7a4ef8befc5511
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362751"
---
# <a name="listentry-element-for-listcontrol-format"></a>ListControl の ListEntry 要素 (書式)

リストビューの定義を提供します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (Format) ListEntries 要素 (format) ListEntry 要素 (形式)

## <a name="syntax"></a>構文

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`ListEntry` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[ListEntry の EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|省略可能な要素。<br /><br /> このリストビュー定義を使用する .NET オブジェクト、またはこの定義を使用するために必要な条件を定義します。|
|[ListItems 要素 (Format)](./listitems-element-for-listentry-for-listcontrol-format.md)|必須の要素です。<br /><br /> リストビューによって値が表示されるプロパティとスクリプトを定義します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ListEntries 要素 (書式)](./listentries-element-for-listcontrol-format.md)|リストビューの定義を提供します。|

## <a name="remarks"></a>コメント

リストビューは、各オブジェクトのプロパティ値またはスクリプト値を表示するリスト形式です。 リストビューの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。

## <a name="example"></a>例

この例は、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトのリストビューを定義する XML 要素を示しています。

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>...</ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a>参照

[リストビューの作成](./creating-a-list-view.md)

[ListEntry の EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[ListEntries 要素 (書式)](./listentries-element-for-listcontrol-format.md)

[ListItems 要素 (Format)](./listitems-element-for-listentry-for-listcontrol-format.md)

[Windows PowerShell のフォーマットファイルと型ファイルの作成](./writing-a-powershell-formatting-file.md)
