---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: オブジェクトの操作
ms.assetid: 7ecc94a4-015c-4459-ae58-85289ea09030
ms.openlocfilehash: 5d86e1658286055f8a7dc57d488a6adcef577a10
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085985"
---
# <a name="working-with-objects"></a><span data-ttu-id="db811-103">オブジェクトの操作</span><span class="sxs-lookup"><span data-stu-id="db811-103">Working with Objects</span></span>

<span data-ttu-id="db811-104">Windows PowerShell がオブジェクトを使用してコマンドレット間でデータを転送する方法について説明しました。また、実際に Get-Member コマンドレットを使用してオブジェクトの詳細情報を表示したり、Format コマンドレットを使用してオブジェクトの特定のプロパティを表示したりする方法を紹介しました。</span><span class="sxs-lookup"><span data-stu-id="db811-104">We have discussed how Windows PowerShell uses objects to transfer data between cmdlets, and demonstrated a few ways to view detailed information about objects by using Get-Member and Format cmdlets to view particular properties of objects.</span></span>

<span data-ttu-id="db811-105">オブジェクトの優れた機能は、既に相互に関連付けられている多数の複雑なデータへのアクセスを提供することです。</span><span class="sxs-lookup"><span data-stu-id="db811-105">The power of objects is that they provide you with access to a lot of complex data, and it is already correlated.</span></span> <span data-ttu-id="db811-106">いくつかの簡単な方法を使用してオブジェクトをさらに細かく操作することで、より多くの作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="db811-106">With some simple techniques you can further manipulate objects to do even more work.</span></span> <span data-ttu-id="db811-107">この章では、特定の種類のオブジェクト、およびそれらの操作方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="db811-107">We are going to look at some specific types of objects and ways you can manipulate them in this chapter.</span></span>