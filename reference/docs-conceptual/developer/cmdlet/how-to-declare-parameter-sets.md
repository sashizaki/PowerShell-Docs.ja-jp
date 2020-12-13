---
ms.date: 09/13/2016
ms.topic: reference
title: パラメーター セットを宣言する方法
description: パラメーター セットを宣言する方法
ms.openlocfilehash: bd4d504a9fe6c7f7626901c49bc08851244f0995
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667064"
---
# <a name="how-to-declare-parameter-sets"></a><span data-ttu-id="1d39c-103">パラメーター セットを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="1d39c-103">How to Declare Parameter Sets</span></span>

<span data-ttu-id="1d39c-104">この例では、コマンドレットのパラメーターを宣言するときに2つのパラメーターセットを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1d39c-104">This example shows how to define two parameter sets when you declare the parameters for a cmdlet.</span></span> <span data-ttu-id="1d39c-105">各パラメーターセットには、一意のパラメーターと、両方のパラメーターセットで使用される共有パラメーターの両方があります。</span><span class="sxs-lookup"><span data-stu-id="1d39c-105">Each parameter set has both a unique parameter and a shared parameter that is used by both parameter sets.</span></span> <span data-ttu-id="1d39c-106">既定のパラメーターセットの指定方法など、パラメーターセットの詳細については、「 [コマンドレットパラメーターセット](./cmdlet-parameter-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d39c-106">For more information about parameters sets, including how to specify the default parameter set, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d39c-107">可能な限り、パラメーターセットの一意のパラメーターを必須パラメーターとして定義します。</span><span class="sxs-lookup"><span data-stu-id="1d39c-107">Whenever possible, define the unique parameter of a parameter set as a required parameter.</span></span> <span data-ttu-id="1d39c-108">ただし、パラメーターを指定せずにコマンドレットを実行する場合は、unique パラメーターを省略可能なパラメーターにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1d39c-108">However, if you want your cmdlet to run without specifying any parameters, the unique parameter can be an optional parameter.</span></span> <span data-ttu-id="1d39c-109">たとえば、コマンドレットの一意のパラメーター `Get-Command` は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="1d39c-109">For example, the unique parameter of the `Get-Command` cmdlet is optional.</span></span>

## <a name="how-to-define-two-parameter-sets"></a><span data-ttu-id="1d39c-110">2つのパラメーターセットを定義する方法</span><span class="sxs-lookup"><span data-stu-id="1d39c-110">How to Define Two Parameter Sets</span></span>

1. <span data-ttu-id="1d39c-111">最初の `ParameterSet` パラメーターセットの unique パラメーターのパラメーター属性にキーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1d39c-111">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the first parameter set.</span></span>

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

2. <span data-ttu-id="1d39c-112">`ParameterSet`2 番目のパラメーターセットの unique パラメーターの parameter 属性にキーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1d39c-112">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the second parameter set.</span></span>

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

3. <span data-ttu-id="1d39c-113">両方のパラメーターセットに属するパラメーターについては、各パラメーターセットにパラメーター属性を追加し、 `ParameterSet` 各セットにキーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1d39c-113">For the parameter that belongs to both parameter sets, add a Parameter attribute for each parameter set and then add the `ParameterSet` keyword to each set.</span></span> <span data-ttu-id="1d39c-114">各パラメーター属性では、パラメーターの定義方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1d39c-114">In each Parameter attribute, you can specify how that parameter is defined.</span></span> <span data-ttu-id="1d39c-115">パラメーターは、1つのセットでは省略可能であり、別のセットでは必須です。</span><span class="sxs-lookup"><span data-stu-id="1d39c-115">A parameter can be optional in one set and mandatory in another.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1d39c-116">参照</span><span class="sxs-lookup"><span data-stu-id="1d39c-116">See Also</span></span>

[<span data-ttu-id="1d39c-117">コマンドレット パラメーター セット</span><span class="sxs-lookup"><span data-stu-id="1d39c-117">Cmdlet Parameter Sets</span></span>](./cmdlet-parameter-sets.md)

[<span data-ttu-id="1d39c-118">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="1d39c-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
