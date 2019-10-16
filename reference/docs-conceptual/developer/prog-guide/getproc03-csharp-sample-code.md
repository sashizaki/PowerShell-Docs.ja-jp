---
title: GetProc03 (C#) Sample Code |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebc0d538-69ac-43d5-837d-b6f47344fc6a
caps.latest.revision: 5
ms.openlocfilehash: 10c41ffd03e9adae82813bfe79d3e15030087953
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360341"
---
# <a name="getproc03-c-sample-code"></a><span data-ttu-id="041a6-102">GetProc03 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="041a6-102">GetProc03 (C#) Sample Code</span></span>

<span data-ttu-id="041a6-103">次のコードは、パイプライン入力を受け入れることができる @no__t 0 コマンドレットの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="041a6-103">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="041a6-104">この実装では、パイプライン入力を受け取り、指定された名前に基づいてローカルコンピューターからプロセス情報を取得して、 [WriteObject (system.object, system.string)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)メソッドを出力として使用する @no__t 0 パラメーターを定義します。オブジェクトをパイプラインに送信するための機構。</span><span class="sxs-lookup"><span data-stu-id="041a6-104">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="041a6-105">この getprov03.cs コマンドレットC#のソースファイル () をダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="041a6-105">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="041a6-106">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="041a6-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="041a6-107">ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="041a6-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="041a6-108">コードサンプル</span><span class="sxs-lookup"><span data-stu-id="041a6-108">Code Sample</span></span>

[!code-csharp[GetProcessSample03.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs#L11-L78 "GetProcessSample03.cs")]

## <a name="see-also"></a><span data-ttu-id="041a6-109">参照</span><span class="sxs-lookup"><span data-stu-id="041a6-109">See Also</span></span>

[<span data-ttu-id="041a6-110">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="041a6-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="041a6-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="041a6-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
