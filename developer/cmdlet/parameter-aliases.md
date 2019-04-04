---
title: パラメーターのエイリアス |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c9096a1-46fa-48ea-9b8a-a583484b9d68
caps.latest.revision: 13
ms.openlocfilehash: 6545e71ea18d10621ee9c203e70f64dece460ef5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853318"
---
# <a name="parameter-aliases"></a><span data-ttu-id="d1237-102">パラメーターのエイリアス</span><span class="sxs-lookup"><span data-stu-id="d1237-102">Parameter Aliases</span></span>

<span data-ttu-id="d1237-103">コマンドレットのパラメーターは、エイリアスをこともできます。</span><span class="sxs-lookup"><span data-stu-id="d1237-103">Cmdlet parameters can also have aliases.</span></span> <span data-ttu-id="d1237-104">入力するかのコマンドで、パラメーターを指定する場合は、パラメーター名の代わりにエイリアスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1237-104">You can use the aliases instead of the parameter names when you type or specify the parameter in a command.</span></span>

## <a name="benefits-of-using-aliases"></a><span data-ttu-id="d1237-105">エイリアスを使用する利点</span><span class="sxs-lookup"><span data-stu-id="d1237-105">Benefits of Using Aliases</span></span>

<span data-ttu-id="d1237-106">パラメーターにエイリアスを追加するには、次の利点が提供します。</span><span class="sxs-lookup"><span data-stu-id="d1237-106">Adding aliases to parameters provides the following benefits.</span></span>

- <span data-ttu-id="d1237-107">ユーザーが、コマンドレットが呼び出されたときに、完全なパラメーター名を使用する必要があるないようにショートカットを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d1237-107">You can provide a shortcut so that the user does not have to use the complete parameter name when the cmdlet is called.</span></span> <span data-ttu-id="d1237-108">たとえば、"ComputerName"パラメーター名の代わりに、"CN"エイリアスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1237-108">For example, you could use the "CN" alias instead of the parameter name "ComputerName".</span></span>

- <span data-ttu-id="d1237-109">同じパラメーターに対して異なる名前を指定する場合は、複数のエイリアスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="d1237-109">You can define multiple aliases if you want to provide different names for the same parameter.</span></span> <span data-ttu-id="d1237-110">さまざまな方法で、同じデータを参照する複数のユーザー グループを使用する必要がある場合は、複数のエイリアスを定義する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1237-110">You might want to define multiple aliases if you have to work with multiple user groups that refer to the same data in different ways.</span></span>

- <span data-ttu-id="d1237-111">行うことができます下位互換性の既存のスクリプトのパラメーターの名前が変更された場合。</span><span class="sxs-lookup"><span data-stu-id="d1237-111">You can provide backwards compatibility for existing scripts if the name of a parameter changes.</span></span>

- <span data-ttu-id="d1237-112">ValueFromPipelineByName 属性とエイリアス属性を使用するにはのコマンドレットを別のオブジェクトの型にバインドできるようにするパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="d1237-112">By using the Alias attribute along with the ValueFromPipelineByName attribute, you can define a parameter that allows your cmdlet to bind to different object types.</span></span> <span data-ttu-id="d1237-113">たとえば、最初のオブジェクトがライターのプロパティと 2 番目のオブジェクトには、エディター プロパティがありました。 さまざまな種類の 2 つのオブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1237-113">For example, say you had two objects of different types and the first object had a writer property and the second object had an editor property.</span></span> <span data-ttu-id="d1237-114">コマンドレットが含まれていたパラメーターがある場合、ライターおよびエディターのエイリアスとコマンドレットは、プロパティ名に基づくパイプライン入力を受け入れ、コマンドレットは、2 つのパラメーターのエイリアスを使用して両方のオブジェクトへバインドできます。</span><span class="sxs-lookup"><span data-stu-id="d1237-114">If your cmdlet had a parameter that had writer and editor aliases and the cmdlet accepted pipeline input based in property names, your cmdlet could bind to both objects using the two parameter aliases.</span></span>

<span data-ttu-id="d1237-115">特定のパラメーターで使用できるエイリアスに関する詳細については、[パラメーターの共通名](./common-parameter-names.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1237-115">For more information about aliases that can be used with specific parameters, see [Common Parameter Names](./common-parameter-names.md).</span></span>

## <a name="defining-parameter-aliases"></a><span data-ttu-id="d1237-116">パラメーターのエイリアスを定義します。</span><span class="sxs-lookup"><span data-stu-id="d1237-116">Defining Parameter Aliases</span></span>

<span data-ttu-id="d1237-117">パラメーターのエイリアスを定義するには、次のパラメーターの宣言で示すように、エイリアス属性を宣言します。</span><span class="sxs-lookup"><span data-stu-id="d1237-117">To define an alias for a parameter, declare the Alias attribute, as shown in the following parameter declaration.</span></span> <span data-ttu-id="d1237-118">この例では、複数のエイリアスは、同じパラメーターに対して定義されます。</span><span class="sxs-lookup"><span data-stu-id="d1237-118">In this example, multiple aliases are defined for the same parameter.</span></span> <span data-ttu-id="d1237-119">(詳細については、次を参照してください[コマンドレット パラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)。)。</span><span class="sxs-lookup"><span data-stu-id="d1237-119">(For more information, see[How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).)</span></span>

```csharp
[Alias("UN","Writer","Editor")]
[Parameter()]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="see-also"></a><span data-ttu-id="d1237-120">参照</span><span class="sxs-lookup"><span data-stu-id="d1237-120">See Also</span></span>

[<span data-ttu-id="d1237-121">一般的なパラメーター名</span><span class="sxs-lookup"><span data-stu-id="d1237-121">Common Parameter Names</span></span>](./common-parameter-names.md)

[<span data-ttu-id="d1237-122">コマンドレットのパラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="d1237-122">How to Declare Cmdlet Parameters</span></span>](./how-to-declare-cmdlet-parameters.md)

[<span data-ttu-id="d1237-123">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="d1237-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
