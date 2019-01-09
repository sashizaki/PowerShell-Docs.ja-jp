---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC 構成
ms.openlocfilehash: 6af27f442de3080facd65892c713c989d0e388c5
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402581"
---
# <a name="dsc-configurations"></a>DSC 構成

> 適用先:Windows PowerShell 4.0、Windows PowerShell 5.0

DSC 構成は、特殊な関数を定義する PowerShell スクリプトです。
構成を定義するには、PowerShell キーワード **Configuration** を使用します。

```powershell
Configuration MyDscConfiguration {
    Node "TEST-PC1" {
        WindowsFeature MyFeatureInstance {
            Ensure = 'Present'
            Name = 'RSAT'
        }
        WindowsFeature My2ndFeatureInstance {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}
MyDscConfiguration
```

としてスクリプトを保存、`.ps1`ファイル。

## <a name="configuration-syntax"></a>構成構文

構成スクリプトは次の部分で構成されます。

- **Configuration** ブロック。 これは、最も外側にあるスクリプト ブロックです。 このブロックを定義するには、**Configuration** キーワードを使用し、名前を指定します。 この場合、構成の名前は "MyDscConfiguration" です。
- 1 つまたは複数の **Node** ブロック。 これらは、構成するノード (コンピューターまたは VM) を定義します。 上記の構成には、"TEST-PC1" という名前のコンピューターを対象とする 1 つの **Node** ブロックがあります。 ノード ブロックには、複数のコンピューター名を受け入れることができます。
- 1 つまたは複数のリソース ブロック。 ここでは、構成するリソースのプロパティを設定します。 この場合は、それぞれ "WindowsFeature" リソースを呼び出す 2 つのリソース ブロックがあります。

**Configuration** ブロック内では、通常 PowerShell 関数内で可能なすべてのことを行うことができます。 たとえば、前の例では、ターゲット コンピューターの名前を構成内でハード コードしなかった場合、ノード名のパラメーターを追加できます。

この例では、構成のコンパイル時にノードの名前を **ComputerName** パラメーターとして渡すことで、ノードの名前を指定します。 名前の既定値は "localhost" です。

```powershell
Configuration MyDscConfiguration
{
    param
    (
        [string[]]$ComputerName='localhost'
    )

    Node $ComputerName
    {
        WindowsFeature MyFeatureInstance
        {
            Ensure = 'Present'
            Name = 'RSAT'
        }

        WindowsFeature My2ndFeatureInstance
        {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}

MyDscConfiguration
```

**ノード**ブロックは、複数のコンピューター名にも使用できます。 上記の例で使用するか、`-ComputerName`パラメーター、またはコンマで区切られたパスのリストを直接使用するコンピューターの**ノード**ブロックします。

```powershell
MyDscConfiguration -ComputerName "localhost", "Server01"
```

コンピューターの一覧を指定するときに、**ノード**ブロック、構成では、内から配列表記を使用する必要があります。

```powershell
Configuration MyDscConfiguration
{
    Node @('localhost', 'Server01')
    {
        WindowsFeature MyFeatureInstance
        {
            Ensure = 'Present'
            Name = 'RSAT'
        }

        WindowsFeature My2ndFeatureInstance
        {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}

MyDscConfiguration
```

## <a name="compiling-the-configuration"></a>構成のコンパイル

構成を適用する前に、MOF ドキュメントにコンパイルする必要があります。
そのためには、PowerShell 関数の場合と同じように構成を呼び出します。
例の最後の行には構成を呼び出すための構成の名前のみが含まれています。

> [!NOTE]
> 構成を呼び出すには、(他の PowerShell 関数と同様に) 関数がグローバル スコープ内にある必要があります。
> そのためには、スクリプトで "ドット ソース" を行うか、F5 キーを使用するか、または ISE で **[スクリプトの実行]** をクリックして、構成スクリプトを実行します。
> スクリプトでドット ソースを行うには、構成を含むスクリプト ファイルの名前が `myConfig.ps1` である場合、`. .\myConfig.ps1` でコマンドを実行します。

構成を呼び出すと、結果は次のようになります。

- すべての変数が解決されます
- 構成と同じ名前のフォルダーが現在のディレクトリ内に作成されます。
- _NodeName_.mof という名前のファイルが新しいディレクトリ内に作成されます。_NodeName_ は、構成のターゲット ノードの名前です。
  1 つ以上のノードがある場合、MOF ファイルがノードごとに作成されます。

> [!NOTE]
> MOF ファイルには、ターゲット ノードのすべての構成情報が含まれています。 このため、このファイルをセキュリティ保護することが重要です。
> 詳細については、「[MOF ファイルのセキュリティ保護](../pull-server/secureMOF.md)」を参照してください。

上記の最初の構成をコンパイルすると、次のフォルダー構造となります。

```powershell
. .\MyDscConfiguration.ps1
MyDscConfiguration
```

```
    Directory: C:\users\default\Documents\DSC Configurations\MyDscConfiguration
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       10/23/2015   4:32 PM           2842 localhost.mof
```

2 番目の例のように構成でパラメーターを受け取る場合は、コンパイル時に指定する必要があります。 その場合、次のようになります。

```powershell
. .\MyDscConfiguration.ps1
MyDscConfiguration -ComputerName 'MyTestNode'
```

```
    Directory: C:\users\default\Documents\DSC Configurations\MyDscConfiguration
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       10/23/2015   4:32 PM           2842 MyTestNode.mof
```

## <a name="using-new-resources-in-your-configuration"></a>構成での新しいリソースの使用

前の例を実行した場合、リソースを明示的にインポートしないで使用することについて警告されることがあります。
今日、DSC には PSDesiredStateConfiguration モジュールの一部として 12 のリソースが付属しています。

コマンドレット [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) を使用して、どのリソースがシステムにインストールされ、LCM で使用できるかを決定できます。
これらのモジュールが `$env:PSModulePath` に配置され、[Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) によって正しく認識された後、構成内に読み込む必要があります。

**Import-dscresource**内でのみ認識できる動的キーワードには、**構成**ブロック、コマンドレットではありません。
**Import-DscResource** は、次の 2 つのパラメーターをサポートしています。

- **ModuleName** は、**Import-DscResource** を使用する場合に推奨される方法です。 これは、インポートするリソースを含むモジュールの名前 (およびモジュール名の文字列配列) を受け取ります。
- **Name** は、インポートするリソースの名前です。 これは、[Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) によって "Name" として返されるフレンドリ名ではありませんが、リソース スキーマを定義するときに使用されるクラス名です ([Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) によって **ResourceType** として返されます)。

使用しての詳細については`Import-DSCResource`を参照してください[Import-dscresource を使用します。](import-dscresource.md)

## <a name="powershell-v4-and-v5-differences"></a>PowerShell v4 および v5 の違い

PowerShell 4.0 に格納する必要がある DSC リソースの違いがあります。 詳細については、次を参照してください。[リソースの場所](import-dscresource.md#resource-location)します。

## <a name="see-also"></a>参照

- [Windows PowerShell Desired State Configuration の概要](../overview/overview.md)
- [DSC リソース](../resources/resources.md)
- [ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)
