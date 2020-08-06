---
title: コマンドレットの作成に関するチュートリアル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 991cceef2b1d18c0cdaad4f092c4affb5c632b0e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784012"
---
# <a name="tutorials-for-writing-cmdlets"></a><span data-ttu-id="67690-102">コマンドレットの記述に関するチュートリアル</span><span class="sxs-lookup"><span data-stu-id="67690-102">Tutorials for Writing Cmdlets</span></span>

<span data-ttu-id="67690-103">このセクションには、コマンドレットの作成に関するチュートリアルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="67690-103">This section contains tutorials for writing cmdlets.</span></span> <span data-ttu-id="67690-104">これらのチュートリアルには、コマンドレットを記述するために必要なコードに加えて、コードが必要な理由についての説明も含まれています。</span><span class="sxs-lookup"><span data-stu-id="67690-104">These tutorials include the code needed to write the cmdlets, plus an explanation of why the code is needed.</span></span> <span data-ttu-id="67690-105">これらのトピックは、コマンドレットの記述を開始するユーザーにとって非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="67690-105">These topics will be very helpful for those who are just starting to write cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67690-106">説明の少ないコード例については、[コマンドレットのサンプル](./cmdlet-samples.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67690-106">For those who want code examples with less description, see [Cmdlet Samples](./cmdlet-samples.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="67690-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="67690-107">In This Section</span></span>

<span data-ttu-id="67690-108">[Getproc チュートリアル](./getproc-tutorial.md)-このチュートリアルでは、コマンドレットクラスを定義し、パラメーターの追加やエラーの報告などの基本的な機能を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="67690-108">[GetProc Tutorial](./getproc-tutorial.md) - This tutorial describes how to define a cmdlet class and add basic functionality such as adding parameters and reporting errors.</span></span> <span data-ttu-id="67690-109">このチュートリアルで説明するコマンドレットは、Windows PowerShell によって提供される[Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットによく似ています。</span><span class="sxs-lookup"><span data-stu-id="67690-109">The cmdlet described in this tutorial is very similar to the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet provided by Windows PowerShell.</span></span>

<span data-ttu-id="67690-110">[Stopproc チュートリアル](./stopproc-tutorial.md)-このチュートリアルでは、コマンドレットを定義し、ユーザープロンプト、ワイルドカードサポート、パラメーターセットの使用などの機能を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="67690-110">[StopProc Tutorial](./stopproc-tutorial.md) - This tutorial describes how to define a cmdlet and add functionality such as user prompts, wildcard support, and the use of parameter sets.</span></span> <span data-ttu-id="67690-111">ここで説明するコマンドレットは、Windows PowerShell によって提供される[Stop Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process)コマンドレットと同じタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="67690-111">The cmdlet described here performs the same task as the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span>

<span data-ttu-id="67690-112">[Selectstr チュートリアル](./selectstr-tutorial.md)-このチュートリアルでは、データストアにアクセスするコマンドレットを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="67690-112">[SelectStr Tutorial](./selectstr-tutorial.md) - This tutorial describes how to define a cmdlet that accesses a data store.</span></span> <span data-ttu-id="67690-113">ここで説明するコマンドレットは、Windows PowerShell によって提供される[選択文字列](/powershell/module/microsoft.powershell.utility/select-string)コマンドレットと同じタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="67690-113">The cmdlet described here performs the same task as the [Select-String](/powershell/module/microsoft.powershell.utility/select-string) cmdlet provided by Windows PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="67690-114">参照</span><span class="sxs-lookup"><span data-stu-id="67690-114">See Also</span></span>

[<span data-ttu-id="67690-115">GetProc チュートリアル</span><span class="sxs-lookup"><span data-stu-id="67690-115">GetProc Tutorial</span></span>](./getproc-tutorial.md)

[<span data-ttu-id="67690-116">StopProc チュートリアル</span><span class="sxs-lookup"><span data-stu-id="67690-116">StopProc Tutorial</span></span>](./stopproc-tutorial.md)

[<span data-ttu-id="67690-117">SelectStr チュートリアル</span><span class="sxs-lookup"><span data-stu-id="67690-117">SelectStr Tutorial</span></span>](./selectstr-tutorial.md)

[<span data-ttu-id="67690-118">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="67690-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
