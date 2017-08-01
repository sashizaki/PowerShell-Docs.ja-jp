---
description: 
manager: dongill
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット, JEA"
ms.date: 2016-06-22
title: "JEA のレポート"
ms.technology: powershell
ms.openlocfilehash: 3e7bd2755281f491bba8a905df018fb2e1cac6ff
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
ms.translationtype: HT
ms.contentlocale: ja-JP
---
# <a name="reporting-on-jea"></a><span data-ttu-id="b12ac-103">JEA のレポート</span><span class="sxs-lookup"><span data-stu-id="b12ac-103">Reporting on JEA</span></span>
<span data-ttu-id="b12ac-104">JEA では権限のないユーザーでも特権コンテキストを実行できるため、ログ記録と監査が極めて重要です。</span><span class="sxs-lookup"><span data-stu-id="b12ac-104">Because JEA allows non-privileged users to run in a privileged context, logging and auditing are extremely important.</span></span>
<span data-ttu-id="b12ac-105">このセクションでは、ログ記録とレポートに役立つツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="b12ac-105">In this section, we'll run through the tools you can use to help you with logging and reporting.</span></span>

## <a name="reporting-on-jea-actions"></a><span data-ttu-id="b12ac-106">JEA 操作のレポート</span><span class="sxs-lookup"><span data-stu-id="b12ac-106">Reporting on JEA Actions</span></span>
### <a name="over-the-shoulder-transcription"></a><span data-ttu-id="b12ac-107">Over-the-Shoulder トランスクリプト</span><span class="sxs-lookup"><span data-stu-id="b12ac-107">Over-the-Shoulder Transcription</span></span>
<span data-ttu-id="b12ac-108">PowerShell セッションで何が行われているかその概要を取得する最も簡単な方法の 1 つとして、入力している人を覗き見ることです。</span><span class="sxs-lookup"><span data-stu-id="b12ac-108">One of the quickest ways to get a summary of what's happening in a PowerShell session is to look over the shoulder of the person typing.</span></span>
<span data-ttu-id="b12ac-109">使っているコマンド、そのコマンドによる出力がわかります。何も問題はありません。</span><span class="sxs-lookup"><span data-stu-id="b12ac-109">You see their commands, the output of those commands, and all is well.</span></span>
<span data-ttu-id="b12ac-110">または、あったとしても、少なくとも情報を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="b12ac-110">Or it's not, but at least you'll know.</span></span>
<span data-ttu-id="b12ac-111">PowerShell トランスクリプションは、事後的に同類のビューを提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="b12ac-111">PowerShell transcription is designed to give you a similar view after the fact.</span></span>

<span data-ttu-id="b12ac-112">セッション構成で TranscriptDirectory フィールドを使用した場合、PowerShell は特定のセッションで実行されたすべてのアクションのトランスクリプトを自動的に記録します。</span><span class="sxs-lookup"><span data-stu-id="b12ac-112">When using the "TranscriptDirectory" field in your Session Configuration, PowerShell will automatically record a transcript of all actions taken in a given session.</span></span>
<span data-ttu-id="b12ac-113">セッションのトランスクリプトは、次のドキュメントにあります: $env:ProgramData\JEAConfiguration\Transcripts。</span><span class="sxs-lookup"><span data-stu-id="b12ac-113">You can find transcripts from your sessions in this document here: "$env:ProgramData\JEAConfiguration\Transcripts"</span></span>

<span data-ttu-id="b12ac-114">おわかりのとおり、トランスクリプトは "接続されているユーザー"、RunAs ユーザー、セッションで実行されたコマンドなどを記録します。</span><span class="sxs-lookup"><span data-stu-id="b12ac-114">As you can tell, the transcript records information about the "Connected" user, the "Run As" user, the commands run in the session, and more.</span></span>
<span data-ttu-id="b12ac-115">PowerShell トランスクリプションについて詳しくは、[こちらのブログ投稿](http://blogs.msdn.com/b/powershell/archive/2015/06/09/powershell-the-blue-team.aspx)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b12ac-115">For more information about PowerShell transcription, check out [this blog post](http://blogs.msdn.com/b/powershell/archive/2015/06/09/powershell-the-blue-team.aspx).</span></span>

### <a name="powershell-event-logs"></a><span data-ttu-id="b12ac-116">PowerShell イベント ログ</span><span class="sxs-lookup"><span data-stu-id="b12ac-116">PowerShell Event Logs</span></span>
<span data-ttu-id="b12ac-117">モジュールのログ記録を有効にした場合、すべての PowerShell アクションも正規の Windows イベント ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="b12ac-117">When you have module logging turned on, all PowerShell actions are also recorded in regular Windows Event logs.</span></span>
<span data-ttu-id="b12ac-118">これはトランスクリプトに比べて多少扱いにくいものの、詳細な情報が提供されるため便利です。</span><span class="sxs-lookup"><span data-stu-id="b12ac-118">This is slightly messier to deal with when compared to transcripts, but the level of detail it gives you can be useful.</span></span>

<span data-ttu-id="b12ac-119">PowerShell の操作ログでは、モジュールのログ記録を有効にしている場合、呼び出された各コマンドがイベント ID 4104 によって記録されます。</span><span class="sxs-lookup"><span data-stu-id="b12ac-119">In the "PowerShell" operational log, Event ID 4104 will record each command invoked if you have enabled module logging.</span></span>

### <a name="other-event-logs"></a><span data-ttu-id="b12ac-120">その他のイベント ログ</span><span class="sxs-lookup"><span data-stu-id="b12ac-120">Other Event Logs</span></span>
<span data-ttu-id="b12ac-121">PowerShell ログおよびトランスクリプトと異なり、他のログ記録メカニズムでは "接続されているユーザー" は取得されません。</span><span class="sxs-lookup"><span data-stu-id="b12ac-121">Unlike PowerShell logs and transcripts, other logging mechanisms will not capture the "Connected User".</span></span>
<span data-ttu-id="b12ac-122">他のログと PowerShell ログの整合性を図るには、これらを相互に関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="b12ac-122">You will need to do some correlation between other logs and PowerShell logs to match up actions taken.</span></span>

<span data-ttu-id="b12ac-123">"Windows リモート管理" 操作ログでは、イベント ID 193 により、接続しているユーザーの SID と名前に加え、RunAs 仮想アカウントの SID が記録されこの関連付けがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b12ac-123">In the "Windows Remote Management" operational log, Event ID 193 will record the Connecting User's SID and Name, as well as the RunAs Virtual Account's SID to assist with this correlation.</span></span>
<span data-ttu-id="b12ac-124">RunAs 仮想アカウントの名前の末尾に、接続しているユーザーのドメインとユーザー名が含まれていることにお気付きかもしれません。</span><span class="sxs-lookup"><span data-stu-id="b12ac-124">You may have also noticed that the name of the RunAs Virtual Account includes the connecting user's domain and username at the end.</span></span>

## <a name="reporting-on-jea-configuration"></a><span data-ttu-id="b12ac-125">JEA 構成のレポート</span><span class="sxs-lookup"><span data-stu-id="b12ac-125">Reporting on JEA Configuration</span></span>
### <a name="get-pssessionconfiguration"></a><span data-ttu-id="b12ac-126">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="b12ac-126">Get-PSSessionConfiguration</span></span>
<span data-ttu-id="b12ac-127">使用している環境の状態の正確なレポートを取得するために、コンピューターにセットアップした JEA エンドポイントの数を把握しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="b12ac-127">In order to accurately report on the state of your environment, it's important to know how many JEA endpoints you have set up on your machine.</span></span>
<span data-ttu-id="b12ac-128">`Get-PSSessionConfiguration` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b12ac-128">`Get-PSSessionConfiguration` does just that.</span></span>

### <a name="get-pssessioncapability"></a><span data-ttu-id="b12ac-129">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="b12ac-129">Get-PSSessionCapability</span></span>
<span data-ttu-id="b12ac-130">JEA エンドポイントを介して特定のユーザーの機能を手動でレポートすることは、非常に複雑になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b12ac-130">Manually reporting on the capabilities of any given user through a JEA endpoint can be quite complex.</span></span>
<span data-ttu-id="b12ac-131">いくつかのロール機能の調査が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b12ac-131">You would potentially need to inspect several role capabilities.</span></span>
<span data-ttu-id="b12ac-132">幸い、ここでは Get-PSSessionCapability コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b12ac-132">Fortunately, the "Get-PSSessionCapability" cmdlet does this.</span></span>

<span data-ttu-id="b12ac-133">これをテストするには、管理者の PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b12ac-133">To test this out, run the following command from an administrator PowerShell prompt:</span></span>
```PowerShell
Get-PSSessionCapability -Username 'CONTOSO\OperatorUser' -ConfigurationName JEADemo
```

