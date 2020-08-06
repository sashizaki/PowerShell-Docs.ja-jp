---
title: DisplayError 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5d46c2fbd48f592db5ba1b33eb6cead8dc1c4698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774288"
---
# <a name="displayerror-element-format"></a>DisplayError 要素 (書式)

データの表示中にエラーが発生した場合に、文字列 #ERR が表示されることを指定します。

Configuration 要素 (Format) DefaultSettings Element (format) DisplayError 要素 (Format)

## <a name="syntax"></a>構文

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `DisplayError` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[DefaultSettings 要素 (書式)](./defaultsettings-element-format.md)|書式設定ファイルのすべてのビューに適用される共通設定を定義します。|

## <a name="remarks"></a>解説

既定では、データの一部を表示しようとしてエラーが発生すると、データの場所は空白のままになります。 この要素が true に設定されている場合、#ERR 文字列が表示されます。

## <a name="see-also"></a>参照

[DefaultSettings 要素 (書式)](./defaultsettings-element-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
