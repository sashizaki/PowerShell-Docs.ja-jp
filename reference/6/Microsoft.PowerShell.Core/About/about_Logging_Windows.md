---
description: PowerShell は、エンジン、プロバイダー、およびコマンドレットからの内部操作を Windows イベントログに記録します。
keywords: powershell
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logging_windows?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logging-Windows
ms.openlocfilehash: 08b2ad8ecd3451f7cb24600b37fad19cd7fc8161
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354816"
---
# <a name="about-logging-windows"></a><span data-ttu-id="e0e36-104">ログ記録ウィンドウについて</span><span class="sxs-lookup"><span data-stu-id="e0e36-104">About Logging Windows</span></span>

## <a name="short-description"></a><span data-ttu-id="e0e36-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="e0e36-105">Short description</span></span>
<span data-ttu-id="e0e36-106">PowerShell は、エンジン、プロバイダー、およびコマンドレットからの内部操作を Windows イベントログに記録します。</span><span class="sxs-lookup"><span data-stu-id="e0e36-106">PowerShell logs internal operations from the engine, providers, and cmdlets to the Windows event log.</span></span>

## <a name="long-description"></a><span data-ttu-id="e0e36-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="e0e36-107">Long description</span></span>

<span data-ttu-id="e0e36-108">Powershell では、エンジンとプロバイダーの起動と停止、PowerShell コマンドの実行など、PowerShell 操作に関する詳細がログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-108">PowerShell logs details about PowerShell operations, such as starting and stopping the engine and providers, and executing PowerShell commands.</span></span>

> [!NOTE]
> <span data-ttu-id="e0e36-109">Windows PowerShell バージョン3.0、4.0、5.0、および5.1 には、Windows イベントログ用の **EventLog** コマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e0e36-109">Windows PowerShell versions 3.0, 4.0, 5.0, and 5.1 include **EventLog** cmdlets for the Windows event logs.</span></span> <span data-ttu-id="e0e36-110">これらのバージョンで、 **EventLog** コマンドレットの一覧を表示するには、「」と入力 `Get-Command -Noun EventLog` します。</span><span class="sxs-lookup"><span data-stu-id="e0e36-110">In those versions, to display the list of **EventLog** cmdlets type: `Get-Command -Noun EventLog`.</span></span> <span data-ttu-id="e0e36-111">詳細については、コマンドレットのドキュメントと、使用している Windows PowerShell のバージョンの about_EventLogs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0e36-111">For more information, see the cmdlet documentation and about_EventLogs for your version of Windows PowerShell.</span></span>

## <a name="viewing-the-powershell-event-log-entries-on-windows"></a><span data-ttu-id="e0e36-112">Windows での PowerShell イベントログエントリの表示</span><span class="sxs-lookup"><span data-stu-id="e0e36-112">Viewing the PowerShell event log entries on Windows</span></span>

<span data-ttu-id="e0e36-113">PowerShell ログは、Windows イベントビューアーを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-113">PowerShell logs can be viewed using the Windows Event Viewer.</span></span> <span data-ttu-id="e0e36-114">イベントログは、[アプリケーションとサービスログ] グループにあり、という名前が付けられてい `PowerShellCore` ます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-114">The event log is located in the Application and Services Logs group and is named `PowerShellCore`.</span></span> <span data-ttu-id="e0e36-115">関連付けられている ETW プロバイダー `GUID` は `{f90714a8-5509-434a-bf6d-b1624c8a19a2}` です。</span><span class="sxs-lookup"><span data-stu-id="e0e36-115">The associated ETW provider `GUID` is `{f90714a8-5509-434a-bf6d-b1624c8a19a2}`.</span></span>

<span data-ttu-id="e0e36-116">スクリプトブロックのログ記録を有効にすると、PowerShell によって次のイベントがログに記録され `PowerShellCore/Operational` ます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-116">When Script Block Logging is enabled, PowerShell logs the following events to the `PowerShellCore/Operational` log:</span></span>

|  <span data-ttu-id="e0e36-117">フィールド</span><span class="sxs-lookup"><span data-stu-id="e0e36-117">Field</span></span>  |       <span data-ttu-id="e0e36-118">値</span><span class="sxs-lookup"><span data-stu-id="e0e36-118">Value</span></span>       |
| ------- | ----------------- |
| <span data-ttu-id="e0e36-119">EventId</span><span class="sxs-lookup"><span data-stu-id="e0e36-119">EventId</span></span> | `4104` / `0x1008` |
| <span data-ttu-id="e0e36-120">チャネル</span><span class="sxs-lookup"><span data-stu-id="e0e36-120">Channel</span></span> | `Operational`     |
| <span data-ttu-id="e0e36-121">Level</span><span class="sxs-lookup"><span data-stu-id="e0e36-121">Level</span></span>   | `Verbose`         |
| <span data-ttu-id="e0e36-122">オペコード</span><span class="sxs-lookup"><span data-stu-id="e0e36-122">Opcode</span></span>  | `Create`          |
| <span data-ttu-id="e0e36-123">タスク</span><span class="sxs-lookup"><span data-stu-id="e0e36-123">Task</span></span>    | `CommandStart`    |
| <span data-ttu-id="e0e36-124">Keyword</span><span class="sxs-lookup"><span data-stu-id="e0e36-124">Keyword</span></span> | `Runspace`        |

### <a name="registering-the-powershell-event-provider-on-windows"></a><span data-ttu-id="e0e36-125">Windows での PowerShell イベントプロバイダーの登録</span><span class="sxs-lookup"><span data-stu-id="e0e36-125">Registering the PowerShell event provider on Windows</span></span>

<span data-ttu-id="e0e36-126">Linux または macOS とは異なり、イベントをイベントログに書き込む前に、Windows でイベントプロバイダーを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0e36-126">Unlike Linux or macOS, Windows requires the event provider to be registered before events can be written to the event log.</span></span> <span data-ttu-id="e0e36-127">PowerShell イベントプロバイダーを有効にするには、管理者特権の PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0e36-127">To enable the PowerShell event provider, run the following command from an elevated PowerShell prompt.</span></span>

```powershell
$PSHOME\RegisterManifest.ps1
```

### <a name="unregistering-the-powershell-event-provider-on-windows"></a><span data-ttu-id="e0e36-128">Windows での PowerShell イベントプロバイダーの登録解除</span><span class="sxs-lookup"><span data-stu-id="e0e36-128">Unregistering the PowerShell event provider on Windows</span></span>

<span data-ttu-id="e0e36-129">イベントプロバイダーを登録すると、イベントのデコードに使用されるバイナリライブラリにロックが配置されます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-129">Registering the event provider places a lock in the binary library used to decode events.</span></span> <span data-ttu-id="e0e36-130">このライブラリを更新するには、このロックを解放するためにプロバイダーの登録を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0e36-130">To update this library, the provider must be unregistered to release this lock.</span></span>

<span data-ttu-id="e0e36-131">PowerShell プロバイダーの登録を解除するには、管理者特権の PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0e36-131">To unregister the PowerShell provider, run the following command from an elevated PowerShell prompt.</span></span>

```powershell
$PSHOME\RegisterManifest.ps1 -Unregister
```

<span data-ttu-id="e0e36-132">PowerShell を更新した後、を実行し `$PSHOME\RegisterManifest.ps1` て更新されたイベントプロバイダーを登録します。</span><span class="sxs-lookup"><span data-stu-id="e0e36-132">After updating PowerShell, run `$PSHOME\RegisterManifest.ps1` to register the updated event provider.</span></span>

## <a name="enabling-script-block-logging"></a><span data-ttu-id="e0e36-133">スクリプトブロックのログ記録を有効にする</span><span class="sxs-lookup"><span data-stu-id="e0e36-133">Enabling Script Block Logging</span></span>

<span data-ttu-id="e0e36-134">スクリプトブロックのログ記録を有効にすると、PowerShell によって処理されるすべてのスクリプトブロックの内容が記録されます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-134">When you enable Script Block Logging, PowerShell records the content of all script blocks that it processes.</span></span> <span data-ttu-id="e0e36-135">有効にすると、新しい PowerShell セッションによってこの情報がログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-135">Once enabled, any new PowerShell session logs this information.</span></span>

> [!NOTE]
> <span data-ttu-id="e0e36-136">診断以外の目的でスクリプトブロックログを使用する場合は、次に示すように、保護されたイベントログを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e0e36-136">It's recommended to enable Protected Event Logging, as described below, when using Script Block Logging for anything other than diagnostics purposes.</span></span>

<span data-ttu-id="e0e36-137">スクリプトブロックのログ記録は、グループポリシーまたはレジストリ設定を使用して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-137">Script Block Logging can be enabled via Group Policy or a registry setting.</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="e0e36-138">グループ ポリシーの使用</span><span class="sxs-lookup"><span data-stu-id="e0e36-138">Using Group Policy</span></span>

<span data-ttu-id="e0e36-139">自動議事録を有効にするには、グループポリシーでこの機能を有効にし `Turn on PowerShell Script Block
Logging` `Administrative Templates -> Windows
Components -> Windows PowerShell` ます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-139">To enable automatic transcription, enable the `Turn on PowerShell Script Block
Logging` feature in Group Policy through `Administrative Templates -> Windows
Components -> Windows PowerShell`.</span></span>

### <a name="using-the-registry"></a><span data-ttu-id="e0e36-140">レジストリの使用</span><span class="sxs-lookup"><span data-stu-id="e0e36-140">Using the Registry</span></span>

<span data-ttu-id="e0e36-141">次の関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="e0e36-141">Run the following function:</span></span>

```powershell
function Enable-PSScriptBlockLogging
{
    $basePath = 'HKLM:\Software\Policies\Microsoft\Windows' +
      '\PowerShell\ScriptBlockLogging'

    if(-not (Test-Path $basePath))
    {
        $null = New-Item $basePath -Force
    }

    Set-ItemProperty $basePath -Name EnableScriptBlockLogging -Value "1"
}
```

## <a name="protected-event-logging"></a><span data-ttu-id="e0e36-142">保護されたイベントのログ記録</span><span class="sxs-lookup"><span data-stu-id="e0e36-142">Protected Event Logging</span></span>

<span data-ttu-id="e0e36-143">システムのログ記録レベルを上げると、ログに記録されたコンテンツに機密データが含まれる可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="e0e36-143">Increasing the level of logging on a system increases the possibility that logged content may contain sensitive data.</span></span> <span data-ttu-id="e0e36-144">たとえば、スクリプトのログ記録を有効にすると、スクリプトによって使用される資格情報やその他の機密データをイベントログに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-144">For example, with script logging enabled, credentials or other sensitive data used by a script can be written to the event log.</span></span> <span data-ttu-id="e0e36-145">機密データがログに記録されているコンピューターが侵害されると、ログによって、攻撃者は、それらの情報を拡張するために必要な情報を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-145">When a machine that has logged sensitive data is compromised, the logs can provide an attacker with information needed to extend their reach.</span></span>

<span data-ttu-id="e0e36-146">この情報を保護するために、Windows 10 では保護されたイベントログが導入されています。</span><span class="sxs-lookup"><span data-stu-id="e0e36-146">To protect this information, Windows 10 introduces Protected Event Logging.</span></span>
<span data-ttu-id="e0e36-147">保護されたイベントログを使用すると、参加アプリケーションは、イベントログに書き込まれた機密データを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-147">Protected Event Logging lets participating applications encrypt sensitive data written to the event log.</span></span> <span data-ttu-id="e0e36-148">後で、より安全で集中管理されたログコレクター上で、これらのログの暗号化を解除して処理することができます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-148">Later, you can decrypt and process these logs on a more secure and centralized log collector.</span></span>

<span data-ttu-id="e0e36-149">イベントログの内容は、IETF Cryptographic Message 構文 (CMS) 標準を使用して保護されています。</span><span class="sxs-lookup"><span data-stu-id="e0e36-149">Event log content is protected using the IETF Cryptographic Message Syntax (CMS) standard.</span></span> <span data-ttu-id="e0e36-150">CMS は公開キー暗号化を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0e36-150">CMS uses public key cryptography.</span></span> <span data-ttu-id="e0e36-151">コンテンツの暗号化とコンテンツの暗号化解除に使用されるキーは、個別に保持されます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-151">The keys used to encrypt content and decrypt content are kept separate.</span></span>

<span data-ttu-id="e0e36-152">公開キーは広く共有でき、機密性の高いデータではありません。</span><span class="sxs-lookup"><span data-stu-id="e0e36-152">The public key can be shared widely and isn't sensitive data.</span></span> <span data-ttu-id="e0e36-153">この公開キーで暗号化されたコンテンツは、秘密キーによってのみ復号化できます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-153">Any content encrypted with this public key can only be decrypted by the private key.</span></span> <span data-ttu-id="e0e36-154">公開キー暗号化の詳細については、「 [Wikipedia-公開キー暗号化](https://en.wikipedia.org/wiki/Public-key_cryptography)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0e36-154">For more information about Public Key Cryptography, see [Wikipedia - Public Key Cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="e0e36-155">保護されたイベントログポリシーを有効にするには、保護するイベントログデータがあるすべてのコンピューターに公開キーを展開します。</span><span class="sxs-lookup"><span data-stu-id="e0e36-155">To enable a Protected Event Logging policy, deploy a public key to all machines that have event log data to protect.</span></span> <span data-ttu-id="e0e36-156">対応する秘密キーは、中央のイベントログコレクターや [SIEM][] アグリゲーターなどのより安全な場所でイベントログを後処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-156">The corresponding private key is used to post-process the event logs at a more secure location such as a central event log collector, or [SIEM][] aggregator.</span></span> <span data-ttu-id="e0e36-157">Azure で SIEM を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-157">You can set up SIEM in Azure.</span></span> <span data-ttu-id="e0e36-158">詳細については、「 [GENERIC SIEM integration](/cloud-app-security/siem)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0e36-158">For more information, see [Generic SIEM integration](/cloud-app-security/siem).</span></span>

### <a name="enabling-protected-event-logging-via-group-policy"></a><span data-ttu-id="e0e36-159">グループポリシーを使用した保護されたイベントのログ記録の有効化</span><span class="sxs-lookup"><span data-stu-id="e0e36-159">Enabling Protected Event Logging via Group Policy</span></span>

<span data-ttu-id="e0e36-160">保護されたイベントのログ記録を有効にするには、 `Enable Protected Event Logging` グループポリシーで機能を有効に `Administrative Templates -> Windows Components
-> Event Logging` します。</span><span class="sxs-lookup"><span data-stu-id="e0e36-160">To enable Protected Event Logging, enable the `Enable Protected Event Logging` feature in Group Policy through `Administrative Templates -> Windows Components
-> Event Logging`.</span></span> <span data-ttu-id="e0e36-161">この設定には暗号化証明書が必要です。暗号化証明書は、次のいずれかの形式で指定できます。</span><span class="sxs-lookup"><span data-stu-id="e0e36-161">This setting requires an encryption certificate, which you can provide in one of several forms:</span></span>

- <span data-ttu-id="e0e36-162">Base-64 でエンコードされた x.509 証明書のコンテンツ ( `Export` 証明書マネージャーのオプションによって提供されるなど)。</span><span class="sxs-lookup"><span data-stu-id="e0e36-162">The content of a base-64 encoded X.509 certificate (for example, as offered by the `Export` option in Certificate Manager).</span></span>
- <span data-ttu-id="e0e36-163">ローカルコンピューターの証明書ストアにある証明書の拇印 (PKI インフラストラクチャで展開できます)。</span><span class="sxs-lookup"><span data-stu-id="e0e36-163">The thumbprint of a certificate that can be found in the Local Machine certificate store (can be deployed by PKI infrastructure).</span></span>
- <span data-ttu-id="e0e36-164">証明書の完全なパス (ローカルまたはリモート共有を指定できます)。</span><span class="sxs-lookup"><span data-stu-id="e0e36-164">The full path to a certificate (can be local, or a remote share).</span></span>
- <span data-ttu-id="e0e36-165">証明書または証明書を含むディレクトリへのパス (ローカルまたはリモート共有を指定できます)。</span><span class="sxs-lookup"><span data-stu-id="e0e36-165">The path to a directory containing a certificate or certificates (can be local, or a remote share).</span></span>
- <span data-ttu-id="e0e36-166">ローカルコンピューターの証明書ストアで検索できる証明書のサブジェクト名 (PKI インフラストラクチャによって展開できます)。</span><span class="sxs-lookup"><span data-stu-id="e0e36-166">The subject name of a certificate that can be found in the Local Machine certificate store (can be deployed by PKI infrastructure).</span></span>

<span data-ttu-id="e0e36-167">結果として得られる証明書は、 `Document Encryption` 拡張キー使用法 () として、 `1.3.6.1.4.1.311.80.1` `Data Encipherment` またはまたは `Key
Encipherment` キー使用法が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0e36-167">The resulting certificate must have `Document Encryption` as an enhanced key usage (`1.3.6.1.4.1.311.80.1`), and either `Data Encipherment` or `Key
Encipherment` key usages enabled.</span></span>

> [!WARNING]
> <span data-ttu-id="e0e36-168">秘密キーは、イベントのログを記録するマシンにデプロイしないでください。</span><span class="sxs-lookup"><span data-stu-id="e0e36-168">The private key shouldn't be deployed to the machines logging events.</span></span> <span data-ttu-id="e0e36-169">メッセージの暗号化を解除する安全な場所に保管しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0e36-169">It should be kept in a secure location where you decrypt the messages.</span></span>

### <a name="decrypting-protected-event-logging-messages"></a><span data-ttu-id="e0e36-170">保護されたイベントログメッセージの復号化</span><span class="sxs-lookup"><span data-stu-id="e0e36-170">Decrypting Protected Event Logging messages</span></span>

<span data-ttu-id="e0e36-171">次のスクリプトは、秘密キーがあることを前提として、取得と復号化を行います。</span><span class="sxs-lookup"><span data-stu-id="e0e36-171">The following script will retrieve and decrypt, assuming that you have the private key:</span></span>

```powershell
Get-WinEvent Microsoft-Windows-PowerShell/Operational |
  Where-Object Id -eq 4104 | Unprotect-CmsMessage
```

## <a name="see-also"></a><span data-ttu-id="e0e36-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0e36-172">See also</span></span>

[<span data-ttu-id="e0e36-173">about_Logging_Non-Windows</span><span class="sxs-lookup"><span data-stu-id="e0e36-173">about_Logging_Non-Windows</span></span>](about_Logging_Non-Windows.md)

[<span data-ttu-id="e0e36-174">Blue Team の PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0e36-174">PowerShell the Blue Team</span></span>](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)

[<span data-ttu-id="e0e36-175">汎用 SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="e0e36-175">Generic SIEM integration</span></span>](/cloud-app-security/siem)

<!-- link references -->
[SIEM]: https://wikipedia.org/wiki/Security_information_and_event_management
