---
title: パラメーターを書式設定 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10e025c5-9aa6-45a5-b851-23d14db1f4cc
caps.latest.revision: 7
ms.openlocfilehash: 0bd3888d81aa6d1dde26c0066f7bca9dac8a8bca
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068115"
---
# <a name="format-parameters"></a>書式のパラメーター

次の表は、推奨される名前と書式を設定するデータを生成するかに使用されるパラメーターの機能を示します。

|パラメーター|機能|
|---|---|
|**として**<br>データの種類:キーワード|コマンドレットの出力形式を指定するには、このパラメーターを実装します。 たとえば、テキストまたはスクリプト可能な値になります。|
|**Binary**<br>データの種類:SwitchParameter|コマンドレットは、バイナリ値を処理することを示すために、このパラメーターを実装します。|
|**エンコード**<br>データの種類:キーワード|サポートされているエンコードの種類を指定するには、このパラメーターを実装します。 たとえば、使用可能な値は、ASCII、UTF8、Unicode、UTF7、BigEndianUnicode、バイト、および文字列可能性があります。|
|**NewLine**<br>データの種類:SwitchParameter|このパラメーターを実装するは、パラメーターを指定した場合に改行文字がサポートされるようにします。|
|**短い名前**<br>データの種類:SwitchParameter|このパラメーターを実装するは、パラメーターを指定した場合に短い名前がサポートされるようにします。|
|**Width**<br>データの種類:Int32|このパラメーターを実装するは、ユーザーは、出力デバイスの幅を指定できるようにします。|
|**ラップ**<br>データの種類:SwitchParameter|このパラメーターを実装するは、パラメーターを指定するテキストの折り返しがサポートされるようにします。|
## <a name="see-also"></a>参照

[コマンドレットのパラメーター](./cmdlet-parameters.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
