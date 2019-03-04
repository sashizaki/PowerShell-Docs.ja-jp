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
ms.openlocfilehash: eff40a01b60985788ae0e21156fec7ec4e27fcf1
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855918"
---
# <a name="how-to-override-input-processing-methods"></a><span data-ttu-id="78f13-102">入力処理メソッドをオーバーライドする方法</span><span class="sxs-lookup"><span data-stu-id="78f13-102">How to Override Input Processing Methods</span></span>

<span data-ttu-id="78f13-103">これらの例では、入力の処理をコマンドレット内のメソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="78f13-103">These examples show how to overwrite the input processing methods within a cmdlet.</span></span> <span data-ttu-id="78f13-104">これらのメソッドは、次の操作を実行に使用されます。</span><span class="sxs-lookup"><span data-stu-id="78f13-104">These methods are used to perform the following operations:</span></span>

- <span data-ttu-id="78f13-105">[System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)コマンドレットによって処理されたすべてのオブジェクトに対して有効では 1 回限りのスタートアップ操作を実行するメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="78f13-105">The [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method is used to perform one-time startup operations that are valid for all the objects processed by the cmdlet.</span></span> <span data-ttu-id="78f13-106">Windows PowerShell ランタイムでは、このメソッドを 1 回だけ呼び出します。</span><span class="sxs-lookup"><span data-stu-id="78f13-106">The Windows PowerShell runtime calls this method only once.</span></span>

- <span data-ttu-id="78f13-107">[System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)コマンドレットに渡されるオブジェクトを処理するメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="78f13-107">The [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is used to process the objects passed to the cmdlet.</span></span> <span data-ttu-id="78f13-108">Windows PowerShell ランタイムでは、コマンドレットに渡される各オブジェクトに対してこのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="78f13-108">The Windows PowerShell runtime calls this method for each object passed to the cmdlet.</span></span>

- <span data-ttu-id="78f13-109">[System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)投稿を 1 回限りの処理操作を実行するメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="78f13-109">The [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method is used to perform one-time post processing operations.</span></span> <span data-ttu-id="78f13-110">Windows PowerShell ランタイムでは、このメソッドを 1 回だけ呼び出します。</span><span class="sxs-lookup"><span data-stu-id="78f13-110">The Windows PowerShell runtime calls this method only once.</span></span>

## <a name="to-override-the-beginprocessing-method"></a><span data-ttu-id="78f13-111">BeginProcessing メソッドをオーバーライドするには</span><span class="sxs-lookup"><span data-stu-id="78f13-111">To override the BeginProcessing method</span></span>

- <span data-ttu-id="78f13-112">保護されたオーバーライドを宣言、 [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッド。</span><span class="sxs-lookup"><span data-stu-id="78f13-112">Declare a protected override of the [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

<span data-ttu-id="78f13-113">次のクラスは、サンプル メッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="78f13-113">The following class prints a sample message.</span></span> <span data-ttu-id="78f13-114">このクラスを使用する動詞と名詞コマンドレット属性での変更、新しい動詞と名詞を反映するようにクラスの名前を変更およびのオーバーライドを必要とする機能を追加し、 [System.Management.Automation.Cmdlet.Beginprocessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッド。</span><span class="sxs-lookup"><span data-stu-id="78f13-114">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method.</span></span>

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

## <a name="to-override-the-processrecord-method"></a><span data-ttu-id="78f13-115">ProcessRecord メソッドをオーバーライドするには</span><span class="sxs-lookup"><span data-stu-id="78f13-115">To override the ProcessRecord method</span></span>

- <span data-ttu-id="78f13-116">保護されたオーバーライドを宣言、 [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。</span><span class="sxs-lookup"><span data-stu-id="78f13-116">Declare a protected override of the [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="78f13-117">次のクラスは、サンプル メッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="78f13-117">The following class prints a sample message.</span></span> <span data-ttu-id="78f13-118">このクラスを使用する動詞と名詞コマンドレット属性での変更、新しい動詞と名詞を反映するようにクラスの名前を変更およびのオーバーライドを必要とする機能を追加し、 [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。</span><span class="sxs-lookup"><span data-stu-id="78f13-118">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

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

## <a name="to-override-the-endprocessing-method"></a><span data-ttu-id="78f13-119">EndProcessing メソッドをオーバーライドするには</span><span class="sxs-lookup"><span data-stu-id="78f13-119">To override the EndProcessing method</span></span>

- <span data-ttu-id="78f13-120">保護されたオーバーライドを宣言、 [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド。</span><span class="sxs-lookup"><span data-stu-id="78f13-120">Declare a protected override of the [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

<span data-ttu-id="78f13-121">次のクラスは、サンプルを印刷します。</span><span class="sxs-lookup"><span data-stu-id="78f13-121">The following class prints a sample.</span></span> <span data-ttu-id="78f13-122">このクラスを使用する動詞と名詞コマンドレット属性での変更、新しい動詞と名詞を反映するようにクラスの名前を変更およびのオーバーライドを必要とする機能を追加し、 [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド。</span><span class="sxs-lookup"><span data-stu-id="78f13-122">To use this class, change the verb and noun in the Cmdlet attribute, change the name of the class to reflect the new verb and noun, and then add the functionality you require to the override of the [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="78f13-123">参照</span><span class="sxs-lookup"><span data-stu-id="78f13-123">See Also</span></span>

[<span data-ttu-id="78f13-124">System.Management.Automation.Cmdlet.Beginprocessing\*</span><span class="sxs-lookup"><span data-stu-id="78f13-124">System.Management.Automation.Cmdlet.Beginprocessing\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="78f13-125">System.Management.Automation.Cmdlet.Endprocessing\*</span><span class="sxs-lookup"><span data-stu-id="78f13-125">System.Management.Automation.Cmdlet.Endprocessing\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="78f13-126">System.Management.Automation.Cmdlet.Processrecord\*</span><span class="sxs-lookup"><span data-stu-id="78f13-126">System.Management.Automation.Cmdlet.Processrecord\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="78f13-127">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="78f13-127">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
