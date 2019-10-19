---
title: Windows PowerShell アクティビティを使用したワークフローの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb55971a-4ea4-4c51-aeff-4e0bb05a51b2
caps.latest.revision: 6
ms.openlocfilehash: 98cac43698b3f537ee318cd2570b2174631665a7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359631"
---
# <a name="creating-a-workflow-with-windows-powershell-activities"></a><span data-ttu-id="fb35a-102">Windows PowerShell アクティビティでワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="fb35a-102">Creating a Workflow with Windows PowerShell Activities</span></span>

<span data-ttu-id="fb35a-103">Windows PowerShell ワークフローを作成するには、Visual Studio のツールボックスからアクティビティを選択し、[ワークフローデザイナー] ウィンドウにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="fb35a-103">You can create a Windows PowerShell workflow by selecting activities from the Visual Studio Toolbox and dragging them to the Workflow Designer window.</span></span> <span data-ttu-id="fb35a-104">Visual Studio のツールボックスに Windows PowerShell アクティビティを追加する方法については、「 [Visual studio のツールボックスへの Windows Powershell アクティビティの追加](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb35a-104">For information about adding Windows PowerShell activities to the Visual Studio Toolbox, see [Adding Windows PowerShell Activities to the Visual Studio Toolbox](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md).</span></span>

<span data-ttu-id="fb35a-105">次の手順では、ユーザー指定のコンピューターのグループのドメインステータスを確認し、まだ参加していない場合はドメインに参加させるワークフローを作成する方法について説明します。その後、状態をもう一度確認します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-105">The following procedures describe how to create a workflow that checks the domain status of a group of user-specified computers, joins them to a domain if they are not already joined, and then checks the status again.</span></span>

### <a name="setting-up-the-project"></a><span data-ttu-id="fb35a-106">プロジェクトの設定</span><span class="sxs-lookup"><span data-stu-id="fb35a-106">Setting up the Project</span></span>

1. <span data-ttu-id="fb35a-107">「 [Visual Studio のツールボックスへの Windows PowerShell アクティビティの追加](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)」の手順に従っ[て、ワークフロー](/dotnet/api/Microsoft.PowerShell.Activities)プロジェクトを作成し、それらの[アクティビティを追加します。](/dotnet/api/Microsoft.PowerShell.Management.Activities)アセンブリをツールボックスに転送します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-107">Follow the procedure in [Adding Windows PowerShell Activities to the Visual Studio Toolbox](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md) to create a workflow project and add the activities from the [Microsoft.Powershell.Activities](/dotnet/api/Microsoft.PowerShell.Activities) and [Microsoft.Powershell.Management.Activities](/dotnet/api/Microsoft.PowerShell.Management.Activities) assemblies to the toolbox.</span></span>

2. <span data-ttu-id="fb35a-108">参照アセンブリとして、プロジェクトに対して、システムの管理、管理、および管理を行います。そのためには、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb35a-108">Add System.Management.Automation, Microsoft.PowerShell.Activities, System.Management, Microsoft.PowerShell.Management.Activities, and Microsoft.PowerShell.Commands.Management as to the project as reference assemblies.</span></span>

### <a name="adding-activities-to-the-workflow"></a><span data-ttu-id="fb35a-109">ワークフローへのアクティビティの追加</span><span class="sxs-lookup"><span data-stu-id="fb35a-109">Adding Activities to the Workflow</span></span>

1. <span data-ttu-id="fb35a-110">ワークフローに**Sequence**アクティビティを追加します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-110">Add a **Sequence** activity to the workflow.</span></span>

2. <span data-ttu-id="fb35a-111">引数の型が `String[]` の `ComputerName` という名前の引数を作成します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-111">Create an argument named `ComputerName` with an argument type of `String[]`.</span></span> <span data-ttu-id="fb35a-112">この引数は、確認して参加させるコンピューターの名前を表します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-112">This argument represents the names of the computers to check and join.</span></span>

3. <span data-ttu-id="fb35a-113">@No__t-0 という名前の引数を[作成します](/dotnet/api/System.Management.Automation.PSCredential)。</span><span class="sxs-lookup"><span data-stu-id="fb35a-113">Create an argument named `DomainCred` of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential).</span></span> <span data-ttu-id="fb35a-114">この引数は、ドメインにコンピューターを参加させる権限を持つドメインアカウントのドメイン資格情報を表します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-114">This argument represents the domain credentials of a domain account that is authorized to join a computer to the domain.</span></span>

4. <span data-ttu-id="fb35a-115">@No__t-0 という名前の引数を[作成します](/dotnet/api/System.Management.Automation.PSCredential)。</span><span class="sxs-lookup"><span data-stu-id="fb35a-115">Create an argument named `MachineCred` of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential).</span></span> <span data-ttu-id="fb35a-116">この引数は、確認および参加するコンピューターの管理者の資格情報を表します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-116">This argument represents the credentials of an administrator on the computers to check and join.</span></span>

5. <span data-ttu-id="fb35a-117">**Sequence**アクティビティ内に**parallelforeach**アクティビティを追加します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-117">Add a **ParallelForEach** activity inside the **Sequence** activity.</span></span> <span data-ttu-id="fb35a-118">テキストボックスに `comp` と `ComputerName` を入力して、ループが `ComputerName` 配列の要素を反復処理するようにします。</span><span class="sxs-lookup"><span data-stu-id="fb35a-118">Enter `comp` and `ComputerName` in the text boxes so that the loop iterates through the elements of the `ComputerName` array.</span></span>

6. <span data-ttu-id="fb35a-119">**Parallelforeach**アクティビティの本文に**Sequence**アクティビティを追加します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-119">Add a **Sequence** activity to the body of the **ParallelForEach** activity.</span></span> <span data-ttu-id="fb35a-120">シーケンスの**DisplayName**プロパティを `JoinDomain` に設定します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-120">Set the **DisplayName** property of the sequence to `JoinDomain`.</span></span>

7. <span data-ttu-id="fb35a-121">**GetWmiObject**アクティビティを**joindomain**シーケンスに追加します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-121">Add a **GetWmiObject** activity to the **JoinDomain** sequence.</span></span>

8. <span data-ttu-id="fb35a-122">**GetWmiObject**アクティビティのプロパティを次のように編集します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-122">Edit the properties of the **GetWmiObject** activity as follows.</span></span>

   |<span data-ttu-id="fb35a-123">プロパティ</span><span class="sxs-lookup"><span data-stu-id="fb35a-123">Property</span></span>|<span data-ttu-id="fb35a-124">値</span><span class="sxs-lookup"><span data-stu-id="fb35a-124">Value</span></span>|
   |--------------|-----------|
   |<span data-ttu-id="fb35a-125">**講義**</span><span class="sxs-lookup"><span data-stu-id="fb35a-125">**Class**</span></span>|<span data-ttu-id="fb35a-126">"Win32_ComputerSystem"</span><span class="sxs-lookup"><span data-stu-id="fb35a-126">"Win32_ComputerSystem"</span></span>|
   |<span data-ttu-id="fb35a-127">**PSComputerName**</span><span class="sxs-lookup"><span data-stu-id="fb35a-127">**PSComputerName**</span></span>|<span data-ttu-id="fb35a-128">コンペティション</span><span class="sxs-lookup"><span data-stu-id="fb35a-128">{comp}</span></span>|
   |<span data-ttu-id="fb35a-129">**PSCredential**</span><span class="sxs-lookup"><span data-stu-id="fb35a-129">**PSCredential**</span></span>|<span data-ttu-id="fb35a-130">各の Ecred</span><span class="sxs-lookup"><span data-stu-id="fb35a-130">MachineCred</span></span>|

9. <span data-ttu-id="fb35a-131">**GetWmiObject**アクティビティの後に、 **Addcomputer**アクティビティを**joindomain**シーケンスに追加します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-131">Add an **AddComputer** activity to the **JoinDomain** sequence after the **GetWmiObject** activity.</span></span>

10. <span data-ttu-id="fb35a-132">次のように、 **Addcomputer**アクティビティのプロパティを編集します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-132">Edit the properties of the **AddComputer** activity as follows.</span></span>

    |<span data-ttu-id="fb35a-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="fb35a-133">Property</span></span>|<span data-ttu-id="fb35a-134">値</span><span class="sxs-lookup"><span data-stu-id="fb35a-134">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="fb35a-135">**コンピューター名**</span><span class="sxs-lookup"><span data-stu-id="fb35a-135">**ComputerName**</span></span>|<span data-ttu-id="fb35a-136">コンペティション</span><span class="sxs-lookup"><span data-stu-id="fb35a-136">{comp}</span></span>|
    |<span data-ttu-id="fb35a-137">**DomainCredential**</span><span class="sxs-lookup"><span data-stu-id="fb35a-137">**DomainCredential**</span></span>|<span data-ttu-id="fb35a-138">DomainCred</span><span class="sxs-lookup"><span data-stu-id="fb35a-138">DomainCred</span></span>|

11. <span data-ttu-id="fb35a-139">**Addcomputer**アクティビティの後に、 **RestartComputer**アクティビティを**joindomain**シーケンスに追加します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-139">Add a **RestartComputer** activity to the **JoinDomain** sequence after the **AddComputer** activity.</span></span>

12. <span data-ttu-id="fb35a-140">**RestartComputer**アクティビティのプロパティを次のように編集します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-140">Edit the properties of the **RestartComputer** activity as follows.</span></span>

    |<span data-ttu-id="fb35a-141">プロパティ</span><span class="sxs-lookup"><span data-stu-id="fb35a-141">Property</span></span>|<span data-ttu-id="fb35a-142">値</span><span class="sxs-lookup"><span data-stu-id="fb35a-142">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="fb35a-143">**コンピューター名**</span><span class="sxs-lookup"><span data-stu-id="fb35a-143">**ComputerName**</span></span>|<span data-ttu-id="fb35a-144">コンペティション</span><span class="sxs-lookup"><span data-stu-id="fb35a-144">{comp}</span></span>|
    |<span data-ttu-id="fb35a-145">**証明**</span><span class="sxs-lookup"><span data-stu-id="fb35a-145">**Credential**</span></span>|<span data-ttu-id="fb35a-146">各の Ecred</span><span class="sxs-lookup"><span data-stu-id="fb35a-146">MachineCred</span></span>|
    |<span data-ttu-id="fb35a-147">**の**</span><span class="sxs-lookup"><span data-stu-id="fb35a-147">**For**</span></span>|<span data-ttu-id="fb35a-148">Microsoft. PowerShell. WaitForServiceTypes. PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb35a-148">Microsoft.PowerShell.Commands.WaitForServiceTypes.PowerShell</span></span>|
    |<span data-ttu-id="fb35a-149">**必ず**</span><span class="sxs-lookup"><span data-stu-id="fb35a-149">**Force**</span></span>|<span data-ttu-id="fb35a-150">True</span><span class="sxs-lookup"><span data-stu-id="fb35a-150">True</span></span>|
    |<span data-ttu-id="fb35a-151">Wait</span><span class="sxs-lookup"><span data-stu-id="fb35a-151">Wait</span></span>|<span data-ttu-id="fb35a-152">True</span><span class="sxs-lookup"><span data-stu-id="fb35a-152">True</span></span>|
    |<span data-ttu-id="fb35a-153">PSComputerName</span><span class="sxs-lookup"><span data-stu-id="fb35a-153">PSComputerName</span></span>|<span data-ttu-id="fb35a-154">{""}</span><span class="sxs-lookup"><span data-stu-id="fb35a-154">{""}</span></span>|

13. <span data-ttu-id="fb35a-155">**RestartComputer**アクティビティの後に、 **GetWmiObject**アクティビティを**joindomain**シーケンスに追加します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-155">Add a **GetWmiObject** activity to the **JoinDomain** sequence after the **RestartComputer** activity.</span></span> <span data-ttu-id="fb35a-156">前の**GetWmiObject**アクティビティと同じになるように、プロパティを編集します。</span><span class="sxs-lookup"><span data-stu-id="fb35a-156">Edit its properties to be the same as the previous **GetWmiObject** activity.</span></span>

    <span data-ttu-id="fb35a-157">手順を完了すると、ワークフローデザインウィンドウは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fb35a-157">When you have finished the procedures, the workflow design window should look like this.</span></span>

    <span data-ttu-id="fb35a-158">ワークフローデザイナーでの @no__t 0JoinDomain XAML ワークフローデザイナーでの no__t![joindomain](../media/joindomainworkflow.png "workflow")</span><span class="sxs-lookup"><span data-stu-id="fb35a-158">![JoinDomain XAML in Workflow designer](../media/joindomainworkflow.png)
    ![JoinDomain XAML in Workflow designer](../media/joindomainworkflow.png "JoinDomainWorkflow")</span></span>