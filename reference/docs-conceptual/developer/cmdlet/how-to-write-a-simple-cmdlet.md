---
title: '方法: 簡単なコマンドレットを記述する |Microsoft Docs'
ms.custom: ''
ms.date: 01/15/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 137543d8-0012-4cba-bcd6-98b25aac83bb
caps.latest.revision: 9
ms.openlocfilehash: 8271512d06047f3ff5e45f81d971ffe2c1f6afd7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365471"
---
# <a name="how-to-write-a-cmdlet"></a><span data-ttu-id="5c466-102">コマンドレットを記述する方法</span><span class="sxs-lookup"><span data-stu-id="5c466-102">How to write a cmdlet</span></span>

<span data-ttu-id="5c466-103">この記事では、コマンドレットを記述する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c466-103">This article shows how to write a cmdlet.</span></span> <span data-ttu-id="5c466-104">@No__t 0 のコマンドレットは、入力として1つのユーザー名を受け取り、そのユーザーにあいさつを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="5c466-104">The `Send-Greeting` cmdlet takes a single user name as input and then writes a greeting to that user.</span></span> <span data-ttu-id="5c466-105">このコマンドレットは多くの作業を実行しませんが、この例ではコマンドレットの主要なセクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="5c466-105">Although the cmdlet does not do much work, this example demonstrates the major sections of a cmdlet.</span></span>

## <a name="steps-to-write-a-cmdlet"></a><span data-ttu-id="5c466-106">コマンドレットを記述する手順</span><span class="sxs-lookup"><span data-stu-id="5c466-106">Steps to write a cmdlet</span></span>

1. <span data-ttu-id="5c466-107">クラスをコマンドレットとして宣言するには、**コマンドレット**の属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c466-107">To declare the class as a cmdlet, use the **Cmdlet** attribute.</span></span> <span data-ttu-id="5c466-108">**コマンドレット**属性では、コマンドレット名の動詞と名詞を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c466-108">The **Cmdlet** attribute specifies the verb and the noun for the cmdlet name.</span></span>

   <span data-ttu-id="5c466-109">コマンドレット属性の詳細については、「**コマンドレット**[属性の宣言](cmdlet-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c466-109">For more information about the **Cmdlet** attribute, see [CmdletAttribute Declaration](cmdlet-attribute-declaration.md).</span></span>

2. <span data-ttu-id="5c466-110">クラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c466-110">Specify the name of the class.</span></span>

3. <span data-ttu-id="5c466-111">コマンドレットが次のいずれかのクラスから派生するように指定します。</span><span class="sxs-lookup"><span data-stu-id="5c466-111">Specify that the cmdlet derives from either of the following classes:</span></span>

   * [<span data-ttu-id="5c466-112">System. Automation. コマンドレット</span><span class="sxs-lookup"><span data-stu-id="5c466-112">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)
   * [<span data-ttu-id="5c466-113">PSCmdlet (システム管理)</span><span class="sxs-lookup"><span data-stu-id="5c466-113">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

4. <span data-ttu-id="5c466-114">コマンドレットのパラメーターを定義するには、 **Parameter**属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c466-114">To define the parameters for the cmdlet, use the **Parameter** attribute.</span></span> <span data-ttu-id="5c466-115">この場合、必須パラメーターが1つだけ指定されています。</span><span class="sxs-lookup"><span data-stu-id="5c466-115">In this case, only one required parameter is specified.</span></span>

   <span data-ttu-id="5c466-116">**Parameter**属性の詳細については、「 [parameterattribute 宣言](parameter-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c466-116">For more information about the **Parameter** attribute, see [ParameterAttribute Declaration](parameter-attribute-declaration.md).</span></span>

5. <span data-ttu-id="5c466-117">入力を処理する入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="5c466-117">Override the input processing method that processes the input.</span></span> <span data-ttu-id="5c466-118">この場合は、システムの管理....[コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="5c466-118">In this case, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden.</span></span>

6. <span data-ttu-id="5c466-119">あいさつ文を記述するには、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5c466-119">To write the greeting, use the method [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span></span>
   <span data-ttu-id="5c466-120">あいさつは次の形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c466-120">The greeting is displayed in the following format:</span></span>

   ```Output
   Hello <UserName>!
   ```

## <a name="example"></a><span data-ttu-id="5c466-121">例</span><span class="sxs-lookup"><span data-stu-id="5c466-121">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5c466-122">「</span><span class="sxs-lookup"><span data-stu-id="5c466-122">See also</span></span>

[<span data-ttu-id="5c466-123">System. Automation. コマンドレット</span><span class="sxs-lookup"><span data-stu-id="5c466-123">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)

[<span data-ttu-id="5c466-124">PSCmdlet (システム管理)</span><span class="sxs-lookup"><span data-stu-id="5c466-124">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

[<span data-ttu-id="5c466-125">システムの管理....................</span><span class="sxs-lookup"><span data-stu-id="5c466-125">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="5c466-126">WriteObject (システム管理)</span><span class="sxs-lookup"><span data-stu-id="5c466-126">System.Management.Automation.Cmdlet.WriteObject</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[<span data-ttu-id="5c466-127">属性の宣言</span><span class="sxs-lookup"><span data-stu-id="5c466-127">CmdletAttribute Declaration</span></span>](cmdlet-attribute-declaration.md)

[<span data-ttu-id="5c466-128">ParameterAttribute の宣言</span><span class="sxs-lookup"><span data-stu-id="5c466-128">ParameterAttribute Declaration</span></span>](parameter-attribute-declaration.md)

[<span data-ttu-id="5c466-129">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="5c466-129">Writing a Windows PowerShell Cmdlet</span></span>](writing-a-windows-powershell-cmdlet.md)