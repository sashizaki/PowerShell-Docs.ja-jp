---
ms.date: 09/12/2016
ms.topic: reference
title: GetProc03 (VB.NET) サンプル コード
description: GetProc03 (VB.NET) サンプル コード
ms.openlocfilehash: fc70496178c85e101b380e68aacd64c8d1f350e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355563"
---
# <a name="getproc03-vbnet-sample-code"></a><span data-ttu-id="eefed-103">GetProc03 (VB.NET) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="eefed-103">GetProc03 (VB.NET) Sample Code</span></span>

<span data-ttu-id="eefed-104">次のコードは、 `Get-Process` パイプライン入力を受け入れることができるコマンドレットの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="eefed-104">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="eefed-105">この実装は `Name` 、パイプライン入力を受け取り、指定された名前に基づいてローカルコンピューターからプロセス情報を取得し、パイプラインにオブジェクトを送信するための出力機構として [WriteObject (system.object, system.string)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) メソッドを使用するパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="eefed-105">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="eefed-106">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="eefed-106">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#getproc03vbAll](Msh_samplesgetproc03#getproc03vbAll)]  -->
