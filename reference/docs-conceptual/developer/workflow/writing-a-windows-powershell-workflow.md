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
ms.openlocfilehash: 0f8a9938a1685e9abc2f1dbfb18c3b2b9008d9be
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564928"
---
# <a name="writing-a-windows-powershell-workflow"></a><span data-ttu-id="d27ad-102">Windows PowerShell ワークフローを記述する</span><span class="sxs-lookup"><span data-stu-id="d27ad-102">Writing a Windows PowerShell Workflow</span></span>

<span data-ttu-id="d27ad-103">Windows PowerShell アセンブリによって公開されているアクティビティを Visual Studio のワークフローデザイナーに追加することによって、XAML ワークフローを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d27ad-103">You can create a XAML workflow by adding activities exposed by Windows PowerShell assemblies to the Workflow designer in Visual Studio.</span></span> <span data-ttu-id="d27ad-104">次の Windows PowerShell アセンブリは、ワークフロー対応のアクティビティを公開します。</span><span class="sxs-lookup"><span data-stu-id="d27ad-104">The following Windows PowerShell assemblies expose workflow-enabled activities.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d27ad-105">ワークフローのヘルプを提供する場合は、XAML ワークフローをモジュールとしてパッケージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d27ad-105">A XAML workflow must be packaged as a module if you want to provide help for the workflow.</span></span> <span data-ttu-id="d27ad-106">モジュールの詳細については、「 [Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d27ad-106">For information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

- [<span data-ttu-id="d27ad-107">Microsoft. Powershell. アクティビティ</span><span class="sxs-lookup"><span data-stu-id="d27ad-107">Microsoft.Powershell.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Activities)

- [<span data-ttu-id="d27ad-108">Microsoft. Powershell. コアアクティビティ</span><span class="sxs-lookup"><span data-stu-id="d27ad-108">Microsoft.Powershell.Core.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Core.Activities)

- [<span data-ttu-id="d27ad-109">Microsoft. Powershell. 診断アクティビティ</span><span class="sxs-lookup"><span data-stu-id="d27ad-109">Microsoft.Powershell.Diagnostics.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Diagnostics.Activities)

- [<span data-ttu-id="d27ad-110">Microsoft. Powershell. 管理アクティビティ</span><span class="sxs-lookup"><span data-stu-id="d27ad-110">Microsoft.Powershell.Management.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Management.Activities)

- [<span data-ttu-id="d27ad-111">Microsoft. Powershell. Security. アクティビティ</span><span class="sxs-lookup"><span data-stu-id="d27ad-111">Microsoft.Powershell.Security.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Security.Activities)

- [<span data-ttu-id="d27ad-112">Microsoft. Powershell. ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="d27ad-112">Microsoft.Powershell.Utility.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Utility.Activities)

  <span data-ttu-id="d27ad-113">次のトピックでは、Windows PowerShell アクティビティを使用してワークフローを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d27ad-113">The following topics describe how to create a Workflow by using Windows PowerShell activities.</span></span>

- [<span data-ttu-id="d27ad-114">Visual Studio ツールボックスに Windows PowerShell アクティビティを追加する</span><span class="sxs-lookup"><span data-stu-id="d27ad-114">Adding Windows PowerShell Activities to the Visual Studio Toolbox</span></span>](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)

- [<span data-ttu-id="d27ad-115">Windows PowerShell アクティビティでワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="d27ad-115">Creating a Workflow with Windows PowerShell Activities</span></span>](./creating-a-workflow-with-windows-powershell-activities.md)

- [<span data-ttu-id="d27ad-116">Windows PowerShell スクリプトを利用してワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="d27ad-116">Creating a Workflow by Using a Windows PowerShell Script</span></span>](./creating-a-workflow-by-using-a-windows-powershell-script.md)

- [<span data-ttu-id="d27ad-117">Windows PowerShell ワークフローをインポートして呼び出す</span><span class="sxs-lookup"><span data-stu-id="d27ad-117">Importing and Invoking a Windows PowerShell Workflow</span></span>](./importing-and-invoking-a-windows-powershell-workflow.md)

- [<span data-ttu-id="d27ad-118">Windows PowerShell コマンドレットからワークフロー アクティビティを作成する</span><span class="sxs-lookup"><span data-stu-id="d27ad-118">Creating a Workflow Activity from a Windows PowerShell Cmdlet</span></span>](./creating-a-workflow-activity-from-a-windows-powershell-cmdlet.md)
