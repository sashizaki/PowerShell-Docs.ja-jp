---
title: Windows PowerShell スクリプトを使用したワークフローの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70532e7e-9cac-43c3-9687-e77011ecc878
caps.latest.revision: 4
ms.openlocfilehash: 5720200ce32f114cd4965d961b9e2804bd154b2e
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870848"
---
# <a name="creating-a-workflow-by-using-a-windows-powershell-script"></a><span data-ttu-id="e908b-102">Windows PowerShell スクリプトを利用してワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="e908b-102">Creating a Workflow by Using a Windows PowerShell Script</span></span>

<span data-ttu-id="e908b-103">Windows PowerShell スクリプトを記述することで、ワークフローを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e908b-103">You can create a workflow by writing a Windows PowerShell script.</span></span> <span data-ttu-id="e908b-104">ワークフローを作成するには、スクリプトの本文の前に workflow キーワードを使用し、その後にワークフローの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e908b-104">To create a workflow, use the workflow keyword followed by a name for the workflow before the body of the script.</span></span> <span data-ttu-id="e908b-105">たとえば次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e908b-105">For example:</span></span>

```powershell

workflow Invoke-HelloWorld {"Hello World from workflow"}
```

<span data-ttu-id="e908b-106">ワークフローは、他の Windows PowerShell コマンドと同じ方法で検索できます。</span><span class="sxs-lookup"><span data-stu-id="e908b-106">You find the workflow in the same way you would any other Windows PowerShell command.</span></span>

## <a name="implementing-parallel-and-sequence"></a><span data-ttu-id="e908b-107">並列とシーケンスの実装</span><span class="sxs-lookup"><span data-stu-id="e908b-107">Implementing Parallel and Sequence</span></span>

<span data-ttu-id="e908b-108">[Windows Workflow Foundation](/previous-versions/dotnet/netframework-3.5/ms735967(v=vs.90))は、アクティビティの並列実行をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e908b-108">[Windows Workflow Foundation](/previous-versions/dotnet/netframework-3.5/ms735967(v=vs.90)) supports execution of activities in parallel.</span></span> <span data-ttu-id="e908b-109">Windows PowerShell スクリプトでこの機能を実装するには、スクリプトブロックの前に `parallel` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="e908b-109">To implement this capability in a Windows PowerShell script, use the `parallel` keyword in front of a script block.</span></span> <span data-ttu-id="e908b-110">また、`foreach -parallel` の構築を使用して、オブジェクトのコレクションを並列に反復処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="e908b-110">You can also use the `foreach -parallel` construction to iterate through a collection of objects in parallel.</span></span> <span data-ttu-id="e908b-111">並列ブロック内で連続した順序でアクティビティのグループを実行するには、そのアクティビティのグループをスクリプトブロックで囲み、ブロックの前に sequence キーワードを付けます。</span><span class="sxs-lookup"><span data-stu-id="e908b-111">To execute a group of activities in sequential order within a parallel block, enclose that group of activities in a script block and precede the block with the sequence keyword.</span></span>

## <a name="joining-computers-to-a-domain"></a><span data-ttu-id="e908b-112">ドメインへのコンピューターの参加</span><span class="sxs-lookup"><span data-stu-id="e908b-112">Joining Computers to a Domain</span></span>

<span data-ttu-id="e908b-113">次のスクリプトは、ユーザー指定のコンピューターのグループのドメインの状態を確認し、まだ参加していない場合はドメインに参加させるワークフローを作成してから、状態を再度確認します。</span><span class="sxs-lookup"><span data-stu-id="e908b-113">The following script creates a workflow that checks the domain status of a group of user-specified computers, joins them to a domain if they are not already joined, and then checks the status again.</span></span>
<span data-ttu-id="e908b-114">これは、「 [Windows PowerShell アクティビティを使用したワークフローの作成](./creating-a-workflow-with-windows-powershell-activities.md)」で説明されている XAML ワークフローのスクリプトバージョンです。</span><span class="sxs-lookup"><span data-stu-id="e908b-114">This is a script version of the XAML workflow explained in [Creating a Workflow with Windows PowerShell Activities](./creating-a-workflow-with-windows-powershell-activities.md).</span></span>

```powershell
workflow Join-Domain
{
    param([string[]] $ComputerName, [PSCredential] $DomainCred, [PsCredential] $MachineCred)

    foreach -parallel($Computer in $ComputerName)
    {
        sequence {
        Get-WmiObject -PSComputerName $Computer -PSCredential $MachineCred
        Add-Computer -PSComputerName $Computer -PSCredential $DomainCred
        Restart-Computer -ComputerName $Computer -Credential $MachineCred -For PowerShell -Force -Wait -PSComputerName ""
        Get-WmiObject -PSComputerName $Computer -PSCredential $MachineCred
        }
    }
}
```