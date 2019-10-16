---
title: コマンドレットクラス宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell SDK], declaring
- declaring cmdlets [PowerShell SDK]
ms.assetid: 1fcc4c5e-0c75-496c-a712-5f844e310576
caps.latest.revision: 14
ms.openlocfilehash: 979025ad5c34ab73dcc23d0e38ffb9acc431f15a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363521"
---
# <a name="cmdlet-class-declaration"></a><span data-ttu-id="d29a1-102">コマンドレットのクラス宣言</span><span class="sxs-lookup"><span data-stu-id="d29a1-102">Cmdlet Class Declaration</span></span>

<span data-ttu-id="d29a1-103">Microsoft .NET Framework クラスは、クラスのメタデータとして**コマンドレット**属性を指定することで、コマンドレットとして宣言されます。</span><span class="sxs-lookup"><span data-stu-id="d29a1-103">A Microsoft .NET Framework class is declared as a cmdlet by specifying the **Cmdlet** attribute as metadata for the class.</span></span> <span data-ttu-id="d29a1-104">(**コマンドレット**属性は、すべてのコマンドレットに必要な唯一の属性です)。</span><span class="sxs-lookup"><span data-stu-id="d29a1-104">(The **Cmdlet** attribute is the only required attribute for all cmdlets).</span></span> <span data-ttu-id="d29a1-105">**コマンドレット**の属性を指定する場合は、コマンドレットを識別する動詞と名詞のペアをユーザーに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d29a1-105">When you specify the **Cmdlet** attribute, you must specify the verb-and-noun pair that identifies the cmdlet to the user.</span></span> <span data-ttu-id="d29a1-106">また、コマンドレットがサポートする Windows PowerShell の機能について説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d29a1-106">And, you must describe the Windows PowerShell functionality that the cmdlet supports.</span></span> <span data-ttu-id="d29a1-107">**コマンドレット**属性の指定に使用される宣言構文の詳細については、「[コマンドレット属性の宣言](./cmdlet-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d29a1-107">For more information about the declaration syntax that is used to specify the **Cmdlet** attribute, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d29a1-108">**コマンドレット**属性は、system.servicemodel[属性](/dotnet/api/System.Management.Automation.CmdletAttribute)クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="d29a1-108">The **Cmdlet** attribute is defined by the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) class.</span></span> <span data-ttu-id="d29a1-109">このクラスのプロパティは、属性を宣言するときに使用される宣言パラメーターに対応します。</span><span class="sxs-lookup"><span data-stu-id="d29a1-109">The properties of this class correspond to the declaration parameters that are used when you declare the attribute.</span></span>

## <a name="nouns"></a><span data-ttu-id="d29a1-110">名詞</span><span class="sxs-lookup"><span data-stu-id="d29a1-110">Nouns</span></span>

<span data-ttu-id="d29a1-111">コマンドレットの名詞は、コマンドレットが処理するリソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="d29a1-111">The noun of the cmdlet specifies the resources upon which the cmdlet acts.</span></span> <span data-ttu-id="d29a1-112">名詞は、コマンドレットを他のコマンドレットと区別します。</span><span class="sxs-lookup"><span data-stu-id="d29a1-112">The noun differentiates your cmdlets from other cmdlets.</span></span>

<span data-ttu-id="d29a1-113">コマンドレット名の名詞は固有である必要があります。また、*サーバー*などの汎用名詞の場合は、リソースを他の類似リソースと区別する短いプレフィックスを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d29a1-113">Nouns in cmdlet names must be specific, and in the case of generic nouns, such as *server*, it is best to add a short prefix that differentiates your resource from other similar resources.</span></span> <span data-ttu-id="d29a1-114">たとえば、プレフィックスを持つ名詞を含むコマンドレット名は、`Get-SQLServer` です。</span><span class="sxs-lookup"><span data-stu-id="d29a1-114">For example, a cmdlet name that includes a noun with a prefix is `Get-SQLServer`.</span></span> <span data-ttu-id="d29a1-115">特定の名詞とより一般的な動詞を組み合わせることで、ユーザーはコマンドレットをアクションですばやく検索し、不要なコマンドレット名の重複を回避して、コマンドレットをリソースで識別できます。</span><span class="sxs-lookup"><span data-stu-id="d29a1-115">The combination of a specific noun with a more general verb enables the user to quickly locate the cmdlet by its action and then identify the cmdlet by its resource while avoiding unnecessary cmdlet name duplication.</span></span>

<span data-ttu-id="d29a1-116">コマンドレット名に使用できない特殊文字の一覧については、「[必要な開発ガイドライン](./required-development-guidelines.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d29a1-116">For a list of special characters that cannot be used in cmdlet names, see [Required Development Guidelines](./required-development-guidelines.md).</span></span>

## <a name="verbs"></a><span data-ttu-id="d29a1-117">[動詞]</span><span class="sxs-lookup"><span data-stu-id="d29a1-117">Verbs</span></span>

<span data-ttu-id="d29a1-118">動詞を指定する場合、開発ガイドラインでは、Windows PowerShell によって提供される定義済み動詞のいずれかを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d29a1-118">When you specify a verb, the development guidelines require you to use one of the predefined verbs provided by Windows PowerShell.</span></span> <span data-ttu-id="d29a1-119">これらの定義済み動詞のいずれかを使用すると、作成したコマンドレットと、Microsoft によって作成されたコマンドレットと他のコマンドレットとの間の一貫性が確保されます。</span><span class="sxs-lookup"><span data-stu-id="d29a1-119">By using one of these predefined verbs, you will ensure consistency between the cmdlets that you write and the cmdlets that are written by Microsoft and by others.</span></span> <span data-ttu-id="d29a1-120">たとえば、データを取得するコマンドレットには、"Get" 動詞を使用します。</span><span class="sxs-lookup"><span data-stu-id="d29a1-120">For example, the "Get" verb is used for cmdlets that retrieve data.</span></span>

<span data-ttu-id="d29a1-121">動詞のガイドラインの詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d29a1-121">For more information about guidelines for verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span> <span data-ttu-id="d29a1-122">コマンドレット名に使用できない特殊文字の一覧については、「[必要な開発ガイドライン](./required-development-guidelines.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d29a1-122">For a list of special characters that cannot be used in cmdlet names, see [Required Development Guidelines](./required-development-guidelines.md).</span></span>

## <a name="supporting-windows-powershell-functionality"></a><span data-ttu-id="d29a1-123">Windows PowerShell の機能のサポート</span><span class="sxs-lookup"><span data-stu-id="d29a1-123">Supporting Windows PowerShell Functionality</span></span>

<span data-ttu-id="d29a1-124">**コマンドレット**属性では、コマンドレットが Windows PowerShell によって提供されるいくつかの一般的な機能をサポートするように指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d29a1-124">The **Cmdlet** attribute also allows you to specify that your cmdlet supports some of the common functionality that is provided by Windows PowerShell.</span></span> <span data-ttu-id="d29a1-125">これには、ユーザーフィードバックの確認 ("ユーザーの操作" 機能のサポートと呼ばれます) などの一般的な機能のサポートと、トランザクションのサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d29a1-125">This includes support for common functionality such as user feedback confirmation (referred to as support for the ShouldProcess feature) and support for transactions.</span></span> <span data-ttu-id="d29a1-126">(トランザクションのサポートは、Windows PowerShell 2.0 で導入されました)。</span><span class="sxs-lookup"><span data-stu-id="d29a1-126">(Support for transactions was introduced in Windows PowerShell 2.0).</span></span>

<span data-ttu-id="d29a1-127">**コマンドレット**属性の指定に使用される宣言構文の詳細については、「[コマンドレット属性の宣言](./cmdlet-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d29a1-127">For more information about the declaration syntax that is used to specify the **Cmdlet** attribute, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="cmdlet-class-definition"></a><span data-ttu-id="d29a1-128">コマンドレットのクラス定義</span><span class="sxs-lookup"><span data-stu-id="d29a1-128">Cmdlet Class Definition</span></span>

<span data-ttu-id="d29a1-129">次のコードは、GetProc cmdlet クラスの定義です。</span><span class="sxs-lookup"><span data-stu-id="d29a1-129">The following code is the definition for a GetProc cmdlet class.</span></span> <span data-ttu-id="d29a1-130">Pascal の大文字と小文字の区別が使用され、クラスの名前にはコマンドレットの動詞と名詞が含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d29a1-130">Notice that Pascal casing is used and that the name of the class includes the verb and noun of the cmdlet.</span></span>

[!code-csharp[GetProcessSample01.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs#L33-L34 "GetProcessSample01.cs")]

## <a name="pascal-casing"></a><span data-ttu-id="d29a1-131">Pascal 形式の文字種</span><span class="sxs-lookup"><span data-stu-id="d29a1-131">Pascal Casing</span></span>

<span data-ttu-id="d29a1-132">コマンドレットに名前を指定する場合は、Pascal 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="d29a1-132">When you name cmdlets, use Pascal casing.</span></span> <span data-ttu-id="d29a1-133">たとえば、`Get-Item` および `Get-ItemProperty` のコマンドレットは、コマンドレットに名前を付けるときに大文字小文字を使用する正しい方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d29a1-133">For example, the `Get-Item` and `Get-ItemProperty` cmdlets show the correct way to use capitalization when you are naming cmdlets.</span></span>

## <a name="see-also"></a><span data-ttu-id="d29a1-134">参照</span><span class="sxs-lookup"><span data-stu-id="d29a1-134">See Also</span></span>

[<span data-ttu-id="d29a1-135">....... の属性</span><span class="sxs-lookup"><span data-stu-id="d29a1-135">System.Management.Automation.CmdletAttribute</span></span>](/dotnet/api/System.Management.Automation.CmdletAttribute)

[<span data-ttu-id="d29a1-136">属性の宣言</span><span class="sxs-lookup"><span data-stu-id="d29a1-136">CmdletAttribute Declaration</span></span>](./cmdlet-attribute-declaration.md)

[<span data-ttu-id="d29a1-137">コマンドレットの動詞名</span><span class="sxs-lookup"><span data-stu-id="d29a1-137">Cmdlet Verb Names</span></span>](./approved-verbs-for-windows-powershell-commands.md)

[<span data-ttu-id="d29a1-138">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="d29a1-138">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="d29a1-139">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="d29a1-139">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
