---
title: 入力処理メソッドをオーバーライドする方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a1ad921-5816-4937-acf1-ed4760fae740
caps.latest.revision: 8
ms.openlocfilehash: cfee55576518cf9ce38501192872ce94054f5213
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364471"
---
# <a name="how-to-override-input-processing-methods"></a><span data-ttu-id="f7a4c-102">入力処理メソッドをオーバーライドする方法</span><span class="sxs-lookup"><span data-stu-id="f7a4c-102">How to Override Input Processing Methods</span></span>

<span data-ttu-id="f7a4c-103">これらの例は、コマンドレット内の入力処理メソッドを上書きする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f7a4c-103">These examples show how to overwrite the input processing methods within a cmdlet.</span></span> <span data-ttu-id="f7a4c-104">これらのメソッドは、次の操作を実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7a4c-104">These methods are used to perform the following operations:</span></span>

- <span data-ttu-id="f7a4c-105">コマンドレットによって処理されるすべてのオブジェクトに対して有効な1回限りのスタートアップ操作を実行するには、[このメソッドを](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)使用します。</span><span class="sxs-lookup"><span data-stu-id="f7a4c-105">The [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method is used to perform one-time startup operations that are valid for all the objects processed by the cmdlet.</span></span> <span data-ttu-id="f7a4c-106">Windows PowerShell ランタイムは、このメソッドを1回だけ呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f7a4c-106">The Windows PowerShell runtime calls this method only once.</span></span>

- <span data-ttu-id="f7a4c-107">コマンドレットに渡されたオブジェクトを処理するには、.................. [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7a4c-107">The [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is used to process the objects passed to the cmdlet.</span></span> <span data-ttu-id="f7a4c-108">Windows PowerShell ランタイムは、コマンドレットに渡された各オブジェクトに対してこのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f7a4c-108">The Windows PowerShell runtime calls this method for each object passed to the cmdlet.</span></span>

- <span data-ttu-id="f7a4c-109">1回限りの処理操作を実行するには、system.servicemodel メソッドを[使用します](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)。</span><span class="sxs-lookup"><span data-stu-id="f7a4c-109">The [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method is used to perform one-time post processing operations.</span></span> <span data-ttu-id="f7a4c-110">Windows PowerShell ランタイムは、このメソッドを1回だけ呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f7a4c-110">The Windows PowerShell runtime calls this method only once.</span></span>

## <a name="to-override-the-beginprocessing-method"></a><span data-ttu-id="f7a4c-111">BeginProcessing メソッドをオーバーライドするには</span><span class="sxs-lookup"><span data-stu-id="f7a4c-111">To override the BeginProcessing method</span></span>

- <span data-ttu-id="f7a4c-112">[システム](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)の保護されたオーバーライドを宣言してください。</span><span class="sxs-lookup"><span data-stu-id="f7a4c-112">Declare a protected override of the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

<span data-ttu-id="f7a4c-113">次のクラスは、サンプルメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="f7a4c-113">The following class prints a sample message.</span></span> <span data-ttu-id="f7a4c-114">このクラスを使用するには、コマンドレット属性の動詞と名詞を変更し、新しい動詞と名詞を反映するようにクラスの名前を変更します。次に、必要な機能を、[システム](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)のオーバーライドに追加します。b.</span><span class="sxs-lookup"><span data-stu-id="f7a4c-114">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "BeginProcessingClass")]
public class TestBeginProcessingClassTemplate : Cmdlet
{
  // Override the BeginProcessing method to add preprocessing
  //operations to the cmdlet.
  protected override void BeginProcessing()
  {
    // Replace the WriteObject method with the logic required
    // by your cmdlet. It is used here to generate the following
    // output:
    // "This is a test of the BeginProcessing template."
    WriteObject("This is a test of the BeginProcessing template.");
  }
}
```

## <a name="to-override-the-processrecord-method"></a><span data-ttu-id="f7a4c-115">ProcessRecord メソッドをオーバーライドするには</span><span class="sxs-lookup"><span data-stu-id="f7a4c-115">To override the ProcessRecord method</span></span>

- <span data-ttu-id="f7a4c-116">保護されたオーバーライドを宣言して、このメソッドを[宣言します](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)。</span><span class="sxs-lookup"><span data-stu-id="f7a4c-116">Declare a protected override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="f7a4c-117">次のクラスは、サンプルメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="f7a4c-117">The following class prints a sample message.</span></span> <span data-ttu-id="f7a4c-118">このクラスを使用するには、コマンドレット属性の動詞と名詞を変更し、新しい動詞と名詞を反映するようにクラスの名前を変更します。次に、必要な機能を、[このメソッドの](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)オーバーライドに追加します。</span><span class="sxs-lookup"><span data-stu-id="f7a4c-118">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "ProcessRecordClass")]
public class TestProcessRecordClassTemplate : Cmdlet
{
    // Override the ProcessRecord method to add processing
    //operations to the cmdlet.
    protected override void ProcessRecord()
    {
        // Replace the WriteObject method with the logic required
        // by your cmdlet. It is used here to generate the following
        // output:
        // "This is a test of the ProcessRecord template."
        WriteObject("This is a test of the ProcessRecord template.");
    }
}

```

## <a name="to-override-the-endprocessing-method"></a><span data-ttu-id="f7a4c-119">EndProcessing メソッドをオーバーライドするには</span><span class="sxs-lookup"><span data-stu-id="f7a4c-119">To override the EndProcessing method</span></span>

- <span data-ttu-id="f7a4c-120">System.object メソッドの保護されたオーバーライドを宣言し[ます。](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)</span><span class="sxs-lookup"><span data-stu-id="f7a4c-120">Declare a protected override of the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

<span data-ttu-id="f7a4c-121">次のクラスは、サンプルを出力します。</span><span class="sxs-lookup"><span data-stu-id="f7a4c-121">The following class prints a sample.</span></span> <span data-ttu-id="f7a4c-122">このクラスを使用するには、コマンドレット属性の動詞と名詞を変更し、新しい動詞と名詞を反映するようにクラスの名前を変更します。次に、必要な機能を、[システム](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)のオーバーライドメソッドのオーバーライドに追加します。</span><span class="sxs-lookup"><span data-stu-id="f7a4c-122">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "EndProcessingClass")]
public class TestEndProcessingClassTemplate : Cmdlet
{
  // Override the EndProcessing method to add postprocessing
  //operations to the cmdlet.
  protected override void EndProcessing()
  {
    // Replace the WriteObject method with the logic required
    // by your cmdlet. It is used here to generate the following
    // output:
    // "This is a test of the BeginProcessing template."
    WriteObject("This is a test of the EndProcessing template.");
  }
}
```

## <a name="see-also"></a><span data-ttu-id="f7a4c-123">参照</span><span class="sxs-lookup"><span data-stu-id="f7a4c-123">See Also</span></span>

[<span data-ttu-id="f7a4c-124">システムの管理... コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f7a4c-124">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="f7a4c-125">システムの管理... コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f7a4c-125">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="f7a4c-126">システムの管理....................</span><span class="sxs-lookup"><span data-stu-id="f7a4c-126">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="f7a4c-127">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="f7a4c-127">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
