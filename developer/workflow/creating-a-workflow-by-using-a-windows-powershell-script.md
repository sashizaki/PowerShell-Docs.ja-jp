---
title: Windows PowerShell スクリプトを使用してワークフローを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70532e7e-9cac-43c3-9687-e77011ecc878
caps.latest.revision: 4
ms.openlocfilehash: 5eb2186cbceee21f8b4a8c88b812e9c71f15e0af
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853048"
---
# <a name="creating-a-workflow-by-using-a-windows-powershell-script"></a><span data-ttu-id="c016e-102">Windows PowerShell スクリプトを利用してワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="c016e-102">Creating a Workflow by Using a Windows PowerShell Script</span></span>

<span data-ttu-id="c016e-103">Windows PowerShell スクリプトを記述して、ワークフローを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="c016e-103">You can create a workflow by writing a Windows PowerShell script.</span></span> <span data-ttu-id="c016e-104">ワークフローを作成するには、ワークフロー キーワードの後に、スクリプトの本体の前にワークフローの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="c016e-104">To create a workflow, use the workflow keyword followed by a name for the workflow before the body of the script.</span></span> <span data-ttu-id="c016e-105">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c016e-105">For example:</span></span>

```powershell

workflow Invoke-HelloWorld {"Hello World from workflow"}
```

<span data-ttu-id="c016e-106">ワークフローは、他の Windows PowerShell コマンドのと同じ方法で検索します。</span><span class="sxs-lookup"><span data-stu-id="c016e-106">You find the workflow in the same way you would any other Windows PowerShell command.</span></span>

## <a name="implementing-parallel-and-sequence"></a><span data-ttu-id="c016e-107">並列シーケンスを実装します。</span><span class="sxs-lookup"><span data-stu-id="c016e-107">Implementing Parallel and Sequence</span></span>

<span data-ttu-id="c016e-108">[Windows Workflow Foundation](https://msdn.microsoft.com/en-us/library/ms735967.aspx)並列アクティビティの実行をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c016e-108">[Windows Workflow Foundation](https://msdn.microsoft.com/en-us/library/ms735967.aspx) supports execution of activities in parallel.</span></span> <span data-ttu-id="c016e-109">Windows PowerShell スクリプトでこの機能を実装するために使用して、`parallel`スクリプト ブロックの前にキーワード。</span><span class="sxs-lookup"><span data-stu-id="c016e-109">To implement this capability in a Windows PowerShell script, use the `parallel` keyword in front of a script block.</span></span> <span data-ttu-id="c016e-110">使用することも、`foreach -parallel`構造を使用して並列でオブジェクトのコレクションを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="c016e-110">You can also use the `foreach -parallel` construction to iterate through a collection of objects in parallel.</span></span> <span data-ttu-id="c016e-111">アクティビティのグループを並列ブロック内で順番に実行するには、スクリプト ブロックでそのグループのアクティビティを囲むし、シーケンス キーワードを使用して、ブロックの前にします。</span><span class="sxs-lookup"><span data-stu-id="c016e-111">To execute a group of activities in sequential order within a parallel block, enclose that group of activities in a script block and precede the block with the sequence keyword.</span></span>

## <a name="joining-computers-to-a-domain"></a><span data-ttu-id="c016e-112">コンピューターをドメインに参加させる</span><span class="sxs-lookup"><span data-stu-id="c016e-112">Joining Computers to a Domain</span></span>

<span data-ttu-id="c016e-113">次のスクリプトは、ユーザーが指定したコンピューターのグループのドメインの状態を確認、状態をもう一度確認し、既に参加していない場合に、ドメインに参加するワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="c016e-113">The following script creates a workflow that checks the domain status of a group of user-specified computers, joins them to a domain if they are not already joined, and then checks the status again.</span></span> <span data-ttu-id="c016e-114">これは、スクリプトのバージョンで説明されている XAML ワークフローの[Windows PowerShell のアクティビティとワークフローを作成する](./creating-a-workflow-with-windows-powershell-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="c016e-114">This is a script version of the XAML workflow explained in [Creating a Workflow with Windows PowerShell Activities](./creating-a-workflow-with-windows-powershell-activities.md).</span></span>

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