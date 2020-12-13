---
ms.date: 01/15/2019
ms.topic: reference
title: 単純なコマンドレットを記述する方法
description: 単純なコマンドレットを記述する方法
ms.openlocfilehash: 59dce5d797f80647e0b70a1f80faf67198652082
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646486"
---
# <a name="how-to-write-a-cmdlet"></a><span data-ttu-id="8068f-103">コマンドレットを記述する方法</span><span class="sxs-lookup"><span data-stu-id="8068f-103">How to write a cmdlet</span></span>

<span data-ttu-id="8068f-104">この記事では、コマンドレットを記述する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8068f-104">This article shows how to write a cmdlet.</span></span> <span data-ttu-id="8068f-105">`Send-Greeting`コマンドレットは、入力として1つのユーザー名を受け取り、そのユーザーにあいさつを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="8068f-105">The `Send-Greeting` cmdlet takes a single user name as input and then writes a greeting to that user.</span></span> <span data-ttu-id="8068f-106">このコマンドレットは多くの作業を実行しませんが、この例ではコマンドレットの主要なセクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="8068f-106">Although the cmdlet does not do much work, this example demonstrates the major sections of a cmdlet.</span></span>

## <a name="steps-to-write-a-cmdlet"></a><span data-ttu-id="8068f-107">コマンドレットを記述する手順</span><span class="sxs-lookup"><span data-stu-id="8068f-107">Steps to write a cmdlet</span></span>

1. <span data-ttu-id="8068f-108">クラスをコマンドレットとして宣言するには、 **コマンドレット** の属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="8068f-108">To declare the class as a cmdlet, use the **Cmdlet** attribute.</span></span> <span data-ttu-id="8068f-109">**コマンドレット** 属性では、コマンドレット名の動詞と名詞を指定します。</span><span class="sxs-lookup"><span data-stu-id="8068f-109">The **Cmdlet** attribute specifies the verb and the noun for the cmdlet name.</span></span>

   <span data-ttu-id="8068f-110">コマンドレット属性の詳細については、「**コマンドレット**[属性の宣言](cmdlet-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8068f-110">For more information about the **Cmdlet** attribute, see [CmdletAttribute Declaration](cmdlet-attribute-declaration.md).</span></span>

2. <span data-ttu-id="8068f-111">クラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8068f-111">Specify the name of the class.</span></span>

3. <span data-ttu-id="8068f-112">コマンドレットが次のいずれかのクラスから派生するように指定します。</span><span class="sxs-lookup"><span data-stu-id="8068f-112">Specify that the cmdlet derives from either of the following classes:</span></span>

   * [<span data-ttu-id="8068f-113">System. Automation. コマンドレット</span><span class="sxs-lookup"><span data-stu-id="8068f-113">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)
   * [<span data-ttu-id="8068f-114">PSCmdlet (システム管理)</span><span class="sxs-lookup"><span data-stu-id="8068f-114">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

4. <span data-ttu-id="8068f-115">コマンドレットのパラメーターを定義するには、 **Parameter** 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="8068f-115">To define the parameters for the cmdlet, use the **Parameter** attribute.</span></span> <span data-ttu-id="8068f-116">この場合、必須パラメーターが1つだけ指定されています。</span><span class="sxs-lookup"><span data-stu-id="8068f-116">In this case, only one required parameter is specified.</span></span>

   <span data-ttu-id="8068f-117">**Parameter** 属性の詳細については、「 [parameterattribute 宣言](parameter-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8068f-117">For more information about the **Parameter** attribute, see [ParameterAttribute Declaration](parameter-attribute-declaration.md).</span></span>

5. <span data-ttu-id="8068f-118">入力を処理する入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="8068f-118">Override the input processing method that processes the input.</span></span> <span data-ttu-id="8068f-119">この場合は、システムの管理.... [コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="8068f-119">In this case, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden.</span></span>

6. <span data-ttu-id="8068f-120">あいさつ文を記述するには、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8068f-120">To write the greeting, use the method [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span></span>
   <span data-ttu-id="8068f-121">あいさつは次の形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="8068f-121">The greeting is displayed in the following format:</span></span>

   ```Output
   Hello <UserName>!
   ```

## <a name="example"></a><span data-ttu-id="8068f-122">例</span><span class="sxs-lookup"><span data-stu-id="8068f-122">Example</span></span>

```csharp
using System.Management.Automation;  // Windows PowerShell assembly.

namespace SendGreeting
{
  // Declare the class as a cmdlet and specify the
  // appropriate verb and noun for the cmdlet name.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory=true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    // Override the ProcessRecord method to process
    // the supplied user name and write out a
    // greeting to the user by calling the WriteObject
    // method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "!");
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="8068f-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="8068f-123">See also</span></span>

[<span data-ttu-id="8068f-124">System. Automation. コマンドレット</span><span class="sxs-lookup"><span data-stu-id="8068f-124">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)

[<span data-ttu-id="8068f-125">PSCmdlet (システム管理)</span><span class="sxs-lookup"><span data-stu-id="8068f-125">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

[<span data-ttu-id="8068f-126">システムの管理....................</span><span class="sxs-lookup"><span data-stu-id="8068f-126">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="8068f-127">WriteObject (システム管理)</span><span class="sxs-lookup"><span data-stu-id="8068f-127">System.Management.Automation.Cmdlet.WriteObject</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[<span data-ttu-id="8068f-128">属性の宣言</span><span class="sxs-lookup"><span data-stu-id="8068f-128">CmdletAttribute Declaration</span></span>](cmdlet-attribute-declaration.md)

[<span data-ttu-id="8068f-129">ParameterAttribute の宣言</span><span class="sxs-lookup"><span data-stu-id="8068f-129">ParameterAttribute Declaration</span></span>](parameter-attribute-declaration.md)

[<span data-ttu-id="8068f-130">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="8068f-130">Writing a Windows PowerShell Cmdlet</span></span>](writing-a-windows-powershell-cmdlet.md)
