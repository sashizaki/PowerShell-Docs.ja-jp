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
ms.openlocfilehash: e5dc525a6c80ce135d6d68e12968613056d447e8
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855188"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a><span data-ttu-id="3bd5d-102">コマンドレット内でコマンドレットとスクリプトを呼び出す</span><span class="sxs-lookup"><span data-stu-id="3bd5d-102">Invoking Cmdlets and Scripts Within a Cmdlet</span></span>

<span data-ttu-id="3bd5d-103">コマンドレットは、その他のコマンドレットとコマンドレットのメソッドを処理する入力の中からスクリプトを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="3bd5d-103">A cmdlet can invoke other cmdlets and scripts from within the input processing method of the cmdlet.</span></span> <span data-ttu-id="3bd5d-104">これにより、コードを書き直すことがなく、コマンドレットを既存のコマンドレットとスクリプトの機能を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="3bd5d-104">This allows you to add the functionality of existing cmdlets and scripts to your cmdlet without having to rewrite the code.</span></span>

## <a name="the-invoke-method"></a><span data-ttu-id="3bd5d-105">メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="3bd5d-105">The Invoke Method</span></span>

<span data-ttu-id="3bd5d-106">すべてのコマンドレットは、呼び出すことによって、既存のコマンドレットを呼び出すことができます、 [System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)メソッドなど、メソッドの処理の入力内から[System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)、つまり、コマンドレットによってオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="3bd5d-106">All cmdlets can invoke an existing cmdlet by calling the [System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method from within an input processing method, such as [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), that is overridden by the cmdlet.</span></span> <span data-ttu-id="3bd5d-107">ただしから直接派生したコマンドレットのみを呼び出すことができます、 [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)クラス。</span><span class="sxs-lookup"><span data-stu-id="3bd5d-107">However, you can invoke only those cmdlets that derive directly from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class.</span></span> <span data-ttu-id="3bd5d-108">派生したコマンドレットを呼び出すことはできません、 [System.Management.Automation.Pscmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)クラス。</span><span class="sxs-lookup"><span data-stu-id="3bd5d-108">You cannot invoke a cmdlet that derives from the [System.Management.Automation.Pscmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span>

<span data-ttu-id="3bd5d-109">[System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)メソッドには次のバリエーション。</span><span class="sxs-lookup"><span data-stu-id="3bd5d-109">The [System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method has the following variants.</span></span>

<span data-ttu-id="3bd5d-110">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)このバリアントは、コマンドレット オブジェクトを呼び出すし、"T"型のオブジェクトのコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="3bd5d-110">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a collection of "T" type objects.</span></span>

<span data-ttu-id="3bd5d-111">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)このバリアントはコマンドレット オブジェクトを呼び出すし、厳密に型指定された emumerator を返します。</span><span class="sxs-lookup"><span data-stu-id="3bd5d-111">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a strongly typed emumerator.</span></span> <span data-ttu-id="3bd5d-112">このバリアントでは、カスタム操作を実行するコレクション内のオブジェクトを使用するユーザーを許可します。</span><span class="sxs-lookup"><span data-stu-id="3bd5d-112">This variant allows the user to use the objects in the collection to perform custom operations.</span></span>

## <a name="examples"></a><span data-ttu-id="3bd5d-113">例</span><span class="sxs-lookup"><span data-stu-id="3bd5d-113">Examples</span></span>

|<span data-ttu-id="3bd5d-114">例</span><span class="sxs-lookup"><span data-stu-id="3bd5d-114">Example</span></span>|<span data-ttu-id="3bd5d-115">説明</span><span class="sxs-lookup"><span data-stu-id="3bd5d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3bd5d-116">コマンドレット内でコマンドレットを呼び出す</span><span class="sxs-lookup"><span data-stu-id="3bd5d-116">Invoking Cmdlets Within a Cmdlet</span></span>](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|<span data-ttu-id="3bd5d-117">この例では、別のコマンドレット内のコマンドレットを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3bd5d-117">This example shows how to invoke a cmdlet from within another cmdlet.</span></span>|
|[<span data-ttu-id="3bd5d-118">コマンドレット内でスクリプトを呼び出す</span><span class="sxs-lookup"><span data-stu-id="3bd5d-118">Invoking Scripts Within a Cmdlet</span></span>](./how-to-invoke-scripts-within-a-cmdlet.md)|<span data-ttu-id="3bd5d-119">この例では、別のコマンドレット内からコマンドレットに指定されているスクリプトを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3bd5d-119">This example shows how to invoke a script that is supplied to the cmdlet from within another cmdlet.</span></span>|

## <a name="see-also"></a><span data-ttu-id="3bd5d-120">参照</span><span class="sxs-lookup"><span data-stu-id="3bd5d-120">See Also</span></span>

[<span data-ttu-id="3bd5d-121">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="3bd5d-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
