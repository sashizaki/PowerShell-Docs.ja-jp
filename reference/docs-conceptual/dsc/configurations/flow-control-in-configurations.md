---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成内での条件付きステートメントとループ
ms.openlocfilehash: 0073d94d28afbb45bb635442129a6cddde4c805a
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954079"
---
# <a name="conditional-statements-and-loops-in-configurations"></a>構成内での条件付きステートメントとループ

PowerShell のフロー制御キーワードを使って、[構成](configurations.md)をより動的にすることができます。 この記事では、条件ステートメントとループを使って構成をより動的にする方法を説明します。 条件とループを[パラメーター](add-parameters-to-a-configuration.md)および[構成データ](configData.md)と組み合わせることで、構成をコンパイルするときの柔軟性と制御が増します。

関数またはスクリプト ブロックと同じように、構成内で任意の PowerShell 言語を使用できます。 使用するステートメントは、".mof" ファイルをコンパイルするために構成を呼び出すときにのみ評価されます。 次の例では、簡単なシナリオを使って概念を説明します。 条件とループは、パラメーターや構成データと共に使われることがよくあります。

この簡単な例では、**Service** リソース ブロックでコンパイル時にサービスの現在の状態を取得し、現在の状態を保持する ".mof" ファイルを生成します。

> [!NOTE]
> 動的な Resource ブロックを使うと、IntelliSense の有効性は失われます。 PowerShell のパーサーでは、構成がコンパイルされるまで、指定された値が許容されるかどうかを判断できません。

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

さらに、`foreach` ループを使って、現在のコンピューター上のすべてのサービスに対して **Service** ブロック リソースを作成できます。

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

また、簡単な `if` ステートメントを使うことで、オンラインになっているコンピューターに対してのみ構成を作成することができます。

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
> 上の例の動的なリソース ブロックでは、現在のコンピューターが参照されています。 このインスタンスでは、それはターゲット ノードではなく、構成を作成しているコンピューターです。

<!---
Mention Get-DSCConfigurationFromSystem
-->

## <a name="summary"></a>要約

まとめると、構成内では任意の PowerShell 言語を使うことができます。

これには次のものが含まれます。

- カスタム オブジェクト
- ハッシュテーブル
- 文字列操作
- リモート処理
- WMI と CIM
- ActiveDirectory オブジェクト
- その他...

構成で定義されているすべての PowerShell コードはコンパイル時に評価されますが、構成を含むスクリプトにコードを配置することもできます。 構成ブロックの外部にあるすべてのコードは、構成をインポートするときに実行されます。

## <a name="see-also"></a>関連項目

- [構成にパラメーターを追加する](add-parameters-to-a-configuration.md)
- [構成から構成データを分離する](configData.md)
