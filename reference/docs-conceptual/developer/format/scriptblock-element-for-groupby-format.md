---
title: GroupBy (Format) の ScriptBlock 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30183927-6f0e-4717-b6f5-f07a6e134cfb
caps.latest.revision: 6
ms.openlocfilehash: 37a297228eb33ff75daf94a12635d42b52c6cc9f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364931"
---
# <a name="scriptblock-element-for-groupby-format"></a>GroupBy の ScriptBlock 要素 (書式)

値が変更されるたびに新しいグループを開始するスクリプトを指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビューの要素 (形式) GroupBy 要素のビュー (形式) の groupby 要素

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`ScriptBlock` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ビューの GroupBy 要素 (Format)](./groupby-element-for-view-format.md)|.NET オブジェクトのグループを表示する方法を定義します。|

## <a name="text-value"></a>テキスト値

評価されるスクリプトを指定します。

## <a name="remarks"></a>コメント

このスクリプトの値が変更されるたびに、PowerShell によって新しいグループが開始されます。

この要素が指定されている場合、 [PropertyName](propertyname-element-for-groupby-format.md)要素を指定して新しいグループを開始することはできません。

## <a name="see-also"></a>参照

[GroupBy (Format) の PropertyName 要素](propertyname-element-for-groupby-format.md)

[ビューの GroupBy 要素 (Format)](groupby-element-for-view-format.md)

[PowerShell フォーマットファイルの作成](writing-a-powershell-formatting-file.md)
