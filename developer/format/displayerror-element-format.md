---
title: DisplayError 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45c45800-a87d-456e-b07c-12d4d8c27c67
caps.latest.revision: 8
ms.openlocfilehash: 2c6a3d678ca68dc0d189f6ab981fdea5fef894cb
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056483"
---
# <a name="displayerror-element-format"></a>DisplayError 要素 (書式)

データの一部を表示するエラーが発生したときに、文字列 #ERR が表示されることを指定します。

構成要素 (形式) DefaultSettings 要素 (形式) DisplayError 要素 (形式)

## <a name="syntax"></a>構文

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`DisplayError`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[DefaultSettings 要素 (形式)](./defaultsettings-element-format.md)|書式設定ファイルのすべてのビューに適用される一般的な設定を定義します。|

## <a name="remarks"></a>コメント

既定では、データの一部を表示するときにエラーが発生したときに、データの場所が空白のままです。 この要素が true の場合、#ERR 文字列に設定するときに表示されます。

## <a name="see-also"></a>参照

[DefaultSettings 要素 (形式)](./defaultsettings-element-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
