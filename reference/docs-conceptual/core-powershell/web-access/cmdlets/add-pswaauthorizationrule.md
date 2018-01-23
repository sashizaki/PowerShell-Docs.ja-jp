---
description: 
ms.topic: article
ms.prod: powershell
keywords: "PowerShell, コマンドレット"
ms.date: 2016-12-12
title: add pswaauthorizationrule
ms.technology: powershell
schema: 2.0.0
ms.openlocfilehash: 196797215a678e6f674592dc6b289816aced3c01
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="add-pswaauthorizationrule"></a><span data-ttu-id="2460f-103">Add-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="2460f-103">Add-PswaAuthorizationRule</span></span>

## <a name="synopsis"></a><span data-ttu-id="2460f-104">概要</span><span class="sxs-lookup"><span data-stu-id="2460f-104">SYNOPSIS</span></span>

<span data-ttu-id="2460f-105">Windows PowerShell® Web Access 承認規則のセットに新しい承認規則を追加します。</span><span class="sxs-lookup"><span data-stu-id="2460f-105">Adds a new authorization rule to the Windows PowerShell® Web Access authorization rule set.</span></span>

## <a name="syntax"></a><span data-ttu-id="2460f-106">構文</span><span class="sxs-lookup"><span data-stu-id="2460f-106">Syntax</span></span>

### <a name="usergroupnamecomputergroupname"></a><span data-ttu-id="2460f-107">UserGroupNameComputerGroupName</span><span class="sxs-lookup"><span data-stu-id="2460f-107">UserGroupNameComputerGroupName</span></span>
```
Add-PswaAuthorizationRule -ComputerGroupName <String> -ConfigurationName <String> -UserGroupName <String[]> [-Credential <PSCredential> ] [-Force] [-RuleName <String> ] [ <CommonParameters>]
```

### <a name="usergroupnamecomputername"></a><span data-ttu-id="2460f-108">UserGroupNameComputerName</span><span class="sxs-lookup"><span data-stu-id="2460f-108">UserGroupNameComputerName</span></span>
```
Add-PswaAuthorizationRule -ComputerName <String> -ConfigurationName <String> -UserGroupName <String[]> [-Credential <PSCredential> ] [-Force] [-RuleName <String> ] [ <CommonParameters>]
```

### <a name="usernamecomputergroupname"></a><span data-ttu-id="2460f-109">UserNameComputerGroupName</span><span class="sxs-lookup"><span data-stu-id="2460f-109">UserNameComputerGroupName</span></span>
```
Add-PswaAuthorizationRule [-UserName] <String[]> -ComputerGroupName <String> -ConfigurationName <String> [-Credential <PSCredential> ] [-Force] [-RuleName <String> ] [ <CommonParameters>]
```

### <a name="usernamecomputername"></a><span data-ttu-id="2460f-110">UserNameComputerName</span><span class="sxs-lookup"><span data-stu-id="2460f-110">UserNameComputerName</span></span>
```
Add-PswaAuthorizationRule [-UserName] <String[]> [-ComputerName] <String> [-ConfigurationName] <String> [-Credential <PSCredential> ] [-Force] [-RuleName <String> ] [ <CommonParameters>]
```

## <a name="description"></a><span data-ttu-id="2460f-111">説明</span><span class="sxs-lookup"><span data-stu-id="2460f-111">DESCRIPTION</span></span>

<span data-ttu-id="2460f-112">**Add-PswaAuthorizationRule** コマンドレットは、Windows PowerShell® Web Access 承認規則のセットに新しい承認規則を追加します。</span><span class="sxs-lookup"><span data-stu-id="2460f-112">The **Add-PswaAuthorizationRule** cmdlet adds a new authorization rule to the Windows PowerShell® Web Access authorization rule set.</span></span>

<span data-ttu-id="2460f-113">この規則には、ユーザー、コンピューター、Windows PowerShell エンドポイントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2460f-113">You must specify the users, computers, and Windows PowerShell endpoints for this rule.</span></span> <span data-ttu-id="2460f-114">個々のユーザー アカウント名、コンピューター名、またはグループを指定して、ユーザーとコンピューターの両方を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2460f-114">You can specify both users and computers either by individual user accounts and computer names, or by specifying groups.</span></span>

<span data-ttu-id="2460f-115">Active Directory ドメインに参加しているコンピューターの場合、このコマンドレットは、コンピューターのセキュリティ識別子 (SID) を使用して規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="2460f-115">For a computer that is joined to an Active Directory domain, the cmdlet uses the security identifier (SID) of the computer to create the rule.</span></span>
<span data-ttu-id="2460f-116">そのため、サインイン ページの **[コンピューター名]** フィールドに、短い名前、完全修飾ドメイン名 (FQDN)、または IP アドレスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2460f-116">This allows you to use a short name, a fully qualified domain name (FQDN), or an IP address for the **Computer Name** field on the sign-in page.</span></span>

<span data-ttu-id="2460f-117">Active Directory ドメインに参加していないコンピューターの場合、このコマンドレットは、管理者が指定したコンピューター名を使用して規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="2460f-117">For a computer that is not joined to an Active Directory domain, the cmdlet creates the rule using the computer name provided by the administrator.</span></span> <span data-ttu-id="2460f-118">このコンピューターに正常に接続するには、規則に指定されているとおりのコンピューター名をエンド ユーザーが正確に入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2460f-118">To successfully connect to this machine, the end user must provide the computer name exactly as it appears in the rule.</span></span>

<span data-ttu-id="2460f-119">ネットワーク上に同じ名前のコンピューターが複数ある場合、短い名前では複数のコンピューターに解決される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2460f-119">If there are multiple computers with the same name on the network, then short name can resolve to more than one computer.</span></span> <span data-ttu-id="2460f-120">その結果、接続を確立するときにあいまいさが生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2460f-120">This can lead to ambiguity when establishing a connection.</span></span> <span data-ttu-id="2460f-121">たとえば、"*Server1*" というワークグループ コンピューターの規則が存在し、*server1.contoso.com* という新しいコンピューターがネットワークに参加した場合、承認規則を使用した確認は成功し、PowerShell Web Access は、"*Server1*" というコンピューターに接続を確立しようとします。</span><span class="sxs-lookup"><span data-stu-id="2460f-121">For example, if a rule exists for the workgroup computer named "*Server1*” and a new computer named *server1.contoso.com* is joined to the network, validation using the authorization rules succeeds and Windows PowerShell Web Access attempts to establish a connection to the computer named “*Server1*”.</span></span> <span data-ttu-id="2460f-122">指定されたワークグループ コンピューターで接続が確立されることは保証されません。試行は、"*Server1*" という名前のワークグループまたはドメイン コンピューターに対して行われます。</span><span class="sxs-lookup"><span data-stu-id="2460f-122">It is not guaranteed that the connection is established with the specified workgroup computer; the attempt could be made on either the workgroup or the domain computer named "*Server1*".</span></span> <span data-ttu-id="2460f-123">承認規則を作成するには、あいまいさを減らすために、対象コンピューターの FQDN を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2460f-123">To reduce ambiguity, it is recommended that you use the FQDN for the destination computer whenever possible to create an authorization rule.</span></span>

<span data-ttu-id="2460f-124">承認規則は、代替資格情報ではなく、Windows PowerShell Web Access ユーザーのプライマリ サインイン資格情報を評価します (代替資格情報は、サインイン ページの **[オプションの接続設定]** セクションにある 2 つ目の資格情報セットです)。</span><span class="sxs-lookup"><span data-stu-id="2460f-124">The authorization rules evaluate the primary sign-in credential of the Windows PowerShell Web Access users, not the alternate credentials (the second set of credentials found in the **Optional connection settings** section of the sign-in page).</span></span> <span data-ttu-id="2460f-125">この例については、「例 6」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2460f-125">For an example of this, see Example 6.</span></span>

## <a name="parameters"></a><span data-ttu-id="2460f-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2460f-126">Parameters</span></span>

### <a name="-computergroupnameltstringgt"></a><span data-ttu-id="2460f-127">-ComputerGroupName&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="2460f-127">-ComputerGroupName&lt;String&gt;</span></span>

<span data-ttu-id="2460f-128">この規則がアクセス権を付与している Active Directory Domain Services (AD DS) のコンピューター グループまたはローカル グループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2460f-128">Specifies the name of a computer group in Active Directory Domain Services (AD DS) or local groups to which this rule grants access.</span></span>

|||  
|-|-|
| <span data-ttu-id="2460f-129">エイリアス</span><span class="sxs-lookup"><span data-stu-id="2460f-129">Aliases</span></span>                              | <span data-ttu-id="2460f-130">なし</span><span class="sxs-lookup"><span data-stu-id="2460f-130">none</span></span>                                 |
| <span data-ttu-id="2460f-131">必須?</span><span class="sxs-lookup"><span data-stu-id="2460f-131">Required?</span></span>                            | <span data-ttu-id="2460f-132">true</span><span class="sxs-lookup"><span data-stu-id="2460f-132">true</span></span>                                 |
| <span data-ttu-id="2460f-133">位置は?</span><span class="sxs-lookup"><span data-stu-id="2460f-133">Position?</span></span>                            | <span data-ttu-id="2460f-134">名前付き</span><span class="sxs-lookup"><span data-stu-id="2460f-134">named</span></span>                                |
| <span data-ttu-id="2460f-135">既定値</span><span class="sxs-lookup"><span data-stu-id="2460f-135">Default Value</span></span>                        | <span data-ttu-id="2460f-136">なし</span><span class="sxs-lookup"><span data-stu-id="2460f-136">none</span></span>                                 |
| <span data-ttu-id="2460f-137">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="2460f-137">Accept Pipeline Input?</span></span>               | <span data-ttu-id="2460f-138">True (ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="2460f-138">True (ByPropertyName)</span></span>                |
| <span data-ttu-id="2460f-139">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="2460f-139">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="2460f-140">false</span><span class="sxs-lookup"><span data-stu-id="2460f-140">false</span></span>                                |

### <a name="-computernameltstringgt"></a><span data-ttu-id="2460f-141">-ComputerName&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="2460f-141">-ComputerName&lt;String&gt;</span></span>

<span data-ttu-id="2460f-142">この規則がアクセス権を付与しているコンピューター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2460f-142">Specifies the computer name to which this rule grants access.</span></span>

|||  
|-|-|
| <span data-ttu-id="2460f-143">エイリアス</span><span class="sxs-lookup"><span data-stu-id="2460f-143">Aliases</span></span>                              | <span data-ttu-id="2460f-144">なし</span><span class="sxs-lookup"><span data-stu-id="2460f-144">none</span></span>                                 |
| <span data-ttu-id="2460f-145">必須?</span><span class="sxs-lookup"><span data-stu-id="2460f-145">Required?</span></span>                            | <span data-ttu-id="2460f-146">true</span><span class="sxs-lookup"><span data-stu-id="2460f-146">true</span></span>                                 |
| <span data-ttu-id="2460f-147">位置は?</span><span class="sxs-lookup"><span data-stu-id="2460f-147">Position?</span></span>                            | <span data-ttu-id="2460f-148">名前付き</span><span class="sxs-lookup"><span data-stu-id="2460f-148">named</span></span>                                |
| <span data-ttu-id="2460f-149">既定値</span><span class="sxs-lookup"><span data-stu-id="2460f-149">Default Value</span></span>                        | <span data-ttu-id="2460f-150">なし</span><span class="sxs-lookup"><span data-stu-id="2460f-150">none</span></span>                                 |
| <span data-ttu-id="2460f-151">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="2460f-151">Accept Pipeline Input?</span></span>               | <span data-ttu-id="2460f-152">True (ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="2460f-152">True (ByPropertyName)</span></span>                |
| <span data-ttu-id="2460f-153">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="2460f-153">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="2460f-154">false</span><span class="sxs-lookup"><span data-stu-id="2460f-154">false</span></span>                                |

### <a name="-configurationnameltstringgt"></a><span data-ttu-id="2460f-155">-ConfigurationName&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="2460f-155">-ConfigurationName&lt;String&gt;</span></span>

<span data-ttu-id="2460f-156">この規則がアクセス権を付与している Windows PowerShell セッション構成 (実行空間とも呼ばれます) の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2460f-156">Specifies the name of the Windows PowerShell session configuration, also known as runspace, to which this rule grants access.</span></span>

|||  
|-|-|
| <span data-ttu-id="2460f-157">エイリアス</span><span class="sxs-lookup"><span data-stu-id="2460f-157">Aliases</span></span>                              | <span data-ttu-id="2460f-158">なし</span><span class="sxs-lookup"><span data-stu-id="2460f-158">none</span></span>                                 |
| <span data-ttu-id="2460f-159">必須?</span><span class="sxs-lookup"><span data-stu-id="2460f-159">Required?</span></span>                            | <span data-ttu-id="2460f-160">true</span><span class="sxs-lookup"><span data-stu-id="2460f-160">true</span></span>                                 |
| <span data-ttu-id="2460f-161">位置は?</span><span class="sxs-lookup"><span data-stu-id="2460f-161">Position?</span></span>                            | <span data-ttu-id="2460f-162">名前付き</span><span class="sxs-lookup"><span data-stu-id="2460f-162">named</span></span>                                |
| <span data-ttu-id="2460f-163">既定値</span><span class="sxs-lookup"><span data-stu-id="2460f-163">Default Value</span></span>                        | <span data-ttu-id="2460f-164">なし</span><span class="sxs-lookup"><span data-stu-id="2460f-164">none</span></span>                                 |
| <span data-ttu-id="2460f-165">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="2460f-165">Accept Pipeline Input?</span></span>               | <span data-ttu-id="2460f-166">True (ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="2460f-166">True (ByPropertyName)</span></span>                |
| <span data-ttu-id="2460f-167">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="2460f-167">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="2460f-168">false</span><span class="sxs-lookup"><span data-stu-id="2460f-168">false</span></span>                                |

### <a name="-credentialltpscredentialgt"></a><span data-ttu-id="2460f-169">-Credential&lt;PSCredential&gt;</span><span class="sxs-lookup"><span data-stu-id="2460f-169">-Credential&lt;PSCredential&gt;</span></span>

<span data-ttu-id="2460f-170">Windows PowerShell Web Access 承認規則の変更に使用するユーザー アカウントの **PSCredential** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="2460f-170">Specifies a **PSCredential** object for a user account that you want to use to change Windows PowerShell Web Access authorization rules.</span></span> <span data-ttu-id="2460f-171">このパラメーターを追加しない場合、現在ログオンしているユーザー アカウントがコマンドレットにより使用されます。</span><span class="sxs-lookup"><span data-stu-id="2460f-171">If you do not add this parameter, the cmdlet uses the currently logged-on user account.</span></span> <span data-ttu-id="2460f-172">承認規則をリモートから追加するために必要な **PSCredential** オブジェクトを取得するには、[Get-Credential](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.security/Get-Credential) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="2460f-172">To get a **PSCredential** object, which is required to add authorization rules remotely, run the [Get-Credential](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.security/Get-Credential) cmdlet.</span></span>

|||  
|-|-|
| <span data-ttu-id="2460f-173">エイリアス</span><span class="sxs-lookup"><span data-stu-id="2460f-173">Aliases</span></span>                              | <span data-ttu-id="2460f-174">なし</span><span class="sxs-lookup"><span data-stu-id="2460f-174">none</span></span>                                 |
| <span data-ttu-id="2460f-175">必須?</span><span class="sxs-lookup"><span data-stu-id="2460f-175">Required?</span></span>                            | <span data-ttu-id="2460f-176">false</span><span class="sxs-lookup"><span data-stu-id="2460f-176">false</span></span>                                |
| <span data-ttu-id="2460f-177">位置は?</span><span class="sxs-lookup"><span data-stu-id="2460f-177">Position?</span></span>                            | <span data-ttu-id="2460f-178">名前付き</span><span class="sxs-lookup"><span data-stu-id="2460f-178">named</span></span>                                |
| <span data-ttu-id="2460f-179">既定値</span><span class="sxs-lookup"><span data-stu-id="2460f-179">Default Value</span></span>                        | <span data-ttu-id="2460f-180">なし</span><span class="sxs-lookup"><span data-stu-id="2460f-180">none</span></span>                                 |
| <span data-ttu-id="2460f-181">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="2460f-181">Accept Pipeline Input?</span></span>               | <span data-ttu-id="2460f-182">false</span><span class="sxs-lookup"><span data-stu-id="2460f-182">false</span></span>                                |
| <span data-ttu-id="2460f-183">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="2460f-183">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="2460f-184">false</span><span class="sxs-lookup"><span data-stu-id="2460f-184">false</span></span>                                |

### <a name="-force"></a><span data-ttu-id="2460f-185">-Force</span><span class="sxs-lookup"><span data-stu-id="2460f-185">-Force</span></span>

<span data-ttu-id="2460f-186">ユーザーに確認を求めずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2460f-186">Forces the command to run without asking for user confirmation.\\</span></span>
<span data-ttu-id="2460f-187">なお、単純な、または短いコンピューター名 (ドメイン名ではない名前、完全修飾されていない名前など) を入力した場合にも確認が求められます。</span><span class="sxs-lookup"><span data-stu-id="2460f-187">In addition, it also prompts for confirmation when you enter a simple or short computer name (such as a name that is not a domain name or is not fully qualified).</span></span> <span data-ttu-id="2460f-188">確認はセキュリティ上の理由で必要です。そのため、コンピューターがワークグループに参加している場合にのみ、コンピューターの追加に単純な名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2460f-188">Confirmation is requested for security reasons, so that you can use the simple name to add a computer only if the computer is in a workgroup.</span></span>

|||  
|-|-|
| <span data-ttu-id="2460f-189">エイリアス</span><span class="sxs-lookup"><span data-stu-id="2460f-189">Aliases</span></span>                              | <span data-ttu-id="2460f-190">なし</span><span class="sxs-lookup"><span data-stu-id="2460f-190">none</span></span>                                 |
| <span data-ttu-id="2460f-191">必須?</span><span class="sxs-lookup"><span data-stu-id="2460f-191">Required?</span></span>                            | <span data-ttu-id="2460f-192">false</span><span class="sxs-lookup"><span data-stu-id="2460f-192">false</span></span>                                |
| <span data-ttu-id="2460f-193">位置は?</span><span class="sxs-lookup"><span data-stu-id="2460f-193">Position?</span></span>                            | <span data-ttu-id="2460f-194">名前付き</span><span class="sxs-lookup"><span data-stu-id="2460f-194">named</span></span>                                |
| <span data-ttu-id="2460f-195">既定値</span><span class="sxs-lookup"><span data-stu-id="2460f-195">Default Value</span></span>                        | <span data-ttu-id="2460f-196">なし</span><span class="sxs-lookup"><span data-stu-id="2460f-196">none</span></span>                                 |
| <span data-ttu-id="2460f-197">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="2460f-197">Accept Pipeline Input?</span></span>               | <span data-ttu-id="2460f-198">false</span><span class="sxs-lookup"><span data-stu-id="2460f-198">false</span></span>                                |
| <span data-ttu-id="2460f-199">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="2460f-199">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="2460f-200">false</span><span class="sxs-lookup"><span data-stu-id="2460f-200">false</span></span>                                |

### <a name="-rulenameltstringgt"></a><span data-ttu-id="2460f-201">-RuleName&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="2460f-201">-RuleName&lt;String&gt;</span></span>

<span data-ttu-id="2460f-202">この規則のフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2460f-202">Specifies the friendly name for this rule.</span></span>

|||  
|-|-|
| <span data-ttu-id="2460f-203">エイリアス</span><span class="sxs-lookup"><span data-stu-id="2460f-203">Aliases</span></span>                              | <span data-ttu-id="2460f-204">なし</span><span class="sxs-lookup"><span data-stu-id="2460f-204">none</span></span>                                 |
| <span data-ttu-id="2460f-205">必須?</span><span class="sxs-lookup"><span data-stu-id="2460f-205">Required?</span></span>                            | <span data-ttu-id="2460f-206">false</span><span class="sxs-lookup"><span data-stu-id="2460f-206">false</span></span>                                |
| <span data-ttu-id="2460f-207">位置は?</span><span class="sxs-lookup"><span data-stu-id="2460f-207">Position?</span></span>                            | <span data-ttu-id="2460f-208">名前付き</span><span class="sxs-lookup"><span data-stu-id="2460f-208">named</span></span>                                |
| <span data-ttu-id="2460f-209">既定値</span><span class="sxs-lookup"><span data-stu-id="2460f-209">Default Value</span></span>                        | <span data-ttu-id="2460f-210">なし</span><span class="sxs-lookup"><span data-stu-id="2460f-210">none</span></span>                                 |
| <span data-ttu-id="2460f-211">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="2460f-211">Accept Pipeline Input?</span></span>               | <span data-ttu-id="2460f-212">True (ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="2460f-212">True (ByPropertyName)</span></span>                |
| <span data-ttu-id="2460f-213">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="2460f-213">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="2460f-214">false</span><span class="sxs-lookup"><span data-stu-id="2460f-214">false</span></span>                                |

### <a name="-usergroupnameltstringgt"></a><span data-ttu-id="2460f-215">-UserGroupName&lt;String\[\]&gt;</span><span class="sxs-lookup"><span data-stu-id="2460f-215">-UserGroupName&lt;String\[\]&gt;</span></span>

<span data-ttu-id="2460f-216">この規則がアクセス権を付与している AD DS またはローカル グループ内の 1 つまたは複数のユーザー グループ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2460f-216">Specifies the name of one or more user groups in AD DS or local groups to which this rule grants access.</span></span>

|||  
|-|-|
| <span data-ttu-id="2460f-217">エイリアス</span><span class="sxs-lookup"><span data-stu-id="2460f-217">Aliases</span></span>                              | <span data-ttu-id="2460f-218">なし</span><span class="sxs-lookup"><span data-stu-id="2460f-218">none</span></span>                                 |
| <span data-ttu-id="2460f-219">必須?</span><span class="sxs-lookup"><span data-stu-id="2460f-219">Required?</span></span>                            | <span data-ttu-id="2460f-220">true</span><span class="sxs-lookup"><span data-stu-id="2460f-220">true</span></span>                                 |
| <span data-ttu-id="2460f-221">位置は?</span><span class="sxs-lookup"><span data-stu-id="2460f-221">Position?</span></span>                            | <span data-ttu-id="2460f-222">名前付き</span><span class="sxs-lookup"><span data-stu-id="2460f-222">named</span></span>                                |
| <span data-ttu-id="2460f-223">既定値</span><span class="sxs-lookup"><span data-stu-id="2460f-223">Default Value</span></span>                        | <span data-ttu-id="2460f-224">なし</span><span class="sxs-lookup"><span data-stu-id="2460f-224">none</span></span>                                 |
| <span data-ttu-id="2460f-225">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="2460f-225">Accept Pipeline Input?</span></span>               | <span data-ttu-id="2460f-226">True (ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="2460f-226">True (ByPropertyName)</span></span>                |
| <span data-ttu-id="2460f-227">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="2460f-227">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="2460f-228">false</span><span class="sxs-lookup"><span data-stu-id="2460f-228">false</span></span>                                |

### <a name="-usernameltstringgt"></a><span data-ttu-id="2460f-229">-UserName&lt;String\[\]&gt;</span><span class="sxs-lookup"><span data-stu-id="2460f-229">-UserName&lt;String\[\]&gt;</span></span>

<span data-ttu-id="2460f-230">この規則がアクセス権を付与している 1 つまたは複数のコンピューター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2460f-230">Specifies one or more users to which this rule grants access.</span></span> <span data-ttu-id="2460f-231">ユーザー名には、ゲートウェイ コンピューター上のローカル ユーザー アカウント、または AD DS のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2460f-231">The user name can be a local user account on the gateway computer or a user in AD DS.</span></span>
<span data-ttu-id="2460f-232">形式は、`domain\user` または `computer\user` です。</span><span class="sxs-lookup"><span data-stu-id="2460f-232">The format is `domain\user` or `computer\user`.</span></span>

|||  
|-|-|
| <span data-ttu-id="2460f-233">エイリアス</span><span class="sxs-lookup"><span data-stu-id="2460f-233">Aliases</span></span>                              | <span data-ttu-id="2460f-234">なし</span><span class="sxs-lookup"><span data-stu-id="2460f-234">none</span></span>                                 |
| <span data-ttu-id="2460f-235">必須?</span><span class="sxs-lookup"><span data-stu-id="2460f-235">Required?</span></span>                            | <span data-ttu-id="2460f-236">true</span><span class="sxs-lookup"><span data-stu-id="2460f-236">true</span></span>                                 |
| <span data-ttu-id="2460f-237">位置は?</span><span class="sxs-lookup"><span data-stu-id="2460f-237">Position?</span></span>                            | <span data-ttu-id="2460f-238">1 で保護されたプロセスとして起動されました</span><span class="sxs-lookup"><span data-stu-id="2460f-238">1</span></span>                                    |
| <span data-ttu-id="2460f-239">既定値</span><span class="sxs-lookup"><span data-stu-id="2460f-239">Default Value</span></span>                        | <span data-ttu-id="2460f-240">なし</span><span class="sxs-lookup"><span data-stu-id="2460f-240">none</span></span>                                 |
| <span data-ttu-id="2460f-241">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="2460f-241">Accept Pipeline Input?</span></span>               | <span data-ttu-id="2460f-242">True (ByValue, ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="2460f-242">True (ByValue, ByPropertyName)</span></span>       |
| <span data-ttu-id="2460f-243">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="2460f-243">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="2460f-244">false</span><span class="sxs-lookup"><span data-stu-id="2460f-244">false</span></span>                                |

### <a name="ltcommonparametersgt"></a><span data-ttu-id="2460f-245">&lt;CommonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="2460f-245">&lt;CommonParameters&gt;</span></span>

<span data-ttu-id="2460f-246">このコマンドレットは、-Verbose、-Debug、-ErrorAction、-ErrorVariable、-OutBuffer、および -OutVariable という共通パラメーターをサポートします。</span><span class="sxs-lookup"><span data-stu-id="2460f-246">This cmdlet supports the common parameters: -Verbose, -Debug, -ErrorAction, -ErrorVariable, -OutBuffer, and -OutVariable.</span></span>
<span data-ttu-id="2460f-247">詳細については、「[about_CommonParameters](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/about/about_commonparameters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2460f-247">For more information, see [about_CommonParameters](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/about/about_commonparameters).</span></span>

## <a name="inputs"></a><span data-ttu-id="2460f-248">入力</span><span class="sxs-lookup"><span data-stu-id="2460f-248">INPUTS</span></span>

### <a name="string"></a><span data-ttu-id="2460f-249">String</span><span class="sxs-lookup"><span data-stu-id="2460f-249">String</span></span>

<span data-ttu-id="2460f-250">このコマンドレットは、入力として文字列または文字列の配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="2460f-250">This cmdlet accepts a string or an array of strings as input.</span></span>

### <a name="string"></a><span data-ttu-id="2460f-251">String\[\]</span><span class="sxs-lookup"><span data-stu-id="2460f-251">String\[\]</span></span>

<span data-ttu-id="2460f-252">このコマンドレットは、入力として文字列または文字列の配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="2460f-252">This cmdlet accepts a string or an array of strings as input.</span></span>

## <a name="outputs"></a><span data-ttu-id="2460f-253">出力</span><span class="sxs-lookup"><span data-stu-id="2460f-253">Outputs</span></span>

### <a name="microsoftmanagementpowershellwebaccesspswaauthorizationrule"></a><span data-ttu-id="2460f-254">Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="2460f-254">Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule</span></span>

<span data-ttu-id="2460f-255">このコマンドレットは、承認規則オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2460f-255">This cmdlet returns the an authorization rule object.</span></span>

## <a name="examples"></a><span data-ttu-id="2460f-256">例</span><span class="sxs-lookup"><span data-stu-id="2460f-256">EXAMPLES</span></span>

### <a name="example-1"></a><span data-ttu-id="2460f-257">例 1</span><span class="sxs-lookup"><span data-stu-id="2460f-257">EXAMPLE 1</span></span>

<span data-ttu-id="2460f-258">この例では、*srv2* 上の *SMAdmins* グループのユーザーについて、セッション構成に *PSWAEndpoint* (制限付き実行空間) のアクセス権を付与しています。</span><span class="sxs-lookup"><span data-stu-id="2460f-258">This example grants access to the session configuration *PSWAEndpoint*, a restricted runspace, on *srv2* for users in the *SMAdmins* group.\\</span></span>
<span data-ttu-id="2460f-259">**注**: このコンピューター名は完全修飾ドメイン名 (FQDN) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2460f-259">**Note**: The computer name must be a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="2460f-260">管理者は制限付きセッション構成または実行空間を定義します。実行空間とは、エンド ユーザーが実行できるコマンドレットおよびタスクの制限された範囲です。</span><span class="sxs-lookup"><span data-stu-id="2460f-260">Administrators define a restricted session configuration or runspace, which is a limited range of cmdlets and tasks that end users can run.</span></span> <span data-ttu-id="2460f-261">制限付き実行空間を定義すると、ユーザーは、許可されている Windows PowerShell® 実行空間内にない他のコンピューターにアクセスできなくなります。そのため、接続のセキュリティが強固になります。</span><span class="sxs-lookup"><span data-stu-id="2460f-261">Defining a restricted runspace can prevent users from accessing other computers that are not in the allowed Windows PowerShell® runspace, thus offering a more secure connection.</span></span> <span data-ttu-id="2460f-262">セッション構成の詳細については、「[about_Session_Configurations](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/about/about_session_configurations)」または「[Windows PowerShell Web Access の展開](../install-and-use-windows-powershell-web-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2460f-262">For more information on session configurations, see [about_Session_Configurations](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/about/about_session_configurations) or the [Install and Use Windows PowerShell Web Access](../install-and-use-windows-powershell-web-access.md).</span></span>

```PowerShell
Add-PswaAuthorizationRule -ComputerName srv2.contoso.com -UserGroupName contoso\SMAdmins -ConfigurationName PSWAEndpoint
```

### <a name="example-2"></a><span data-ttu-id="2460f-263">例 2</span><span class="sxs-lookup"><span data-stu-id="2460f-263">EXAMPLE 2</span></span>

<span data-ttu-id="2460f-264">この例では、*srv2* 上のユーザーで、contoso\\user1、contoso\\user2、contoso\\user3 というユーザーについて、既定の Windows PowerShell セッション構成 `Microsoft.PowerShell` にアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="2460f-264">This example grants access to the default Windows PowerShell session configuration, `Microsoft.PowerShell`, on *srv2* for users in the users named contoso\\user1, contoso\\user2, and contoso\\user3.</span></span> <span data-ttu-id="2460f-265">このコマンドレットは、3 つの規則を作成します (1 人 1 規則)。</span><span class="sxs-lookup"><span data-stu-id="2460f-265">This cmdlet creates three rules (1 per person).</span></span>

```PowerShell
Add-PswaAuthorizationRule –UserName contoso\user1, contoso\user2, contoso\user3 –ComputerName srv2.contoso.com -ConfigurationName Microsoft.PowerShell
```

### <a name="example-3"></a><span data-ttu-id="2460f-266">例 3</span><span class="sxs-lookup"><span data-stu-id="2460f-266">EXAMPLE 3</span></span>

<span data-ttu-id="2460f-267">この例は、パイプラインを使用してユーザー名値を入力する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2460f-267">This example illustrates how to input user name values via the pipeline.</span></span>

```
"contoso\user1","contoso\user2" | Add-pswaAuthorizationRule –ComputerName srv2.contoso.com –ConfigurationName Microsoft.PowerShell
```

### <a name="example-4"></a><span data-ttu-id="2460f-268">例 4</span><span class="sxs-lookup"><span data-stu-id="2460f-268">EXAMPLE 4</span></span>

<span data-ttu-id="2460f-269">この例は、プロパティ名を指定して、すべてのパラメーターがすべてのパイプラインの値を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2460f-269">This example illustrates how all parameters take values from pipeline by property name.</span></span>

````PowerShell
$o = New-Object -TypeName PSObject | 
    Add-Member -Type NoteProperty -Name "UserName" -Value "contoso\user1" -PassThru | 
    Add-Member -Type NoteProperty -Name "ComputerName" -Value "srv2.contoso.com" -PassThru | 
    Add-Member -Type NoteProperty -Name "ConfigurationName" -Value "Microsoft.PowerShell" –PassThru

$o | Add-PswaAuthorizationRule -UserName contoso\user1 -ConfigurationName Microsoft.PowerShell
````

### <a name="example-5"></a><span data-ttu-id="2460f-270">例 5</span><span class="sxs-lookup"><span data-stu-id="2460f-270">EXAMPLE 5</span></span>

<span data-ttu-id="2460f-271">この例は、*PswaServer\\ChrisLocal* というローカル ユーザーに、*srv1.contoso.com* というサーバーへのアクセス権を付与する規則を追加します。</span><span class="sxs-lookup"><span data-stu-id="2460f-271">This example adds a rule to allow the local user named *PswaServer\\ChrisLocal* access to the server named *srv1.contoso.com*.</span></span>

<span data-ttu-id="2460f-272">この例は、ゲートウェイがワークグループ内にあり、対象コンピューターがドメイン内にあるシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="2460f-272">This example illustrates a scenario where the gateway is in a workgroup and the destination computer is in a domain.</span></span> <span data-ttu-id="2460f-273">承認規則はゲートウェイ上のローカル ユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2460f-273">The authorization rule applies to the local users on the gateway.</span></span> <span data-ttu-id="2460f-274">Windows PowerShell Web Access のサインイン ページで、正常に認証するには、ユーザーが **[オプションの接続設定]** 領域で、2 つ目の資格情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2460f-274">On the Windows PowerShell Web Access sign-in page, to successfully authenticate, the user must provide a second set of credentials in the **Optional connection settings** area.</span></span> <span data-ttu-id="2460f-275">ゲートウェイ サーバーでは、複数セットの資格情報が使用され、*srv1.contoso.com* という対象コンピューターでユーザーの認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2460f-275">The gateway server uses the additional set of credentials to authenticate the user on the destination computer, a server named *srv1.contoso.com*.</span></span>

````
Add-PswaAuthorizationRule –UserName PswaServer\ChrisLocal –ComputerName srv1.contoso.com –ConfigurationName Microsoft.PowerShell
````

### <a name="example-6"></a><span data-ttu-id="2460f-276">例 6</span><span class="sxs-lookup"><span data-stu-id="2460f-276">EXAMPLE 6</span></span>

<span data-ttu-id="2460f-277">この例では、すべてのコンピューターですべてのエンドポイントに対するアクセス権をすべてのユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="2460f-277">This example allows all users access to all endpoints on all computers.</span></span>
<span data-ttu-id="2460f-278">これで、基本的に承認規則がオフになります。</span><span class="sxs-lookup"><span data-stu-id="2460f-278">This essentially turns off authorization rules.\\</span></span>
<span data-ttu-id="2460f-279">**注**: `*` ワイルド カード文字の使用は、セキュリティが重要な展開には推奨されません。また、テスト環境のみで使用するか、セキュリティを緩和できる展開でのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="2460f-279">**Note**: Use of the `*` wildcard character is not recommended for security-sensitive deployments and should only be considered for test environments or used in deployments where security can be relaxed.</span></span>

````PowerShell
Add-PswaAuthorizationRule –UserName * -ComputerName * -ConfigurationName *
````

## <a name="see-also"></a><span data-ttu-id="2460f-280">参照</span><span class="sxs-lookup"><span data-stu-id="2460f-280">See Also</span></span>

- <span data-ttu-id="2460f-281">[Get-PswaAuthorizationRule](https://technet.microsoft.com/en-us/library/jj592891(v=wps.630).aspx)</span><span class="sxs-lookup"><span data-stu-id="2460f-281">[Get-PswaAuthorizationRule](https://technet.microsoft.com/en-us/library/jj592891(v=wps.630).aspx)</span></span>
- <span data-ttu-id="2460f-282">[Remove-PswaAuthorizationRule](https://technet.microsoft.com/en-us/library/jj592893(v=wps.630).aspx)</span><span class="sxs-lookup"><span data-stu-id="2460f-282">[Remove-PswaAuthorizationRule](https://technet.microsoft.com/en-us/library/jj592893(v=wps.630).aspx)</span></span>
- <span data-ttu-id="2460f-283">[Test-PswaAuthorizationRule](https://technet.microsoft.com/en-us/library/jj592892(v=wps.630).aspx)</span><span class="sxs-lookup"><span data-stu-id="2460f-283">[Test-PswaAuthorizationRule](https://technet.microsoft.com/en-us/library/jj592892(v=wps.630).aspx)</span></span>
- <span data-ttu-id="2460f-284">[Install-PswaWebApplication](https://technet.microsoft.com/en-us/library/jj592894(v=wps.630).aspx)</span><span class="sxs-lookup"><span data-stu-id="2460f-284">[Install-PswaWebApplication](https://technet.microsoft.com/en-us/library/jj592894(v=wps.630).aspx)</span></span>
- [<span data-ttu-id="2460f-285">Add-Member</span><span class="sxs-lookup"><span data-stu-id="2460f-285">Add-Member</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=113280)
- [<span data-ttu-id="2460f-286">New-Object</span><span class="sxs-lookup"><span data-stu-id="2460f-286">New-Object</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=113355)
- [<span data-ttu-id="2460f-287">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="2460f-287">Get-Credential</span></span>](http://go.microsoft.com/fwlink/?LinkID=293936)
