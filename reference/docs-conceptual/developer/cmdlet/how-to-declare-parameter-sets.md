---
title: パラメーターセットを宣言する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46905eb9-64d7-4c55-9c2a-7bc7bf04e14b
caps.latest.revision: 10
ms.openlocfilehash: 6c2e5891a8e3f24969c12a2e57dc5ae8caa68e41
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365611"
---
# <a name="how-to-declare-parameter-sets"></a><span data-ttu-id="91aaa-102">パラメーター セットを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="91aaa-102">How to Declare Parameter Sets</span></span>

<span data-ttu-id="91aaa-103">この例では、コマンドレットのパラメーターを宣言するときに2つのパラメーターセットを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="91aaa-103">This example shows how to define two parameter sets when you declare the parameters for a cmdlet.</span></span> <span data-ttu-id="91aaa-104">各パラメーターセットには、一意のパラメーターと、両方のパラメーターセットで使用される共有パラメーターの両方があります。</span><span class="sxs-lookup"><span data-stu-id="91aaa-104">Each parameter set has both a unique parameter and a shared parameter that is used by both parameter sets.</span></span> <span data-ttu-id="91aaa-105">既定のパラメーターセットの指定方法など、パラメーターセットの詳細については、「[コマンドレットパラメーターセット](./cmdlet-parameter-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91aaa-105">For more information about parameters sets, including how to specify the default parameter set, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91aaa-106">可能な限り、パラメーターセットの一意のパラメーターを必須パラメーターとして定義します。</span><span class="sxs-lookup"><span data-stu-id="91aaa-106">Whenever possible, define the unique parameter of a parameter set as a required parameter.</span></span> <span data-ttu-id="91aaa-107">ただし、パラメーターを指定せずにコマンドレットを実行する場合は、unique パラメーターを省略可能なパラメーターにすることができます。</span><span class="sxs-lookup"><span data-stu-id="91aaa-107">However, if you want your cmdlet to run without specifying any parameters, the unique parameter can be an optional parameter.</span></span> <span data-ttu-id="91aaa-108">たとえば、`Get-Command` コマンドレットの unique パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="91aaa-108">For example, the unique parameter of the `Get-Command` cmdlet is optional.</span></span>

## <a name="how-to-define-two-parameter-sets"></a><span data-ttu-id="91aaa-109">2つのパラメーターセットを定義する方法</span><span class="sxs-lookup"><span data-stu-id="91aaa-109">How to Define Two Parameter Sets</span></span>

1. <span data-ttu-id="91aaa-110">最初のパラメーターセットの一意のパラメーターのパラメーター属性に `ParameterSet` キーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="91aaa-110">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the first parameter set.</span></span>

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test01")]
   public string UserName
   {
     get { return userName; }
     set { userName = value; }
   }
   private string userName;
   ```

2. <span data-ttu-id="91aaa-111">2番目のパラメーターセットの unique パラメーターの Parameter 属性に `ParameterSet` キーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="91aaa-111">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the second parameter set.</span></span>

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test02")]
   public string ComputerName
   {
     get { return computerName; }
     set { computerName = value; }
   }
   private string computerName;
   ```

3. <span data-ttu-id="91aaa-112">両方のパラメーターセットに属するパラメーターについては、各パラメーターセットにパラメーター属性を追加し、各セットに `ParameterSet` キーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="91aaa-112">For the parameter that belongs to both parameter sets, add a Parameter attribute for each parameter set and then add the `ParameterSet` keyword to each set.</span></span> <span data-ttu-id="91aaa-113">各パラメーター属性では、パラメーターの定義方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="91aaa-113">In each Parameter attribute, you can specify how that parameter is defined.</span></span> <span data-ttu-id="91aaa-114">パラメーターは、1つのセットでは省略可能であり、別のセットでは必須です。</span><span class="sxs-lookup"><span data-stu-id="91aaa-114">A parameter can be optional in one set and mandatory in another.</span></span>

   ```csharp
   [Parameter(Mandatory= true, ParameterSetName = "Test01")]
   [Parameter(ParameterSetName = "Test02")]
   public string SharedParam
   {
       get { return sharedParam; }
       set { sharedParam = value; }
   }
   private string sharedParam;
   ```

## <a name="see-also"></a><span data-ttu-id="91aaa-115">参照</span><span class="sxs-lookup"><span data-stu-id="91aaa-115">See Also</span></span>

[<span data-ttu-id="91aaa-116">コマンドレットのパラメーターセット</span><span class="sxs-lookup"><span data-stu-id="91aaa-116">Cmdlet Parameter Sets</span></span>](./cmdlet-parameter-sets.md)

[<span data-ttu-id="91aaa-117">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="91aaa-117">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
