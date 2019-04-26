---
title: Windows PowerShell ワークフローの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2551ceed-836f-4275-9fc0-ea68446d6a35
caps.latest.revision: 7
ms.openlocfilehash: 4f0be193fb5b5c753d040a48e5f49235ece11708
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080324"
---
# <a name="writing-a-windows-powershell-workflow"></a><span data-ttu-id="50c5b-102">Windows PowerShell ワークフローを記述する</span><span class="sxs-lookup"><span data-stu-id="50c5b-102">Writing a Windows PowerShell Workflow</span></span>

<span data-ttu-id="50c5b-103">XAML ワークフローを作成するには、Visual studio ワークフロー デザイナーに Windows PowerShell アセンブリによって公開されているアクティビティを追加します。</span><span class="sxs-lookup"><span data-stu-id="50c5b-103">You can create a XAML workflow by adding activities exposed by Windows PowerShell assemblies to the Workflow designer in Visual Studio.</span></span> <span data-ttu-id="50c5b-104">次の Windows PowerShell アセンブリは、ワークフローが有効なアクティビティを公開します。</span><span class="sxs-lookup"><span data-stu-id="50c5b-104">The following Windows PowerShell assemblies expose workflow-enabled activities.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="50c5b-105">XAML ワークフローは、ワークフローのヘルプを提供する場合、モジュールとしてパッケージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c5b-105">A XAML workflow must be packaged as a module if you want to provide help for the workflow.</span></span> <span data-ttu-id="50c5b-106">モジュールについては、次を参照してください。 [Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)します。</span><span class="sxs-lookup"><span data-stu-id="50c5b-106">For information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

- [<span data-ttu-id="50c5b-107">Microsoft.Powershell.Activities</span><span class="sxs-lookup"><span data-stu-id="50c5b-107">Microsoft.Powershell.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Activities)

- [<span data-ttu-id="50c5b-108">Microsoft.Powershell.Core.Activities</span><span class="sxs-lookup"><span data-stu-id="50c5b-108">Microsoft.Powershell.Core.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Core.Activities)

- [<span data-ttu-id="50c5b-109">Microsoft.Powershell.Diagnostics.Activities</span><span class="sxs-lookup"><span data-stu-id="50c5b-109">Microsoft.Powershell.Diagnostics.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Diagnostics.Activities)

- [<span data-ttu-id="50c5b-110">Microsoft.Powershell.Management.Activities</span><span class="sxs-lookup"><span data-stu-id="50c5b-110">Microsoft.Powershell.Management.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Management.Activities)

- [<span data-ttu-id="50c5b-111">Microsoft.Powershell.Security.Activities</span><span class="sxs-lookup"><span data-stu-id="50c5b-111">Microsoft.Powershell.Security.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Security.Activities)

- [<span data-ttu-id="50c5b-112">Microsoft.Powershell.Utility.Activities</span><span class="sxs-lookup"><span data-stu-id="50c5b-112">Microsoft.Powershell.Utility.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Utility.Activities)

  <span data-ttu-id="50c5b-113">次のトピックでは、Windows PowerShell のアクティビティを使用して、ワークフローを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="50c5b-113">The following topics describe how to create a Workflow by using Windows PowerShell activities.</span></span>

- [<span data-ttu-id="50c5b-114">Visual Studio ツールボックスへの Windows PowerShell アクティビティの追加</span><span class="sxs-lookup"><span data-stu-id="50c5b-114">Adding Windows PowerShell Activities to the Visual Studio Toolbox</span></span>](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)

- [<span data-ttu-id="50c5b-115">Windows PowerShell のアクティビティとワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="50c5b-115">Creating a Workflow with Windows PowerShell Activities</span></span>](./creating-a-workflow-with-windows-powershell-activities.md)

- [<span data-ttu-id="50c5b-116">Windows PowerShell スクリプトを使用してワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="50c5b-116">Creating a Workflow by Using a Windows PowerShell Script</span></span>](./creating-a-workflow-by-using-a-windows-powershell-script.md)

- [<span data-ttu-id="50c5b-117">インポートして、Windows PowerShell ワークフローを呼び出す</span><span class="sxs-lookup"><span data-stu-id="50c5b-117">Importing and Invoking a Windows PowerShell Workflow</span></span>](./importing-and-invoking-a-windows-powershell-workflow.md)

- [<span data-ttu-id="50c5b-118">Windows PowerShell コマンドレットからワークフロー アクティビティを作成します。</span><span class="sxs-lookup"><span data-stu-id="50c5b-118">Creating a Workflow Activity from a Windows PowerShell Cmdlet</span></span>](./creating-a-workflow-activity-from-a-windows-powershell-cmdlet.md)