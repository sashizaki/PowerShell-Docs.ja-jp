---
title: パラメーターの別名 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c9096a1-46fa-48ea-9b8a-a583484b9d68
caps.latest.revision: 13
ms.openlocfilehash: 6545e71ea18d10621ee9c203e70f64dece460ef5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369591"
---
# <a name="parameter-aliases"></a><span data-ttu-id="46934-102">パラメーターのエイリアス</span><span class="sxs-lookup"><span data-stu-id="46934-102">Parameter Aliases</span></span>

<span data-ttu-id="46934-103">コマンドレット パラメーターはエイリアスを持つこともできます。</span><span class="sxs-lookup"><span data-stu-id="46934-103">Cmdlet parameters can also have aliases.</span></span> <span data-ttu-id="46934-104">コマンドでパラメーターを入力または指定するときに、パラメーター名の代わりにエイリアスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="46934-104">You can use the aliases instead of the parameter names when you type or specify the parameter in a command.</span></span>

## <a name="benefits-of-using-aliases"></a><span data-ttu-id="46934-105">エイリアスを使用する利点</span><span class="sxs-lookup"><span data-stu-id="46934-105">Benefits of Using Aliases</span></span>

<span data-ttu-id="46934-106">パラメーターに別名を追加すると、次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="46934-106">Adding aliases to parameters provides the following benefits.</span></span>

- <span data-ttu-id="46934-107">コマンドレットが呼び出されたときに、ユーザーが完全なパラメーター名を使用する必要がないように、ショートカットを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="46934-107">You can provide a shortcut so that the user does not have to use the complete parameter name when the cmdlet is called.</span></span> <span data-ttu-id="46934-108">たとえば、パラメーター名 "ComputerName" の代わりに "CN" エイリアスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="46934-108">For example, you could use the "CN" alias instead of the parameter name "ComputerName".</span></span>

- <span data-ttu-id="46934-109">同じパラメーターに別の名前を指定する場合は、複数のエイリアスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="46934-109">You can define multiple aliases if you want to provide different names for the same parameter.</span></span> <span data-ttu-id="46934-110">同じデータをさまざまな方法で参照する複数のユーザーグループを操作する必要がある場合は、複数のエイリアスを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="46934-110">You might want to define multiple aliases if you have to work with multiple user groups that refer to the same data in different ways.</span></span>

- <span data-ttu-id="46934-111">パラメーターの名前が変更された場合は、既存のスクリプトに下位互換性を持たせることができます。</span><span class="sxs-lookup"><span data-stu-id="46934-111">You can provide backwards compatibility for existing scripts if the name of a parameter changes.</span></span>

- <span data-ttu-id="46934-112">Alias 属性を ValueFromPipelineByName 属性と共に使用することで、コマンドレットがさまざまなオブジェクトの種類にバインドできるようにするパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="46934-112">By using the Alias attribute along with the ValueFromPipelineByName attribute, you can define a parameter that allows your cmdlet to bind to different object types.</span></span> <span data-ttu-id="46934-113">たとえば、異なる型の2つのオブジェクトがあり、最初のオブジェクトが writer プロパティを持ち、2番目のオブジェクトにエディタープロパティがあるとします。</span><span class="sxs-lookup"><span data-stu-id="46934-113">For example, say you had two objects of different types and the first object had a writer property and the second object had an editor property.</span></span> <span data-ttu-id="46934-114">コマンドレットにライターとエディターのエイリアスを持つパラメーターがあり、コマンドレットがプロパティ名に基づくパイプライン入力を受け入れた場合、2つのパラメーターエイリアスを使用して、コマンドレットで両方のオブジェクトにバインドすることができます。</span><span class="sxs-lookup"><span data-stu-id="46934-114">If your cmdlet had a parameter that had writer and editor aliases and the cmdlet accepted pipeline input based in property names, your cmdlet could bind to both objects using the two parameter aliases.</span></span>

<span data-ttu-id="46934-115">特定のパラメーターと共に使用できるエイリアスの詳細については、「[共通パラメーター名](./common-parameter-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46934-115">For more information about aliases that can be used with specific parameters, see [Common Parameter Names](./common-parameter-names.md).</span></span>

## <a name="defining-parameter-aliases"></a><span data-ttu-id="46934-116">パラメーターの別名の定義</span><span class="sxs-lookup"><span data-stu-id="46934-116">Defining Parameter Aliases</span></span>

<span data-ttu-id="46934-117">パラメーターのエイリアスを定義するには、次のパラメーター宣言に示すように、Alias 属性を宣言します。</span><span class="sxs-lookup"><span data-stu-id="46934-117">To define an alias for a parameter, declare the Alias attribute, as shown in the following parameter declaration.</span></span> <span data-ttu-id="46934-118">この例では、同じパラメーターに対して複数のエイリアスが定義されています。</span><span class="sxs-lookup"><span data-stu-id="46934-118">In this example, multiple aliases are defined for the same parameter.</span></span> <span data-ttu-id="46934-119">(詳細については、「[コマンドレットのパラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="46934-119">(For more information, see[How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).)</span></span>

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

## <a name="see-also"></a><span data-ttu-id="46934-120">参照</span><span class="sxs-lookup"><span data-stu-id="46934-120">See Also</span></span>

[<span data-ttu-id="46934-121">共通パラメーター名</span><span class="sxs-lookup"><span data-stu-id="46934-121">Common Parameter Names</span></span>](./common-parameter-names.md)

[<span data-ttu-id="46934-122">コマンドレットのパラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="46934-122">How to Declare Cmdlet Parameters</span></span>](./how-to-declare-cmdlet-parameters.md)

[<span data-ttu-id="46934-123">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="46934-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
