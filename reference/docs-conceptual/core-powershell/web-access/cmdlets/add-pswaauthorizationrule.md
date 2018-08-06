---
ms.topic: reference
keywords: PowerShell, コマンドレット
ms.date: 12/12/2016
title: Add-PswaAuthorizationRule
schema: 2.0.0
ms.openlocfilehash: bcf897730881551ec16ce970de6a1330961b67e6
ms.sourcegitcommit: c3f1a83b59484651119630f3089aa51b6e7d4c3c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2018
ms.locfileid: "39268267"
---
# <a name="add-pswaauthorizationrule"></a><span data-ttu-id="82e83-103">Add-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="82e83-103">Add-PswaAuthorizationRule</span></span>

## <a name="synopsis"></a><span data-ttu-id="82e83-104">概要</span><span class="sxs-lookup"><span data-stu-id="82e83-104">SYNOPSIS</span></span>

<span data-ttu-id="82e83-105">Windows PowerShell Web Access 承認規則のセットに新しい承認規則を追加します。</span><span class="sxs-lookup"><span data-stu-id="82e83-105">Adds a new authorization rule to the Windows PowerShell Web Access authorization rule set.</span></span>

## <a name="syntax"></a><span data-ttu-id="82e83-106">構文</span><span class="sxs-lookup"><span data-stu-id="82e83-106">Syntax</span></span>

### <a name="usergroupnamecomputergroupname"></a><span data-ttu-id="82e83-107">UserGroupNameComputerGroupName</span><span class="sxs-lookup"><span data-stu-id="82e83-107">UserGroupNameComputerGroupName</span></span>

```
Add-PswaAuthorizationRule -ComputerGroupName <String> -ConfigurationName <String> -UserGroupName <String[]> [-Credential <PSCredential> ] [-Force] [-RuleName <String> ] [ <CommonParameters>]
```

### <a name="usergroupnamecomputername"></a><span data-ttu-id="82e83-108">UserGroupNameComputerName</span><span class="sxs-lookup"><span data-stu-id="82e83-108">UserGroupNameComputerName</span></span>

```
Add-PswaAuthorizationRule -ComputerName <String> -ConfigurationName <String> -UserGroupName <String[]> [-Credential <PSCredential> ] [-Force] [-RuleName <String> ] [ <CommonParameters>]
```

### <a name="usernamecomputergroupname"></a><span data-ttu-id="82e83-109">UserNameComputerGroupName</span><span class="sxs-lookup"><span data-stu-id="82e83-109">UserNameComputerGroupName</span></span>

```
Add-PswaAuthorizationRule [-UserName] <String[]> -ComputerGroupName <String> -ConfigurationName <String> [-Credential <PSCredential> ] [-Force] [-RuleName <String> ] [ <CommonParameters>]
```

### <a name="usernamecomputername"></a><span data-ttu-id="82e83-110">UserNameComputerName</span><span class="sxs-lookup"><span data-stu-id="82e83-110">UserNameComputerName</span></span>

```
Add-PswaAuthorizationRule [-UserName] <String[]> [-ComputerName] <String> [-ConfigurationName] <String> [-Credential <PSCredential> ] [-Force] [-RuleName <String> ] [ <CommonParameters>]
```

## <a name="description"></a><span data-ttu-id="82e83-111">説明</span><span class="sxs-lookup"><span data-stu-id="82e83-111">DESCRIPTION</span></span>

<span data-ttu-id="82e83-112">**Add-PswaAuthorizationRule** コマンドレットは、Windows PowerShell(r) Web Access 承認規則のセットに新しい承認規則を追加します。</span><span class="sxs-lookup"><span data-stu-id="82e83-112">The **Add-PswaAuthorizationRule** cmdlet adds a new authorization rule to the Windows PowerShell(r) Web Access authorization rule set.</span></span>

<span data-ttu-id="82e83-113">この規則には、ユーザー、コンピューター、Windows PowerShell エンドポイントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82e83-113">You must specify the users, computers, and Windows PowerShell endpoints for this rule.</span></span> <span data-ttu-id="82e83-114">個々のユーザー アカウント名、コンピューター名、またはグループを指定して、ユーザーとコンピューターの両方を指定できます。</span><span class="sxs-lookup"><span data-stu-id="82e83-114">You can specify both users and computers either by individual user accounts and computer names, or by specifying groups.</span></span>

<span data-ttu-id="82e83-115">Active Directory ドメインに参加しているコンピューターの場合、このコマンドレットは、コンピューターのセキュリティ識別子 (SID) を使用して規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="82e83-115">For a computer that is joined to an Active Directory domain, the cmdlet uses the security identifier (SID) of the computer to create the rule.</span></span> <span data-ttu-id="82e83-116">そのため、サインイン ページの **[コンピューター名]** フィールドに、短い名前、完全修飾ドメイン名 (FQDN)、または IP アドレスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="82e83-116">This allows you to use a short name, a fully qualified domain name (FQDN), or an IP address for the **Computer Name** field on the sign-in page.</span></span>

<span data-ttu-id="82e83-117">Active Directory ドメインに参加していないコンピューターの場合、このコマンドレットは、管理者が指定したコンピューター名を使用して規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="82e83-117">For a computer that is not joined to an Active Directory domain, the cmdlet creates the rule using the computer name provided by the administrator.</span></span> <span data-ttu-id="82e83-118">このコンピューターに正常に接続するには、規則に指定されているとおりのコンピューター名をエンド ユーザーが正確に入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82e83-118">To successfully connect to this machine, the end user must provide the computer name exactly as it appears in the rule.</span></span>

<span data-ttu-id="82e83-119">ネットワーク上に同じ名前のコンピューターが複数ある場合、短い名前では複数のコンピューターに解決される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82e83-119">If there are multiple computers with the same name on the network, then short name can resolve to more than one computer.</span></span> <span data-ttu-id="82e83-120">その結果、接続を確立するときにあいまいさが生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82e83-120">This can lead to ambiguity when establishing a connection.</span></span> <span data-ttu-id="82e83-121">たとえば、"*Server1*" というワークグループ コンピューターの規則が存在し、*server1.contoso.com* という新しいコンピューターがネットワークに参加した場合、承認規則を使用した確認は成功し、PowerShell Web Access は、"*Server1*" というコンピューターに接続を確立しようとします。</span><span class="sxs-lookup"><span data-stu-id="82e83-121">For example, if a rule exists for the workgroup computer named "*Server1*" and a new computer named *server1.contoso.com* is joined to the network, validation using the authorization rules succeeds and Windows PowerShell Web Access attempts to establish a connection to the computer named "*Server1*".</span></span> <span data-ttu-id="82e83-122">指定されたワークグループ コンピューターで接続が確立されることは保証されません。試行は、"*Server1*" という名前のワークグループまたはドメイン コンピューターに対して行われます。</span><span class="sxs-lookup"><span data-stu-id="82e83-122">It is not guaranteed that the connection is established with the specified workgroup computer; the attempt could be made on either the workgroup or the domain computer named "*Server1*".</span></span> <span data-ttu-id="82e83-123">承認規則を作成するには、あいまいさを減らすために、対象コンピューターの FQDN を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="82e83-123">To reduce ambiguity, it is recommended that you use the FQDN for the destination computer whenever possible to create an authorization rule.</span></span>

<span data-ttu-id="82e83-124">承認規則は、代替資格情報ではなく、Windows PowerShell Web Access ユーザーのプライマリ サインイン資格情報を評価します (代替資格情報は、サインイン ページの **[オプションの接続設定]** セクションにある 2 つ目の資格情報セットです)。</span><span class="sxs-lookup"><span data-stu-id="82e83-124">The authorization rules evaluate the primary sign-in credential of the Windows PowerShell Web Access users, not the alternate credentials (the second set of credentials found in the **Optional connection settings** section of the sign-in page).</span></span> <span data-ttu-id="82e83-125">この例については、「例 6」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82e83-125">For an example of this, see Example 6.</span></span>

## <a name="parameters"></a><span data-ttu-id="82e83-126">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82e83-126">Parameters</span></span>

### <a name="-computergroupname-string"></a><span data-ttu-id="82e83-127">-ComputerGroupName \<String\></span><span class="sxs-lookup"><span data-stu-id="82e83-127">-ComputerGroupName \<String\></span></span>

<span data-ttu-id="82e83-128">この規則がアクセス権を付与している Active Directory Domain Services (AD DS) のコンピューター グループまたはローカル グループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="82e83-128">Specifies the name of a computer group in Active Directory Domain Services (AD DS) or local groups to which this rule grants access.</span></span>

|||
|-|-|
| <span data-ttu-id="82e83-129">エイリアス</span><span class="sxs-lookup"><span data-stu-id="82e83-129">Aliases</span></span>                     | <span data-ttu-id="82e83-130">なし</span><span class="sxs-lookup"><span data-stu-id="82e83-130">none</span></span>                  |
| <span data-ttu-id="82e83-131">必須?</span><span class="sxs-lookup"><span data-stu-id="82e83-131">Required?</span></span>                   | <span data-ttu-id="82e83-132">true</span><span class="sxs-lookup"><span data-stu-id="82e83-132">true</span></span>                  |
| <span data-ttu-id="82e83-133">位置は?</span><span class="sxs-lookup"><span data-stu-id="82e83-133">Position?</span></span>                   | <span data-ttu-id="82e83-134">名前付き</span><span class="sxs-lookup"><span data-stu-id="82e83-134">named</span></span>                 |
| <span data-ttu-id="82e83-135">既定値</span><span class="sxs-lookup"><span data-stu-id="82e83-135">Default Value</span></span>               | <span data-ttu-id="82e83-136">なし</span><span class="sxs-lookup"><span data-stu-id="82e83-136">none</span></span>                  |
| <span data-ttu-id="82e83-137">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="82e83-137">Accept Pipeline Input?</span></span>      | <span data-ttu-id="82e83-138">True (ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="82e83-138">True (ByPropertyName)</span></span> |
| <span data-ttu-id="82e83-139">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="82e83-139">Accept Wildcard Characters?</span></span> | <span data-ttu-id="82e83-140">false</span><span class="sxs-lookup"><span data-stu-id="82e83-140">false</span></span>                 |

### <a name="-computername-string"></a><span data-ttu-id="82e83-141">-ComputerName \<String\></span><span class="sxs-lookup"><span data-stu-id="82e83-141">-ComputerName \<String\></span></span>

<span data-ttu-id="82e83-142">この規則がアクセス権を付与しているコンピューター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="82e83-142">Specifies the computer name to which this rule grants access.</span></span>

|||
|-|-|
| <span data-ttu-id="82e83-143">エイリアス</span><span class="sxs-lookup"><span data-stu-id="82e83-143">Aliases</span></span>                     | <span data-ttu-id="82e83-144">なし</span><span class="sxs-lookup"><span data-stu-id="82e83-144">none</span></span>                  |
| <span data-ttu-id="82e83-145">必須?</span><span class="sxs-lookup"><span data-stu-id="82e83-145">Required?</span></span>                   | <span data-ttu-id="82e83-146">true</span><span class="sxs-lookup"><span data-stu-id="82e83-146">true</span></span>                  |
| <span data-ttu-id="82e83-147">位置は?</span><span class="sxs-lookup"><span data-stu-id="82e83-147">Position?</span></span>                   | <span data-ttu-id="82e83-148">名前付き</span><span class="sxs-lookup"><span data-stu-id="82e83-148">named</span></span>                 |
| <span data-ttu-id="82e83-149">既定値</span><span class="sxs-lookup"><span data-stu-id="82e83-149">Default Value</span></span>               | <span data-ttu-id="82e83-150">なし</span><span class="sxs-lookup"><span data-stu-id="82e83-150">none</span></span>                  |
| <span data-ttu-id="82e83-151">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="82e83-151">Accept Pipeline Input?</span></span>      | <span data-ttu-id="82e83-152">True (ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="82e83-152">True (ByPropertyName)</span></span> |
| <span data-ttu-id="82e83-153">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="82e83-153">Accept Wildcard Characters?</span></span> | <span data-ttu-id="82e83-154">false</span><span class="sxs-lookup"><span data-stu-id="82e83-154">false</span></span>                 |

### <a name="-configurationname-string"></a><span data-ttu-id="82e83-155">-ConfigurationName \<String\></span><span class="sxs-lookup"><span data-stu-id="82e83-155">-ConfigurationName \<String\></span></span>

<span data-ttu-id="82e83-156">この規則がアクセス権を付与している Windows PowerShell セッション構成 (実行空間とも呼ばれます) の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="82e83-156">Specifies the name of the Windows PowerShell session configuration, also known as runspace, to which this rule grants access.</span></span>

|||
|-|-|
| <span data-ttu-id="82e83-157">エイリアス</span><span class="sxs-lookup"><span data-stu-id="82e83-157">Aliases</span></span>                     | <span data-ttu-id="82e83-158">なし</span><span class="sxs-lookup"><span data-stu-id="82e83-158">none</span></span>                  |
| <span data-ttu-id="82e83-159">必須?</span><span class="sxs-lookup"><span data-stu-id="82e83-159">Required?</span></span>                   | <span data-ttu-id="82e83-160">true</span><span class="sxs-lookup"><span data-stu-id="82e83-160">true</span></span>                  |
| <span data-ttu-id="82e83-161">位置は?</span><span class="sxs-lookup"><span data-stu-id="82e83-161">Position?</span></span>                   | <span data-ttu-id="82e83-162">名前付き</span><span class="sxs-lookup"><span data-stu-id="82e83-162">named</span></span>                 |
| <span data-ttu-id="82e83-163">既定値</span><span class="sxs-lookup"><span data-stu-id="82e83-163">Default Value</span></span>               | <span data-ttu-id="82e83-164">なし</span><span class="sxs-lookup"><span data-stu-id="82e83-164">none</span></span>                  |
| <span data-ttu-id="82e83-165">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="82e83-165">Accept Pipeline Input?</span></span>      | <span data-ttu-id="82e83-166">True (ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="82e83-166">True (ByPropertyName)</span></span> |
| <span data-ttu-id="82e83-167">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="82e83-167">Accept Wildcard Characters?</span></span> | <span data-ttu-id="82e83-168">false</span><span class="sxs-lookup"><span data-stu-id="82e83-168">false</span></span>                 |

### <a name="-credential--pscredential"></a><span data-ttu-id="82e83-169">-Credential  \<PSCredential\></span><span class="sxs-lookup"><span data-stu-id="82e83-169">-Credential  \<PSCredential\></span></span>

<span data-ttu-id="82e83-170">Windows PowerShell Web Access 承認規則の変更に使用するユーザー アカウントの **PSCredential** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="82e83-170">Specifies a **PSCredential** object for a user account that you want to use to change Windows PowerShell Web Access authorization rules.</span></span> <span data-ttu-id="82e83-171">このパラメーターを追加しない場合、現在ログオンしているユーザー アカウントがコマンドレットにより使用されます。</span><span class="sxs-lookup"><span data-stu-id="82e83-171">If you do not add this parameter, the cmdlet uses the currently logged-on user account.</span></span> <span data-ttu-id="82e83-172">承認規則をリモートから追加するために必要な **PSCredential** オブジェクトを取得するには、[Get-Credential](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.security/Get-Credential) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="82e83-172">To get a **PSCredential** object, which is required to add authorization rules remotely, run the [Get-Credential](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.security/Get-Credential) cmdlet.</span></span>

|||
|-|-|
| <span data-ttu-id="82e83-173">エイリアス</span><span class="sxs-lookup"><span data-stu-id="82e83-173">Aliases</span></span>                     | <span data-ttu-id="82e83-174">なし</span><span class="sxs-lookup"><span data-stu-id="82e83-174">none</span></span>  |
| <span data-ttu-id="82e83-175">必須?</span><span class="sxs-lookup"><span data-stu-id="82e83-175">Required?</span></span>                   | <span data-ttu-id="82e83-176">false</span><span class="sxs-lookup"><span data-stu-id="82e83-176">false</span></span> |
| <span data-ttu-id="82e83-177">位置は?</span><span class="sxs-lookup"><span data-stu-id="82e83-177">Position?</span></span>                   | <span data-ttu-id="82e83-178">名前付き</span><span class="sxs-lookup"><span data-stu-id="82e83-178">named</span></span> |
| <span data-ttu-id="82e83-179">既定値</span><span class="sxs-lookup"><span data-stu-id="82e83-179">Default Value</span></span>               | <span data-ttu-id="82e83-180">なし</span><span class="sxs-lookup"><span data-stu-id="82e83-180">none</span></span>  |
| <span data-ttu-id="82e83-181">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="82e83-181">Accept Pipeline Input?</span></span>      | <span data-ttu-id="82e83-182">false</span><span class="sxs-lookup"><span data-stu-id="82e83-182">false</span></span> |
| <span data-ttu-id="82e83-183">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="82e83-183">Accept Wildcard Characters?</span></span> | <span data-ttu-id="82e83-184">false</span><span class="sxs-lookup"><span data-stu-id="82e83-184">false</span></span> |

### <a name="-force"></a><span data-ttu-id="82e83-185">-Force</span><span class="sxs-lookup"><span data-stu-id="82e83-185">-Force</span></span>

<span data-ttu-id="82e83-186">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82e83-186">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="82e83-187">なお、単純な、または短いコンピューター名 (ドメイン名ではない名前、完全修飾されていない名前など) を入力した場合にも確認が求められます。</span><span class="sxs-lookup"><span data-stu-id="82e83-187">In addition, it also prompts for confirmation when you enter a simple or short computer name (such as a name that is not a domain name or is not fully qualified).</span></span> <span data-ttu-id="82e83-188">確認はセキュリティ上の理由で必要です。そのため、コンピューターがワークグループに参加している場合にのみ、コンピューターの追加に単純な名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="82e83-188">Confirmation is requested for security reasons, so that you can use the simple name to add a computer only if the computer is in a workgroup.</span></span>

|||
|-|-|
| <span data-ttu-id="82e83-189">エイリアス</span><span class="sxs-lookup"><span data-stu-id="82e83-189">Aliases</span></span>                              | <span data-ttu-id="82e83-190">なし</span><span class="sxs-lookup"><span data-stu-id="82e83-190">none</span></span>                                 |
| <span data-ttu-id="82e83-191">必須?</span><span class="sxs-lookup"><span data-stu-id="82e83-191">Required?</span></span>                            | <span data-ttu-id="82e83-192">false</span><span class="sxs-lookup"><span data-stu-id="82e83-192">false</span></span>                                |
| <span data-ttu-id="82e83-193">位置は?</span><span class="sxs-lookup"><span data-stu-id="82e83-193">Position?</span></span>                            | <span data-ttu-id="82e83-194">名前付き</span><span class="sxs-lookup"><span data-stu-id="82e83-194">named</span></span>                                |
| <span data-ttu-id="82e83-195">既定値</span><span class="sxs-lookup"><span data-stu-id="82e83-195">Default Value</span></span>                        | <span data-ttu-id="82e83-196">なし</span><span class="sxs-lookup"><span data-stu-id="82e83-196">none</span></span>                                 |
| <span data-ttu-id="82e83-197">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="82e83-197">Accept Pipeline Input?</span></span>               | <span data-ttu-id="82e83-198">false</span><span class="sxs-lookup"><span data-stu-id="82e83-198">false</span></span>                                |
| <span data-ttu-id="82e83-199">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="82e83-199">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="82e83-200">false</span><span class="sxs-lookup"><span data-stu-id="82e83-200">false</span></span>                                |

### <a name="-rulename-string"></a><span data-ttu-id="82e83-201">-RuleName \<String\></span><span class="sxs-lookup"><span data-stu-id="82e83-201">-RuleName \<String\></span></span>

<span data-ttu-id="82e83-202">この規則のフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="82e83-202">Specifies the friendly name for this rule.</span></span>

|||
|-|-|
| <span data-ttu-id="82e83-203">エイリアス</span><span class="sxs-lookup"><span data-stu-id="82e83-203">Aliases</span></span>                              | <span data-ttu-id="82e83-204">なし</span><span class="sxs-lookup"><span data-stu-id="82e83-204">none</span></span>                                 |
| <span data-ttu-id="82e83-205">必須?</span><span class="sxs-lookup"><span data-stu-id="82e83-205">Required?</span></span>                            | <span data-ttu-id="82e83-206">false</span><span class="sxs-lookup"><span data-stu-id="82e83-206">false</span></span>                                |
| <span data-ttu-id="82e83-207">位置は?</span><span class="sxs-lookup"><span data-stu-id="82e83-207">Position?</span></span>                            | <span data-ttu-id="82e83-208">名前付き</span><span class="sxs-lookup"><span data-stu-id="82e83-208">named</span></span>                                |
| <span data-ttu-id="82e83-209">既定値</span><span class="sxs-lookup"><span data-stu-id="82e83-209">Default Value</span></span>                        | <span data-ttu-id="82e83-210">なし</span><span class="sxs-lookup"><span data-stu-id="82e83-210">none</span></span>                                 |
| <span data-ttu-id="82e83-211">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="82e83-211">Accept Pipeline Input?</span></span>               | <span data-ttu-id="82e83-212">True (ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="82e83-212">True (ByPropertyName)</span></span>                |
| <span data-ttu-id="82e83-213">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="82e83-213">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="82e83-214">false</span><span class="sxs-lookup"><span data-stu-id="82e83-214">false</span></span>                                |

### <a name="-usergroupname-string"></a><span data-ttu-id="82e83-215">-UserGroupName \<String\[\]\></span><span class="sxs-lookup"><span data-stu-id="82e83-215">-UserGroupName \<String\[\]\></span></span>

<span data-ttu-id="82e83-216">この規則がアクセス権を付与している AD DS またはローカル グループ内の 1 つまたは複数のユーザー グループ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="82e83-216">Specifies the name of one or more user groups in AD DS or local groups to which this rule grants access.</span></span>

|||
|-|-|
| <span data-ttu-id="82e83-217">エイリアス</span><span class="sxs-lookup"><span data-stu-id="82e83-217">Aliases</span></span>                              | <span data-ttu-id="82e83-218">なし</span><span class="sxs-lookup"><span data-stu-id="82e83-218">none</span></span>                                 |
| <span data-ttu-id="82e83-219">必須?</span><span class="sxs-lookup"><span data-stu-id="82e83-219">Required?</span></span>                            | <span data-ttu-id="82e83-220">true</span><span class="sxs-lookup"><span data-stu-id="82e83-220">true</span></span>                                 |
| <span data-ttu-id="82e83-221">位置は?</span><span class="sxs-lookup"><span data-stu-id="82e83-221">Position?</span></span>                            | <span data-ttu-id="82e83-222">名前付き</span><span class="sxs-lookup"><span data-stu-id="82e83-222">named</span></span>                                |
| <span data-ttu-id="82e83-223">既定値</span><span class="sxs-lookup"><span data-stu-id="82e83-223">Default Value</span></span>                        | <span data-ttu-id="82e83-224">なし</span><span class="sxs-lookup"><span data-stu-id="82e83-224">none</span></span>                                 |
| <span data-ttu-id="82e83-225">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="82e83-225">Accept Pipeline Input?</span></span>               | <span data-ttu-id="82e83-226">True (ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="82e83-226">True (ByPropertyName)</span></span>                |
| <span data-ttu-id="82e83-227">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="82e83-227">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="82e83-228">false</span><span class="sxs-lookup"><span data-stu-id="82e83-228">false</span></span>                                |

### <a name="-username-string"></a><span data-ttu-id="82e83-229">-UserName \<String\[\]\></span><span class="sxs-lookup"><span data-stu-id="82e83-229">-UserName \<String\[\]\></span></span>

<span data-ttu-id="82e83-230">この規則がアクセス権を付与している 1 つまたは複数のコンピューター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="82e83-230">Specifies one or more users to which this rule grants access.</span></span> <span data-ttu-id="82e83-231">ユーザー名には、ゲートウェイ コンピューター上のローカル ユーザー アカウント、または AD DS のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="82e83-231">The user name can be a local user account on the gateway computer or a user in AD DS.</span></span> <span data-ttu-id="82e83-232">形式は、`domain\user` または `computer\user` です。</span><span class="sxs-lookup"><span data-stu-id="82e83-232">The format is `domain\user` or `computer\user`.</span></span>

|||
|-|-|
| <span data-ttu-id="82e83-233">エイリアス</span><span class="sxs-lookup"><span data-stu-id="82e83-233">Aliases</span></span>                              | <span data-ttu-id="82e83-234">なし</span><span class="sxs-lookup"><span data-stu-id="82e83-234">none</span></span>                                 |
| <span data-ttu-id="82e83-235">必須?</span><span class="sxs-lookup"><span data-stu-id="82e83-235">Required?</span></span>                            | <span data-ttu-id="82e83-236">true</span><span class="sxs-lookup"><span data-stu-id="82e83-236">true</span></span>                                 |
| <span data-ttu-id="82e83-237">位置は?</span><span class="sxs-lookup"><span data-stu-id="82e83-237">Position?</span></span>                            | <span data-ttu-id="82e83-238">1 で保護されたプロセスとして起動されました</span><span class="sxs-lookup"><span data-stu-id="82e83-238">1</span></span>                                    |
| <span data-ttu-id="82e83-239">既定値</span><span class="sxs-lookup"><span data-stu-id="82e83-239">Default Value</span></span>                        | <span data-ttu-id="82e83-240">なし</span><span class="sxs-lookup"><span data-stu-id="82e83-240">none</span></span>                                 |
| <span data-ttu-id="82e83-241">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="82e83-241">Accept Pipeline Input?</span></span>               | <span data-ttu-id="82e83-242">True (ByValue, ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="82e83-242">True (ByValue, ByPropertyName)</span></span>       |
| <span data-ttu-id="82e83-243">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="82e83-243">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="82e83-244">false</span><span class="sxs-lookup"><span data-stu-id="82e83-244">false</span></span>                                |

###  <a name="commonparameters"></a><span data-ttu-id="82e83-245">\<CommonParameters\></span><span class="sxs-lookup"><span data-stu-id="82e83-245">\<CommonParameters\></span></span>

<span data-ttu-id="82e83-246">このコマンドレットでは、</span><span class="sxs-lookup"><span data-stu-id="82e83-246">This cmdlet supports the common parameters:</span></span>

<span data-ttu-id="82e83-247">-Verbose、-Debug、-ErrorAction、-ErrorVariable、-OutBuffer、および -OutVariable といった一般的なパラメーターをサポートします。</span><span class="sxs-lookup"><span data-stu-id="82e83-247">-Verbose, -Debug, -ErrorAction, -ErrorVariable, -OutBuffer, and -OutVariable.</span></span>
<span data-ttu-id="82e83-248">詳細については、「[about_CommonParameters](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/about/about_commonparameters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82e83-248">For more information, see [about_CommonParameters](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/about/about_commonparameters).</span></span>

## <a name="inputs"></a><span data-ttu-id="82e83-249">入力</span><span class="sxs-lookup"><span data-stu-id="82e83-249">INPUTS</span></span>

### <a name="string"></a><span data-ttu-id="82e83-250">String</span><span class="sxs-lookup"><span data-stu-id="82e83-250">String</span></span>

<span data-ttu-id="82e83-251">このコマンドレットは、入力として文字列または文字列の配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="82e83-251">This cmdlet accepts a string or an array of strings as input.</span></span>

### <a name="string"></a><span data-ttu-id="82e83-252">String\[\]</span><span class="sxs-lookup"><span data-stu-id="82e83-252">String\[\]</span></span>

<span data-ttu-id="82e83-253">このコマンドレットは、入力として文字列または文字列の配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="82e83-253">This cmdlet accepts a string or an array of strings as input.</span></span>

## <a name="outputs"></a><span data-ttu-id="82e83-254">出力</span><span class="sxs-lookup"><span data-stu-id="82e83-254">Outputs</span></span>

### <a name="microsoftmanagementpowershellwebaccesspswaauthorizationrule"></a><span data-ttu-id="82e83-255">Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="82e83-255">Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule</span></span>

<span data-ttu-id="82e83-256">このコマンドレットは、承認規則オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="82e83-256">This cmdlet returns the an authorization rule object.</span></span>

## <a name="examples"></a><span data-ttu-id="82e83-257">例</span><span class="sxs-lookup"><span data-stu-id="82e83-257">EXAMPLES</span></span>

### <a name="example-1"></a><span data-ttu-id="82e83-258">例 1</span><span class="sxs-lookup"><span data-stu-id="82e83-258">EXAMPLE 1</span></span>

<span data-ttu-id="82e83-259">この例では、_srv2_ 上の _SMAdmins_ グループのユーザーについて、セッション構成に _PSWAEndpoint_ (制限付き実行空間) のアクセス権を付与しています。</span><span class="sxs-lookup"><span data-stu-id="82e83-259">This example grants access to the session configuration _PSWAEndpoint_, a restricted runspace, on _srv2_ for users in the _SMAdmins_ group.</span></span>

> [!NOTE]
> <span data-ttu-id="82e83-260">このコンピューター名は完全修飾ドメイン名 (FQDN) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82e83-260">The computer name must be a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="82e83-261">管理者は制限付きセッション構成または実行空間を定義します。実行空間とは、エンド ユーザーが実行できるコマンドレットおよびタスクの制限された範囲です。</span><span class="sxs-lookup"><span data-stu-id="82e83-261">Administrators define a restricted session configuration or runspace, which is a limited range of cmdlets and tasks that end users can run.</span></span> <span data-ttu-id="82e83-262">制限付き実行空間を定義すると、ユーザーは、許可されている Windows PowerShell(r) 実行空間内にない他のコンピューターにアクセスできなくなります。そのため、接続のセキュリティが強固になります。</span><span class="sxs-lookup"><span data-stu-id="82e83-262">Defining a restricted runspace can prevent users from accessing other computers that are not in the allowed Windows PowerShell(r) runspace, thus offering a more secure connection.</span></span> <span data-ttu-id="82e83-263">セッション構成の詳細については、「[about_Session_Configurations](/powershell/module/microsoft.powershell.core/about/about_session_configurations)」または「[Windows PowerShell Web Access のインストールと使用](../install-and-use-windows-powershell-web-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82e83-263">For more information on session configurations, see [about_Session_Configurations](/powershell/module/microsoft.powershell.core/about/about_session_configurations) or [Install and Use Windows PowerShell Web Access](../install-and-use-windows-powershell-web-access.md).</span></span>

```powershell
Add-PswaAuthorizationRule -ComputerName srv2.contoso.com -UserGroupName contoso\SMAdmins -ConfigurationName PSWAEndpoint
```

### <a name="example-2"></a><span data-ttu-id="82e83-264">例 2</span><span class="sxs-lookup"><span data-stu-id="82e83-264">EXAMPLE 2</span></span>

<span data-ttu-id="82e83-265">この例では、既定の Windows PowerShell セッション構成 (`Microsoft.PowerShell`) に対するアクセス権を、ユーザー名が `contoso\user1`、`contoso\user2`、`contoso\user3` であるユーザーの *srv2* に付与します。</span><span class="sxs-lookup"><span data-stu-id="82e83-265">This example grants access to the default Windows PowerShell session configuration, `Microsoft.PowerShell`, on *srv2* for users in the users named `contoso\user1`, `contoso\user2`, and `contoso\user3`.</span></span> <span data-ttu-id="82e83-266">このコマンドレットは、3 つの規則を作成します (1 人 1 規則)。</span><span class="sxs-lookup"><span data-stu-id="82e83-266">This cmdlet creates three rules (1 per person).</span></span>

```powershell
Add-PswaAuthorizationRule -UserName contoso\user1, contoso\user2, contoso\user3 -ComputerName srv2.contoso.com -ConfigurationName Microsoft.PowerShell
```

### <a name="example-3"></a><span data-ttu-id="82e83-267">例 3</span><span class="sxs-lookup"><span data-stu-id="82e83-267">EXAMPLE 3</span></span>

<span data-ttu-id="82e83-268">この例は、パイプラインを使用してユーザー名値を入力する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="82e83-268">This example illustrates how to input user name values via the pipeline.</span></span>

```powershell
"contoso\user1","contoso\user2" | Add-pswaAuthorizationRule -ComputerName srv2.contoso.com -ConfigurationName Microsoft.PowerShell
```

### <a name="example-4"></a><span data-ttu-id="82e83-269">例 4</span><span class="sxs-lookup"><span data-stu-id="82e83-269">EXAMPLE 4</span></span>

<span data-ttu-id="82e83-270">この例は、プロパティ名を指定して、すべてのパラメーターがすべてのパイプラインの値を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="82e83-270">This example illustrates how all parameters take values from pipeline by property name.</span></span>

````powershell
$o = New-Object -TypeName PSObject |
    Add-Member -Type NoteProperty -Name "UserName" -Value "contoso\user1" -PassThru |
    Add-Member -Type NoteProperty -Name "ComputerName" -Value "srv2.contoso.com" -PassThru |
    Add-Member -Type NoteProperty -Name "ConfigurationName" -Value "Microsoft.PowerShell" -PassThru

$o | Add-PswaAuthorizationRule -UserName contoso\user1 -ConfigurationName Microsoft.PowerShell
````

### <a name="example-5"></a><span data-ttu-id="82e83-271">例 5</span><span class="sxs-lookup"><span data-stu-id="82e83-271">EXAMPLE 5</span></span>

<span data-ttu-id="82e83-272">この例は、`PswaServer\ChrisLocal` というローカル ユーザーに、**srv1.contoso.com** というサーバーへのアクセス権を付与する規則を追加します。</span><span class="sxs-lookup"><span data-stu-id="82e83-272">This example adds a rule to allow the local user named `PswaServer\ChrisLocal` access to the server named **srv1.contoso.com**.</span></span>

<span data-ttu-id="82e83-273">この例は、ゲートウェイがワークグループ内にあり、対象コンピューターがドメイン内にあるシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="82e83-273">This example illustrates a scenario where the gateway is in a workgroup and the destination computer is in a domain.</span></span> <span data-ttu-id="82e83-274">承認規則はゲートウェイ上のローカル ユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="82e83-274">The authorization rule applies to the local users on the gateway.</span></span> <span data-ttu-id="82e83-275">Windows PowerShell Web Access のサインイン ページで、正常に認証するには、ユーザーが **[オプションの接続設定]** 領域で、2 つ目の資格情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82e83-275">On the Windows PowerShell Web Access sign-in page, to successfully authenticate, the user must provide a second set of credentials in the **Optional connection settings** area.</span></span> <span data-ttu-id="82e83-276">ゲートウェイ サーバーでは、複数セットの資格情報が使用され、*srv1.contoso.com* という対象コンピューターでユーザーの認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="82e83-276">The gateway server uses the additional set of credentials to authenticate the user on the destination computer, a server named *srv1.contoso.com*.</span></span>

````powershell
Add-PswaAuthorizationRule -UserName PswaServer\ChrisLocal -ComputerName srv1.contoso.com -ConfigurationName Microsoft.PowerShell
````

### <a name="example-6"></a><span data-ttu-id="82e83-277">例 6</span><span class="sxs-lookup"><span data-stu-id="82e83-277">EXAMPLE 6</span></span>

<span data-ttu-id="82e83-278">この例では、すべてのコンピューターですべてのエンドポイントに対するアクセス権をすべてのユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="82e83-278">This example allows all users access to all endpoints on all computers.</span></span> <span data-ttu-id="82e83-279">これで、基本的に承認規則がオフになります。</span><span class="sxs-lookup"><span data-stu-id="82e83-279">This essentially turns off authorization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="82e83-280">`*` ワイルド カード文字の使用は、セキュリティが重要な展開には推奨されません。また、テスト環境のみで使用するか、セキュリティを緩和できる展開でのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="82e83-280">Use of the `*` wildcard character is not recommended for security-sensitive deployments and should only be considered for test environments or used in deployments where security can be relaxed.</span></span>

````powershell
Add-PswaAuthorizationRule -UserName * -ComputerName * -ConfigurationName *
````

## <a name="see-also"></a><span data-ttu-id="82e83-281">参照</span><span class="sxs-lookup"><span data-stu-id="82e83-281">See Also</span></span>

<span data-ttu-id="82e83-282">[Get-PswaAuthorizationRule](https://technet.microsoft.com/en-us/library/jj592891(v=wps.630).aspx)</span><span class="sxs-lookup"><span data-stu-id="82e83-282">[Get-PswaAuthorizationRule](https://technet.microsoft.com/en-us/library/jj592891(v=wps.630).aspx)</span></span>

<span data-ttu-id="82e83-283">[Remove-PswaAuthorizationRule](https://technet.microsoft.com/en-us/library/jj592893(v=wps.630).aspx)</span><span class="sxs-lookup"><span data-stu-id="82e83-283">[Remove-PswaAuthorizationRule](https://technet.microsoft.com/en-us/library/jj592893(v=wps.630).aspx)</span></span>

<span data-ttu-id="82e83-284">[Test-PswaAuthorizationRule](https://technet.microsoft.com/en-us/library/jj592892(v=wps.630).aspx)</span><span class="sxs-lookup"><span data-stu-id="82e83-284">[Test-PswaAuthorizationRule](https://technet.microsoft.com/en-us/library/jj592892(v=wps.630).aspx)</span></span>

<span data-ttu-id="82e83-285">[Install-PswaWebApplication](https://technet.microsoft.com/en-us/library/jj592894(v=wps.630).aspx)</span><span class="sxs-lookup"><span data-stu-id="82e83-285">[Install-PswaWebApplication](https://technet.microsoft.com/en-us/library/jj592894(v=wps.630).aspx)</span></span>

[<span data-ttu-id="82e83-286">Add-Member</span><span class="sxs-lookup"><span data-stu-id="82e83-286">Add-Member</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=113280)

[<span data-ttu-id="82e83-287">New-Object</span><span class="sxs-lookup"><span data-stu-id="82e83-287">New-Object</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=113355)

[<span data-ttu-id="82e83-288">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="82e83-288">Get-Credential</span></span>](http://go.microsoft.com/fwlink/?LinkID=293936)