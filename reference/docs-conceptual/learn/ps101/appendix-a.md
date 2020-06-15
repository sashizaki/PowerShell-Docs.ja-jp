---
title: 付録 A - ヘルプの構文
description: この記事では、Get-Help によって表示されるコマンドレットの構文を読んで理解する方法について説明します。
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: e8e28f66c02370b098f63a0396ef8a724cf3a1bd
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2020
ms.locfileid: "84437983"
---
# <a name="appendix-a---help-syntax"></a><span data-ttu-id="e5d9e-103">付録 A - ヘルプの構文</span><span class="sxs-lookup"><span data-stu-id="e5d9e-103">Appendix A - Help Syntax</span></span>

<span data-ttu-id="e5d9e-104">次の例は、`Get-EventLog` コマンドレットのヘルプの **SYNTAX** セクションを表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-104">The following example shows the **SYNTAX** section of the help for the `Get-EventLog` cmdlet.</span></span>

```powershell
help Get-EventLog
```

```Output
NAME
    Get-EventLog

SYNOPSIS
    Gets the events in an event log, or a list of the event logs, on the local or remote
    computers.


SYNTAX
    Get-EventLog [-LogName] <String> [[-InstanceId] <Int64[]>] [-After <DateTime>]
    [-AsBaseObject] [-Before <DateTime>] [-ComputerName <String[]>] [-EntryType {Error |
    Information | FailureAudit | SuccessAudit | Warning}] [-Index <Int32[]>] [-Message
    <String>] [-Newest <Int32>] [-Source <String[]>] [-UserName <String[]>]
    [<CommonParameters>]

    Get-EventLog [-AsString] [-ComputerName <String[]>] [-List] [<CommonParameters>]
```

<span data-ttu-id="e5d9e-105">この例では、ヘルプの該当する部分のみを示しています。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-105">Only the relevant portion of the help is shown in this example.</span></span>

<span data-ttu-id="e5d9e-106">構文は基本的に複数の左角かっこと右角かっこ (`[]`) で構成されています。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-106">The syntax is primarily made up of several sets of opening and closing brackets (`[]`).</span></span> <span data-ttu-id="e5d9e-107">その意味は 2 つあり、使用方法に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-107">These have two different meanings depending on how they're used.</span></span> <span data-ttu-id="e5d9e-108">角かっこに含まれるものは、空の角かっこ `[]` を除いて、すべて省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-108">Anything contained within square brackets is optional unless they're a set of empty square brackets `[]`.</span></span> <span data-ttu-id="e5d9e-109">空の角かっこは、データ型の後にのみ表示されます (`<string[]>` など)。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-109">Empty square brackets only appear after a datatype such as `<string[]>`.</span></span> <span data-ttu-id="e5d9e-110">これは、特定のパラメーターが、その型の値を複数受け入れることができることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-110">This means that particular parameter can accept more than one value of that type.</span></span>

<span data-ttu-id="e5d9e-111">`Get-EventLog` の最初のパラメーター セットの最初のパラメーター は **LogName** です。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-111">The first parameter in the first parameter set of `Get-EventLog` is **LogName**.</span></span> <span data-ttu-id="e5d9e-112">LogName は角かっこで囲まれており、位置指定パラメーターであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-112">LogName is surrounded by square brackets which means that it's a positional parameter.</span></span> <span data-ttu-id="e5d9e-113">つまり、パラメーターが正しい位置に指定されていれば、パラメーター自体の名前は指定しなくても構いません。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-113">In other words, specifying the name of the parameter itself is optional as long as it's specified in the correct position.</span></span> <span data-ttu-id="e5d9e-114">パラメーター名の後の山かっこ (`<>`) の情報は、1 つの**文字列**値が必要であることを示します。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-114">The information in the angle brackets (`<>`) after the parameter name indicates that it needs a single **string** value.</span></span> <span data-ttu-id="e5d9e-115">パラメーター名とデータ型全体が角かっこで囲まれていないので、このパラメーター セットを使用する場合は、**LogName** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-115">The entire parameter name and datatype are not surrounded by square brackets so the **LogName** parameter is required when using this parameter set.</span></span>

```powershell
Get-EventLog [-LogName] <String>
```

<span data-ttu-id="e5d9e-116">2 番目のパラメーターは **InstanceId** です。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-116">The second parameter is **InstanceId**.</span></span> <span data-ttu-id="e5d9e-117">パラメーター名とデータ型の両方が角かっこで囲まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-117">Notice that the parameter name and the datatype are both completely surrounded by square brackets.</span></span> <span data-ttu-id="e5d9e-118">これは、**InstanceId** パラメーターが省略可能で、必須ではないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-118">This means that the **InstanceId** parameter is optional, not mandatory.</span></span> <span data-ttu-id="e5d9e-119">また、**InstanceId** だけが自身の角かっこで囲まれていることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-119">Also notice that **InstanceId** is surrounded by its own set of square brackets.</span></span> <span data-ttu-id="e5d9e-120">**LogName** パラメーターと同様、これは位置指定パラメーターであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-120">As with the **LogName** parameter, this means the parameter is positional.</span></span> <span data-ttu-id="e5d9e-121">データ型の後ろには、1 組の角かっこがあります。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-121">There's one last set of square brackets after the datatype.</span></span> <span data-ttu-id="e5d9e-122">これは、配列またはコンマ区切りのリストの形式で、複数の値を受け入れることができることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-122">This means that it can accept more than one value in the form of an array or a comma-separated list.</span></span>

```
[[-InstanceId] <Int64[]>]
```

<span data-ttu-id="e5d9e-123">2 番目のパラメーター セットには **List** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-123">The second parameter set has a **List** parameter.</span></span> <span data-ttu-id="e5d9e-124">パラメーター名の後にデータ型がないため、これはスイッチ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-124">It's a switch parameter because there's no datatype following the parameter name.</span></span> <span data-ttu-id="e5d9e-125">**List** パラメーターが指定されている場合、値は **True** です。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-125">When the **List** parameter is specified, the value is **True**.</span></span> <span data-ttu-id="e5d9e-126">指定されていない場合、値は **False** です。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-126">When it's not specified, the value is **False**.</span></span>

```
[-List]
```

<span data-ttu-id="e5d9e-127">コマンドの構文情報は、`Get-Command` コマンドで **Syntax** パラメーターを指定して取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-127">The syntax information for a command can also be retrieved using `Get-Command` using the **Syntax** parameter.</span></span> <span data-ttu-id="e5d9e-128">これは私がいつも使っている便利なショートカットです。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-128">This is a handy shortcut that I use all the time.</span></span> <span data-ttu-id="e5d9e-129">これによりコマンドの使用方法をすばやく確認できます。複数のページにわたるヘルプ情報を見る必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-129">It allows me to quickly learn how to use a command without having to sift through multiple pages of help information.</span></span> <span data-ttu-id="e5d9e-130">最終的に情報が必要になった場合は、実際のヘルプ コンテンツに戻って情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-130">If I end up needing more information, then I'll revert to using the actual help content.</span></span>

```powershell
Get-Command -Name Get-EventLog -Syntax
```

```Output
Get-EventLog [-LogName] <string> [[-InstanceId] <long[]>] [-ComputerName <string[]>] [-Newest <int>]
 [-After <datetime>] [-Before <datetime>] [-UserName <string[]>] [-Index <int[]> ]
 [-EntryType <string[]>] [-Source <string[]>] [-Message <string>] [-AsBaseObject]
 [<CommonParameters>]

Get-EventLog [-ComputerName <string[]>] [-List] [-AsString] [<CommonParameters>]
```

<span data-ttu-id="e5d9e-131">PowerShell でヘルプ システムを使用するほど、さまざまなニュアンスが把握しやすくなり、</span><span class="sxs-lookup"><span data-stu-id="e5d9e-131">The more you use the help system in PowerShell, the easier remembering all of the different nuances becomes.</span></span> <span data-ttu-id="e5d9e-132">いつの間にか使うことに慣れるでしょう。</span><span class="sxs-lookup"><span data-stu-id="e5d9e-132">Before you know it, using it becomes second nature.</span></span>
