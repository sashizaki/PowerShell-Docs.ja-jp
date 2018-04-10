---
ms.date: 06/12/2017
author: rpsqrd
ms.topic: conceptual
keywords: JEA, PowerShell, セキュリティ
title: JEA の監査とレポート
ms.openlocfilehash: 7fc670c77b5fbf9bce8fb55dd99a2f9a984100d2
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="auditing-and-reporting-on-jea"></a><span data-ttu-id="3048e-103">JEA の監査とレポート</span><span class="sxs-lookup"><span data-stu-id="3048e-103">Auditing and Reporting on JEA</span></span>

> <span data-ttu-id="3048e-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="3048e-104">Applies to: Windows PowerShell 5.0</span></span>

<span data-ttu-id="3048e-105">JEA の展開後、JEA 構成を定期的に監査することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="3048e-105">After you've deployed JEA, you will want to regularly audit the JEA configuration.</span></span>
<span data-ttu-id="3048e-106">JEA エンドポイントに適切なユーザーがアクセスしていること、ロールの割り当てが適切であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3048e-106">This will help you assess if the correct people have access to the JEA endpoint and if their assigned roles are still appropriate.</span></span>

<span data-ttu-id="3048e-107">このトピックでは、JEA エンドポイントを監査するさまざまな方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3048e-107">This topic describes the various ways you can audit a JEA endpoint.</span></span>

## <a name="find-registered-jea-sessions-on-a-machine"></a><span data-ttu-id="3048e-108">コンピューターに登録されている JEA セッションを見つける</span><span class="sxs-lookup"><span data-stu-id="3048e-108">Find registered JEA sessions on a machine</span></span>

<span data-ttu-id="3048e-109">コンピューターに登録されている JEA セッションを確認するには、[Get-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/get-pssessionconfiguration) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3048e-109">To check which JEA sessions are registered on a machine, use the [Get-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/get-pssessionconfiguration) cmdlet.</span></span>

```powershell
# Filter for sessions that are configured as 'RestrictedRemoteServer' to find JEA-like session configurations
PS C:\> Get-PSSessionConfiguration | Where-Object { $_.SessionType -eq 'RestrictedRemoteServer' }


Name          : JEAMaintenance
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : CONTOSO\JEA_DNS_ADMINS AccessAllowed, CONTOSO\JEA_DNS_OPERATORS AccessAllowed, CONTOSO\JEA_DNS_AUDITORS AccessAllowed
```

<span data-ttu-id="3048e-110">エンドポイントに対して有効な権限は "Permission" プロパティで確認できます。</span><span class="sxs-lookup"><span data-stu-id="3048e-110">The effective rights for the endpoint are listed in the "Permission" property.</span></span>
<span data-ttu-id="3048e-111">これらのユーザーには、JEA エンドポイントに接続する権限が与えられますが、アクセスできるロール (さらにはコマンド) は、エンドポイントの登録に使用された[セッション構成ファイル](session-configurations.md)の "RoleDefinitions" フィールドにより決定されます。</span><span class="sxs-lookup"><span data-stu-id="3048e-111">These users have the right to connect to the JEA endpoint, but which roles (and, by extension, commands) they have access to is determined by the "RoleDefinitions" field in the [session configuration file](session-configurations.md) that was used to register the endpoint.</span></span>

<span data-ttu-id="3048e-112">"RoleDefinitions" プロパティのデータを展開すると、登録されている JEA エンドポイントのロール マッピングを評価できます。</span><span class="sxs-lookup"><span data-stu-id="3048e-112">You can evaluate the role mappings in a registered JEA endpoint by expanding the data in the "RoleDefinitions" property.</span></span>

```powershell
# Get the desired session configuration
$jea = Get-PSSessionConfiguration -Name 'JEAMaintenance'

# Enumerate users/groups and which roles they have access to
$jea.RoleDefinitions.GetEnumerator() | Select-Object Name, @{ Name = 'Role Capabilities'; Expression = { $_.Value.RoleCapabilities } }
```

## <a name="find-available-role-capabilities-on-the-machine"></a><span data-ttu-id="3048e-113">コンピューターで利用できるロール機能を見つける</span><span class="sxs-lookup"><span data-stu-id="3048e-113">Find available role capabilities on the machine</span></span>

<span data-ttu-id="3048e-114">有効な PowerShell モジュール内の "RoleCapabilities" フォルダーに保存されている場合、ロール機能ファイルは JEA のみで利用されます。</span><span class="sxs-lookup"><span data-stu-id="3048e-114">Role capability files will only be used by JEA if they are stored in a "RoleCapabilities" folder inside a valid PowerShell module.</span></span>
<span data-ttu-id="3048e-115">利用可能なモジュールの一覧を検索することで、コンピューターで利用できるすべてのロール機能を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="3048e-115">You can find all role capabilities available on a computer by searching the list of available modules.</span></span>

```powershell
function Find-LocalRoleCapability {
    $results = @()

    # Find modules with a "RoleCapabilities" subfolder and add any PSRC files to the result set
    Get-Module -ListAvailable | ForEach-Object {
        $psrcpath = Join-Path -Path $_.ModuleBase -ChildPath 'RoleCapabilities'
        if (Test-Path $psrcpath) {
            $results += Get-ChildItem -Path $psrcpath -Filter *.psrc
        }
    }

    # Format the results nicely to make it easier to read
    $results | Select-Object @{ Name = 'Name'; Expression = { $_.Name.TrimEnd('.psrc') }}, @{ Name = 'Path'; Expression = { $_.FullName }} | Sort-Object Name
}
```

> [!NOTE]
> <span data-ttu-id="3048e-116">この関数の結果の順序は、必ずしも、複数のロール機能で同じ名前が共有されているときのロール機能の選択順に一致しません。</span><span class="sxs-lookup"><span data-stu-id="3048e-116">The order of results from this function is not necessarily the order in which the role capabilities will be selected if multiple role capabilities share the same name.</span></span>

## <a name="check-effective-rights-for-a-specific-user"></a><span data-ttu-id="3048e-117">特定のユーザーに対して有効な権限を確認する</span><span class="sxs-lookup"><span data-stu-id="3048e-117">Check effective rights for a specific user</span></span>

<span data-ttu-id="3048e-118">JEA エンドポイントを設定したら、JEA セッションで特定のユーザーが利用できるコマンドを確認することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="3048e-118">Once you have set up a JEA endpoint, you may want to check which commands are available to a specific user in a JEA session.</span></span>
<span data-ttu-id="3048e-119">ユーザーが現在のグループ メンバーシップで JEA セッションを開始するのであれば、[Get-PSSessionCapability](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/Get-PSSessionCapability) を利用し、ユーザーに該当するすべてのコマンドを列挙できます。</span><span class="sxs-lookup"><span data-stu-id="3048e-119">You can use [Get-PSSessionCapability](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/Get-PSSessionCapability) to enumerate all of the commands applicable to a user if they were to start a JEA session with their current group memberships.</span></span>
<span data-ttu-id="3048e-120">`Get-PSSessionCapability` の出力は、JEA セッションで `Get-Command -CommandType All` を実行している指定ユーザーのそれと同じになります。</span><span class="sxs-lookup"><span data-stu-id="3048e-120">The output of `Get-PSSessionCapability` is identical to that of the specified user running `Get-Command -CommandType All` in a JEA session.</span></span>

```powershell
Get-PSSessionCapability -ConfigurationName 'JEAMaintenance' -Username 'CONTOSO\Alice'
```

<span data-ttu-id="3048e-121">ユーザーが、追加 JEA 権限が与えられるグループの永続的なメンバーではないとき、このコマンドレットでこれらの追加のアクセス許可が反映されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="3048e-121">If your users are not permanent members of groups which would grant them additional JEA rights, this cmdlet may not reflect those extra permissions.</span></span>
<span data-ttu-id="3048e-122">一般的に、Just-In-Time の特権アクセス (必要なときに必要な許可を与える) 管理システムを利用し、セキュリティ グループに一時的に属することをユーザーに許可する場合がそれに該当します。</span><span class="sxs-lookup"><span data-stu-id="3048e-122">This is typically the case when using just-in-time privileged access management systems to allow users to temporarily belong to a security group.</span></span>
<span data-ttu-id="3048e-123">仕事を行うために必要な最小限のコマンドだけが与えられるように、ユーザーとロール (と各ロールのコンテンツ) のマッピングを常に注意深く評価してください。</span><span class="sxs-lookup"><span data-stu-id="3048e-123">Always carefully evaluate the mapping of users to roles and the contents of each role to ensure users are only getting access to the least amount of commands needed to do their jobs successfully.</span></span>

## <a name="powershell-event-logs"></a><span data-ttu-id="3048e-124">PowerShell イベント ログ</span><span class="sxs-lookup"><span data-stu-id="3048e-124">PowerShell event logs</span></span>

<span data-ttu-id="3048e-125">システムでモジュールやスクリプト ブロックのログ記録を有効にしている場合、ユーザーが JEA セッションで実行したコマンドごとに、Windows イベント ログでイベントを検索できます。</span><span class="sxs-lookup"><span data-stu-id="3048e-125">If you enabled module and/or script block logging on the system, you will be able to find events in the Windows event logs for each command a user ran in their JEA sessions.</span></span>
<span data-ttu-id="3048e-126">イベントを検索するには、Windows イベント ビューアーを起動し、**Microsoft-Windows-PowerShell/Operational** イベント ログに移動し、イベント ID が **4104** のイベントを探します。</span><span class="sxs-lookup"><span data-stu-id="3048e-126">To find these events, open the Windows Event Viewer, navigate to the **Microsoft-Windows-PowerShell/Operational** event log, and look for events with event ID **4104**.</span></span>

<span data-ttu-id="3048e-127">各イベント ログ エントリに、コマンドを実行したセッションに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3048e-127">Each event log entry will include information about the session in which the command was run.</span></span>
<span data-ttu-id="3048e-128">JEA セッションの場合、これには **ConnectedUser** と **RunAsUser** に関する重要な情報が含まれます。ConnectedUser は JEA セッションを実行した実際のユーザーであり、RunAsUser はコマンドの実行に利用されたアカウント JEA を識別します。</span><span class="sxs-lookup"><span data-stu-id="3048e-128">For JEA sessions, this includes important information about the **ConnectedUser**, which is the actual user who created the JEA session, as well as the **RunAsUser** which identifies the account JEA used to execute the command.</span></span>
<span data-ttu-id="3048e-129">アプリケーション イベント ログには、RunAsUser により行われた変更が表示されます。そのため、トランスクリプトまたはモジュール/スクリプトのログ記録を有効にしておくことが、コマンドの呼び出しをユーザーにさかのぼって追跡するために重要です。</span><span class="sxs-lookup"><span data-stu-id="3048e-129">Application event logs will show changes being made by the RunAsUser, so having transcripts or module/script logging enabled is crucial to be able to trace a specific command invocation back to a user.</span></span>

## <a name="application-event-logs"></a><span data-ttu-id="3048e-130">アプリケーション イベント ログ</span><span class="sxs-lookup"><span data-stu-id="3048e-130">Application event logs</span></span>

<span data-ttu-id="3048e-131">外部のアプリケーションやサービスと情報を交換する JEA セッションでコマンドを実行すると、そのようなアプリケーションやサービスでは、独自のイベント ログにイベントが記録されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3048e-131">When you run a command in a JEA session that interacts with an external application or service, those applications may log events to their own event logs.</span></span>
<span data-ttu-id="3048e-132">PowerShell のログやトランスクリプトとは異なり、他のログ記録メカニズムでは、JEA セッションの接続ユーザーが記録されず、代わりに、仮想実行ユーザーかグループの管理されたサービス アカウントのみが記録されます。</span><span class="sxs-lookup"><span data-stu-id="3048e-132">Unlike PowerShell logs and transcripts, other logging mechanisms will not capture the connected user of the JEA session, and will instead only log the virtual run-as user or group managed service account.</span></span>
<span data-ttu-id="3048e-133">コマンドの実行ユーザーを判断するには、[セッション トランスクリプト](#session-transcripts)を確認するか、PowerShell イベント ログと、アプリケーション イベント ログに表示されている時刻とユーザーを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="3048e-133">In order to determine who ran the command, you will need to consult a [session transcript](#session-transcripts) or correlate PowerShell event logs with the time and user shown in the application event log.</span></span>

<span data-ttu-id="3048e-134">アプリケーション イベント ログの実行ユーザーと接続ユーザーを比較するとき、WinRM ログも役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="3048e-134">The WinRM log can also help you correlate run as users in an application event log with the connecting user.</span></span>
<span data-ttu-id="3048e-135">**Microsoft-Windows-Windows Remote Management/Operational** ログのイベント ID **193** では、JEA セッションが作成されるたびに、接続ユーザーと実行ユーザーの両方に対して、セキュリティ識別子 (SID) とアカウント名が記録されます。</span><span class="sxs-lookup"><span data-stu-id="3048e-135">Event ID **193** in the **Microsoft-Windows-Windows Remote Management/Operational** log records the security identifier (SID) and account name for both the connecting user and run as user every time a JEA session is created.</span></span>

## <a name="session-transcripts"></a><span data-ttu-id="3048e-136">セッションのトランスクリプト</span><span class="sxs-lookup"><span data-stu-id="3048e-136">Session transcripts</span></span>

<span data-ttu-id="3048e-137">ユーザー セッションごとにトランスクリプトを作成するように JEA を構成した場合、すべてのユーザーのアクションのテキスト コピーが指定のフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="3048e-137">If you configured JEA to create a transcript for each user session, a text copy of every user's actions will be stored in the specified folder.</span></span>

<span data-ttu-id="3048e-138">すべてのトランスクリプト ディレクトリを見つけるには、JEA で構成されているコンピューターで管理者として次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3048e-138">To find all transcript directories, run the following command as an administrator on the computer configured with JEA:</span></span>

```powershell
Get-PSSessionConfiguration | Where-Object { $_.TranscriptDirectory -ne $null } | Format-Table Name, TranscriptDirectory
```

<span data-ttu-id="3048e-139">各トランスクリプトは、セッションの開始時刻、セッションに接続したユーザー、そのユーザーに割り当てられた JEA ID に関する情報で始まります。</span><span class="sxs-lookup"><span data-stu-id="3048e-139">Each transcript starts with information about the time the session started, which user connected to the session, and which JEA identity was assigned to them.</span></span>

```
**********************
Windows PowerShell transcript start
Start time: 20160710144736
Username: CONTOSO\Alice
RunAs User: WinRM Virtual Users\WinRM VA_1_CONTOSO_Alice
Machine: SERVER01 (Microsoft Windows NT 10.0.14393.0)
[...]
```

<span data-ttu-id="3048e-140">トランスクリプトの本文には、ユーザーが実行した各コマンドに関する情報が記録されています。</span><span class="sxs-lookup"><span data-stu-id="3048e-140">In the body of the transcript, information is logged about each command the user invoked.</span></span>
<span data-ttu-id="3048e-141">ユーザーが実行したコマンドの厳密な構文は、PowerShell リモート処理のためにコマンドが変換されるため、JEA セッションでは確認できません。ただし、実行された有効なコマンドを判断することはできます。</span><span class="sxs-lookup"><span data-stu-id="3048e-141">The exact syntax of the command the user ran is unavailable in JEA sessions due to the way commands are transformed for PowerShell remoting, however you can still determine the effective command that was executed.</span></span>
<span data-ttu-id="3048e-142">次は、JEA セッションでユーザーが `Get-Service Dns` を実行した場合のトランスクリプト例からの抜粋です。</span><span class="sxs-lookup"><span data-stu-id="3048e-142">Below is an example transcript snippet from a user running `Get-Service Dns` in a JEA session:</span></span>

```
PS>CommandInvocation(Get-Service): "Get-Service"
>> ParameterBinding(Get-Service): name="Name"; value="Dns"
>> CommandInvocation(Out-Default): "Out-Default"
>> ParameterBinding(Out-Default): name="InputObject"; value="Dns"

Running  Dns                DNS Server
```

<span data-ttu-id="3048e-143">ユーザーが実行するコマンドごとに、"CommandInvocation" 行が書き込まれます。これは、ユーザーが実行したコマンドレットまたは関数を意味します。</span><span class="sxs-lookup"><span data-stu-id="3048e-143">For each command a user runs, a "CommandInvocation" line will be written, describing the cmdlet or function the user invoked.</span></span>
<span data-ttu-id="3048e-144">各 CommandInvocation の後ろに ParameterBindings が続きます。これは、コマンドと共に指定された各パラメーターとその値に関する情報です。</span><span class="sxs-lookup"><span data-stu-id="3048e-144">ParameterBindings follow each CommandInvocation to tell you about each parameter and value that was supplied with the command.</span></span>
<span data-ttu-id="3048e-145">上記の例では、"Get-Service" コマンドレットでパラメーター "Name" に値 "Dns" が指定されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3048e-145">In the above example, you can see that the parameter "Name" was supplied the value "Dns" for the "Get-Service" cmdlet.</span></span>

<span data-ttu-id="3048e-146">各コマンドの出力も CommandInvocation をトリガーします (通常は Out-Default に)。</span><span class="sxs-lookup"><span data-stu-id="3048e-146">The output of each command will also trigger a CommandInvocation, usually to Out-Default.</span></span>
<span data-ttu-id="3048e-147">Out-Default の InputObject は、コマンドから返される PowerShell オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="3048e-147">The InputObject of Out-Default is the PowerShell object returned from the command.</span></span>
<span data-ttu-id="3048e-148">そのオブジェクトの詳細が数行下に出力されています。ユーザーに表示される内容と同様のものが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3048e-148">The details of that object are printed a few lines below, closely mimicking what the user would have seen.</span></span>

## <a name="see-also"></a><span data-ttu-id="3048e-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="3048e-149">See also</span></span>

- [<span data-ttu-id="3048e-150">JEA セッションでユーザー アクションを監査する</span><span class="sxs-lookup"><span data-stu-id="3048e-150">Audit user actions in a JEA session</span></span>](audit-and-report.md)
- [<span data-ttu-id="3048e-151">*PowerShell ♥ the Blue Team* のセキュリティに関するブログ投稿</span><span class="sxs-lookup"><span data-stu-id="3048e-151">*PowerShell ♥ the Blue Team* blog post on security</span></span>](https://blogs.msdn.microsoft.com/powershell/2015/06/09/powershell-the-blue-team/)