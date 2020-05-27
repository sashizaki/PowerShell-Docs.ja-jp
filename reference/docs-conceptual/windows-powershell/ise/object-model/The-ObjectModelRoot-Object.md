---
ms.date: 08/25/2017
keywords: powershell,コマンドレット
title: ObjectModelRoot オブジェクト
ms.openlocfilehash: cd94e69de2e62f7ce9fac413e15458ae9986540e
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809568"
---
# <a name="the-objectmodelroot-object"></a><span data-ttu-id="18a62-103">ObjectModelRoot オブジェクト</span><span class="sxs-lookup"><span data-stu-id="18a62-103">The ObjectModelRoot Object</span></span>

<span data-ttu-id="18a62-104">Windows PowerShell® Integrated Scripting Environment (ISE) のプリンシパル ルート オブジェクトである `$psISE` オブジェクトは、Microsoft.PowerShell.Host.ISE.ObjectModelRoot クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="18a62-104">The `$psISE` object, which is the principal root object in Windows PowerShell® Integrated Scripting Environment (ISE) is an instance of the Microsoft.PowerShell.Host.ISE.ObjectModelRoot class.</span></span> <span data-ttu-id="18a62-105">このトピックでは、**ObjectModelRoot** オブジェクトのプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="18a62-105">This topic describes the properties of the **ObjectModelRoot** object.</span></span>

## <a name="properties"></a><span data-ttu-id="18a62-106">Properties</span><span class="sxs-lookup"><span data-stu-id="18a62-106">Properties</span></span>

### <a name="currentfile"></a><span data-ttu-id="18a62-107">CurrentFile</span><span class="sxs-lookup"><span data-stu-id="18a62-107">CurrentFile</span></span>

> <span data-ttu-id="18a62-108">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="18a62-108">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="18a62-109">現在フォーカスしているこのホスト オブジェクトに関連付けられているファイルを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="18a62-109">The read-only property that gets the file, which is associated with this host object that currently has the focus.</span></span>

### <a name="currentpowershelltab"></a><span data-ttu-id="18a62-110">CurrentPowerShellTab</span><span class="sxs-lookup"><span data-stu-id="18a62-110">CurrentPowerShellTab</span></span>

> <span data-ttu-id="18a62-111">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="18a62-111">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="18a62-112">フォーカスしている PowerShell タブを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="18a62-112">The read-only property that gets the PowerShell tab that has the focus.</span></span>

### <a name="currentvisiblehorizontaltool"></a><span data-ttu-id="18a62-113">CurrentVisibleHorizontalTool</span><span class="sxs-lookup"><span data-stu-id="18a62-113">CurrentVisibleHorizontalTool</span></span>

> <span data-ttu-id="18a62-114">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="18a62-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="18a62-115">エディターの下部にある水平方向のツール ウィンドウに現在表示されている Windows PowerShell ISE アドオン ツールを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="18a62-115">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the horizontal tool pane at the bottom of the editor.</span></span>

### <a name="currentvisibleverticaltool"></a><span data-ttu-id="18a62-116">CurrentVisibleVerticalTool</span><span class="sxs-lookup"><span data-stu-id="18a62-116">CurrentVisibleVerticalTool</span></span>

> <span data-ttu-id="18a62-117">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="18a62-117">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="18a62-118">エディターの右側にある垂直方向のツール ウィンドウに現在表示されている Windows PowerShell ISE アドオン ツールを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="18a62-118">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the vertical tool pane on the right side of the editor.</span></span>

### <a name="options"></a><span data-ttu-id="18a62-119">Options</span><span class="sxs-lookup"><span data-stu-id="18a62-119">Options</span></span>

> <span data-ttu-id="18a62-120">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="18a62-120">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="18a62-121">Windows PowerShell ISE の設定を変更することができるさまざまなオプションを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="18a62-121">The read-only property that gets the various options that can change settings in Windows PowerShell ISE.</span></span>

### <a name="powershelltabs"></a><span data-ttu-id="18a62-122">PowerShellTabs</span><span class="sxs-lookup"><span data-stu-id="18a62-122">PowerShellTabs</span></span>

> <span data-ttu-id="18a62-123">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="18a62-123">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="18a62-124">Windows PowerShell ISE で開かれている PowerShell タブのコレクションを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="18a62-124">The read-only property that gets the collection of the PowerShell tabs, which are open in Windows PowerShell ISE.</span></span> <span data-ttu-id="18a62-125">既定では、このオブジェクトには 1 つの PowerShell タブが含まれています。ただし、スクリプトまたは Windows PowerShell ISE のメニューを使用して、このオブジェクトに他の PowerShell タブを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="18a62-125">By default, this object contains one PowerShell tab. However, you can add more PowerShell tabs to this object by using scripts or by using the menus in Windows PowerShell ISE.</span></span>

## <a name="see-also"></a><span data-ttu-id="18a62-126">参照</span><span class="sxs-lookup"><span data-stu-id="18a62-126">See Also</span></span>

- [<span data-ttu-id="18a62-127">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="18a62-127">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="18a62-128">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="18a62-128">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
