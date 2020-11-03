---
Download Help Link: https://go.microsoft.com/fwlink/?linkid=390758
Help Version: 5.2.0.0
keywords: powershell,コマンドレット
Locale: en-US
Module Guid: fb6cc51d-c096-4b38-b78d-0fed6277096a
Module Name: CimCmdlets
ms.date: 02/20/2019
schema: 2.0.0
title: CimCmdlets モジュール
ms.openlocfilehash: f4ab8e5cd7dc6120e119e969dc7926659c204a02
ms.sourcegitcommit: 3571b9e87e8881adbf7984cda46a63891039a987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2020
ms.locfileid: "93209562"
---
# <span data-ttu-id="e58e6-103">CimCmdlets モジュール</span><span class="sxs-lookup"><span data-stu-id="e58e6-103">CimCmdlets Module</span></span>

## <span data-ttu-id="e58e6-104">説明</span><span class="sxs-lookup"><span data-stu-id="e58e6-104">Description</span></span>

<span data-ttu-id="e58e6-105">Windows Management Instrumentation (WMI) サービスなどの Common Information Model (CIM) サーバーと対話するコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e58e6-105">Contains cmdlets that interact with Common Information Model (CIM) Servers like the Windows Management Instrumentation (WMI) service.</span></span>

## <span data-ttu-id="e58e6-106">CimCmdlets コマンドレット</span><span class="sxs-lookup"><span data-stu-id="e58e6-106">CimCmdlets Cmdlets</span></span>

### [<span data-ttu-id="e58e6-107">Export-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="e58e6-107">Export-BinaryMiLog</span></span>](Export-BinaryMiLog.md)
<span data-ttu-id="e58e6-108">オブジェクトのバイナリエンコードされた表現を作成し、ファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="e58e6-108">Creates a binary encoded representation of an object or objects and stores it in a file.</span></span>

### [<span data-ttu-id="e58e6-109">Get-CimAssociatedInstance</span><span class="sxs-lookup"><span data-stu-id="e58e6-109">Get-CimAssociatedInstance</span></span>](Get-CimAssociatedInstance.md)
<span data-ttu-id="e58e6-110">アソシエーションによって特定の CIM インスタンスに接続されている CIM インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e58e6-110">Retrieves the CIM instances that are connected to a specific CIM instance by an association.</span></span>

### [<span data-ttu-id="e58e6-111">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="e58e6-111">Get-CimClass</span></span>](Get-CimClass.md)
<span data-ttu-id="e58e6-112">特定の名前空間にある CIM クラスのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="e58e6-112">Gets a list of CIM classes in a specific namespace.</span></span>

### [<span data-ttu-id="e58e6-113">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="e58e6-113">Get-CimInstance</span></span>](Get-CimInstance.md)
<span data-ttu-id="e58e6-114">CIM サーバーからクラスの CIM インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e58e6-114">Gets the CIM instances of a class from a CIM server.</span></span>

### [<span data-ttu-id="e58e6-115">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="e58e6-115">Get-CimSession</span></span>](Get-CimSession.md)
<span data-ttu-id="e58e6-116">現在のセッションから CIM セッションオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="e58e6-116">Gets the CIM session objects from the current session.</span></span>

### [<span data-ttu-id="e58e6-117">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="e58e6-117">Import-BinaryMiLog</span></span>](Import-BinaryMiLog.md)
<span data-ttu-id="e58e6-118">エクスポートファイルの内容に基づいて、保存されたオブジェクトを再作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e58e6-118">Used to re-create the saved objects based on the contents of an export file.</span></span>

### [<span data-ttu-id="e58e6-119">Invoke-CimMethod</span><span class="sxs-lookup"><span data-stu-id="e58e6-119">Invoke-CimMethod</span></span>](Invoke-CimMethod.md)
<span data-ttu-id="e58e6-120">CIM クラスのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e58e6-120">Invokes a method of a CIM class.</span></span>

### [<span data-ttu-id="e58e6-121">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="e58e6-121">New-CimInstance</span></span>](New-CimInstance.md)
<span data-ttu-id="e58e6-122">CIM インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e58e6-122">Creates a CIM instance.</span></span>

### [<span data-ttu-id="e58e6-123">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="e58e6-123">New-CimSession</span></span>](New-CimSession.md)
<span data-ttu-id="e58e6-124">CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e58e6-124">Creates a CIM session.</span></span>

### [<span data-ttu-id="e58e6-125">New-CimSessionOption</span><span class="sxs-lookup"><span data-stu-id="e58e6-125">New-CimSessionOption</span></span>](New-CimSessionOption.md)
<span data-ttu-id="e58e6-126">コマンドレットの詳細オプションを指定し `New-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="e58e6-126">Specifies advanced options for the `New-CimSession` cmdlet.</span></span>

### [<span data-ttu-id="e58e6-127">Register-CimIndicationEvent</span><span class="sxs-lookup"><span data-stu-id="e58e6-127">Register-CimIndicationEvent</span></span>](Register-CimIndicationEvent.md)
<span data-ttu-id="e58e6-128">フィルター式またはクエリ式を使用した表示をサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="e58e6-128">Subscribes to indications using a filter expression or a query expression.</span></span>

### [<span data-ttu-id="e58e6-129">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="e58e6-129">Remove-CimInstance</span></span>](Remove-CimInstance.md)
<span data-ttu-id="e58e6-130">コンピューターから CIM インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="e58e6-130">Removes a CIM instance from a computer.</span></span>

### [<span data-ttu-id="e58e6-131">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="e58e6-131">Remove-CimSession</span></span>](Remove-CimSession.md)
<span data-ttu-id="e58e6-132">1つ以上の CIM セッションを削除します。</span><span class="sxs-lookup"><span data-stu-id="e58e6-132">Removes one or more CIM sessions.</span></span>

### [<span data-ttu-id="e58e6-133">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="e58e6-133">Set-CimInstance</span></span>](Set-CimInstance.md)
<span data-ttu-id="e58e6-134">Cim クラスの **modifyinstance** メソッドを呼び出すことによって、cim サーバー上の cim インスタンスを変更します。</span><span class="sxs-lookup"><span data-stu-id="e58e6-134">Modifies a CIM instance on a CIM server by calling the **ModifyInstance** method of the CIM class.</span></span>
