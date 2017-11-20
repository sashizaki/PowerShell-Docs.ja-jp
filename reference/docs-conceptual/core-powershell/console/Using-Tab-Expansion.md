---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "タブ拡張の使用"
ms.assetid: c8730471-bf6a-43b8-ab1d-f9ef5a74f04e
ms.openlocfilehash: 8412bd97a95719f07b16c6671d3b8801bbfab8e3
ms.sourcegitcommit: 4807ab554d55fdee499980835bcc279368b1df68
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="using-tab-expansion"></a><span data-ttu-id="63e2c-103">タブ拡張の使用</span><span class="sxs-lookup"><span data-stu-id="63e2c-103">Using Tab Expansion</span></span>
<span data-ttu-id="63e2c-104">コマンド ライン シェルは多くの場合、長いファイルやコマンドの名前を自動補完する手段を備えており、コマンド入力を迅速化したり、ヒントを与えたりします。</span><span class="sxs-lookup"><span data-stu-id="63e2c-104">Command-line shells often provide a way to complete the names of long files or commands automatically, speeding up command entry and providing .</span></span> <span data-ttu-id="63e2c-105">Windows PowerShell では、**Tab** キーを押してファイル名やコマンドレット名を入力できます。</span><span class="sxs-lookup"><span data-stu-id="63e2c-105">Windows PowerShell allows you to fill in file names and cmdlet names by pressing the **Tab** key.</span></span>

> [!NOTE]
> <span data-ttu-id="63e2c-106">タブ拡張は、内部関数 TabExpansion または TabExpansion2 によって制御されています。</span><span class="sxs-lookup"><span data-stu-id="63e2c-106">Tab expansion is controlled by the internal function TabExpansion or TabExpansion2.</span></span> <span data-ttu-id="63e2c-107">この関数は変更やオーバーライドができるため、この説明は既定の PowerShell 構成の動作についてのガイドとなっています。</span><span class="sxs-lookup"><span data-stu-id="63e2c-107">Since this function can be modified or overridden, this discussion is a guide to the behavior of the default PowerShell configuration.</span></span>

<span data-ttu-id="63e2c-108">使用可能な選択肢からファイル名またはパスを自動的に入力するには、名前の一部を入力して **Tab** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="63e2c-108">To fill in a filename or path from the available choices automatically, type part of the name and press the **Tab** key.</span></span> <span data-ttu-id="63e2c-109">PowerShell は自動的に名前を拡張し、最初に見つかった一致する項目を表示します。</span><span class="sxs-lookup"><span data-stu-id="63e2c-109">PowerShell will automatically expand the name to the first match that it finds.</span></span> <span data-ttu-id="63e2c-110">**Tab** キーを繰り返し押すと、すべての利用可能な選択肢が順番に表示されます。</span><span class="sxs-lookup"><span data-stu-id="63e2c-110">Pressing the **Tab** key repeatedly will cycle through all of the available choices.</span></span>

<span data-ttu-id="63e2c-111">コマンドレット名のタブ拡張は若干異なります。</span><span class="sxs-lookup"><span data-stu-id="63e2c-111">The tab expansion of cmdlet names is slightly different.</span></span> <span data-ttu-id="63e2c-112">コマンドレット名にタブ拡張を使用するには、名前の最初の部分全体 (動詞) とそれに続くハイフンを入力します。</span><span class="sxs-lookup"><span data-stu-id="63e2c-112">To use tab expansion on a cmdlet name, type the entire first part of the name (the verb) and the hyphen that follows it.</span></span> <span data-ttu-id="63e2c-113">部分一致するよう、名前をより詳細に入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="63e2c-113">You can fill in more of the name for a partial match.</span></span> <span data-ttu-id="63e2c-114">たとえば、「**get-co**」と入力してから **Tab** キーを押した場合、PowerShell はこれを自動的に **Get-Command** コマンドレットに拡張します (文字の大文字と小文字も標準形式に変更されることにも注目してください)。</span><span class="sxs-lookup"><span data-stu-id="63e2c-114">For example, if you type **get-co** and then press the **Tab** key, PowerShell will automatically expand this to the **Get-Command** cmdlet (notice that it also changes the case of letters to their standard form).</span></span> <span data-ttu-id="63e2c-115">もう一度 **Tab** キーを押すと、PowerShell はこれを置き換えて、もう 1 つだけある一致するコマンドレット名 **Get-Content** を表示します。</span><span class="sxs-lookup"><span data-stu-id="63e2c-115">If you press **Tab** key again, PowerShell replaces this with the only other matching cmdlet name, **Get-Content**.</span></span>

<span data-ttu-id="63e2c-116">同じ行にタブ拡張を繰り返し使用できます。</span><span class="sxs-lookup"><span data-stu-id="63e2c-116">You can use tab expansion repeatedly on the same line.</span></span> <span data-ttu-id="63e2c-117">たとえば、次のように入力すると **Get-Content** コマンドレットの名前にタブ拡張を使用できます。</span><span class="sxs-lookup"><span data-stu-id="63e2c-117">For example, you can use tab expansion on the name of the **Get-Content** cmdlet by entering:</span></span>

```
PS> Get-Con<Tab>
```

<span data-ttu-id="63e2c-118">**Tab** キーを押すと、コマンドは次のように拡張されます。</span><span class="sxs-lookup"><span data-stu-id="63e2c-118">When you press the **Tab** key, the command expands to:</span></span>

```
PS> Get-Content
```

<span data-ttu-id="63e2c-119">次に、アクティブ セットアップのログ ファイルのパスを部分的に指定し、もう一度タブ拡張を使用できます。</span><span class="sxs-lookup"><span data-stu-id="63e2c-119">You can then partially specify the path to the Active Setup log file and use tab expansion again:</span></span>

```
PS> Get-Content c:\windows\acts<Tab>
```

<span data-ttu-id="63e2c-120">**Tab** キーを押すと、コマンドは次のように拡張されます。</span><span class="sxs-lookup"><span data-stu-id="63e2c-120">When you press the **Tab** key, the command expands to:</span></span>

```
PS> Get-Content C:\windows\actsetup.log
```

> [!NOTE]
> <span data-ttu-id="63e2c-121">タブ拡張プロセスの 1 つの制限は、タブがあると、必ず単語の補完を試みていると解釈されることです。</span><span class="sxs-lookup"><span data-stu-id="63e2c-121">One limitation of the tab expansion process is that tabs are always interpreted as attempts to complete a word.</span></span> <span data-ttu-id="63e2c-122">コマンドの例をコピーして PowerShell コンソールに貼り付ける場合は、サンプルにタブが含まれていないことを確認ください。タブが含まれていると結果は予測できず、ほぼ確実に意図したとおりにはなりません。</span><span class="sxs-lookup"><span data-stu-id="63e2c-122">If you copy and paste command examples into a PowerShell console, make sure that the sample does not contain tabs; if it does, the results will be unpredictable and will almost certainly not be what you intended.</span></span>

