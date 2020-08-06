---
title: GetProc03 (VB.NET) サンプルコード |Microsoft Docs
ms.date: 09/12/2016
ms.openlocfilehash: ad8a7b13d30b77acdaa2f5365b9b2da02aaeedce
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771925"
---
# <a name="getproc03-vbnet-sample-code"></a><span data-ttu-id="ef069-102">GetProc03 (VB.NET) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="ef069-102">GetProc03 (VB.NET) Sample Code</span></span>

<span data-ttu-id="ef069-103">次のコードは、 `Get-Process` パイプライン入力を受け入れることができるコマンドレットの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="ef069-103">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="ef069-104">この実装は `Name` 、パイプライン入力を受け取り、指定された名前に基づいてローカルコンピューターからプロセス情報を取得し、パイプラインにオブジェクトを送信するための出力機構として[WriteObject (system.object, system.string)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)メソッドを使用するパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="ef069-104">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="ef069-105">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="ef069-105">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#getproc03vbAll](Msh_samplesgetproc03#getproc03vbAll)]  -->
