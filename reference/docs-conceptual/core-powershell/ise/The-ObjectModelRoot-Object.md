---
ms.date: 08/25/2017
keywords: PowerShell, コマンドレット
title: ObjectModelRoot オブジェクト
ms.openlocfilehash: 2670321ebac1eac4ecc8457afb796f9f260da471
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="the-objectmodelroot-object"></a><span data-ttu-id="7ddad-103">ObjectModelRoot オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7ddad-103">The ObjectModelRoot Object</span></span>

<span data-ttu-id="7ddad-104">Windows PowerShell® Integrated Scripting Environment (ISE) のプリンシパル ルート オブジェクトである **$PsISE** オブジェクトは、Microsoft.PowerShell.Host.ISE.ObjectModelRoot クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="7ddad-104">The **$psISE** object, which is the principal root object in Windows PowerShell® Integrated Scripting Environment (ISE) is an instance of the Microsoft.PowerShell.Host.ISE.ObjectModelRoot class.</span></span>
<span data-ttu-id="7ddad-105">このトピックでは、**ObjectModelRoot** オブジェクトのプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7ddad-105">This topic describes the properties of the **ObjectModelRoot** object.</span></span>

## <a name="properties"></a><span data-ttu-id="7ddad-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7ddad-106">Properties</span></span>

### <a name="currentfile"></a><span data-ttu-id="7ddad-107">CurrentFile</span><span class="sxs-lookup"><span data-stu-id="7ddad-107">CurrentFile</span></span>

> <span data-ttu-id="7ddad-108">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7ddad-108">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7ddad-109">現在フォーカスしているこのホスト オブジェクトに関連付けられているファイルを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="7ddad-109">The read-only property that gets the file, which is associated with this host object that currently has the focus.</span></span>

### <a name="currentpowershelltab"></a><span data-ttu-id="7ddad-110">CurrentPowerShellTab</span><span class="sxs-lookup"><span data-stu-id="7ddad-110">CurrentPowerShellTab</span></span>

> <span data-ttu-id="7ddad-111">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7ddad-111">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7ddad-112">フォーカスしている PowerShell タブを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="7ddad-112">The read-only property that gets the PowerShell tab that has the focus.</span></span>

### <a name="currentvisiblehorizontaltool"></a><span data-ttu-id="7ddad-113">CurrentVisibleHorizontalTool</span><span class="sxs-lookup"><span data-stu-id="7ddad-113">CurrentVisibleHorizontalTool</span></span>

> <span data-ttu-id="7ddad-114">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7ddad-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7ddad-115">エディターの下部にある水平方向のツール ウィンドウに現在表示されている Windows PowerShell ISE アドオン ツールを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="7ddad-115">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the horizontal tool pane at the bottom of the editor.</span></span>

### <a name="currentvisibleverticaltool"></a><span data-ttu-id="7ddad-116">CurrentVisibleVerticalTool</span><span class="sxs-lookup"><span data-stu-id="7ddad-116">CurrentVisibleVerticalTool</span></span>

> <span data-ttu-id="7ddad-117">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7ddad-117">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7ddad-118">エディターの右側にある垂直方向のツール ウィンドウに現在表示されている Windows PowerShell ISE アドオン ツールを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="7ddad-118">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the vertical tool pane on the right side of the editor.</span></span>

### <a name="options"></a><span data-ttu-id="7ddad-119">オプション</span><span class="sxs-lookup"><span data-stu-id="7ddad-119">Options</span></span>

> <span data-ttu-id="7ddad-120">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7ddad-120">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7ddad-121">Windows PowerShell ISE の設定を変更することができるさまざまなオプションを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="7ddad-121">The read-only property that gets the various options that can change settings in Windows PowerShell ISE.</span></span>

### <a name="powershelltabs"></a><span data-ttu-id="7ddad-122">PowerShellTabs</span><span class="sxs-lookup"><span data-stu-id="7ddad-122">PowerShellTabs</span></span>

> <span data-ttu-id="7ddad-123">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7ddad-123">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="7ddad-124">Windows PowerShell ISE で開かれている PowerShell タブのコレクションを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="7ddad-124">The read-only property that gets the collection of the PowerShell tabs, which are open in Windows PowerShell ISE.</span></span> <span data-ttu-id="7ddad-125">既定では、このオブジェクトには 1 つの PowerShell タブが含まれています。ただし、スクリプトまたは Windows PowerShell ISE のメニューを使用して、このオブジェクトに他の PowerShell タブを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="7ddad-125">By default, this object contains one PowerShell tab. However, you can add more PowerShell tabs to this object by using scripts or by using the menus in Windows PowerShell ISE.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ddad-126">参照</span><span class="sxs-lookup"><span data-stu-id="7ddad-126">See Also</span></span>

- [<span data-ttu-id="7ddad-127">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="7ddad-127">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="7ddad-128">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="7ddad-128">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)