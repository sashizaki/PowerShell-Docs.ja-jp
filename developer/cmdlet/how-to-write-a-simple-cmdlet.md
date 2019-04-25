---
title: 単純なコマンドレットを記述する方法 |Microsoft Docs
ms.custom: ''
ms.date: 01/15/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 137543d8-0012-4cba-bcd6-98b25aac83bb
caps.latest.revision: 9
ms.openlocfilehash: 8271512d06047f3ff5e45f81d971ffe2c1f6afd7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067741"
---
# <a name="how-to-write-a-cmdlet"></a><span data-ttu-id="b545c-102">コマンドレットを記述する方法</span><span class="sxs-lookup"><span data-stu-id="b545c-102">How to write a cmdlet</span></span>

<span data-ttu-id="b545c-103">この記事では、コマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b545c-103">This article shows how to write a cmdlet.</span></span> <span data-ttu-id="b545c-104">`Send-Greeting`コマンドレットは入力として 1 人のユーザー名を受け取りし、そのユーザーにあいさつ文を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="b545c-104">The `Send-Greeting` cmdlet takes a single user name as input and then writes a greeting to that user.</span></span> <span data-ttu-id="b545c-105">コマンドレットは、多くの作業を実行しない、コマンドレットの主要なセクションでは、この例を示しています。</span><span class="sxs-lookup"><span data-stu-id="b545c-105">Although the cmdlet does not do much work, this example demonstrates the major sections of a cmdlet.</span></span>

## <a name="steps-to-write-a-cmdlet"></a><span data-ttu-id="b545c-106">コマンドレットを記述する手順について</span><span class="sxs-lookup"><span data-stu-id="b545c-106">Steps to write a cmdlet</span></span>

1. <span data-ttu-id="b545c-107">コマンドレットとクラスを宣言するには、使用、**コマンドレット**属性。</span><span class="sxs-lookup"><span data-stu-id="b545c-107">To declare the class as a cmdlet, use the **Cmdlet** attribute.</span></span> <span data-ttu-id="b545c-108">**コマンドレット**属性は、動詞と名詞コマンドレット名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b545c-108">The **Cmdlet** attribute specifies the verb and the noun for the cmdlet name.</span></span>

   <span data-ttu-id="b545c-109">詳細については、**コマンドレット**属性は、「 [CmdletAttribute 宣言](cmdlet-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="b545c-109">For more information about the **Cmdlet** attribute, see [CmdletAttribute Declaration](cmdlet-attribute-declaration.md).</span></span>

2. <span data-ttu-id="b545c-110">クラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b545c-110">Specify the name of the class.</span></span>

3. <span data-ttu-id="b545c-111">コマンドレットが、次のクラスのいずれかから派生したことを指定します。</span><span class="sxs-lookup"><span data-stu-id="b545c-111">Specify that the cmdlet derives from either of the following classes:</span></span>

   * [<span data-ttu-id="b545c-112">System.Management.Automation.Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b545c-112">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)
   * [<span data-ttu-id="b545c-113">System.Management.Automation.PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="b545c-113">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

4. <span data-ttu-id="b545c-114">コマンドレットのパラメーターを定義するには、使用、**パラメーター**属性。</span><span class="sxs-lookup"><span data-stu-id="b545c-114">To define the parameters for the cmdlet, use the **Parameter** attribute.</span></span> <span data-ttu-id="b545c-115">この場合、パラメーターが指定された 1 つだけが必要です。</span><span class="sxs-lookup"><span data-stu-id="b545c-115">In this case, only one required parameter is specified.</span></span>

   <span data-ttu-id="b545c-116">詳細については、**パラメーター**属性は、「 [ParameterAttribute 宣言](parameter-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="b545c-116">For more information about the **Parameter** attribute, see [ParameterAttribute Declaration](parameter-attribute-declaration.md).</span></span>

5. <span data-ttu-id="b545c-117">入力の処理、入力を処理するメソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="b545c-117">Override the input processing method that processes the input.</span></span> <span data-ttu-id="b545c-118">ここで、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="b545c-118">In this case, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden.</span></span>

6. <span data-ttu-id="b545c-119">応答メッセージを書き込むメソッドを使用して[System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)します。</span><span class="sxs-lookup"><span data-stu-id="b545c-119">To write the greeting, use the method [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span></span>
   <span data-ttu-id="b545c-120">応答メッセージは、次の形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="b545c-120">The greeting is displayed in the following format:</span></span>

   ```Output
   Hello <UserName>!
   ```

## <a name="example"></a><span data-ttu-id="b545c-121">例</span><span class="sxs-lookup"><span data-stu-id="b545c-121">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b545c-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="b545c-122">See also</span></span>

[<span data-ttu-id="b545c-123">System.Management.Automation.Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b545c-123">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)

[<span data-ttu-id="b545c-124">System.Management.Automation.PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="b545c-124">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

[<span data-ttu-id="b545c-125">System.Management.Automation.Cmdlet.ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="b545c-125">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="b545c-126">System.Management.Automation.Cmdlet.WriteObject</span><span class="sxs-lookup"><span data-stu-id="b545c-126">System.Management.Automation.Cmdlet.WriteObject</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[<span data-ttu-id="b545c-127">CmdletAttribute 宣言</span><span class="sxs-lookup"><span data-stu-id="b545c-127">CmdletAttribute Declaration</span></span>](cmdlet-attribute-declaration.md)

[<span data-ttu-id="b545c-128">ParameterAttribute 宣言</span><span class="sxs-lookup"><span data-stu-id="b545c-128">ParameterAttribute Declaration</span></span>](parameter-attribute-declaration.md)

[<span data-ttu-id="b545c-129">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="b545c-129">Writing a Windows PowerShell Cmdlet</span></span>](writing-a-windows-powershell-cmdlet.md)