---
title: コマンドレットクラス宣言 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- cmdlets [PowerShell SDK], declaring
- declaring cmdlets [PowerShell SDK]
ms.openlocfilehash: 96ce8144795346b6f46878ee6163ce69cdb1799a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784505"
---
# <a name="cmdlet-class-declaration"></a><span data-ttu-id="956c0-102">コマンドレットのクラス宣言</span><span class="sxs-lookup"><span data-stu-id="956c0-102">Cmdlet Class Declaration</span></span>

<span data-ttu-id="956c0-103">Microsoft .NET Framework クラスは、クラスのメタデータとして**コマンドレット**属性を指定することで、コマンドレットとして宣言されます。</span><span class="sxs-lookup"><span data-stu-id="956c0-103">A Microsoft .NET Framework class is declared as a cmdlet by specifying the **Cmdlet** attribute as metadata for the class.</span></span> <span data-ttu-id="956c0-104">(**コマンドレット**属性は、すべてのコマンドレットに必要な唯一の属性です)。</span><span class="sxs-lookup"><span data-stu-id="956c0-104">(The **Cmdlet** attribute is the only required attribute for all cmdlets).</span></span>
<span data-ttu-id="956c0-105">**コマンドレット**の属性を指定する場合は、コマンドレットを識別する動詞と名詞のペアをユーザーに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="956c0-105">When you specify the **Cmdlet** attribute, you must specify the verb-and-noun pair that identifies the cmdlet to the user.</span></span> <span data-ttu-id="956c0-106">また、コマンドレットがサポートする Windows PowerShell の機能について説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="956c0-106">And, you must describe the Windows PowerShell functionality that the cmdlet supports.</span></span> <span data-ttu-id="956c0-107">**コマンドレット**属性の指定に使用される宣言構文の詳細については、「[コマンドレット属性の宣言](./cmdlet-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="956c0-107">For more information about the declaration syntax that is used to specify the **Cmdlet** attribute, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

> [!NOTE]
> <span data-ttu-id="956c0-108">**コマンドレット**属性は、system.servicemodel[属性](/dotnet/api/System.Management.Automation.CmdletAttribute)クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="956c0-108">The **Cmdlet** attribute is defined by the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) class.</span></span> <span data-ttu-id="956c0-109">このクラスのプロパティは、属性を宣言するときに使用される宣言パラメーターに対応します。</span><span class="sxs-lookup"><span data-stu-id="956c0-109">The properties of this class correspond to the declaration parameters that are used when you declare the attribute.</span></span>

## <a name="nouns"></a><span data-ttu-id="956c0-110">名詞</span><span class="sxs-lookup"><span data-stu-id="956c0-110">Nouns</span></span>

<span data-ttu-id="956c0-111">コマンドレットの名詞は、コマンドレットが処理するリソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="956c0-111">The noun of the cmdlet specifies the resources upon which the cmdlet acts.</span></span> <span data-ttu-id="956c0-112">名詞は、コマンドレットを他のコマンドレットと区別します。</span><span class="sxs-lookup"><span data-stu-id="956c0-112">The noun differentiates your cmdlets from other cmdlets.</span></span>

<span data-ttu-id="956c0-113">コマンドレット名の名詞は固有である必要があります。また、*サーバー*などの汎用名詞の場合は、リソースを他の類似リソースと区別する短いプレフィックスを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="956c0-113">Nouns in cmdlet names must be specific, and in the case of generic nouns, such as *server*, it is best to add a short prefix that differentiates your resource from other similar resources.</span></span> <span data-ttu-id="956c0-114">たとえば、というプレフィックスを持つ名詞を含むコマンドレット名は、 `Get-SQLServer` です。</span><span class="sxs-lookup"><span data-stu-id="956c0-114">For example, a cmdlet name that includes a noun with a prefix is `Get-SQLServer`.</span></span> <span data-ttu-id="956c0-115">特定の名詞とより一般的な動詞を組み合わせることで、ユーザーはコマンドレットをアクションですばやく検索し、不要なコマンドレット名の重複を回避して、コマンドレットをリソースで識別できます。</span><span class="sxs-lookup"><span data-stu-id="956c0-115">The combination of a specific noun with a more general verb enables the user to quickly locate the cmdlet by its action and then identify the cmdlet by its resource while avoiding unnecessary cmdlet name duplication.</span></span>

<span data-ttu-id="956c0-116">コマンドレット名に使用できない特殊文字の一覧については、「[必要な開発ガイドライン](./required-development-guidelines.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="956c0-116">For a list of special characters that cannot be used in cmdlet names, see [Required Development Guidelines](./required-development-guidelines.md).</span></span>

## <a name="verbs"></a><span data-ttu-id="956c0-117">動詞</span><span class="sxs-lookup"><span data-stu-id="956c0-117">Verbs</span></span>

<span data-ttu-id="956c0-118">動詞を指定する場合、開発ガイドラインでは、Windows PowerShell によって提供される定義済み動詞のいずれかを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="956c0-118">When you specify a verb, the development guidelines require you to use one of the predefined verbs provided by Windows PowerShell.</span></span> <span data-ttu-id="956c0-119">これらの定義済み動詞のいずれかを使用すると、作成したコマンドレットと、Microsoft によって作成されたコマンドレットと他のコマンドレットとの間の一貫性が確保されます。</span><span class="sxs-lookup"><span data-stu-id="956c0-119">By using one of these predefined verbs, you will ensure consistency between the cmdlets that you write and the cmdlets that are written by Microsoft and by others.</span></span> <span data-ttu-id="956c0-120">たとえば、データを取得するコマンドレットには、"Get" 動詞を使用します。</span><span class="sxs-lookup"><span data-stu-id="956c0-120">For example, the "Get" verb is used for cmdlets that retrieve data.</span></span>

<span data-ttu-id="956c0-121">動詞のガイドラインの詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="956c0-121">For more information about guidelines for verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span> <span data-ttu-id="956c0-122">コマンドレット名に使用できない特殊文字の一覧については、「[必要な開発ガイドライン](./required-development-guidelines.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="956c0-122">For a list of special characters that cannot be used in cmdlet names, see [Required Development Guidelines](./required-development-guidelines.md).</span></span>

## <a name="supporting-windows-powershell-functionality"></a><span data-ttu-id="956c0-123">Windows PowerShell の機能のサポート</span><span class="sxs-lookup"><span data-stu-id="956c0-123">Supporting Windows PowerShell Functionality</span></span>

<span data-ttu-id="956c0-124">**コマンドレット**属性では、コマンドレットが Windows PowerShell によって提供されるいくつかの一般的な機能をサポートするように指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="956c0-124">The **Cmdlet** attribute also allows you to specify that your cmdlet supports some of the common functionality that is provided by Windows PowerShell.</span></span> <span data-ttu-id="956c0-125">これには、ユーザーフィードバックの確認 ("ユーザーの操作" 機能のサポートと呼ばれます) などの一般的な機能のサポートと、トランザクションのサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="956c0-125">This includes support for common functionality such as user feedback confirmation (referred to as support for the ShouldProcess feature) and support for transactions.</span></span> <span data-ttu-id="956c0-126">(トランザクションのサポートは、Windows PowerShell 2.0 で導入されました)。</span><span class="sxs-lookup"><span data-stu-id="956c0-126">(Support for transactions was introduced in Windows PowerShell 2.0).</span></span>

<span data-ttu-id="956c0-127">**コマンドレット**属性の指定に使用される宣言構文の詳細については、「[コマンドレット属性の宣言](./cmdlet-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="956c0-127">For more information about the declaration syntax that is used to specify the **Cmdlet** attribute, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="cmdlet-class-definition"></a><span data-ttu-id="956c0-128">コマンドレットのクラス定義</span><span class="sxs-lookup"><span data-stu-id="956c0-128">Cmdlet Class Definition</span></span>

<span data-ttu-id="956c0-129">次のコードは、GetProc cmdlet クラスの定義です。</span><span class="sxs-lookup"><span data-stu-id="956c0-129">The following code is the definition for a GetProc cmdlet class.</span></span> <span data-ttu-id="956c0-130">Pascal の大文字と小文字の区別が使用され、クラスの名前にはコマンドレットの動詞と名詞が含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="956c0-130">Notice that Pascal casing is used and that the name of the class includes the verb and noun of the cmdlet.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs" range="33-34":::

## <a name="pascal-casing"></a><span data-ttu-id="956c0-131">Pascal 形式の文字種</span><span class="sxs-lookup"><span data-stu-id="956c0-131">Pascal Casing</span></span>

<span data-ttu-id="956c0-132">コマンドレットに名前を指定する場合は、Pascal 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="956c0-132">When you name cmdlets, use Pascal casing.</span></span> <span data-ttu-id="956c0-133">たとえば、コマンドレット `Get-Item` と `Get-ItemProperty` コマンドレットは、コマンドレットに名前を付けるときに大文字小文字を使用する正しい方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="956c0-133">For example, the `Get-Item` and `Get-ItemProperty` cmdlets show the correct way to use capitalization when you are naming cmdlets.</span></span>

## <a name="see-also"></a><span data-ttu-id="956c0-134">参照</span><span class="sxs-lookup"><span data-stu-id="956c0-134">See Also</span></span>

[<span data-ttu-id="956c0-135">....... の属性</span><span class="sxs-lookup"><span data-stu-id="956c0-135">System.Management.Automation.CmdletAttribute</span></span>](/dotnet/api/System.Management.Automation.CmdletAttribute)

[<span data-ttu-id="956c0-136">属性の宣言</span><span class="sxs-lookup"><span data-stu-id="956c0-136">CmdletAttribute Declaration</span></span>](./cmdlet-attribute-declaration.md)

[<span data-ttu-id="956c0-137">コマンドレットの動詞名</span><span class="sxs-lookup"><span data-stu-id="956c0-137">Cmdlet Verb Names</span></span>](./approved-verbs-for-windows-powershell-commands.md)

[<span data-ttu-id="956c0-138">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="956c0-138">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="956c0-139">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="956c0-139">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
