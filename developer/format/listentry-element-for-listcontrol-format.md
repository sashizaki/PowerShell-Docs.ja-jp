---
title: ListControl (形式) の要素を ListEntry |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d16bca8-d025-432d-aa84-8b607b8af3ae
caps.latest.revision: 12
ms.openlocfilehash: 1a3bafd4ca94aee70e869c699f7a4ef8befc5511
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065225"
---
# <a name="listentry-element-for-listcontrol-format"></a>ListControl の ListEntry 要素 (書式)

リスト ビューの定義を提供します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式) ListEntry 要素 (形式)

## <a name="syntax"></a>構文

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ListEntry`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[ListEntry (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|省略可能な要素です。<br /><br /> このリスト ビューの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET オブジェクトを定義します。|
|[リスト項目要素 (形式)](./listitems-element-for-listentry-for-listcontrol-format.md)|必須の要素。<br /><br /> リスト ビューで表示値を持つスクリプトとプロパティを定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ListEntries 要素 (形式)](./listentries-element-for-listcontrol-format.md)|リスト ビューの定義を提供します。|

## <a name="remarks"></a>コメント

リスト ビューは、プロパティ値または各オブジェクトのスクリプトの値を表示するリスト形式です。 リスト ビューの詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。

## <a name="example"></a>例

この例のリスト ビューを定義する XML 要素を示しています、 [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。

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

[リスト ビューの作成](./creating-a-list-view.md)

[ListEntry (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[ListEntries 要素 (形式)](./listentries-element-for-listcontrol-format.md)

[リスト項目要素 (形式)](./listitems-element-for-listentry-for-listcontrol-format.md)

[Windows PowerShell の書式設定の書き込みとファイルの種類](./writing-a-powershell-formatting-file.md)
