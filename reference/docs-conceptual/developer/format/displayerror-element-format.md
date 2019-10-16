---
title: DisplayError 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45c45800-a87d-456e-b07c-12d4d8c27c67
caps.latest.revision: 8
ms.openlocfilehash: 2c6a3d678ca68dc0d189f6ab981fdea5fef894cb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363991"
---
# <a name="displayerror-element-format"></a>DisplayError 要素 (書式)

データの表示中にエラーが発生した場合に、文字列 #ERR が表示されることを指定します。

Configuration 要素 (Format) DefaultSettings Element (format) DisplayError 要素 (Format)

## <a name="syntax"></a>構文

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、`DisplayError` 要素の親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[DefaultSettings 要素 (Format)](./defaultsettings-element-format.md)|書式設定ファイルのすべてのビューに適用される共通設定を定義します。|

## <a name="remarks"></a>コメント

既定では、データの一部を表示しようとしてエラーが発生すると、データの場所は空白のままになります。 この要素が true に設定されている場合、#ERR 文字列が表示されます。

## <a name="see-also"></a>参照

[DefaultSettings 要素 (Format)](./defaultsettings-element-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
