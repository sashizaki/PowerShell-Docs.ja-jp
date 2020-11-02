---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC 構成
description: DSC 構成は、特殊な関数を定義する PowerShell スクリプトです。
ms.openlocfilehash: e59ad2791055ee3ff0150c342ec621d0228c4fc1
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658560"
---
# <a name="dsc-configurations"></a>DSC 構成

> 適用先:Windows PowerShell 4.0、Windows PowerShell 5.0

DSC 構成は、特殊な関数を定義する PowerShell スクリプトです。 構成を定義するには、PowerShell キーワード **Configuration** を使用します。

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

スクリプトを `.ps1` ファイルとして保存します。

## <a name="configuration-syntax"></a>構成構文

構成スクリプトは次の部分で構成されます。

- **Configuration** ブロック。 これは、最も外側にあるスクリプト ブロックです。 このブロックを定義するには、 **Configuration** キーワードを使用し、名前を指定します。 この場合、構成の名前は "MyDscConfiguration" です。
- 1 つまたは複数の **Node** ブロック。 これらは、構成するノード (コンピューターまたは VM) を定義します。
  上記の構成には、"TEST-PC1" という名前のコンピューターを対象とする 1 つの **Node** ブロックがあります。
  Node ブロックは、複数のコンピューター名を受け入れることができます。
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

また、 **Node** ブロックは複数のコンピューター名を受け入れることができます。 上の例では、`-ComputerName` パラメーターを使うか、またはコンピューターのコンマ区切りリストを **Node** ブロックに直接渡すことができます。

```powershell
MyDscConfiguration -ComputerName "localhost", "Server01"
```

構成内から **Node** ブロックに対してコンピューターのリストを指定するときは、配列表記を使う必要があります。

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

構成を適用する前に、MOF ドキュメントにコンパイルする必要があります。 そのためには、PowerShell 関数の場合と同じように構成を呼び出します。 例の最後の行には構成を呼び出すための構成の名前のみが含まれています。

> [!NOTE]
> 構成を呼び出すには、(他の PowerShell 関数と同様に) 関数がグローバル スコープ内にある必要があります。 そのためには、スクリプトで "ドット ソース" を行うか、F5 キーを使用するか、または ISE で **[スクリプトの実行]** をクリックして、構成スクリプトを実行します。 スクリプトでドット ソースを行うには、構成を含むスクリプト ファイルの名前が `myConfig.ps1` である場合、`. .\myConfig.ps1` でコマンドを実行します。

構成を呼び出すと、結果は次のようになります。

- すべての変数が解決されます
- 構成と同じ名前のフォルダーが現在のディレクトリ内に作成されます。
- _NodeName_ .mof という名前のファイルが新しいディレクトリ内に作成されます。 _NodeName_ は、構成のターゲット ノードの名前です。 複数のノードがある場合は、ノードごとに MOF ファイルが作成されます。

> [!NOTE]
> MOF ファイルには、ターゲット ノードのすべての構成情報が含まれています。 このため、このファイルをセキュリティ保護することが重要です。 詳細については、「[MOF ファイルのセキュリティ保護](../pull-server/secureMOF.md)」を参照してください。

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

前の例を実行した場合、リソースを明示的にインポートしないで使用することについて警告されることがあります。 今日、DSC には PSDesiredStateConfiguration モジュールの一部として 12 のリソースが付属しています。

コマンドレット [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) を使用して、どのリソースがシステムにインストールされ、LCM で使用できるかを決定できます。
これらのモジュールが `$env:PSModulePath` に配置され、[Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) によって正しく認識された後、構成内に読み込む必要があります。

**Import-DscResource** は、 **Configuration** ブロック内でのみ認識される動的なキーワードであり、コマンドレットではありません。 **Import-DscResource** は、次の 2 つのパラメーターをサポートしています。

- **ModuleName** は、 **Import-DscResource** を使用する場合に推奨される方法です。 これは、インポートするリソースを含むモジュールの名前 (およびモジュール名の文字列配列) を受け取ります。
- **Name** は、インポートするリソースの名前です。 これは、 [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) によって "Name" として返されるフレンドリ名ではありませんが、リソース スキーマを定義するときに使用されるクラス名です ( [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) によって **ResourceType** として返されます)。

`Import-DSCResource` の使用について詳しくは、「[Import-DSCResource の使用](import-dscresource.md)」をご覧ください

## <a name="powershell-v4-and-v5-differences"></a>PowerShell の v4 と v5 の違い

PowerShell 4.0 では DSC リソースを格納する必要がある場所が違います。 詳しくは、「[リソースの場所](import-dscresource.md#resource-location)」をご覧ください。

## <a name="see-also"></a>参照

- [Windows PowerShell Desired State Configuration の概要](../overview/overview.md)
- [DSC リソース](../resources/resources.md)
- [ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)
