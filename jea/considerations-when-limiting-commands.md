---
description: 
manager: dongill
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット, JEA"
ms.date: 2016-06-22
title: "コマンドの制限時の考慮事項"
ms.technology: powershell
ms.openlocfilehash: 0b4396ee130d99c42f613c1b79193c236ad472e7
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
ms.translationtype: HT
ms.contentlocale: ja-JP
---
### <a name="considerations-when-limiting-commands"></a><span data-ttu-id="69c28-103">コマンドの制限時の考慮事項</span><span class="sxs-lookup"><span data-stu-id="69c28-103">Considerations When Limiting Commands</span></span>
<span data-ttu-id="69c28-104">この手順では、考慮すべき重量な点が 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="69c28-104">There is one important point to make about this step.</span></span>
<span data-ttu-id="69c28-105">JEA を通じて公開されるすべての機能は、管理者によって制限された領域に配置することが重要です。</span><span class="sxs-lookup"><span data-stu-id="69c28-105">It is critical that all capabilities exposed through JEA are located in administrator-restricted areas.</span></span>
<span data-ttu-id="69c28-106">管理者以外のユーザーは、JEA エンドポイント経由で使用されるスクリプトを変更する機能を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="69c28-106">Non-administrator users should not have the capability to modify the scripts used through JEA endpoints.</span></span>

<span data-ttu-id="69c28-107">関連する注意事項として、JEA ユーザーに、その JEA セッション内で JEA 構成やホワイトリストに載ったスクリプトを上書きする権限を付与しないでください。</span><span class="sxs-lookup"><span data-stu-id="69c28-107">On a related note, it is critical that you do not give JEA users the ability to overwrite JEA configurations and whitelisted scripts within their JEA sessions.</span></span>
<span data-ttu-id="69c28-108">`Copy-Item` のようなコマンドを公開するときは十分に注意してください。</span><span class="sxs-lookup"><span data-stu-id="69c28-108">Be extremely careful when exposing commands like `Copy-Item`!</span></span>

