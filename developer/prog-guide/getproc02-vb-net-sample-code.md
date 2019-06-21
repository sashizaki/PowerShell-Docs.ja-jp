---
title: GetProc02 (VB.NET) サンプル コード |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f3497546-5b3a-4e29-84ba-cd9747be64b3
caps.latest.revision: 6
ms.openlocfilehash: 4ec63ed32bd2906f5b027523aa0f253b51a5d873
ms.sourcegitcommit: f60fa420bdc81db174e6168d3aeb11371e483162
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2019
ms.locfileid: "67301342"
---
# <a name="getproc02-vbnet-sample-code"></a><span data-ttu-id="a66ed-102">GetProc02 (VB.NET) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="a66ed-102">GetProc02 (VB.NET) Sample Code</span></span>

<span data-ttu-id="a66ed-103">次のコードの実装を示しています、`Get-Process`コマンドライン入力を受け付けるコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="a66ed-103">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="a66ed-104">この実装を定義する通知を`Name`とコマンドラインの入力を許可するパラメーターを使用して、 [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)メソッドの出力を送信するための出力機構としてオブジェクトをパイプラインです。</span><span class="sxs-lookup"><span data-stu-id="a66ed-104">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="a66ed-105">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="a66ed-105">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc02#getproc02vball](Msh_samplesgetproc02#getproc02vball)]  -->

## <a name="see-also"></a><span data-ttu-id="a66ed-106">参照</span><span class="sxs-lookup"><span data-stu-id="a66ed-106">See Also</span></span>

[<span data-ttu-id="a66ed-107">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="a66ed-107">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
