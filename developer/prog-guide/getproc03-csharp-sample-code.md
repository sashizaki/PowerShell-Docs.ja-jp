---
title: GetProc03 (C#) サンプル コード |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebc0d538-69ac-43d5-837d-b6f47344fc6a
caps.latest.revision: 5
ms.openlocfilehash: 4d921dd62999bc68b80838bafa2a3da8d4df3ebb
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057521"
---
# <a name="getproc03-c-sample-code"></a><span data-ttu-id="300ce-102">GetProc03 (C#) サンプル コード</span><span class="sxs-lookup"><span data-stu-id="300ce-102">GetProc03 (C#) Sample Code</span></span>

<span data-ttu-id="300ce-103">次のコードの実装を示しています、`Get-Process`パイプライン処理の入力を受け入れることができるコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="300ce-103">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="300ce-104">この実装を定義、`Name`をパイプラインの入力を受け取るパラメーターが、指定された名前に基づいて、ローカル コンピューターからプロセス情報を取得しを使用して、 [System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29)パイプラインにオブジェクトを送信するため、出力メカニズムとしてのメソッド。</span><span class="sxs-lookup"><span data-stu-id="300ce-104">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29) method as the output mechanism for sending objects to the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="300ce-105">ダウンロードすることができます、C#この Get-proc コマンドレットは、Microsoft Windows ソフトウェア開発キットの Windows Vista と .NET Framework 3.0 ランタイム コンポーネントを使用してソース ファイル (getprov03.cs)。</span><span class="sxs-lookup"><span data-stu-id="300ce-105">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="300ce-106">ダウンロードの手順については、[Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="300ce-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="300ce-107">ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="300ce-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="300ce-108">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="300ce-108">Code Sample</span></span>

[!code-csharp[GetProcessSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs#L11-L78 "GetProcessSample03.cs")]

## <a name="see-also"></a><span data-ttu-id="300ce-109">参照</span><span class="sxs-lookup"><span data-stu-id="300ce-109">See Also</span></span>

[<span data-ttu-id="300ce-110">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="300ce-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="300ce-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="300ce-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)