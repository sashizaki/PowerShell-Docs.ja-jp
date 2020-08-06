---
title: コマンドレット内のコマンドレットとスクリプトの呼び出し |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3d5f76242c02763c41b81215bbb031e19869066a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786579"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a><span data-ttu-id="42088-102">コマンドレット内でコマンドレットとスクリプトを呼び出す</span><span class="sxs-lookup"><span data-stu-id="42088-102">Invoking Cmdlets and Scripts Within a Cmdlet</span></span>

<span data-ttu-id="42088-103">コマンドレットは、コマンドレットの入力処理メソッド内から他のコマンドレットとスクリプトを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="42088-103">A cmdlet can invoke other cmdlets and scripts from within the input processing method of the cmdlet.</span></span> <span data-ttu-id="42088-104">これにより、コードを書き直しなくても、既存のコマンドレットとスクリプトの機能をコマンドレットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="42088-104">This allows you to add the functionality of existing cmdlets and scripts to your cmdlet without having to rewrite the code.</span></span>

## <a name="the-invoke-method"></a><span data-ttu-id="42088-105">Invoke メソッド</span><span class="sxs-lookup"><span data-stu-id="42088-105">The Invoke Method</span></span>

<span data-ttu-id="42088-106">すべてのコマンドレットで既存のコマンドレットを呼び出すことができます。これは、コマンドレットによってオーバーライドさ[れる、入力](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)処理メソッド (たとえば、) から[、システムの呼び出しメソッドを](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)呼び出すことによって実行できます。</span><span class="sxs-lookup"><span data-stu-id="42088-106">All cmdlets can invoke an existing cmdlet by calling the [System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method from within an input processing method, such as [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), that is overridden by the cmdlet.</span></span> <span data-ttu-id="42088-107">ただし、を呼び出すことが[できるのは、system.servicemodel クラスから](/dotnet/api/System.Management.Automation.Cmdlet)直接派生したコマンドレットだけです。</span><span class="sxs-lookup"><span data-stu-id="42088-107">However, you can invoke only those cmdlets that derive directly from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class.</span></span> <span data-ttu-id="42088-108">[PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)クラスから派生したコマンドレットを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="42088-108">You cannot invoke a cmdlet that derives from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span>

<span data-ttu-id="42088-109">System.servicemodel [\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)メソッドには、次のバリアントがあります。</span><span class="sxs-lookup"><span data-stu-id="42088-109">The [System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method has the following variants.</span></span>

<span data-ttu-id="42088-110">System.string。この variant を[呼び出す](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)と、コマンドレットオブジェクトが呼び出され、"T" 型のオブジェクトのコレクションが返されます。</span><span class="sxs-lookup"><span data-stu-id="42088-110">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a collection of "T" type objects.</span></span>

<span data-ttu-id="42088-111">Emumerator この variant を[呼び出す](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)と、コマンドレットオブジェクトが呼び出され、厳密に型指定されたが返されます。</span><span class="sxs-lookup"><span data-stu-id="42088-111">[System.Management.Automation.Cmdlet.Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) This variant invokes the cmdlet object and returns a strongly typed emumerator.</span></span> <span data-ttu-id="42088-112">このバリアントを使用すると、ユーザーはコレクション内のオブジェクトを使用してカスタム操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="42088-112">This variant allows the user to use the objects in the collection to perform custom operations.</span></span>

## <a name="examples"></a><span data-ttu-id="42088-113">例</span><span class="sxs-lookup"><span data-stu-id="42088-113">Examples</span></span>

|<span data-ttu-id="42088-114">例</span><span class="sxs-lookup"><span data-stu-id="42088-114">Example</span></span>|<span data-ttu-id="42088-115">説明</span><span class="sxs-lookup"><span data-stu-id="42088-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="42088-116">コマンドレット内でのコマンドレットの呼び出し</span><span class="sxs-lookup"><span data-stu-id="42088-116">Invoking Cmdlets Within a Cmdlet</span></span>](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|<span data-ttu-id="42088-117">この例は、別のコマンドレット内からコマンドレットを呼び出す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="42088-117">This example shows how to invoke a cmdlet from within another cmdlet.</span></span>|
|[<span data-ttu-id="42088-118">コマンドレット内でのスクリプトの呼び出し</span><span class="sxs-lookup"><span data-stu-id="42088-118">Invoking Scripts Within a Cmdlet</span></span>](./how-to-invoke-scripts-within-a-cmdlet.md)|<span data-ttu-id="42088-119">この例では、別のコマンドレット内からコマンドレットに指定されたスクリプトを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="42088-119">This example shows how to invoke a script that is supplied to the cmdlet from within another cmdlet.</span></span>|

## <a name="see-also"></a><span data-ttu-id="42088-120">参照</span><span class="sxs-lookup"><span data-stu-id="42088-120">See Also</span></span>

[<span data-ttu-id="42088-121">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="42088-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
