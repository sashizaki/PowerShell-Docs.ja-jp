---
title: コマンドレットのエイリアス |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0d70864-33fb-49ce-8054-c41ba19fd554
caps.latest.revision: 11
ms.openlocfilehash: 32f45702cc0d28e6652ef61ebdbe085291013408
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860508"
---
# <a name="cmdlet-aliases"></a><span data-ttu-id="821b7-102">コマンドレット エイリアス</span><span class="sxs-lookup"><span data-stu-id="821b7-102">Cmdlet Aliases</span></span>

<span data-ttu-id="821b7-103">コマンドレットのエイリアスを使用して、コマンドレットのユーザー エクスペリエンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="821b7-103">You can use cmdlet aliases to improve the cmdlet user experience.</span></span> <span data-ttu-id="821b7-104">頻繁に使用されるコマンドレット」と入力を削減し、迅速でタスクの実行を容易にできるようにするには、エイリアスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="821b7-104">You can add aliases to frequently used cmdlets to reduce typing and to make it easier to complete tasks quickly.</span></span> <span data-ttu-id="821b7-105">コマンドレットでは、組み込みエイリアスを含めることも、ユーザーが独自のカスタム エイリアスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="821b7-105">You can include built-in aliases in your cmdlets, or users can define their own custom aliases.</span></span>

<span data-ttu-id="821b7-106">たとえば、 [Get-command](/powershell/module/microsoft.powershell.core/get-command)コマンドレットは、組み込み`gcm`エイリアス。</span><span class="sxs-lookup"><span data-stu-id="821b7-106">For example, the [Get-Command](/powershell/module/microsoft.powershell.core/get-command) cmdlet has a built-in `gcm` alias.</span></span> <span data-ttu-id="821b7-107">ユーザーは新しいコマンドの習得するのに必要があるないように、他の言語からコマンド名を追加するのにエイリアスを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="821b7-107">You can also use aliases to add command names from other languages so that users do not have to learn new commands.</span></span>

## <a name="alias-guidelines"></a><span data-ttu-id="821b7-108">エイリアスのガイドライン</span><span class="sxs-lookup"><span data-stu-id="821b7-108">Alias Guidelines</span></span>

<span data-ttu-id="821b7-109">コマンドレットの組み込みエイリアスを作成するときに、次のガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="821b7-109">Follow these guidelines when you create built-in aliases for your cmdlets:</span></span>

- <span data-ttu-id="821b7-110">別名を割り当てる前に、Windows PowerShell を起動し、実行、 [Get-alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias)コマンドレットを既に使用されているエイリアスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="821b7-110">Before you assign aliases, start Windows PowerShell, and then run the [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet to see the aliases that are already used.</span></span>

- <span data-ttu-id="821b7-111">コマンドレット名と、コマンドレット名の名詞を参照する別名サフィックスの動詞を参照する別名のプレフィックスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="821b7-111">Include an alias prefix that references the verb of the cmdlet name and an alias suffix that references the noun of the cmdlet name.</span></span> <span data-ttu-id="821b7-112">エイリアスなど、`Import-Module`コマンドレットは、"ipmo"です。</span><span class="sxs-lookup"><span data-stu-id="821b7-112">For example, the alias for the `Import-Module` cmdlet is "ipmo".</span></span> <span data-ttu-id="821b7-113">すべての動詞と、エイリアスの一覧は、[コマンドレット動詞](./approved-verbs-for-windows-powershell-commands.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="821b7-113">For a list of all the verbs and their aliases, see [Cmdlet Verbs](./approved-verbs-for-windows-powershell-commands.md).</span></span>

- <span data-ttu-id="821b7-114">同じ動詞を含むコマンドレットでは、同じ別名のプレフィックスを含めます。</span><span class="sxs-lookup"><span data-stu-id="821b7-114">For cmdlets that have the same verb, include the same alias prefix.</span></span> <span data-ttu-id="821b7-115">たとえば、名前に"Get"動詞を含むすべての Windows PowerShell コマンドレットのエイリアスは、"g"プレフィックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="821b7-115">For example, the aliases for all the Windows PowerShell cmdlets that have the "Get" verb in their name use the "g" prefix.</span></span>

- <span data-ttu-id="821b7-116">同じ名詞を含むコマンドレットでは、同じエイリアス サフィックスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="821b7-116">For cmdlets that have the same noun, include the same alias suffix.</span></span> <span data-ttu-id="821b7-117">たとえば、名前に「セッション」という名詞を含むすべての Windows PowerShell コマンドレットのエイリアスは"sn"サフィックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="821b7-117">For example, the aliases for all the Windows PowerShell cmdlets that have the "Session" noun in their name use the "sn" suffix.</span></span>

- <span data-ttu-id="821b7-118">他の言語でのコマンドとほぼ同等であるコマンドレット、コマンドの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="821b7-118">For cmdlets that are equivalent to commands in other languages, use the name of the command.</span></span>

- <span data-ttu-id="821b7-119">一般に、できるだけ短くエイリアスを行います。</span><span class="sxs-lookup"><span data-stu-id="821b7-119">In general, make aliases as short as possible.</span></span> <span data-ttu-id="821b7-120">エイリアスが動詞の少なくとも 1 つの異なる文字と、名詞の 1 つの異なる文字確認します。</span><span class="sxs-lookup"><span data-stu-id="821b7-120">Make sure the alias has at least one distinct character for the verb and one distinct character for the noun.</span></span> <span data-ttu-id="821b7-121">エイリアスに一意にするために必要な多くの文字を追加します。</span><span class="sxs-lookup"><span data-stu-id="821b7-121">Add more characters as needed to make the alias unique.</span></span>

## <a name="see-also"></a><span data-ttu-id="821b7-122">参照</span><span class="sxs-lookup"><span data-stu-id="821b7-122">See Also</span></span>

[<span data-ttu-id="821b7-123">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="821b7-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
