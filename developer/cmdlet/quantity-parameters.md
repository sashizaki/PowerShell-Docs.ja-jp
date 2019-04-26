---
title: 数量パラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c0bd8a9-1749-4885-ab24-38c0a4d9f2cb
caps.latest.revision: 6
ms.openlocfilehash: 7a3efc60fcc8729d833f6de070016cfd08cc9b88
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067537"
---
# <a name="quantity-parameters"></a>数量のパラメーター

次の表は、推奨される名前と数量のパラメーターの機能を示します。

|パラメーター|機能|
|---|---|
|**すべての**<br>データの種類:ブール型|このパラメーターを実装できるように`true`リソースの既定のサブセットではなくすべてのリソースが左右されることを示します。 このパラメーターを実装できるように`false`リソースのサブセットを示します。|
|**割り当て**<br>データの種類:Int32|ユーザーが割り当てる項目の数を指定できるように、このパラメーターを実装します。|
|**BlockCount**<br>データの種類:Int64|このパラメーターを実装するは、ユーザーは、ブロックの数を指定できるようにします。|
|**Count**<br>データの種類:Int64|このパラメーターを実装するは、ユーザーが数を指定できるようにします。|
|**Scope**<br>データの種類:キーワード|ユーザーが操作するスコープを指定できるように、このパラメーターを実装します。|

## <a name="see-also"></a>参照

[コマンドレットのパラメーター](./cmdlet-parameters.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
