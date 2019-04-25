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
# <a name="runspace02-c-code-sample"></a><span data-ttu-id="cdae7-102">Runspace02 (C#) コード サンプル</span><span class="sxs-lookup"><span data-stu-id="cdae7-102">Runspace02 (C#) Code Sample</span></span>

<span data-ttu-id="cdae7-103">ここでは、 C# Runspace02 サンプルのコードのソースします。</span><span class="sxs-lookup"><span data-stu-id="cdae7-103">Here is the C# source code for the Runspace02 sample.</span></span> <span data-ttu-id="cdae7-104">このサンプルでは、 [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)を実行するクラス、`Get-Process`コマンドレット同期的にします。</span><span class="sxs-lookup"><span data-stu-id="cdae7-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute the `Get-Process` cmdlet synchronously.</span></span> <span data-ttu-id="cdae7-105">Windows フォームおよびデータ バインド DataGridView コントロールに結果を表示に使用されます。</span><span class="sxs-lookup"><span data-stu-id="cdae7-105">Windows Forms and data binding are then used to display the results in a DataGridView control</span></span>

## <a name="code-sample"></a><span data-ttu-id="cdae7-106">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="cdae7-106">Code Sample</span></span>

[!code-csharp[Runspace02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs#L11-L82 "Runspace02.cs")]

## <a name="see-also"></a><span data-ttu-id="cdae7-107">参照</span><span class="sxs-lookup"><span data-stu-id="cdae7-107">See Also</span></span>

[<span data-ttu-id="cdae7-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="cdae7-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)