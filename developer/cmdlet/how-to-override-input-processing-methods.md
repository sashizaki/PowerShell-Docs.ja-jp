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
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056398"
---
# <a name="how-to-override-input-processing-methods"></a><span data-ttu-id="fb7df-102">入力処理メソッドをオーバーライドする方法</span><span class="sxs-lookup"><span data-stu-id="fb7df-102">How to Override Input Processing Methods</span></span>

<span data-ttu-id="fb7df-103">これらの例では、入力の処理をコマンドレット内のメソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fb7df-103">These examples show how to overwrite the input processing methods within a cmdlet.</span></span> <span data-ttu-id="fb7df-104">これらのメソッドは、次の操作を実行に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb7df-104">These methods are used to perform the following operations:</span></span>

- <span data-ttu-id="fb7df-105">[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)コマンドレットによって処理されたすべてのオブジェクトに対して有効では 1 回限りのスタートアップ操作を実行するメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb7df-105">The [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method is used to perform one-time startup operations that are valid for all the objects processed by the cmdlet.</span></span> <span data-ttu-id="fb7df-106">Windows PowerShell ランタイムでは、このメソッドを 1 回だけ呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fb7df-106">The Windows PowerShell runtime calls this method only once.</span></span>

- <span data-ttu-id="fb7df-107">[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)コマンドレットに渡されるオブジェクトを処理するメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb7df-107">The [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is used to process the objects passed to the cmdlet.</span></span> <span data-ttu-id="fb7df-108">Windows PowerShell ランタイムでは、コマンドレットに渡される各オブジェクトに対してこのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fb7df-108">The Windows PowerShell runtime calls this method for each object passed to the cmdlet.</span></span>

- <span data-ttu-id="fb7df-109">[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)投稿を 1 回限りの処理操作を実行するメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb7df-109">The [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method is used to perform one-time post processing operations.</span></span> <span data-ttu-id="fb7df-110">Windows PowerShell ランタイムでは、このメソッドを 1 回だけ呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fb7df-110">The Windows PowerShell runtime calls this method only once.</span></span>

## <a name="to-override-the-beginprocessing-method"></a><span data-ttu-id="fb7df-111">BeginProcessing メソッドをオーバーライドするには</span><span class="sxs-lookup"><span data-stu-id="fb7df-111">To override the BeginProcessing method</span></span>

- <span data-ttu-id="fb7df-112">保護されたオーバーライドを宣言、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッド。</span><span class="sxs-lookup"><span data-stu-id="fb7df-112">Declare a protected override of the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

<span data-ttu-id="fb7df-113">次のクラスは、サンプル メッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="fb7df-113">The following class prints a sample message.</span></span> <span data-ttu-id="fb7df-114">このクラスを使用する動詞と名詞コマンドレット属性での変更、新しい動詞と名詞を反映するようにクラスの名前を変更およびのオーバーライドを必要とする機能を追加し、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッド。</span><span class="sxs-lookup"><span data-stu-id="fb7df-114">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

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

## <a name="to-override-the-processrecord-method"></a><span data-ttu-id="fb7df-115">ProcessRecord メソッドをオーバーライドするには</span><span class="sxs-lookup"><span data-stu-id="fb7df-115">To override the ProcessRecord method</span></span>

- <span data-ttu-id="fb7df-116">保護されたオーバーライドを宣言、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。</span><span class="sxs-lookup"><span data-stu-id="fb7df-116">Declare a protected override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="fb7df-117">次のクラスは、サンプル メッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="fb7df-117">The following class prints a sample message.</span></span> <span data-ttu-id="fb7df-118">このクラスを使用する動詞と名詞コマンドレット属性での変更、新しい動詞と名詞を反映するようにクラスの名前を変更およびのオーバーライドを必要とする機能を追加し、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。</span><span class="sxs-lookup"><span data-stu-id="fb7df-118">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

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

## <a name="to-override-the-endprocessing-method"></a><span data-ttu-id="fb7df-119">EndProcessing メソッドをオーバーライドするには</span><span class="sxs-lookup"><span data-stu-id="fb7df-119">To override the EndProcessing method</span></span>

- <span data-ttu-id="fb7df-120">保護されたオーバーライドを宣言、 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド。</span><span class="sxs-lookup"><span data-stu-id="fb7df-120">Declare a protected override of the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

<span data-ttu-id="fb7df-121">次のクラスは、サンプルを印刷します。</span><span class="sxs-lookup"><span data-stu-id="fb7df-121">The following class prints a sample.</span></span> <span data-ttu-id="fb7df-122">このクラスを使用する動詞と名詞コマンドレット属性での変更、新しい動詞と名詞を反映するようにクラスの名前を変更およびのオーバーライドを必要とする機能を追加し、 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド。</span><span class="sxs-lookup"><span data-stu-id="fb7df-122">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="fb7df-123">参照</span><span class="sxs-lookup"><span data-stu-id="fb7df-123">See Also</span></span>

[<span data-ttu-id="fb7df-124">System.Management.Automation.Cmdlet.BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="fb7df-124">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="fb7df-125">System.Management.Automation.Cmdlet.EndProcessing</span><span class="sxs-lookup"><span data-stu-id="fb7df-125">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="fb7df-126">System.Management.Automation.Cmdlet.ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="fb7df-126">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="fb7df-127">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="fb7df-127">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
