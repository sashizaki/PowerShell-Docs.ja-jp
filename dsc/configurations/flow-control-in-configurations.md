---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成内での条件付きステートメントとループ
ms.openlocfilehash: 0073d94d28afbb45bb635442129a6cddde4c805a
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402317"
---
# <a name="conditional-statements-and-loops-in-configurations"></a>構成内での条件付きステートメントとループ

行うことができます、[構成](configurations.md)より動的な PowerShell のフロー制御キーワードを使用します。 この記事では説明する条件付きのステートメントとループを使用して、動的な構成を作成する方法。 結合条件とループの[パラメーター](add-parameters-to-a-configuration.md)と[構成データ](configData.md)できる柔軟性と制御の構成をコンパイルするときにします。

関数またはスクリプト ブロックと同じようには、構成内の任意の PowerShell 言語を使用できます。 使用するステートメントは、".mof"ファイルをコンパイルするための構成を呼び出すときにのみ評価されます。 次の例では、概念を説明する単純なシナリオを説明します。 条件は、ループはパラメーターと構成データをよりよく使用されます。

この簡単な例で、**サービス**リソース ブロックは、現在の状態を保持する".mof"ファイルを生成するコンパイル時に、サービスの現在の状態を取得します。

> [!NOTE]
> 動的リソースのブロックを使用すると、Intellisense の有効性を切断します。 PowerShell のパーサーでは、構成をコンパイルするまで指定された値が許容されるかどうかを判断できません。

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        Service Spooler
        {
            Name = "Spooler"
            State = $(Get-Service -Name 'spooler').Status
            StartType = $(Get-Service -Name 'spooler').StartType
        }
    }
}
```

さらに、作成することが、**サービス**ブロックの現在のコンピューター上のすべてのサービスのリソースを使用して、`foreach`ループします。

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        Foreach ($service in $(Get-Service))
        {
            Service $service.Name
            {
                Name = $service.Name
                State = $service.Status
                StartType = $service.StartType
            }
        }
    }
}
```

単純なを使用してオンラインでマシンの構成を作成することだけでした`if`ステートメント。

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration

    Foreach ($computer in @('Server01', 'Server02', 'Server03'))
    {
        if (Test-Connection -ComputerName $computer)
        {
            Node $computer
            {
                Service "Spooler"
                {
                    Name = "Spooler"
                    State = "Started"
                }
            }
        }
    }
}
```

> [!NOTE]
> 動的なリソースは、上記の例のリファレンスで、現在のコンピューターをブロックします。 構成を作成しているコンピューターになる、このインスタンスは、ターゲット ノードではありません。

<!---
Mention Get-DSCConfigurationFromSystem
-->

## <a name="summary"></a>要約

要約すると、構成内の任意の PowerShell 言語を使用することができます。

これなどが含まれます。

- カスタム オブジェクト
- ハッシュ テーブル
- 文字列操作
- リモート処理
- WMI と CIM
- Active Directory オブジェクト
- その他...

構成で定義されている任意の PowerShell コードがコンパイル時に評価されますが、構成を含むスクリプトのコードを配置することもできます。 構成ブロック外の任意のコードは、構成をインポートするときに実行されます。

## <a name="see-also"></a>関連項目

- [構成にパラメーターを追加する](add-parameters-to-a-configuration.md)
- [構成から構成データを分離する](configData.md)
