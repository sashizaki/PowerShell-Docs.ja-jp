---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell Web Access の承認規則とセキュリティ機能"
ms.openlocfilehash: 706830f618173879185f5b84570fdc7782434d59
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="authorization-rules-and-security-features-of-windows-powershell-web-access"></a><span data-ttu-id="c3501-103">Windows PowerShell Web Access の承認規則とセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="c3501-103">Authorization Rules and Security Features of Windows PowerShell Web Access</span></span>

<span data-ttu-id="c3501-104">最終更新日: 2013 年 6 月 24 日</span><span class="sxs-lookup"><span data-stu-id="c3501-104">Updated: June 24, 2013</span></span>

<span data-ttu-id="c3501-105">適用対象: Windows Server 2012 R2、Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="c3501-105">Applies To: Windows Server 2012 R2, Windows Server 2012</span></span>

<span data-ttu-id="c3501-106">Windows Server® 2012 R2 および Windows Server® 2012 の Windows PowerShell® Web Access のセキュリティ モデルには制限があります。</span><span class="sxs-lookup"><span data-stu-id="c3501-106">Windows PowerShell® Web Access in Windows Server® 2012 R2 and Windows Server® 2012 has a restrictive security model.</span></span> <span data-ttu-id="c3501-107">ユーザーが Windows PowerShell Web Access ゲートウェイにサインインし、Web ベースの Windows PowerShell コンソールを使用するには、アクセス許可が明示的に付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3501-107">Users must explicitly be granted access before they can sign in to the Windows PowerShell Web Access gateway and use the web-based Windows PowerShell console.</span></span>

-   [<span data-ttu-id="c3501-108">承認規則とサイト セキュリティの構成</span><span class="sxs-lookup"><span data-stu-id="c3501-108">Configuring authorization rules and site security</span></span>](#BKMK_auth)

-   [<span data-ttu-id="c3501-109">セッションの管理</span><span class="sxs-lookup"><span data-stu-id="c3501-109">Session management</span></span>](#BKMK_sesmgmt)


<span data-ttu-id="c3501-110">Windows PowerShell Web Access をインストールし、ゲートウェイを構成すると、ユーザーがブラウザーでサインイン ページを開けるようになります。ただし、Windows PowerShell Web Access 管理者によってアクセスを明示的に許可されない限りサインインできません。</span><span class="sxs-lookup"><span data-stu-id="c3501-110">After Windows PowerShell Web Access is installed and the gateway is configured, users can open the sign-in page in a browser, but they cannot sign in until the Windows PowerShell Web Access administrator grants users access explicitly.</span></span> <span data-ttu-id="c3501-111">Windows PowerShell Web Access のアクセス制御は、次の表に示す一連の Windows PowerShell コマンドレットによって管理します。</span><span class="sxs-lookup"><span data-stu-id="c3501-111">Windows PowerShell Web Access access control is managed by using the set of Windows PowerShell cmdlets described in the following table.</span></span> <span data-ttu-id="c3501-112">承認規則の追加と管理に関しては、相当する GUI はありません。</span><span class="sxs-lookup"><span data-stu-id="c3501-112">There is no comparable GUI for adding or managing authorization rules.</span></span> <span data-ttu-id="c3501-113">Windows PowerShell Web Access コマンドレットの詳細については、コマンドレット リファレンス トピック「[Windows PowerShell Web Access Cmdlets](https://technet.microsoft.com/library/hh918342.aspx)」(Windows PowerShell Web Access コマンドレット) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3501-113">For more detailed information about Windows PowerShell Web Access cmdlets, see the cmdlet reference topics, [Windows PowerShell Web Access Cmdlets](https://technet.microsoft.com/library/hh918342.aspx).</span></span>

<span data-ttu-id="c3501-114">管理者は、Windows PowerShell Web Access に 0 個から*n* 個の認証規則を定義できます。</span><span class="sxs-lookup"><span data-stu-id="c3501-114">Administrators can define 0-*n* authentication rules for Windows PowerShell Web Access.</span></span> <span data-ttu-id="c3501-115">既定のセキュリティは、許容的ではなく制限的なものになります。認証規則がゼロの場合には、すべてのユーザーがすべてのアクセスを禁止されます。</span><span class="sxs-lookup"><span data-stu-id="c3501-115">The default security is restrictive rather than permissive; zero authentication rules means no users have access to anything.</span></span>

<span data-ttu-id="c3501-116">Windows Server 2012 R2 の Add-PswaAuthorizationRule および Test-PswaAuthorizationRule に、リモート コンピューターから、またはアクティブな Windows PowerShell Web Access セッション内から Windows PowerShell Web Access 承認規則を追加およびテストできるようにするために、資格情報パラメーターが用意されました。</span><span class="sxs-lookup"><span data-stu-id="c3501-116">Add-PswaAuthorizationRule and Test-PswaAuthorizationRule in Windows Server 2012 R2 include a Credential parameter that allows you to add and test Windows PowerShell Web Access authorization rules from a remote computer, or from within an active Windows PowerShell Web Access session.</span></span> <span data-ttu-id="c3501-117">資格情報パラメーターを持つ他の Windows PowerShell コマンドレットと同様、PSCredential オブジェクトをパラメーターの値として指定できます。</span><span class="sxs-lookup"><span data-stu-id="c3501-117">As with other Windows PowerShell cmdlets that have a Credential parameter, you can specify a PSCredential object as the value of the parameter.</span></span> <span data-ttu-id="c3501-118">リモート コンピューターに渡す資格情報を含む PSCredential オブジェクトを作成するには、[Get-Credential](https://technet.microsoft.com/library/hh849815.aspx) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3501-118">To create a PSCredential object that contains credentials you want to pass to a remote computer, run the [Get-Credential](https://technet.microsoft.com/library/hh849815.aspx) cmdlet.</span></span>

<span data-ttu-id="c3501-119">Windows PowerShell Web Access の認証規則はホワイトリスト方式です。</span><span class="sxs-lookup"><span data-stu-id="c3501-119">Windows PowerShell Web Access authentication rules are whitelist rules.</span></span> <span data-ttu-id="c3501-120">各規則は、ユーザー、対象コンピューター、および指定された対象コンピューターにおける特定の Windows PowerShell [セッション構成](https://technet.microsoft.com/library/dd819508.aspx) (エンドポイントまたは実行空間とも呼ばれます) の間に許可される接続を定義したものです。</span><span class="sxs-lookup"><span data-stu-id="c3501-120">Each rule is a definition of an allowed connection between users, target computers, and particular Windows PowerShell [session configurations](https://technet.microsoft.com/library/dd819508.aspx) (also referred to as endpoints or runspaces) on specified target computers.</span></span>

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3501-121"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC17938.jpeg" title="System_CAPS_security" alt="System_CAPS_security" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-security" /></span><span class="alertTitle">セキュリティ メモ</span></span><span class="sxs-lookup"><span data-stu-id="c3501-121"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC17938.jpeg" title="System_CAPS_security" alt="System_CAPS_security" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-security" /></span><span class="alertTitle"> Security Note </span></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3501-122">アクセスを許可されるためにユーザーが従う必要がある規則は 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="c3501-122">A user needs only one rule to be true to get access.</span></span> <span data-ttu-id="c3501-123">1 つのコンピューターに対する全言語でのアクセス、または Windows PowerShell リモート管理コマンドレットだけに対するアクセスを許可されているユーザーは、Web ベース コンソールから、最初の対象コンピューターに接続されているその他のコンピューターにログオン (ホップ) できます。</span><span class="sxs-lookup"><span data-stu-id="c3501-123">If a user is given access to one computer with either full language access or access only to Windows PowerShell remote management cmdlets, from the web-based console, the user can log on (or hop) to other computers that are connected to the first target computer.</span></span> <span data-ttu-id="c3501-124">Windows PowerShell Web Access の最も安全な構成方法は、制約付きセッション構成 (エンドポイントまたは実行空間とも呼ばれます) に対するアクセスだけを許可し、通常リモートでの実行が必要になる特定のタスクを完了できるようにする方法です。</span><span class="sxs-lookup"><span data-stu-id="c3501-124">The most secure way to configure Windows PowerShell Web Access is to allow users access only to constrained session configurations (also called endpoints or runspaces) that allow them to accomplish specific tasks that they normally need to perform remotely.</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c3501-125">名前</span><span class="sxs-lookup"><span data-stu-id="c3501-125">Name</span></span></p></th>
<th><p><span data-ttu-id="c3501-126">説明</span><span class="sxs-lookup"><span data-stu-id="c3501-126">Description</span></span></p></th>
<th><p><span data-ttu-id="c3501-127">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3501-127">Parameters</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3501-128"><a href="https://technet.microsoft.com/library/jj592890.aspx">Add-PswaAuthorizationRule</a></span><span class="sxs-lookup"><span data-stu-id="c3501-128"><a href="https://technet.microsoft.com/library/jj592890.aspx">Add-PswaAuthorizationRule</a></span></span></p></td>
<td><p><span data-ttu-id="c3501-129">Windows PowerShell Web Access 承認規則のセットに新しい承認規則を追加します。</span><span class="sxs-lookup"><span data-stu-id="c3501-129">Adds a new authorization rule to the Windows PowerShell Web Access authorization rule set.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c3501-130">ComputerGroupName</span><span class="sxs-lookup"><span data-stu-id="c3501-130">ComputerGroupName</span></span></p></li>
<li><p><span data-ttu-id="c3501-131">ComputerName</span><span class="sxs-lookup"><span data-stu-id="c3501-131">ComputerName</span></span></p></li>
<li><p><span data-ttu-id="c3501-132">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="c3501-132">ConfigurationName</span></span></p></li>
<li><p><span data-ttu-id="c3501-133">RuleName</span><span class="sxs-lookup"><span data-stu-id="c3501-133">RuleName</span></span></p></li>
<li><p><span data-ttu-id="c3501-134">UserGroupName</span><span class="sxs-lookup"><span data-stu-id="c3501-134">UserGroupName</span></span></p></li>
<li><p><span data-ttu-id="c3501-135">UserName</span><span class="sxs-lookup"><span data-stu-id="c3501-135">UserName</span></span></p></li>
<li><p><span data-ttu-id="c3501-136">資格情報 (Windows Server 2012 R2 以降)</span><span class="sxs-lookup"><span data-stu-id="c3501-136">Credential (Windows Server 2012 R2 and later)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3501-137"><a href="https://technet.microsoft.com/library/jj592893.aspx">Remove-PswaAuthorizationRule</a></span><span class="sxs-lookup"><span data-stu-id="c3501-137"><a href="https://technet.microsoft.com/library/jj592893.aspx">Remove-PswaAuthorizationRule</a></span></span></p></td>
<td><p><span data-ttu-id="c3501-138">指定された承認規則を Windows PowerShell Web Access から削除します。</span><span class="sxs-lookup"><span data-stu-id="c3501-138">Removes a specified authorization rule from Windows PowerShell Web Access.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c3501-139">Id</span><span class="sxs-lookup"><span data-stu-id="c3501-139">Id</span></span></p></li>
<li><p><span data-ttu-id="c3501-140">RuleName</span><span class="sxs-lookup"><span data-stu-id="c3501-140">RuleName</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3501-141"><a href="https://technet.microsoft.com/library/jj592891.aspx">Get-PswaAuthorizationRule</a></span><span class="sxs-lookup"><span data-stu-id="c3501-141"><a href="https://technet.microsoft.com/library/jj592891.aspx">Get-PswaAuthorizationRule</a></span></span></p></td>
<td><p><span data-ttu-id="c3501-142">Windows PowerShell Web Access の承認規則のセットを返します。</span><span class="sxs-lookup"><span data-stu-id="c3501-142">Returns a set of Windows PowerShell Web Access authorization rules.</span></span> <span data-ttu-id="c3501-143">パラメーターなしで使われた場合、このコマンドレットはすべての規則を返します。</span><span class="sxs-lookup"><span data-stu-id="c3501-143">When it is used without parameters, the cmdlet returns all rules.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c3501-144">Id</span><span class="sxs-lookup"><span data-stu-id="c3501-144">Id</span></span></p></li>
<li><p><span data-ttu-id="c3501-145">RuleName</span><span class="sxs-lookup"><span data-stu-id="c3501-145">RuleName</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3501-146"><a href="https://technet.microsoft.com/library/jj592892.aspx">Test-PswaAuthorizationRule</a></span><span class="sxs-lookup"><span data-stu-id="c3501-146"><a href="https://technet.microsoft.com/library/jj592892.aspx">Test-PswaAuthorizationRule</a></span></span></p></td>
<td><p><span data-ttu-id="c3501-147">承認規則を評価して、特定のユーザー、コンピューター、またはセッション構成のアクセス要求が承認されるかどうかを判定します。</span><span class="sxs-lookup"><span data-stu-id="c3501-147">Evaluates authorization rules to determine if a specific user, computer, or session configuration access request is authorized.</span></span> <span data-ttu-id="c3501-148">既定では、パラメーターが追加されていない場合、このコマンドレットはすべての承認規則を評価します。</span><span class="sxs-lookup"><span data-stu-id="c3501-148">By default, if no parameters are added, the cmdlet evaluates all authorization rules.</span></span> <span data-ttu-id="c3501-149">管理者は、パラメーターを追加して、テスト対象の承認規則または規則のサブセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c3501-149">By adding parameters, administrators can specify an authorization rule or a subset of rules to test.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c3501-150">ComputerName</span><span class="sxs-lookup"><span data-stu-id="c3501-150">ComputerName</span></span></p></li>
<li><p><span data-ttu-id="c3501-151">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="c3501-151">ConfigurationName</span></span></p></li>
<li><p><span data-ttu-id="c3501-152">RuleName</span><span class="sxs-lookup"><span data-stu-id="c3501-152">RuleName</span></span></p></li>
<li><p><span data-ttu-id="c3501-153">UserName</span><span class="sxs-lookup"><span data-stu-id="c3501-153">UserName</span></span></p></li>
<li><p><span data-ttu-id="c3501-154">資格情報 (Windows Server 2012 R2 以降)</span><span class="sxs-lookup"><span data-stu-id="c3501-154">Credential (Windows Server 2012 R2 and later)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c3501-155">これらのコマンドレットによって作成されるアクセス規則のセットを使って、Windows PowerShell Web Access ゲートウェイでユーザーを承認できます。</span><span class="sxs-lookup"><span data-stu-id="c3501-155">The preceding cmdlets create a set of access rules which are used to authorize a user on the Windows PowerShell Web Access gateway.</span></span> <span data-ttu-id="c3501-156">これらの規則は、対象コンピューター上のアクセス制御リスト (ACL) とは別に、Web アクセスに対する追加のセキュリティ層として機能します。</span><span class="sxs-lookup"><span data-stu-id="c3501-156">The rules are different from the access control lists (ACLs) on the destination computer, and provide an additional layer of security for web access.</span></span> <span data-ttu-id="c3501-157">以降のセクションでは、セキュリティについてさらに詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="c3501-157">More details about security are described in the following section.</span></span>

<span data-ttu-id="c3501-158">先に説明したセキュリティ層のいずれかを通過できない場合、ユーザーのブラウザー ウィンドウに通常の "アクセス拒否" メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3501-158">If users cannot pass any of the preceding security layers, they receive a generic “access denied” message in their browser windows.</span></span> <span data-ttu-id="c3501-159">ゲートウェイ サーバーには詳細なセキュリティ情報が記録されますが、エンド ユーザーに対しては、通過したセキュリティ層の数や、サインインまたは認証のエラーが発生した具体的な層などの情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="c3501-159">Although security details are logged on the gateway server, end users are not shown information about how many security layers they passed, or at which layer the sign-in or authentication failure occurred.</span></span>

<span data-ttu-id="c3501-160">承認規則の構成方法の詳細については、このトピックの「[承認規則の構成](#BKMK_configrules)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3501-160">For more information about configuring authorization rules, see [Configuring authorization rules](#BKMK_configrules) in this topic.</span></span>

<a href="" id="BKMK_sec"></a>
###

<span data-ttu-id="c3501-161"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">セキュリティ</span></a></span><span class="sxs-lookup"><span data-stu-id="c3501-161"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Security</span></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="c3501-162">Windows PowerShell Web Access のセキュリティ モデルは、Web ベース コンソールのエンド ユーザーと対象コンピューターの間に 4 つの層を構成します。</span><span class="sxs-lookup"><span data-stu-id="c3501-162">The Windows PowerShell Web Access security model has four layers between an end user of the web-based console, and a target computer.</span></span> <span data-ttu-id="c3501-163">Windows PowerShell Web Access 管理者は、IIS マネージャー コンソールで構成を追加することで、セキュリティ層をさらに追加できます。</span><span class="sxs-lookup"><span data-stu-id="c3501-163">Windows PowerShell Web Access administrators can add security layers through additional configuration in the IIS Manager console.</span></span> <span data-ttu-id="c3501-164">IIS マネージャー コンソールで Web サイトを保護する方法の詳細については、「[Configure Web Server Security (IIS 7) (Web サーバーのセキュリティを構成する (IIS 7))](https://technet.microsoft.com/library/cc731278(v=ws.10).aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3501-164">For more information about securing websites in the IIS Manager console, see [Configure Web Server Security (IIS 7)](https://technet.microsoft.com/library/cc731278(v=ws.10).aspx).</span></span> <span data-ttu-id="c3501-165">IIS のベスト プラクティスと、サービス拒否攻撃を阻止する方法の詳細については、[DoS/サービス拒否攻撃阻止のベスト プラクティスに関するページ](https://technet.microsoft.com/library/cc750213.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3501-165">For more information about IIS best practices and preventing denial-of-service attacks, see [Best Practices for Preventing DoS/Denial of Service Attacks](https://technet.microsoft.com/library/cc750213.aspx).</span></span> <span data-ttu-id="c3501-166">管理者は、市販の認証ソフトウェアを購入してインストールすることも可能です。</span><span class="sxs-lookup"><span data-stu-id="c3501-166">An administrator can also buy and install additional, retail authentication software.</span></span>

<span data-ttu-id="c3501-167">エンド ユーザーと対象コンピューターの間に構成される 4 つの層を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="c3501-167">The following table describes the four layers of security between end users and target computers.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c3501-168">順番</span><span class="sxs-lookup"><span data-stu-id="c3501-168">Order</span></span></p></th>
<th><p><span data-ttu-id="c3501-169">層</span><span class="sxs-lookup"><span data-stu-id="c3501-169">Layer</span></span></p></th>
<th><p><span data-ttu-id="c3501-170">説明</span><span class="sxs-lookup"><span data-stu-id="c3501-170">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3501-171">1 で保護されたプロセスとして起動されました</span><span class="sxs-lookup"><span data-stu-id="c3501-171">1</span></span></p></td>
<td><p><span data-ttu-id="c3501-172">Web サーバー (IIS) のセキュリティ機能 (クライアント証明書の認証など)</span><span class="sxs-lookup"><span data-stu-id="c3501-172">Web Server (IIS) security features, such as client certificate authentication</span></span></p></td>
<td><p><span data-ttu-id="c3501-173">Windows PowerShell Web Access のユーザーは、常にゲートウェイでユーザー名とパスワードを入力し、アカウントを認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3501-173">Windows PowerShell Web Access users must always provide a user name and password to authenticate their accounts on the gateway.</span></span> <span data-ttu-id="c3501-174">ただし Windows PowerShell Web Access 管理者は、クライアント証明書による認証をオプションで有効または無効にすることができます (<a href="https://technet.microsoft.com/en-us/library/hh831611(v=ws.11).aspx">Windows PowerShell Web Access のインストールと使用に関するページ</a>の「IIS マネージャーを使って既存の Web サイトにゲートウェイを構成するには」の手順 10. を参照)。</span><span class="sxs-lookup"><span data-stu-id="c3501-174">However, Windows PowerShell Web Access administrators can also turn optional client certificate authentication on or off (see step 10 of “To use IIS Manager to configure the gateway in an existing website” in <a href="https://technet.microsoft.com/en-us/library/hh831611(v=ws.11).aspx">Install and Use Windows PowerShell Web Access</a>).</span></span> <span data-ttu-id="c3501-175">オプションのクライアント証明書機能は、Web サーバー (IIS) 構成の一環として、ユーザー名とパスワードに加えて有効なクライアント証明書の所有をエンド ユーザーに要求します。</span><span class="sxs-lookup"><span data-stu-id="c3501-175">The optional client certificate feature requires end users to have a valid client certificate, in addition to their user names and passwords, and is part of Web Server (IIS) configuration.</span></span> <span data-ttu-id="c3501-176">クライアント証明書の層が有効になっている場合、Windows PowerShell Web Access のサインイン ページは、サインイン資格情報を評価する前に、有効な証明書の提示を求めるメッセージをユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="c3501-176">When the client certificate layer is enabled, the Windows PowerShell Web Access sign-in page prompts users to provide valid certificates before their sign-in credentials are evaluated.</span></span> <span data-ttu-id="c3501-177">クライアント証明書の認証によってクライアント証明書を自動的に確認します。</span><span class="sxs-lookup"><span data-stu-id="c3501-177">Client certificate authentication automatically checks for the client certificate.</span></span></p>
<p><span data-ttu-id="c3501-178">有効な証明書が見つからない場合、Windows PowerShell Web Access は通知を表示し、ここでユーザーは証明書を提示できます。</span><span class="sxs-lookup"><span data-stu-id="c3501-178">If a valid certificate is not found, Windows PowerShell Web Access informs users, so they can provide the certificate.</span></span> <span data-ttu-id="c3501-179">有効な証明書が見つかった場合、Windows PowerShell Web Access はサインイン ページを表示し、ここでユーザーは名前とパスワードを入力できます。</span><span class="sxs-lookup"><span data-stu-id="c3501-179">If a valid client certificate is found, Windows PowerShell Web Access opens the sign-in page for users to provide their user names and passwords.</span></span></p>
<p><span data-ttu-id="c3501-180">これが、Web サーバー (IIS) が提供する追加のセキュリティ設定の 1 つの例です。</span><span class="sxs-lookup"><span data-stu-id="c3501-180">This is one example of additional security settings that are offered by Web Server (IIS).</span></span> <span data-ttu-id="c3501-181">IIS が提供するその他のセキュリティ機能の詳細については、「<a href="https://technet.microsoft.com/library/cc731278(ws.10).aspx">Configure Web Server Security (IIS 7) (Web サーバーのセキュリティを構成する (IIS 7))</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3501-181">For more information about other IIS security features, see <a href="https://technet.microsoft.com/library/cc731278(ws.10).aspx">Configure Web Server Security (IIS 7)</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3501-182">2</span><span class="sxs-lookup"><span data-stu-id="c3501-182">2</span></span></p></td>
<td><p><span data-ttu-id="c3501-183">Windows PowerShell Web Access のフォーム ベースのゲートウェイ認証</span><span class="sxs-lookup"><span data-stu-id="c3501-183">Windows PowerShell Web Access forms-based gateway authentication</span></span></p></td>
<td><p><span data-ttu-id="c3501-184">Windows PowerShell Web Access のサインイン ページは、一連の資格情報 (ユーザー名とパスワード) を要求すると共に、対象コンピューターに対する別の資格情報を提示するためのオプションをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="c3501-184">The Windows PowerShell Web Access sign-in page requires a set of credentials (user name and password) and offers users the option of providing different credentials for the target computer.</span></span> <span data-ttu-id="c3501-185">ユーザーがその他の資格情報を提示しない場合、ゲートウェイへの接続に使われるプライマリのユーザー名とパスワードが、対象コンピューターへの接続にも使われます。</span><span class="sxs-lookup"><span data-stu-id="c3501-185">If the user does not provide alternate credentials, the primary user name and password that are used to connect to the gateway are also used to connect to the target computer.</span></span></p>
<p><span data-ttu-id="c3501-186">要求された資格情報は Windows PowerShell Web Access ゲートウェイで認証されます。</span><span class="sxs-lookup"><span data-stu-id="c3501-186">The required credentials are authenticated on the Windows PowerShell Web Access gateway.</span></span> <span data-ttu-id="c3501-187">これらの資格情報は、ローカルの Windows PowerShell Web Access ゲートウェイ サーバーまたは Active Directory® の有効なユーザー アカウントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3501-187">These credentials must be valid user accounts on either the local Windows PowerShell Web Access gateway server, or in Active Directory®.</span></span></p>
<p><span data-ttu-id="c3501-188">ゲートウェイでユーザーが認証されると、Windows PowerShell Web Access が承認規則を確認して、要求された対象コンピューターへのアクセスがユーザーに許可されているかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="c3501-188">After a user is authenticated at the gateway, Windows PowerShell Web Access checks authorization rules to verify if the user has access to the requested target computer.</span></span> <span data-ttu-id="c3501-189">問題なく承認されると、ユーザーの資格情報が対象コンピューターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="c3501-189">After successful authorization, the user’s credentials are passed along to the target computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3501-190">3</span><span class="sxs-lookup"><span data-stu-id="c3501-190">3</span></span></p></td>
<td><p><span data-ttu-id="c3501-191">Windows PowerShell Web Access の承認規則</span><span class="sxs-lookup"><span data-stu-id="c3501-191">Windows PowerShell Web Access authorization rules</span></span></p></td>
<td><p><span data-ttu-id="c3501-192">ゲートウェイでユーザーが認証されると、Windows PowerShell Web Access が承認規則を確認して、要求された対象コンピューターへのアクセスがユーザーに許可されているかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="c3501-192">After a user is authenticated at the gateway, Windows PowerShell Web Access checks authorization rules to verify if the user has access to the requested target computer.</span></span> <span data-ttu-id="c3501-193">問題なく承認されると、ユーザーの資格情報が対象コンピューターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="c3501-193">After successful authorization, the user’s credentials are passed along to the target computer.</span></span></p>
<p><span data-ttu-id="c3501-194">これらの規則の評価は常にゲートウェイでのユーザー認証の後で実行され、その後、対象コンピューターでユーザー認証を実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c3501-194">These rules are evaluated only after a user has been authenticated by the gateway, and before a user can be authenticated on a target computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3501-195">4</span><span class="sxs-lookup"><span data-stu-id="c3501-195">4</span></span></p></td>
<td><p><span data-ttu-id="c3501-196">対象コンピューターでの認証と承認規則</span><span class="sxs-lookup"><span data-stu-id="c3501-196">Target authentication and authorization rules</span></span></p></td>
<td><p><span data-ttu-id="c3501-197">Windows PowerShell Web Access におけるセキュリティの最後の層は、対象コンピューター独自のセキュリティ構成です。</span><span class="sxs-lookup"><span data-stu-id="c3501-197">The final layer of security for Windows PowerShell Web Access is the target computer’s own security configuration.</span></span> <span data-ttu-id="c3501-198">Windows PowerShell Web Access 経由で対象コンピューターを操作する Windows PowerShell Web ベース コンソールを実行するには、ユーザーは、対象コンピューターと Windows PowerShell Web Access の承認規則でアクセス権を適切に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3501-198">Users must have the appropriate access rights configured on the target computer, and also in the Windows PowerShell Web Access authorization rules, to run a Windows PowerShell web-based console that affects a target computer through Windows PowerShell Web Access.</span></span></p>
<p><span data-ttu-id="c3501-199">この層は、ユーザーが <strong>Enter-PSSession</strong> または <strong>New-PSSession</strong> コマンドレットを実行して Windows PowerShell から対象コンピューターへのリモート Windows PowerShell セッション作成を試みた場合に、試行された接続を評価するのと同じセキュリティ メカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="c3501-199">This layer offers the same security mechanisms that would evaluate connection attempts if users tried to create a remote Windows PowerShell session to a target computer from within Windows PowerShell by running the <strong>Enter-PSSession</strong> or <strong>New-PSSession</strong> cmdlets.</span></span></p>
<p><span data-ttu-id="c3501-200">既定では、Windows PowerShell Web Access は、ゲートウェイと対象コンピューター両方での認証に、プライマリのユーザー名とパスワードを使います。</span><span class="sxs-lookup"><span data-stu-id="c3501-200">By default, Windows PowerShell Web Access uses the primary user name and password for authentication on both the gateway and the target computer.</span></span> <span data-ttu-id="c3501-201">Web ベースのサインイン ページでは、<strong>[オプションの接続設定]</strong> というセクションで、必要に応じて対象コンピューターに対する別の資格情報を提示するためのオプションをユーザーに提供しています。</span><span class="sxs-lookup"><span data-stu-id="c3501-201">The web-based sign-in page, in a section titled <strong>Optional connection settings</strong>, offers users the option of providing different credentials for the target computer, if they are required.</span></span> <span data-ttu-id="c3501-202">ユーザーがその他の資格情報を提示しない場合、ゲートウェイへの接続に使われるプライマリのユーザー名とパスワードが、対象コンピューターへの接続にも使われます。</span><span class="sxs-lookup"><span data-stu-id="c3501-202">If the user does not provide alternate credentials, the primary user name and password that are used to connect to the gateway are also used to connect to the target computer.</span></span></p>
<p><span data-ttu-id="c3501-203">承認規則を使って、特定のセッション構成に対するユーザーのアクセスを許可することができます。</span><span class="sxs-lookup"><span data-stu-id="c3501-203">Authorization rules can be used to allow users access to a particular session configuration.</span></span> <span data-ttu-id="c3501-204">担当者は、Windows PowerShell Web Access 用の制限付き実行空間またはセッション構成を作成し、特定のユーザーが特定のセッション構成だけにアクセスできるようにして、それらのユーザーを Windows PowerShell Web Access にサインインさせることができます。</span><span class="sxs-lookup"><span data-stu-id="c3501-204">You can create restricted runspaces or session configurations for Windows PowerShell Web Access, and allow specific users to connect only to specific session configurations when they sign in to Windows PowerShell Web Access.</span></span> <span data-ttu-id="c3501-205">アクセス制御リスト (ACL) を使って特定のエンドポイントにアクセスできるユーザーを決定できることに加えて、このセクションで説明する承認規則を使用すると、エンドポイントへのアクセスを特定のユーザーにさらに制限することができます。</span><span class="sxs-lookup"><span data-stu-id="c3501-205">You can use access control lists (ACLs) to determine which users have access to specific endpoints, and further restrict access to the endpoint for a specific set of users by using authorization rules described in this section.</span></span> <span data-ttu-id="c3501-206">制限付き実行空間の詳細については、MSDN の<a href="https://msdn.microsoft.com/library/windows/desktop/ee706589.aspx">制約付き実行空間に関するページ</a>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3501-206">For more information about restricted runspaces, see <a href="https://msdn.microsoft.com/library/windows/desktop/ee706589.aspx">Constrained Runspaces</a> on MSDN.</span></span></p></td>
</tr>
</tbody>
</table><span data-ttu-id="c3501-207">

<a href="" id="BKMK_configrules"></a>
###

<a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">承認規則の構成</span></a></span><span class="sxs-lookup"><span data-stu-id="c3501-207">

<a href="" id="BKMK_configrules"></a>
###

<a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Configuring authorization rules</span></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="c3501-208">多くの場合、管理者が Windows PowerShell Web Access ユーザー用に必要とする承認規則は、環境内で Windows PowerShell のリモート管理用に定義されているものと同じになります。</span><span class="sxs-lookup"><span data-stu-id="c3501-208">Administrators likely want the same authorization rule for Windows PowerShell Web Access users that is already defined in their environment for Windows PowerShell remote management.</span></span> <span data-ttu-id="c3501-209">このセクションの最初の手順では、安全な承認規則を追加することによって、サインインして 1 つのセッション構成で 1 つのコンピューターを管理するためのアクセスを、ユーザー 1 人に許可する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="c3501-209">The first procedure in this section describes how to add a secure authorization rule that grants access to one user, signing in to manage one computer, and within a single session configuration.</span></span> <span data-ttu-id="c3501-210">2 つ目の手順では、不要になった承認規則を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3501-210">The second procedure describes how to remove an authorization rule that is no longer needed.</span></span>

<span data-ttu-id="c3501-211">カスタム セッション構成を使用することで、特定のユーザーに対して Windows PowerShell Web Access の制限付き実行空間内でのみ作業することを許可する場合、カスタム セッション構成は、これらが参照される承認規則を追加する前に作成してください。</span><span class="sxs-lookup"><span data-stu-id="c3501-211">If you plan to use custom session configurations to allow specific users to work only within restricted runspaces in Windows PowerShell Web Access, create your custom session configurations before you add authorization rules that refer to them.</span></span> <span data-ttu-id="c3501-212">Windows PowerShell Web Access コマンドレットを使用してカスタム セッション構成を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="c3501-212">You cannot use the Windows PowerShell Web Access cmdlets to create custom session configurations.</span></span> <span data-ttu-id="c3501-213">カスタム セッション構成の作成方法の詳細については、MSDN サイトの「[about_Session_Configuration_Files](https://msdn.microsoft.com/library/windows/desktop/hh847838.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3501-213">For more information about creating custom session configurations, see [about_Session_Configuration_Files](https://msdn.microsoft.com/library/windows/desktop/hh847838.aspx) on MSDN.</span></span>

<span data-ttu-id="c3501-214">Windows PowerShell Web Access コマンドレットは、ワイルドカード文字、アスタリスク(\*) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c3501-214">Windows PowerShell Web Access cmdlets support one wildcard character, an asterisk ( \* ).</span></span> <span data-ttu-id="c3501-215">文字列内のワイルドカード文字はサポートされていません。アスタリスクは、プロパティ (ユーザー、コンピューター、セッション構成) ごとに 1 つ使うことができます。</span><span class="sxs-lookup"><span data-stu-id="c3501-215">Wildcard characters within strings are not supported; use a single asterisk per property (users, computers, or session configurations).</span></span>

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3501-216"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">注意</span></span><span class="sxs-lookup"><span data-stu-id="c3501-216"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">Note </span></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3501-217">承認規則を使ってユーザーのアクセスを許可し Windows PowerShell Web Access 環境のセキュリティ保護を実現するその他のさまざまな方法については、このトピックの「<a href="#BKMK_others">承認規則のその他のシナリオの例</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3501-217">For more ways you can use authorization rules to grant access to users and help secure the Windows PowerShell Web Access environment, see <a href="#BKMK_others">Other authorization rule scenario examples</a> in this topic.</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="to-add-a-restrictive-authorization-rule"></a><span data-ttu-id="c3501-218">制限的な承認規則を追加するには</span><span class="sxs-lookup"><span data-stu-id="c3501-218">To add a restrictive authorization rule</span></span>

1.  <span data-ttu-id="c3501-219">次のいずれかを実行して、管理者特権を使って Windows PowerShell セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="c3501-219">Do one of the following to open a Windows PowerShell session with elevated user rights.</span></span>

    -   <span data-ttu-id="c3501-220">Windows デスクトップで、タスク バーの **[Windows PowerShell]** を右クリックし、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3501-220">On the Windows desktop, right-click **Windows PowerShell** on the taskbar, and then click **Run as Administrator**.</span></span>

    -   <span data-ttu-id="c3501-221">Windows の**スタート**画面で、**[Windows PowerShell]** を右クリックし、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3501-221">On the Windows **Start** screen, right-click **Windows PowerShell**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="c3501-222"><span class="label">セッション構成を使用してユーザー アクセスを制限するためのオプション手順:</span> 規則内で使用するセッション構成が既に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3501-222"><span class="label">Optional step for restricting user access by using session configurations:</span> Verify that session configurations that you want to use in your rules already exist.</span></span> <span data-ttu-id="c3501-223">まだ作成されていない場合は、MSDN の「[about_Session_Configuration_Files](https://msdn.microsoft.com/library/windows/desktop/hh847838.aspx)」に記載されているセッション構成の作成手順を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c3501-223">If they have not yet been created, use instructions for creating session configurations in [about_Session_Configuration_Files](https://msdn.microsoft.com/library/windows/desktop/hh847838.aspx) on MSDN.</span></span>

3.  <span data-ttu-id="c3501-224">次のように入力して **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c3501-224">Type the following, and then press **Enter**.</span></span>

    [<span data-ttu-id="c3501-225">Copy</span><span class="sxs-lookup"><span data-stu-id="c3501-225">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_1079478f-cd51-4d35-8022-4b532a9d57a4'); "Copy to clipboard.")

        Add-PswaAuthorizationRule -UserName <domain\user | computer\user> -ComputerName <computer_name> -ConfigurationName <session_configuration_name>

    <span data-ttu-id="c3501-226">この承認規則により、特定のユーザー 1 人が、通常アクセスが許可されているネットワーク上の 1 つのコンピューターにアクセスして、このユーザーが通常必要とするスクリプトとコマンドレットに制限された特定の 1 つのセッション構成にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="c3501-226">This authorization rule allows a specific user access to one computer on the network to which they typically have access, with access to a specific session configuration that is scoped to the user’s typical scripting and cmdlet needs.</span></span> <span data-ttu-id="c3501-227">次の例では、<span class="code">Contoso</span> ドメインの <span class="code">JSmith</span> というユーザーに、<span class="code">Contoso_214</span> というコンピューターを管理し、<span class="code">NewAdminsOnly</span> というセッション構成を使うためのアクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="c3501-227">In the following example, a user named <span class="code">JSmith</span> in the <span class="code">Contoso</span> domain is granted access to manage the computer <span class="code">Contoso_214</span>, and use a session configuration named <span class="code">NewAdminsOnly</span>.</span></span>

    [<span data-ttu-id="c3501-228">Copy</span><span class="sxs-lookup"><span data-stu-id="c3501-228">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_4e760377-e401-4ef4-988f-7a0aec1b2a90'); "Copy to clipboard.")

        Add-PswaAuthorizationRule -UserName Contoso\JSmith -ComputerName Contoso_214 -ConfigurationName NewAdminsOnly

4.  <span data-ttu-id="c3501-229">**Get-PswaAuthorizationRule** コマンドレットまたは **Test-PswaAuthorizationRule -UserName &lt;domain\\user | computer\\user&gt; -ComputerName** &lt;computer_name&gt; を実行して、規則が作成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3501-229">Verify that the rule has been created by running either the **Get-PswaAuthorizationRule** cmdlet, or **Test-PswaAuthorizationRule -UserName &lt;domain\\user | computer\\user&gt; -ComputerName** &lt;computer_name&gt;.</span></span> <span data-ttu-id="c3501-230">例: **Test-PswaAuthorizationRule -UserName Contoso\\JSmith -ComputerName Contoso_214**。</span><span class="sxs-lookup"><span data-stu-id="c3501-230">For example, **Test-PswaAuthorizationRule -UserName Contoso\\JSmith -ComputerName Contoso_214**.</span></span>

#### <a name="to-remove-an-authorization-rule"></a><span data-ttu-id="c3501-231">承認規則を削除するには</span><span class="sxs-lookup"><span data-stu-id="c3501-231">To remove an authorization rule</span></span>

1.  <span data-ttu-id="c3501-232">Windows PowerShell セッションが開かれていない場合は、このセクションの[非制限的な承認規則を追加する方法](#BKMK_arar)の手順 1. を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3501-232">If a Windows PowerShell session is not already open, see step 1 of [To add a restrictive authorization rule](#BKMK_arar) in this section.</span></span>

2.  <span data-ttu-id="c3501-233">次のように入力して **Enter** キーを押します。*rule ID* には削除する規則の一意の ID 番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3501-233">Type the following, and then press **Enter**, where *rule ID* represents the unique ID number of the rule that you want to remove.</span></span>

    [<span data-ttu-id="c3501-234">Copy</span><span class="sxs-lookup"><span data-stu-id="c3501-234">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_0daef66d-0ecf-47fb-a8a0-d4dbceb8409d'); "Copy to clipboard.")

        Remove-PswaAuthorizationRule -ID <rule ID>

    <span data-ttu-id="c3501-235">または、削除する規則の ID 番号を知らないがフレンドリ名は知っている場合、規則の名前を取得し、パイプ処理によって名前を <span class="code">Remove-PswaAuthorizationRule</span> コマンドレットに渡すことによって、規則を削除できます。次の例を参照してください: Get-PswaAuthorizationRule -RuleName &lt;*ルール名*&gt; | Remove-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="c3501-235">Alternatively, if you do not know the ID number, but know the friendly name of the rule you want to remove, you can get the name of the rule, and pipe it to the <span class="code">Remove-PswaAuthorizationRule</span> cmdlet to remove the rule, as shown in the following example: Get-PswaAuthorizationRule -RuleName &lt;*rule name*&gt; | Remove-PswaAuthorizationRule.</span></span>

    <table>
    <colgroup>
    <col width="100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="c3501-236"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">注意</span></span><span class="sxs-lookup"><span data-stu-id="c3501-236"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">Note </span></span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="c3501-237">指定した承認規則を削除するかどうかを確認するメッセージは表示されず、<strong>Enter</strong> キーを押すと規則が削除されます。</span><span class="sxs-lookup"><span data-stu-id="c3501-237">You are not prompted to confirm whether you want to delete the specified authorization rule; the rule is deleted when you press <strong>Enter</strong>.</span></span> <span data-ttu-id="c3501-238"><strong>Remove-PswaAuthorizationRule</strong> コマンドレットを実行する前に、削除する承認規則が正しいことを必ず確認してください。</span><span class="sxs-lookup"><span data-stu-id="c3501-238">Be sure that you want to remove the authorization rule before running the <strong>Remove-PswaAuthorizationRule</strong> cmdlet.</span></span></p></td>
    </tr>
    </tbody>
    </table><span data-ttu-id="c3501-239">

<a href="" id="BKMK_others"></a>
####

<a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">承認規則のその他のシナリオの例</span></a></span><span class="sxs-lookup"><span data-stu-id="c3501-239">

<a href="" id="BKMK_others"></a>
####

<a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Other authorization rule scenario examples</span></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="c3501-240">あらゆる Windows PowerShell セッションはいずれかのセッション構成を使います。セッションにセッション構成が指定されていない場合、Windows PowerShell は、組み込み済みの Windows PowerShell セッション構成である Microsoft.PowerShell という既定値を使います。</span><span class="sxs-lookup"><span data-stu-id="c3501-240">Every Windows PowerShell session uses a session configuration; if one is not specified for a session, Windows PowerShell uses the default, built-in Windows PowerShell session configuration, called Microsoft.PowerShell.</span></span> <span data-ttu-id="c3501-241">既定のセッション構成には、コンピューターで使うことができるすべてのコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3501-241">The default session configuration includes all cmdlets that are available on a computer.</span></span> <span data-ttu-id="c3501-242">管理者は、制限付き実行空間 (エンド ユーザーが実行できるコマンドレットとタスクの範囲が制限されている) が指定されたセッション構成を定義することで、すべてのコンピューターに対するアクセスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="c3501-242">Administrators can restrict access to all computers by defining a session configuration with a restricted runspace (a limited range of cmdlets and tasks that their end users could perform).</span></span> <span data-ttu-id="c3501-243">1 つのコンピューターに対する全言語でのアクセス、または Windows PowerShell リモート管理コマンドレットだけに対するアクセスを許可されているユーザーは、最初の対象コンピューターに接続されているその他のコンピューターに接続できます。</span><span class="sxs-lookup"><span data-stu-id="c3501-243">A user who is granted access to one computer with either full language access or only the Windows PowerShell remote management cmdlets can connect to other computers that are connected to the first computer.</span></span> <span data-ttu-id="c3501-244">制限付き実行空間を定義することで、許可されている Windows PowerShell 実行空間から他のコンピューターへのユーザー アクセスを阻止し、Windows PowerShell Web Access 環境のセキュリティを強化できます。</span><span class="sxs-lookup"><span data-stu-id="c3501-244">Defining a restricted runspace can prevent users from accessing other computers from their allowed Windows PowerShell runspace, and improves the security of your Windows PowerShell Web Access environment.</span></span> <span data-ttu-id="c3501-245">セッション構成は、Windows PowerShell Web Access からアクセス可能な状態にすると管理者が判断したすべてのコンピューターに (グループ ポリシーを使って) 配布できます。</span><span class="sxs-lookup"><span data-stu-id="c3501-245">The session configuration can be distributed (by using Group Policy) to all computers that administrators want to make accessible through Windows PowerShell Web Access.</span></span> <span data-ttu-id="c3501-246">セッション構成の詳細については、「[about_Session_Configurations](https://technet.microsoft.com/library/dd819508.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3501-246">For more information about session configurations, see [about_Session_Configurations](https://technet.microsoft.com/library/dd819508.aspx).</span></span> <span data-ttu-id="c3501-247">次に、シナリオの例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="c3501-247">The following are some examples of this scenario.</span></span>

-   <span data-ttu-id="c3501-248">管理者が、制限付き実行空間を指定して、**PswaEndpoint** というエンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3501-248">An administrator creates an endpoint, called **PswaEndpoint**, with a restricted runspace.</span></span> <span data-ttu-id="c3501-249">その後管理者が **\*,\*,PswaEndpoint** という規則を作成し、このエンドポイントをその他のコンピューターに配布します。</span><span class="sxs-lookup"><span data-stu-id="c3501-249">Then, the administrator creates a rule, **\*,\*,PswaEndpoint**, and distributes the endpoint to other computers.</span></span> <span data-ttu-id="c3501-250">この規則によって、エンドポイント **PswaEndpoint** を持つすべてのコンピューターにすべてのユーザーがアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="c3501-250">The rule allows all users to access all computers with the endpoint **PswaEndpoint**.</span></span> <span data-ttu-id="c3501-251">規則セットにこの承認規則だけ定義されている場合、このエンドポイントを持たないコンピューターにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="c3501-251">If this is the only authorization rule defined in the rule set, computers without that endpoint would not be accessible.</span></span>

-   <span data-ttu-id="c3501-252">制限付き実行空間を指定して **PswaEndpoint** というエンドポイントを作成した後は、アクセスを特定のユーザーに制限します。</span><span class="sxs-lookup"><span data-stu-id="c3501-252">The administrator created an endpoint with a restricted runspace called **PswaEndpoint**,and wants to restrict access to specific users.</span></span> <span data-ttu-id="c3501-253">管理者は **Level1Support** というユーザー グループを作成し、**Level1Support,\*,PswaEndpoint** という規則を定義します。</span><span class="sxs-lookup"><span data-stu-id="c3501-253">The administrator creates a group of users called **Level1Support**, and defines the following rule: **Level1Support,\*,PswaEndpoint**.</span></span> <span data-ttu-id="c3501-254">この規則によって、**Level1Support** グループのすべてのユーザーが、**PswaEndpoint** 構成を持つコンピューターにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="c3501-254">The rule grants any users in the group **Level1Support** access to all computers with the **PswaEndpoint** configuration.</span></span> <span data-ttu-id="c3501-255">同様に、アクセスを特定のコンピューターに制限することも可能です。</span><span class="sxs-lookup"><span data-stu-id="c3501-255">Similarly, access can be restricted to a specific set of computers.</span></span>

-   <span data-ttu-id="c3501-256">管理者は、その他のユーザーよりも権限の強いアクセスを特定のユーザーに許可することができます。</span><span class="sxs-lookup"><span data-stu-id="c3501-256">Some administrators provide certain users more access than others.</span></span> <span data-ttu-id="c3501-257">たとえば、管理者が、**Admins** と **BasicSupport** という 2 つのユーザー グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3501-257">For example, an administrator creates two user groups, **Admins** and **BasicSupport**.</span></span> <span data-ttu-id="c3501-258">管理者はさらに、制限付き実行空間を指定して **PswaEndpoint** というエンドポイントを作成し、**Admins,\*,\*** と **BasicSupport,\*,PswaEndpoint** という 2 つの規則を定義します。</span><span class="sxs-lookup"><span data-stu-id="c3501-258">The administrator also creates an endpoint with a restricted runspace called **PswaEndpoint**, and defines the following two rules: **Admins,\*,\*** and **BasicSupport,\*,PswaEndpoint**.</span></span> <span data-ttu-id="c3501-259">最初の規則は、**Admin** グループのすべてのユーザーにすべてのコンピューターへのアクセスを許可します。2 つ目の規則は、**BasicSupport** グループに、**PswaEndpoint** を持つコンピューターだけに対するアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="c3501-259">The first rule provides all users in the **Admin** group access to all computers, and the second rule provides all users in the **BasicSupport** group access only to those computers with **PswaEndpoint**.</span></span>

-   <span data-ttu-id="c3501-260">管理者がプライベートなテスト環境をセットアップして、すべての承認済みネットワーク ユーザーに、通常アクセスが許可されるネットワーク内のすべてのコンピューターに対するアクセスと、通常アクセスが許可されるすべてのセッション構成に対するアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="c3501-260">An administrator has set up a private test environment, and wants to allow all authorized network users access to all computers on the network to which they typically have access, with access to all session configurations to which they typically have access.</span></span> <span data-ttu-id="c3501-261">これはプライベートなテスト環境であるため、管理者が作成する承認規則は安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="c3501-261">Because this is a private test environment, the administrator creates an authorization rule that is not secure.</span></span> <span data-ttu-id="c3501-262">管理者が <span class="code">Add-PswaAuthorizationRule \* \* \* </span> コマンドレットを実行します。ここで使われているワイルドカード文字 **\*** は、すべてのコンピューター、すべてのユーザー、すべてのセッション構成をそれぞれ示します。</span><span class="sxs-lookup"><span data-stu-id="c3501-262">The administrator runs the cmdlet <span class="code">Add-PswaAuthorizationRule \* \* \*</span>, which uses the wildcard character **\*** to represent all users, all computers, and all configurations.</span></span> <span data-ttu-id="c3501-263">この規則は、<span class="code">Add-PswaAuthorizationRule -UserName \* -ComputerName \* -ConfigurationName \*</span> と同等です。</span><span class="sxs-lookup"><span data-stu-id="c3501-263">This rule is the equivalent of the following: <span class="code">Add-PswaAuthorizationRule -UserName \* -ComputerName \* -ConfigurationName \*</span>.</span></span>

    <table>
    <colgroup>
    <col width="100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="c3501-264"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC17938.jpeg" title="System_CAPS_security" alt="System_CAPS_security" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-security" /></span><span class="alertTitle">セキュリティ メモ</span></span><span class="sxs-lookup"><span data-stu-id="c3501-264"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC17938.jpeg" title="System_CAPS_security" alt="System_CAPS_security" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-security" /></span><span class="alertTitle"> Security Note </span></span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="c3501-265">この規則は、Windows PowerShell Web Access が提供する承認規則によるセキュリティ層をバイパスするものであり、セキュリティ保護された環境には推奨されません。</span><span class="sxs-lookup"><span data-stu-id="c3501-265">This rule is not recommended in a secure environment, and bypasses the authorization rule layer of security provided by Windows PowerShell Web Access.</span></span></p></td>
    </tr>
    </tbody>
    </table>

-   <span data-ttu-id="c3501-266">管理者は、ワークグループとドメインの両方が含まれている環境で、対象コンピューターへの接続をユーザーに許可する必要があります。ワークグループ コンピューターは、ドメイン内の対象コンピューターに接続するために使用されることがあります。ドメイン内のコンピューターは、ワークグループ内の対象コンピューターに接続するために使用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="c3501-266">An administrator must allow users to connect to target computers in an environment that includes both workgroups and domains, where workgroup computers are occasionally used to connect to target computers in domains, and computers in domains are occasionally used to connect to target computers in workgroups.</span></span> <span data-ttu-id="c3501-267">ワークグループ内にはゲートウェイ サーバー *PswaServer* があり、ドメイン内には対象コンピューター *srv1.contoso.com* があります。</span><span class="sxs-lookup"><span data-stu-id="c3501-267">The administrator has a gateway server, *PswaServer*, in a workgroup; and target computer *srv1.contoso.com* is in a domain.</span></span> <span data-ttu-id="c3501-268">ユーザー *Chris* は、ワークグループ ゲートウェイ サーバーと対象コンピューターの両方で承認されているローカル ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="c3501-268">User *Chris* is an authorized local user on both the workgroup gateway server and the target computer.</span></span> <span data-ttu-id="c3501-269">ワークグループ サーバー上のユーザー名は *chrisLocal*、対象コンピューター上のユーザー名は *contoso\\chris* です。</span><span class="sxs-lookup"><span data-stu-id="c3501-269">His user name on the workgroup server is *chrisLocal*; and his user name on the target computer is *contoso\\chris*.</span></span> <span data-ttu-id="c3501-270">Chris に srv1.contoso.com へのアクセスを承認するには、管理者は以下の規則を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3501-270">To authorize access to srv1.contoso.com for Chris, the administrator adds the following rule.</span></span>

    [<span data-ttu-id="c3501-271">Copy</span><span class="sxs-lookup"><span data-stu-id="c3501-271">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_8d183d3d-1c19-44b8-9297-530b0efc7c79'); "Copy to clipboard.")

        Add-PswaAuthorizationRule -userName PswaServer\chrisLocal -computerName srv1.contoso.com -configurationName Microsoft.PowerShell

    <span data-ttu-id="c3501-272">この規則例では、Chris がゲートウェイ サーバーで認証され、Chris による *srv1* へのアクセスが承認されます。</span><span class="sxs-lookup"><span data-stu-id="c3501-272">The preceding rule example authenticates Chris on the gateway server, and then authorizes his access to *srv1*.</span></span> <span data-ttu-id="c3501-273">サインイン ページで、Chris は 2 番目の資格情報 (*contoso\\chris*) を **[オプションの接続設定]** に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3501-273">On the sign-in page, Chris must provide a second set of credentials in the **Optional connection settings** area (*contoso\\chris*).</span></span> <span data-ttu-id="c3501-274">ゲートウェイ サーバーでは、対象コンピューター (*srv1.contoso.com*) で Chris を認証するために、追加の資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3501-274">The gateway server uses the additional set of credentials to authenticate him on the target computer, *srv1.contoso.com*.</span></span>

    <span data-ttu-id="c3501-275">このシナリオでは、Windows PowerShell Web Access が対象コンピューターへの接続に成功するのは、次の動作に成功し、1 つ以上の承認規則で許可された場合のみです。</span><span class="sxs-lookup"><span data-stu-id="c3501-275">In the preceding scenario, Windows PowerShell Web Access establishes a successful connection to the target computer only after the following have been successful, and allowed by at least one authorization rule.</span></span>

    1.  <span data-ttu-id="c3501-276">*server_name*\\*user_name* の形式のユーザー名を承認規則に追加することによる、ワークグループ ゲートウェイ サーバーでの認証</span><span class="sxs-lookup"><span data-stu-id="c3501-276">Authentication on the workgroup gateway server by adding a user name in the format *server_name*\\*user_name* to the authorization rule</span></span>

    2.  <span data-ttu-id="c3501-277">サインイン ページの **[オプションの接続設定]** で指定された別の資格情報を使用することによる、対象コンピューターでの認証</span><span class="sxs-lookup"><span data-stu-id="c3501-277">Authentication on the target computer by using alternate credentials provided on the sign-in page, in the **Optional connection settings** area</span></span>

    <table>
    <colgroup>
    <col width="100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="c3501-278"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">注意</span></span><span class="sxs-lookup"><span data-stu-id="c3501-278"><span><img src="https://i-technet.sec.s-msft.com/dynimg/IC101471.jpeg" title="System_CAPS_note" alt="System_CAPS_note" id="s-e6f6a65cf14f462597b64ac058dbe1d0-system-media-system-caps-note" /></span><span class="alertTitle">Note </span></span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="c3501-279">ゲートウェイ コンピューターと対象コンピューターが別々のワークグループまたはドメインにある場合は、2 つのワークグループ コンピューター間、2 つのドメイン間、またはワークグループとドメインの間で、信頼関係を確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3501-279">If gateway and target computers are in different workgroups or domains, a trust relationship must be established between the two workgroup computers, the two domains, or between the workgroup and the domain.</span></span> <span data-ttu-id="c3501-280">Windows PowerShell Web Access の承認規則コマンドレットを使用してこの関係を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="c3501-280">This relationship cannot be configured by using Windows PowerShell Web Access authorization rule cmdlets.</span></span> <span data-ttu-id="c3501-281">承認規則では、コンピューター間の信頼関係は定義されません。承認規則では、特定の対象コンピューターとセッション構成に接続できるようにユーザーを承認することしかできません。</span><span class="sxs-lookup"><span data-stu-id="c3501-281">Authorization rules do not define a trust relationship between computers; they can only authorize users to connect to specific target computers and session configurations.</span></span> <span data-ttu-id="c3501-282">異なるドメイン間で信頼関係を構成する方法の詳細については、<a href="https://technet.microsoft.com/library/cc794775.aspx">ドメインおよびフォレストの信頼の作成に関するページ</a>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3501-282">For more information about how to configure a trust relationship between different domains, see <a href="https://technet.microsoft.com/library/cc794775.aspx">Creating Domain and Forest Trusts</a>.</span></span> <span data-ttu-id="c3501-283">信頼されたホストの一覧にワークグループ コンピューターを追加する方法の詳細については、「<a href="https://technet.microsoft.com/library/dd759202.aspx">サーバー マネージャーによるリモート管理</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3501-283">For more information about how to add workgroup computers to a trusted hosts list, see <a href="https://technet.microsoft.com/library/dd759202.aspx">Remote Management with Server Manager</a>.</span></span></p></td>
    </tr>
    </tbody>
    </table>

###

<span data-ttu-id="c3501-284"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">複数サイトでの 1 セットの承認規則の使用</span></a></span><span class="sxs-lookup"><span data-stu-id="c3501-284"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Using a single set of authorization rules for multiple sites</span></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="c3501-285">承認規則は 1 つの XML ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="c3501-285">Authorization rules are stored in an XML file.</span></span> <span data-ttu-id="c3501-286">既定では、この XML ファイルのパス名は %windir%\\Web\\PowershellWebAccess\\data\\AuthorizationRules.xml です。</span><span class="sxs-lookup"><span data-stu-id="c3501-286">By default, the path name of the XML file is %windir%\\Web\\PowershellWebAccess\\data\\AuthorizationRules.xml.</span></span>

<span data-ttu-id="c3501-287">承認規則 XML ファイルのパスは、**powwa.config** ファイルに格納されます。このファイルは %windir%\\Web\\PowershellWebAccess\\data にあります。</span><span class="sxs-lookup"><span data-stu-id="c3501-287">The path to the authorization rules XML file is stored in the **powwa.config** file, which is found in %windir%\\Web\\PowershellWebAccess\\data.</span></span> <span data-ttu-id="c3501-288">管理者は、**powwa.config** に記述されている既定パスへの参照を、設定や要件に合わせて柔軟に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="c3501-288">The administrator has the flexibility to change the reference to the default path in **powwa.config** to suit preferences or requirements.</span></span> <span data-ttu-id="c3501-289">管理者がファイルの場所を変更できるので、構成上の必要に応じて、複数の Windows PowerShell Web Access ゲートウェイが同じ承認規則を使うことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="c3501-289">Allowing the administrator to change the location of the file lets multiple Windows PowerShell Web Access gateways use the same authorization rules, if such a configuration is desired.</span></span>

<a href="" id="BKMK_sesmgmt"></a>

<span data-ttu-id="c3501-290"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">セッションの管理</span></a>
<a href="/en-us/library/dn282394(v=ws.11).aspx#Anchor_1" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="c3501-290"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Session management</span></a>
<a href="/en-us/library/dn282394(v=ws.11).aspx#Anchor_1" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="c3501-291">Windows PowerShell Web Access では、ユーザーが同時に接続できるセッションは既定で 3 つまでに制限されています。</span><span class="sxs-lookup"><span data-stu-id="c3501-291">By default, Windows PowerShell Web Access limits a user to three sessions at one time.</span></span> <span data-ttu-id="c3501-292">Web アプリケーションの **web.config** ファイルを IIS マネージャーで編集することで、ユーザーごとにサポートされるセッションの数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c3501-292">You can edit the web application’s **web.config** file in IIS Manager to support a different number of sessions per user.</span></span> <span data-ttu-id="c3501-293">**web.config** ファイルのパスは $Env:Windir\\Web\\PowerShellWebAccess\\wwwroot\\Web.config です。</span><span class="sxs-lookup"><span data-stu-id="c3501-293">The path to the **web.config** file is $Env:Windir\\Web\\PowerShellWebAccess\\wwwroot\\Web.config.</span></span>

<span data-ttu-id="c3501-294">何らかの設定が編集された場合、Web サーバーの既定の構成によってアプリケーション プールが再起動します。</span><span class="sxs-lookup"><span data-stu-id="c3501-294">By default, Web Server (IIS) is configured to restart the application pool if any settings are edited.</span></span> <span data-ttu-id="c3501-295">たとえば **web.config** ファイルが編集された場合、アプリケーション プールが再起動します。</span><span class="sxs-lookup"><span data-stu-id="c3501-295">For example, the application pool is restarted if changes are made to the **web.config** file.</span></span> <span data-ttu-id="c3501-296">Windows PowerShell Web Access はインメモリ セッション状態を使うため、アプリケーション プールの再起動によって、Windows PowerShell Web Access セッションにサインインしているユーザーのセッションは切断されます。</span><span class="sxs-lookup"><span data-stu-id="c3501-296">Because Windows PowerShell Web Access uses in-memory session states, users signed in to Windows PowerShell Web Access sessions lose their sessions when the application pool is restarted.</span></span>

###

<span data-ttu-id="c3501-297"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">サインイン ページに既定のパラメーターを設定する</span></a></span><span class="sxs-lookup"><span data-stu-id="c3501-297"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Setting default parameters on the sign-in page</span></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="c3501-298">Windows PowerShell Web Access ゲートウェイを Windows Server 2012 R2 で実行する場合、Windows PowerShell Web Access サインイン ページに表示される設定に既定の値を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c3501-298">If your Windows PowerShell Web Access gateway is running on Windows Server 2012 R2, you can configure default values for the settings that are displayed on the Windows PowerShell Web Access sign-in page.</span></span> <span data-ttu-id="c3501-299">前の段落で説明されている **web.config** ファイルに値を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c3501-299">You can configure values in the **web.config** file that is described in the preceding paragraph.</span></span> <span data-ttu-id="c3501-300">サインイン ページの設定の既定値は、web.config ファイルの **appSettings** セクションにあります。**appSettings** セクションの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c3501-300">Default values for the sign-in page settings are found in the **appSettings** section of the web.config file; the following is an example of the **appSettings** section.</span></span> <span data-ttu-id="c3501-301">これらの設定の多くに有効な値は、Windows PowerShell の [New-PSSession](https://technet.microsoft.com/library/hh849717.aspx) コマンドレットの対応するパラメーターのものと同じです。</span><span class="sxs-lookup"><span data-stu-id="c3501-301">Valid values for many of these settings are the same as those for the corresponding parameters of the [New-PSSession](https://technet.microsoft.com/library/hh849717.aspx) cmdlet in Windows PowerShell.</span></span> <span data-ttu-id="c3501-302">たとえば、次のコード ブロックに示された <span class="code">defaultApplicationName</span> キーは、ターゲット コンピューター上の **$PSSessionApplicationName** ユーザー設定変数の値になります。</span><span class="sxs-lookup"><span data-stu-id="c3501-302">For example, the <span class="code">defaultApplicationName</span> key, as shown in the following code block, is the value of the **$PSSessionApplicationName** preference variable on the target computer.</span></span>

[<span data-ttu-id="c3501-303">Copy</span><span class="sxs-lookup"><span data-stu-id="c3501-303">Copy</span></span>](javascript:if%20(window.epx.codeSnippet)window.epx.codeSnippet.copyCode('CodeSnippetContainerCode_6ccfd0a1-485a-4ac5-9636-89ebab501bef'); "Copy to clipboard.")

    <appSettings>
            <add key="maxSessionsAllowedPerUser" value="3"/>
            <add key="defaultPortNumber" value="5985"/>
            <add key="defaultSSLPortNumber" value="5986"/>
            <add key="defaultApplicationName" value="WSMAN"/>
            <add key="defaultUseSslSelection" value="0"/>
            <add key="defaultAuthenticationType" value="0"/>
            <add key="defaultAllowRedirection" value="0"/>
            <add key="defaultConfigurationName" value="Microsoft.PowerShell"/>
    </appSettings>

###

<span data-ttu-id="c3501-304"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">タイムアウトと計画外の切断</span></a></span><span class="sxs-lookup"><span data-stu-id="c3501-304"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">Time-outs and unplanned disconnections</span></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="c3501-305">Windows PowerShell Web Access セッションではタイムアウトが発生します。</span><span class="sxs-lookup"><span data-stu-id="c3501-305">Windows PowerShell Web Access sessions time out.</span></span> <span data-ttu-id="c3501-306">Windows Server 2012 で実行する Windows PowerShell Web Access では、非アクティブな状態が 15 分続くと、セッションのタイムアウト メッセージがサインインしているユーザーに対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3501-306">In Windows PowerShell Web Access running on Windows Server 2012, A time-out message is displayed to signed-in users after 15 minutes of session inactivity.</span></span> <span data-ttu-id="c3501-307">タイムアウト メッセージが表示されてから 5 分以内にユーザーの応答がない場合、セッションが終了しユーザーがサインアウトされます。</span><span class="sxs-lookup"><span data-stu-id="c3501-307">If the user does not respond within five minutes after the time-out message is displayed, the session is ended, and the user is signed out.</span></span> <span data-ttu-id="c3501-308">セッションのタイムアウト時間は、IIS マネージャーの Web サイト設定で変更できます。</span><span class="sxs-lookup"><span data-stu-id="c3501-308">You can change time-out periods for sessions in the website settings in IIS Manager.</span></span>

<span data-ttu-id="c3501-309">Windows Server 2012 R2 で実行する Windows PowerShell Web Access では、非アクティブな状態が 20 分続くと、セッションは既定でタイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="c3501-309">In Windows PowerShell Web Access running on Windows Server 2012 R2, sessions time out, by default, after 20 minutes of inactivity.</span></span> <span data-ttu-id="c3501-310">ユーザー自身がセッションを閉じたためではなく、ネットワーク エラーまたはその他の予期しないシャットダウンや障害のために、ユーザーがセッションから切断された場合、クライアント側でタイムアウト期間が経過するまで、Windows PowerShell Web Access セッションは実行を続け、ターゲット コンピューターに接続されたままになります。</span><span class="sxs-lookup"><span data-stu-id="c3501-310">If users are disconnected from sessions in the web-based console because of network errors or other unplanned shutdowns or failures, and not because they have closed the sessions themselves, the Windows PowerShell Web Access sessions continue to run, connected to target computers, until the time-out period on the client side lapses.</span></span> <span data-ttu-id="c3501-311">既定の 20 分またはゲートウェイ管理者が指定したタイムアウト期間のどちらか短い方が経過すると、セッションは切断されます。</span><span class="sxs-lookup"><span data-stu-id="c3501-311">The session is disconnected after either the default 20 minutes, or after the time-out period specified by the gateway administrator, whichever is shorter.</span></span>

<span data-ttu-id="c3501-312">ゲートウェイ サーバーが Windows Server 2012 R2 を実行している場合の Windows PowerShell Web Access では、ユーザーは保存されているセッションに再接続できますが、ネットワーク エラー、予期しないシャットダウン、または他のエラーによるセッションの切断が発生した場合、ユーザーはゲートウェイ管理者によって指定されたタイムアウト期間が経過するまでは、保存されているセッションを表示または再接続できません。</span><span class="sxs-lookup"><span data-stu-id="c3501-312">If the gateway server is running Windows Server 2012 R2, Windows PowerShell Web Access lets users reconnect to saved sessions at a later time, but when network errors, unplanned shutdowns, or other failures disconnect sessions, users cannot see or reconnect to saved sessions until after the time-out period specified by the gateway administrator has lapsed.</span></span>

<span data-ttu-id="c3501-313"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">関連項目</span></a>
<a href="/en-us/library/dn282394(v=ws.11).aspx#Anchor_2" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="c3501-313"><a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">See Also</span></a>
<a href="/en-us/library/dn282394(v=ws.11).aspx#Anchor_2" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="c3501-314">[Windows PowerShell Web Access のインストールと使用](https://technet.microsoft.com/en-us/library/hh831611(v=ws.11).aspx)
[about_Session_Configurations](https://technet.microsoft.com/library/dd819508.aspx)
[Windows PowerShell Web Access コマンドレット](https://technet.microsoft.com/library/hh918342.aspx)</span><span class="sxs-lookup"><span data-stu-id="c3501-314">[Install and Use Windows PowerShell Web Access](https://technet.microsoft.com/en-us/library/hh831611(v=ws.11).aspx)
[about_Session_Configurations](https://technet.microsoft.com/library/dd819508.aspx)
[Windows PowerShell Web Access Cmdlets](https://technet.microsoft.com/library/hh918342.aspx)</span></span>

<span data-ttu-id="c3501-315"><span>表示:</span> 継承 保護</span><span class="sxs-lookup"><span data-stu-id="c3501-315"><span>Show:</span> Inherited Protected</span></span>

<span data-ttu-id="c3501-316"><span class="stdr-votetitle">このページは役に立ちましたか。</span></span><span class="sxs-lookup"><span data-stu-id="c3501-316"><span class="stdr-votetitle">Was this page helpful?</span></span></span>
<span data-ttu-id="c3501-317">はい いいえ</span><span class="sxs-lookup"><span data-stu-id="c3501-317">Yes No</span></span>

<span data-ttu-id="c3501-318">その他にご意見はありますか。</span><span class="sxs-lookup"><span data-stu-id="c3501-318">Additional feedback?</span></span>

<span data-ttu-id="c3501-319">残り <span class="stdr-count"><span class="stdr-charcnt">1500</span> 文字</span> 送信 スキップする</span><span class="sxs-lookup"><span data-stu-id="c3501-319"><span class="stdr-count"><span class="stdr-charcnt">1500</span> characters remaining</span> Submit Skip this</span></span>

<span data-ttu-id="c3501-320"><span class="stdr-thankyou">ありがとうございました。</span></span><span class="sxs-lookup"><span data-stu-id="c3501-320"><span class="stdr-thankyou">Thank you!</span></span></span> <span data-ttu-id="c3501-321"><span class="stdr-appreciate">ご意見をお送りいただきありがとうございます。</span></span><span class="sxs-lookup"><span data-stu-id="c3501-321"><span class="stdr-appreciate">We appreciate your feedback.</span></span></span>

[<span data-ttu-id="c3501-322">プロファイル (個人情報) の管理</span><span class="sxs-lookup"><span data-stu-id="c3501-322">Manage Your Profile</span></span>](https://social.technet.microsoft.com/profile)

|

<span data-ttu-id="c3501-323"><a href="javascript:void(0)" id="SiteFeedbackLinkOpener"><span id="FeedbackButton" class="FeedbackButton clip20x21"><img src="https://i-technet.sec.s-msft.com/Areas/Epx/Content/Images/ImageSprite.png?v=635975720914499532" alt="Site Feedback" id="feedBackImg" class="cl_footer_feedback_icon" /> </span>サイトのフィードバック</a> サイトのフィードバック</span><span class="sxs-lookup"><span data-stu-id="c3501-323"><a href="javascript:void(0)" id="SiteFeedbackLinkOpener"><span id="FeedbackButton" class="FeedbackButton clip20x21"> <img src="https://i-technet.sec.s-msft.com/Areas/Epx/Content/Images/ImageSprite.png?v=635975720914499532" alt="Site Feedback" id="feedBackImg" class="cl_footer_feedback_icon" /> </span> Site Feedback</a> Site Feedback</span></span>

<span data-ttu-id="c3501-324"><a href="javascript:void(0)" id="SiteFeedbackLinkCloser">X</a></span><span class="sxs-lookup"><span data-stu-id="c3501-324"><a href="javascript:void(0)" id="SiteFeedbackLinkCloser">x</a></span></span>

<span data-ttu-id="c3501-325">お客様のご体験をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="c3501-325">Tell us about your experience...</span></span>

<span data-ttu-id="c3501-326">ページはすばやく表示されましたか?</span><span class="sxs-lookup"><span data-stu-id="c3501-326">Did the page load quickly?</span></span>

<span data-ttu-id="c3501-327"><span> はい<span> </span></span> <span> いいえ<span> </span></span></span><span class="sxs-lookup"><span data-stu-id="c3501-327"><span> Yes<span> </span></span> <span> No<span> </span></span></span></span>

<span data-ttu-id="c3501-328">ページのデザインは気に入りましたか?</span><span class="sxs-lookup"><span data-stu-id="c3501-328">Do you like the page design?</span></span>

<span data-ttu-id="c3501-329"><span> はい<span> </span></span> <span> いいえ<span> </span></span></span><span class="sxs-lookup"><span data-stu-id="c3501-329"><span> Yes<span> </span></span> <span> No<span> </span></span></span></span>

<span data-ttu-id="c3501-330">詳しくお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="c3501-330">Tell us more</span></span>

-   [<span data-ttu-id="c3501-331">Flash ニュースレター</span><span class="sxs-lookup"><span data-stu-id="c3501-331">Flash Newsletter</span></span>](https://technet.microsoft.com/cc543196.aspx)
-   |
-   [<span data-ttu-id="c3501-332">お問い合わせ先</span><span class="sxs-lookup"><span data-stu-id="c3501-332">Contact Us</span></span>](https://technet.microsoft.com/cc512759.aspx)
-   |
-   [<span data-ttu-id="c3501-333">プライバシーに関する声明</span><span class="sxs-lookup"><span data-stu-id="c3501-333">Privacy Statement</span></span>](https://privacy.microsoft.com/privacystatement)
-   |
-   [<span data-ttu-id="c3501-334">使用条件</span><span class="sxs-lookup"><span data-stu-id="c3501-334">Terms of Use</span></span>](https://technet.microsoft.com/cc300389.aspx)
-   |
-   [<span data-ttu-id="c3501-335">商標</span><span class="sxs-lookup"><span data-stu-id="c3501-335">Trademarks</span></span>](https://www.microsoft.com/en-us/legal/intellectualproperty/Trademarks/)
-   |

<span data-ttu-id="c3501-336">© 2016 Microsoft</span><span class="sxs-lookup"><span data-stu-id="c3501-336">© 2016 Microsoft</span></span>

<span data-ttu-id="c3501-337">© 2016 Microsoft</span><span class="sxs-lookup"><span data-stu-id="c3501-337">© 2016 Microsoft</span></span>

<span data-ttu-id="c3501-338">サードパーティのスクリプトやコード、サードパーティから本 Web サイトへのリンク、あるいは本サイトからサードパーティへのリンクは、マイクロソフトではなく、そのようなコードの所有者によってお客様にライセンス供与されています。</span><span class="sxs-lookup"><span data-stu-id="c3501-338">Third party scripts and code linked to or referenced from this website are licensed to you by the parties that own such code, not by Microsoft.</span></span> <span data-ttu-id="c3501-339">ASP.NET Ajax CDN の使用条件 - http://www.asp.net/ajaxlibrary/CDN.ashx を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3501-339">See ASP.NET Ajax CDN Terms of Use - http://www.asp.net/ajaxlibrary/CDN.ashx.</span></span>
<img src="https://m.webtrends.com/dcsjwb9vb00000c932fd0rjc7_5p3t/njs.gif?dcsuri=/nojavascript&amp;WT.js=No" alt="DCSIMG" id="Img1" width="1" height="1" />

