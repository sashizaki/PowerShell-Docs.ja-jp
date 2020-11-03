---
description: PowerShell の実行ポリシーに準拠するようにスクリプトに署名する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 07/31/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_signing?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Signing
ms.openlocfilehash: ae0e9290696d8b50fce29137f98721220e7511c7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221155"
---
# <a name="about-signing"></a><span data-ttu-id="4c9cd-104">署名について</span><span class="sxs-lookup"><span data-stu-id="4c9cd-104">About Signing</span></span>

## <a name="short-description"></a><span data-ttu-id="4c9cd-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="4c9cd-105">Short description</span></span>
<span data-ttu-id="4c9cd-106">PowerShell の実行ポリシーに準拠するようにスクリプトに署名する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-106">Explains how to sign scripts so that they comply with the PowerShell execution policies.</span></span>

## <a name="long-description"></a><span data-ttu-id="4c9cd-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="4c9cd-107">Long description</span></span>

<span data-ttu-id="4c9cd-108">制限された実行ポリシーでは、スクリプトの実行は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-108">The Restricted execution policy does not permit any scripts to run.</span></span> <span data-ttu-id="4c9cd-109">**AllSigned** と **RemoteSigned** の実行ポリシーによって、PowerShell がデジタル署名のないスクリプトを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-109">The **AllSigned** and **RemoteSigned** execution policies prevent PowerShell from running scripts that do not have a digital signature.</span></span>

<span data-ttu-id="4c9cd-110">このトピックでは、実行ポリシーが **RemoteSigned** されている場合でも、署名されていない選択したスクリプトを実行する方法と、独自に使用するスクリプトに署名する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-110">This topic explains how to run selected scripts that are not signed, even while the execution policy is **RemoteSigned** , and how to sign scripts for your own use.</span></span>

<span data-ttu-id="4c9cd-111">PowerShell 実行ポリシーの詳細については、「 [about_Execution_Policies](about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-111">For more information about PowerShell execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

## <a name="to-permit-signed-scripts-to-run"></a><span data-ttu-id="4c9cd-112">署名されたスクリプトの実行を許可するには</span><span class="sxs-lookup"><span data-stu-id="4c9cd-112">To permit signed scripts to run</span></span>

<span data-ttu-id="4c9cd-113">コンピューターで PowerShell を初めて起動するときは、 **制限** された実行ポリシー (既定) が有効になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-113">When you start PowerShell on a computer for the first time, the **Restricted** execution policy (the default) is likely to be in effect.</span></span>

<span data-ttu-id="4c9cd-114">**制限付き** ポリシーでは、スクリプトの実行は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-114">The **Restricted** policy does not permit any scripts to run.</span></span>

<span data-ttu-id="4c9cd-115">コンピューターで有効な実行ポリシーを見つけるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-115">To find the effective execution policy on your computer, type:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="4c9cd-116">ローカルコンピューター上で作成され、他のユーザーから署名されたスクリプトを実行するには、[管理者として実行] オプションを使用して PowerShell を起動し、次のコマンドを使用してコンピューターの実行ポリシーを **RemoteSigned** に変更します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-116">To run unsigned scripts that you write on your local computer and signed scripts from other users, start PowerShell with the Run as Administrator option and then use the following command to change the execution policy on the computer to **RemoteSigned** :</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

<span data-ttu-id="4c9cd-117">詳細については、コマンドレットのヘルプトピックを参照してください `Set-ExecutionPolicy` 。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-117">For more information, see the help topic for the `Set-ExecutionPolicy` cmdlet.</span></span>

## <a name="running-unsigned-scripts-using-the-remotesigned-execution-policy"></a><span data-ttu-id="4c9cd-118">RemoteSigned 実行ポリシーを使用した未署名のスクリプトの実行</span><span class="sxs-lookup"><span data-stu-id="4c9cd-118">Running unsigned scripts using the RemoteSigned execution policy</span></span>

<span data-ttu-id="4c9cd-119">PowerShell の実行ポリシーが **RemoteSigned** の場合、電子メールやインスタントメッセージングプログラムを通じて受信する署名されていないスクリプトを含め、インターネットからダウンロードされた未署名のスクリプトは実行されません。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-119">If your PowerShell execution policy is **RemoteSigned** , PowerShell will not run unsigned scripts that are downloaded from the internet, including unsigned scripts you receive through email and instant messaging programs.</span></span>

<span data-ttu-id="4c9cd-120">ダウンロードしたスクリプトを実行しようとすると、PowerShell によって次のエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-120">If you try to run a downloaded script, PowerShell displays the following error message:</span></span>

```Output
The file <file-name> cannot be loaded. The file <file-name> is not digitally
signed. The script will not execute on the system. Please see "Get-Help
about_Signing" for more details.
```

<span data-ttu-id="4c9cd-121">スクリプトを実行する前に、コードを確認して、信頼できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-121">Before you run the script, review the code to be sure that you trust it.</span></span>
<span data-ttu-id="4c9cd-122">スクリプトは、実行可能プログラムと同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-122">Scripts have the same effect as any executable program.</span></span>

<span data-ttu-id="4c9cd-123">署名されていないスクリプトを実行するには、Unblock-File コマンドレットを使用するか、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-123">To run an unsigned script, use the Unblock-File cmdlet or use the following procedure.</span></span>

1. <span data-ttu-id="4c9cd-124">スクリプトファイルをコンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-124">Save the script file on your computer.</span></span>
2. <span data-ttu-id="4c9cd-125">[スタート] をクリックし、[マイコンピューター] をクリックして、保存されているスクリプトファイルを探します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-125">Click Start, click My Computer, and locate the saved script file.</span></span>
3. <span data-ttu-id="4c9cd-126">スクリプトファイルを右クリックし、[プロパティ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-126">Right-click the script file, and then click Properties.</span></span>
4. <span data-ttu-id="4c9cd-127">[ブロックの解除] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-127">Click Unblock.</span></span>

<span data-ttu-id="4c9cd-128">インターネットからダウンロードされたスクリプトがデジタル署名されていても、その発行元を信頼するように選択していない場合は、PowerShell によって次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-128">If a script that was downloaded from the internet is digitally signed, but you have not yet chosen to trust its publisher, PowerShell displays the following message:</span></span>

```Output
Do you want to run software from this untrusted publisher?
The file <file-name> is published by CN=<publisher-name>. This
publisher is not trusted on your system. Only run scripts
from trusted publishers.

[V] Never run  [D] Do not run  [R] Run once  [A] Always run
[?] Help (default is "D"):
```

<span data-ttu-id="4c9cd-129">発行元を信頼する場合は、[一度だけ実行する] または [常に実行する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-129">If you trust the publisher, select "Run once" or "Always run."</span></span> <span data-ttu-id="4c9cd-130">発行元を信頼していない場合は、[実行しない] または [実行しない] のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-130">If you do not trust the publisher, select either "Never run" or "Do not run."</span></span> <span data-ttu-id="4c9cd-131">[実行しない] または [常に実行する] を選択した場合、PowerShell はこのパブリッシャーに対して再度メッセージを表示しません。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-131">If you select "Never run" or "Always run," PowerShell will not prompt you again for this publisher.</span></span>

## <a name="methods-of-signing-scripts"></a><span data-ttu-id="4c9cd-132">スクリプトの署名方法</span><span class="sxs-lookup"><span data-stu-id="4c9cd-132">Methods of signing scripts</span></span>

<span data-ttu-id="4c9cd-133">作成したスクリプトと他のソースから取得したスクリプトに署名することができます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-133">You can sign the scripts that you write and the scripts that you obtain from other sources.</span></span> <span data-ttu-id="4c9cd-134">任意のスクリプトに署名する前に、各コマンドを調べて、実行しても安全かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-134">Before you sign any script, examine each command to verify that it is safe to run.</span></span>

<span data-ttu-id="4c9cd-135">コード署名のベストプラクティスについては、「 [コード署名のベストプラクティス](/previous-versions/windows/hardware/design/dn653556(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-135">For best practices about code signing, see [Code-Signing Best Practices](/previous-versions/windows/hardware/design/dn653556(v=vs.85)).</span></span>

<span data-ttu-id="4c9cd-136">スクリプトファイルに署名する方法の詳細については、「 [get-authenticodesignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-136">For more information about how to sign a script file, see [Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature).</span></span>

<span data-ttu-id="4c9cd-137">`New-SelfSignedCertificate`PowerShell 3.0 の PKI モジュールで導入されたコマンドレットは、テストに適した自己署名証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-137">The `New-SelfSignedCertificate` cmdlet, introduced in the PKI module in PowerShell 3.0, creates a self-signed certificate that is Appropriate for testing.</span></span> <span data-ttu-id="4c9cd-138">詳細については、New-SelfSignedCertificate コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-138">For more information, see the help topic for the New-SelfSignedCertificate cmdlet.</span></span>

<span data-ttu-id="4c9cd-139">デジタル署名をスクリプトに追加するには、コード署名証明書を使用して署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-139">To add a digital signature to a script, you must sign it with a code signing certificate.</span></span> <span data-ttu-id="4c9cd-140">スクリプトファイルの署名には、次の2種類の証明書が適しています。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-140">Two types of certificates are suitable for signing a script file:</span></span>

- <span data-ttu-id="4c9cd-141">証明機関によって作成された証明書: 有料では、パブリック証明機関が id を検証し、コード署名証明書を提供します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-141">Certificates that are created by a certification authority: For a fee, a public certification authority verifies your identity and gives you a code signing certificate.</span></span> <span data-ttu-id="4c9cd-142">信頼できる証明機関から証明書を購入すると、他のコンピューターが証明機関を信頼しているため、Windows を実行している他のコンピューターのユーザーとスクリプトを共有できます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-142">When you purchase your certificate from a reputable certification authority, you are able to share your script with users on other computers that are running Windows because those other computers trust the certification authority.</span></span>

- <span data-ttu-id="4c9cd-143">証明書を作成する: 自分のコンピューターが証明書を作成する機関である自己署名証明書を作成できます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-143">Certificates that you create: You can create a self-signed certificate for which your computer is the authority that creates the certificate.</span></span> <span data-ttu-id="4c9cd-144">この証明書は無料で使用でき、コンピューター上でスクリプトの記述、署名、および実行を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-144">This certificate is free of charge and enables you to write, sign, and run scripts on your computer.</span></span> <span data-ttu-id="4c9cd-145">ただし、自己署名証明書によって署名されたスクリプトは、他のコンピューターでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-145">However, a script signed by a self-signed certificate will not run on other computers.</span></span>

<span data-ttu-id="4c9cd-146">通常は、自己署名証明書を使用して、自分で使用するために作成したスクリプトに署名したり、安全であることを確認した他のソースから取得したスクリプトに署名したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-146">Typically, you would use a self-signed certificate only to sign scripts that you write for your own use and to sign scripts that you get from other sources that you have verified to be safe.</span></span> <span data-ttu-id="4c9cd-147">企業内でも共有されるスクリプトには適していません。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-147">It is not appropriate for scripts that will be shared, even within an enterprise.</span></span>

<span data-ttu-id="4c9cd-148">自己署名証明書を作成する場合は、証明書に対して強力な秘密キーの保護を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-148">If you create a self-signed certificate, be sure to enable strong private key protection on your certificate.</span></span> <span data-ttu-id="4c9cd-149">これにより、悪意のあるプログラムがユーザーに代わってスクリプトに署名するのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-149">This prevents malicious programs from signing scripts on your behalf.</span></span> <span data-ttu-id="4c9cd-150">手順については、このトピックの最後に記載されています。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-150">The instructions are included at the end of this topic.</span></span>

## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="4c9cd-151">自己署名証明書の作成</span><span class="sxs-lookup"><span data-stu-id="4c9cd-151">Create a self-signed certificate</span></span>

<span data-ttu-id="4c9cd-152">自己署名証明書を作成するには、 `New-SelfSignedCertificate` PKI モジュールのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-152">To create a self-signed certificate use the `New-SelfSignedCertificate` cmdlet in the PKI module.</span></span> <span data-ttu-id="4c9cd-153">このモジュールは PowerShell 3.0 で導入され、Windows 8 および Windows Server 2012 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-153">This module is introduced in PowerShell 3.0 and is included in Windows 8 and Windows Server 2012.</span></span> <span data-ttu-id="4c9cd-154">詳細については、コマンドレットのヘルプトピックを参照してください `New-SelfSignedCertificate` 。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-154">For more information, see the help topic for the `New-SelfSignedCertificate` cmdlet.</span></span>

<span data-ttu-id="4c9cd-155">以前のバージョンの Windows で自己署名証明書を作成するには、証明書作成ツールを使用し `MakeCert.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-155">To create a self-signed certificate in earlier versions of Windows, use the Certificate Creation tool `MakeCert.exe`.</span></span> <span data-ttu-id="4c9cd-156">このツールは、Microsoft .NET SDK (バージョン1.1 以降) と Microsoft Windows SDK に含まれています。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-156">This tool is included in the Microsoft .NET SDK (versions 1.1 and later) and in the Microsoft Windows SDK.</span></span>

<span data-ttu-id="4c9cd-157">MakeCert.exe ツールの構文とパラメーターの説明の詳細については、「 [証明書作成ツール (MakeCert.exe)](/previous-versions/dotnet/netframework-2.0/bfsktky3(v=vs.80))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-157">For more information about the syntax and the parameter descriptions of the MakeCert.exe tool, see [Certificate Creation Tool (MakeCert.exe)](/previous-versions/dotnet/netframework-2.0/bfsktky3(v=vs.80)).</span></span>

<span data-ttu-id="4c9cd-158">MakeCert.exe ツールを使用して証明書を作成するには、SDK コマンドプロンプトウィンドウで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-158">To use the MakeCert.exe tool to create a certificate, run the following commands in an SDK Command Prompt window.</span></span>

<span data-ttu-id="4c9cd-159">注: 最初のコマンドは、コンピューターのローカル証明機関を作成します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-159">Note: The first command creates a local certification authority for your computer.</span></span> <span data-ttu-id="4c9cd-160">2番目のコマンドは、証明機関から個人証明書を生成します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-160">The second command generates a personal certificate from the certification authority.</span></span>

<span data-ttu-id="4c9cd-161">注: コマンドは、表示されたとおりにコピーまたは入力できます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-161">Note: You can copy or type the commands exactly as they appear.</span></span> <span data-ttu-id="4c9cd-162">証明書の名前は変更できますが、置換は不要です。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-162">No substitutions are necessary, although you can change the certificate name.</span></span>

```powershell
makecert -n "CN=PowerShell Local Certificate Root" -a sha1 `
-eku 1.3.6.1.5.5.7.3.3 -r -sv root.pvk root.cer `
-ss Root -sr localMachine

makecert -pe -n "CN=PowerShell User" -ss MY -a sha1 `
-eku 1.3.6.1.5.5.7.3.3 -iv root.pvk -ic root.cer
```

<span data-ttu-id="4c9cd-163">MakeCert.exe ツールでは、秘密キーのパスワードの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-163">The MakeCert.exe tool will prompt you for a private key password.</span></span> <span data-ttu-id="4c9cd-164">パスワードは、同意せずに証明書を使用またはアクセスできないようにします。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-164">The password ensures that no one can use or access the certificate without your consent.</span></span>
<span data-ttu-id="4c9cd-165">覚えやすいパスワードを作成して入力します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-165">Create and enter a password that you can remember.</span></span> <span data-ttu-id="4c9cd-166">このパスワードは後で証明書を取得するために使用します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-166">You will use this password later to retrieve the certificate.</span></span>

<span data-ttu-id="4c9cd-167">証明書が正しく生成されたことを確認するには、次のコマンドを使用して、コンピューター上の証明書ストアにある証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-167">To verify that the certificate was generated correctly, use the following command to get the certificate in the certificate store on the computer.</span></span> <span data-ttu-id="4c9cd-168">証明書ファイルがファイルシステムディレクトリに見つかりません。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-168">You will not find a certificate file in the file system directory.</span></span>

<span data-ttu-id="4c9cd-169">PowerShell プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-169">At the PowerShell prompt, type:</span></span>

```powershell
Get-ChildItem cert:\CurrentUser\my -codesigning
```

<span data-ttu-id="4c9cd-170">このコマンドは、PowerShell 証明書プロバイダーを使用して、証明書に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-170">This command uses the PowerShell Certificate provider to view information about the certificate.</span></span>

<span data-ttu-id="4c9cd-171">証明書が作成された場合、出力には、次のような画面で証明書を識別する **サムプリント** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-171">If the certificate was created, the output shows the **thumbprint** that identifies the certificate in a display that resembles the following:</span></span>

```Output
Directory: Microsoft.PowerShell.Security\Certificate::CurrentUser\My

Thumbprint                                Subject
----------                                -------
4D4917CB140714BA5B81B96E0B18AAF2C4564FDF  CN=PowerShell User ]
```

## <a name="sign-a-script"></a><span data-ttu-id="4c9cd-172">スクリプトに署名する</span><span class="sxs-lookup"><span data-stu-id="4c9cd-172">Sign a script</span></span>

<span data-ttu-id="4c9cd-173">自己署名証明書を作成したら、スクリプトに署名することができます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-173">After you create a self-signed certificate, you can sign scripts.</span></span> <span data-ttu-id="4c9cd-174">**AllSigned** 実行ポリシーを使用すると、スクリプトに署名することで、コンピューターでスクリプトを実行することが許可されます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-174">If you use the **AllSigned** execution policy, signing a script permits you to run the script on your computer.</span></span>

<span data-ttu-id="4c9cd-175">次のサンプルスクリプトでは、 `Add-Signature.ps1` スクリプトに署名します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-175">The following sample script, `Add-Signature.ps1`, signs a script.</span></span> <span data-ttu-id="4c9cd-176">ただし、 **AllSigned** 実行ポリシーを使用している場合は、スクリプトを実行する前に署名する必要があり `Add-Signature.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-176">However, if you are using the **AllSigned** execution policy, you must sign the `Add-Signature.ps1` script before you run it.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c9cd-177">スクリプトは、ASCII または UTF8NoBOM エンコードを使用して保存する必要があります。別のエンコードを使用するスクリプトファイルに署名することができます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-177">The script must be saved using ASCII or UTF8NoBOM encoding.You can sign a script file that uses a different encoding.</span></span> <span data-ttu-id="4c9cd-178">ただし、スクリプトを実行できないか、スクリプトを含むモジュールをインポートできません。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-178">But the script fails to run or the module containing the script fails to import.</span></span>

<span data-ttu-id="4c9cd-179">このスクリプトを使用するには、テキストファイルに次のテキストをコピーして、という名前を指定し `Add-Signature.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-179">To use this script, copy the following text into a text file, and name it `Add-Signature.ps1`.</span></span>

```powershell
## Signs a file
param([string] $file=$(throw "Please specify a filename."))
$cert = @(Get-ChildItem cert:\CurrentUser\My -codesigning)[0]
Set-AuthenticodeSignature $file $cert
```

<span data-ttu-id="4c9cd-180">スクリプトファイルに署名するには `Add-Signature.ps1` 、PowerShell コマンドプロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-180">To sign the `Add-Signature.ps1` script file, type the following commands at the PowerShell command prompt:</span></span>

```powershell
$cert = @(Get-ChildItem cert:\CurrentUser\My -codesigning)[0]
Set-AuthenticodeSignature add-signature.ps1 $cert
```

<span data-ttu-id="4c9cd-181">スクリプトが署名されたら、ローカルコンピューターで実行できます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-181">After the script is signed, you can run it on the local computer.</span></span> <span data-ttu-id="4c9cd-182">ただし、このスクリプトは、PowerShell の実行ポリシーが信頼できる機関からのデジタル署名を必要とするコンピューターでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-182">However, the script will not run on computers on which the PowerShell execution policy requires a digital signature from a trusted authority.</span></span> <span data-ttu-id="4c9cd-183">試行すると、PowerShell によって次のエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-183">If you try, PowerShell displays the following error message:</span></span>

```Output
The file C:\remote_file.ps1 cannot be loaded. The signature of the
certificate cannot be verified.
At line:1 char:15
+ .\ remote_file.ps1 <<<<
```

<span data-ttu-id="4c9cd-184">書き込みが行われていないスクリプトを実行したときに PowerShell でこのメッセージが表示される場合は、署名されていないスクリプトを扱う場合と同様に、ファイルを扱います。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-184">If PowerShell displays this message when you run a script that you did not write, treat the file as you would treat any unsigned script.</span></span> <span data-ttu-id="4c9cd-185">コードを確認して、スクリプトを信頼できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-185">Review the code to determine whether you can trust the script.</span></span>

## <a name="enable-strong-private-key-protection-for-your-certificate"></a><span data-ttu-id="4c9cd-186">証明書の秘密キーの強力な保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="4c9cd-186">Enable strong private key protection for your certificate</span></span>

<span data-ttu-id="4c9cd-187">コンピューターにプライベート証明書がある場合は、悪意のあるプログラムによって、ユーザーに代わってスクリプトに署名できる可能性があります。これにより、PowerShell の実行が承認されます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-187">If you have a private certificate on your computer, malicious programs might be able to sign scripts on your behalf, which authorizes PowerShell to run them.</span></span>

<span data-ttu-id="4c9cd-188">自動的に署名を行わないようにするには、証明書マネージャーを使用し `Certmgr.exe` て署名証明書をファイルにエクスポートし `.pfx` ます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-188">To prevent automated signing on your behalf, use Certificate Manager `Certmgr.exe` to export your signing certificate to a `.pfx` file.</span></span> <span data-ttu-id="4c9cd-189">証明書マネージャーは、Microsoft .NET SDK、Microsoft Windows SDK、および internet Explorer に含まれています。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-189">Certificate Manager is included in the Microsoft .NET SDK, the Microsoft Windows SDK, and in internet Explorer.</span></span>

<span data-ttu-id="4c9cd-190">証明書をエクスポートするには:</span><span class="sxs-lookup"><span data-stu-id="4c9cd-190">To export the certificate:</span></span>

1. <span data-ttu-id="4c9cd-191">証明書マネージャーを起動します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-191">Start Certificate Manager.</span></span>
2. <span data-ttu-id="4c9cd-192">PowerShell ローカル証明書のルートによって発行された証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-192">Select the certificate issued by PowerShell Local Certificate Root.</span></span>
3. <span data-ttu-id="4c9cd-193">[エクスポート] をクリックして、証明書のエクスポートウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-193">Click Export to start the Certificate Export Wizard.</span></span>
4. <span data-ttu-id="4c9cd-194">[はい、秘密キーをエクスポートします] を選択し、[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-194">Select "Yes, export the private key", and then click Next.</span></span>
5. <span data-ttu-id="4c9cd-195">[強力な保護を有効にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-195">Select "Enable strong protection."</span></span>
6. <span data-ttu-id="4c9cd-196">パスワードを入力し、確認のためにもう一度入力します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-196">Type a password, and then type it again to confirm.</span></span>
7. <span data-ttu-id="4c9cd-197">ファイル名拡張子が .pfx のファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-197">Type a file name that has the .pfx file name extension.</span></span>
8. <span data-ttu-id="4c9cd-198">[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-198">Click Finish.</span></span>

<span data-ttu-id="4c9cd-199">証明書を再インポートするには:</span><span class="sxs-lookup"><span data-stu-id="4c9cd-199">To re-import the certificate:</span></span>

1. <span data-ttu-id="4c9cd-200">証明書マネージャーを起動します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-200">Start Certificate Manager.</span></span>
2. <span data-ttu-id="4c9cd-201">[インポート] をクリックして、証明書のインポートウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-201">Click Import to start the Certificate Import Wizard.</span></span>
3. <span data-ttu-id="4c9cd-202">エクスポートプロセスで作成した .pfx ファイルの場所を開きます。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-202">Open to the location of the .pfx file that you created during the export process.</span></span>
4. <span data-ttu-id="4c9cd-203">[パスワード] ページで、[秘密キーの保護を強力にする] を選択し、エクスポート処理中に割り当てたパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-203">On the Password page, select "Enable strong private key protection", and then enter the password that you assigned during the export process.</span></span>
5. <span data-ttu-id="4c9cd-204">[ 個人 ] 証明書ストアを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-204">Select the Personal certificate store.</span></span>
6. <span data-ttu-id="4c9cd-205">[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-205">Click Finish.</span></span>

## <a name="prevent-the-signature-from-expiring"></a><span data-ttu-id="4c9cd-206">署名の有効期限が切れないようにする</span><span class="sxs-lookup"><span data-stu-id="4c9cd-206">Prevent the signature from expiring</span></span>

<span data-ttu-id="4c9cd-207">スクリプトのデジタル署名は、署名証明書の有効期限が切れている間に、署名証明書の有効期限が切れるか、タイムスタンプサーバーでスクリプトが署名されたことを確認できる限り有効です。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-207">The digital signature in a script is valid until the signing certificate expires or as long as a timestamp server can verify that the script was signed while the signing certificate was valid.</span></span>

<span data-ttu-id="4c9cd-208">ほとんどの署名証明書は1年間有効であるため、タイムスタンプサーバーを使用すると、ユーザーがスクリプトを何年も使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4c9cd-208">Because most signing certificates are valid for one year only, using a time stamp server ensures that users can use your script for many years to come.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c9cd-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c9cd-209">See also</span></span>

[<span data-ttu-id="4c9cd-210">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="4c9cd-210">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="4c9cd-211">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="4c9cd-211">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="4c9cd-212">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="4c9cd-212">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="4c9cd-213">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="4c9cd-213">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="4c9cd-214">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="4c9cd-214">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

<span data-ttu-id="4c9cd-215">[コード署名の概要](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537361(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="4c9cd-215">[Introduction to Code Signing](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537361(v=vs.85))</span></span>
