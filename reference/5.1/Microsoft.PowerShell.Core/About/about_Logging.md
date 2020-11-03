---
description: PowerShell は、エンジン、プロバイダー、およびコマンドレットからの内部操作をログに記録します。
keywords: powershell
Locale: en-US
ms.date: 12/14/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logging?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logging
ms.openlocfilehash: 5d061b38b5b0fa45cf0a86c2f5b7e0efcb8d1f7b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222704"
---
# <a name="about-logging"></a><span data-ttu-id="118d8-104">ログ記録について</span><span class="sxs-lookup"><span data-stu-id="118d8-104">About Logging</span></span>

## <a name="short-description"></a><span data-ttu-id="118d8-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="118d8-105">Short description</span></span>

<span data-ttu-id="118d8-106">PowerShell は、エンジン、プロバイダー、およびコマンドレットからの内部操作をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="118d8-106">PowerShell logs internal operations from the engine, providers, and cmdlets.</span></span>

## <a name="long-description"></a><span data-ttu-id="118d8-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="118d8-107">Long description</span></span>

<span data-ttu-id="118d8-108">Powershell では、エンジンとプロバイダーの起動と停止、PowerShell コマンドの実行など、PowerShell 操作に関する詳細がログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="118d8-108">PowerShell logs details about PowerShell operations, such as starting and stopping the engine and providers, and executing PowerShell commands.</span></span>

> [!NOTE]
> <span data-ttu-id="118d8-109">Windows PowerShell バージョン3.0、4.0、5.0、および5.1 には、Windows イベントログ用の **EventLog** コマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="118d8-109">Windows PowerShell versions 3.0, 4.0, 5.0, and 5.1 include **EventLog** cmdlets for the Windows event logs.</span></span> <span data-ttu-id="118d8-110">これらのバージョンで、 **EventLog** コマンドレットの一覧を表示するには、「」と入力 `Get-Command -Noun EventLog` します。</span><span class="sxs-lookup"><span data-stu-id="118d8-110">In those versions, to display the list of **EventLog** cmdlets type: `Get-Command -Noun EventLog`.</span></span> <span data-ttu-id="118d8-111">詳細については、コマンドレットのドキュメントと、使用している Windows PowerShell のバージョンの about_EventLogs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="118d8-111">For more information, see the cmdlet documentation and about_EventLogs for your version of Windows PowerShell.</span></span>

## <a name="viewing-the-powershell-event-log-entries-on-windows"></a><span data-ttu-id="118d8-112">Windows での PowerShell イベントログエントリの表示</span><span class="sxs-lookup"><span data-stu-id="118d8-112">Viewing the PowerShell event log entries on Windows</span></span>

<span data-ttu-id="118d8-113">PowerShell ログは、Windows イベントビューアーを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="118d8-113">PowerShell logs can be viewed using the Windows Event Viewer.</span></span> <span data-ttu-id="118d8-114">イベントログは、[アプリケーションとサービスログ] グループにあり、という名前が付けられてい `Microsoft-Windows-PowerShell` ます。</span><span class="sxs-lookup"><span data-stu-id="118d8-114">The event log is located in the Application and Services Logs group and is named `Microsoft-Windows-PowerShell`.</span></span> <span data-ttu-id="118d8-115">関連付けられている ETW プロバイダー `GUID` は `{A0C1853B-5C40-4B15-8766-3CF1C58F985A}` です。</span><span class="sxs-lookup"><span data-stu-id="118d8-115">The associated ETW provider `GUID` is `{A0C1853B-5C40-4B15-8766-3CF1C58F985A}`.</span></span>

<span data-ttu-id="118d8-116">スクリプトブロックのログ記録を有効にすると、PowerShell によって次のイベントがログに記録され `Microsoft-Windows-PowerShell/Operational` ます。</span><span class="sxs-lookup"><span data-stu-id="118d8-116">When Script Block Logging is enabled, PowerShell logs the following events to the `Microsoft-Windows-PowerShell/Operational` log:</span></span>

|<span data-ttu-id="118d8-117">フィールド</span><span class="sxs-lookup"><span data-stu-id="118d8-117">Field</span></span>| <span data-ttu-id="118d8-118">値</span><span class="sxs-lookup"><span data-stu-id="118d8-118">Value</span></span>|
|-|-|
|<span data-ttu-id="118d8-119">EventId</span><span class="sxs-lookup"><span data-stu-id="118d8-119">EventId</span></span>|`4104` / `0x1008`|
|<span data-ttu-id="118d8-120">チャネル</span><span class="sxs-lookup"><span data-stu-id="118d8-120">Channel</span></span>|`Operational`|
|<span data-ttu-id="118d8-121">Level</span><span class="sxs-lookup"><span data-stu-id="118d8-121">Level</span></span>|`Verbose`|
|<span data-ttu-id="118d8-122">オペコード</span><span class="sxs-lookup"><span data-stu-id="118d8-122">Opcode</span></span>|`Create`|
|<span data-ttu-id="118d8-123">タスク</span><span class="sxs-lookup"><span data-stu-id="118d8-123">Task</span></span>|`CommandStart`|
|<span data-ttu-id="118d8-124">Keyword</span><span class="sxs-lookup"><span data-stu-id="118d8-124">Keyword</span></span>|`Runspace`|

## <a name="enabling-script-block-logging"></a><span data-ttu-id="118d8-125">スクリプトブロックのログ記録を有効にする</span><span class="sxs-lookup"><span data-stu-id="118d8-125">Enabling Script Block Logging</span></span>

<span data-ttu-id="118d8-126">スクリプトブロックのログ記録を有効にすると、PowerShell によって処理されるすべてのスクリプトブロックの内容が記録されます。</span><span class="sxs-lookup"><span data-stu-id="118d8-126">When you enable Script Block Logging, PowerShell records the content of all script blocks that it processes.</span></span> <span data-ttu-id="118d8-127">有効にすると、新しい PowerShell セッションによってこの情報がログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="118d8-127">Once enabled, any new PowerShell session logs this information.</span></span>

> [!NOTE]
> <span data-ttu-id="118d8-128">診断以外の目的でスクリプトブロックログを使用する場合は、次に示すように、保護されたイベントログを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="118d8-128">It's recommended to enable Protected Event Logging, as described below, when using Script Block Logging for anything other than diagnostics purposes.</span></span>

<span data-ttu-id="118d8-129">スクリプトブロックのログ記録は、グループポリシーまたはレジストリ設定を使用して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="118d8-129">Script Block Logging can be enabled via Group Policy or a registry setting.</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="118d8-130">グループ ポリシーの使用</span><span class="sxs-lookup"><span data-stu-id="118d8-130">Using Group Policy</span></span>

<span data-ttu-id="118d8-131">自動議事録を有効にするには、グループポリシーでこの機能を有効にし `Turn on PowerShell Script Block
Logging` `Administrative Templates -> Windows
Components -> Windows PowerShell` ます。</span><span class="sxs-lookup"><span data-stu-id="118d8-131">To enable automatic transcription, enable the `Turn on PowerShell Script Block
Logging` feature in Group Policy through `Administrative Templates -> Windows
Components -> Windows PowerShell`.</span></span>

### <a name="using-the-registry"></a><span data-ttu-id="118d8-132">レジストリの使用</span><span class="sxs-lookup"><span data-stu-id="118d8-132">Using the Registry</span></span>

<span data-ttu-id="118d8-133">次の関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="118d8-133">Run the following function:</span></span>

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

## <a name="protected-event-logging"></a><span data-ttu-id="118d8-134">保護されたイベントのログ記録</span><span class="sxs-lookup"><span data-stu-id="118d8-134">Protected Event Logging</span></span>

<span data-ttu-id="118d8-135">システムのログ記録レベルを上げると、ログに記録されたコンテンツに機密データが含まれる可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="118d8-135">Increasing the level of logging on a system increases the possibility that logged content may contain sensitive data.</span></span> <span data-ttu-id="118d8-136">たとえば、スクリプトのログ記録を有効にすると、スクリプトによって使用される資格情報やその他の機密データをイベントログに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="118d8-136">For example, with script logging enabled, credentials or other sensitive data used by a script can be written to the event log.</span></span> <span data-ttu-id="118d8-137">機密データがログに記録されているコンピューターが侵害されると、ログによって、攻撃者は、それらの情報を拡張するために必要な情報を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="118d8-137">When a machine that has logged sensitive data is compromised, the logs can provide an attacker with information needed to extend their reach.</span></span>

<span data-ttu-id="118d8-138">この情報を保護するために、Windows 10 では保護されたイベントログが導入されています。</span><span class="sxs-lookup"><span data-stu-id="118d8-138">To protect this information, Windows 10 introduces Protected Event Logging.</span></span>
<span data-ttu-id="118d8-139">保護されたイベントログを使用すると、参加アプリケーションは、イベントログに書き込まれた機密データを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="118d8-139">Protected Event Logging lets participating applications encrypt sensitive data written to the event log.</span></span> <span data-ttu-id="118d8-140">後で、より安全で集中管理されたログコレクター上で、これらのログの暗号化を解除して処理することができます。</span><span class="sxs-lookup"><span data-stu-id="118d8-140">Later, you can decrypt and process these logs on a more secure and centralized log collector.</span></span>

<span data-ttu-id="118d8-141">イベントログの内容は、IETF Cryptographic Message 構文 (CMS) 標準を使用して保護されています。</span><span class="sxs-lookup"><span data-stu-id="118d8-141">Event log content is protected using the IETF Cryptographic Message Syntax (CMS) standard.</span></span> <span data-ttu-id="118d8-142">CMS は公開キー暗号化を使用します。</span><span class="sxs-lookup"><span data-stu-id="118d8-142">CMS uses public key cryptography.</span></span> <span data-ttu-id="118d8-143">コンテンツの暗号化とコンテンツの暗号化解除に使用されるキーは、個別に保持されます。</span><span class="sxs-lookup"><span data-stu-id="118d8-143">The keys used to encrypt content and decrypt content are kept separate.</span></span>

<span data-ttu-id="118d8-144">公開キーは広く共有でき、機密性の高いデータではありません。</span><span class="sxs-lookup"><span data-stu-id="118d8-144">The public key can be shared widely and isn't sensitive data.</span></span> <span data-ttu-id="118d8-145">この公開キーで暗号化されたコンテンツは、秘密キーによってのみ復号化できます。</span><span class="sxs-lookup"><span data-stu-id="118d8-145">Any content encrypted with this public key can only be decrypted by the private key.</span></span> <span data-ttu-id="118d8-146">公開キー暗号化の詳細については、「 [Wikipedia-公開キー暗号化](https://en.wikipedia.org/wiki/Public-key_cryptography)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="118d8-146">For more information about Public Key Cryptography, see [Wikipedia - Public Key Cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="118d8-147">保護されたイベントログポリシーを有効にするには、保護するイベントログデータがあるすべてのコンピューターに公開キーを展開します。</span><span class="sxs-lookup"><span data-stu-id="118d8-147">To enable a Protected Event Logging policy, deploy a public key to all machines that have event log data to protect.</span></span> <span data-ttu-id="118d8-148">対応する秘密キーは、中央のイベントログコレクターや [SIEM][] アグリゲーターなどのより安全な場所でイベントログを後処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="118d8-148">The corresponding private key is used to post-process the event logs at a more secure location such as a central event log collector, or [SIEM][] aggregator.</span></span> <span data-ttu-id="118d8-149">Azure で SIEM を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="118d8-149">You can set up SIEM in Azure.</span></span> <span data-ttu-id="118d8-150">詳細については、「 [GENERIC SIEM integration](/cloud-app-security/siem)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="118d8-150">For more information, see [Generic SIEM integration](/cloud-app-security/siem).</span></span>

### <a name="enabling-protected-event-logging-via-group-policy"></a><span data-ttu-id="118d8-151">グループポリシーを使用した保護されたイベントのログ記録の有効化</span><span class="sxs-lookup"><span data-stu-id="118d8-151">Enabling Protected Event Logging via Group Policy</span></span>

<span data-ttu-id="118d8-152">保護されたイベントのログ記録を有効にするには、 `Enable Protected Event Logging` グループポリシーで機能を有効に `Administrative Templates -> Windows Components
-> Event Logging` します。</span><span class="sxs-lookup"><span data-stu-id="118d8-152">To enable Protected Event Logging, enable the `Enable Protected Event Logging` feature in Group Policy through `Administrative Templates -> Windows Components
-> Event Logging`.</span></span> <span data-ttu-id="118d8-153">この設定には暗号化証明書が必要です。暗号化証明書は、次のいずれかの形式で指定できます。</span><span class="sxs-lookup"><span data-stu-id="118d8-153">This setting requires an encryption certificate, which you can provide in one of several forms:</span></span>

- <span data-ttu-id="118d8-154">Base-64 でエンコードされた x.509 証明書のコンテンツ ( `Export` 証明書マネージャーのオプションによって提供されるなど)。</span><span class="sxs-lookup"><span data-stu-id="118d8-154">The content of a base-64 encoded X.509 certificate (for example, as offered by the `Export` option in Certificate Manager).</span></span>
- <span data-ttu-id="118d8-155">ローカルコンピューターの証明書ストアにある証明書の拇印 (PKI インフラストラクチャで展開できます)。</span><span class="sxs-lookup"><span data-stu-id="118d8-155">The thumbprint of a certificate that can be found in the Local Machine certificate store (can be deployed by PKI infrastructure).</span></span>
- <span data-ttu-id="118d8-156">証明書の完全なパス (ローカルまたはリモート共有を指定できます)。</span><span class="sxs-lookup"><span data-stu-id="118d8-156">The full path to a certificate (can be local, or a remote share).</span></span>
- <span data-ttu-id="118d8-157">証明書または証明書を含むディレクトリへのパス (ローカルまたはリモート共有を指定できます)。</span><span class="sxs-lookup"><span data-stu-id="118d8-157">The path to a directory containing a certificate or certificates (can be local, or a remote share).</span></span>
- <span data-ttu-id="118d8-158">ローカルコンピューターの証明書ストアで検索できる証明書のサブジェクト名 (PKI インフラストラクチャによって展開できます)。</span><span class="sxs-lookup"><span data-stu-id="118d8-158">The subject name of a certificate that can be found in the Local Machine certificate store (can be deployed by PKI infrastructure).</span></span>

<span data-ttu-id="118d8-159">結果として得られる証明書は、 `Document Encryption` 拡張キー使用法 () として、 `1.3.6.1.4.1.311.80.1` `Data Encipherment` またはまたは `Key
Encipherment` キー使用法が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="118d8-159">The resulting certificate must have `Document Encryption` as an enhanced key usage (`1.3.6.1.4.1.311.80.1`), and either `Data Encipherment` or `Key
Encipherment` key usages enabled.</span></span>

> [!WARNING]
> <span data-ttu-id="118d8-160">秘密キーは、イベントのログを記録するマシンにデプロイしないでください。</span><span class="sxs-lookup"><span data-stu-id="118d8-160">The private key shouldn't be deployed to the machines logging events.</span></span> <span data-ttu-id="118d8-161">メッセージの暗号化を解除する安全な場所に保管しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="118d8-161">It should be kept in a secure location where you decrypt the messages.</span></span>

### <a name="decrypting-protected-event-logging-messages"></a><span data-ttu-id="118d8-162">保護されたイベントログメッセージの復号化</span><span class="sxs-lookup"><span data-stu-id="118d8-162">Decrypting Protected Event Logging messages</span></span>

<span data-ttu-id="118d8-163">次のスクリプトは、秘密キーがあることを前提として、取得と復号化を行います。</span><span class="sxs-lookup"><span data-stu-id="118d8-163">The following script will retrieve and decrypt, assuming that you have the private key:</span></span>

```powershell
Get-WinEvent Microsoft-Windows-PowerShell/Operational |
  Where-Object Id -eq 4104 | Unprotect-CmsMessage
```

## <a name="see-also"></a><span data-ttu-id="118d8-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="118d8-164">See also</span></span>

[<span data-ttu-id="118d8-165">Blue Team の PowerShell</span><span class="sxs-lookup"><span data-stu-id="118d8-165">PowerShell the Blue Team</span></span>](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)

[<span data-ttu-id="118d8-166">汎用 SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="118d8-166">Generic SIEM integration</span></span>](/cloud-app-security/siem)

<!-- link references -->
[SIEM]: https://wikipedia.org/wiki/Security_information_and_event_management