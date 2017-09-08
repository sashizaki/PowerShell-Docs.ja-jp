---
description: 
manager: carmonm
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット"
ms.date: 2016-12-12
title: "Web Access のコマンドレット"
ms.technology: powershell
ms.openlocfilehash: ac8717c2aa97d0482b4d88f1b57d621d7ff47535
ms.sourcegitcommit: 4102ecc35d473211f50a453f6ae3fbea31cb3428
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2017
---
#  <a name="windows-powershell-web-access-cmdlets"></a><span data-ttu-id="04e82-103">Windows PowerShell Web Access のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="04e82-103">Windows PowerShell Web Access Cmdlets</span></span>

<span data-ttu-id="04e82-104">このリファレンスでは、Windows PowerShell® Web Access 固有のコマンドレットの説明と構文について情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="04e82-104">This reference provides cmdlet descriptions and syntax for all Windows PowerShell® Web Access-specific cmdlets.</span></span> <span data-ttu-id="04e82-105">コマンドレットの先頭の動詞に基づいて、アルファベット順に記載しています。</span><span class="sxs-lookup"><span data-stu-id="04e82-105">It lists the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet.</span></span>

## <a name="add-pswaauthorizationruleadd-pswaauthorizationrulemd"></a>[<span data-ttu-id="04e82-106">Add-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="04e82-106">Add-PswaAuthorizationRule</span></span>](add-pswaauthorizationrule.md)

<span data-ttu-id="04e82-107">Windows PowerShell® Web Access 承認規則のセットに新しい承認規則を追加します。</span><span class="sxs-lookup"><span data-stu-id="04e82-107">Adds a new authorization rule to the Windows PowerShell® Web Access authorization rule set.</span></span>

## <a name="get-pswaauthorizationruleget-pswaauthorizationrulemd"></a>[<span data-ttu-id="04e82-108">Get-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="04e82-108">Get-PswaAuthorizationRule</span></span>](get-pswaauthorizationrule.md)

<span data-ttu-id="04e82-109">Windows PowerShell Web Access の承認規則のセットを返します。</span><span class="sxs-lookup"><span data-stu-id="04e82-109">Returns a set of the Windows PowerShell Web Access authorization rules.</span></span>

## <a name="install-pswawebapplicationinstall-pswawebapplicationmd"></a>[<span data-ttu-id="04e82-110">Install-PswaWebApplication</span><span class="sxs-lookup"><span data-stu-id="04e82-110">Install-PswaWebApplication</span></span>](install-pswawebapplication.md)

<span data-ttu-id="04e82-111">IIS で Windows PowerShell Web Access Web アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="04e82-111">Configures the Windows PowerShell Web Access web application in IIS.</span></span>

## <a name="remove-pswaauthorizationruleremove-pswaauthorizationrulemd"></a>[<span data-ttu-id="04e82-112">Remove-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="04e82-112">Remove-PswaAuthorizationRule</span></span>](remove-pswaauthorizationrule.md)

<span data-ttu-id="04e82-113">指定された承認規則を Windows PowerShell Web Access から削除します。</span><span class="sxs-lookup"><span data-stu-id="04e82-113">Removes a specified authorization rule from Windows PowerShell Web Access.</span></span>

## <a name="test-pswaauthorizationruletest-pswaauthorizationrulemd"></a>[<span data-ttu-id="04e82-114">Test-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="04e82-114">Test-PswaAuthorizationRule</span></span>](test-pswaauthorizationrule.md)

<span data-ttu-id="04e82-115">特定のユーザー、コンピューター、エンドポイント アクセス要求が承認されていることを確認する承認規則をテストします。</span><span class="sxs-lookup"><span data-stu-id="04e82-115">Tests authorization rules to validate that a particular user, computer, endpoint access request is authorized.</span></span>

## <a name="uninstall-pswawebapplicationuninstall-pswawebapplicationmd"></a>[<span data-ttu-id="04e82-116">Uninstall-PswaWebApplication</span><span class="sxs-lookup"><span data-stu-id="04e82-116">Uninstall-PswaWebApplication</span></span>](uninstall-pswawebapplication.md)

<span data-ttu-id="04e82-117">IIS から Windows PowerShell Web アプリケーションをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="04e82-117">Uninstalls the Windows PowerShell web application from IIS.</span></span>

><span data-ttu-id="04e82-118">**注**:</span><span class="sxs-lookup"><span data-stu-id="04e82-118">**Note**:</span></span>
>
><span data-ttu-id="04e82-119">利用可能なコマンドレットすべての一覧を表示するには、</span><span class="sxs-lookup"><span data-stu-id="04e82-119">To list all the cmdlets that are available, use the:</span></span>
>
> <span data-ttu-id="04e82-120">`Get-Command –Module PowerShellWebAccess` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="04e82-120">`Get-Command –Module PowerShellWebAccess` cmdlet.</span></span>

<span data-ttu-id="04e82-121">コマンドレットの詳細、構文などの情を取得するには、</span><span class="sxs-lookup"><span data-stu-id="04e82-121">For more information about, or for the syntax of, any of the cmdlets, use:</span></span>  
<span data-ttu-id="04e82-122">`Get-Help `*&lt;コマンドレット名&gt;*を使用します。</span><span class="sxs-lookup"><span data-stu-id="04e82-122">`Get-Help `*&lt;cmdlet name&gt;*</span></span>  
<span data-ttu-id="04e82-123">この*&lt;コマンドレット名&gt;*は、調べるコマンドレットの名前です。</span><span class="sxs-lookup"><span data-stu-id="04e82-123">where *&lt;cmdlet name&gt;* is the name of the cmdlet that you want to research.</span></span>

<span data-ttu-id="04e82-124">詳細については、次のコマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="04e82-124">For more detailed information, you can run any of the following cmdlets:</span></span>

-  <span data-ttu-id="04e82-125">`Get-Help `*&lt;コマンドレット名&gt;*` -Detailed`</span><span class="sxs-lookup"><span data-stu-id="04e82-125">`Get-Help `*&lt;cmdlet name&gt;*` -Detailed`</span></span>
-  <span data-ttu-id="04e82-126">`Get-Help `*&lt;コマンドレット名&gt;*` -Examples`</span><span class="sxs-lookup"><span data-stu-id="04e82-126">`Get-Help `*&lt;cmdlet name&gt;*` -Examples`</span></span>
-  <span data-ttu-id="04e82-127">`Get-Help `*&lt;コマンドレット名&gt;*` -Full`</span><span class="sxs-lookup"><span data-stu-id="04e82-127">`Get-Help `*&lt;cmdlet name&gt;*` -Full`</span></span>

### <a name="more-information"></a><span data-ttu-id="04e82-128">詳細情報</span><span class="sxs-lookup"><span data-stu-id="04e82-128">More Information</span></span>

<span data-ttu-id="04e82-129">PowerShell Web Access の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04e82-129">For more information about PowerShell Web Access, see the following:</span></span>

-   [<span data-ttu-id="04e82-130">Windows PowerShell Web Access のインストールと使用</span><span class="sxs-lookup"><span data-stu-id="04e82-130">Install and Use Windows PowerShell Web Access</span></span>](../install-and-use-windows-powershell-web-access.md)

