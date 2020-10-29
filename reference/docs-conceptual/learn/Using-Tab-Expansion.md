---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: タブ拡張の使用
description: PowerShell でタブ拡張機能を使用する方法について説明します。
ms.openlocfilehash: d3408aac8cc9325666082577a7b00bc3362bfca3
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500047"
---
# <a name="using-tab-expansion"></a><span data-ttu-id="3bece-104">タブ拡張の使用</span><span class="sxs-lookup"><span data-stu-id="3bece-104">Using Tab Expansion</span></span>

<span data-ttu-id="3bece-105">コマンド ライン シェルは多くの場合、長いファイルやコマンドの名前を自動補完する手段を備えており、コマンド入力を迅速化したり、ヒントを与えたりします。</span><span class="sxs-lookup"><span data-stu-id="3bece-105">Command-line shells often provide a way to complete the names of long files or commands automatically, speeding up command entry and providing hints.</span></span> <span data-ttu-id="3bece-106">PowerShell では、<kbd>Tab</kbd> キーを押してファイル名やコマンドレット名を入力することができます。</span><span class="sxs-lookup"><span data-stu-id="3bece-106">PowerShell allows you to fill in file names and cmdlet names by pressing the <kbd>Tab</kbd> key.</span></span>

> [!NOTE]
> <span data-ttu-id="3bece-107">タブ拡張は、内部関数 TabExpansion または TabExpansion2 によって制御されています。</span><span class="sxs-lookup"><span data-stu-id="3bece-107">Tab expansion is controlled by the internal function TabExpansion or TabExpansion2.</span></span> <span data-ttu-id="3bece-108">この関数は変更やオーバーライドができるため、この説明は既定の PowerShell 構成の動作についてのガイドとなっています。</span><span class="sxs-lookup"><span data-stu-id="3bece-108">Since this function can be modified or overridden, this discussion is a guide to the behavior of the default PowerShell configuration.</span></span>

<span data-ttu-id="3bece-109">使用可能な選択肢からファイル名またはパスを自動的に入力するには、名前の一部を入力して <kbd>Tab</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3bece-109">To fill in a filename or path from the available choices automatically, type part of the name and press the <kbd>Tab</kbd> key.</span></span> <span data-ttu-id="3bece-110">PowerShell は自動的に名前を拡張し、最初に見つかった一致する項目を表示します。</span><span class="sxs-lookup"><span data-stu-id="3bece-110">PowerShell will automatically expand the name to the first match that it finds.</span></span> <span data-ttu-id="3bece-111"><kbd>Tab</kbd> キーを繰り返し押すと、すべての利用可能な選択肢が順番に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3bece-111">Pressing the <kbd>Tab</kbd> key repeatedly will cycle through all of the available choices.</span></span>

<span data-ttu-id="3bece-112">コマンドレット名のタブ拡張は若干異なります。</span><span class="sxs-lookup"><span data-stu-id="3bece-112">The tab expansion of cmdlet names is slightly different.</span></span> <span data-ttu-id="3bece-113">コマンドレット名にタブ拡張を使用するには、名前の最初の部分全体 (動詞) とそれに続くハイフンを入力します。</span><span class="sxs-lookup"><span data-stu-id="3bece-113">To use tab expansion on a cmdlet name, type the entire first part of the name (the verb) and the hyphen that follows it.</span></span> <span data-ttu-id="3bece-114">部分一致するよう、名前をより詳細に入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="3bece-114">You can fill in more of the name for a partial match.</span></span> <span data-ttu-id="3bece-115">たとえば、「`get-co`」と入力して <kbd>Tab</kbd> キーを押すと、これが PowerShell によって `Get-Command` コマンドレットに自動的に展開されます (文字の大文字と小文字の区別もその標準形式に変更されることに注目してください)。</span><span class="sxs-lookup"><span data-stu-id="3bece-115">For example, if you type `get-co` and then press the <kbd>Tab</kbd> key, PowerShell will automatically expand this to the `Get-Command` cmdlet (notice that it also changes the case of letters to their standard form).</span></span> <span data-ttu-id="3bece-116">もう一度 <kbd>Tab</kbd> キーを押すと、PowerShell によってこれが他の一致する唯一のコマンドレット名 `Get-Content` に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="3bece-116">If you press <kbd>Tab</kbd> key again, PowerShell replaces this with the only other matching cmdlet name, `Get-Content`.</span></span>

<span data-ttu-id="3bece-117">同じ行にタブ拡張を繰り返し使用できます。</span><span class="sxs-lookup"><span data-stu-id="3bece-117">You can use tab expansion repeatedly on the same line.</span></span> <span data-ttu-id="3bece-118">たとえば、`Get-Content` コマンドレットの名前に対してタブ展開を使用するには、次のように入力できます。</span><span class="sxs-lookup"><span data-stu-id="3bece-118">For example, you can use tab expansion on the name of the `Get-Content` cmdlet by entering:</span></span>

```
PS> Get-Con<Tab>
```

<span data-ttu-id="3bece-119"><kbd>Tab</kbd> キーを押すと、コマンドは次のように拡張されます。</span><span class="sxs-lookup"><span data-stu-id="3bece-119">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content
```

<span data-ttu-id="3bece-120">次に、アクティブ セットアップのログ ファイルのパスを部分的に指定し、もう一度タブ拡張を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3bece-120">You can then partially specify the path to the Active Setup log file and use tab expansion again:</span></span>

```
PS> Get-Content c:\windows\acts<Tab>
```

<span data-ttu-id="3bece-121"><kbd>Tab</kbd> キーを押すと、コマンドは次のように拡張されます。</span><span class="sxs-lookup"><span data-stu-id="3bece-121">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content C:\windows\actsetup.log
```

> [!NOTE]
> <span data-ttu-id="3bece-122">タブ拡張プロセスの 1 つの制限は、タブがあると、必ず単語の補完を試みていると解釈されることです。</span><span class="sxs-lookup"><span data-stu-id="3bece-122">One limitation of the tab expansion process is that tabs are always interpreted as attempts to complete a word.</span></span> <span data-ttu-id="3bece-123">コマンドの例をコピーして PowerShell コンソールに貼り付ける場合は、サンプルにタブが含まれていないことを確認ください。タブが含まれていると結果は予測できず、ほぼ確実に意図したとおりにはなりません。</span><span class="sxs-lookup"><span data-stu-id="3bece-123">If you copy and paste command examples into a PowerShell console, make sure that the sample does not contain tabs; if it does, the results will be unpredictable and will almost certainly not be what you intended.</span></span>
