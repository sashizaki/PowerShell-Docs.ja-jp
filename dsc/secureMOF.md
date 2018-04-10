---
ms.date: 10/31/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: MOF ファイルのセキュリティ保護
ms.openlocfilehash: 80ef37ef1bdcb0a8b0ad343b4eab99f1bc66e116
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="securing-the-mof-file"></a><span data-ttu-id="abdaf-103">MOF ファイルのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="abdaf-103">Securing the MOF File</span></span>

><span data-ttu-id="abdaf-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="abdaf-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="abdaf-105">DSC では、ローカル構成マネージャー (LCM) が必要な終了状態を実装する、MOF ファイルに格納されている情報を適用することで、サーバー ノードの構成を管理します。</span><span class="sxs-lookup"><span data-stu-id="abdaf-105">DSC manages the configuration of server nodes by applying information stored in a MOF file, where the Local Configuration Manager (LCM) implements the desired end state.</span></span>
<span data-ttu-id="abdaf-106">このファイルには構成の詳細が含まれているため、安全に保つことが重要です。</span><span class="sxs-lookup"><span data-stu-id="abdaf-106">Because this file contains the details of the configuration, it’s important to keep it secure.</span></span>
<span data-ttu-id="abdaf-107">このトピックでは、ターゲット ノードがファイルを暗号化したことを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="abdaf-107">This topic describes how to ensure the target node has encrypted the file.</span></span>

<span data-ttu-id="abdaf-108">PowerShell バージョン 5.0 以降では、**Start-DSCConfiguration** コマンドレットを使用してノードに適用されている場合、MOF ファイル全体が既定で暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="abdaf-108">Beginning with PowerShell version 5.0, the entire MOF file is encrypted by default when it is applied to the node using the **Start-DSCConfiguration** cmdlet.</span></span>
<span data-ttu-id="abdaf-109">この記事で説明されているプロセスが必要になるのは、証明書が管理されていない場合にプル サービス プロトコルを使用してソリューションを実装する場合のみです。これにより、ターゲット ノードによってダウンロードされた構成を暗号化解除し、適用される前にシステムで読み取れるようになります (たとえば、Windows Server でプル サービスが使用できるようになります)。</span><span class="sxs-lookup"><span data-stu-id="abdaf-109">The process described in this article is required only when implementing a solution using the pull service protocol if certificates are not managed, to ensure configurations downloaded by the target node can be decrypted and read by the system before they are applied (for example, the pull service available in Windows Server).</span></span>
<span data-ttu-id="abdaf-110">[Azure Automation DSC](https://docs.microsoft.com/azure/automation/automation-dsc-overview) に登録されているノードには自動的に証明書がインストールされ、サービスによって管理されます。管理オーバーヘッドは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="abdaf-110">Nodes registered to [Azure Automation DSC](https://docs.microsoft.com/azure/automation/automation-dsc-overview) will automatically have certificates installed and managed by the service with no administrative overhead required.</span></span>

><span data-ttu-id="abdaf-111">**注:** このトピックでは、暗号化に使用する証明書について説明します。</span><span class="sxs-lookup"><span data-stu-id="abdaf-111">**Note:** This topic discusses certificates used for encryption.</span></span>
><span data-ttu-id="abdaf-112">暗号化には、自己署名証明書で十分です。秘密キーは常に秘密に保たれますし、暗号化はドキュメントの信頼性を意味しないからです。</span><span class="sxs-lookup"><span data-stu-id="abdaf-112">For encryption, a self-signed certificate is sufficient, because the private key is always kept secret and encryption does not imply trust of the document.</span></span>
><span data-ttu-id="abdaf-113">認証の目的では、自己署名証明書を使用*しないでください*。</span><span class="sxs-lookup"><span data-stu-id="abdaf-113">Self-signed certificates should *not* be used for authentication purposes.</span></span>
><span data-ttu-id="abdaf-114">認証の目的では、常に信頼された証明機関 (CA) からの証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abdaf-114">You should use a certificate from a trusted Certification Authority (CA) for any authentication purposes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="abdaf-115">前提条件</span><span class="sxs-lookup"><span data-stu-id="abdaf-115">Prerequisites</span></span>

<span data-ttu-id="abdaf-116">DSC 構成のセキュリティ保護に使用される資格情報を正常に暗号化するには、次のものが必要になります。</span><span class="sxs-lookup"><span data-stu-id="abdaf-116">To successfully encrypt the credentials used to secure a DSC configuration, make sure you have the following:</span></span>

* <span data-ttu-id="abdaf-117">**証明書を発行して配布するための手段**。</span><span class="sxs-lookup"><span data-stu-id="abdaf-117">**Some means of issuing and distributing certificates**.</span></span> <span data-ttu-id="abdaf-118">このトピックとその例では、Active Directory 証明機関を使用することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="abdaf-118">This topic and its examples assume you are using Active Directory Certification Authority.</span></span> <span data-ttu-id="abdaf-119">Active Directory 証明書サービスの背景情報の詳細については、「[Active Directory 証明書サービスの概要](https://technet.microsoft.com/library/hh831740.aspx)」と「[Active Directory 証明書サービス](https://technet.microsoft.com/windowsserver/dd448615.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abdaf-119">For more background information on Active Directory Certificate Services, see [Active Directory Certificate Services Overview](https://technet.microsoft.com/library/hh831740.aspx) and [Active Directory Certificate Services in Windows Server 2008](https://technet.microsoft.com/windowsserver/dd448615.aspx).</span></span>
* <span data-ttu-id="abdaf-120">**ターゲット ノードへの管理アクセス**。</span><span class="sxs-lookup"><span data-stu-id="abdaf-120">**Administrative access to the target node or nodes**.</span></span>
* <span data-ttu-id="abdaf-121">**各ターゲット ノードでは、暗号化可能な証明書がそれぞれの個人用ストアに保存されています**。</span><span class="sxs-lookup"><span data-stu-id="abdaf-121">**Each target node has an encryption-capable certificate saved its Personal Store**.</span></span> <span data-ttu-id="abdaf-122">Windows PowerShell では、ストアへのパスは Cert:\LocalMachine\My です。</span><span class="sxs-lookup"><span data-stu-id="abdaf-122">In Windows PowerShell, the path to the store is Cert:\LocalMachine\My.</span></span> <span data-ttu-id="abdaf-123">このトピックの例では、"ワークステーション認証" テンプレートを使用します。このテンプレートは、その他の証明書テンプレートと共に、[[既定の証明書テンプレート]](https://technet.microsoft.com/library/cc740061(v=WS.10).aspx) にあります。</span><span class="sxs-lookup"><span data-stu-id="abdaf-123">The examples in this topic use the “workstation authentication” template, which you can find (along with other certificate templates) at [Default Certificate Templates](https://technet.microsoft.com/library/cc740061(v=WS.10).aspx).</span></span>
* <span data-ttu-id="abdaf-124">ターゲット ノード以外のコンピューターでこの構成を実行する場合は、**証明書の公開キーをエクスポート**して、構成の実行元であるコンピューターにインポートします。</span><span class="sxs-lookup"><span data-stu-id="abdaf-124">If you will be running this configuration on a computer other than the target node, **export the public key of the certificate**, and then import it to the computer you will run the configuration from.</span></span> <span data-ttu-id="abdaf-125">**公開**キーのみをエクスポートし、秘密キーは安全に保護してください。</span><span class="sxs-lookup"><span data-stu-id="abdaf-125">Make sure that you export only the **public** key; keep the private key secure.</span></span>

## <a name="overall-process"></a><span data-ttu-id="abdaf-126">全体的なプロセス</span><span class="sxs-lookup"><span data-stu-id="abdaf-126">Overall process</span></span>

 1. <span data-ttu-id="abdaf-127">ターゲット ノードごとに証明書のコピーが保持され、構成コンピューターに公開キーと拇印が保持されるように、証明書、キー、および拇印をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="abdaf-127">Set up the certificates, keys, and thumbprints, making sure that each target node has copies of the certificate and the configuration computer has the public key and thumbprint.</span></span>
 2. <span data-ttu-id="abdaf-128">公開キーのパスと拇印が含まれた構成データ ブロックを作成します。</span><span class="sxs-lookup"><span data-stu-id="abdaf-128">Create a configuration data block that contains the path and thumbprint of the public key.</span></span>
 3. <span data-ttu-id="abdaf-129">ターゲット ノードに必要な構成を定義し、ターゲット ノードで暗号化の解除をセットアップする構成スクリプトを作成します。暗号化の解除は、証明書とその拇印を使用して構成データを解読するように、ローカル構成マネージャーに指示することによって行います。</span><span class="sxs-lookup"><span data-stu-id="abdaf-129">Create a configuration script that defines your desired configuration for the target node and sets up decryption on the target nodes by commanding the Local Configuration manager to decrypt the configuration data using the certificate and its thumbprint.</span></span>
 4. <span data-ttu-id="abdaf-130">構成を実行すると、ローカル構成マネージャーの設定が行われ、DSC 構成が起動します。</span><span class="sxs-lookup"><span data-stu-id="abdaf-130">Run the configuration, which will set the Local Configuration Manager settings and start the DSC configuration.</span></span>

![Diagram1](images/CredentialEncryptionDiagram1.png)

## <a name="certificate-requirements"></a><span data-ttu-id="abdaf-132">証明書の要件</span><span class="sxs-lookup"><span data-stu-id="abdaf-132">Certificate Requirements</span></span>

<span data-ttu-id="abdaf-133">資格情報の暗号化を指定するには、公開キー証明書が、DSC 構成の作成に使用されているコンピューターから**信頼された**_ターゲット ノード_で使用可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="abdaf-133">To enact credential encryption, a public key certificate must be available on the _Target Node_ that is **trusted** by the computer being used to author the DSC configuration.</span></span>
<span data-ttu-id="abdaf-134">この公開キー証明書を DSC 資格情報の暗号化に使うには、満たす必要のある特定の要件があります。</span><span class="sxs-lookup"><span data-stu-id="abdaf-134">This public key certificate has specific requirements for it to be used for DSC credential encryption:</span></span>
 1. <span data-ttu-id="abdaf-135">**キー使用法**:</span><span class="sxs-lookup"><span data-stu-id="abdaf-135">**Key Usage**:</span></span>
   - <span data-ttu-id="abdaf-136">含める必要がある: 'KeyEncipherment' と 'DataEncipherment'。</span><span class="sxs-lookup"><span data-stu-id="abdaf-136">Must contain: 'KeyEncipherment' and 'DataEncipherment'.</span></span>
   - <span data-ttu-id="abdaf-137">含める_べきではない_: 'Digital Signature'。</span><span class="sxs-lookup"><span data-stu-id="abdaf-137">Should _not_ contain: 'Digital Signature'.</span></span>
 2. <span data-ttu-id="abdaf-138">**拡張キー使用法**:</span><span class="sxs-lookup"><span data-stu-id="abdaf-138">**Enhanced Key Usage**:</span></span>
   - <span data-ttu-id="abdaf-139">含める必要がある: ドキュメントの暗号化 (1.3.6.1.4.1.311.80.1)。</span><span class="sxs-lookup"><span data-stu-id="abdaf-139">Must contain: Document Encryption (1.3.6.1.4.1.311.80.1).</span></span>
   - <span data-ttu-id="abdaf-140">含める_べきではない_: クライアント認証 (1.3.6.1.5.5.7.3.2) とサーバー認証 (1.3.6.1.5.5.7.3.1)。</span><span class="sxs-lookup"><span data-stu-id="abdaf-140">Should _not_ contain: Client Authentication (1.3.6.1.5.5.7.3.2) and Server Authentication (1.3.6.1.5.5.7.3.1).</span></span>
 3. <span data-ttu-id="abdaf-141">証明書の秘密キーが \*ターゲット ノード_ で使用可能であること。</span><span class="sxs-lookup"><span data-stu-id="abdaf-141">The Private Key for the certificate is available on the \*Target Node_.</span></span>
 4. <span data-ttu-id="abdaf-142">証明書の**プロバイダー**は、"Microsoft RSA SChannel Cryptographic Provider" でなければならない。</span><span class="sxs-lookup"><span data-stu-id="abdaf-142">The **Provider** for the certificate must be "Microsoft RSA SChannel Cryptographic Provider".</span></span>

><span data-ttu-id="abdaf-143">**推奨されるベスト プラクティス:** 'Digital Signature' のキー使用法またはいずれかの認証 EKU が含まれている証明書を使用することもできますが、暗号化キーを誤用しやすくなり、攻撃に対して脆弱になります。</span><span class="sxs-lookup"><span data-stu-id="abdaf-143">**Recommended Best Practice:** Although you can use a certificate with containing a Key Usage of 'Digital Signature' or one of the Authentication EKU's, this will enable the encryption key to be more easily misused and vulnerable to attack.</span></span> <span data-ttu-id="abdaf-144">したがって、ベスト プラクティスとしては、DSC の資格情報をセキュリティで保護する目的で特別に作成した証明書を使い、その証明書ではこれらのキー使用法と EKU を省略することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="abdaf-144">So it is best practice to use a certificate created specifically for the purpose of securing DSC credentials that omits these Key Usage and EKUs.</span></span>

<span data-ttu-id="abdaf-145">_ターゲット ノード_にある既存の証明書で、これらの条件を満たしているものがあれば、DSC 資格情報をセキュリティで保護するために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="abdaf-145">Any existing certificate on the _Target Node_ that meets these criteria can be used to secure DSC credentials.</span></span>

## <a name="certificate-creation"></a><span data-ttu-id="abdaf-146">証明書の作成</span><span class="sxs-lookup"><span data-stu-id="abdaf-146">Certificate creation</span></span>

<span data-ttu-id="abdaf-147">必要な暗号化証明書 (公開/秘密キー ペア) を作成して使用するための方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="abdaf-147">There are two approaches you can take to create and use the required Encryption Certificate (public-private key pair).</span></span>

1. <span data-ttu-id="abdaf-148">**ターゲット ノード**上に作成し、公開キーのみを**オーサリング ノード**にエクスポートする</span><span class="sxs-lookup"><span data-stu-id="abdaf-148">Create it on the **Target Node** and export just the public key to the **Authoring Node**</span></span>
2. <span data-ttu-id="abdaf-149">**オーサリング ノード**上に作成し、キー ペア全体を**ターゲット ノード**にエクスポートする</span><span class="sxs-lookup"><span data-stu-id="abdaf-149">Create it on the **Authoring Node** and export the entire key pair to the **Target Node**</span></span>

<span data-ttu-id="abdaf-150">MOF の証明書の暗号化を解除するための秘密キーが常にターゲット ノードで保持されるため、1 つ目の方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="abdaf-150">Method 1 is recommended because the private key used to decrypt credentials in the MOF stays on the Target Node at all times.</span></span>


### <a name="creating-the-certificate-on-the-target-node"></a><span data-ttu-id="abdaf-151">ターゲット ノードでの証明書の作成</span><span class="sxs-lookup"><span data-stu-id="abdaf-151">Creating the Certificate on the Target Node</span></span>

<span data-ttu-id="abdaf-152">秘密キーは、**ターゲット ノード**で MOF の暗号化解除に使用されるため、秘密に保つ必要があります。そのための最も簡単な方法は、**ターゲット ノード**で秘密キー証明書を作成し、DSC 構成を MOF ファイルに作成するために使用されるコンピューターに**公開キー証明書**をコピーすることです。</span><span class="sxs-lookup"><span data-stu-id="abdaf-152">The private key must be kept secret, because is used to decrypt the MOF on the **Target Node** The easiest way to do that is to create the private key certificate on the **Target Node**, and copy the **public key certificate** to the computer being used to author the DSC configuration into a MOF file.</span></span>
<span data-ttu-id="abdaf-153">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="abdaf-153">The following example:</span></span>
 1. <span data-ttu-id="abdaf-154">**ターゲット ノード**で証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="abdaf-154">creates a certificate on the **Target node**</span></span>
 2. <span data-ttu-id="abdaf-155">公開キー証明書を**ターゲット ノード**にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="abdaf-155">exports the public key certificate on the **Target node**.</span></span>
 3. <span data-ttu-id="abdaf-156">公開キー証明書を**オーサリング ノード**の**マイ**証明書ストアにインポートします。</span><span class="sxs-lookup"><span data-stu-id="abdaf-156">imports the public key certificate into the **my** certificate store on the **Authoring node**.</span></span>

#### <a name="on-the-target-node-create-and-export-the-certificate"></a><span data-ttu-id="abdaf-157">ターゲット ノード: 証明書を作成してエクスポートする</span><span class="sxs-lookup"><span data-stu-id="abdaf-157">On the Target Node: create and export the certificate</span></span>
><span data-ttu-id="abdaf-158">ターゲット ノード: Windows Server 2016 および Windows 10</span><span class="sxs-lookup"><span data-stu-id="abdaf-158">Target Node: Windows Server 2016 and Windows 10</span></span>

```powershell
# note: These steps need to be performed in an Administrator PowerShell session
$cert = New-SelfSignedCertificate -Type DocumentEncryptionCertLegacyCsp -DnsName 'DscEncryptionCert' -HashAlgorithm SHA256
# export the public key certificate
$cert | Export-Certificate -FilePath "$env:temp\DscPublicKey.cer" -Force
```
<span data-ttu-id="abdaf-159">エクスポートしたら、```DscPublicKey.cer``` を**オーサリング ノード**にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="abdaf-159">Once exported, the ```DscPublicKey.cer``` would need to be copied to the **Authoring Node**.</span></span>

><span data-ttu-id="abdaf-160">ターゲット ノード: Windows Server 2012 R2/Windows 8.1 以前</span><span class="sxs-lookup"><span data-stu-id="abdaf-160">Target Node: Windows Server 2012 R2/Windows 8.1 and earlier</span></span>

<span data-ttu-id="abdaf-161">Windows 10 および Windows Server 2016 より前の Windows オペレーティング システムの New-SelfSignedCertificate コマンドレットでは、**Type** パラメーターがサポートされていないため、これらのオペレーティング システムでは、他の方法でこの証明書を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abdaf-161">Because the New-SelfSignedCertificate cmdlet on Windows Operating Systems prior to Windows 10 and Windows Server 2016 do not support the **Type** parameter, an alternate method of creating this certificate is required on these operating systems.</span></span>
<span data-ttu-id="abdaf-162">この場合は、```makecert.exe``` または ```certutil.exe``` を使って証明書を作成できます。</span><span class="sxs-lookup"><span data-stu-id="abdaf-162">In this case you can use ```makecert.exe``` or ```certutil.exe``` to create the certificate.</span></span>

<span data-ttu-id="abdaf-163">また、別の方法として、[Microsoft スクリプト センターから New-SelfSignedCertificateEx.ps1 スクリプトをダウンロード](https://gallery.technet.microsoft.com/scriptcenter/Self-signed-certificate-5920a7c6)し、それを使用して証明書を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="abdaf-163">An alternate method is to [download the New-SelfSignedCertificateEx.ps1 script from Microsoft Script Center](https://gallery.technet.microsoft.com/scriptcenter/Self-signed-certificate-5920a7c6) and use it to create the certificate instead:</span></span>
```powershell
# note: These steps need to be performed in an Administrator PowerShell session
# and in the folder that contains New-SelfSignedCertificateEx.ps1
. .\New-SelfSignedCertificateEx.ps1
New-SelfsignedCertificateEx `
    -Subject "CN=${ENV:ComputerName}" `
    -EKU 'Document Encryption' `
    -KeyUsage 'KeyEncipherment, DataEncipherment' `
    -SAN ${ENV:ComputerName} `
    -FriendlyName 'DSC Credential Encryption certificate' `
    -Exportable `
    -StoreLocation 'LocalMachine' `
    -KeyLength 2048 `
    -ProviderName 'Microsoft Enhanced Cryptographic Provider v1.0' `
    -AlgorithmName 'RSA' `
    -SignatureAlgorithm 'SHA256'
# Locate the newly created certificate
$Cert = Get-ChildItem -Path cert:\LocalMachine\My `
    | Where-Object {
        ($_.FriendlyName -eq 'DSC Credential Encryption certificate') `
        -and ($_.Subject -eq "CN=${ENV:ComputerName}")
    } | Select-Object -First 1
# export the public key certificate
$cert | Export-Certificate -FilePath "$env:temp\DscPublicKey.cer" -Force
```
<span data-ttu-id="abdaf-164">エクスポートしたら、```DscPublicKey.cer``` を**オーサリング ノード**にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="abdaf-164">Once exported, the ```DscPublicKey.cer``` would need to be copied to the **Authoring Node**.</span></span>

#### <a name="on-the-authoring-node-import-the-certs-public-key"></a><span data-ttu-id="abdaf-165">オーサリング ノード: 証明書の公開キーをインポートする</span><span class="sxs-lookup"><span data-stu-id="abdaf-165">On the Authoring Node: import the cert’s public key</span></span>
```powershell
# Import to the my store
Import-Certificate -FilePath "$env:temp\DscPublicKey.cer" -CertStoreLocation Cert:\LocalMachine\My
```

### <a name="creating-the-certificate-on-the-authoring-node"></a><span data-ttu-id="abdaf-166">オーサリング ノードでの証明書の作成</span><span class="sxs-lookup"><span data-stu-id="abdaf-166">Creating the Certificate on the Authoring Node</span></span>
<span data-ttu-id="abdaf-167">**オーサリング ノード**で暗号化証明書を作成し、**秘密キー**と共に PFX ファイルとしてエクスポートして、**ターゲット ノード**にインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="abdaf-167">Alternately, the encryption certificate can be created on the **Authoring Node**, exported with the **private key** as a PFX file and then imported on the **Target Node**.</span></span>
<span data-ttu-id="abdaf-168">これは、DSC 資格情報の暗号化を実装するために _Nano Server_ で実行されている現在の手法です。</span><span class="sxs-lookup"><span data-stu-id="abdaf-168">This is the current method for implementing DSC credential encryption on _Nano Server_.</span></span>
<span data-ttu-id="abdaf-169">PFX はパスワードで保護されていますが、転送中はセキュリティで保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abdaf-169">Although the PFX is secured with a password it should be kept secure during transit.</span></span>
<span data-ttu-id="abdaf-170">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="abdaf-170">The following example:</span></span>
 1. <span data-ttu-id="abdaf-171">**オーサリング ノード**で証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="abdaf-171">creates a certificate on the **Authoring node**.</span></span>
 2. <span data-ttu-id="abdaf-172">**オーサリング ノード**で、秘密キーを含む証明書をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="abdaf-172">exports the certificate including the private key on the **Authoring node**.</span></span>
 3. <span data-ttu-id="abdaf-173">**オーサリング ノード**から秘密キーを削除します。ただし、公開キー証明書を**マイ** ストアに保管しておきます。</span><span class="sxs-lookup"><span data-stu-id="abdaf-173">removes the private key from the **Authoring node**, but keeps the public key certificate in the **my** store.</span></span>
 4. <span data-ttu-id="abdaf-174">秘密キー証明書を**ターゲット ノード**のルート証明書ストアにインポートします。</span><span class="sxs-lookup"><span data-stu-id="abdaf-174">imports the private key certificate into the root certificate store on the **Target node**.</span></span>
   - <span data-ttu-id="abdaf-175">これはルート ストアに追加されるため、**ターゲット ノード**で信頼されるようになります。</span><span class="sxs-lookup"><span data-stu-id="abdaf-175">it must be added to the root store so that it will be trusted by the **Target node**.</span></span>

#### <a name="on-the-authoring-node-create-and-export-the-certificate"></a><span data-ttu-id="abdaf-176">オーサリング ノード: 証明書を作成してエクスポートする</span><span class="sxs-lookup"><span data-stu-id="abdaf-176">On the Authoring Node: create and export the certificate</span></span>
><span data-ttu-id="abdaf-177">ターゲット ノード: Windows Server 2016 および Windows 10</span><span class="sxs-lookup"><span data-stu-id="abdaf-177">Target Node: Windows Server 2016 and Windows 10</span></span>

```powershell
# note: These steps need to be performed in an Administrator PowerShell session
$cert = New-SelfSignedCertificate -Type DocumentEncryptionCertLegacyCsp -DnsName 'DscEncryptionCert' -HashAlgorithm SHA256
# export the private key certificate
$mypwd = ConvertTo-SecureString -String "YOUR_PFX_PASSWD" -Force -AsPlainText
$cert | Export-PfxCertificate -FilePath "$env:temp\DscPrivateKey.pfx" -Password $mypwd -Force
# remove the private key certificate from the node but keep the public key certificate
$cert | Export-Certificate -FilePath "$env:temp\DscPublicKey.cer" -Force
$cert | Remove-Item -Force
Import-Certificate -FilePath "$env:temp\DscPublicKey.cer" -CertStoreLocation Cert:\LocalMachine\My
```
<span data-ttu-id="abdaf-178">エクスポートしたら、```DscPrivateKey.pfx``` を**ターゲット ノード**にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="abdaf-178">Once exported, the ```DscPrivateKey.pfx``` would need to be copied to the **Target Node**.</span></span>

><span data-ttu-id="abdaf-179">ターゲット ノード: Windows Server 2012 R2/Windows 8.1 以前</span><span class="sxs-lookup"><span data-stu-id="abdaf-179">Target Node: Windows Server 2012 R2/Windows 8.1 and earlier</span></span>

<span data-ttu-id="abdaf-180">Windows 10 および Windows Server 2016 より前の Windows オペレーティング システムの New-SelfSignedCertificate コマンドレットでは、**Type** パラメーターがサポートされていないため、これらのオペレーティング システムでは、他の方法でこの証明書を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abdaf-180">Because the New-SelfSignedCertificate cmdlet on Windows Operating Systems prior to Windows 10 and Windows Server 2016 do not support the **Type** parameter, an alternate method of creating this certificate is required on these operating systems.</span></span>
<span data-ttu-id="abdaf-181">この場合は、```makecert.exe``` または ```certutil.exe``` を使って証明書を作成できます。</span><span class="sxs-lookup"><span data-stu-id="abdaf-181">In this case you can use ```makecert.exe``` or ```certutil.exe``` to create the certificate.</span></span>

<span data-ttu-id="abdaf-182">また、別の方法として、[Microsoft スクリプト センターから New-SelfSignedCertificateEx.ps1 スクリプトをダウンロード](https://gallery.technet.microsoft.com/scriptcenter/Self-signed-certificate-5920a7c6)し、それを使用して証明書を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="abdaf-182">An alternate method is to [download the New-SelfSignedCertificateEx.ps1 script from Microsoft Script Center](https://gallery.technet.microsoft.com/scriptcenter/Self-signed-certificate-5920a7c6) and use it to create the certificate instead:</span></span>
```powershell
# note: These steps need to be performed in an Administrator PowerShell session
# and in the folder that contains New-SelfSignedCertificateEx.ps1
. .\New-SelfSignedCertificateEx.ps1
New-SelfsignedCertificateEx `
    -Subject "CN=${ENV:ComputerName}" `
    -EKU 'Document Encryption' `
    -KeyUsage 'KeyEncipherment, DataEncipherment' `
    -SAN ${ENV:ComputerName} `
    -FriendlyName 'DSC Credential Encryption certificate' `
    -Exportable `
    -StoreLocation 'LocalMachine' `
    -KeyLength 2048 `
    -ProviderName 'Microsoft Enhanced Cryptographic Provider v1.0' `
    -AlgorithmName 'RSA' `
    -SignatureAlgorithm 'SHA256'
# Locate the newly created certificate
$Cert = Get-ChildItem -Path cert:\LocalMachine\My `
    | Where-Object {
        ($_.FriendlyName -eq 'DSC Credential Encryption certificate') `
        -and ($_.Subject -eq "CN=${ENV:ComputerName}")
    } | Select-Object -First 1
# export the public key certificate
$mypwd = ConvertTo-SecureString -String "YOUR_PFX_PASSWD" -Force -AsPlainText
$cert | Export-PfxCertificate -FilePath "$env:temp\DscPrivateKey.pfx" -Password $mypwd -Force
# remove the private key certificate from the node but keep the public key certificate
$cert | Export-Certificate -FilePath "$env:temp\DscPublicKey.cer" -Force
$cert | Remove-Item -Force
Import-Certificate -FilePath "$env:temp\DscPublicKey.cer" -CertStoreLocation Cert:\LocalMachine\My
```

#### <a name="on-the-target-node-import-the-certs-private-key-as-a-trusted-root"></a><span data-ttu-id="abdaf-183">ターゲット ノード: 証明書の秘密キーを信頼されたルートとしてインポートする</span><span class="sxs-lookup"><span data-stu-id="abdaf-183">On the Target Node: import the cert’s private key as a trusted root</span></span>
```powershell
# Import to the root store so that it is trusted
$mypwd = ConvertTo-SecureString -String "YOUR_PFX_PASSWD" -Force -AsPlainText
Import-PfxCertificate -FilePath "$env:temp\DscPrivateKey.pfx" -CertStoreLocation Cert:\LocalMachine\My -Password $mypwd > $null
```

## <a name="configuration-data"></a><span data-ttu-id="abdaf-184">構成データ</span><span class="sxs-lookup"><span data-stu-id="abdaf-184">Configuration data</span></span>

<span data-ttu-id="abdaf-185">構成データ ブロックでは、操作対象のターゲット ノード、資格情報を暗号化するかどうか、暗号化の手段、およびその他の情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="abdaf-185">The configuration data block defines which target nodes to operate on, whether or not to encrypt the credentials, the means of encryption, and other information.</span></span> <span data-ttu-id="abdaf-186">構成データ ブロックの詳細については、「[Separating Configuration and Environment Data (構成データと環境データの分離)](configData.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abdaf-186">For more information on the configuration data block, see [Separating Configuration and Environment Data](configData.md).</span></span>

<span data-ttu-id="abdaf-187">資格情報の暗号化に関連するノードごとに構成可能な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="abdaf-187">The elements that can be configured for each node that are related to credential encryption are:</span></span>
* <span data-ttu-id="abdaf-188">**NodeName** - 資格情報の暗号化が構成されているターゲット ノードの名前。</span><span class="sxs-lookup"><span data-stu-id="abdaf-188">**NodeName** - the name of the target node that the credential encryption is being configured for.</span></span>
* <span data-ttu-id="abdaf-189">**PsDscAllowPlainTextPassword** - 暗号化されていない資格情報をこのノードに渡してよいかどうか。</span><span class="sxs-lookup"><span data-stu-id="abdaf-189">**PsDscAllowPlainTextPassword** - whether unencrypted credentials will be allowed to be passed to this node.</span></span> <span data-ttu-id="abdaf-190">これは**推奨されません**。</span><span class="sxs-lookup"><span data-stu-id="abdaf-190">This is **not recommended**.</span></span>
* <span data-ttu-id="abdaf-191">**Thumbprint** - _ターゲット ノード_上で DSC 構成に含まれる資格情報を復号化するために使用される証明書の拇印です。</span><span class="sxs-lookup"><span data-stu-id="abdaf-191">**Thumbprint** - the thumbprint of the certificate that will be used to decrypt the credentials in the DSC Configuration on the _Target Node_.</span></span> <span data-ttu-id="abdaf-192">**この証明書は、ターゲット ノード上のローカル コンピューターの証明書ストアに存在する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="abdaf-192">**This certificate must exist in the Local Machine certificate store on the Target Node.**</span></span>
* <span data-ttu-id="abdaf-193">**CertificateFile** - _ターゲット ノード_用の証明書を暗号化するために使用する必要のある証明書ファイル (公開キーのみを含む)。</span><span class="sxs-lookup"><span data-stu-id="abdaf-193">**CertificateFile** - the certificate file (containing the public key only) that should be used to encrypt the credentials for the _Target Node_.</span></span> <span data-ttu-id="abdaf-194">これは、DER Encoded Binary X.509 または Base-64 encoded X.509 のいずれかの形式の証明書ファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="abdaf-194">This must be either a DER encoded binary X.509 or Base-64 encoded X.509 format certificate file.</span></span>

<span data-ttu-id="abdaf-195">この例に示す構成データ ブロックでは、処理対象のターゲット ノードの名前を targetNode とし、公開キー証明書ファイル (targetNode.cer という名前) へのパス、および公開キーの拇印を指定しています。</span><span class="sxs-lookup"><span data-stu-id="abdaf-195">This example shows a configuration data block that specifies a target node to act on named targetNode, the path to the public key certificate file (named targetNode.cer), and the thumbprint for the public key.</span></span>

```powershell
$ConfigData= @{
    AllNodes = @(
            @{
                # The name of the node we are describing
                NodeName = "targetNode"

                # The path to the .cer file containing the
                # public key of the Encryption Certificate
                # used to encrypt credentials for this node
                CertificateFile = "C:\publicKeys\targetNode.cer"


                # The thumbprint of the Encryption Certificate
                # used to decrypt the credentials on target node
                Thumbprint = "AC23EA3A9E291A75757A556D0B71CBBF8C4F6FD8"
            };
        );
    }
```


## <a name="configuration-script"></a><span data-ttu-id="abdaf-196">構成スクリプト</span><span class="sxs-lookup"><span data-stu-id="abdaf-196">Configuration script</span></span>

<span data-ttu-id="abdaf-197">構成スクリプト自体では、`PsCredential` パラメーターを使用して、できる限り短時間で資格情報が格納されるようにします。</span><span class="sxs-lookup"><span data-stu-id="abdaf-197">In the configuration script itself, use the `PsCredential` parameter to ensure that credentials are stored for the shortest possible time.</span></span> <span data-ttu-id="abdaf-198">ここに示した例を実行すると、DSC では資格情報の入力を求め、構成データ ブロック内のターゲット ノードに関連付けられている CertificateFile を使用して MOF ファイルを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="abdaf-198">When you run the supplied example, DSC will prompt you for credentials and then encrypt the MOF file using the CertificateFile that is associated with the target node in the configuration data block.</span></span> <span data-ttu-id="abdaf-199">このコード例では、ユーザーに対してセキュリティ保護された共有からファイルをコピーしています。</span><span class="sxs-lookup"><span data-stu-id="abdaf-199">This code example copies a file from a share that is secured to a user.</span></span>

```
configuration CredentialEncryptionExample
{
    param(
        [Parameter(Mandatory=$true)]
        [ValidateNotNullorEmpty()]
        [PsCredential] $credential
        )


    Node $AllNodes.NodeName
    {
        File exampleFile
        {
            SourcePath = "\\Server\share\path\file.ext"
            DestinationPath = "C:\destinationPath"
            Credential = $credential
        }
    }
}
```

## <a name="setting-up-decryption"></a><span data-ttu-id="abdaf-200">暗号化の解除のセットアップ</span><span class="sxs-lookup"><span data-stu-id="abdaf-200">Setting up decryption</span></span>

<span data-ttu-id="abdaf-201">[`Start-DscConfiguration`](https://technet.microsoft.com/library/dn521623.aspx) が機能するようにするには、各ターゲット ノードのローカル構成マネージャーに対して、どの証明書を使用して資格情報の暗号化を解除するかを指示し、CertificateID リソースを使用して証明書の拇印を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abdaf-201">Before [`Start-DscConfiguration`](https://technet.microsoft.com/library/dn521623.aspx) can work, you have to tell the Local Configuration Manager on each target node which certificate to use to decrypt the credentials, using the CertificateID resource to verify the certificate’s thumbprint.</span></span> <span data-ttu-id="abdaf-202">この例の関数は、適切なローカル証明書を検出します (使用する証明書が正しく検出されるようにカスタマイズすることが必要になる場合もあります)。</span><span class="sxs-lookup"><span data-stu-id="abdaf-202">This example function will find the appropriate local certificate (you might have to customize it so it will find the exact certificate you want to use):</span></span>

```powershell
# Get the certificate that works for encryption
function Get-LocalEncryptionCertificateThumbprint
{
    (dir Cert:\LocalMachine\my) | %{
        # Verify the certificate is for Encryption and valid
        if ($_.PrivateKey.KeyExchangeAlgorithm -and $_.Verify())
        {
            return $_.Thumbprint
        }
    }
}
```

<span data-ttu-id="abdaf-203">拇印で証明書を識別する場合は、その値を使用するように構成スクリプトを更新します。</span><span class="sxs-lookup"><span data-stu-id="abdaf-203">With the certificate identified by its thumbprint, the configuration script can be updated to use the value:</span></span>

```powershell
configuration CredentialEncryptionExample
{
    param(
        [Parameter(Mandatory=$true)]
        [ValidateNotNullorEmpty()]
        [PsCredential] $credential
        )


    Node $AllNodes.NodeName
    {
        File exampleFile
        {
            SourcePath = "\\Server\share\path\file.ext"
            DestinationPath = "C:\destinationPath"
            Credential = $credential
        }

        LocalConfigurationManager
        {
             CertificateId = $node.Thumbprint
        }
    }
}
```

## <a name="running-the-configuration"></a><span data-ttu-id="abdaf-204">構成の実行</span><span class="sxs-lookup"><span data-stu-id="abdaf-204">Running the configuration</span></span>

<span data-ttu-id="abdaf-205">この時点では、構成を実行すると、次の 2 つのファイルが出力されます。</span><span class="sxs-lookup"><span data-stu-id="abdaf-205">At this point, you can run the configuration, which will output two files:</span></span>

 * <span data-ttu-id="abdaf-206">\*.meta.mof ファイル。ローカル コンピューター ストアに格納され、拇印で識別される証明書を使用して資格情報の暗号化を解除するように、ローカル構成マネージャーを構成します。</span><span class="sxs-lookup"><span data-stu-id="abdaf-206">A \*.meta.mof file that configures the Local Configuration Manager to decrypt the credentials using the certificate that is stored on the local machine store and identified by its thumbprint.</span></span> <span data-ttu-id="abdaf-207">[`Set-DscLocalConfigurationManager`](https://technet.microsoft.com/library/dn521621.aspx) は、\*.meta.mof ファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="abdaf-207">[`Set-DscLocalConfigurationManager`](https://technet.microsoft.com/library/dn521621.aspx) applies the \*.meta.mof file.</span></span>
 * <span data-ttu-id="abdaf-208">構成を実際に適用する MOF ファイル。</span><span class="sxs-lookup"><span data-stu-id="abdaf-208">A MOF file that actually applies the configuration.</span></span> <span data-ttu-id="abdaf-209">Start-DscConfiguration は、構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="abdaf-209">Start-DscConfiguration applies the configuration.</span></span>

<span data-ttu-id="abdaf-210">次のコマンドがこれらの手順を実施します。</span><span class="sxs-lookup"><span data-stu-id="abdaf-210">These commands will accomplish those steps:</span></span>

```powershell
Write-Host "Generate DSC Configuration..."
CredentialEncryptionExample -ConfigurationData $ConfigData -OutputPath .\CredentialEncryptionExample

Write-Host "Setting up LCM to decrypt credentials..."
Set-DscLocalConfigurationManager .\CredentialEncryptionExample -Verbose

Write-Host "Starting Configuration..."
Start-DscConfiguration .\CredentialEncryptionExample -wait -Verbose
```

<span data-ttu-id="abdaf-211">この例では、DSC 構成をターゲット ノードにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="abdaf-211">This example would push the DSC configuration to the target node.</span></span>
<span data-ttu-id="abdaf-212">DSC プル サーバーが利用可能な場合は、DSC プル サーバーを使って DSC 構成を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="abdaf-212">The DSC configuration can also be applied using a DSC Pull Server if one is available.</span></span>

<span data-ttu-id="abdaf-213">DSC プル サーバーを使って DSC 構成を適用する方法の詳細については、「[DSC プル クライアントのセットアップ](pullClient.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abdaf-213">See [Setting up a DSC pull client](pullClient.md) for more information on applying DSC configurations using a DSC Pull Server.</span></span>

## <a name="credential-encryption-module-example"></a><span data-ttu-id="abdaf-214">資格情報暗号化モジュールの例</span><span class="sxs-lookup"><span data-stu-id="abdaf-214">Credential Encryption Module Example</span></span>

<span data-ttu-id="abdaf-215">次に、これらのすべての手順に加え、公開キーをエクスポートおよびコピーするヘルパー コマンドレットが組み込まれた完全な例を示します。</span><span class="sxs-lookup"><span data-stu-id="abdaf-215">Here is a full example that incorporates all of these steps, plus a helper cmdlet that exports and copies the public keys:</span></span>

```powershell
# A simple example of using credentials
configuration CredentialEncryptionExample
{
    param(
        [Parameter(Mandatory=$true)]
        [ValidateNotNullorEmpty()]
        [PsCredential] $credential
        )


    Node $AllNodes.NodeName
    {
        File exampleFile
        {
            SourcePath = "\\server\share\file.txt"
            DestinationPath = "C:\Users\user"
            Credential = $credential
        }

        LocalConfigurationManager
        {
            CertificateId = $node.Thumbprint
        }
    }
}

# A Helper to invoke the configuration, with the correct public key
# To encrypt the configuration credentials
function Start-CredentialEncryptionExample
{
    [CmdletBinding()]
    param ($computerName)


    [string] $thumbprint = Get-EncryptionCertificate -computerName $computerName -Verbose
    Write-Verbose "using cert: $thumbprint"

    $certificatePath = join-path -Path "$env:SystemDrive\$script:publicKeyFolder" -childPath "$computername.EncryptionCertificate.cer"

    $ConfigData=    @{
        AllNodes = @(
                        @{
                            # The name of the node we are describing
                            NodeName = "$computerName"

                            # The path to the .cer file containing the
                            # public key of the Encryption Certificate
                            CertificateFile = "$certificatePath"

                            # The thumbprint of the Encryption Certificate
                            # used to decrypt the credentials
                            Thumbprint = $thumbprint
                        };
                    );
    }

    Write-Verbose "Generate DSC Configuration..."
    CredentialEncryptionExample -ConfigurationData $ConfigData -OutputPath .\CredentialEncryptionExample `
        -credential (Get-Credential -UserName "$env:USERDOMAIN\$env:USERNAME" -Message "Enter credentials for configuration")

    Write-Verbose "Setting up LCM to decrypt credentials..."
    Set-DscLocalConfigurationManager .\CredentialEncryptionExample -Verbose

    Write-Verbose "Starting Configuration..."
    Start-DscConfiguration .\CredentialEncryptionExample -wait -Verbose

}


#region HelperFunctions

# The folder name for the exported public keys
$script:publicKeyFolder = "publicKeys"

# Get the certificate that works for encryptions
function Get-EncryptionCertificate
{
    [CmdletBinding()]
    param ($computerName)
    $returnValue= Invoke-Command -ComputerName $computerName -ScriptBlock {
            $certificates = dir Cert:\LocalMachine\my

            $certificates | %{
                    # Verify the certificate is for Encryption and valid
                    if ($_.PrivateKey.KeyExchangeAlgorithm -and $_.Verify())
                    {
                        # Create the folder to hold the exported public key
                        $folder= Join-Path -Path $env:SystemDrive\ -ChildPath $using:publicKeyFolder
                        if (! (Test-Path $folder))
                        {
                            md $folder | Out-Null
                        }

                        # Export the public key to a well known location
                        $certPath = Export-Certificate -Cert $_ -FilePath (Join-Path -path $folder -childPath "EncryptionCertificate.cer")

                        # Return the thumbprint, and exported certificate path
                        return @($_.Thumbprint,$certPath);
                    }
                  }
        }
    Write-Verbose "Identified and exported cert..."
    # Copy the exported certificate locally
    $destinationPath = join-path -Path "$env:SystemDrive\$script:publicKeyFolder" -childPath "$computername.EncryptionCertificate.cer"
    Copy-Item -Path (join-path -path \\$computername -childPath $returnValue[1].FullName.Replace(":","$"))  $destinationPath | Out-Null

    # Return the thumbprint
    return $returnValue[0]
}

Start-CredentialEncryptionExample
```