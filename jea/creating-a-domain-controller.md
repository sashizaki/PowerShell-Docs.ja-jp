---
description: 
manager: dongill
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット, JEA"
ms.date: 2016-06-22
title: "ドメイン コントローラーの作成"
ms.technology: powershell
ms.openlocfilehash: 80b957ed666ca626c6083041cf99c263e2e0dc27
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
ms.translationtype: HT
ms.contentlocale: ja-JP
---
### <a name="creating-a-domain-controller"></a><span data-ttu-id="9e395-103">ドメイン コントローラーの作成</span><span class="sxs-lookup"><span data-stu-id="9e395-103">Creating a Domain Controller</span></span>

<span data-ttu-id="9e395-104">このドキュメントでは、お使いのコンピューターがドメインに参加していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="9e395-104">This document assumes that your machine is domain joined.</span></span>
<span data-ttu-id="9e395-105">現在ドメインに参加していない場合は、このセクションを利用して、DSC を使ってドメイン コントローラーを簡単に立ち上げることができます。</span><span class="sxs-lookup"><span data-stu-id="9e395-105">If you currently don't have a domain to join, this section can help you quickly stand up a domain controller using DSC.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="9e395-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="9e395-106">Prerequisites</span></span>

1.  <span data-ttu-id="9e395-107">コンピューターが内部ネットワークにあること</span><span class="sxs-lookup"><span data-stu-id="9e395-107">The machine is on an internal network</span></span>
2.  <span data-ttu-id="9e395-108">コンピューターが、既存のドメインに参加していないこと</span><span class="sxs-lookup"><span data-stu-id="9e395-108">The machine is not joined to an existing domain</span></span>
3.  <span data-ttu-id="9e395-109">コンピューターが Windows Server 2016 を実行しているか、WMF 5.0 がインストールされていること</span><span class="sxs-lookup"><span data-stu-id="9e395-109">The machine is running Windows Server 2016 or has WMF 5.0 installed</span></span>

#### <a name="install-xactivedirectory"></a><span data-ttu-id="9e395-110">xActiveDirectory のインストール</span><span class="sxs-lookup"><span data-stu-id="9e395-110">Install xActiveDirectory</span></span>
<span data-ttu-id="9e395-111">コンピューターにアクティブなインターネット接続がある場合は、管理者特権の PowerShell ウィンドウで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9e395-111">If your machine has an active internet connection, run the following command in an elevated PowerShell window:</span></span>
```PowerShell
Install-Module xActiveDirectory -Force
```
<span data-ttu-id="9e395-112">インターネット接続がない場合は、xActiveDirectory を別のコンピューターにインストールしてから、xActiveDirectory フォルダーをコンピューターの C:\Program Files\WindowsPowerShell\Modules フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9e395-112">If you do not have an internet connection, install xActiveDirectory to another machine and then copy the xActiveDirectory folder to the "C:\Program Files\WindowsPowerShell\Modules" folder on your machine.</span></span>

<span data-ttu-id="9e395-113">インストールに成功したか確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9e395-113">To confirm the installation succeeded, run the following command:</span></span>
```PowerShell
Get-Module xActiveDirectory -ListAvailable
```

#### <a name="set-up-a-domain-with-dsc"></a><span data-ttu-id="9e395-114">DSC を使用したドメインのセットアップ</span><span class="sxs-lookup"><span data-stu-id="9e395-114">Set up a domain with DSC</span></span>
<span data-ttu-id="9e395-115">PowerShell で次のスクリプトをコピーして、お使いのコンピューターを新しいドメインのドメイン コントローラーにします。</span><span class="sxs-lookup"><span data-stu-id="9e395-115">Copy the following script in PowerShell to make your machine a Domain Controller in a new domain.</span></span>
<span data-ttu-id="9e395-116">**著者のメモ: 指定した資格情報が使用されないという既知の問題があります。安全のため、ローカルの管理者パスワードを忘れないようにしてください。**</span><span class="sxs-lookup"><span data-stu-id="9e395-116">**AUTHOR'S NOTE: THERE IS A KNOWN ISSUE WITH THE CREDENTIALS PROVIDED NOT BEING USED.  TO BE SAFE, DON'T FORGET YOUR LOCAL ADMIN PASSWORD.**</span></span>

```PowerShell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value $env:COMPUTERNAME -Force

# This "MetaConfiguration" sets the DSC Engine to automatically reboot if required
[DscLocalConfigurationManager()]
Configuration MetaConfiguration
{
    Node $env:Computername
    {
        Settings
        {
            RebootNodeIfNeeded = $true
        }
    }

}

MetaConfiguration
# Apply the MetaConfiguration
Set-DscLocalConfigurationManager .\MetaConfiguration

# Configure a domain controller of a new "Contoso" domain
configuration DomainController
{
    param
    (
        $node,
        $cred
    )
    Import-DscResource -ModuleName xActiveDirectory

    Node $node
    {
        WindowsFeature ADDS
        {
            Ensure = 'Present'
            Name = 'AD-Domain-Services'
        }

        xADDomain Contoso
        {
            DomainName = 'contoso.com'
            DomainAdministratorCredential = $cred
            SafemodeAdministratorPassword = $cred
            DependsOn = '[WindowsFeature]ADDS'
        }

        file temp
        {
            DestinationPath = 'C:\temp.txt'
            Contents = 'Domain has been created'
            DependsOn = '[xADDomain]Contoso'
        }
    }
}

$ConfigData = @{
    AllNodes = @(
        @{
            NodeName = $env:Computername
            PSDscAllowPlainTextPassword = $true
        }
    )
}

# Enter your desired password for the domain administrator (note, this will be stored as plain text)
DomainController -cred (Get-Credential -Message "Enter desired credential for domain administrator") -node $env:Computername -configurationData $ConfigData

# Apply the configuration to create the domain controller
Start-DSCConfiguration -path .\DomainController -ComputerName $env:Computername -Wait -Force -Verbose
```
<span data-ttu-id="9e395-117">コンピューターが数回再起動します。</span><span class="sxs-lookup"><span data-stu-id="9e395-117">Your machine will restart a few times.</span></span>
<span data-ttu-id="9e395-118">ドメインが作成されたことを伝える C:\temp.txt というファイルが表示されたら、プロセスは完了しています。</span><span class="sxs-lookup"><span data-stu-id="9e395-118">You will know the process is complete once you see a file called "C:\temp.txt" containing "Domain has been created."</span></span>

#### <a name="set-up-users-and-groups"></a><span data-ttu-id="9e395-119">ユーザーとグループの設定</span><span class="sxs-lookup"><span data-stu-id="9e395-119">Set up Users and Groups</span></span>
<span data-ttu-id="9e395-120">次のコマンドは、ドメインにオペレーターとヘルプデスクのグループ、またそのグループのメンバーである対応する管理者以外のユーザーを設定します。</span><span class="sxs-lookup"><span data-stu-id="9e395-120">The following commands will set up an Operator and Helpdesk group in your domain and a corresponding non-administrator user who is a member of that group.</span></span>
```PowerShell
# Make Groups
$NonAdminOperatorGroup = New-ADGroup -Name "JEA_NonAdmin_Operator" -GroupScope DomainLocal -PassThru
$NonAdminHelpDeskGroup = New-ADGroup -Name "JEA_NonAdmin_HelpDesk" -GroupScope DomainLocal -PassThru
$TestGroup = New-ADGroup -Name "Test_Group" -GroupScope DomainLocal -PassThru

# Make Users
$OperatorUser = New-ADUser -Name "OperatorUser" -AccountPassword (ConvertTo-SecureString 'pa$$w0rd' -AsPlainText -Force) -PassThru
Enable-ADAccount -Identity $OperatorUser

$HelpDeskUser = New-ADUser -name "HelpDeskUser" -AccountPassword (ConvertTo-SecureString 'pa$$w0rd' -AsPlainText -Force) -PassThru
Enable-ADAccount -Identity $HelpDeskUser

# Add Users to Groups
Add-ADGroupMember -Identity $NonAdminOperatorGroup -Members $OperatorUser
Add-ADGroupMember -Identity $NonAdminHelpDeskGroup -Members $HelpDeskUser
```

