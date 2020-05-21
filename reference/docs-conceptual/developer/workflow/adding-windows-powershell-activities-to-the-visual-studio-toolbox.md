---
title: Visual Studio ツールボックスへの Windows PowerShell アクティビティの追加 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c8ef289-0659-42d1-9976-044b144201eb
caps.latest.revision: 6
ms.openlocfilehash: ecd23d3eb722137bdda0498fc71e0e966c57a589
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561191"
---
# <a name="adding-windows-powershell-activities-to-the-visual-studio-toolbox"></a><span data-ttu-id="d796d-102">Visual Studio ツールボックスに Windows PowerShell アクティビティを追加する</span><span class="sxs-lookup"><span data-stu-id="d796d-102">Adding Windows PowerShell Activities to the Visual Studio Toolbox</span></span>

<span data-ttu-id="d796d-103">ワークフローデザイナーを使用して PowerShell ワークフローを作成する前に、まず Visual Studio Workflow コンソールアプリケーションプロジェクトの [ツールボックス] に PowerShell アクティビティを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d796d-103">Before you author a PowerShell Workflow using Workflow Designer, you must first add the PowerShell Activities to the Toolbox in a Visual Studio Workflow console application project.</span></span> <span data-ttu-id="d796d-104">次の手順は、Visual Studio のツールボックスにアクティビティを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d796d-104">The following procedure shows how to add the activities from the Microsoft.PowerShell.Core.Activities assembly to the Visual Studio toolbox.</span></span>

### <a name="adding-windows-powershell-activities-to-the-toolbox"></a><span data-ttu-id="d796d-105">ツールボックスへの Windows PowerShell アクティビティの追加</span><span class="sxs-lookup"><span data-stu-id="d796d-105">Adding Windows PowerShell Activities to the Toolbox</span></span>

1. <span data-ttu-id="d796d-106">Visual Studio で新しいワークフローコンソールアプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d796d-106">Create a new Workflow console application project in Visual Studio.</span></span>

2. <span data-ttu-id="d796d-107">**[表示]** メニューの **[ツールボックス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d796d-107">On the **View** menu, click **Toolbox**.</span></span>

3. <span data-ttu-id="d796d-108">ツールボックスの内部を右クリックして [**タブの追加]** をクリックし、新しいタブに「PowerShell アクティビティ」などの名前を付けて、ツールボックスに新しいタブを追加します。</span><span class="sxs-lookup"><span data-stu-id="d796d-108">Add a new tab in the Toolbox by right-clicking inside the Toolbox and clicking **Add Tab**, and give the new tab a name such as "PowerShell Activities".</span></span>

   <span data-ttu-id="d796d-109">タブを追加すると、PowerShell アクティビティをツールボックスの他のツールとは別にグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="d796d-109">Adding a tab allows you to group the PowerShell Activities separate from other tools in the Toolbox.</span></span>

4. <span data-ttu-id="d796d-110">[新しいツールボックス] タブで、[**項目の選択**...] をクリックします。[**ツールボックスアイテムの選択**] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d796d-110">On the new Toolbox tab, click **Choose Items...**. The **Choose Toolbox Items** dialog appears.</span></span>

5. <span data-ttu-id="d796d-111">[**ツールボックスアイテムの選択**] ダイアログで、[**システム**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d796d-111">In the **Choose Toolbox Items** dialog, click the **System.Activities** tab.</span></span>

6. <span data-ttu-id="d796d-112">**[参照]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d796d-112">Click **Browse**.</span></span>

7. <span data-ttu-id="d796d-113">%WINDIR%\Microsoft.NET\assembly\ GAC_MSIL \Microsoft.PowerShell.Core.Activities\v4.0_3.0.0. 0__31bf3856ad364e フォルダーに移動し、[] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d796d-113">Navigate to the %WINDIR%\Microsoft.NET\assembly\GAC_MSIL\Microsoft.PowerShell.Core.Activities\v4.0_3.0.0.0__31bf3856ad364e folder and double-click Microsoft.PowerShell.Core.Activities.dll.</span></span>

8. <span data-ttu-id="d796d-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d796d-114">Click **OK**.</span></span> <span data-ttu-id="d796d-115">これで、[ツールボックス] で使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d796d-115">The activities defined by the Microsoft.PowerShell.Core.Activities assembly are now available in the toolbox.</span></span>

## <a name="see-also"></a><span data-ttu-id="d796d-116">参照</span><span class="sxs-lookup"><span data-stu-id="d796d-116">See Also</span></span>

[<span data-ttu-id="d796d-117">Windows PowerShell ワークフローを記述する</span><span class="sxs-lookup"><span data-stu-id="d796d-117">Writing a Windows PowerShell Workflow</span></span>](./writing-a-windows-powershell-workflow.md)

[<span data-ttu-id="d796d-118">Windows PowerShell アクティビティでワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="d796d-118">Creating a Workflow with Windows PowerShell Activities</span></span>](./creating-a-workflow-with-windows-powershell-activities.md)
