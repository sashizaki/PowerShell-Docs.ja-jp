---
title: Runspace02 (C#) コードサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59a7b8b9-f72e-43fd-9a10-77404441a3f2
caps.latest.revision: 6
ms.openlocfilehash: abf539bc29bd9ccac59bd5957397fbe68951f266
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366621"
---
# <a name="runspace02-c-code-sample"></a>Runspace02 (C#) コード サンプル

Runspace02 サンプルのC#ソースコードを次に示します。 このサンプルでは、 [Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)クラスを使用して、`Get-Process` コマンドレットを同期的に実行します。 次に、Windows フォームとデータバインディングを使用して、DataGridView コントロールに結果を表示します。

## <a name="code-sample"></a>コード サンプル

[!code-csharp[Runspace02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs#L11-L82 "Runspace02.cs")]

## <a name="see-also"></a>参照

[Windows PowerShell SDK](../windows-powershell-reference.md)
