---
title: パラメーター セットを宣言する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46905eb9-64d7-4c55-9c2a-7bc7bf04e14b
caps.latest.revision: 10
ms.openlocfilehash: 6c2e5891a8e3f24969c12a2e57dc5ae8caa68e41
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067894"
---
# <a name="how-to-declare-parameter-sets"></a><span data-ttu-id="d9d37-102">パラメーター セットを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="d9d37-102">How to Declare Parameter Sets</span></span>

<span data-ttu-id="d9d37-103">この例では、コマンドレットのパラメーターを宣言するときに、2 つのパラメーター セットを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d9d37-103">This example shows how to define two parameter sets when you declare the parameters for a cmdlet.</span></span> <span data-ttu-id="d9d37-104">各パラメーター セットは、一意のパラメーターと両方のパラメーター セットによって使用される共有パラメーターの両方を持っています。</span><span class="sxs-lookup"><span data-stu-id="d9d37-104">Each parameter set has both a unique parameter and a shared parameter that is used by both parameter sets.</span></span> <span data-ttu-id="d9d37-105">既定のパラメーター セットを指定する方法などのパラメーター セットの詳細については、次を参照してください。[コマンドレット パラメーター設定](./cmdlet-parameter-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="d9d37-105">For more information about parameters sets, including how to specify the default parameter set, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9d37-106">可能であれば、パラメーターとして必要なパラメーター セットの一意のパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="d9d37-106">Whenever possible, define the unique parameter of a parameter set as a required parameter.</span></span> <span data-ttu-id="d9d37-107">ただし、コマンドレット、パラメーターを指定せずに実行する場合は、一意のパラメーターは、オプションのパラメーターをできます。</span><span class="sxs-lookup"><span data-stu-id="d9d37-107">However, if you want your cmdlet to run without specifying any parameters, the unique parameter can be an optional parameter.</span></span> <span data-ttu-id="d9d37-108">一意のパラメーターなど、`Get-Command`コマンドレットは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d9d37-108">For example, the unique parameter of the `Get-Command` cmdlet is optional.</span></span>

## <a name="how-to-define-two-parameter-sets"></a><span data-ttu-id="d9d37-109">2 つのパラメーター セットを定義する方法</span><span class="sxs-lookup"><span data-stu-id="d9d37-109">How to Define Two Parameter Sets</span></span>

1. <span data-ttu-id="d9d37-110">追加、`ParameterSet`最初のパラメーター セットの一意のパラメーターのパラメーター属性にキーワード。</span><span class="sxs-lookup"><span data-stu-id="d9d37-110">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the first parameter set.</span></span>

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

2. <span data-ttu-id="d9d37-111">追加、`ParameterSet`キーワードを 2 番目のパラメーター セットの一意のパラメーターのパラメーター属性。</span><span class="sxs-lookup"><span data-stu-id="d9d37-111">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the second parameter set.</span></span>

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

3. <span data-ttu-id="d9d37-112">両方のパラメーター セットに属するパラメーターには、各パラメーター セットのパラメーター属性を追加し、追加、`ParameterSet`キーワードごとにします。</span><span class="sxs-lookup"><span data-stu-id="d9d37-112">For the parameter that belongs to both parameter sets, add a Parameter attribute for each parameter set and then add the `ParameterSet` keyword to each set.</span></span> <span data-ttu-id="d9d37-113">各パラメーター属性では、そのパラメーターを定義する方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d9d37-113">In each Parameter attribute, you can specify how that parameter is defined.</span></span> <span data-ttu-id="d9d37-114">1 つのセットで省略可能で、別の必須パラメーターができます。</span><span class="sxs-lookup"><span data-stu-id="d9d37-114">A parameter can be optional in one set and mandatory in another.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d9d37-115">参照</span><span class="sxs-lookup"><span data-stu-id="d9d37-115">See Also</span></span>

[<span data-ttu-id="d9d37-116">コマンドレットのパラメーター セット</span><span class="sxs-lookup"><span data-stu-id="d9d37-116">Cmdlet Parameter Sets</span></span>](./cmdlet-parameter-sets.md)

[<span data-ttu-id="d9d37-117">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="d9d37-117">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
