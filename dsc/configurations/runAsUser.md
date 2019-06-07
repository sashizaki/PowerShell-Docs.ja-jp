---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC リソースに対して資格情報を使用する
ms.openlocfilehash: fea2e3cad8d081c17853e127203f1d40d98c5de2
ms.sourcegitcommit: bc42c9166857147a1ecf9924b718d4a48eb901e3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2019
ms.locfileid: "66470770"
---
# <a name="use-credentials-with-dsc-resources"></a><span data-ttu-id="f0187-103">DSC リソースに対して資格情報を使用する</span><span class="sxs-lookup"><span data-stu-id="f0187-103">Use Credentials with DSC Resources</span></span>

> <span data-ttu-id="f0187-104">適用先:Windows PowerShell 5.0、Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="f0187-104">Applies To: Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="f0187-105">資格情報のセットを指定して DSC リソースを実行するには、構成の中で自動 **PsDscRunAsCredential** プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="f0187-105">You can run a DSC resource under a specified set of credentials by using the automatic **PsDscRunAsCredential** property in the configuration.</span></span> <span data-ttu-id="f0187-106">既定では、DSC はシステム アカウントとして各リソースを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0187-106">By default, DSC runs each resource as the system account.</span></span> <span data-ttu-id="f0187-107">時には、ユーザーとして実行することが必要な場合があります。たとえば、特定のユーザー コンテキストで MSI パッケージをインストールする場合や、ユーザーのレジストリ キーを設定する場合、ユーザーの特定のローカル ディレクトリにアクセスする場合、ネットワーク共有にアクセスする場合などです。</span><span class="sxs-lookup"><span data-stu-id="f0187-107">There are times when running as a user is necessary, such as installing MSI packages in a specific user context, setting a user's registry keys, accessing a user's specific local directory, or accessing a network share.</span></span> <span data-ttu-id="f0187-108">**PSDSCRunAsCredential** に指定するアカウントに対しては、ターゲット コンピューターによって、**SeInteractiveLogonRight** が要求されます。</span><span class="sxs-lookup"><span data-stu-id="f0187-108">The **SeInteractiveLogonRight** is required, by the target machine, for any account you specify to **PSDSCRunAsCredential**.</span></span> <span data-ttu-id="f0187-109">詳細については、「[Account Rights Constants (アカウントの権限に関する定数)](/windows/desktop/secauthz/account-rights-constants)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f0187-109">For more information, see [Account Rights Constants](/windows/desktop/secauthz/account-rights-constants).</span></span>

<span data-ttu-id="f0187-110">すべての DSC リソースには、任意のユーザー資格情報に設定できる **PsDscRunAsCredential** プロパティがあります ([PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクト)。</span><span class="sxs-lookup"><span data-stu-id="f0187-110">Every DSC resource has a **PsDscRunAsCredential** property that can be set to any user credentials (a [PSCredential](/dotnet/api/system.management.automation.pscredential) object).</span></span> <span data-ttu-id="f0187-111">資格情報は、構成内でプロパティの値としてハードコーディングするか、[Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) に対して値を設定することができます。後者の場合は、構成のコンパイル時に資格情報を入力するように求めるプロンプトが表示されます (構成のコンパイルの詳細については、[構成](configurations.md)に関する記事を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f0187-111">The credential can be hard-coded as the value of the property in the configuration, or you can set the value to [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential), which will prompt the user for a credential when the configuration is compiled (for information about compiling configurations, see [Configurations](configurations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f0187-112">PowerShell 5.0 では、複合リソースを呼び出す構成での **PsDscRunAsCredential** プロパティの使用はサポートされていませんでした。</span><span class="sxs-lookup"><span data-stu-id="f0187-112">In PowerShell 5.0, using the **PsDscRunAsCredential** property in configurations calling composite resources was not supported.</span></span> <span data-ttu-id="f0187-113">PowerShell 5.1 では、複合リソースを呼び出す構成で **PsDscRunAsCredential** プロパティがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f0187-113">In PowerShell 5.1, the **PsDscRunAsCredential** property is supported in configurations calling composite resources.</span></span> <span data-ttu-id="f0187-114">**PsDscRunAsCredential** プロパティは PowerShell 4.0 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="f0187-114">The **PsDscRunAsCredential** property is not available in PowerShell 4.0.</span></span>

<span data-ttu-id="f0187-115">次の例では、`Get-Credential` を使って、ユーザーに資格情報を入力するようにプロンプトが出ます。</span><span class="sxs-lookup"><span data-stu-id="f0187-115">In the following example, `Get-Credential` is used to prompt the user for credentials.</span></span> <span data-ttu-id="f0187-116">また、**Registry** リソースを使って、Windows のコマンド プロンプト ウィンドウの背景色を指定するレジストリ キーを変更します。</span><span class="sxs-lookup"><span data-stu-id="f0187-116">The **Registry** resource is used to change the registry key that specifies the background color for the Windows command prompt window.</span></span>

```powershell
Configuration ChangeCmdBackGroundColor
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    Node $AllNodes.NodeName
    {
        Registry CmdPath
        {
            Key                  = 'HKEY_CURRENT_USER\SOFTWARE\Microsoft\Command Processor'
            ValueName            = 'DefaultColor'
            ValueData            = '1F'
            ValueType            = 'DWORD'
            Ensure               = 'Present'
            Force                = $true
            Hex                  = $true
            PsDscRunAsCredential = Get-Credential
        }
    }
}

$configData = @{
    AllNodes = @(
        @{
            NodeName             = 'localhost';
            PSDscAllowDomainUser = $true
            CertificateFile      = 'C:\publicKeys\targetNode.cer'
            Thumbprint           = '7ee7f09d-4be0-41aa-a47f-96b9e3bdec25'
        }
    )
}

ChangeCmdBackGroundColor -ConfigurationData $configData
```

> [!NOTE]
> <span data-ttu-id="f0187-117">この例では、有効な証明書が `C:\publicKeys\targetNode.cer` に存在することと、示されている値がその証明書の拇印であることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="f0187-117">This example assumes that you have a valid certificate at `C:\publicKeys\targetNode.cer`, and that the thumbprint of that certificate is the value shown.</span></span> <span data-ttu-id="f0187-118">DSC 構成 MOF ファイル内の資格情報を暗号化する方法の詳細については、「[MOF ファイルのセキュリティ保護](../pull-server/secureMOF.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0187-118">For information about encrypting credentials in DSC configuration MOF files, see [Securing the MOF file](../pull-server/secureMOF.md).</span></span>
