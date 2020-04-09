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
ms.openlocfilehash: 24f47ab8d99683e6d0024bd8073b6d7bb5dcbd90
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978374"
---
# <a name="getproc03-c-sample-code"></a><span data-ttu-id="4ee5d-102">GetProc03 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="4ee5d-102">GetProc03 (C#) Sample Code</span></span>

<span data-ttu-id="4ee5d-103">次のコードは、パイプライン入力を受け入れることができる `Get-Process` コマンドレットの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="4ee5d-103">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="4ee5d-104">この実装は、パイプライン入力を受け取り、指定された名前に基づいてローカルコンピューターからプロセス情報を取得し、 [WriteObject (system.object, system.string)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)メソッドをパイプラインにオブジェクトを送信するための出力機構として使用する、`Name` パラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="4ee5d-104">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="4ee5d-105">この getprov03.cs コマンドレットC#のソースファイル () をダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4ee5d-105">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="4ee5d-106">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ee5d-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="4ee5d-107">ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="4ee5d-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="4ee5d-108">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="4ee5d-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="11-78":::

## <a name="see-also"></a><span data-ttu-id="4ee5d-109">参照</span><span class="sxs-lookup"><span data-stu-id="4ee5d-109">See Also</span></span>

[<span data-ttu-id="4ee5d-110">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="4ee5d-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="4ee5d-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="4ee5d-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
