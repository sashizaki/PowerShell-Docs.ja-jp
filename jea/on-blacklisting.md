---
description: 
manager: dongill
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット, JEA"
ms.date: 2016-06-22
title: "ブラックリストへの登録"
ms.technology: powershell
ms.openlocfilehash: e823cc0b130500fb7ea60e65acf27f90ad3f3802
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
ms.translationtype: HT
ms.contentlocale: ja-JP
---
### <a name="on-blacklisting"></a><span data-ttu-id="db19e-103">ブラックリストへの登録</span><span class="sxs-lookup"><span data-stu-id="db19e-103">On Blacklisting</span></span>
<span data-ttu-id="db19e-104">JEA を一通り試したら、コマンドをブラックリストに登録できるか気になるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="db19e-104">After playing around with JEA, you may be wondering if it is possible to blacklist commands.</span></span>
<span data-ttu-id="db19e-105">これはもっともな要求ですが、現時点では次の理由で JEA ではその予定はありません。</span><span class="sxs-lookup"><span data-stu-id="db19e-105">This is an understandable request, but it is not currently planned for JEA for the following reasons:</span></span>

1.  <span data-ttu-id="db19e-106">JEA では、オペレーターの操作を、オペレーターが必要なアクションにのみ制限しています。</span><span class="sxs-lookup"><span data-stu-id="db19e-106">We designed JEA to limit operators to only the actions they need to do.</span></span>
<span data-ttu-id="db19e-107">ブラックリストは、その対極に位置します。</span><span class="sxs-lookup"><span data-stu-id="db19e-107">A blacklist is the opposite.</span></span>

2.  <span data-ttu-id="db19e-108">PowerShell コマンドの設計者は、その設計時に JEA を念頭に置いていませんでした。</span><span class="sxs-lookup"><span data-stu-id="db19e-108">PowerShell command authors did not design PowerShell commands with the JEA in mind.</span></span>
<span data-ttu-id="db19e-109">Windows Server 2016 の初期インストール時には、1520 個のコマンドを直ちに使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="db19e-109">On a fresh install of Windows Server 2016, there are about 1520 commands immediately available.</span></span>
<span data-ttu-id="db19e-110">これらのコマンドの脅威モデルには、ユーザーがより特権の高いアカウントとしてコマンドを実行するようになるという可能性は含まれていませんでした。</span><span class="sxs-lookup"><span data-stu-id="db19e-110">The threat models for these commands did not include the possibility that a user would be running commands as a more privileged account.</span></span>
<span data-ttu-id="db19e-111">たとえば、特定のコマンドでは、設計上のコード インジェクションが許可されます (コア PowerShell モジュールの Add-Type や Invoke-Command など)。</span><span class="sxs-lookup"><span data-stu-id="db19e-111">For example, certain commands allow for code injection by design (e.g. Add-Type and Invoke-Command in the core PowerShell module).</span></span>
<span data-ttu-id="db19e-112">マイクロソフトは、認識しているコマンドが公開されると JEA により警告を表示できますが、新しい脅威モデルに基づいて Windows の他のすべてのコマンドを再評価することはしていません。</span><span class="sxs-lookup"><span data-stu-id="db19e-112">JEA can warn you when you expose the specific commands we know about, but we have not re-assessed every other command in Windows based on the new threat model.</span></span>
<span data-ttu-id="db19e-113">JEA を通じて公開するコマンドの機能はご自身で把握している必要があります。</span><span class="sxs-lookup"><span data-stu-id="db19e-113">You must understand the capabilities of the commands you exposing through JEA.</span></span>  

3.  <span data-ttu-id="db19e-114">また、JEA がコード インジェクションの脆弱性によりすべてのコマンドをブロックしていても、悪意のあるユーザーがブラックリストに掲載された操作を他の関連するコマンドで実行できなくなるという保証はありません。</span><span class="sxs-lookup"><span data-stu-id="db19e-114">Furthermore, even if JEA blocked all commands with code-injection vulnerabilities, there is no guarantee that a malicious user would not be able to carry out a blacklisted action with another related command.</span></span>
<span data-ttu-id="db19e-115">特定の操作を確実に実行されないようにするには、公開するすべてのコマンドを理解しておくことが不可欠です。</span><span class="sxs-lookup"><span data-stu-id="db19e-115">Unless you understand all of the commands that you are exposing, it is impossible for you to guarantee that a certain action is not possible.</span></span>
<span data-ttu-id="db19e-116">ホワイトリストまたはブラックリストの使用の有無にかかわらず、ご自身の判断のもと、公開するコマンドを選択してください。</span><span class="sxs-lookup"><span data-stu-id="db19e-116">The burden is on you to understand what commands you are exposing, whether they are using a whitelist or a blacklist.</span></span>
<span data-ttu-id="db19e-117">ブラックリストで公開されるコマンドは管理することが困難なため、JEA は代わりにホワイトリストを使って実装されます。</span><span class="sxs-lookup"><span data-stu-id="db19e-117">The number of commands a blacklist would expose is unmanageable, so JEA is implemented using whitelists instead.</span></span>

