---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: タブ拡張の使用
ms.assetid: c8730471-bf6a-43b8-ab1d-f9ef5a74f04e
ms.openlocfilehash: 437c1e3c04352f2c5c3aba4c67b542821975f739
ms.sourcegitcommit: 58fb23c854f5a8b40ad1f952d3323aeeccac7a24
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65229431"
---
# <a name="using-tab-expansion"></a><span data-ttu-id="09499-103">タブ拡張の使用</span><span class="sxs-lookup"><span data-stu-id="09499-103">Using Tab Expansion</span></span>

<span data-ttu-id="09499-104">コマンド ライン シェルは多くの場合、長いファイルやコマンドの名前を自動補完する手段を備えており、コマンド入力を迅速化したり、ヒントを与えたりします。</span><span class="sxs-lookup"><span data-stu-id="09499-104">Command-line shells often provide a way to complete the names of long files or commands automatically, speeding up command entry and providing hints.</span></span> <span data-ttu-id="09499-105">PowerShell では、<kbd>Tab</kbd> キーを押してファイル名やコマンドレット名を入力することができます。</span><span class="sxs-lookup"><span data-stu-id="09499-105">PowerShell allows you to fill in file names and cmdlet names by pressing the <kbd>Tab</kbd> key.</span></span>

> [!NOTE]
> <span data-ttu-id="09499-106">タブ拡張は、内部関数 TabExpansion または TabExpansion2 によって制御されています。</span><span class="sxs-lookup"><span data-stu-id="09499-106">Tab expansion is controlled by the internal function TabExpansion or TabExpansion2.</span></span> <span data-ttu-id="09499-107">この関数は変更やオーバーライドができるため、この説明は既定の PowerShell 構成の動作についてのガイドとなっています。</span><span class="sxs-lookup"><span data-stu-id="09499-107">Since this function can be modified or overridden, this discussion is a guide to the behavior of the default PowerShell configuration.</span></span>

<span data-ttu-id="09499-108">使用可能な選択肢からファイル名またはパスを自動的に入力するには、名前の一部を入力して <kbd>Tab</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="09499-108">To fill in a filename or path from the available choices automatically, type part of the name and press the <kbd>Tab</kbd> key.</span></span> <span data-ttu-id="09499-109">PowerShell は自動的に名前を拡張し、最初に見つかった一致する項目を表示します。</span><span class="sxs-lookup"><span data-stu-id="09499-109">PowerShell will automatically expand the name to the first match that it finds.</span></span> <span data-ttu-id="09499-110"><kbd>Tab</kbd> キーを繰り返し押すと、すべての利用可能な選択肢が順番に表示されます。</span><span class="sxs-lookup"><span data-stu-id="09499-110">Pressing the <kbd>Tab</kbd> key repeatedly will cycle through all of the available choices.</span></span>

<span data-ttu-id="09499-111">コマンドレット名のタブ拡張は若干異なります。</span><span class="sxs-lookup"><span data-stu-id="09499-111">The tab expansion of cmdlet names is slightly different.</span></span> <span data-ttu-id="09499-112">コマンドレット名にタブ拡張を使用するには、名前の最初の部分全体 (動詞) とそれに続くハイフンを入力します。</span><span class="sxs-lookup"><span data-stu-id="09499-112">To use tab expansion on a cmdlet name, type the entire first part of the name (the verb) and the hyphen that follows it.</span></span> <span data-ttu-id="09499-113">部分一致するよう、名前をより詳細に入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="09499-113">You can fill in more of the name for a partial match.</span></span> <span data-ttu-id="09499-114">たとえば、「`get-co`」と入力して <kbd>Tab</kbd> キーを押すと、これが PowerShell によって `Get-Command` コマンドレットに自動的に展開されます (文字の大文字と小文字の区別もその標準形式に変更されることに注目してください)。</span><span class="sxs-lookup"><span data-stu-id="09499-114">For example, if you type `get-co` and then press the <kbd>Tab</kbd> key, PowerShell will automatically expand this to the `Get-Command` cmdlet (notice that it also changes the case of letters to their standard form).</span></span> <span data-ttu-id="09499-115">もう一度 <kbd>Tab</kbd> キーを押すと、PowerShell によってこれが他の一致する唯一のコマンドレット名 `Get-Content` に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="09499-115">If you press <kbd>Tab</kbd> key again, PowerShell replaces this with the only other matching cmdlet name, `Get-Content`.</span></span>

<span data-ttu-id="09499-116">同じ行にタブ拡張を繰り返し使用できます。</span><span class="sxs-lookup"><span data-stu-id="09499-116">You can use tab expansion repeatedly on the same line.</span></span> <span data-ttu-id="09499-117">たとえば、`Get-Content` コマンドレットの名前に対してタブ展開を使用するには、次のように入力できます。</span><span class="sxs-lookup"><span data-stu-id="09499-117">For example, you can use tab expansion on the name of the `Get-Content` cmdlet by entering:</span></span>

```
PS> Get-Con<Tab>
```

<span data-ttu-id="09499-118"><kbd>Tab</kbd> キーを押すと、コマンドは次のように拡張されます。</span><span class="sxs-lookup"><span data-stu-id="09499-118">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content
```

<span data-ttu-id="09499-119">次に、アクティブ セットアップのログ ファイルのパスを部分的に指定し、もう一度タブ拡張を使用できます。</span><span class="sxs-lookup"><span data-stu-id="09499-119">You can then partially specify the path to the Active Setup log file and use tab expansion again:</span></span>

```
PS> Get-Content c:\windows\acts<Tab>
```

<span data-ttu-id="09499-120"><kbd>Tab</kbd> キーを押すと、コマンドは次のように拡張されます。</span><span class="sxs-lookup"><span data-stu-id="09499-120">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content C:\windows\actsetup.log
```

> [!NOTE]
> <span data-ttu-id="09499-121">タブ拡張プロセスの 1 つの制限は、タブがあると、必ず単語の補完を試みていると解釈されることです。</span><span class="sxs-lookup"><span data-stu-id="09499-121">One limitation of the tab expansion process is that tabs are always interpreted as attempts to complete a word.</span></span> <span data-ttu-id="09499-122">コマンドの例をコピーして PowerShell コンソールに貼り付ける場合は、サンプルにタブが含まれていないことを確認ください。タブが含まれていると結果は予測できず、ほぼ確実に意図したとおりにはなりません。</span><span class="sxs-lookup"><span data-stu-id="09499-122">If you copy and paste command examples into a PowerShell console, make sure that the sample does not contain tabs; if it does, the results will be unpredictable and will almost certainly not be what you intended.</span></span>