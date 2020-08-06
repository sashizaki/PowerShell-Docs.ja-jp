---
title: パラメーターの別名 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e320eeb4d2ab91acf2116fdc817a50e93c82aead
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781989"
---
# <a name="parameter-aliases"></a><span data-ttu-id="a4e5d-102">パラメーターのエイリアス</span><span class="sxs-lookup"><span data-stu-id="a4e5d-102">Parameter Aliases</span></span>

<span data-ttu-id="a4e5d-103">コマンドレットのパラメーターには別名を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4e5d-103">Cmdlet parameters can also have aliases.</span></span> <span data-ttu-id="a4e5d-104">コマンドでパラメーターを入力または指定するときに、パラメーター名の代わりにエイリアスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4e5d-104">You can use the aliases instead of the parameter names when you type or specify the parameter in a command.</span></span>

## <a name="benefits-of-using-aliases"></a><span data-ttu-id="a4e5d-105">エイリアスを使用する利点</span><span class="sxs-lookup"><span data-stu-id="a4e5d-105">Benefits of Using Aliases</span></span>

<span data-ttu-id="a4e5d-106">パラメーターに別名を追加すると、次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="a4e5d-106">Adding aliases to parameters provides the following benefits.</span></span>

- <span data-ttu-id="a4e5d-107">コマンドレットが呼び出されたときに、ユーザーが完全なパラメーター名を使用する必要がないように、ショートカットを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="a4e5d-107">You can provide a shortcut so that the user does not have to use the complete parameter name when the cmdlet is called.</span></span> <span data-ttu-id="a4e5d-108">たとえば、パラメーター名 "ComputerName" の代わりに "CN" エイリアスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4e5d-108">For example, you could use the "CN" alias instead of the parameter name "ComputerName".</span></span>

- <span data-ttu-id="a4e5d-109">同じパラメーターに別の名前を指定する場合は、複数のエイリアスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="a4e5d-109">You can define multiple aliases if you want to provide different names for the same parameter.</span></span> <span data-ttu-id="a4e5d-110">同じデータをさまざまな方法で参照する複数のユーザーグループを操作する必要がある場合は、複数のエイリアスを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4e5d-110">You might want to define multiple aliases if you have to work with multiple user groups that refer to the same data in different ways.</span></span>

- <span data-ttu-id="a4e5d-111">パラメーターの名前が変更された場合は、既存のスクリプトに下位互換性を持たせることができます。</span><span class="sxs-lookup"><span data-stu-id="a4e5d-111">You can provide backwards compatibility for existing scripts if the name of a parameter changes.</span></span>

- <span data-ttu-id="a4e5d-112">Alias 属性を ValueFromPipelineByName 属性と共に使用することで、コマンドレットがさまざまなオブジェクトの種類にバインドできるようにするパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="a4e5d-112">By using the Alias attribute along with the ValueFromPipelineByName attribute, you can define a parameter that allows your cmdlet to bind to different object types.</span></span> <span data-ttu-id="a4e5d-113">たとえば、異なる型の2つのオブジェクトがあり、最初のオブジェクトが writer プロパティを持ち、2番目のオブジェクトにエディタープロパティがあるとします。</span><span class="sxs-lookup"><span data-stu-id="a4e5d-113">For example, say you had two objects of different types and the first object had a writer property and the second object had an editor property.</span></span> <span data-ttu-id="a4e5d-114">コマンドレットにライターとエディターのエイリアスを持つパラメーターがあり、コマンドレットがプロパティ名に基づくパイプライン入力を受け入れた場合、2つのパラメーターエイリアスを使用して、コマンドレットで両方のオブジェクトにバインドすることができます。</span><span class="sxs-lookup"><span data-stu-id="a4e5d-114">If your cmdlet had a parameter that had writer and editor aliases and the cmdlet accepted pipeline input based in property names, your cmdlet could bind to both objects using the two parameter aliases.</span></span>

<span data-ttu-id="a4e5d-115">特定のパラメーターと共に使用できるエイリアスの詳細については、「[共通パラメーター名](./common-parameter-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4e5d-115">For more information about aliases that can be used with specific parameters, see [Common Parameter Names](./common-parameter-names.md).</span></span>

## <a name="defining-parameter-aliases"></a><span data-ttu-id="a4e5d-116">パラメーターの別名の定義</span><span class="sxs-lookup"><span data-stu-id="a4e5d-116">Defining Parameter Aliases</span></span>

<span data-ttu-id="a4e5d-117">パラメーターのエイリアスを定義するには、次のパラメーター宣言に示すように、Alias 属性を宣言します。</span><span class="sxs-lookup"><span data-stu-id="a4e5d-117">To define an alias for a parameter, declare the Alias attribute, as shown in the following parameter declaration.</span></span> <span data-ttu-id="a4e5d-118">この例では、同じパラメーターに対して複数のエイリアスが定義されています。</span><span class="sxs-lookup"><span data-stu-id="a4e5d-118">In this example, multiple aliases are defined for the same parameter.</span></span> <span data-ttu-id="a4e5d-119">(詳細については、「[コマンドレットのパラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a4e5d-119">(For more information, see[How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).)</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a4e5d-120">参照</span><span class="sxs-lookup"><span data-stu-id="a4e5d-120">See Also</span></span>

[<span data-ttu-id="a4e5d-121">共有パラメーター名</span><span class="sxs-lookup"><span data-stu-id="a4e5d-121">Common Parameter Names</span></span>](./common-parameter-names.md)

[<span data-ttu-id="a4e5d-122">コマンドレット パラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="a4e5d-122">How to Declare Cmdlet Parameters</span></span>](./how-to-declare-cmdlet-parameters.md)

[<span data-ttu-id="a4e5d-123">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="a4e5d-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
