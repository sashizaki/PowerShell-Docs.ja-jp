---
title: "DSC を使用した初回起動時の仮想マシンの構成"
ms.date: 2016-05-16
keywords: PowerShell, DSC
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
ms.openlocfilehash: 38751d62a56dc90ff69fe3ab6e92829fb33edb2b
ms.sourcegitcommit: a81ffb39f370b95ae802cd054dc4480c9e68cf77
translationtype: HT
---
>適用先: Windows PowerShell 5.0

>**注:** このトピックで説明されている **DSCAutomationHostEnabled** レジストリ キーは、PowerShell 4.0 では使用できません。
PowerShell 4.0 の初回起動時に、新しい仮想マシンを構成する方法については、「[Want to Automatically Configure Your Machines Using DSC at Initial Boot-up?](https://blogs.msdn.microsoft.com/powershell/2014/02/28/want-to-automatically-configure-your-machines-using-dsc-at-initial-boot-up/)」 (初回起動時に DSC を使用して自動的にマシンを構成する方法) をご覧ください。

# <a name="configure-a-virtual-machines-at-initial-boot-up-by-using-dsc"></a>DSC を使用した初回起動時の仮想マシンの構成

## <a name="requirements"></a>要件

これらの例を実行するには、以下が必要になります。

- 作業する起動可能な VHD。 bpt id="p1" xmlns="urn:oasis:names:tc:xliff:document:1.2">  [</bpt>TechNet Evaluation Center](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2016) で、Windows Server 2016 の評価版と共に ISO をダウンロードできます。 「[Creating Bootable Virtual Hard Disks](https://technet.microsoft.com/en-us/library/gg318049.aspx)」 (起動可能な仮想ハード ディスクの作成) で、ISO イメージから VHD を作成する方法に関する手順を参照してください。
- Hyper-V が有効なホスト コンピューター。 詳細については、「[Hyper-V の概要](https://technet.microsoft.com/library/hh831531.aspx)」をご覧ください。

DSC を使用すると、ソフトウェアのインストールと初回起動時のコンピューターの構成を自動化できます。
初回起動時のプロセスで実行されるように、起動可能なメディア (VHD など) に構成 MOF ドキュメントまたはメタ構成のいずれかを挿入して、この操作を行います。
この動作は、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies** の下の [DSCAutomationHostEnabled レジストリ キー](DSCAutomationHostEnabled.md)で指定されます。
このキーの既定値は 2 です。これは、初回起動時に DSC を実行することを許可します。

初回起動時に DSC を実行しない場合は、[DSCAutomationHostEnabled レジストリ キー](DSCAutomationHostEnabled.md)を 0 に設定します。

- 構成 MOF ドキュメントを VHD に挿入する
- DSC のメタ構成を VHD に挿入する
- 起動時の DSC を無効にする

>**注:** `Pending.mof` と `MetaConfig.mof` を同時にコンピューターに挿入することができます。
両方のファイルが存在する場合、`MetaConfig.mof` に指定された設定が優先されます。

## <a name="inject-a-configuration-mof-document-into-a-vhd"></a>構成 MOF ドキュメントを VHD に挿入する

初回起動時に構成を適用するために、コンパイル済みの構成 MOF ドキュメントをその `Pending.mof` ファイルとして VHD に挿入できます。
**DSCAutomationHostEnabled** レジストリ キーを 2 (既定値) に設定した場合、コンピューターが最初に起動されたときに、DSC では `Pending.mof` で定義された構成を適用します。

この例では次の構成を使用します。ここでは、新しいコンピューターに IIS をインストールします。

```powershell
Configuration SampleIISInstall
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    node ('localhost')
    {
        WindowsFeature IIS
        {
            Ensure = 'Present'
            Name   = 'Web-Server'
        }
    }
}
```

### <a name="to-inject-the-configuration-mof-document-on-the-vhd"></a>VHD 上で構成 MOF ドキュメントを挿入するには

1. [Mount-VHD](https://technet.microsoft.com/library/hh848551.aspx) コマンドレットを呼び出して、構成を挿入する VHD をマウントします。 たとえば、次のように入力します。

    ```powershell
    Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
    ```
2. PowerShell 5.0 以降を実行しているコンピューターで、上記の構成 (**SampleIISInstall**) を PowerShell スクリプト (.ps1) ファイルとして保存します。

3. PowerShell コンソールで、.ps1 ファイルを保存したフォルダーに移動します。

4. 次の PowerShell コマンドを実行して、MOF ドキュメントをコンパイルします (DSC 構成のコンパイルについては、「[DSC 構成](configurations.md)」をご覧ください):

    ```powershell
    . .\SampleIISInstall.ps1
    SampleIISInstall
    ```

5. この操作を行うと、`SampleIISInstall` という名前の新しいフォルダーに、`localhost.mof` ファイルが作成されます。
[Move-Item](https://technet.microsoft.comlibrary/hh849852.aspx) コマンドレットを使用して、`Pending.mof` に名前を変更し、VHD の適切な場所にそのファイルを移動します。 たとえば、次のように入力します。

    ```powershell
        Move-Item -Path C:\DSCTest\SampleIISInstall\localhost.mof -Destination E:\Windows\Sytem32\Configuration\Pending.mof
    ```
6. [Dismount-VHD](https://technet.microsoft.com/library/hh848562.aspx) コマンドレットを呼び出して、VHD のマウントを解除します。 たとえば、次のように入力します。

    ```powershell
    Dismount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
    ```

7. DSC MOF ドキュメントをインストールした VHD を使用して、VM を作成します。 初回起動が行われ、オペレーティング システムがインストールされると、IIS がインストールされます。
[Get-WindowsFeature](https://technet.microsoft.com/library/jj205469.aspx) コマンドレットを呼び出して、これを確認することができます。

## <a name="inject-a-dsc-metaconfiguration-into-a-vhd"></a>DSC のメタ構成を VHD に挿入する

メタ構成 (「[ローカル構成マネージャーの構成](metaConfig.md)」を参照) をその `MetaConfig.mof` ファイルとして VHD に挿入して、コンピューターが初回起動時に構成をプルするように構成することもできます。
**DSCAutomationHostEnabled** レジストリ キーを 2 (既定値) に設定した場合、コンピューターが最初に起動されたときに、DSC は `MetaConfig.mof` で定義されたメタ構成を LCM に適用します。
メタ構成で LCM がプル サーバーから構成をプルする必要があることを指定した場合、コンピューターは初回起動時にプル サーバーから構成をプルしようとします。
DSC プル サーバーのセットアップについては、「[DSC Web プル サーバーのセットアップ](pullServer.md)」をご覧ください。

この例では、前のセクションで示された構成 (**SampleIISInstall**)、および次のメタ構成の両方を使用します。

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientBootstrap
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = '140a952b-b9d6-406b-b416-e0f759c9c0e4'
            ConfigurationNames = @('SampleIISInstall')
        }
    }
}
```

### <a name="to-inject-the-metaconfiguration-mof-document-on-the-vhd"></a>VHD 上でメタ構成 MOF ドキュメントを挿入するには

1. [Mount-VHD](https://technet.microsoft.com/library/hh848551.aspx) コマンドレットを呼び出して、メタ構成を挿入する VHD をマウントします。 たとえば、次のように入力します。

    ```powershell
    Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
    ```

2. [DSC Web プル サーバーをセットアップ](pullServer.md)して、**SampleIISInistall** 構成を適切なフォルダーに保存します。

3. PowerShell 5.0 以降を実行しているコンピューターで、上記のメタ構成 (**PullClientBootstrap**) を PowerShell スクリプト (.ps1) ファイルとして保存します。

4. PowerShell コンソールで、.ps1 ファイルを保存したフォルダーに移動します。

5. 次の PowerShell コマンドを実行して、メタ構成 MOF ドキュメントをコンパイルします (DSC 構成のコンパイルについては、「[DSC 構成](configurations.md)」をご覧ください)。

    ```powershell
    . .\PullClientBootstrap.ps1
    PullClientBootstrap
    ```

6. この操作を行うと、`PullClientBootstrap` という名前の新しいフォルダーに、`localhost.meta.mof` ファイルが作成されます。
[Move-Item](https://technet.microsoft.comlibrary/hh849852.aspx) コマンドレットを使用して、`MetaConfig.mof` に名前を変更し、VHD の適切な場所にそのファイルを移動します。

    ```powershell
    Move-Item -Path C:\DSCTest\PullClientBootstrap\localhost.meta.mof -Destination E:\Windows\Sytem32\Configuration\MetaConfig.mof
    ```

7. [Dismount-VHD](https://technet.microsoft.com/library/hh848562.aspx) コマンドレットを呼び出して、VHD のマウントを解除します。 たとえば、次のように入力します。

    ```powershell
    Dismount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
    ```

8. DSC MOF ドキュメントをインストールした VHD を使用して、VM を作成します。
初回起動が行われ、オペレーティング システムがインストールされると、DSC はプル サーバーから構成をプルして、IIS がインストールされます。
[Get-WindowsFeature](https://technet.microsoft.com/library/jj205469.aspx) コマンドレットを呼び出して、これを確認することができます。

## <a name="disable-dsc-at-boot-time"></a>起動時の DSC を無効にする

既定では、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\DSCAutomationHostEnabled** キーの値は 2 に設定されます。これにより、コンピューターの状態が保留中または最新の場合に、DSC 構成を実行することを許可します。 初回起動時に構成を実行しない場合は、このキーの値を 0 に設定する必要があります。

1. [Mount-VHD](https://technet.microsoft.com/library/hh848551.aspx) コマンドレットを呼び出して、VHD をマウントします。 たとえば、次のように入力します。

    ```powershell
    Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
    ```

2. `reg load` を呼び出して、VHD からレジストリの **HKLM\Software** サブキーを読み込みます。

    ```
    reg load HKLM\Vhd E:\Windows\System32\Config\Software`
    ```

3. PowerShell レジストリ プロバイダーを使用して、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\*** に移動します。

    ```powershell
    Set-Location HKLM:\Software\Microsoft\Windows\CurrentVersion\Policies`
    ```

4. `DSCAutomationHostEnabled` の値を 0 に変更します。

    ```powershell
    Set-ItemProperty -Path . -Name DSCAutomationHostEnabled -Value 0
    ```

5. 次のコマンドを実行して、レジストリをアンロードします。

    ```powershell
    [gc]::Collect()
    reg unload HKLM\Vhd
    ```

## <a name="see-also"></a>参照

- [DSC 構成](configurations.md)
- [DSCAutomationHostEnabled レジストリ キー](DSCAutomationHostEnabled.md)
- [ローカル構成マネージャー (LCM) の構成](metaConfig.md)
- [DSC Web プル サーバーのセットアップ](pullServer.md)
