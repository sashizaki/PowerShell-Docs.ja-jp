---
title: GroupBy (形式) の ScriptBlock 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30183927-6f0e-4717-b6f5-f07a6e134cfb
caps.latest.revision: 6
ms.openlocfilehash: 37a297228eb33ff75daf94a12635d42b52c6cc9f
ms.sourcegitcommit: 58fb23c854f5a8b40ad1f952d3323aeeccac7a24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65229328"
---
# <a name="scriptblock-element-for-groupby-format"></a>GroupBy の ScriptBlock 要素 (書式)

その値が変更されるたびに、新しいグループを開始するスクリプトを指定します。

構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) の GroupBy (形式) のビュー (形式) スクリプト ブロックの要素の GroupBy 要素

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビュー (形式) の GroupBy 要素](./groupby-element-for-view-format.md)|.NET オブジェクトのグループを表示する方法を定義します。|

## <a name="text-value"></a>テキスト値

評価されるスクリプトを指定します。

## <a name="remarks"></a>コメント

PowerShell は、このスクリプトの値が変更されるたびに、新しいグループを開始します。

この要素が指定されている場合は指定できません、 [PropertyName](propertyname-element-for-groupby-format.md)要素を新しいグループを開始します。

## <a name="see-also"></a>参照

[GroupBy (形式) の PropertyName 要素](propertyname-element-for-groupby-format.md)

[ビュー (形式) の GroupBy 要素](groupby-element-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](writing-a-powershell-formatting-file.md)
