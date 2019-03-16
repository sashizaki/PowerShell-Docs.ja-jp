---
title: コマンドレットとコマンドレット内でスクリプトを呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7040a5c-4a47-42df-a2ea-96b134a4ed9b
caps.latest.revision: 10
ms.openlocfilehash: f20708ff41d9a6de90090997a875ba5371eccd74
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58058880"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a><span data-ttu-id="a6397-102">コマンドレット内でコマンドレットとスクリプトを呼び出す</span><span class="sxs-lookup"><span data-stu-id="a6397-102">Invoking Cmdlets and Scripts Within a Cmdlet</span></span>

<span data-ttu-id="a6397-103">コマンドレットは、その他のコマンドレットとコマンドレットのメソッドを処理する入力の中からスクリプトを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a6397-103">A cmdlet can invoke other cmdlets and scripts from within the input processing method of the cmdlet.</span></span> <span data-ttu-id="a6397-104">これにより、コードを書き直すことがなく、コマンドレットを既存のコマンドレットとスクリプトの機能を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="a6397-104">This allows you to add the functionality of existing cmdlets and scripts to your cmdlet without having to rewrite the code.</span></span>

## <a name="the-invoke-method"></a><span data-ttu-id="a6397-105">メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="a6397-105">The Invoke Method</span></span>

<span data-ttu-id="a6397-106">すべてのコマンドレットは、呼び出すことによって、既存のコマンドレットを呼び出すことができます、 [System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)メソッドなど、メソッドの処理の入力内から[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)、つまり、コマンドレットによってオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="a6397-106">All cmdlets can invoke an existing cmdlet by calling the [System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method from within an input processing method, such as [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), that is overridden by the cmdlet.</span></span> <span data-ttu-id="a6397-107">ただしから直接派生したコマンドレットのみを呼び出すことができます、 [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)クラス。</span><span class="sxs-lookup"><span data-stu-id="a6397-107">However, you can invoke only those cmdlets that derive directly from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class.</span></span> <span data-ttu-id="a6397-108">派生したコマンドレットを呼び出すことはできません、 [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)クラス。</span><span class="sxs-lookup"><span data-stu-id="a6397-108">You cannot invoke a cmdlet that derives from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span>

<span data-ttu-id="a6397-109">[System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)メソッドには次のバリエーション。</span><span class="sxs-lookup"><span data-stu-id="a6397-109">The [System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method has the following variants.</span></span>

<span data-ttu-id="a6397-110">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)このバリアントは、コマンドレット オブジェクトを呼び出すし、"T"型のオブジェクトのコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="a6397-110">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a collection of "T" type objects.</span></span>

<span data-ttu-id="a6397-111">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)このバリアントはコマンドレット オブジェクトを呼び出すし、厳密に型指定された emumerator を返します。</span><span class="sxs-lookup"><span data-stu-id="a6397-111">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a strongly typed emumerator.</span></span> <span data-ttu-id="a6397-112">このバリアントでは、カスタム操作を実行するコレクション内のオブジェクトを使用するユーザーを許可します。</span><span class="sxs-lookup"><span data-stu-id="a6397-112">This variant allows the user to use the objects in the collection to perform custom operations.</span></span>

## <a name="examples"></a><span data-ttu-id="a6397-113">例</span><span class="sxs-lookup"><span data-stu-id="a6397-113">Examples</span></span>

|<span data-ttu-id="a6397-114">例</span><span class="sxs-lookup"><span data-stu-id="a6397-114">Example</span></span>|<span data-ttu-id="a6397-115">説明</span><span class="sxs-lookup"><span data-stu-id="a6397-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a6397-116">コマンドレット内でコマンドレットを呼び出す</span><span class="sxs-lookup"><span data-stu-id="a6397-116">Invoking Cmdlets Within a Cmdlet</span></span>](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|<span data-ttu-id="a6397-117">この例では、別のコマンドレット内のコマンドレットを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6397-117">This example shows how to invoke a cmdlet from within another cmdlet.</span></span>|
|[<span data-ttu-id="a6397-118">コマンドレット内でスクリプトを呼び出す</span><span class="sxs-lookup"><span data-stu-id="a6397-118">Invoking Scripts Within a Cmdlet</span></span>](./how-to-invoke-scripts-within-a-cmdlet.md)|<span data-ttu-id="a6397-119">この例では、別のコマンドレット内からコマンドレットに指定されているスクリプトを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6397-119">This example shows how to invoke a script that is supplied to the cmdlet from within another cmdlet.</span></span>|

## <a name="see-also"></a><span data-ttu-id="a6397-120">参照</span><span class="sxs-lookup"><span data-stu-id="a6397-120">See Also</span></span>

[<span data-ttu-id="a6397-121">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="a6397-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
