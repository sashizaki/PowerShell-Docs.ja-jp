---
title: 動的パラメーターを宣言する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db04f1df-def5-4456-8869-336024cda723
caps.latest.revision: 8
ms.openlocfilehash: a9c530cdc66302eb6b3d9d2b284eeb486c3b2ba9
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857658"
---
# <a name="how-to-declare-dynamic-parameters"></a><span data-ttu-id="79ce9-102">動的パラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="79ce9-102">How to Declare Dynamic Parameters</span></span>

<span data-ttu-id="79ce9-103">この例では、実行時に、コマンドレットに追加される動的パラメーターを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="79ce9-103">This example shows how to define dynamic parameters that are added to the cmdlet at runtime.</span></span> <span data-ttu-id="79ce9-104">この例で、`Department`パラメーターは、ユーザーが指定されるたびに、コマンドレットに追加されます、`Employee`スイッチ パラメーター。</span><span class="sxs-lookup"><span data-stu-id="79ce9-104">In this example, the `Department` parameter is added to the cmdlet whenever the user specifies the `Employee` switch parameter.</span></span> <span data-ttu-id="79ce9-105">動的パラメーターの詳細については、[コマンドレットの動的パラメーター](./cmdlet-dynamic-parameters.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79ce9-105">For more information about dynamic parameters, see [Cmdlet Dynamic Parameters](./cmdlet-dynamic-parameters.md).</span></span>

## <a name="to-define-dynamic-parameters"></a><span data-ttu-id="79ce9-106">動的パラメーターを定義するには</span><span class="sxs-lookup"><span data-stu-id="79ce9-106">To define dynamic parameters</span></span>

1. <span data-ttu-id="79ce9-107">コマンドレットのクラス宣言で追加、 [System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters)インターフェイスに表示します。</span><span class="sxs-lookup"><span data-stu-id="79ce9-107">In the cmdlet class declaration, add the [System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) interface as shown.</span></span>

   ```csharp
   public class SendGreetingCommand : Cmdlet, IDynamicParameters
   ```

2. <span data-ttu-id="79ce9-108">呼び出す、 [System.Management.Automation.Idynamicparameters.Getdynamicparameters\*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)メソッドで、動的パラメーターが定義されているオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="79ce9-108">Call the [System.Management.Automation.Idynamicparameters.Getdynamicparameters\*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) method, which returns the object in which the dynamic parameters are defined.</span></span> <span data-ttu-id="79ce9-109">この例では、メソッドを呼び出したときに、`Employee`パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="79ce9-109">In this example, the method is called when the `Employee` parameter is specified.</span></span>

   ```csharp
   public object GetDynamicParameters()
   {
       if (employee)
       {
         context= new SendGreetingCommandDynamicParameters();
         return context;
       }
       return null;
   }
   private SendGreetingCommandDynamicParameters context;
   ```

3. <span data-ttu-id="79ce9-110">追加する動的パラメーターを定義するクラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="79ce9-110">Declare a class that defines the dynamic parameters to be added.</span></span> <span data-ttu-id="79ce9-111">動的パラメーターを宣言する静的なコマンドレットのパラメーターを宣言するために使用する属性を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="79ce9-111">You can use the attributes that you used to declare the static cmdlet parameters to declare the dynamic parameters.</span></span>

   ```csharp
   public class SendGreetingCommandDynamicParameters
   {
     [Parameter]
     [ValidateSet ("Marketing", "Sales", "Development")]
     public string Department
     {
       get { return department; }
       set { department = value; }
     }
     private string department;
   }
   ```

## <a name="example"></a><span data-ttu-id="79ce9-112">例</span><span class="sxs-lookup"><span data-stu-id="79ce9-112">Example</span></span>

<span data-ttu-id="79ce9-113">この例で、 `Department` 、ユーザーが指定されるたびに、パラメーターを追加、`Employee`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="79ce9-113">In this example, the `Department` parameter is added whenever the user specifies the `Employee` parameter.</span></span> <span data-ttu-id="79ce9-114">`Department`パラメーターは省略可能なパラメーター、および ValidateSet 属性は許可されている引数を指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="79ce9-114">The `Department` parameter is an optional parameter, and the ValidateSet attribute is used to specify the allowed arguments.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;     // PowerShell assembly.

namespace SendGreeting
{
  // Declare the cmdlet class that supports the
  // IDynamicParameters interface.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet, IDynamicParameters
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory = true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    [Parameter]
    [Alias ("FTE")]
    public SwitchParameter Employee
    {
      get { return employee; }
      set { employee = value; }
    }
    private Boolean employee;

    // Implement GetDynamicParameters to
    // retrieve the dynamic parameter.
    public object GetDynamicParameters()
    {
      if (employee)
      {
        context= new SendGreetingCommandDynamicParameters();
        return context;
      }
      return null;
   }
   private SendGreetingCommandDynamicParameters context;

    // Overide the ProcessRecord method to process the
    // supplied user name and write out a greeting to
    // the user by calling the WriteObject method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "! ");
      if (employee)
      {
        WriteObject("Department: " + context.Department);
      }
    }
  }

  // Define the dynamic parameters to be added
  public class SendGreetingCommandDynamicParameters
  {
    [Parameter]
    [ValidateSet ("Marketing", "Sales", "Development")]
    public string Department
    {
      get { return department; }
      set { department = value; }
    }
    private string department;
  }
}
```

## <a name="see-also"></a><span data-ttu-id="79ce9-115">参照</span><span class="sxs-lookup"><span data-stu-id="79ce9-115">See Also</span></span>

[<span data-ttu-id="79ce9-116">System.Management.Automation.Runtimedefinedparameterdictionary</span><span class="sxs-lookup"><span data-stu-id="79ce9-116">System.Management.Automation.Runtimedefinedparameterdictionary</span></span>](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)

[<span data-ttu-id="79ce9-117">System.Management.Automation.Idynamicparameters.Getdynamicparameters\*</span><span class="sxs-lookup"><span data-stu-id="79ce9-117">System.Management.Automation.Idynamicparameters.Getdynamicparameters\*</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="79ce9-118">コマンドレットの動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="79ce9-118">Cmdlet Dynamic Parameters</span></span>](./cmdlet-dynamic-parameters.md)

[<span data-ttu-id="79ce9-119">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="79ce9-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)