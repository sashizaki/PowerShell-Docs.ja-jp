---
title: Windows PowerShell ワークフローを記述する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2551ceed-836f-4275-9fc0-ea68446d6a35
caps.latest.revision: 7
ms.openlocfilehash: 4f0be193fb5b5c753d040a48e5f49235ece11708
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366011"
---
# <a name="writing-a-windows-powershell-workflow"></a><span data-ttu-id="e47a5-102">Windows PowerShell ワークフローを記述する</span><span class="sxs-lookup"><span data-stu-id="e47a5-102">Writing a Windows PowerShell Workflow</span></span>

<span data-ttu-id="e47a5-103">Windows PowerShell アセンブリによって公開されているアクティビティを Visual Studio のワークフローデザイナーに追加することによって、XAML ワークフローを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e47a5-103">You can create a XAML workflow by adding activities exposed by Windows PowerShell assemblies to the Workflow designer in Visual Studio.</span></span> <span data-ttu-id="e47a5-104">次の Windows PowerShell アセンブリは、ワークフロー対応のアクティビティを公開します。</span><span class="sxs-lookup"><span data-stu-id="e47a5-104">The following Windows PowerShell assemblies expose workflow-enabled activities.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e47a5-105">ワークフローのヘルプを提供する場合は、XAML ワークフローをモジュールとしてパッケージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e47a5-105">A XAML workflow must be packaged as a module if you want to provide help for the workflow.</span></span> <span data-ttu-id="e47a5-106">モジュールの詳細については、「 [Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e47a5-106">For information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

- [<span data-ttu-id="e47a5-107">Microsoft. Powershell. アクティビティ</span><span class="sxs-lookup"><span data-stu-id="e47a5-107">Microsoft.Powershell.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Activities)

- [<span data-ttu-id="e47a5-108">Microsoft. Powershell. コアアクティビティ</span><span class="sxs-lookup"><span data-stu-id="e47a5-108">Microsoft.Powershell.Core.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Core.Activities)

- [<span data-ttu-id="e47a5-109">Microsoft. Powershell. 診断アクティビティ</span><span class="sxs-lookup"><span data-stu-id="e47a5-109">Microsoft.Powershell.Diagnostics.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Diagnostics.Activities)

- [<span data-ttu-id="e47a5-110">Microsoft. Powershell. 管理アクティビティ</span><span class="sxs-lookup"><span data-stu-id="e47a5-110">Microsoft.Powershell.Management.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Management.Activities)

- [<span data-ttu-id="e47a5-111">Microsoft. Powershell. Security. アクティビティ</span><span class="sxs-lookup"><span data-stu-id="e47a5-111">Microsoft.Powershell.Security.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Security.Activities)

- [<span data-ttu-id="e47a5-112">Microsoft. Powershell. ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="e47a5-112">Microsoft.Powershell.Utility.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Utility.Activities)

  <span data-ttu-id="e47a5-113">次のトピックでは、Windows PowerShell アクティビティを使用してワークフローを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e47a5-113">The following topics describe how to create a Workflow by using Windows PowerShell activities.</span></span>

- [<span data-ttu-id="e47a5-114">Visual Studio ツールボックスへの Windows PowerShell アクティビティの追加</span><span class="sxs-lookup"><span data-stu-id="e47a5-114">Adding Windows PowerShell Activities to the Visual Studio Toolbox</span></span>](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)

- [<span data-ttu-id="e47a5-115">Windows PowerShell アクティビティを使用したワークフローの作成</span><span class="sxs-lookup"><span data-stu-id="e47a5-115">Creating a Workflow with Windows PowerShell Activities</span></span>](./creating-a-workflow-with-windows-powershell-activities.md)

- [<span data-ttu-id="e47a5-116">Windows PowerShell スクリプトを使用したワークフローの作成</span><span class="sxs-lookup"><span data-stu-id="e47a5-116">Creating a Workflow by Using a Windows PowerShell Script</span></span>](./creating-a-workflow-by-using-a-windows-powershell-script.md)

- [<span data-ttu-id="e47a5-117">Windows PowerShell ワークフローのインポートと呼び出し</span><span class="sxs-lookup"><span data-stu-id="e47a5-117">Importing and Invoking a Windows PowerShell Workflow</span></span>](./importing-and-invoking-a-windows-powershell-workflow.md)

- [<span data-ttu-id="e47a5-118">Windows PowerShell コマンドレットからのワークフローアクティビティの作成</span><span class="sxs-lookup"><span data-stu-id="e47a5-118">Creating a Workflow Activity from a Windows PowerShell Cmdlet</span></span>](./creating-a-workflow-activity-from-a-windows-powershell-cmdlet.md)