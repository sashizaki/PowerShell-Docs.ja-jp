---
description: 
manager: dongill
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット, JEA"
ms.date: 2016-06-22
title: "はじめに"
ms.technology: powershell
ms.openlocfilehash: 71264d1001228249d9f2bb0f72473e9761170bf0
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
ms.translationtype: HT
ms.contentlocale: ja-JP
---
# <a name="introduction"></a><span data-ttu-id="96367-103">はじめに</span><span class="sxs-lookup"><span data-stu-id="96367-103">Introduction</span></span>

##  <a name="motivation"></a><span data-ttu-id="96367-104">**動機**</span><span class="sxs-lookup"><span data-stu-id="96367-104">**Motivation**</span></span>  
<span data-ttu-id="96367-105">システムに対する特権アクセスを誰かに付与することは、信頼の境界をその人物まで拡張することを意味します。</span><span class="sxs-lookup"><span data-stu-id="96367-105">When you grant someone privileged access to your systems, you extend your trust boundary to that person.</span></span>
<span data-ttu-id="96367-106">これにはリスクが伴います。なぜなら、管理者は、システムを攻撃する者になる可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="96367-106">This is a risk -- administrators are an attack surface.</span></span>
<span data-ttu-id="96367-107">内部の関係者による攻撃と資格情報の盗難は、どちらも実際によくあることです。</span><span class="sxs-lookup"><span data-stu-id="96367-107">Insider attacks and stolen credentials are both real and common.</span></span>

##  <a name="not-a-new-problem"></a><span data-ttu-id="96367-108">**新しい問題ではありません。**</span><span class="sxs-lookup"><span data-stu-id="96367-108">**Not a new problem**</span></span>  
<span data-ttu-id="96367-109">最小権限の原則を熟知し、ロール ベースのアクセス制御 (RBAC) を何らかの形で使用してアプリケーションの管理を行っているかもしれません。</span><span class="sxs-lookup"><span data-stu-id="96367-109">You are probably very familiar with the principle of least privilege, and you might use some form of role-based access control (RBAC) with applications that provide it.</span></span>
<span data-ttu-id="96367-110">ただし、このソリューションの有効性と管理容易性は、多くの場合、その適用範囲の幅広さと不正確さによる限界があります。</span><span class="sxs-lookup"><span data-stu-id="96367-110">However, the effectiveness and manageability of these solutions are often limited by their broad scope and imprecision.</span></span>
<span data-ttu-id="96367-111">さらに、RBAC には、その適用範囲にずれがあります。</span><span class="sxs-lookup"><span data-stu-id="96367-111">Furthermore, there are gaps in RBAC coverage.</span></span>
<span data-ttu-id="96367-112">たとえば、Windows では、特権アクセスの大部分はバイナリ スイッチであり、ユーザーを Administrators グループに追加するときに、不要なアクセス許可が強制的に付与されることになります。</span><span class="sxs-lookup"><span data-stu-id="96367-112">For example, in Windows, privileged access is largely a binary switch, forcing you to give unnecessary permissions when adding users to the Administrators group.</span></span>

##  <a name="just-enough-administration-jea"></a><span data-ttu-id="96367-113">**Just Enough Administration (JEA)**</span><span class="sxs-lookup"><span data-stu-id="96367-113">**Just Enough Administration (JEA)**</span></span> 
<span data-ttu-id="96367-114">PowerShell リモート処理によるロール ベースのアクセス制御 (RBAC) プラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="96367-114">Provides a role-based access control (RBAC) platform through PowerShell Remoting.</span></span>
<span data-ttu-id="96367-115">*また、特定のユーザーに管理者権限を与えることなく、そのユーザーが特定のサーバーで特定の管理タスクを実行できるようにします。*</span><span class="sxs-lookup"><span data-stu-id="96367-115">*It allows specific users to perform specific administrative tasks on servers without giving them administrator rights.*</span></span>
<span data-ttu-id="96367-116">これにより、既存の RBAC ソリューションのずれを補い、設定を容易に管理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="96367-116">This allows you to fill in the gaps between your existing RBAC solutions, and simplifies management of those settings.</span></span>

