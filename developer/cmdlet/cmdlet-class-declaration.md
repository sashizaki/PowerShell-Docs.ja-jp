---
title: コマンドレット クラスの宣言 |Microsoft Docs
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
ms.openlocfilehash: 3168275423dc65fcb2e41dedd9bea275ede58397
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068642"
---
# <a name="cmdlet-class-declaration"></a><span data-ttu-id="495c7-102">コマンドレットのクラス宣言</span><span class="sxs-lookup"><span data-stu-id="495c7-102">Cmdlet Class Declaration</span></span>

<span data-ttu-id="495c7-103">Microsoft .NET Framework クラスが指定することでコマンドレットとして宣言されている、**コマンドレット**属性として、クラスのメタデータ。</span><span class="sxs-lookup"><span data-stu-id="495c7-103">A Microsoft .NET Framework class is declared as a cmdlet by specifying the **Cmdlet** attribute as metadata for the class.</span></span> <span data-ttu-id="495c7-104">(**コマンドレット**属性は、すべてのコマンドレットの唯一の必須属性)。</span><span class="sxs-lookup"><span data-stu-id="495c7-104">(The **Cmdlet** attribute is the only required attribute for all cmdlets).</span></span> <span data-ttu-id="495c7-105">指定した場合、**コマンドレット**属性、ユーザーにコマンドレットを識別する動詞-名詞形式のペアを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="495c7-105">When you specify the **Cmdlet** attribute, you must specify the verb-and-noun pair that identifies the cmdlet to the user.</span></span> <span data-ttu-id="495c7-106">また、このコマンドレットをサポートする Windows PowerShell の機能を記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="495c7-106">And, you must describe the Windows PowerShell functionality that the cmdlet supports.</span></span> <span data-ttu-id="495c7-107">指定に使用される宣言の構文の詳細については、**コマンドレット**属性は、「[コマンドレット属性宣言](./cmdlet-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="495c7-107">For more information about the declaration syntax that is used to specify the **Cmdlet** attribute, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

> [!NOTE]
> <span data-ttu-id="495c7-108">**コマンドレット**属性を定義した、 [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute)クラス。</span><span class="sxs-lookup"><span data-stu-id="495c7-108">The **Cmdlet** attribute is defined by the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) class.</span></span> <span data-ttu-id="495c7-109">このクラスのプロパティは、属性を宣言するときに使用されるパラメーターの宣言に対応します。</span><span class="sxs-lookup"><span data-stu-id="495c7-109">The properties of this class correspond to the declaration parameters that are used when you declare the attribute.</span></span>

## <a name="nouns"></a><span data-ttu-id="495c7-110">名詞</span><span class="sxs-lookup"><span data-stu-id="495c7-110">Nouns</span></span>

<span data-ttu-id="495c7-111">コマンドレットの名詞には、コマンドレットの処理となるリソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="495c7-111">The noun of the cmdlet specifies the resources upon which the cmdlet acts.</span></span> <span data-ttu-id="495c7-112">名詞では、他のコマンドレットから、コマンドレットが区別されます。</span><span class="sxs-lookup"><span data-stu-id="495c7-112">The noun differentiates your cmdlets from other cmdlets.</span></span>

<span data-ttu-id="495c7-113">コマンドレットの名前に名詞などでなければなりません具体的である場合は、汎用の名詞と*server*、他の同様のリソースからリソースを識別する短いプレフィックスを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="495c7-113">Nouns in cmdlet names must be specific, and in the case of generic nouns, such as *server*, it is best to add a short prefix that differentiates your resource from other similar resources.</span></span> <span data-ttu-id="495c7-114">たとえば、プレフィックス付きの名詞を含むコマンドレット名は`Get-SQLServer`します。</span><span class="sxs-lookup"><span data-stu-id="495c7-114">For example, a cmdlet name that includes a noun with a prefix is `Get-SQLServer`.</span></span> <span data-ttu-id="495c7-115">一般的な動詞を使用して特定の名詞を組み合わせたには、その操作によって、コマンドレットをすばやく検索し、そのリソースによって不要なコマンドレット名の重複を回避しながら、コマンドレットを識別するユーザーができるようにします。</span><span class="sxs-lookup"><span data-stu-id="495c7-115">The combination of a specific noun with a more general verb enables the user to quickly locate the cmdlet by its action and then identify the cmdlet by its resource while avoiding unnecessary cmdlet name duplication.</span></span>

<span data-ttu-id="495c7-116">コマンドレット名では使用できませんの特殊文字の一覧は、次を参照してください。[開発ガイドラインのために必要な](./required-development-guidelines.md)します。</span><span class="sxs-lookup"><span data-stu-id="495c7-116">For a list of special characters that cannot be used in cmdlet names, see [Required Development Guidelines](./required-development-guidelines.md).</span></span>

## <a name="verbs"></a><span data-ttu-id="495c7-117">動詞</span><span class="sxs-lookup"><span data-stu-id="495c7-117">Verbs</span></span>

<span data-ttu-id="495c7-118">動詞を指定すると、開発のガイドラインでは、Windows PowerShell によって提供される定義済みの動詞のいずれかを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="495c7-118">When you specify a verb, the development guidelines require you to use one of the predefined verbs provided by Windows PowerShell.</span></span> <span data-ttu-id="495c7-119">これらの定義済みの動詞のいずれかは、作成したコマンドレットと Microsoft によっては他のユーザーが記述されたコマンドレット一貫性が確保されます。</span><span class="sxs-lookup"><span data-stu-id="495c7-119">By using one of these predefined verbs, you will ensure consistency between the cmdlets that you write and the cmdlets that are written by Microsoft and by others.</span></span> <span data-ttu-id="495c7-120">たとえば、"Get"動詞は、データを取得するコマンドレットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="495c7-120">For example, the "Get" verb is used for cmdlets that retrieve data.</span></span>

<span data-ttu-id="495c7-121">動詞に関するガイドラインの詳細については、次を参照してください。[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)します。</span><span class="sxs-lookup"><span data-stu-id="495c7-121">For more information about guidelines for verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span> <span data-ttu-id="495c7-122">コマンドレット名では使用できませんの特殊文字の一覧は、次を参照してください。[開発ガイドラインのために必要な](./required-development-guidelines.md)します。</span><span class="sxs-lookup"><span data-stu-id="495c7-122">For a list of special characters that cannot be used in cmdlet names, see [Required Development Guidelines](./required-development-guidelines.md).</span></span>

## <a name="supporting-windows-powershell-functionality"></a><span data-ttu-id="495c7-123">Windows PowerShell の機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="495c7-123">Supporting Windows PowerShell Functionality</span></span>

<span data-ttu-id="495c7-124">**コマンドレット**属性では、コマンドレットがいくつかの Windows PowerShell によって提供される一般的な機能をサポートしているを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="495c7-124">The **Cmdlet** attribute also allows you to specify that your cmdlet supports some of the common functionality that is provided by Windows PowerShell.</span></span> <span data-ttu-id="495c7-125">これには、ユーザーのフィードバックの確認 (ShouldProcess 機能のサポートと呼ばれます) などの一般的な機能をサポートし、トランザクションのサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="495c7-125">This includes support for common functionality such as user feedback confirmation (referred to as support for the ShouldProcess feature) and support for transactions.</span></span> <span data-ttu-id="495c7-126">(トランザクションのサポートは、Windows PowerShell 2.0 で導入されました。)</span><span class="sxs-lookup"><span data-stu-id="495c7-126">(Support for transactions was introduced in Windows PowerShell 2.0).</span></span>

<span data-ttu-id="495c7-127">指定に使用される宣言の構文の詳細については、**コマンドレット**属性は、「[コマンドレット属性宣言](./cmdlet-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="495c7-127">For more information about the declaration syntax that is used to specify the **Cmdlet** attribute, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="cmdlet-class-definition"></a><span data-ttu-id="495c7-128">コマンドレット クラスの定義</span><span class="sxs-lookup"><span data-stu-id="495c7-128">Cmdlet Class Definition</span></span>

<span data-ttu-id="495c7-129">次のコードは、GetProc コマンドレット クラスの定義です。</span><span class="sxs-lookup"><span data-stu-id="495c7-129">The following code is the definition for a GetProc cmdlet class.</span></span> <span data-ttu-id="495c7-130">大文字と小文字を使用する pascal 形式と、クラスの名前には、コマンドレットの名詞と動詞が含まれることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="495c7-130">Notice that Pascal casing is used and that the name of the class includes the verb and noun of the cmdlet.</span></span>

[!code-csharp[GetProcessSample01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs#L33-L34 "GetProcessSample01.cs")]

## <a name="pascal-casing"></a><span data-ttu-id="495c7-131">Pascal 形式の大文字小文字の区別</span><span class="sxs-lookup"><span data-stu-id="495c7-131">Pascal Casing</span></span>

<span data-ttu-id="495c7-132">Pascal 形式を使用して、コマンドレットの名前を入力するとき大文字小文字の区別します。</span><span class="sxs-lookup"><span data-stu-id="495c7-132">When you name cmdlets, use Pascal casing.</span></span> <span data-ttu-id="495c7-133">たとえば、`Get-Item`と`Get-ItemProperty`コマンドレットは、コマンドレットに名前を付けるときに、大文字と小文字を使用する正しい方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="495c7-133">For example, the `Get-Item` and `Get-ItemProperty` cmdlets show the correct way to use capitalization when you are naming cmdlets.</span></span>

## <a name="see-also"></a><span data-ttu-id="495c7-134">参照</span><span class="sxs-lookup"><span data-stu-id="495c7-134">See Also</span></span>

[<span data-ttu-id="495c7-135">System.Management.Automation.CmdletAttribute</span><span class="sxs-lookup"><span data-stu-id="495c7-135">System.Management.Automation.CmdletAttribute</span></span>](/dotnet/api/System.Management.Automation.CmdletAttribute)

[<span data-ttu-id="495c7-136">CmdletAttribute 宣言</span><span class="sxs-lookup"><span data-stu-id="495c7-136">CmdletAttribute Declaration</span></span>](./cmdlet-attribute-declaration.md)

[<span data-ttu-id="495c7-137">コマンドレットの動詞名</span><span class="sxs-lookup"><span data-stu-id="495c7-137">Cmdlet Verb Names</span></span>](./approved-verbs-for-windows-powershell-commands.md)

[<span data-ttu-id="495c7-138">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="495c7-138">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="495c7-139">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="495c7-139">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
