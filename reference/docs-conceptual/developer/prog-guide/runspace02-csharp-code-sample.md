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
# <a name="runspace02-c-code-sample"></a><span data-ttu-id="f0c68-102">Runspace02 (C#) コード サンプル</span><span class="sxs-lookup"><span data-stu-id="f0c68-102">Runspace02 (C#) Code Sample</span></span>

<span data-ttu-id="f0c68-103">Runspace02 サンプルのC#ソースコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f0c68-103">Here is the C# source code for the Runspace02 sample.</span></span> <span data-ttu-id="f0c68-104">このサンプルでは、 [Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)クラスを使用して、`Get-Process` コマンドレットを同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="f0c68-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute the `Get-Process` cmdlet synchronously.</span></span> <span data-ttu-id="f0c68-105">次に、Windows フォームとデータバインディングを使用して、DataGridView コントロールに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0c68-105">Windows Forms and data binding are then used to display the results in a DataGridView control</span></span>

## <a name="code-sample"></a><span data-ttu-id="f0c68-106">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="f0c68-106">Code Sample</span></span>

[!code-csharp[Runspace02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs#L11-L82 "Runspace02.cs")]

## <a name="see-also"></a><span data-ttu-id="f0c68-107">参照</span><span class="sxs-lookup"><span data-stu-id="f0c68-107">See Also</span></span>

[<span data-ttu-id="f0c68-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="f0c68-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
