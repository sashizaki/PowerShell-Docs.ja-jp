---
title: ListControl (形式) の要素を ListEntries |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b62e81cc-4175-40fa-829f-634245b09f86
caps.latest.revision: 12
ms.openlocfilehash: aaf16702e485135b5299ccb43a2b62db2d9f5762
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065395"
---
# <a name="listentries-element-for-listcontrol-format"></a>ListControl の ListEntries 要素 (書式)

リスト ビューの定義を提供します。 リスト ビューには、1 つまたは複数の定義を指定する必要があります。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式)

## <a name="syntax"></a>構文

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ListEntries`要素。 少なくとも 1 つの子要素を指定する必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[ListEntry 要素 (形式)](./listentry-element-for-listcontrol-format.md)|リスト ビューの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ListControl 要素 (形式)](./listcontrol-element-format.md)|ビューの一覧の形式を定義します。|

## <a name="remarks"></a>コメント

リスト ビューの詳細については、次を参照してください。[リスト ビュー](./creating-a-list-view.md)します。

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

[ListControl 要素 (形式)](./listcontrol-element-format.md)

[ListEntry 要素 (形式)](./listentry-element-for-listcontrol-format.md)

[リスト ビュー](./creating-a-list-view.md)

[Windows PowerShell の書式設定の書き込みとファイルの種類](./writing-a-powershell-formatting-file.md)
