---
title: コマンドレット Alias |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0d70864-33fb-49ce-8054-c41ba19fd554
caps.latest.revision: 11
ms.openlocfilehash: 32f45702cc0d28e6652ef61ebdbe085291013408
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369981"
---
# <a name="cmdlet-aliases"></a><span data-ttu-id="cb941-102">コマンドレット エイリアス</span><span class="sxs-lookup"><span data-stu-id="cb941-102">Cmdlet Aliases</span></span>

<span data-ttu-id="cb941-103">コマンドレットのエイリアスを使用して、コマンドレットのユーザーエクスペリエンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="cb941-103">You can use cmdlet aliases to improve the cmdlet user experience.</span></span> <span data-ttu-id="cb941-104">頻繁に使用するコマンドレットにエイリアスを追加して、入力を減らし、タスクをすばやく完了できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cb941-104">You can add aliases to frequently used cmdlets to reduce typing and to make it easier to complete tasks quickly.</span></span> <span data-ttu-id="cb941-105">組み込みのエイリアスをコマンドレットに含めることも、ユーザーが独自のカスタムエイリアスを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="cb941-105">You can include built-in aliases in your cmdlets, or users can define their own custom aliases.</span></span>

<span data-ttu-id="cb941-106">たとえば、 [Get コマンド](/powershell/module/microsoft.powershell.core/get-command)レットには `gcm` エイリアスが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="cb941-106">For example, the [Get-Command](/powershell/module/microsoft.powershell.core/get-command) cmdlet has a built-in `gcm` alias.</span></span> <span data-ttu-id="cb941-107">エイリアスを使用して、他の言語のコマンド名を追加して、ユーザーが新しいコマンドを習得する必要がないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cb941-107">You can also use aliases to add command names from other languages so that users do not have to learn new commands.</span></span>

## <a name="alias-guidelines"></a><span data-ttu-id="cb941-108">エイリアスのガイドライン</span><span class="sxs-lookup"><span data-stu-id="cb941-108">Alias Guidelines</span></span>

<span data-ttu-id="cb941-109">コマンドレットの組み込みエイリアスを作成するときは、次のガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="cb941-109">Follow these guidelines when you create built-in aliases for your cmdlets:</span></span>

- <span data-ttu-id="cb941-110">エイリアスを割り当てる前に、Windows PowerShell を起動してから、 [Get Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias)コマンドレットを実行して、既に使用されているエイリアスを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb941-110">Before you assign aliases, start Windows PowerShell, and then run the [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet to see the aliases that are already used.</span></span>

- <span data-ttu-id="cb941-111">コマンドレット名の動詞を参照するエイリアスプレフィックスと、コマンドレット名の名詞を参照するエイリアスサフィックスを含めます。</span><span class="sxs-lookup"><span data-stu-id="cb941-111">Include an alias prefix that references the verb of the cmdlet name and an alias suffix that references the noun of the cmdlet name.</span></span> <span data-ttu-id="cb941-112">たとえば、`Import-Module` コマンドレットのエイリアスは "ipmo" です。</span><span class="sxs-lookup"><span data-stu-id="cb941-112">For example, the alias for the `Import-Module` cmdlet is "ipmo".</span></span> <span data-ttu-id="cb941-113">すべての動詞とそのエイリアスの一覧については、「[コマンドレットの動詞](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb941-113">For a list of all the verbs and their aliases, see [Cmdlet Verbs](./approved-verbs-for-windows-powershell-commands.md).</span></span>

- <span data-ttu-id="cb941-114">同じ動詞を持つコマンドレットの場合は、同じエイリアスプレフィックスを含めます。</span><span class="sxs-lookup"><span data-stu-id="cb941-114">For cmdlets that have the same verb, include the same alias prefix.</span></span> <span data-ttu-id="cb941-115">たとえば、名前に "Get" という動詞があるすべての Windows PowerShell コマンドレットのエイリアスは、"g" プレフィックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb941-115">For example, the aliases for all the Windows PowerShell cmdlets that have the "Get" verb in their name use the "g" prefix.</span></span>

- <span data-ttu-id="cb941-116">同じ名詞を持つコマンドレットの場合は、同じエイリアスサフィックスを含めます。</span><span class="sxs-lookup"><span data-stu-id="cb941-116">For cmdlets that have the same noun, include the same alias suffix.</span></span> <span data-ttu-id="cb941-117">たとえば、名前に "Session" という名詞が付いているすべての Windows PowerShell コマンドレットのエイリアスは、"sn" サフィックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb941-117">For example, the aliases for all the Windows PowerShell cmdlets that have the "Session" noun in their name use the "sn" suffix.</span></span>

- <span data-ttu-id="cb941-118">他の言語のコマンドと同等のコマンドレットについては、コマンドの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="cb941-118">For cmdlets that are equivalent to commands in other languages, use the name of the command.</span></span>

- <span data-ttu-id="cb941-119">一般に、エイリアスはできるだけ短くしてください。</span><span class="sxs-lookup"><span data-stu-id="cb941-119">In general, make aliases as short as possible.</span></span> <span data-ttu-id="cb941-120">動詞と名詞に1つの個別の文字がエイリアスに1つ以上含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb941-120">Make sure the alias has at least one distinct character for the verb and one distinct character for the noun.</span></span> <span data-ttu-id="cb941-121">エイリアスを一意にするために、必要に応じてさらに文字を追加します。</span><span class="sxs-lookup"><span data-stu-id="cb941-121">Add more characters as needed to make the alias unique.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb941-122">参照</span><span class="sxs-lookup"><span data-stu-id="cb941-122">See Also</span></span>

[<span data-ttu-id="cb941-123">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="cb941-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
