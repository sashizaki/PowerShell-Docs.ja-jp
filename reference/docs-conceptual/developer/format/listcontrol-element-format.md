---
title: ListControl 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0173b9797bffcca74f1a32903686f771366ebb1b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785729"
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

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `ListControl` ます。 この要素には、1つの子要素のみを含める必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[ListEntries 要素 (書式)](./listentries-element-for-listcontrol-format.md)|必須の要素です。<br /><br /> リストビューの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[View 要素 (書式)](./view-element-format.md)|1つ以上のオブジェクトのメンバーを表示するために使用されるビューを定義します。|

## <a name="remarks"></a>解説

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

[View 要素 (書式)](./view-element-format.md)

[ListEntries 要素 (書式)](./listentries-element-for-listcontrol-format.md)

[リスト ビューを作成する](./creating-a-list-view.md)

[Windows PowerShell のフォーマットファイルと型ファイルの作成](./writing-a-powershell-formatting-file.md)
