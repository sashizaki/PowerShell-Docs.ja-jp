---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: ノードの相互依存関係の指定
ms.openlocfilehash: 1bdfbd9f8a94809d6bf410eff525e1c877fb6aad
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402198"
---
# <a name="specifying-cross-node-dependencies"></a>ノードの相互依存関係の指定

> 適用先:Windows PowerShell 5.0

DSC には、**WaitForAll**、**WaitForAny**、**WaitForSome** などの特別なリソースが用意されています。このリソースを構成で使用すると、他のノードの構成への依存関係を指定することができます。 これらのリソースの動作は次のとおりです。

- **WaitForAll**:指定されたリソースがで定義されているすべてのターゲット ノードで目的の状態の場合、成功、 **NodeName**プロパティ。
- **WaitForAny**:指定されたリソースが目的の状態では、少なくとも 1 つで定義されているターゲット ノードの場合、成功、 **NodeName**プロパティ。
- **WaitForSome**:指定します、 **NodeCount**プロパティに加え、 **NodeName**プロパティ。 リソースは、**NodeName** プロパティで定義されたノードの最小数 (**NodeCount** で指定) で目的の状態になった場合に成功します。

## <a name="syntax"></a>構文

**WaitForAll**と**WaitForAny**リソースが同じ構文を共有します。 置換\<ResourceType\>いずれかでは、次の例で**WaitForAny**または**WaitForAll**します。
ように、 **DependsOn**キーワード、名前を"[ResourceType] ResourceName"として書式設定する必要があります。 リソースが個別に属している場合[構成](configurations.md)、含める、 **ConfigurationName**書式設定された文字列で"[ResourceType] ResourceName:: [ConfigurationName]:: [ConfigurationName]"。 **NodeName**がコンピューター、またはノードで、現在のリソースが待機する必要があります。

```
<ResourceType> [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential]]
    [ RetryCount = [Uint32] ]
    [ RetryIntervalSec = [Uint64] ]
    [ ThrottleLimit = [Uint32]]
}
```

**WaitForSome**リソースは追加しますが、上記の例のような構文、 **NodeCount**キー。 **NodeCount**数のノードで、現在のリソースを待機する必要がありますかを示します。

```
WaitForSome [String] #ResourceName
{
    NodeCount = [UInt32]
    NodeName = [string[]]
    ResourceName = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [RetryCount = [UInt32]]
    [RetryIntervalSec = [UInt64]]
    [ThrottleLimit = [UInt32]]
}
```

すべて**WaitForXXXX**構文の次のキーを共有します。

| プロパティ | 説明 | |RetryIntervalSec |再試行するまでの秒数。 最小値は 1 |。|RetryCount |再試行の回数の最大数 |。|ThrottleLimit |同時に接続するコンピューターの数。 既定値は`New-CimSession`既定 | |。DependsOn |このリソースを構成する前に、別のリソースの構成を実行する必要があることを示します。 詳細については、次を参照してください[DependsOn](resource-depends-on.md)| |。PsDscRunAsCredential |参照してください[ユーザーの資格情報での DSC の使用](./runAsUser.md) |


## <a name="using-waitforxxxx-resources"></a>WaitForXXXX リソースの使用

各**WaitForXXXX**リソースが、指定したノードで完了までに、指定されたリソースを待機します。 その他のリソースで同じ構成できますし、*に依存して*、 **WaitForXXXX**リソースを使用して、 **DependsOn**キー。

たとえば、次の構成では、ターゲット ノードは **MyDC** ノード上の **xADDomain** リソースが完了するまで 15 秒間隔で最大 30 回試行しながら待機した後、ドメインに参加できるようになります。

```powershell
Configuration JoinDomain
{
    Import-DscResource -Module xComputerManagement, xActiveDirectory

    Node myDC
    {
        WindowsFeature InstallAD
        {
            Ensure = 'Present'
            Name = 'AD-Domain-Services'
        }

        xADDomain NewDomain
        {
            DomainName = 'Contoso.com'
            DomainAdministratorCredential = (Get-Credential)
            SafemodeAdministratorPassword = (Get-Credential)
            DatabasePath = "C:\Windows\NTDS"
            LogPath = "C:\Windows\NTDS"
            SysvolPath = "C:\Windows\Sysvol"
        }
    }

    Node myDomainJoinedServer
    {
        WaitForAll DC
        {
            ResourceName      = '[xADDomain]NewDomain'
            NodeName          = 'MyDC'
            RetryIntervalSec  = 15
            RetryCount        = 30
        }

        xComputer JoinDomain
        {
            Name             = 'myPC'
            DomainName       = 'Contoso.com'
            Credential       = (Get-Credential)
            DependsOn        ='[WaitForAll]DC'
        }
    }
}
```

構成をコンパイルするときに、2 つの".mof"ファイルが生成されます。 使用してターゲット ノードに".mof"の両方のファイルを適用、 [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration)コマンドレット

>**注:** 既定では、WaitForXXX リソースは 1 回試行してから失敗します。 指定する、通常は必要ありません、 **RetryCount**と**RetryIntervalSec**します。

## <a name="see-also"></a>参照

- [DSC 構成](configurations.md)
- [リソースの依存関係を使用して、](resource-depends-on.md)
- [DSC リソース](../resources/resources.md)
- [ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)
