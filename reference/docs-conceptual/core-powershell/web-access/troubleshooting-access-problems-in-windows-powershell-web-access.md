---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell Web Access でのアクセスに関する問題のトラブルシューティング"
ms.openlocfilehash: c10e19b177110ff62d44f28b6a523380b55b79e0
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
#  <a name="troubleshooting-access-problems-in-windows-powershell-web-access"></a><span data-ttu-id="fb10e-103">Windows PowerShell Web Access でのアクセスに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="fb10e-103">Troubleshooting Access Problems in Windows PowerShell Web Access</span></span>

<span data-ttu-id="fb10e-104">最終更新日: 2013 年 6 月 24 日</span><span class="sxs-lookup"><span data-stu-id="fb10e-104">Updated: June 24, 2013</span></span>

<span data-ttu-id="fb10e-105">適用対象: Windows Server 2012 R2、Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="fb10e-105">Applies To: Windows Server 2012 R2, Windows Server 2012</span></span>

<a href="" id="BKMK_trouble"></a>

------------------------------------------------------------------------

<span data-ttu-id="fb10e-106">Windows PowerShell Web Access を使ったリモート コンピューターへの接続を試行する場合に発生する可能性がある一般的な問題と、問題解決のための推奨事項を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="fb10e-106">The following table identifies some common problems that users might experience when they are attempting to connect to a remote computer by using Windows PowerShell Web Access, and includes suggestions for resolving the problems.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fb10e-107">問題</span><span class="sxs-lookup"><span data-stu-id="fb10e-107">Problem</span></span></p></th>
<th><p><span data-ttu-id="fb10e-108">考えられる原因と解決策</span><span class="sxs-lookup"><span data-stu-id="fb10e-108">Possible cause and solution</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb10e-109">サインイン エラー</span><span class="sxs-lookup"><span data-stu-id="fb10e-109">Sign-in failure</span></span></p></td>
<td><p><span data-ttu-id="fb10e-110">エラー発生の原因として以下が考えられます。</span><span class="sxs-lookup"><span data-stu-id="fb10e-110">Failure could occur because of any of the following.</span></span></p>
<ul>
<li><p><span data-ttu-id="fb10e-111">コンピューターまたはリモート コンピューターの特定のセッション構成に対するユーザー アクセスを許可する承認規則が存在しない。</span><span class="sxs-lookup"><span data-stu-id="fb10e-111">An authorization rule that allows the user access to the computer, or a specific session configuration on the remote computer, does not exist.</span></span> <span data-ttu-id="fb10e-112">Windows PowerShell Web Access では制限的なセキュリティを採用しているため、承認規則を使ってリモート コンピューターへのアクセス権をユーザーに明示的に付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb10e-112">Windows PowerShell Web Access security is restrictive; users must be granted explicit access to remote computers by using authorization rules.</span></span> <span data-ttu-id="fb10e-113">承認規則の作成の詳細については、「<a href="https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx">Windows PowerShell Web Access の承認規則とセキュリティ機能</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb10e-113">For more information about creating authorization rules, see <a href="https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx">Authorization Rules and Security Features of Windows PowerShell Web Access</a> in this guide.</span></span></p></li>
<li><p><span data-ttu-id="fb10e-114">ユーザーによる対象コンピューターへのアクセスが承認されていない。</span><span class="sxs-lookup"><span data-stu-id="fb10e-114">The user does not have authorized access to the destination computer.</span></span> <span data-ttu-id="fb10e-115">これはアクセス制御リスト (ACL) によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="fb10e-115">This is determined by access control lists (ACLs).</span></span> <span data-ttu-id="fb10e-116">詳細については、「<a href="https://technet.microsoft.com/en-us/library/hh831417(v=ws.11).aspx">Web ベースの Windows PowerShell コンソールの使用</a>」の「Windows PowerShell Web Access へのサインイン」または <a href="https://msdn.microsoft.com/library/windows/desktop/ee706585.aspx">Windows PowerShell チームのブログ</a>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb10e-116">For more information, see “Signing in to Windows PowerShell Web Access” in <a href="https://technet.microsoft.com/en-us/library/hh831417(v=ws.11).aspx">Use the Web-based Windows PowerShell Console</a>, or the <a href="https://msdn.microsoft.com/library/windows/desktop/ee706585.aspx">Windows PowerShell Team Blog</a>.</span></span></p>
<ul>
<li><p><span data-ttu-id="fb10e-117">Windows PowerShell のリモート管理が対象コンピューター上で有効になっていない。</span><span class="sxs-lookup"><span data-stu-id="fb10e-117">Windows PowerShell remote management might not be enabled on the destination computer.</span></span> <span data-ttu-id="fb10e-118">ユーザーが接続しようとしているコンピューターでリモート管理が有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fb10e-118">Verify that it is enabled on the computer to which the user is trying to connect.</span></span> <span data-ttu-id="fb10e-119">詳細については、Windows PowerShell の About ヘルプ トピックの「<a href="https://technet.microsoft.com/library/dd315349.aspx">about_Remote_Requirements</a>」にある、「リモート処理用にコンピューターを構成する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb10e-119">For more information, see “How to Configure Your Computer for Remoting” in <a href="https://technet.microsoft.com/library/dd315349.aspx">about_Remote_Requirements</a> in the Windows PowerShell About Help Topics.</span></span></p></li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb10e-120">ユーザーが Internet Explorer ウィンドウで Windows PowerShell Web Access にサインインしようとすると、<strong>[内部サーバー エラー]</strong> ページが表示されるか、Internet Explorer が応答しなくなる。</span><span class="sxs-lookup"><span data-stu-id="fb10e-120">When users try to sign in to Windows PowerShell Web Access in an Internet Explorer window, they are shown an <strong>Internal Server Error</strong> page, or Internet Explorer stops responding.</span></span> <span data-ttu-id="fb10e-121">この問題は Internet Explorer に限られている。</span><span class="sxs-lookup"><span data-stu-id="fb10e-121">This issue is specific to Internet Explorer.</span></span></p></td>
<td><p><span data-ttu-id="fb10e-122">この問題は、ユーザーがサインイン時に指定したドメイン名に漢字が含まれていた場合や、ゲートウェイ サーバー名に 1 つ以上の漢字が含まれている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="fb10e-122">This can occur for users who have signed in with a domain name that contains Chinese characters, or if one or more Chinese characters are part of the gateway server name.</span></span> <span data-ttu-id="fb10e-123">ユーザーがこの問題に対処するには、<a href="http://ie.microsoft.com/testdrive/info/downloads/Default.html">Internet Explorer 10 をインストールおよび実行</a>し、次の手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb10e-123">To work around this issue, the user should <a href="http://ie.microsoft.com/testdrive/info/downloads/Default.html">install and run Internet Explorer 10</a>, and then perform the following steps.</span></span></p>
<ol>
<li><p><span data-ttu-id="fb10e-124">Internet Explorer の <strong>[ドキュメント モード]</strong> 設定を <strong>[IE10 標準]</strong> に変更します。</span><span class="sxs-lookup"><span data-stu-id="fb10e-124">Change the Internet Explorer <strong>Document Mode</strong> setting to <strong>IE10 standards</strong>.</span></span></p>
<ol>
<li><p><span data-ttu-id="fb10e-125"><strong>F12</strong> キーを押して開発者ツール コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="fb10e-125">Press <strong>F12</strong> to open the Developer Tools console.</span></span></p></li>
<li><p><span data-ttu-id="fb10e-126">Internet Explorer 10 で、<strong>[ブラウザー モード]</strong> をクリックし、<strong>[Internet Explorer 10]</strong> をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb10e-126">In Internet Explorer 10, click <strong>Browser Mode</strong>, and then select <strong>Internet Explorer 10</strong>.</span></span></p></li>
<li><p><span data-ttu-id="fb10e-127"><strong>[ドキュメント モード]</strong>、<strong>[IE10 標準]</strong> の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb10e-127">Click <strong>Document Mode</strong>, and then click <strong>IE10 standards</strong>.</span></span></p></li>
<li><p><span data-ttu-id="fb10e-128">もう一度 <strong>F12</strong> キーを押して開発者ツール コンソールを閉じます。</span><span class="sxs-lookup"><span data-stu-id="fb10e-128">Press <strong>F12</strong> again to close the Developer Tools console.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="fb10e-129">自動プロキシ構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="fb10e-129">Disable automatic proxy configuration.</span></span></p>
<ol>
<li><p><span data-ttu-id="fb10e-130">Internet Explorer 10 で、<strong>[ツール]</strong>、<strong>[インターネット オプション]</strong> の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb10e-130">In Internet Explorer 10, click <strong>Tools</strong>, and then click <strong>Internet Options</strong>.</span></span></p></li>
<li><p><span data-ttu-id="fb10e-131"><strong>[インターネット オプション]</strong> ダイアログ ボックスの <strong>[接続]</strong> タブで、<strong>[LAN の設定]</strong> をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb10e-131">In the <strong>Internet Options</strong> dialog box, on the <strong>Connections</strong> tab, click <strong>LAN settings</strong>.</span></span></p></li>
<li><p><span data-ttu-id="fb10e-132"><strong>[設定を自動的に検出する]</strong> チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="fb10e-132">Clear the <strong>Automatically detect settings</strong> check box.</span></span> <span data-ttu-id="fb10e-133"><strong>[OK]</strong> をクリックし、もう一度 <strong>[OK]</strong> をクリックして、<strong>[インターネット オプション]</strong> ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="fb10e-133">Click <strong>OK</strong>, and then click <strong>OK</strong> again to close the <strong>Internet Options</strong> dialog box.</span></span></p></li>
</ol></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb10e-134">リモートのワークグループ コンピューターに接続できない</span><span class="sxs-lookup"><span data-stu-id="fb10e-134">Cannot connect to a remote workgroup computer</span></span></p></td>
<td><p><span data-ttu-id="fb10e-135">対象のコンピューターがワークグループ メンバーである場合、次の構文を使ってユーザー名を入力し、コンピューターにサインインします: &lt;<em>workgroup_name</em>&gt;\&lt;<em>user_name</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="fb10e-135">If the destination computer is a member of a workgroup, use the following syntax to provide your user name and sign in to the computer: &lt;<em>workgroup_name</em>&gt;\&lt;<em>user_name</em>&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb10e-136">ロールがインストールされているにもかかわらず Web サーバー (IIS) 管理ツールが見つからない</span><span class="sxs-lookup"><span data-stu-id="fb10e-136">Cannot find Web Server (IIS) management tools, even though the role was installed</span></span></p></td>
<td><p><span data-ttu-id="fb10e-137"><span class="code">Install-windowsfeature</span> コマンドレットを使用して Windows PowerShell Web Access をインストールした場合、 <span class="code">IncludeManagementTools</span> パラメーターをコマンドレットに追加しない限り、管理ツールはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="fb10e-137">If you installed Windows PowerShell Web Access by using the <span class="code">Install-WindowsFeature</span> cmdlet, management tools are not installed unless the <span class="code">IncludeManagementTools</span> parameter is added to the cmdlet.</span></span> <span data-ttu-id="fb10e-138">例については、「<a href="https://technet.microsoft.com/en-us/library/hh831611(v=ws.11).aspx">Windows PowerShell Web Access のインストールと使用</a>」の「Windows PowerShell コマンドレットを使って Windows PowerShell Web Access をインストールするには」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb10e-138">For an example, see “To install Windows PowerShell Web Access by using Windows PowerShell cmdlets” in <a href="https://technet.microsoft.com/en-us/library/hh831611(v=ws.11).aspx">Install and Use Windows PowerShell Web Access</a>.</span></span> <span data-ttu-id="fb10e-139">ゲートウェイ サーバーを対象とする役割と機能の追加ウィザードのセッションでツールを選択することで、IIS マネージャー コンソールとその他の必要な IIS 管理ツールを追加できます。</span><span class="sxs-lookup"><span data-stu-id="fb10e-139">You can add the IIS Manager console and other IIS management tools that you need by selecting the tools in an Add Roles and Features Wizard session that is targeted at the gateway server.</span></span> <span data-ttu-id="fb10e-140">役割および機能の追加ウィザードは、サーバー マネージャー内で開きます。</span><span class="sxs-lookup"><span data-stu-id="fb10e-140">The Add Roles and Features Wizard is opened from within Server Manager.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb10e-141">Windows PowerShell Web Access Web サイトにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="fb10e-141">The Windows PowerShell Web Access website is not accessible</span></span></p></td>
<td><p><span data-ttu-id="fb10e-142">Internet Explorer セキュリティ強化の構成 (IE ESC) を有効にして、信頼済みサイトの一覧に Windows PowerShell Web Access Web サイトを追加するか、IE ESC を無効にします。</span><span class="sxs-lookup"><span data-stu-id="fb10e-142">If Enhanced Security Configuration is enabled in Internet Explorer (IE ESC), you can add the Windows PowerShell Web Access website to the list of trusted sites, or disable IE ESC.</span></span> <span data-ttu-id="fb10e-143">IE ESC は、サーバー マネージャーの <strong>[ローカル サーバー]</strong> ページの <strong>[プロパティ]</strong> タイルで無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fb10e-143">You can disable IE ESC in the <strong>Properties</strong> tile on the <strong>Local Server</strong> page in Server Manager.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb10e-144">ゲートウェイ サーバーが対象のコンピューターであり、ワークグループ内にある場合に、接続しようとすると次のエラー メッセージが表示される: <strong>"承認エラーが発生しました。対象のコンピューターに接続する権限が与えられているかどうかを確認してください。</strong></span><span class="sxs-lookup"><span data-stu-id="fb10e-144">The following error message is displayed while trying to connect when the gateway server is the destination computer, and is also in a workgroup: <strong>An authorization failure occurred. Verify that you are authorized to connect to the destination computer.</strong></span></span></p></td>
<td><p><span data-ttu-id="fb10e-145">ゲートウェイ サーバーが対象のサーバーでもあり、ワークグループ内にある場合は、次の表に示されているようにユーザー名、コンピューター名、およびユーザー グループ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb10e-145">When the gateway server is also the destination server, and it is in a workgroup, specify the user name, computer name, and user group name as shown in the following table.</span></span> <span data-ttu-id="fb10e-146">ドット (.) を単体で使用してコンピューター名を表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="fb10e-146">Do not use a dot (.) by itself to represent the computer name.</span></span></p>
<div>
<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fb10e-147">シナリオ</span><span class="sxs-lookup"><span data-stu-id="fb10e-147">Scenario</span></span></p></th>
<th><p><span data-ttu-id="fb10e-148">UserName パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb10e-148">UserName Parameter</span></span></p></th>
<th><p><span data-ttu-id="fb10e-149">UserGroup パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb10e-149">UserGroup Parameter</span></span></p></th>
<th><p><span data-ttu-id="fb10e-150">ComputerName パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb10e-150">ComputerName Parameter</span></span></p></th>
<th><p><span data-ttu-id="fb10e-151">ComputerGroup パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb10e-151">ComputerGroup Parameter</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb10e-152">ゲートウェイ サーバーがドメイン内にある場合</span><span class="sxs-lookup"><span data-stu-id="fb10e-152">Gateway server is in a domain</span></span></p></td>
<td><p><span data-ttu-id="fb10e-153"><em>Server_name</em>\<em>user_name</em>、Localhost\<em>user_name</em>、または .\<em>user_name</em></span><span class="sxs-lookup"><span data-stu-id="fb10e-153"><em>Server_name</em>\<em>user_name</em>, Localhost\<em>user_name</em>, or .\<em>user_name</em></span></span></p></td>
<td><p><span data-ttu-id="fb10e-154"><em>Server_name</em>\<em>user_group</em>、Localhost\<em>user_group</em>、または.\<em>user_group</em></span><span class="sxs-lookup"><span data-stu-id="fb10e-154"><em>Server_name</em>\<em>user_group</em>, Localhost\<em>user_group</em>, or .\<em>user_group</em></span></span></p></td>
<td><p><span data-ttu-id="fb10e-155">ゲートウェイ サーバーの完全修飾名または Localhost</span><span class="sxs-lookup"><span data-stu-id="fb10e-155">Fully qualified name of gateway server, or Localhost</span></span></p></td>
<td><p><span data-ttu-id="fb10e-156"><em>Server_name</em>\<em>computer_group</em>、Localhost\<em>computer_group</em>、または .\<em>computer_group</em></span><span class="sxs-lookup"><span data-stu-id="fb10e-156"><em>Server_name</em>\<em>computer_group</em>, Localhost\<em>computer_group</em>, or .\<em>computer_group</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb10e-157">ゲートウェイ サーバーがワークグループ内にある場合</span><span class="sxs-lookup"><span data-stu-id="fb10e-157">Gateway server is in a workgroup</span></span></p></td>
<td><p><span data-ttu-id="fb10e-158"><em>Server_name</em>\<em>user_name</em>、Localhost\<em>user_name</em>、または .\<em>user_name</em></span><span class="sxs-lookup"><span data-stu-id="fb10e-158"><em>Server_name</em>\<em>user_name</em>, Localhost\<em>user_name</em>, or .\<em>user_name</em></span></span></p></td>
<td><p><span data-ttu-id="fb10e-159"><em>Server_name</em>\<em>user_group</em>、Localhost\<em>user_group</em>、または .\<em>user_group</em></span><span class="sxs-lookup"><span data-stu-id="fb10e-159"><em>Server_name</em>\<em>user_group</em>, Localhost\<em>user_group</em> or .\<em>user_group</em></span></span></p></td>
<td><p><span data-ttu-id="fb10e-160">サーバー名</span><span class="sxs-lookup"><span data-stu-id="fb10e-160">Server name</span></span></p></td>
<td><p><span data-ttu-id="fb10e-161"><em>Server_name</em>\<em>computer_group</em>、Localhost\<em>computer_group</em>、または .\<em>computer_group</em></span><span class="sxs-lookup"><span data-stu-id="fb10e-161"><em>Server_name</em>\<em>computer_group</em>, Localhost\<em>computer_group</em> or .\<em>computer_group</em></span></span></p></td>
</tr>
</tbody>
</table>
</div>
<p><span data-ttu-id="fb10e-162">次のいずれかの形式の資格情報を使用して、対象コンピューターとしてゲートウェイ サーバーにサインインします。</span><span class="sxs-lookup"><span data-stu-id="fb10e-162">Sign in to a gateway server as target computer by using credentials formatted as one of the following.</span></span></p>
<ul>
<li><p><span data-ttu-id="fb10e-163"><em>Server_name</em>\<em>user_name</em></span><span class="sxs-lookup"><span data-stu-id="fb10e-163"><em>Server_name</em>\<em>user_name</em></span></span></p></li>
<li><p><span data-ttu-id="fb10e-164">Localhost\<em>user_name</em></span><span class="sxs-lookup"><span data-stu-id="fb10e-164">Localhost\<em>user_name</em></span></span></p></li>
<li><p><span data-ttu-id="fb10e-165">.\<em>user_name</em></span><span class="sxs-lookup"><span data-stu-id="fb10e-165">.\<em>user_name</em></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb10e-166">承認規則内に、構文 <em>user_name</em>/<em>computer_name</em>  ではなくセキュリティ識別子 (SID) が表示される</span><span class="sxs-lookup"><span data-stu-id="fb10e-166">A security identifier (SID) is displayed in an authorization rule instead of the syntax <em>user_name</em>/<em>computer_name</em> </span></span></p></td>
<td><p><span data-ttu-id="fb10e-167">規則が有効ではなくなっているか、Active Directory Domain Services のクエリが失敗しています。</span><span class="sxs-lookup"><span data-stu-id="fb10e-167">Either the rule is no longer valid, or the Active Directory Domain Services query failed.</span></span> <span data-ttu-id="fb10e-168">以前はワークグループ内にあったゲートウェイ サーバーが後でドメインに参加した場合は通常、承認規則は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="fb10e-168">An authorization rule is usually not valid in scenarios where the gateway server was at one time in a workgroup, but was later joined to a domain.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb10e-169">ドメインを伴う IPv6 アドレスとして承認規則内で指定されている対象コンピューターにサインインできない。</span><span class="sxs-lookup"><span data-stu-id="fb10e-169">Cannot sign in to a target computer that has been specified in authorization rules as an IPv6 address with a domain.</span></span></p></td>
<td><p><span data-ttu-id="fb10e-170">承認規則では、ドメイン名形式の IPv6 アドレスがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fb10e-170">Authorization rules do not support an IPv6 address in form of a domain name.</span></span> <span data-ttu-id="fb10e-171">IPv6 アドレスを使用して対象コンピューターを指定するには、承認規則内で元の (コロンを含む) IPv6 アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb10e-171">To specify a destination computer by using an IPv6 address, use the original IPv6 address (that contains colons) in the authorization rule.</span></span> <span data-ttu-id="fb10e-172">Windows PowerShell Web Access のサインイン ページでは、ドメイン名形式の IPv6 アドレスも数値形式の (コロンを含む) IPv6 アドレスも対象コンピューター名としてサポートされていますが、承認規則内では異なります。</span><span class="sxs-lookup"><span data-stu-id="fb10e-172">Both domain and numerical (with colons) IPv6 addresses are supported as the target computer name on the Windows PowerShell Web Access sign-in page, but not in authorization rules.</span></span> <span data-ttu-id="fb10e-173">IPv6 アドレスの詳細については、<a href="https://technet.microsoft.com/library/cc781672.aspx">IPv6 の動作のしくみに関するページ</a>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb10e-173">For more information about IPv6 addresses, see <a href="https://technet.microsoft.com/library/cc781672.aspx">How IPv6 Works</a>.</span></span></p></td>
</tr>
</tbody>
</table><span data-ttu-id="fb10e-174">

<a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">関連項目</span></a>
<a href="/en-us/library/dn282395(v=ws.11).aspx#Anchor_1" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span><span class="sxs-lookup"><span data-stu-id="fb10e-174">

<a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">See Also</span></a>
<a href="/en-us/library/dn282395(v=ws.11).aspx#Anchor_1" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a></span></span>

------------------------------------------------------------------------

<span data-ttu-id="fb10e-175">[Windows PowerShell Web Access の承認規則とセキュリティ機能](https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx)
[Web ベースの Windows PowerShell コンソールの使用](https://technet.microsoft.com/en-us/library/hh831417(v=ws.11).aspx)
[about_Remote_Requirements](https://technet.microsoft.com/library/dd315349.aspx)</span><span class="sxs-lookup"><span data-stu-id="fb10e-175">[Authorization Rules and Security Features of Windows PowerShell Web Access](https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx)
[Use the Web-based Windows PowerShell Console](https://technet.microsoft.com/en-us/library/hh831417(v=ws.11).aspx)
[about_Remote_Requirements](https://technet.microsoft.com/library/dd315349.aspx)</span></span>

<span data-ttu-id="fb10e-176"><span>表示:</span> 継承 保護</span><span class="sxs-lookup"><span data-stu-id="fb10e-176"><span>Show:</span> Inherited Protected</span></span>

<span data-ttu-id="fb10e-177"><span class="stdr-votetitle">このページは役に立ちましたか。</span></span><span class="sxs-lookup"><span data-stu-id="fb10e-177"><span class="stdr-votetitle">Was this page helpful?</span></span></span>
<span data-ttu-id="fb10e-178">はい いいえ</span><span class="sxs-lookup"><span data-stu-id="fb10e-178">Yes No</span></span>

<span data-ttu-id="fb10e-179">その他にご意見はありますか。</span><span class="sxs-lookup"><span data-stu-id="fb10e-179">Additional feedback?</span></span>

<span data-ttu-id="fb10e-180">残り <span class="stdr-count"><span class="stdr-charcnt">1500</span> 文字</span> 送信 スキップする</span><span class="sxs-lookup"><span data-stu-id="fb10e-180"><span class="stdr-count"><span class="stdr-charcnt">1500</span> characters remaining</span> Submit Skip this</span></span>

<span data-ttu-id="fb10e-181"><span class="stdr-thankyou">ありがとうございました。</span></span><span class="sxs-lookup"><span data-stu-id="fb10e-181"><span class="stdr-thankyou">Thank you!</span></span></span> <span data-ttu-id="fb10e-182"><span class="stdr-appreciate">ご意見をお送りいただきありがとうございます。</span></span><span class="sxs-lookup"><span data-stu-id="fb10e-182"><span class="stdr-appreciate">We appreciate your feedback.</span></span></span>

[<span data-ttu-id="fb10e-183">プロファイル (個人情報) の管理</span><span class="sxs-lookup"><span data-stu-id="fb10e-183">Manage Your Profile</span></span>](https://social.technet.microsoft.com/profile)

|

<span data-ttu-id="fb10e-184"><a href="javascript:void(0)" id="SiteFeedbackLinkOpener"><span id="FeedbackButton" class="FeedbackButton clip20x21"><img src="https://i-technet.sec.s-msft.com/Areas/Epx/Content/Images/ImageSprite.png?v=635975720914499532" alt="Site Feedback" id="feedBackImg" class="cl_footer_feedback_icon" /> </span>サイトのフィードバック</a> サイトのフィードバック</span><span class="sxs-lookup"><span data-stu-id="fb10e-184"><a href="javascript:void(0)" id="SiteFeedbackLinkOpener"><span id="FeedbackButton" class="FeedbackButton clip20x21"> <img src="https://i-technet.sec.s-msft.com/Areas/Epx/Content/Images/ImageSprite.png?v=635975720914499532" alt="Site Feedback" id="feedBackImg" class="cl_footer_feedback_icon" /> </span> Site Feedback</a> Site Feedback</span></span>

<span data-ttu-id="fb10e-185"><a href="javascript:void(0)" id="SiteFeedbackLinkCloser">X</a></span><span class="sxs-lookup"><span data-stu-id="fb10e-185"><a href="javascript:void(0)" id="SiteFeedbackLinkCloser">x</a></span></span>

<span data-ttu-id="fb10e-186">お客様のご体験をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="fb10e-186">Tell us about your experience...</span></span>

<span data-ttu-id="fb10e-187">ページはすばやく表示されましたか?</span><span class="sxs-lookup"><span data-stu-id="fb10e-187">Did the page load quickly?</span></span>

<span data-ttu-id="fb10e-188"><span> はい<span> </span></span> <span> いいえ<span> </span></span></span><span class="sxs-lookup"><span data-stu-id="fb10e-188"><span> Yes<span> </span></span> <span> No<span> </span></span></span></span>

<span data-ttu-id="fb10e-189">ページのデザインは気に入りましたか?</span><span class="sxs-lookup"><span data-stu-id="fb10e-189">Do you like the page design?</span></span>

<span data-ttu-id="fb10e-190"><span> はい<span> </span></span> <span> いいえ<span> </span></span></span><span class="sxs-lookup"><span data-stu-id="fb10e-190"><span> Yes<span> </span></span> <span> No<span> </span></span></span></span>

<span data-ttu-id="fb10e-191">詳しくお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="fb10e-191">Tell us more</span></span>

-   [<span data-ttu-id="fb10e-192">Flash ニュースレター</span><span class="sxs-lookup"><span data-stu-id="fb10e-192">Flash Newsletter</span></span>](https://technet.microsoft.com/cc543196.aspx)
-   |
-   [<span data-ttu-id="fb10e-193">お問い合わせ先</span><span class="sxs-lookup"><span data-stu-id="fb10e-193">Contact Us</span></span>](https://technet.microsoft.com/cc512759.aspx)
-   |
-   [<span data-ttu-id="fb10e-194">プライバシーに関する声明</span><span class="sxs-lookup"><span data-stu-id="fb10e-194">Privacy Statement</span></span>](https://privacy.microsoft.com/privacystatement)
-   |
-   [<span data-ttu-id="fb10e-195">使用条件</span><span class="sxs-lookup"><span data-stu-id="fb10e-195">Terms of Use</span></span>](https://technet.microsoft.com/cc300389.aspx)
-   |
-   [<span data-ttu-id="fb10e-196">商標</span><span class="sxs-lookup"><span data-stu-id="fb10e-196">Trademarks</span></span>](https://www.microsoft.com/en-us/legal/intellectualproperty/Trademarks/)
-   |

<span data-ttu-id="fb10e-197">© 2016 Microsoft</span><span class="sxs-lookup"><span data-stu-id="fb10e-197">© 2016 Microsoft</span></span>

<span data-ttu-id="fb10e-198">© 2016 Microsoft</span><span class="sxs-lookup"><span data-stu-id="fb10e-198">© 2016 Microsoft</span></span>

<span data-ttu-id="fb10e-199">サードパーティのスクリプトやコード、サードパーティから本 Web サイトへのリンク、あるいは本サイトからサードパーティへのリンクは、マイクロソフトではなく、そのようなコードの所有者によってお客様にライセンス供与されています。</span><span class="sxs-lookup"><span data-stu-id="fb10e-199">Third party scripts and code linked to or referenced from this website are licensed to you by the parties that own such code, not by Microsoft.</span></span> <span data-ttu-id="fb10e-200">ASP.NET Ajax CDN の使用条件 - http://www.asp.net/ajaxlibrary/CDN.ashx を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb10e-200">See ASP.NET Ajax CDN Terms of Use - http://www.asp.net/ajaxlibrary/CDN.ashx.</span></span>
<img src="https://m.webtrends.com/dcsjwb9vb00000c932fd0rjc7_5p3t/njs.gif?dcsuri=/nojavascript&amp;WT.js=No" alt="DCSIMG" id="Img1" width="1" height="1" />

