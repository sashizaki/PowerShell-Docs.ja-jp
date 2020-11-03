---
description: このトピックでは、すべての Windows PowerShell ワークフローコマンドで有効なパラメーターについて説明します。 Windows PowerShell エンジンによってそれらがワークフローに追加されるため、ワークフローでこれらのパラメーターを使用することができ、作成したワークフローで自動的に有効になります。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_workflowcommonparameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WorkflowCommonParameters
ms.openlocfilehash: 386200475c1dab9735921edd60abbde20ee354c4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221856"
---
# <a name="about-workflowcommonparameters"></a><span data-ttu-id="79c33-105">WorkflowCommonParameters について</span><span class="sxs-lookup"><span data-stu-id="79c33-105">About WorkflowCommonParameters</span></span>

## <a name="short-description"></a><span data-ttu-id="79c33-106">概要</span><span class="sxs-lookup"><span data-stu-id="79c33-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="79c33-107">このトピックでは、すべての Windows PowerShell ワークフローコマンドで有効なパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="79c33-107">This topic describes the parameters that are valid on all Windows PowerShell workflow commands.</span></span> <span data-ttu-id="79c33-108">Windows PowerShell エンジンによってそれらがワークフローに追加されるため、ワークフローでこれらのパラメーターを使用することができ、作成したワークフローで自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="79c33-108">Because the Windows PowerShell engine adds them to workflows, you can use these parameters on any workflow and they are automatically enabled on the workflows that you author.</span></span>

## <a name="long-description"></a><span data-ttu-id="79c33-109">詳細説明</span><span class="sxs-lookup"><span data-stu-id="79c33-109">LONG DESCRIPTION</span></span>

<span data-ttu-id="79c33-110">Windows PowerShell ワークフローの共通パラメーターは、すべての Windows PowerShell ワークフローおよびアクティビティで使用できるコマンドレットパラメーターのセットです。</span><span class="sxs-lookup"><span data-stu-id="79c33-110">Windows PowerShell Workflow common parameters are a set of cmdlet parameters that you can use with all Windows PowerShell workflows and activities.</span></span> <span data-ttu-id="79c33-111">これらは、ワークフローの作成者ではなく、Windows PowerShell ワークフローエンジンによって追加され、ワークフローとアクティビティで自動的に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="79c33-111">They are added by the Windows PowerShell Workflow engine, not by the workflow author, and they are automatically available on workflows and activities.</span></span> <span data-ttu-id="79c33-112">ただし、入れ子になった3つのレベルのワークフローは、ワークフロー共通パラメーターを含む共通パラメーターをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="79c33-112">However, workflows that are nested three levels deep do not support any common parameters, including workflow common parameters.</span></span>

<span data-ttu-id="79c33-113">すべてのワークフローパラメーターは省略可能であり、(位置指定ではありません) という名前です。</span><span class="sxs-lookup"><span data-stu-id="79c33-113">All workflow parameters are optional and named (not positional).</span></span> <span data-ttu-id="79c33-114">パイプラインからの入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="79c33-114">They do not take input from the pipeline.</span></span>

<span data-ttu-id="79c33-115">ほとんどのワークフロー共通パラメーターには、やなどの PS プレフィックスがあり `PSComputerName` `PSCredential` ます。</span><span class="sxs-lookup"><span data-stu-id="79c33-115">Most of the workflow common parameters have a PS prefix, such as `PSComputerName` and `PSCredential`.</span></span> <span data-ttu-id="79c33-116">PS プレフィックス付きパラメーターは、ターゲットコンピューターの接続と実行環境を構成します。 "リモートノード" とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="79c33-116">The PS-prefixed parameters configure the connection and the execution environment for the target computers, also known as "remote nodes."</span></span>

<span data-ttu-id="79c33-117">やなどのワークフロー共通パラメーターの多くには、 `PSAllowRedirection` `AsJob` Windows PowerShell リモート処理およびバックグラウンドジョブで使用されるパラメーターに似た名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="79c33-117">Many of the workflow common parameters, such as `PSAllowRedirection` and `AsJob`, have names that are similar to parameters used in Windows PowerShell remoting and background jobs.</span></span> <span data-ttu-id="79c33-118">これらのパラメーターは、同様に名前が付けられたリモート処理およびジョブパラメーターと同じように動作するため、リモート処理およびジョブで作成したナレッジを使用してワークフローを管理できます。</span><span class="sxs-lookup"><span data-stu-id="79c33-118">These parameters work in the same way as the similarly-named remoting and job parameters, so you can use the knowledge that you developed in remoting and jobs to manage workflows.</span></span>

<span data-ttu-id="79c33-119">ワークフローは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="79c33-119">Workflows are introduced in Windows PowerShell 3.0.</span></span>

### <a name="parameter-descriptions"></a><span data-ttu-id="79c33-120">パラメーターの説明</span><span class="sxs-lookup"><span data-stu-id="79c33-120">PARAMETER DESCRIPTIONS</span></span>

<span data-ttu-id="79c33-121">ここでは、ワークフロー共通パラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="79c33-121">This section describes the workflow common parameters.</span></span>

#### <a name="-asjob-switchparameter"></a><span data-ttu-id="79c33-122">-AsJob \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="79c33-122">-AsJob \<SwitchParameter\></span></span>

<span data-ttu-id="79c33-123">ワークフローをワークフロージョブとして実行します。</span><span class="sxs-lookup"><span data-stu-id="79c33-123">Runs the workflow as a workflow job.</span></span> <span data-ttu-id="79c33-124">Workflow コマンドを実行すると、親ジョブを表すオブジェクトが直ちに返されます。</span><span class="sxs-lookup"><span data-stu-id="79c33-124">The workflow command immediately returns an object that represents a parent job.</span></span> <span data-ttu-id="79c33-125">親ジョブには、各ターゲットコンピューターで実行されている子ジョブが含まれます。</span><span class="sxs-lookup"><span data-stu-id="79c33-125">The parent job contains the child jobs that are running on each of the target computers.</span></span> <span data-ttu-id="79c33-126">ジョブを管理するには、Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="79c33-126">To manage the job, use the Job cmdlets.</span></span> <span data-ttu-id="79c33-127">ジョブの結果を取得するには、[Receive-Job](xref:Microsoft.PowerShell.Core.Receive-Job) を使用します。</span><span class="sxs-lookup"><span data-stu-id="79c33-127">To get the job results, use [Receive-Job](xref:Microsoft.PowerShell.Core.Receive-Job).</span></span>

#### <a name="-jobname-string"></a><span data-ttu-id="79c33-128">-JobName \<String\></span><span class="sxs-lookup"><span data-stu-id="79c33-128">-JobName \<String\></span></span>

<span data-ttu-id="79c33-129">ワークフロージョブのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-129">Specifies a friendly name for the workflow job.</span></span> <span data-ttu-id="79c33-130">既定では、ジョブは "Job\<n\>" と名付けられます。ここで、\<n\> は、順序を示す番号です。</span><span class="sxs-lookup"><span data-stu-id="79c33-130">By default, jobs are named "Job\<n\>", where \<n\> is an ordinal number.</span></span>

<span data-ttu-id="79c33-131">ワークフローコマンドで JobName パラメーターを使用すると、ワークフローはジョブとして実行され、コマンドにパラメーターを含めない場合でも、ワークフローコマンドはジョブオブジェクトを返します `AsJob` 。</span><span class="sxs-lookup"><span data-stu-id="79c33-131">If you use the JobName parameter in a workflow command, the workflow is run as a job and the workflow command returns a job object, even if you do not include the `AsJob` parameter in the command.</span></span>

<span data-ttu-id="79c33-132">Windows PowerShell のバックグラウンド ジョブの詳細については、「[about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79c33-132">For more information about Windows PowerShell background jobs, see [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

#### <a name="-psallowredirection-switchparameter"></a><span data-ttu-id="79c33-133">-PSAllowRedirection \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="79c33-133">-PSAllowRedirection \<SwitchParameter\></span></span>

<span data-ttu-id="79c33-134">ターゲットコンピューターへの接続のリダイレクトを許可します。</span><span class="sxs-lookup"><span data-stu-id="79c33-134">Allows redirection of the connection to the target computers.</span></span>

<span data-ttu-id="79c33-135">パラメーターを使用すると `PSConnectionURI` 、リモートの送信先は別の URI にリダイレクトする命令を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="79c33-135">When you use the `PSConnectionURI` parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="79c33-136">既定では、Windows PowerShell は接続をリダイレクトしませんが、パラメーターを使用して、 `PSAllowRedirection` ターゲットコンピューターへの接続のリダイレクトを許可することができます。</span><span class="sxs-lookup"><span data-stu-id="79c33-136">By default, Windows PowerShell does not redirect connections, but you can use the `PSAllowRedirection` parameter to allow redirection of the connection to the target computer.</span></span>

<span data-ttu-id="79c33-137">`MaximumConnectionRedirectionCount`また、ユーザー設定変数のプロパティ、 `$PSSessionOption` または `MaximumConnectionRedirectionCount` の値のプロパティを設定することによって、接続をリダイレクトする回数を制限することもできます `PSSessionOption parameter` 。</span><span class="sxs-lookup"><span data-stu-id="79c33-137">You can also limit the number of times that the connection is redirected by setting the `MaximumConnectionRedirectionCount` property of the `$PSSessionOption` preference variable, or the `MaximumConnectionRedirectionCount` property of the value of the `PSSessionOption parameter`.</span></span> <span data-ttu-id="79c33-138">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="79c33-138">The default value is 5.</span></span> <span data-ttu-id="79c33-139">詳細については、 `PSSessionOption` パラメーターと [新しい-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)の説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79c33-139">For more information, see the description of the `PSSessionOption` parameter and [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

#### <a name="-psapplicationname-string"></a><span data-ttu-id="79c33-140">-PSApplicationName \<String\></span><span class="sxs-lookup"><span data-stu-id="79c33-140">-PSApplicationName \<String\></span></span>

<span data-ttu-id="79c33-141">ターゲットコンピューターへの接続に使用される接続 URI のアプリケーション名セグメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-141">Specifies the application name segment of the connection URI that is used to connect to the target computers.</span></span> <span data-ttu-id="79c33-142">コマンドでパラメーターを使用しない場合は、このパラメーターを使用してアプリケーション名を指定し `ConnectionURI` ます。</span><span class="sxs-lookup"><span data-stu-id="79c33-142">Use this parameter to specify the application name when you are not using the `ConnectionURI` parameter in the command.</span></span>

<span data-ttu-id="79c33-143">既定値は、 `$PSSessionApplicationName` ローカルコンピューター上のユーザー設定変数の値です。</span><span class="sxs-lookup"><span data-stu-id="79c33-143">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="79c33-144">このユーザー設定変数が定義されていない場合、既定値は WSMAN です。</span><span class="sxs-lookup"><span data-stu-id="79c33-144">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="79c33-145">この値はほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="79c33-145">This value is appropriate for most uses.</span></span> <span data-ttu-id="79c33-146">詳細については、「 [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79c33-146">For more information, see [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="79c33-147">WinRM サービスは、アプリケーション名を使用して、接続要求を処理するリスナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="79c33-147">The WinRM service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="79c33-148">このパラメーターの値は、 `URLPrefix` リモートコンピューター上のリスナーのプロパティの値と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="79c33-148">The value of this parameter should match the value of the `URLPrefix` property of a listener on the remote computer.</span></span>

#### <a name="-psauthentication-authenticationmechanism"></a><span data-ttu-id="79c33-149">-PSAuthentication \<AuthenticationMechanism\></span><span class="sxs-lookup"><span data-stu-id="79c33-149">-PSAuthentication \<AuthenticationMechanism\></span></span>

<span data-ttu-id="79c33-150">対象のコンピュータに接続するときに、ユーザーの資格情報を認証するために使用されるメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-150">Specifies the mechanism that is used to authenticate the user's credentials when connecting to the target computers.</span></span>

<span data-ttu-id="79c33-151">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="79c33-151">Valid values are:</span></span>

- <span data-ttu-id="79c33-152">**[Default]**</span><span class="sxs-lookup"><span data-stu-id="79c33-152">**Default**</span></span>
- <span data-ttu-id="79c33-153">**Basic**</span><span class="sxs-lookup"><span data-stu-id="79c33-153">**Basic**</span></span>
- <span data-ttu-id="79c33-154">**Credssp**</span><span class="sxs-lookup"><span data-stu-id="79c33-154">**Credssp**</span></span>
- <span data-ttu-id="79c33-155">**ダイジェスト**</span><span class="sxs-lookup"><span data-stu-id="79c33-155">**Digest**</span></span>
- <span data-ttu-id="79c33-156">**Kerberos**</span><span class="sxs-lookup"><span data-stu-id="79c33-156">**Kerberos**</span></span>
- <span data-ttu-id="79c33-157">**ネゴシエーション**</span><span class="sxs-lookup"><span data-stu-id="79c33-157">**Negotiate**</span></span>
- <span data-ttu-id="79c33-158">**NegotiateWithImplicitCredential**</span><span class="sxs-lookup"><span data-stu-id="79c33-158">**NegotiateWithImplicitCredential**</span></span>

<span data-ttu-id="79c33-159">既定値は **Default** です。</span><span class="sxs-lookup"><span data-stu-id="79c33-159">The default value is **Default**.</span></span>

<span data-ttu-id="79c33-160">このパラメーターの値の詳細については、MSDN の列挙の説明を参照してください `System.Management.Automation.Runspaces.AuthenticationMechanism` 。</span><span class="sxs-lookup"><span data-stu-id="79c33-160">For information about the values of this parameter, see the description of the `System.Management.Automation.Runspaces.AuthenticationMechanism` enumeration in MSDN.</span></span>

> [!WARNING]
> <span data-ttu-id="79c33-161">ユーザーの資格情報が認証対象のリモート コンピューターに渡される Credential Security Service Provider (CredSSP) 認証は、リモート ネットワーク共有にアクセスする場合など、複数のリソースの認証を必要とするコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="79c33-161">Credential Security Service Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="79c33-162">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="79c33-162">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="79c33-163">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="79c33-163">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

#### <a name="-psauthenticationlevel-authenticationlevel"></a><span data-ttu-id="79c33-164">-PSAuthenticationLevel \<AuthenticationLevel\></span><span class="sxs-lookup"><span data-stu-id="79c33-164">-PSAuthenticationLevel \<AuthenticationLevel\></span></span>

<span data-ttu-id="79c33-165">対象のコンピュータへの接続の認証レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-165">Specifies the authentication level for the connections to the target computers.</span></span>
<span data-ttu-id="79c33-166">既定値は **Default** です。</span><span class="sxs-lookup"><span data-stu-id="79c33-166">The default value is **Default**.</span></span>

<span data-ttu-id="79c33-167">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="79c33-167">Valid values are:</span></span>

|<span data-ttu-id="79c33-168">名前</span><span class="sxs-lookup"><span data-stu-id="79c33-168">Name</span></span> |<span data-ttu-id="79c33-169">説明</span><span class="sxs-lookup"><span data-stu-id="79c33-169">Description</span></span> |
|---------|---------|
|<span data-ttu-id="79c33-170">**Unchanged**</span><span class="sxs-lookup"><span data-stu-id="79c33-170">**Unchanged**</span></span> | <span data-ttu-id="79c33-171">認証レベルは前のコマンドと同じです。</span><span class="sxs-lookup"><span data-stu-id="79c33-171">The authentication level is the same as the previous command.</span></span> |
|<span data-ttu-id="79c33-172">**[Default]**</span><span class="sxs-lookup"><span data-stu-id="79c33-172">**Default**</span></span> | <span data-ttu-id="79c33-173">[Windows 認証]。</span><span class="sxs-lookup"><span data-stu-id="79c33-173">Windows Authentication.</span></span> |
|<span data-ttu-id="79c33-174">**なし**</span><span class="sxs-lookup"><span data-stu-id="79c33-174">**None**</span></span> | <span data-ttu-id="79c33-175">COM 認証なし。</span><span class="sxs-lookup"><span data-stu-id="79c33-175">No COM authentication.</span></span>   |
|<span data-ttu-id="79c33-176">**のインスタンスに接続するときには、**</span><span class="sxs-lookup"><span data-stu-id="79c33-176">**Connect**</span></span> | <span data-ttu-id="79c33-177">接続レベルの COM 認証。</span><span class="sxs-lookup"><span data-stu-id="79c33-177">Connect-level COM authentication.</span></span>|
|<span data-ttu-id="79c33-178">**Call**</span><span class="sxs-lookup"><span data-stu-id="79c33-178">**Call**</span></span> | <span data-ttu-id="79c33-179">呼び出しレベルの COM 認証。</span><span class="sxs-lookup"><span data-stu-id="79c33-179">Call-level COM authentication.</span></span>   |
|<span data-ttu-id="79c33-180">**パック**</span><span class="sxs-lookup"><span data-stu-id="79c33-180">**Packet**</span></span> | <span data-ttu-id="79c33-181">パケット レベルの COM 認証。</span><span class="sxs-lookup"><span data-stu-id="79c33-181">Packet-level COM authentication.</span></span>|
|<span data-ttu-id="79c33-182">**PacketIntegrity**</span><span class="sxs-lookup"><span data-stu-id="79c33-182">**PacketIntegrity**</span></span> | <span data-ttu-id="79c33-183">パケット整合性レベルの COM 認証。</span><span class="sxs-lookup"><span data-stu-id="79c33-183">Packet Integrity-level COM authentication.</span></span>  |
|<span data-ttu-id="79c33-184">**PacketPrivacy**</span><span class="sxs-lookup"><span data-stu-id="79c33-184">**PacketPrivacy**</span></span> | <span data-ttu-id="79c33-185">パケット プライバシ レベルの COM 認証。</span><span class="sxs-lookup"><span data-stu-id="79c33-185">Packet Privacy-level COM authentication.</span></span> |

#### <a name="-pscertificatethumbprint-string"></a><span data-ttu-id="79c33-186">-PSCertificateThumbprint \<String\></span><span class="sxs-lookup"><span data-stu-id="79c33-186">-PSCertificateThumbprint \<String\></span></span>

<span data-ttu-id="79c33-187">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-187">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="79c33-188">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="79c33-188">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="79c33-189">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="79c33-189">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="79c33-190">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="79c33-190">They can only be mapped to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="79c33-191">証明書を取得するには、 [Get Item](xref:Microsoft.PowerShell.Management.Get-Item) または [get-childitem] (../../Microsoft.PowerShell.Management/Get-Childitem.md) Windows PowerShell Cert: ドライブのコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="79c33-191">To get a certificate, use the [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) or [Get-ChildItem] (../../Microsoft.PowerShell.Management/Get-Childitem.md) cmdlets in the Windows PowerShell Cert: drive.</span></span>

#### <a name="-pscomputername-string"></a><span data-ttu-id="79c33-192">-PSComputerName \<String[]\></span><span class="sxs-lookup"><span data-stu-id="79c33-192">-PSComputerName \<String[]\></span></span>

<span data-ttu-id="79c33-193">ワークフローのターゲットノードであるコンピューターの一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-193">Specifies the list of computers that are the target nodes of the workflow.</span></span>
<span data-ttu-id="79c33-194">ワークフロー内のコマンドまたはアクティビティは、このパラメーターを使用して指定されたコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="79c33-194">Commands or activities in a workflow are run on the computers that are specified by using this parameter.</span></span> <span data-ttu-id="79c33-195">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="79c33-195">The default is the local computer.</span></span>

<span data-ttu-id="79c33-196">1 台または複数のコンピューターの NETBIOS 名、IP アドレス、または完全修飾ドメイン名をコンマ区切りリストで入力します。</span><span class="sxs-lookup"><span data-stu-id="79c33-196">Type the NETBIOS name, IP address, or fully-qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="79c33-197">ローカルのコンピューターを指定するには、コンピューター名、「localhost」、またはドット (.) を入力します。</span><span class="sxs-lookup"><span data-stu-id="79c33-197">To specify the local computer, type the computer name, "localhost", or a dot (.).</span></span>

<span data-ttu-id="79c33-198">パラメーターの値にローカルコンピューターを含めるには `PSComputerName` 、[管理者として実行] オプションを使用して Windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="79c33-198">To include the local computer in the value of the `PSComputerName` parameter, open Windows PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="79c33-199">コマンドでこのパラメーターを省略した場合、またはその値が `$null` または空の文字列の場合、ワークフローターゲットはローカルコンピューターであり、Windows PowerShell リモート処理はコマンドの実行には使用されません。</span><span class="sxs-lookup"><span data-stu-id="79c33-199">If this parameter is omitted from the command, or it value is `$null` or an empty string, the workflow target is the local computer and Windows PowerShell remoting is not used to run the command.</span></span>

<span data-ttu-id="79c33-200">パラメーターの値に IP アドレスを使用するには、 `ComputerName` コマンドにパラメーターを含める必要があり `PSCredential` ます。</span><span class="sxs-lookup"><span data-stu-id="79c33-200">To use an IP address in the value of the `ComputerName` parameter, the command must include the `PSCredential` parameter.</span></span> <span data-ttu-id="79c33-201">また、HTTPS トランスポート用にコンピューターを構成するか、リモート コンピューターの IP アドレスをローカル コンピューター上の WinRM TrustedHosts 一覧に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="79c33-201">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="79c33-202">TrustedHosts の一覧にコンピューター名を追加する手順については、 [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md)の「 *信頼されたホストの一覧にコンピューターを追加する方法」* を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79c33-202">For instructions for adding a computer name to the TrustedHosts list, see *"How to Add a Computer to the Trusted Host List"* in [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span></span>

#### <a name="-psconfigurationname-string"></a><span data-ttu-id="79c33-203">-PSConfigurationName \<String\></span><span class="sxs-lookup"><span data-stu-id="79c33-203">-PSConfigurationName \<String\></span></span>

<span data-ttu-id="79c33-204">対象のコンピューターでセッションを構成するために使用されるセッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-204">Specifies the session configurations that are used to configure sessions on the target computers.</span></span> <span data-ttu-id="79c33-205">(ワークフローサーバーコンピューターではなく) ターゲットコンピューターにセッション構成を入力します。</span><span class="sxs-lookup"><span data-stu-id="79c33-205">Enter a session configuration on the target computers (not the workflow server computer).</span></span> <span data-ttu-id="79c33-206">既定値は、`Microsoft.PowerShell.Workflow` です。</span><span class="sxs-lookup"><span data-stu-id="79c33-206">The default is `Microsoft.PowerShell.Workflow`.</span></span>

#### <a name="-psconnectionretrycount-uint"></a><span data-ttu-id="79c33-207">-PSConnectionRetryCount \<UInt\></span><span class="sxs-lookup"><span data-stu-id="79c33-207">-PSConnectionRetryCount \<UInt\></span></span>

<span data-ttu-id="79c33-208">最初の接続試行が失敗した場合に、各ターゲットコンピュータへの接続試行回数の最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-208">Specifies the maximum number of attempts to connect to each target computer if the first connection attempt fails.</span></span> <span data-ttu-id="79c33-209">1から 4294967295 (UInt) までの数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="79c33-209">Enter a number between 1 and 4,294,967,295 (UInt.MaxValue).</span></span> <span data-ttu-id="79c33-210">既定値のゼロ (0) は、再試行の回数を表します。</span><span class="sxs-lookup"><span data-stu-id="79c33-210">The default value, zero (0), represents no retry attempts.</span></span>

#### <a name="-psconnectionretryintervalsec-uint"></a><span data-ttu-id="79c33-211">-PSConnectionRetryIntervalSec \<UInt\></span><span class="sxs-lookup"><span data-stu-id="79c33-211">-PSConnectionRetryIntervalSec \<UInt\></span></span>

<span data-ttu-id="79c33-212">接続再試行の間隔を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-212">Specifies the delay between connection retry attempts in seconds.</span></span> <span data-ttu-id="79c33-213">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="79c33-213">The default value is zero (0).</span></span> <span data-ttu-id="79c33-214">このパラメーターは、PSConnectionRetryCount の値が1以上の場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="79c33-214">This parameter is valid only when the value of PSConnectionRetryCount is at least 1.</span></span>

#### <a name="-psconnectionuri-systemuri"></a><span data-ttu-id="79c33-215">-PSConnectionURI \<System.Uri\></span><span class="sxs-lookup"><span data-stu-id="79c33-215">-PSConnectionURI \<System.Uri\></span></span>

<span data-ttu-id="79c33-216">ターゲットコンピューター上のワークフローの接続エンドポイントを定義する Uniform Resource Identifier (URI) を指定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-216">Specifies a Uniform Resource Identifier (URI) that defines the connection endpoint for the workflow on the target computer.</span></span> <span data-ttu-id="79c33-217">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79c33-217">The URI must be fully qualified.</span></span>

<span data-ttu-id="79c33-218">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="79c33-218">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="79c33-219">既定値は `http://localhost:5985/WSMAN` です。</span><span class="sxs-lookup"><span data-stu-id="79c33-219">The default value is `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="79c33-220">を指定しない場合は、、、、およびの各パラメーターを使用して `PSConnectionURI` 値を `PSUseSSL` 指定でき `PSComputerName` `PSPort` `PSApplicationName` `PSConnectionURI` ます。</span><span class="sxs-lookup"><span data-stu-id="79c33-220">If you do not specify a `PSConnectionURI`, you can use the `PSUseSSL`, `PSComputerName`, `PSPort`, and `PSApplicationName` parameters to specify the `PSConnectionURI` values.</span></span>

<span data-ttu-id="79c33-221">URI のトランスポートセグメントの有効な値は、 **HTTP** と **HTTPS** です。</span><span class="sxs-lookup"><span data-stu-id="79c33-221">Valid values for the Transport segment of the URI are **HTTP** and **HTTPS**.</span></span>
<span data-ttu-id="79c33-222">トランスポートセグメントを使用して接続 URI を指定し、ポートを指定しない場合、セッションは標準ポート80で HTTP 用および 443 (HTTPS 用) で作成されます。</span><span class="sxs-lookup"><span data-stu-id="79c33-222">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="79c33-223">Windows PowerShell リモート処理用の既定のポートを使用するには、HTTP の場合は 5985、HTTPS の場合は 5986 を指定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-223">To use the default ports for Windows PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

#### <a name="-pscredential-pscredential"></a><span data-ttu-id="79c33-224">-PSCredential \<PSCredential\></span><span class="sxs-lookup"><span data-stu-id="79c33-224">-PSCredential \<PSCredential\></span></span>

<span data-ttu-id="79c33-225">対象のコンピューターでワークフローを実行する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-225">Specifies a user account that has permission to run a workflow on the target computer.</span></span> <span data-ttu-id="79c33-226">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="79c33-226">The default is the current user.</span></span> <span data-ttu-id="79c33-227">このパラメーターは、PSComputerName パラメーターがコマンドに含まれている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="79c33-227">This parameter is valid only when the PSComputerName parameter is included in the command.</span></span>

<span data-ttu-id="79c33-228">"User01" や "Domain01\user01」" などのユーザー名を入力するか、 `PSCredential` コマンドレットから返されるオブジェクトなどのオブジェクトを含む変数を入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="79c33-228">Type a user name, such as "User01" or "Domain01\User01", or enter a variable that contains a `PSCredential` object, such as one that the `Get-Credential` cmdlet returns.</span></span> <span data-ttu-id="79c33-229">ユーザー名のみを入力すると、パスワードの入力を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79c33-229">If you enter only a user name, you will be prompted for a password.</span></span>

#### <a name="-pselapsedtimeoutsec-uint32"></a><span data-ttu-id="79c33-230">-PSElapsedTimeoutSec \<UInt32\></span><span class="sxs-lookup"><span data-stu-id="79c33-230">-PSElapsedTimeoutSec \<UInt32\></span></span>

<span data-ttu-id="79c33-231">ワークフローと関連するすべてのリソースがシステムで保持される期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-231">Determines how long the workflow and all related resources are maintained in the system.</span></span> <span data-ttu-id="79c33-232">タイムアウトが経過すると、ワークフローはまだ処理中であっても、削除されます。</span><span class="sxs-lookup"><span data-stu-id="79c33-232">When the timeout expires, the workflow is deleted, even if it is still processing.</span></span> <span data-ttu-id="79c33-233">10 ~ 4294967295 の値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="79c33-233">Enter a value between 10 and 4,294,967,295.</span></span> <span data-ttu-id="79c33-234">既定値の 0 (ゼロ) は、経過タイムアウトがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="79c33-234">The default value, 0 (zero), means that there is no elapsed timeout.</span></span>

#### <a name="-psparametercollection-hashtable"></a><span data-ttu-id="79c33-235">-PSParameterCollection \<Hashtable[]\></span><span class="sxs-lookup"><span data-stu-id="79c33-235">-PSParameterCollection \<Hashtable[]\></span></span>

<span data-ttu-id="79c33-236">異なるターゲットコンピューターに対して、異なるワークフロー共通パラメーター値を指定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-236">Specifies different workflow common parameter values for different target computers.</span></span>

<span data-ttu-id="79c33-237">ターゲットコンピューターごとに1つのハッシュテーブルを含むハッシュテーブルのコンマ区切りの一覧を入力します。</span><span class="sxs-lookup"><span data-stu-id="79c33-237">Enter a comma-separated list of hash tables with one hash table for each target computer.</span></span> <span data-ttu-id="79c33-238">各ハッシュテーブルでは、最初のキーはで、 `PSComputerName` その値はターゲットコンピューターの名前です。</span><span class="sxs-lookup"><span data-stu-id="79c33-238">In each hash table, the first key is `PSComputerName` and its value is the name of the target computer.</span></span> <span data-ttu-id="79c33-239">コンピューター名にはワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="79c33-239">Wildcard characters are permitted in the computer name.</span></span> <span data-ttu-id="79c33-240">ハッシュテーブル内の残りのキーについては、キーがパラメーター名で、値がパラメーター値になります。</span><span class="sxs-lookup"><span data-stu-id="79c33-240">For the remaining keys in the hash table, the key is the parameter name and the value is the parameter value.</span></span>

<span data-ttu-id="79c33-241">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="79c33-241">For example:</span></span>

```powershell
-PSParameterCollection @{PSComputerName="*"; PSElapsedTimeoutSec=20},
@{PSComputerName="Server02"},
@{PSComputerName="Server03"},
@{PSComputerName="Server01"; PSElapsedTimeoutSec=10}
```

<span data-ttu-id="79c33-242">上の例では、すべての接続に既定の PSElapsedTimeoutSec 20 秒が設定されています。ただし、Server01 では、独自のタイムアウトを10秒に指定することで既定値を上書きします。</span><span class="sxs-lookup"><span data-stu-id="79c33-242">In the above example, all connections will have a default PSElapsedTimeoutSec of 20 seconds, except for Server01 which overrides the default value by specifying its own timeout of 10 seconds.</span></span>

#### <a name="-pspersist-boolean"></a><span data-ttu-id="79c33-243">-PSPersist \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="79c33-243">-PSPersist \<Boolean\></span></span>

<span data-ttu-id="79c33-244">ワークフローで指定されているチェックポイントに加えて、ワークフローにチェックポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="79c33-244">Adds checkpoints to the workflow, in addition to any checkpoints that are specified in the workflow.</span></span>

<span data-ttu-id="79c33-245">このパラメーターでは、 `PSPersist` アクティビティ共通パラメーター、 `Checkpoint-Workflow` アクティビティ、または変数を使用して指定されたチェックポイントなど、ワークフローのチェックポイントを抑制することはできません `$PSPersistPreference` 。</span><span class="sxs-lookup"><span data-stu-id="79c33-245">This parameter cannot suppress the checkpoints in a workflow, such as those specified by using the `PSPersist` activity common parameter, the `Checkpoint-Workflow` activity, or the `$PSPersistPreference` variable.</span></span>

<span data-ttu-id="79c33-246">"チェックポイント" または "永続化ポイント" は、ワークフローの実行中にキャプチャされ、ディスクまたは SQL データベースの永続ストアに保存される、ワークフローの状態とデータのスナップショットです。</span><span class="sxs-lookup"><span data-stu-id="79c33-246">A "checkpoint" or "persistence point" is a snapshot of the workflow state and data that is captured while the workflow runs and is saved to a persistence store on disk or in a SQL database.</span></span> <span data-ttu-id="79c33-247">Windows PowerShell ワークフローでは、保存されたデータを使用して、ワークフローを再開するのではなく、最後の永続化ポイントから中断または中断されたワークフローを再開します。</span><span class="sxs-lookup"><span data-stu-id="79c33-247">Windows PowerShell Workflow uses the saved data to resume a suspended or interrupted workflow from the last persistence point, rather than to restart the workflow.</span></span>

<span data-ttu-id="79c33-248">有効な値:</span><span class="sxs-lookup"><span data-stu-id="79c33-248">Valid values:</span></span>

- <span data-ttu-id="79c33-249">( *既定値* )このパラメーターを省略すると、ワークフローで指定されているチェックポイントだけでなく、ワークフローの先頭と末尾にチェックポイントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="79c33-249">( *Default* ) If you omit this parameter, a checkpoint is added to the beginning and end of the workflow, in addition to any checkpoints that are specified in the workflow.</span></span>

- <span data-ttu-id="79c33-250">`$True`.</span><span class="sxs-lookup"><span data-stu-id="79c33-250">`$True`.</span></span> <span data-ttu-id="79c33-251">ワークフローで指定されているチェックポイントだけでなく、ワークフローの開始時と終了時、および各アクティビティの後のチェックポイントにチェックポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="79c33-251">Adds a checkpoint to the beginning and end of the workflow and a checkpoint after each activity, in addition to any checkpoints that are specified in the workflow.</span></span>

- <span data-ttu-id="79c33-252">`$False`.</span><span class="sxs-lookup"><span data-stu-id="79c33-252">`$False`.</span></span> <span data-ttu-id="79c33-253">チェックポイントは追加されません。</span><span class="sxs-lookup"><span data-stu-id="79c33-253">No checkpoints are added.</span></span> <span data-ttu-id="79c33-254">チェックポイントは、ワークフローで指定されている場合にのみ取得されます。</span><span class="sxs-lookup"><span data-stu-id="79c33-254">Checkpoints are taken only when specified in the workflow.</span></span>

#### <a name="-psport-int32"></a><span data-ttu-id="79c33-255">-PSPort \<Int32\></span><span class="sxs-lookup"><span data-stu-id="79c33-255">-PSPort \<Int32\></span></span>

<span data-ttu-id="79c33-256">ターゲットコンピューターのネットワークポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-256">Specifies the network port on the target computers.</span></span> <span data-ttu-id="79c33-257">既定のポート番号は 5985 (HTTP 用の WinRM ポート) と 5986 (HTTPS 用の WinRM ポート) です。</span><span class="sxs-lookup"><span data-stu-id="79c33-257">The default ports are 5985 (the WinRM port for HTTP) and 5986 (the WinRM port for HTTPS).</span></span>

<span data-ttu-id="79c33-258">必要な場合を除き、PSPort パラメーターは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="79c33-258">Do not use the PSPort parameter unless you must.</span></span> <span data-ttu-id="79c33-259">コマンドで設定されたポートは、コマンドを実行するすべてのコンピューターまたはセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="79c33-259">The port set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="79c33-260">代替ポートの設定によっては、コマンドがすべてのコンピューターで実行されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="79c33-260">An alternate port setting might prevent the command from running on all computers.</span></span> <span data-ttu-id="79c33-261">代替ポートを使用する前に、そのポートでリッスンするようにリモート コンピューター上の WinRM リスナーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79c33-261">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span>

#### <a name="-psprivatemetadata-hashtable"></a><span data-ttu-id="79c33-262">-PSPrivateMetadata \<Hashtable\></span><span class="sxs-lookup"><span data-stu-id="79c33-262">-PSPrivateMetadata \<Hashtable\></span></span>

<span data-ttu-id="79c33-263">ワークフロージョブにカスタマイズされた情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="79c33-263">Provides customized information to workflow jobs.</span></span> <span data-ttu-id="79c33-264">ハッシュテーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="79c33-264">Enter a hash table.</span></span> <span data-ttu-id="79c33-265">これらのキーと値は、ワークフローごとにカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="79c33-265">The keys and values are customized for each workflow.</span></span> <span data-ttu-id="79c33-266">ワークフローのプライベートメタデータの詳細については、ワークフローのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79c33-266">For information about the private metadata of a workflow, see the help topic for the workflow.</span></span>

<span data-ttu-id="79c33-267">このパラメーターは、Windows PowerShell ワークフローエンジンによって処理されません。</span><span class="sxs-lookup"><span data-stu-id="79c33-267">This parameter is not processed by the Windows PowerShell Workflow engine.</span></span>
<span data-ttu-id="79c33-268">代わりに、エンジンがハッシュテーブルをワークフローに直接渡します。</span><span class="sxs-lookup"><span data-stu-id="79c33-268">Instead, the engine passes the hash table directly to the workflow.</span></span>

#### <a name="-psrunningtimeoutsec-uint32"></a><span data-ttu-id="79c33-269">-PSRunningTimeoutSec \<UInt32\></span><span class="sxs-lookup"><span data-stu-id="79c33-269">-PSRunningTimeoutSec \<UInt32\></span></span>

<span data-ttu-id="79c33-270">ワークフローが中断された時間を除く、ワークフローの実行時間を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-270">Specifies the running time of the workflow in seconds, excluding any time that the workflow is suspended.</span></span> <span data-ttu-id="79c33-271">時間が経過してもワークフローの実行が完了しない場合、Windows PowerShell ワークフローエンジンはワークフローの実行を強制的に停止します。</span><span class="sxs-lookup"><span data-stu-id="79c33-271">If workflow execution is not complete when the time expires, the Windows PowerShell Workflow engine forcibly stops the execution of the workflow.</span></span>

#### <a name="-pssessionoption-pssessionoption"></a><span data-ttu-id="79c33-272">-PSSessionOption \<PSSessionOption\></span><span class="sxs-lookup"><span data-stu-id="79c33-272">-PSSessionOption \<PSSessionOption\></span></span>

<span data-ttu-id="79c33-273">セッションの詳細オプションを対象のコンピューターに設定します。</span><span class="sxs-lookup"><span data-stu-id="79c33-273">Sets advanced options for the sessions to the target computers.</span></span> <span data-ttu-id="79c33-274">コマンドレットを使用して作成したオブジェクトなどのオブジェクトを入力し `PSSessionOption` `New-PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="79c33-274">Enter a `PSSessionOption` object, such as one that you create by using the `New-PSSessionOption` cmdlet.</span></span>

<span data-ttu-id="79c33-275">セッションオプションの既定値は、設定されている場合は、ユーザー設定変数の値によって決まり `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="79c33-275">The default values for the session options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="79c33-276">それ以外の場合は、セッション構成で指定された値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="79c33-276">Otherwise, the session uses the values specified in the session configuration.</span></span>

<span data-ttu-id="79c33-277">既定値を含むセッションオプションの説明については、コマンドレットのヘルプトピック `New-PSSessionOption` (../../Microsoft.PowerShell.Core/New-PSSessionOption.md).</span><span class="sxs-lookup"><span data-stu-id="79c33-277">For a description of the session options, including the default values, see the help topic for the `New-PSSessionOption` cmdlet (../../Microsoft.PowerShell.Core/New-PSSessionOption.md).</span></span> <span data-ttu-id="79c33-278">ユーザー設定変数の詳細については `$PSSessionOption` 、「 [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79c33-278">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

#### <a name="-psusessl-switchparameter"></a><span data-ttu-id="79c33-279">-PSUseSSL \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="79c33-279">-PSUseSSL \<SwitchParameter\></span></span>

<span data-ttu-id="79c33-280">は、Secure Sockets Layer (SSL) プロトコルを使用して、対象のコンピューターへの接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="79c33-280">Uses the Secure Sockets Layer (SSL) protocol to establish a connection to the target computer.</span></span> <span data-ttu-id="79c33-281">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="79c33-281">By default, SSL is not used.</span></span>

<span data-ttu-id="79c33-282">WS-Management は、ネットワークを介して転送されるすべての Windows PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="79c33-282">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span> <span data-ttu-id="79c33-283">UseSSL は、HTTP 経由ではなく HTTPS 経由でデータを送信するために追加された保護機能です。</span><span class="sxs-lookup"><span data-stu-id="79c33-283">UseSSL is an additional protection that sends the data across an HTTPS, instead of HTTP.</span></span> <span data-ttu-id="79c33-284">コマンドに使用するポートで SSL が使用できない場合に、このパラメーターを指定すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="79c33-284">If you use this parameter, but SSL is not available on the port used for the command, the command fails.</span></span>

## <a name="see-also"></a><span data-ttu-id="79c33-285">関連項目</span><span class="sxs-lookup"><span data-stu-id="79c33-285">SEE ALSO</span></span>

- [<span data-ttu-id="79c33-286">about_ActivityCommonParameters</span><span class="sxs-lookup"><span data-stu-id="79c33-286">about_ActivityCommonParameters</span></span>](about_ActivityCommonParameters.md)
- [<span data-ttu-id="79c33-287">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="79c33-287">about_Workflows</span></span>](about_Workflows.md)
- [<span data-ttu-id="79c33-288">Invoke-AsWorkflow</span><span class="sxs-lookup"><span data-stu-id="79c33-288">Invoke-AsWorkflow</span></span>](xref:PSWorkflowUtility.Invoke-AsWorkflow)
- [<span data-ttu-id="79c33-289">New-PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="79c33-289">New-PSWorkflowExecutionOption</span></span>](xref:PSWorkflow.New-PSWorkflowExecutionOption)
- [<span data-ttu-id="79c33-290">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="79c33-290">New-PSWorkflowSession</span></span>](xref:PSWorkflow.New-PSWorkflowSession)
