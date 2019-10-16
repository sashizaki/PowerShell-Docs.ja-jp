---
title: パラメーターの書式設定 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10e025c5-9aa6-45a5-b851-23d14db1f4cc
caps.latest.revision: 7
ms.openlocfilehash: 0bd3888d81aa6d1dde26c0066f7bca9dac8a8bca
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369751"
---
# <a name="format-parameters"></a>書式のパラメーター

次の表に、データの書式設定または生成に使用されるパラメーターの推奨される名前と機能を示します。

|パラメーター|機能|
|---|---|
|**と**<br>データ型: キーワード|コマンドレットの出力形式を指定するには、このパラメーターを実装します。 たとえば、テキストやスクリプトなどが考えられます。|
|**バイナリ**<br>データ型: SwitchParameter|コマンドレットがバイナリ値を処理することを示すには、このパラメーターを実装します。|
|**暗号化**<br>データ型: キーワード|サポートされているエンコードの種類を指定するには、このパラメーターを実装します。 たとえば、ASCII、UTF8、Unicode、UTF7、BigEndianUnicode、Byte、String などの値を指定できます。|
|**改行**<br>データ型: SwitchParameter|パラメーターを指定したときに改行文字がサポートされるように、このパラメーターを実装します。|
|**ShortName**<br>データ型: SwitchParameter|パラメーターを指定したときに短い名前がサポートされるように、このパラメーターを実装します。|
|**幅**<br>データ型: Int32|ユーザーが出力デバイスの幅を指定できるように、このパラメーターを実装します。|
|**アラウンド**<br>データ型: SwitchParameter|パラメーターを指定したときにテキストの折り返しがサポートされるように、このパラメーターを実装します。|
## <a name="see-also"></a>参照

[コマンドレットのパラメーター](./cmdlet-parameters.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
