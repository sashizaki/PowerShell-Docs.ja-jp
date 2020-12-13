---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc02 (C#) サンプル コード
description: GetProc02 (C#) サンプル コード
ms.openlocfilehash: 17fd0d0c0829ed21ef955fd2e62e9ee089d62190
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355614"
---
# <a name="getproc02-c-sample-code"></a><span data-ttu-id="c4ab2-103">GetProc02 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="c4ab2-103">GetProc02 (C#) Sample Code</span></span>

<span data-ttu-id="c4ab2-104">次のコードは、コマンドライン入力を受け入れるコマンドレットの実装を示して `Get-Process` います。</span><span class="sxs-lookup"><span data-stu-id="c4ab2-104">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="c4ab2-105">この実装では `Name` 、コマンドライン入力を許可するパラメーターを定義し、 [WriteObject (system.object, system.string)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) メソッドを出力機構として使用して、パイプラインに出力オブジェクトを送信することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c4ab2-105">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="c4ab2-106">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="c4ab2-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample02/GetProcessSample02.cs" range="11-76":::

## <a name="see-also"></a><span data-ttu-id="c4ab2-107">参照</span><span class="sxs-lookup"><span data-stu-id="c4ab2-107">See Also</span></span>

[<span data-ttu-id="c4ab2-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="c4ab2-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
