---
ms.date: 08/25/2017
title: ObjectModelRoot オブジェクト
description: PowerShell ISE のプリンシパル ルート オブジェクトである $psISE オブジェクトは、Microsoft.PowerShell.Host.ISE.ObjectModelRoot クラスのインスタンスです。 このトピックでは、ObjectModelRoot オブジェクトのプロパティについて説明します。
ms.openlocfilehash: c8ae703c2663256ca037090fd3b1eb239cfc431a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660949"
---
# <a name="the-objectmodelroot-object"></a><span data-ttu-id="121f4-104">ObjectModelRoot オブジェクト</span><span class="sxs-lookup"><span data-stu-id="121f4-104">The ObjectModelRoot Object</span></span>

<span data-ttu-id="121f4-105">Windows PowerShell&reg; Integrated Scripting Environment (ISE) のプリンシパル ルート オブジェクトである `$psISE` オブジェクトは、Microsoft.PowerShell.Host.ISE.ObjectModelRoot クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="121f4-105">The `$psISE` object, which is the principal root object in Windows PowerShell&reg; Integrated Scripting Environment (ISE) is an instance of the Microsoft.PowerShell.Host.ISE.ObjectModelRoot class.</span></span> <span data-ttu-id="121f4-106">このトピックでは、 **ObjectModelRoot** オブジェクトのプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="121f4-106">This topic describes the properties of the **ObjectModelRoot** object.</span></span>

## <a name="properties"></a><span data-ttu-id="121f4-107">Properties</span><span class="sxs-lookup"><span data-stu-id="121f4-107">Properties</span></span>

### <a name="currentfile"></a><span data-ttu-id="121f4-108">CurrentFile</span><span class="sxs-lookup"><span data-stu-id="121f4-108">CurrentFile</span></span>

> <span data-ttu-id="121f4-109">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="121f4-109">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="121f4-110">現在フォーカスしているこのホスト オブジェクトに関連付けられているファイルを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="121f4-110">The read-only property that gets the file, which is associated with this host object that currently has the focus.</span></span>

### <a name="currentpowershelltab"></a><span data-ttu-id="121f4-111">CurrentPowerShellTab</span><span class="sxs-lookup"><span data-stu-id="121f4-111">CurrentPowerShellTab</span></span>

> <span data-ttu-id="121f4-112">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="121f4-112">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="121f4-113">フォーカスしている PowerShell タブを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="121f4-113">The read-only property that gets the PowerShell tab that has the focus.</span></span>

### <a name="currentvisiblehorizontaltool"></a><span data-ttu-id="121f4-114">CurrentVisibleHorizontalTool</span><span class="sxs-lookup"><span data-stu-id="121f4-114">CurrentVisibleHorizontalTool</span></span>

> <span data-ttu-id="121f4-115">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="121f4-115">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="121f4-116">エディターの下部にある水平方向のツール ウィンドウに現在表示されている Windows PowerShell ISE アドオン ツールを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="121f4-116">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the horizontal tool pane at the bottom of the editor.</span></span>

### <a name="currentvisibleverticaltool"></a><span data-ttu-id="121f4-117">CurrentVisibleVerticalTool</span><span class="sxs-lookup"><span data-stu-id="121f4-117">CurrentVisibleVerticalTool</span></span>

> <span data-ttu-id="121f4-118">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="121f4-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="121f4-119">エディターの右側にある垂直方向のツール ウィンドウに現在表示されている Windows PowerShell ISE アドオン ツールを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="121f4-119">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the vertical tool pane on the right side of the editor.</span></span>

### <a name="options"></a><span data-ttu-id="121f4-120">オプション</span><span class="sxs-lookup"><span data-stu-id="121f4-120">Options</span></span>

> <span data-ttu-id="121f4-121">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="121f4-121">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="121f4-122">Windows PowerShell ISE の設定を変更することができるさまざまなオプションを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="121f4-122">The read-only property that gets the various options that can change settings in Windows PowerShell ISE.</span></span>

### <a name="powershelltabs"></a><span data-ttu-id="121f4-123">PowerShellTabs</span><span class="sxs-lookup"><span data-stu-id="121f4-123">PowerShellTabs</span></span>

> <span data-ttu-id="121f4-124">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="121f4-124">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="121f4-125">Windows PowerShell ISE で開かれている PowerShell タブのコレクションを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="121f4-125">The read-only property that gets the collection of the PowerShell tabs, which are open in Windows PowerShell ISE.</span></span> <span data-ttu-id="121f4-126">既定では、このオブジェクトには 1 つの PowerShell タブが含まれています。ただし、スクリプトまたは Windows PowerShell ISE のメニューを使用して、このオブジェクトに他の PowerShell タブを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="121f4-126">By default, this object contains one PowerShell tab. However, you can add more PowerShell tabs to this object by using scripts or by using the menus in Windows PowerShell ISE.</span></span>

## <a name="see-also"></a><span data-ttu-id="121f4-127">参照</span><span class="sxs-lookup"><span data-stu-id="121f4-127">See Also</span></span>

- [<span data-ttu-id="121f4-128">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="121f4-128">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="121f4-129">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="121f4-129">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
