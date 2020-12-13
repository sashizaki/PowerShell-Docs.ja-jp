---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc03 (C#) サンプル コード
description: GetProc03 (C#) サンプル コード
ms.openlocfilehash: c81ba04b2b335f4ce992c6b3ed2f019cf6d7d20f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355580"
---
# <a name="getproc03-c-sample-code"></a><span data-ttu-id="6f319-103">GetProc03 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="6f319-103">GetProc03 (C#) Sample Code</span></span>

<span data-ttu-id="6f319-104">次のコードは、 `Get-Process` パイプライン入力を受け入れることができるコマンドレットの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="6f319-104">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="6f319-105">この実装は `Name` 、パイプライン入力を受け取り、指定された名前に基づいてローカルコンピューターからプロセス情報を取得し、パイプラインにオブジェクトを送信するための出力機構として [WriteObject (system.object, system.string)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) メソッドを使用するパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="6f319-105">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="6f319-106">この Get-Proc コマンドレットの C# ソースファイル (getprov03.cs) をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f319-106">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="6f319-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f319-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="6f319-108">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="6f319-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="6f319-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="6f319-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="11-78":::

## <a name="see-also"></a><span data-ttu-id="6f319-110">参照</span><span class="sxs-lookup"><span data-stu-id="6f319-110">See Also</span></span>

[<span data-ttu-id="6f319-111">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="6f319-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="6f319-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="6f319-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
