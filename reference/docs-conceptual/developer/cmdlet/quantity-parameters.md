---
title: Quantity パラメーター |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7ff6562380bb6336b08879b31d8d9fed47bfb6a7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781819"
---
# <a name="quantity-parameters"></a>数量のパラメーター

次の表に、quantity パラメーターの推奨される名前と機能を示します。

|パラメーター|機能|
|---|---|
|**すべて**<br>データ型: ブール値|このパラメーターは、 `true` リソースの既定のサブセットではなく、すべてのリソースを処理する必要があることを示すために実装します。 リソースのサブセットを示すように、このパラメーターを実装 `false` します。|
|**Allocation**<br>データ型: Int32|割り当てられる項目の数をユーザーが指定できるように、このパラメーターを実装します。|
|**ブロック数**<br>データ型: Int64|ユーザーがブロックカウントを指定できるように、このパラメーターを実装します。|
|**Count**<br>データ型: Int64|ユーザーがカウントを指定できるように、このパラメーターを実装します。|
|**スコープ**<br>データ型: キーワード|操作するスコープをユーザーが指定できるように、このパラメーターを実装します。|

## <a name="see-also"></a>参照

[コマンドレットのパラメーター](./cmdlet-parameters.md)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
