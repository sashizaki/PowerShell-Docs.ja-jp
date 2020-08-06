---
title: WideControl の WideItem の PropertyName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7728f960a67faa99eaafb4a4934674e119b8af27
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780476"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a>WideControl の WideItem の PropertyName 要素 (書式)

ワイドビューに表示される値を持つオブジェクトのプロパティを指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideItem Element (format) PropertyName Element for WideItem (Format)

## <a name="syntax"></a>構文

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[WideItem 要素 (Format)](./wideitem-element-for-widecontrol-format.md)|ワイドビューに表示される値を持つプロパティまたはスクリプトを定義します。|

## <a name="text-value"></a>テキスト値

値が表示されるプロパティの名前を指定します。

## <a name="remarks"></a>解説

ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。

## <a name="example"></a>例

この例[は、ProcessName オブジェクトの](/dotnet/api/System.Diagnostics.Process)プロパティの値を表示するワイドビューを示しています。

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

## <a name="see-also"></a>参照

[WideItem 要素 (Format)](./wideitem-element-for-widecontrol-format.md)

[ワイド ビューを作成する](./creating-a-wide-view.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
