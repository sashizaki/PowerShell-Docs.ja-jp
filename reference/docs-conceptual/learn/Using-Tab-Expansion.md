---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: タブ拡張の使用
description: PowerShell でタブ拡張機能を使用する方法について説明します。
ms.openlocfilehash: 658cdf5ddf78bbd6dd431c2170cd5ff643e6bf95
ms.sourcegitcommit: 7f712e12ec5b3f3f3e695da804b050ea0ce58b3a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "94661343"
---
# <a name="using-tab-expansion"></a><span data-ttu-id="0eaec-104">タブ拡張の使用</span><span class="sxs-lookup"><span data-stu-id="0eaec-104">Using Tab Expansion</span></span>

<span data-ttu-id="0eaec-105">コマンド ライン シェルは多くの場合、長いファイルやコマンドの名前を自動補完する手段を備えており、コマンド入力を迅速化したり、ヒントを与えたりします。</span><span class="sxs-lookup"><span data-stu-id="0eaec-105">Command-line shells often provide a way to complete the names of long files or commands automatically, speeding up command entry and providing hints.</span></span> <span data-ttu-id="0eaec-106">PowerShell では、<kbd>Tab</kbd> キーを押してファイル名やコマンドレット名を入力することができます。</span><span class="sxs-lookup"><span data-stu-id="0eaec-106">PowerShell allows you to fill in file names and cmdlet names by pressing the <kbd>Tab</kbd> key.</span></span>

> [!NOTE]
> <span data-ttu-id="0eaec-107">タブ拡張は、内部関数 TabExpansion または TabExpansion2 によって制御されています。</span><span class="sxs-lookup"><span data-stu-id="0eaec-107">Tab expansion is controlled by the internal function TabExpansion or TabExpansion2.</span></span> <span data-ttu-id="0eaec-108">この関数は変更やオーバーライドができるため、この説明は既定の PowerShell 構成の動作についてのガイドとなっています。</span><span class="sxs-lookup"><span data-stu-id="0eaec-108">Since this function can be modified or overridden, this discussion is a guide to the behavior of the default PowerShell configuration.</span></span>

<span data-ttu-id="0eaec-109">使用可能な選択肢からファイル名またはパスを自動的に入力するには、名前の一部を入力して <kbd>Tab</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0eaec-109">To fill in a filename or path from the available choices automatically, type part of the name and press the <kbd>Tab</kbd> key.</span></span> <span data-ttu-id="0eaec-110">PowerShell は自動的に名前を拡張し、最初に見つかった一致する項目を表示します。</span><span class="sxs-lookup"><span data-stu-id="0eaec-110">PowerShell will automatically expand the name to the first match that it finds.</span></span> <span data-ttu-id="0eaec-111"><kbd>Tab</kbd> キーを繰り返し押すと、すべての利用可能な選択肢が順番に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0eaec-111">Pressing the <kbd>Tab</kbd> key repeatedly will cycle through all of the available choices.</span></span>

<span data-ttu-id="0eaec-112">コマンドレット名のタブ拡張は若干異なります。</span><span class="sxs-lookup"><span data-stu-id="0eaec-112">The tab expansion of cmdlet names is slightly different.</span></span> <span data-ttu-id="0eaec-113">コマンドレット名にタブ拡張を使用するには、名前の最初の部分全体 (動詞) とそれに続くハイフンを入力します。</span><span class="sxs-lookup"><span data-stu-id="0eaec-113">To use tab expansion on a cmdlet name, type the entire first part of the name (the verb) and the hyphen that follows it.</span></span> <span data-ttu-id="0eaec-114">部分一致するよう、名前をより詳細に入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="0eaec-114">You can fill in more of the name for a partial match.</span></span> <span data-ttu-id="0eaec-115">たとえば、「`get-co`」と入力して <kbd>Tab</kbd> キーを押すと、これが PowerShell によって `Get-Command` コマンドレットに自動的に展開されます (文字の大文字と小文字の区別もその標準形式に変更されることに注目してください)。</span><span class="sxs-lookup"><span data-stu-id="0eaec-115">For example, if you type `get-co` and then press the <kbd>Tab</kbd> key, PowerShell will automatically expand this to the `Get-Command` cmdlet (notice that it also changes the case of letters to their standard form).</span></span> <span data-ttu-id="0eaec-116">もう一度 <kbd>Tab</kbd> キーを押すと、PowerShell によってこれが他の一致する唯一のコマンドレット名 `Get-Content` に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="0eaec-116">If you press <kbd>Tab</kbd> key again, PowerShell replaces this with the only other matching cmdlet name, `Get-Content`.</span></span>

> [!NOTE]
> <span data-ttu-id="0eaec-117">また、PowerShell 7.0 より、<kbd>Tab</kbd> キーで省略形のコマンドレットや関数が完全な形で示されます。</span><span class="sxs-lookup"><span data-stu-id="0eaec-117">As of PowerShell 7.0, <kbd>Tab</kbd> will also expand abbreviated cmdlets and functions.</span></span> <span data-ttu-id="0eaec-118">たとえば、`i-psdf<tab>` では `Import-PowerShellDataFile` が返されます。</span><span class="sxs-lookup"><span data-stu-id="0eaec-118">For example, `i-psdf<tab>` returns `Import-PowerShellDataFile`.</span></span>

<span data-ttu-id="0eaec-119">同じ行にタブ拡張を繰り返し使用できます。</span><span class="sxs-lookup"><span data-stu-id="0eaec-119">You can use tab expansion repeatedly on the same line.</span></span> <span data-ttu-id="0eaec-120">たとえば、`Get-Content` コマンドレットの名前に対してタブ展開を使用するには、次のように入力できます。</span><span class="sxs-lookup"><span data-stu-id="0eaec-120">For example, you can use tab expansion on the name of the `Get-Content` cmdlet by entering:</span></span>

```
PS> Get-Con<Tab>
```

<span data-ttu-id="0eaec-121"><kbd>Tab</kbd> キーを押すと、コマンドは次のように拡張されます。</span><span class="sxs-lookup"><span data-stu-id="0eaec-121">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content
```

<span data-ttu-id="0eaec-122">次に、アクティブ セットアップのログ ファイルのパスを部分的に指定し、もう一度タブ拡張を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0eaec-122">You can then partially specify the path to the Active Setup log file and use tab expansion again:</span></span>

```
PS> Get-Content c:\windows\acts<Tab>
```

<span data-ttu-id="0eaec-123"><kbd>Tab</kbd> キーを押すと、コマンドは次のように拡張されます。</span><span class="sxs-lookup"><span data-stu-id="0eaec-123">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content C:\windows\actsetup.log
```

> [!NOTE]
> <span data-ttu-id="0eaec-124">タブ拡張プロセスの 1 つの制限は、タブがあると、必ず単語の補完を試みていると解釈されることです。</span><span class="sxs-lookup"><span data-stu-id="0eaec-124">One limitation of the tab expansion process is that tabs are always interpreted as attempts to complete a word.</span></span> <span data-ttu-id="0eaec-125">コマンドの例をコピーして PowerShell コンソールに貼り付ける場合は、サンプルにタブが含まれていないことを確認ください。タブが含まれていると結果は予測できず、ほぼ確実に意図したとおりにはなりません。</span><span class="sxs-lookup"><span data-stu-id="0eaec-125">If you copy and paste command examples into a PowerShell console, make sure that the sample does not contain tabs; if it does, the results will be unpredictable and will almost certainly not be what you intended.</span></span>
