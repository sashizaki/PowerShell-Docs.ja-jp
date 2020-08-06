---
title: GroupBy (Format) の CustomControl 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b8265e872d34ea5dbcedfaa1668d21df8c3b35eb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786069"
---
# <a name="customcontrol-element-for-groupby-format"></a><span data-ttu-id="f2633-102">GroupBy の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f2633-102">CustomControl Element for GroupBy (Format)</span></span>

<span data-ttu-id="f2633-103">新しいグループを表示するカスタムコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="f2633-103">Defines the custom control that displays the new group.</span></span>

<span data-ttu-id="f2633-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) groupby 要素 (format) の CustomControl 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2633-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f2633-105">構文</span><span class="sxs-lookup"><span data-stu-id="f2633-105">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
<CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f2633-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f2633-106">Attributes and Elements</span></span>

<span data-ttu-id="f2633-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControl` ます。</span><span class="sxs-lookup"><span data-stu-id="f2633-107">The following sections describe the attributes, child elements, and parent element of the `CustomControl` element.</span></span> <span data-ttu-id="f2633-108">任意の数の子要素を指定し、任意の順序で一覧表示することができます。</span><span class="sxs-lookup"><span data-stu-id="f2633-108">You can specify any number of child elements and list them in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="f2633-109">属性</span><span class="sxs-lookup"><span data-stu-id="f2633-109">Attributes</span></span>

<span data-ttu-id="f2633-110">なし。</span><span class="sxs-lookup"><span data-stu-id="f2633-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f2633-111">子要素</span><span class="sxs-lookup"><span data-stu-id="f2633-111">Child Elements</span></span>

|<span data-ttu-id="f2633-112">要素</span><span class="sxs-lookup"><span data-stu-id="f2633-112">Element</span></span>|<span data-ttu-id="f2633-113">説明</span><span class="sxs-lookup"><span data-stu-id="f2633-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f2633-114">GroupBy の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f2633-114">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="f2633-115">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="f2633-115">Required element.</span></span><br /><br /> <span data-ttu-id="f2633-116">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="f2633-116">Provides the definitions for the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f2633-117">親要素</span><span class="sxs-lookup"><span data-stu-id="f2633-117">Parent Elements</span></span>

|<span data-ttu-id="f2633-118">要素</span><span class="sxs-lookup"><span data-stu-id="f2633-118">Element</span></span>|<span data-ttu-id="f2633-119">説明</span><span class="sxs-lookup"><span data-stu-id="f2633-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f2633-120">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f2633-120">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="f2633-121">Windows PowerShell がオブジェクトの新しいグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="f2633-121">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f2633-122">解説</span><span class="sxs-lookup"><span data-stu-id="f2633-122">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="f2633-123">参照</span><span class="sxs-lookup"><span data-stu-id="f2633-123">See Also</span></span>

[<span data-ttu-id="f2633-124">GroupBy の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f2633-124">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="f2633-125">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f2633-125">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="f2633-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="f2633-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
