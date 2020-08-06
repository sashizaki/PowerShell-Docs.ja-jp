---
title: Runspace02 (C#) コードサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1e58f035f20baa7443d9031499062a45beae01b9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87778451"
---
# <a name="runspace02-c-code-sample"></a><span data-ttu-id="46812-102">Runspace02 (C#) コード サンプル</span><span class="sxs-lookup"><span data-stu-id="46812-102">Runspace02 (C#) Code Sample</span></span>

<span data-ttu-id="46812-103">Runspace02 サンプルの C# ソースコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="46812-103">Here is the C# source code for the Runspace02 sample.</span></span> <span data-ttu-id="46812-104">このサンプルでは、 [Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)クラスを使用して、 `Get-Process` コマンドレットを同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="46812-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute the `Get-Process` cmdlet synchronously.</span></span> <span data-ttu-id="46812-105">次に、Windows フォームとデータバインディングを使用して、DataGridView コントロールに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="46812-105">Windows Forms and data binding are then used to display the results in a DataGridView control</span></span>

## <a name="code-sample"></a><span data-ttu-id="46812-106">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="46812-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs" range="11-82":::

## <a name="see-also"></a><span data-ttu-id="46812-107">参照</span><span class="sxs-lookup"><span data-stu-id="46812-107">See Also</span></span>

[<span data-ttu-id="46812-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="46812-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
