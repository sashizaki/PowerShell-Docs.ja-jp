---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc02 (VB.NET) サンプル コード
description: GetProc02 (VB.NET) サンプル コード
ms.openlocfilehash: aefc3a4df5e0f29120916648ecdca41931a4c1c6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "93354543"
---
# <a name="getproc02-vbnet-sample-code"></a><span data-ttu-id="6ec3e-103">GetProc02 (VB.NET) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="6ec3e-103">GetProc02 (VB.NET) Sample Code</span></span>

<span data-ttu-id="6ec3e-104">次のコードは、コマンドライン入力を受け入れるコマンドレットの実装を示して `Get-Process` います。</span><span class="sxs-lookup"><span data-stu-id="6ec3e-104">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="6ec3e-105">この実装では `Name` 、コマンドライン入力を許可するパラメーターを定義し、 [WriteObject (system.object, system.string)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) メソッドを出力機構として使用して、パイプラインに出力オブジェクトを送信することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6ec3e-105">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="6ec3e-106">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="6ec3e-106">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc02#getproc02vball](Msh_samplesgetproc02#getproc02vball)]  -->

## <a name="see-also"></a><span data-ttu-id="6ec3e-107">参照</span><span class="sxs-lookup"><span data-stu-id="6ec3e-107">See Also</span></span>

[<span data-ttu-id="6ec3e-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="6ec3e-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
