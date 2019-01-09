---
ms.date: 12/12/2018
keywords: dsc、powershell、resource、ギャラリーのセットアップ
title: 構成にパラメーターを追加する
ms.openlocfilehash: 15213404f0cdd6416baf1f83af91b8f5279cc97f
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402557"
---
# <a name="add-parameters-to-a-configuration"></a>構成にパラメーターを追加する

などの関数、[構成](configurations.md)ユーザー入力に基づいて動的な構成を許可するパラメーター化することができます。 手順で説明したものと似ています[パラメーターを受け取る関数](/powershell/module/microsoft.powershell.core/about/about_functions)します。

この例では、「実行」、"Spooler"サービスを構成する基本的な構成を開始します。

```powershell
Configuration TestConfig
{
    # It is best practice to implicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node localhost
    {
        Service 'Spooler'
        {
            Name = 'Spooler'
            State = 'Running'
        }
    }
}
```

## <a name="built-in-configuration-parameters"></a>組み込みの構成パラメーター

関数とは異なり、 [CmdletBinding](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute)属性を使用しないため、機能を追加します。 ほかに[共通パラメーター](/powershell/module/microsoft.powershell.core/about/about_commonparameters)構成には、次のパラメーターを定義することがなく組み込みが使用してもできます。

|パラメーター  |説明  |
|---------|---------|
|`-InstanceName`|定義で使用される[複合構成](compositeconfigs.md)|
|`-DependsOn`|定義で使用される[複合構成](compositeconfigs.md)|
|`-PSDSCRunAsCredential`|定義で使用される[複合構成](compositeconfigs.md)|
|`-ConfigurationData`|渡すために使用で構造化[構成データ](configData.md)構成で使用します。|
|`-OutputPath`|場所を指定するために使用して"\<computername\>.mof"ファイルがコンパイルされます|

## <a name="adding-your-own-parameters-to-configurations"></a>構成への独自のパラメーターの追加

組み込みのパラメーターだけでなく、構成を独自のパラメーターを追加することもできます。 パラメーターのブロックは、関数と同様、構成の宣言内に直接移動します。 構成パラメーターのブロックは、いずれかの外から**ノード**宣言、および上*インポート*ステートメント。 パラメーターを追加するより堅牢で動的に、構成を行うことができます。

```powershell
Configuration TestConfig
{
    param
    (

    )
```

### <a name="add-a-computername-parameter"></a>ComputerName パラメーターを追加します。

最初のパラメーターを追加する場合がありますが、`-Computername`パラメーターのいずれかの".mof"ファイルを動的にコンパイルできるように`-Computername`の構成を渡します。 関数のように定義することも、既定値をユーザーに値を渡さない場合 `-ComputerName`

```powershell
param
(
    [String]
    $ComputerName="localhost"
)
```

内の構成を指定できます、`-ComputerName`パラメーター ノードのブロックを定義するときにします。

```powershell
Node $ComputerName
{

}
```

### <a name="calling-your-configuration-with-parameters"></a>パラメーターを持つ構成を呼び出す

構成にパラメーターを追加した後、コマンドレットを使用した場合と同様にだけ使用することができます。

```powershell
TestConfig -ComputerName "server01"
```

### <a name="compiling-multiple-mof-files"></a>複数の .mof ファイルをコンパイルします。

ノード ブロックでは、コンピューター名のコンマ区切りのリストを受け入れることがもでき、各".mof"ファイルが生成されます。 渡されるコンピューターのすべての".mof"ファイルを生成する次の例を実行することができます、`-ComputerName`パラメーター。

```powershell
Configuration TestConfig
{
    param
    (
        [String]
        $ComputerName="localhost"
    )

    # It is best practice to implicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service 'Spooler'
        {
            Name = 'Spooler'
            State = 'Running'
        }
    }
}

TestConfig -ComputerName "server01", "server02", "server03"
```

## <a name="advanced-parameters-in-configurations"></a>高度なパラメーターの構成

加え、`-ComputerName`パラメーター、サービス名と状態のパラメーターを追加することができます。 次の例では、パラメーター ブロックを`-ServiceName`パラメーター オブジェクトを動的に定義を使用して、**サービス**リソース ブロック。 さらに追加、`-State`を動的に定義するパラメーター、**状態**で、**サービス**リソース ブロック。

```powershell
Configuration TestConfig
{
    param
    (
        [String]
        $ServiceName,

        [String]
        $State,

        [String]
        $ComputerName="localhost"
    )

    # It is best practice to implicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service $ServiceName
        {
            Name = $ServiceName
            State = $State
        }
    }
}
```

> [!NOTE]
> 多くの advacned シナリオより適切に構造化、動的なデータを移動する必要があります[構成データ](configData.md)します。

構成を今すぐこの例では、動的`$ServiceName`が、いずれかが指定されていない場合は、コンパイル エラーが発生します。 この例のように既定値を追加できます。

```powershell
[String]
$ServiceName="Spooler"
```

このインスタンスで、方の値を指定するユーザーを実行するだけでは、`$ServiceName`パラメーター。 `parameter`属性を使用すると、それ以上の検証とパイプライン サポートの構成のパラメーターを追加します。

追加のパラメーター宣言の上、`parameter`次の例のように、属性ブロックします。

```powershell
[parameter()]
[String]
$ServiceName
```

各引数を指定できます`parameter`属性、定義されているパラメーターの要素を制御します。 次の例では、 `$ServiceName` 、**必須**パラメーター。

```powershell
[parameter(Mandatory)]
[String]
$ServiceName
```

`$State`パラメーター、今回は、ユーザーが定義済みセット以外の値を指定することを防ぐために (停止、実行など)、`ValidationSet*`ユーザーなるため (実行されているなどの定義済みセット以外の値を指定する属性停止) します。 次の例では、追加、`ValidationSet`属性を`$State`パラメーター。 作成したくないので、`$State`パラメーター**必須**は既定値を追加する必要があります。

```powershell
[ValidateSet("Running", "Stopped")]
[String]
$State="Running"
```

> [!NOTE]
> 指定する必要はありません、`parameter`属性を使用する場合、`validation`属性。

詳細をご覧ください、`parameter`と検証属性で[指示](/powershell/module/microsoft.powershell.core/about/about_Functions_Advanced_Parameters.md)します。

## <a name="fully-parameterized-configuration"></a>完全にパラメーター化された構成

パラメーター化された構成を指定するユーザーが強制的にある、 `-InstanceName`、 `-ServiceName`、し、検証、`-State`パラメーター。

```powershell
Configuration TestConfig
{
    param
    (
        [parameter(Mandatory)]
        [String]
        $ServiceName,

        [ValidateSet("Running","Stopped")]
        [String]
        $State="Running",

        [String]
        $ComputerName="localhost",
    )

    # It is best practice to implicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node localhost
    {
        Service $ServiceName
        {
            Name = $ServiceName
            State = $State
        }
    }
}
```

## <a name="see-also"></a>関連項目

- [DSC 構成のヘルプを作成する](configHelp.md)
- [動的構成](flow-control-in-configurations.md)
- [構成データを使用して、構成で](configData.md)
- [別の構成と環境データ](separatingEnvData.md)
