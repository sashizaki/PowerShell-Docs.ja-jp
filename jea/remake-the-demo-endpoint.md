---
description: 
manager: dongill
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット, JEA"
ms.date: 2016-06-22
title: "デモ エンドポイントを作り直す"
ms.technology: powershell
ms.openlocfilehash: 4a56272b6f995500d443d441f5e03db85dac6f96
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
ms.translationtype: HT
ms.contentlocale: ja-JP
---
# <a name="remake-the-demo-endpoint"></a><span data-ttu-id="ad962-103">デモ エンドポイントを作り直す</span><span class="sxs-lookup"><span data-stu-id="ad962-103">Remake the Demo Endpoint</span></span>
<span data-ttu-id="ad962-104">このセクションでは、前のセクションで使用したデモ エンドポイントの完全なレプリカを生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ad962-104">In this section, you will learn how to generate an exact replica of the demo endpoint you used in the above section.</span></span>
<span data-ttu-id="ad962-105">ここでは、PowerShell セッション構成とロール機能を含む、JEA を理解するために必要な中心概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="ad962-105">This will introduce core concepts that are necessary to understand JEA, including PowerShell Session Configurations and Role Capabilities.</span></span>

## <a name="powershell-session-configurations"></a><span data-ttu-id="ad962-106">PowerShell セッション構成</span><span class="sxs-lookup"><span data-stu-id="ad962-106">PowerShell Session Configurations</span></span>
<span data-ttu-id="ad962-107">前のセクションで JEA を使用したとき、次のコマンドを実行することから始めました。</span><span class="sxs-lookup"><span data-stu-id="ad962-107">When you used JEA in the above section, you started by running the following command:</span></span>

```PowerShell
Enter-PSSession -ComputerName . -ConfigurationName JEA_Demo -Credential $NonAdminCred
```

<span data-ttu-id="ad962-108">ほとんどのパラメーターは見ればわかりますが、*ConfigurationName* パラメーターは、最初はわかりにくいかもしれません。</span><span class="sxs-lookup"><span data-stu-id="ad962-108">While most of the parameters are self-explanatory, the *ConfigurationName* parameter may seem confusing at first.</span></span>
<span data-ttu-id="ad962-109">そのパラメーターは、接続される PowerShell セッション構成を指定していました。</span><span class="sxs-lookup"><span data-stu-id="ad962-109">That parameter specified the PowerShell Session Configuration to which you were connecting.</span></span>

<span data-ttu-id="ad962-110">*PowerShell セッション構成*は、PowerShell エンドポイントの別名です。</span><span class="sxs-lookup"><span data-stu-id="ad962-110">*PowerShell Session Configuration* is a fancy term for a PowerShell endpoint.</span></span>
<span data-ttu-id="ad962-111">それは、ユーザーが接続して PowerShell の機能にアクセスする比喩的な "場所" です。</span><span class="sxs-lookup"><span data-stu-id="ad962-111">It is the figurative "place" where users connect and get access to PowerShell functionality.</span></span>
<span data-ttu-id="ad962-112">セッション構成の設定方法に基づいて、接続しているユーザーに異なる機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="ad962-112">Based on how you set up a Session Configuration, it can provide different functionality to connecting users.</span></span>
<span data-ttu-id="ad962-113">JEA では、セッション構成を使用して、PowerShell の機能を限定されたセットに制限し、特権のある仮想アカウントとして実行します。</span><span class="sxs-lookup"><span data-stu-id="ad962-113">For JEA, we use Session Configurations to restrict PowerShell to a limited set of functionality and to run as a privileged virtual account.</span></span>

<span data-ttu-id="ad962-114">既にいくつかの PowerShell セッション構成がコンピューターに登録されていますが、それぞれの設定はわずかに異なります。</span><span class="sxs-lookup"><span data-stu-id="ad962-114">You already have several registered PowerShell Session Configurations on your machine, each set up slightly differently.</span></span>
<span data-ttu-id="ad962-115">ほとんどは Windows に付属していますが、"JEA_Demo" セッション構成は「[前提条件](prerequisites.md)」セクションで設定したものです。</span><span class="sxs-lookup"><span data-stu-id="ad962-115">Most of them come with Windows, but the "JEA_Demo" Session Configuration was set up in the [prerequisites](prerequisites.md) section.</span></span>
<span data-ttu-id="ad962-116">Administrator PowerShell プロンプトで次のコマンドを実行することで、登録されているすべてのセッション構成を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ad962-116">You can see all registered Session Configurations by running the following command in an Administrator PowerShell prompt:</span></span>

```PowerShell
Get-PSSessionConfiguration
```

## <a name="powershell-session-configuration-files"></a><span data-ttu-id="ad962-117">PowerShell セッション構成ファイル</span><span class="sxs-lookup"><span data-stu-id="ad962-117">PowerShell Session Configuration Files</span></span>
<span data-ttu-id="ad962-118">新しいセッション構成は、新しい *PowerShell セッション構成ファイル*を登録することで作成できます。</span><span class="sxs-lookup"><span data-stu-id="ad962-118">You can make new Session Configurations by registering new *PowerShell Session Configuration Files*.</span></span>
<span data-ttu-id="ad962-119">セッション構成ファイルのファイル拡張子は ".pssc" です。</span><span class="sxs-lookup"><span data-stu-id="ad962-119">Session Configuration Files have ".pssc" file extensions.</span></span>
<span data-ttu-id="ad962-120">セッション構成ファイルは、New-PSSessionConfigurationFile コマンドレットを使用して生成できます。</span><span class="sxs-lookup"><span data-stu-id="ad962-120">You can generate Session Configuration Files with the New-PSSessionConfigurationFile cmdlet.</span></span>

<span data-ttu-id="ad962-121">この後、JEA 用の新しいセッション構成を作成して登録します。</span><span class="sxs-lookup"><span data-stu-id="ad962-121">Next, you are going to create and register a new Session Configuration for JEA.</span></span>

## <a name="generate-and-modify-your-powershell-session-configuration"></a><span data-ttu-id="ad962-122">PowerShell セッション構成を生成して変更する</span><span class="sxs-lookup"><span data-stu-id="ad962-122">Generate and Modify your PowerShell Session Configuration</span></span>
<span data-ttu-id="ad962-123">次のコマンドを実行して、PowerShell セッション構成の "スケルトン" ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="ad962-123">Run the following command to generate a PowerShell Session Configuration "skeleton" file.</span></span>

```PowerShell
New-PSSessionConfigurationFile -Path "$env:ProgramData\JEAConfiguration\JEADemo2.pssc"
```

> <span data-ttu-id="ad962-124">**ヒント:** 既定では、スケルトン ファイルには、最も一般的な構成設定のみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ad962-124">**TIP:** Only the most common configuration settings are included in the skeleton file by default.</span></span>
> <span data-ttu-id="ad962-125">`-Full` パラメーターを使用して、適用できるすべての設定を、生成される PSSC に含めてください。</span><span class="sxs-lookup"><span data-stu-id="ad962-125">Use the `-Full` parameter to include all applicable settings in the generated PSSC.</span></span>

<span data-ttu-id="ad962-126">PowerShell ISE または任意のテキスト エディターでファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ad962-126">Open the file in PowerShell ISE, or your favorite text editor.</span></span>

```PowerShell
ise "$env:ProgramData\JEAConfiguration\JEADemo2.pssc"
```

<span data-ttu-id="ad962-127">ファイルの次のフィールドを、その下に示されている値に更新します。(管理者以外のセキュリティ グループに置き換えるのを忘れないでください)。</span><span class="sxs-lookup"><span data-stu-id="ad962-127">Update the following fields in the file with the values below (remember to substitute in your own non-administrator security group):</span></span>

```PowerShell
# OLD: SessionType = 'Default'
SessionType = 'RestrictedRemoteServer'

# OLD: TranscriptDirectory = 'C:\Transcripts\'
TranscriptDirectory = "C:\ProgramData\JEAConfiguration\Transcripts"

# OLD: # RunAsVirtualAccount = $true
RunAsVirtualAccount = $true

# OLD: RoleDefinitions = @{ 'CONTOSO\SqlAdmins' = @{ RoleCapabilities = 'SqlAdministration' }; 'CONTOSO\ServerMonitors' = @{ VisibleCmdlets = 'Get-Process' } }
RoleDefinitions = @{'CONTOSO\JEA_NonAdmin_Operator' = @{ RoleCapabilities =  'Maintenance' }}
```

<span data-ttu-id="ad962-128">各エントリの意味は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ad962-128">Here is what each of those entries mean:</span></span>

1.  <span data-ttu-id="ad962-129">*SessionType* フィールドは、このエンドポイントで使用する事前設定された既定の設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad962-129">The *SessionType* field defines preset default settings to use with this endpoint.</span></span>
<span data-ttu-id="ad962-130">*RestrictedRemoteServer* は、リモート管理を行うために必要な最小限の設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad962-130">*RestrictedRemoteServer* defines the minimal settings necessary for remote management.</span></span>
<span data-ttu-id="ad962-131">既定では、*RestrictedRemoteServer* エンドポイントは、Get-Command、Get-FormatData、Select-Object、Get-Help、Measure-Object、Exit-PSSession、Clear-Host、および Out-Default を公開します。</span><span class="sxs-lookup"><span data-stu-id="ad962-131">By default, a *RestrictedRemoteServer* endpoint will expose Get-Command, Get-FormatData, Select-Object, Get-Help, Measure-Object, Exit-PSSession, Clear-Host, and Out-Default.</span></span>
<span data-ttu-id="ad962-132">それは、*ExecutionPolicy* を *RemoteSigned* に設定し、*LanguageMode* を *NoLanguage* に設定します。</span><span class="sxs-lookup"><span data-stu-id="ad962-132">It will set the *ExecutionPolicy* to *RemoteSigned*, and the *LanguageMode* to *NoLanguage*.</span></span>
<span data-ttu-id="ad962-133">これらの設定の実際の効果は、エンドポイントを構成するためのセキュリティで保護された最小限の構成の開始点になることです。</span><span class="sxs-lookup"><span data-stu-id="ad962-133">The net effect of these settings is a secure and minimal starting point for configuring your endpoint.</span></span>

2.  <span data-ttu-id="ad962-134">*RoleDefinitions* フィールドは、ロール機能を特定のグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ad962-134">The *RoleDefinitions* field assigns Role Capabilities to specific groups.</span></span>
<span data-ttu-id="ad962-135">これは、特権アカウントとして誰が何を実行できるかを定義します。</span><span class="sxs-lookup"><span data-stu-id="ad962-135">It defines who can do what as a privileged account.</span></span>
<span data-ttu-id="ad962-136">このフィールドを使用して、接続しているユーザーがグループ メンバーシップに基づいて利用できる機能を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ad962-136">With this field, you can specify the functionality available to any connecting user based on group membership.</span></span>
<span data-ttu-id="ad962-137">これは、JEA の RBAC 機能の核心です。</span><span class="sxs-lookup"><span data-stu-id="ad962-137">This is the core of JEA's RBAC functionality.</span></span>
<span data-ttu-id="ad962-138">この例では、事前に作成された "保守管理用の" ロール機能を "Contoso\JEA_NonAdmin_Operator" グループのメンバーに公開しています。</span><span class="sxs-lookup"><span data-stu-id="ad962-138">In this example, you are exposing the pre-made "Maintenance" RoleCapability to members of the "Contoso\JEA_NonAdmin_Operator" group.</span></span>

3.  <span data-ttu-id="ad962-139">*RunAsVirtualAccount* フィールドは、このエンドポイントで PowerShell を仮想アカウント "として (RunAs)" 実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="ad962-139">The *RunAsVirtualAccount* field indicates that PowerShell should "run as" a Virtual Account at this endpoint.</span></span>
<span data-ttu-id="ad962-140">既定では、仮想アカウントは、組み込み Administrators グループのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="ad962-140">By default, the Virtual Account is a member of the built in Administrators group.</span></span>
<span data-ttu-id="ad962-141">ドメイン コントローラーでは、既定では、Domain Administrators グループのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="ad962-141">On a domain controller, it is also a member of the Domain Administrators group by default.</span></span>
<span data-ttu-id="ad962-142">このガイドの後半で、仮想アカウントの特権をカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ad962-142">Later in this guide, you will learn how to customize the privileges of the Virtual Account.</span></span>

4.  <span data-ttu-id="ad962-143">*TranscriptDirectory* フィールドは、各リモート セッションの後で "肩越しの" PowerShell トランスクリプトを保存する場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad962-143">The *TranscriptDirectory* field defines where "over-the-shoulder" PowerShell transcripts are saved after each remote session.</span></span>
<span data-ttu-id="ad962-144">これらのトランスクリプトを使用して、各セッションで実行された操作を読みやすい方法で調べることができます。</span><span class="sxs-lookup"><span data-stu-id="ad962-144">These transcripts allow you to inspect the actions taken in each session in a readable way.</span></span>
<span data-ttu-id="ad962-145">PowerShell トランスクリプトについて詳しくは、[こちらのブログ投稿](http://blogs.msdn.com/b/powershell/archive/2015/06/09/powershell-the-blue-team.aspx)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ad962-145">For more information about PowerShell transcripts, check out this [blog post](http://blogs.msdn.com/b/powershell/archive/2015/06/09/powershell-the-blue-team.aspx).</span></span>
<span data-ttu-id="ad962-146">注: 標準の Windows Eventing も、各ユーザーが PowerShell で何を実行したかについての情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="ad962-146">Note: regular Windows Eventing also captures information about what each user ran with PowerShell.</span></span>
<span data-ttu-id="ad962-147">トランスクリプトのほうが、少し読みやすくなっています。</span><span class="sxs-lookup"><span data-stu-id="ad962-147">Transcripts are just a bit more readable.</span></span>

<span data-ttu-id="ad962-148">最後に、変更を *JEADemo2.pssc* に保存します。</span><span class="sxs-lookup"><span data-stu-id="ad962-148">Finally, save your changes to *JEADemo2.pssc*.</span></span>

## <a name="apply-the-powershell-session-configuration"></a><span data-ttu-id="ad962-149">PowerShell セッション構成を適用する</span><span class="sxs-lookup"><span data-stu-id="ad962-149">Apply the PowerShell Session Configuration</span></span>

<span data-ttu-id="ad962-150">セッション構成ファイルからエンドポイントを作成するには、ファイルを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad962-150">To create an endpoint from a Session Configuration file, you need to register the file.</span></span>
<span data-ttu-id="ad962-151">これを行うには、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="ad962-151">This requires a few pieces of information:</span></span>

1. <span data-ttu-id="ad962-152">セッション構成ファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="ad962-152">The path to the Session Configuration file.</span></span>
2. <span data-ttu-id="ad962-153">登録されるセッション構成の名前。</span><span class="sxs-lookup"><span data-stu-id="ad962-153">The name of your registered Session Configuration.</span></span> <span data-ttu-id="ad962-154">これは、ユーザーが `Enter-PSSession` または `New-PSSession` を使用してエンドポイントに接続するときに "ConfigurationName" パラメーターに指定する名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="ad962-154">This is the same name users provide to the "ConfigurationName" parameter when they connect to your endpoint with `Enter-PSSession` or `New-PSSession`.</span></span>

<span data-ttu-id="ad962-155">ローカル コンピューターにセッション構成を登録するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad962-155">To register the Session Configuration on your local machine, run the following command:</span></span>

```PowerShell
Register-PSSessionConfiguration -Name 'JEADemo2' -Path "$env:ProgramData\JEAConfiguration\JEADemo2.pssc"
```

<span data-ttu-id="ad962-156">以上で、</span><span class="sxs-lookup"><span data-stu-id="ad962-156">Congratulations!</span></span> <span data-ttu-id="ad962-157">JEA エンドポイントが設定されました。</span><span class="sxs-lookup"><span data-stu-id="ad962-157">You have set up your JEA endpoint.</span></span>

## <a name="test-out-your-endpoint"></a><span data-ttu-id="ad962-158">エンドポイントをテストする</span><span class="sxs-lookup"><span data-stu-id="ad962-158">Test Out Your Endpoint</span></span>
<span data-ttu-id="ad962-159">「[JEA の使用](using-jea.md)」セクションに示されている手順をもう一度実行して、新しいエンドポイントが意図したとおりに動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad962-159">Re-run the steps listed in the [Using JEA](using-jea.md) section against your new endpoint to confirm it is operating as intended.</span></span>
<span data-ttu-id="ad962-160">`Enter-PSSession` に構成名を指定するときに、新しいエンドポイント名 (JEADemo2) を必ず使用してください。</span><span class="sxs-lookup"><span data-stu-id="ad962-160">Be sure to use the new endpoint name (JEADemo2) when providing the configuration name to `Enter-PSSession`.</span></span>

```PowerShell
Enter-PSSession -ComputerName . -ConfigurationName JEADemo2 -Credential $NonAdminCred
```

## <a name="key-concepts"></a><span data-ttu-id="ad962-161">主要概念</span><span class="sxs-lookup"><span data-stu-id="ad962-161">Key Concepts</span></span>
<span data-ttu-id="ad962-162">**PowerShell セッション構成**: *PowerShell エンドポイント* と呼ばれることもあります。これは、ユーザーが接続して PowerShell の機能にアクセスする比喩的な "場所" です。</span><span class="sxs-lookup"><span data-stu-id="ad962-162">**PowerShell Session Configuration**: Sometimes referred to as *PowerShell Endpoint*, this is the figurative "place" where users connect and get access to PowerShell functionality.</span></span>
<span data-ttu-id="ad962-163">`Get-PSSessionConfiguration` を実行することで、システムに登録されているセッション構成を一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="ad962-163">You can list the registered Session Configurations on your system by running `Get-PSSessionConfiguration`.</span></span>
<span data-ttu-id="ad962-164">特別な方法で構成した PowerShell セッション構成を *JEA エンドポイント*と呼ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="ad962-164">When configured in a specific way, a PowerShell Session Configuration can be called a *JEA Endpoint*.</span></span>

<span data-ttu-id="ad962-165">**PowerShell セッション構成ファイル (.pssc)**: 登録すると、PowerShell セッション構成の設定を定義するファイルです。</span><span class="sxs-lookup"><span data-stu-id="ad962-165">**PowerShell Session Configuration File (.pssc)**: A file that, when registered, defines settings for a PowerShell Session Configuration.</span></span>
<span data-ttu-id="ad962-166">エンドポイントに接続できるユーザー ロール、仮想アカウント "として (RunAs)" 実行するアカウントなどの仕様が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ad962-166">It contains specifications for user roles that can connect to the endpoint, the "run as" Virtual Account, and more.</span></span>     

<span data-ttu-id="ad962-167">**ロール定義**: セッション構成ファイル内のフィールドであり、接続しているユーザーに与えられるロール機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad962-167">**Role Definitions**: The field in a Session Configuration File that defines the Role Capabilities granted to connecting users.</span></span>
<span data-ttu-id="ad962-168">これは、特権アカウントとして、*誰が**何を*実行できるかを定義します。</span><span class="sxs-lookup"><span data-stu-id="ad962-168">It defines *who* can do *what* as a privileged account.</span></span>
<span data-ttu-id="ad962-169">これは、JEA の RBAC 機能の核心です。</span><span class="sxs-lookup"><span data-stu-id="ad962-169">This is the core of JEA's RBAC capabilities.</span></span>

<span data-ttu-id="ad962-170">**SessionType**: セッション構成の既定の設定を表すセッション構成ファイル内のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="ad962-170">**SessionType**: A field in a Session Configuration File that represents default settings for a Session Configuration.</span></span>
<span data-ttu-id="ad962-171">JEA エンドポイントでは、このフィールドは RestrictedRemoteServer に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad962-171">For JEA endpoints, this must be set to RestrictedRemoteServer.</span></span>

<span data-ttu-id="ad962-172">**PowerShell トランスクリプト**: PowerShell セッションの "肩越しの" ビューを含むファイルです。</span><span class="sxs-lookup"><span data-stu-id="ad962-172">**PowerShell Transcript**: A file containing an "over-the-shoulder" view of a PowerShell session.</span></span>
<span data-ttu-id="ad962-173">TranscriptDirectory フィールドを使用して、JEA セッションのトランスクリプトを生成するように PowerShell を設定できます。</span><span class="sxs-lookup"><span data-stu-id="ad962-173">You can set PowerShell to generate transcripts for JEA sessions using the TranscriptDirectory field.</span></span>
<span data-ttu-id="ad962-174">トランスクリプトについて詳しくは、[こちらのブログ投稿](https://technet.microsoft.com/en-us/magazine/ff687007.aspx)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ad962-174">For more information on transcripts, check out this [blog post](https://technet.microsoft.com/en-us/magazine/ff687007.aspx).</span></span>

