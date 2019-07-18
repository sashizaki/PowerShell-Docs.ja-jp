---
title: Runspace02 (C#) コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59a7b8b9-f72e-43fd-9a10-77404441a3f2
caps.latest.revision: 6
ms.openlocfilehash: 0a8fc05db74529e2bfb88820b9cfd988245e0aeb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081412"
---
# <a name="runspace02-c-code-sample"></a>Runspace02 (C#) コード サンプル

ここでは、 C# Runspace02 サンプルのコードのソースします。 このサンプルでは、 [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)を実行するクラス、`Get-Process`コマンドレット同期的にします。 Windows フォームおよびデータ バインド DataGridView コントロールに結果を表示に使用されます。

## <a name="code-sample"></a>コード サンプル

[!code-csharp[Runspace02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs#L11-L82 "Runspace02.cs")]

## <a name="see-also"></a>参照

[Windows PowerShell SDK](../windows-powershell-reference.md)