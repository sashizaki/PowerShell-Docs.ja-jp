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
ms.openlocfilehash: 2a8372d937fc3c959f7d829bb52495048423d506
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863568"
---
# <a name="adding-windows-powershell-activities-to-the-visual-studio-toolbox"></a><span data-ttu-id="81588-102">Visual Studio ツールボックスに Windows PowerShell アクティビティを追加する</span><span class="sxs-lookup"><span data-stu-id="81588-102">Adding Windows PowerShell Activities to the Visual Studio Toolbox</span></span>

<span data-ttu-id="81588-103">ワークフロー デザイナーを使用して、PowerShell ワークフローを作成する前に、Visual Studio のワークフロー コンソール アプリケーション プロジェクトのツールボックスに PowerShell アクティビティを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81588-103">Before you author a PowerShell Workflow using Workflow Designer, you must first add the PowerShell Activities to the Toolbox in a Visual Studio Workflow console application project.</span></span> <span data-ttu-id="81588-104">次の手順では、Microsoft.PowerShell.Core.Activities アセンブリから、Visual Studio のツールボックスにアクティビティを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="81588-104">The following procedure shows how to add the activities from the Microsoft.PowerShell.Core.Activities assembly to the Visual Studio toolbox.</span></span>

### <a name="adding-windows-powershell-activities-to-the-toolbox"></a><span data-ttu-id="81588-105">Windows PowerShell のアクティビティをツールボックスに追加します。</span><span class="sxs-lookup"><span data-stu-id="81588-105">Adding Windows PowerShell Activities to the Toolbox</span></span>

1. <span data-ttu-id="81588-106">Visual Studio で新しいワークフロー コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="81588-106">Create a new Workflow console application project in Visual Studio.</span></span>

2. <span data-ttu-id="81588-107">**ビュー**  メニューのをクリックして**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="81588-107">On the **View** menu, click **Toolbox**.</span></span>

3. <span data-ttu-id="81588-108">ツールボックスの内側を右クリックして、ツールボックスに新しいタブを追加**タブの追加**、新しいタブなどの「PowerShell アクティビティ」名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="81588-108">Add a new tab in the Toolbox by right-clicking inside the Toolbox and clicking **Add Tab**, and give the new tab a name such as "PowerShell Activities".</span></span>

   <span data-ttu-id="81588-109">タブを追加する PowerShell アクティビティをツールボックスには、その他のツールとは別にグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="81588-109">Adding a tab allows you to group the PowerShell Activities separate from other tools in the Toolbox.</span></span>

4. <span data-ttu-id="81588-110">新しいツールボックス タブのをクリックして**アイテムの選択.**.**ツールボックス アイテムの選択**ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="81588-110">On the new Toolbox tab, click **Choose Items...**. The **Choose Toolbox Items** dialog appears.</span></span>

5. <span data-ttu-id="81588-111">**ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **System.Activities**タブ。</span><span class="sxs-lookup"><span data-stu-id="81588-111">In the **Choose Toolbox Items** dialog, click the **System.Activities** tab.</span></span>

6. <span data-ttu-id="81588-112">クリックして**参照**します。</span><span class="sxs-lookup"><span data-stu-id="81588-112">Click **Browse**.</span></span>

7. <span data-ttu-id="81588-113">%WINDIR%\Microsoft.NET\assembly\GAC_MSIL\Microsoft.PowerShell.Core.Activities\v4.0_3.0.0.0__31bf3856ad364e フォルダーに移動し、Microsoft.PowerShell.Core.Activities.dll をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="81588-113">Navigate to the %WINDIR%\Microsoft.NET\assembly\GAC_MSIL\Microsoft.PowerShell.Core.Activities\v4.0_3.0.0.0__31bf3856ad364e folder and double-click Microsoft.PowerShell.Core.Activities.dll.</span></span>

8. <span data-ttu-id="81588-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81588-114">Click **OK**.</span></span> <span data-ttu-id="81588-115">Microsoft.PowerShell.Core.Activities アセンブリによって定義されたアクティビティは、ツールボックスで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="81588-115">The activities defined by the Microsoft.PowerShell.Core.Activities assembly are now available in the toolbox.</span></span>

## <a name="see-also"></a><span data-ttu-id="81588-116">参照</span><span class="sxs-lookup"><span data-stu-id="81588-116">See Also</span></span>

[<span data-ttu-id="81588-117">Windows PowerShell ワークフローを記述する</span><span class="sxs-lookup"><span data-stu-id="81588-117">Writing a Windows PowerShell Workflow</span></span>](./writing-a-windows-powershell-workflow.md)

[<span data-ttu-id="81588-118">Windows PowerShell のアクティビティとワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="81588-118">Creating a Workflow with Windows PowerShell Activities</span></span>](./creating-a-workflow-with-windows-powershell-activities.md)