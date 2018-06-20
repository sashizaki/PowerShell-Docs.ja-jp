---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: ユーザーの資格情報を指定して DSC を実行する
ms.openlocfilehash: b2992ad562dea375aba980611312c7b96a23189c
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
ms.locfileid: "34189705"
---
# <a name="running-dsc-with-user-credentials"></a><span data-ttu-id="30fab-103">ユーザーの資格情報を指定して DSC を実行する</span><span class="sxs-lookup"><span data-stu-id="30fab-103">Running DSC with user credentials</span></span>

> <span data-ttu-id="30fab-104">適用先: Windows PowerShell 5.0、Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="30fab-104">Applies To: Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="30fab-105">資格情報のセットを指定して DSC リソースを実行するには、構成の中で自動 **PsDscRunAsCredential** プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="30fab-105">You can run a DSC resource under a specified set of credentials by using the automatic **PsDscRunAsCredential** property in the configuration.</span></span>
<span data-ttu-id="30fab-106">既定では、DSC はシステム アカウントとして各リソースを実行します。</span><span class="sxs-lookup"><span data-stu-id="30fab-106">By default, DSC runs each resource as the system account.</span></span>
<span data-ttu-id="30fab-107">時には、ユーザーとして実行することが必要な場合があります。たとえば、特定のユーザー コンテキストで MSI パッケージをインストールする場合や、ユーザーのレジストリ キーを設定する場合、ユーザーの特定のローカル ディレクトリにアクセスする場合、ネットワーク共有にアクセスする場合などです。</span><span class="sxs-lookup"><span data-stu-id="30fab-107">There are times when running as a user is necessary, such as installing MSI packages in a specific user context, setting a user's registry keys, accessing a user's specific local directory, or accessing a network share.</span></span>

<span data-ttu-id="30fab-108">すべての DSC リソースには、任意のユーザー資格情報に設定できる **PsDscRunAsCredential** プロパティがあります ([PSCredential](https://msdn.microsoft.com/library/ms572524(v=VS.85).aspx) オブジェクト)。</span><span class="sxs-lookup"><span data-stu-id="30fab-108">Every DSC resource has a **PsDscRunAsCredential** property that can be set to any user credentials (a [PSCredential](https://msdn.microsoft.com/library/ms572524(v=VS.85).aspx) object).</span></span>
<span data-ttu-id="30fab-109">資格情報は、構成内でプロパティの値としてハードコーディングするか、[Get-Credential](https://technet.microsoft.com/library/hh849815.aspx) に対して値を設定することができます。後者の場合は、構成のコンパイル時に資格情報を入力するように求めるプロンプトが表示されます (構成のコンパイルの詳細については、[構成](configurations.md)に関する記事を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="30fab-109">The credential can be hard-coded as the value of the property in the configuration, or you can set the value to [Get-Credential](https://technet.microsoft.com/library/hh849815.aspx), which will prompt the user for a credential when the configuration is compiled (for information about compiling configurations, see [Configurations](configurations.md).</span></span>

><span data-ttu-id="30fab-110">**注:** PowerShell 5.0 では、複合リソースを呼び出す構成での **PsDscRunAsCredential** プロパティの使用はサポートされていませんでした。</span><span class="sxs-lookup"><span data-stu-id="30fab-110">**Note:** In PowerShell 5.0, using the **PsDscRunAsCredential** property in configurations calling composite resources was not supported.</span></span>
><span data-ttu-id="30fab-111">PowerShell 5.1 では、複合リソースを呼び出す構成で **PsDscRunAsCredential** プロパティがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="30fab-111">In PowerShell 5.1, the **PsDscRunAsCredential** property is supported in configurations calling composite resources.</span></span>

><span data-ttu-id="30fab-112">**注:** **PsDscRunAsCredential** プロパティは PowerShell 4.0 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="30fab-112">**Note:** The **PsDscRunAsCredential** property is not available in PowerShell 4.0.</span></span>

<span data-ttu-id="30fab-113">次の例では、**Get-Credential** を使って、ユーザーに資格情報を入力するようにプロンプトが出ます。</span><span class="sxs-lookup"><span data-stu-id="30fab-113">In the following example, **Get-Credential** is used to prompt the user for credentials.</span></span>
<span data-ttu-id="30fab-114">また、[Registry](registryResource.md) リソースを使って、Windows のコマンド プロンプト ウィンドウの背景色を指定するレジストリ キーを変更します。</span><span class="sxs-lookup"><span data-stu-id="30fab-114">The [Registry](registryResource.md) resource is used to change the registry key that specifies the background color for the Windows command prompt window.</span></span>

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
><span data-ttu-id="30fab-115">**注:** この例では、有効な証明書が `C:\publicKeys\targetNode.cer` に存在することと、示されている値がその証明書の拇印であることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="30fab-115">**Note:** This example assumes that you have a valid certificate at `C:\publicKeys\targetNode.cer`, and that the thumbprint of that certificate is the value shown.</span></span>
><span data-ttu-id="30fab-116">DSC 構成 MOF ファイル内の資格情報を暗号化する方法の詳細については、「[MOF ファイルのセキュリティ保護](secureMOF.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30fab-116">For information about encrypting credentials in DSC configuration MOF files, see [Securing the MOF file](secureMOF.md).</span></span>