---
title: Windows PowerShell のアクティビティとワークフローを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb55971a-4ea4-4c51-aeff-4e0bb05a51b2
caps.latest.revision: 6
ms.openlocfilehash: 65d04c526ef7aa112da82adb924c0789731f3850
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853468"
---
# <a name="creating-a-workflow-with-windows-powershell-activities"></a><span data-ttu-id="06ae4-102">Windows PowerShell アクティビティでワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="06ae4-102">Creating a Workflow with Windows PowerShell Activities</span></span>

<span data-ttu-id="06ae4-103">Visual Studio のツールボックスからアクティビティを選択して、ワークフロー デザイナー ウィンドウにドラッグすることによって、Windows PowerShell ワークフローを作成できます。</span><span class="sxs-lookup"><span data-stu-id="06ae4-103">You can create a Windows PowerShell workflow by selecting activities from the Visual Studio Toolbox and dragging them to the Workflow Designer window.</span></span> <span data-ttu-id="06ae4-104">Visual Studio ツールボックスに Windows PowerShell のアクティビティを追加する方法の詳細については、次を参照してください。[を Visual Studio ツールボックスに追加の Windows PowerShell アクティビティ](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)します。</span><span class="sxs-lookup"><span data-stu-id="06ae4-104">For information about adding Windows PowerShell activities to the Visual Studio Toolbox, see [Adding Windows PowerShell Activities to the Visual Studio Toolbox](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md).</span></span>

<span data-ttu-id="06ae4-105">次の手順では、ユーザーが指定したコンピューターのグループのドメインの状態を確認、状態をもう一度確認し、既に参加していない場合に、ドメインに参加するワークフローを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="06ae4-105">The following procedures describe how to create a workflow that checks the domain status of a group of user-specified computers, joins them to a domain if they are not already joined, and then checks the status again.</span></span>

### <a name="setting-up-the-project"></a><span data-ttu-id="06ae4-106">プロジェクトの設定</span><span class="sxs-lookup"><span data-stu-id="06ae4-106">Setting up the Project</span></span>

1. <span data-ttu-id="06ae4-107">」の手順に従って[を Visual Studio ツールボックスに追加の Windows PowerShell アクティビティ](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)ワークフロー プロジェクトを作成し、アクティビティを追加する、 [Microsoft.Powershell.Activities](/dotnet/api/Microsoft.PowerShell.Activities)と[Microsoft.Powershell.Management.Activities](/dotnet/api/Microsoft.PowerShell.Management.Activities)をツールボックスにアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="06ae4-107">Follow the procedure in [Adding Windows PowerShell Activities to the Visual Studio Toolbox](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md) to create a workflow project and add the activities from the [Microsoft.Powershell.Activities](/dotnet/api/Microsoft.PowerShell.Activities) and [Microsoft.Powershell.Management.Activities](/dotnet/api/Microsoft.PowerShell.Management.Activities) assemblies to the toolbox.</span></span>

2. <span data-ttu-id="06ae4-108">参照アセンブリとプロジェクトに関する System.Management.Automation、Microsoft.PowerShell.Activities、System.Management、Microsoft.PowerShell.Management.Activities、および Microsoft.PowerShell.Commands.Management を追加します。</span><span class="sxs-lookup"><span data-stu-id="06ae4-108">Add System.Management.Automation, Microsoft.PowerShell.Activities, System.Management, Microsoft.PowerShell.Management.Activities, and Microsoft.PowerShell.Commands.Management as to the project as reference assemblies.</span></span>

### <a name="adding-activities-to-the-workflow"></a><span data-ttu-id="06ae4-109">ワークフローにアクティビティを追加します。</span><span class="sxs-lookup"><span data-stu-id="06ae4-109">Adding Activities to the Workflow</span></span>

1. <span data-ttu-id="06ae4-110">追加、**シーケンス**アクティビティをワークフロー。</span><span class="sxs-lookup"><span data-stu-id="06ae4-110">Add a **Sequence** activity to the workflow.</span></span>

2. <span data-ttu-id="06ae4-111">名前付き引数を作成する`ComputerName`の引数の型と`String[]`します。</span><span class="sxs-lookup"><span data-stu-id="06ae4-111">Create an argument named `ComputerName` with an argument type of `String[]`.</span></span> <span data-ttu-id="06ae4-112">この引数は、確認し、参加するコンピューターの名前を表します。</span><span class="sxs-lookup"><span data-stu-id="06ae4-112">This argument represents the names of the computers to check and join.</span></span>

3. <span data-ttu-id="06ae4-113">名前付き引数`DomainCred`型の[System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)します。</span><span class="sxs-lookup"><span data-stu-id="06ae4-113">Create an argument named `DomainCred` of type [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential).</span></span> <span data-ttu-id="06ae4-114">この引数は、コンピューターをドメインに参加する権限を持つドメイン アカウントのドメインの資格情報を表します。</span><span class="sxs-lookup"><span data-stu-id="06ae4-114">This argument represents the domain credentials of a domain account that is authorized to join a computer to the domain.</span></span>

4. <span data-ttu-id="06ae4-115">名前付き引数`MachineCred`型の[System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)します。</span><span class="sxs-lookup"><span data-stu-id="06ae4-115">Create an argument named `MachineCred` of type [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential).</span></span> <span data-ttu-id="06ae4-116">この引数は、確認し、参加するには、コンピューターの管理者の資格情報を表します。</span><span class="sxs-lookup"><span data-stu-id="06ae4-116">This argument represents the credentials of an administrator on the computers to check and join.</span></span>

5. <span data-ttu-id="06ae4-117">追加、 **ParallelForEach**内のアクティビティ、**シーケンス**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="06ae4-117">Add a **ParallelForEach** activity inside the **Sequence** activity.</span></span> <span data-ttu-id="06ae4-118">入力`comp`と`ComputerName`内の要素をループが反復処理するためのテキスト ボックス、`ComputerName`配列。</span><span class="sxs-lookup"><span data-stu-id="06ae4-118">Enter `comp` and `ComputerName` in the text boxes so that the loop iterates through the elements of the `ComputerName` array.</span></span>

6. <span data-ttu-id="06ae4-119">追加、**シーケンス**アクティビティの本体に、 **ParallelForEach**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="06ae4-119">Add a **Sequence** activity to the body of the **ParallelForEach** activity.</span></span> <span data-ttu-id="06ae4-120">設定、 **DisplayName**するシーケンスのプロパティ`JoinDomain`します。</span><span class="sxs-lookup"><span data-stu-id="06ae4-120">Set the **DisplayName** property of the sequence to `JoinDomain`.</span></span>

7. <span data-ttu-id="06ae4-121">追加、 **GetWmiObject**アクティビティを**JoinDomain**シーケンス。</span><span class="sxs-lookup"><span data-stu-id="06ae4-121">Add a **GetWmiObject** activity to the **JoinDomain** sequence.</span></span>

8. <span data-ttu-id="06ae4-122">プロパティを編集、 **GetWmiObject**アクティビティとして次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="06ae4-122">Edit the properties of the **GetWmiObject** activity as follows.</span></span>

   |<span data-ttu-id="06ae4-123">プロパティ</span><span class="sxs-lookup"><span data-stu-id="06ae4-123">Property</span></span>|<span data-ttu-id="06ae4-124">値</span><span class="sxs-lookup"><span data-stu-id="06ae4-124">Value</span></span>|
   |--------------|-----------|
   |<span data-ttu-id="06ae4-125">**Class**</span><span class="sxs-lookup"><span data-stu-id="06ae4-125">**Class**</span></span>|<span data-ttu-id="06ae4-126">"Win32_ComputerSystem"</span><span class="sxs-lookup"><span data-stu-id="06ae4-126">"Win32_ComputerSystem"</span></span>|
   |<span data-ttu-id="06ae4-127">**PSComputerName**</span><span class="sxs-lookup"><span data-stu-id="06ae4-127">**PSComputerName**</span></span>|<span data-ttu-id="06ae4-128">{comp}</span><span class="sxs-lookup"><span data-stu-id="06ae4-128">{comp}</span></span>|
   |<span data-ttu-id="06ae4-129">**PSCredential**</span><span class="sxs-lookup"><span data-stu-id="06ae4-129">**PSCredential**</span></span>|<span data-ttu-id="06ae4-130">MachineCred</span><span class="sxs-lookup"><span data-stu-id="06ae4-130">MachineCred</span></span>|

9. <span data-ttu-id="06ae4-131">追加、 **AddComputer**アクティビティを**JoinDomain**シーケンスした後、 **GetWmiObject**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="06ae4-131">Add an **AddComputer** activity to the **JoinDomain** sequence after the **GetWmiObject** activity.</span></span>

10. <span data-ttu-id="06ae4-132">プロパティを編集、 **AddComputer**アクティビティとして次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="06ae4-132">Edit the properties of the **AddComputer** activity as follows.</span></span>

    |<span data-ttu-id="06ae4-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="06ae4-133">Property</span></span>|<span data-ttu-id="06ae4-134">値</span><span class="sxs-lookup"><span data-stu-id="06ae4-134">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="06ae4-135">**コンピューター名**</span><span class="sxs-lookup"><span data-stu-id="06ae4-135">**ComputerName**</span></span>|<span data-ttu-id="06ae4-136">{comp}</span><span class="sxs-lookup"><span data-stu-id="06ae4-136">{comp}</span></span>|
    |<span data-ttu-id="06ae4-137">**DomainCredential**</span><span class="sxs-lookup"><span data-stu-id="06ae4-137">**DomainCredential**</span></span>|<span data-ttu-id="06ae4-138">DomainCred</span><span class="sxs-lookup"><span data-stu-id="06ae4-138">DomainCred</span></span>|

11. <span data-ttu-id="06ae4-139">追加、 **RestartComputer**アクティビティを**JoinDomain**シーケンスした後、 **AddComputer**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="06ae4-139">Add a **RestartComputer** activity to the **JoinDomain** sequence after the **AddComputer** activity.</span></span>

12. <span data-ttu-id="06ae4-140">プロパティを編集、 **RestartComputer**アクティビティとして次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="06ae4-140">Edit the properties of the **RestartComputer** activity as follows.</span></span>

    |<span data-ttu-id="06ae4-141">プロパティ</span><span class="sxs-lookup"><span data-stu-id="06ae4-141">Property</span></span>|<span data-ttu-id="06ae4-142">値</span><span class="sxs-lookup"><span data-stu-id="06ae4-142">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="06ae4-143">**コンピューター名**</span><span class="sxs-lookup"><span data-stu-id="06ae4-143">**ComputerName**</span></span>|<span data-ttu-id="06ae4-144">{comp}</span><span class="sxs-lookup"><span data-stu-id="06ae4-144">{comp}</span></span>|
    |<span data-ttu-id="06ae4-145">**資格情報**</span><span class="sxs-lookup"><span data-stu-id="06ae4-145">**Credential**</span></span>|<span data-ttu-id="06ae4-146">MachineCred</span><span class="sxs-lookup"><span data-stu-id="06ae4-146">MachineCred</span></span>|
    |<span data-ttu-id="06ae4-147">**の**</span><span class="sxs-lookup"><span data-stu-id="06ae4-147">**For**</span></span>|<span data-ttu-id="06ae4-148">Microsoft.PowerShell.Commands.WaitForServiceTypes.PowerShell</span><span class="sxs-lookup"><span data-stu-id="06ae4-148">Microsoft.PowerShell.Commands.WaitForServiceTypes.PowerShell</span></span>|
    |<span data-ttu-id="06ae4-149">**Force**</span><span class="sxs-lookup"><span data-stu-id="06ae4-149">**Force**</span></span>|<span data-ttu-id="06ae4-150">True</span><span class="sxs-lookup"><span data-stu-id="06ae4-150">True</span></span>|
    |<span data-ttu-id="06ae4-151">Wait</span><span class="sxs-lookup"><span data-stu-id="06ae4-151">Wait</span></span>|<span data-ttu-id="06ae4-152">True</span><span class="sxs-lookup"><span data-stu-id="06ae4-152">True</span></span>|
    |<span data-ttu-id="06ae4-153">PSComputerName</span><span class="sxs-lookup"><span data-stu-id="06ae4-153">PSComputerName</span></span>|<span data-ttu-id="06ae4-154">{""}</span><span class="sxs-lookup"><span data-stu-id="06ae4-154">{""}</span></span>|

13. <span data-ttu-id="06ae4-155">追加、 **GetWmiObject**アクティビティを**JoinDomain**シーケンスした後、 **RestartComputer**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="06ae4-155">Add a **GetWmiObject** activity to the **JoinDomain** sequence after the **RestartComputer** activity.</span></span> <span data-ttu-id="06ae4-156">前と同じにするのには、そのプロパティを編集**GetWmiObject**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="06ae4-156">Edit its properties to be the same as the previous **GetWmiObject** activity.</span></span>

    <span data-ttu-id="06ae4-157">手順が完了したら、ワークフローのデザイン ウィンドウは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="06ae4-157">When you have finished the procedures, the workflow design window should look like this.</span></span>

    <span data-ttu-id="06ae4-158">![ワークフロー デザイナーでの JoinDomain XAML](../media/joindomainworkflow.png)
    ![ワークフロー デザイナーでの JoinDomain XAML](../media/joindomainworkflow.png "JoinDomainWorkflow")</span><span class="sxs-lookup"><span data-stu-id="06ae4-158">![JoinDomain XAML in Workflow designer](../media/joindomainworkflow.png)
![JoinDomain XAML in Workflow designer](../media/joindomainworkflow.png "JoinDomainWorkflow")</span></span>