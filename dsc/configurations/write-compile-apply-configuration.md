---
ms.date: 12/12/2018
keywords: dsc, powershell, 構成、サービス, セットアップ
title: 構成の作成、コンパイル、適用
ms.openlocfilehash: fa4d98fd12202439ba7025fd8af3fa398653ca05
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402349"
---
> 適用先:Windows PowerShell 4.0、Windows PowerShell 5.0

# <a name="write-compile-and-apply-a-configuration"></a>構成の作成、コンパイル、適用

この演習では、Desired State Configuration (DSC) の構成の作成と適用について最初から最後まで説明します。
次の例では、書き込みし、非常に単純な構成を適用する方法を学びます。 構成が"HelloWorld.txt"ファイルがローカル コンピューターに存在することを確認します。 ファイルを削除する場合は、DSC ことに、次回の更新は再作成します。

DSC とそのしくみの概要については、次を参照してください。 [Desired State Configuration の概要開発者向け](../overview/overview.md)します。

## <a name="requirements"></a>要件

この例を実行するには、PowerShell 4.0 またはそれ以降を実行しているコンピューターが必要です。

## <a name="write-the-configuration"></a>構成を記述する

DSC [構成](configurations.md)は、1 つ以上のターゲット コンピューター (ノード) を構成する方法を定義する特別な PowerShell 関数です。

PowerShell ISE で、またはその他の PowerShell エディターで、次のように入力します。

```powershell
Configuration HelloWorld {

    # Import the module that contains the File resource.
    Import-DscResource -ModuleName PsDesiredStateConfiguration

    # The Node statement specifies which targets to compile MOF files for, when this configuration is executed.
    Node 'localhost' {

        # The File resource can ensure the state of files, or copy them from a source to a destination with persistent updates.
        File HelloWorld {
            DestinationPath = "C:\Temp\HelloWorld.txt"
            Ensure = "Present"
            Contents   = "Hello World from DSC!"
        }
    }
}
```

"HelloWorld.ps1"として保存します。

関数を定義するようには、構成の定義です。 `localhost` 場合、**ノード**ブロックは構成するターゲット ノードを指定します。

構成では、1 つを呼び出す[リソース](../resources/resources.md)、`File`リソース。 リソースは、ターゲット ノードが構成によって定義された状態になっているか確認します。

## <a name="compile-the-configuration"></a>構成をコンパイルする

DSC 構成をノードに適用するには、最初にコンパイルを行い、MOF ファイルを出力する必要があります。
によって定義されたすべてのノードの 1 つの".mof"ファイルをコンパイルは、関数のように、構成を実行している、`Node`ブロックします。
構成を実行するのには、する必要があります*ドット ソース*現在のスコープに"HelloWorld.ps1"スクリプト。
詳細については、次を参照してください。 [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-6#script-scope-and-dot-sourcing)します。

*ドット ソース*"HelloWorld.ps1"スクリプトの後のそれを格納場所のパスを入力して、 `. ` (ドット、領域)。 次に、可能性があります関数のように呼び出して、構成を実行します。

```powershell
. C:\Scripts\WebsiteTest.ps1
HelloWolrd
```

これにより、次の出力が生成されます。

```output
Directory: C:\Scripts\HelloWorld


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

## <a name="apply-the-configuration"></a>構成を適用する

コンパイル済みの MOF があるため、[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットを呼び出すことで、ターゲット ノード (今回の場合はローカル コンピューター) に構成を適用できます。

`Start-DscConfiguration`コマンドレットの指示、[ローカル構成マネージャー (LCM)](../managing-nodes/metaConfig.md)構成を適用する、DSC のエンジンです。
LCM はDSC リソースを呼び出し、構成を適用します。

次のコードを使用して実行する、`Start-DSCConfiguration`コマンドレット。 "Localhost.mof"を格納する場所のディレクトリ パスを指定、`-Path`パラメーター。 `Start-DSCConfiguration`コマンドレットは、いずれかに指定されたディレクトリを検索"\<computername\>.mof"ファイル。 `Start-DSCConfiguration`コマンドレットはファイル名 ("localhost"、"server01"、「dc 02」など) で指定されたコンピューター名に見つけた各".mof"ファイルを適用しようとしています。

> [!NOTE]
> 場合、`-Wait`パラメーターが指定されていない`Start-DSCConfiguration`操作を実行するバック グラウンド ジョブを作成します。 指定する、`-Verbose`パラメーターを使用すると、ウォッチ、 **Verbose**が操作の出力。 `-Wait`、および`-Verbose`は両方の省略可能なパラメーターです。

```powershell
Start-DscConfiguration -Path C:\Scripts\HelloWorld -Verbose -Wait
```

## <a name="test-the-configuration"></a>構成をテストする

1 回、`Start-DSCConfiguration`コマンドレットが完了したら、指定した場所にある"HelloWorld.txt"ファイルが表示されます。 内容を確認することができます、 [Get-content](/powershell/module/microsoft.powershell.management/get-content)コマンドレット。

できます*テスト*を使用して現在の状態[Test-dscconfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)します。

出力は、ノードが現在適用されている構成で準拠している場合は、"True"にすることがあります。

```powershell
Test-DSCConfiguration
```

```output
True
```

```powershell
Get-Content -Path C:\Temp\HelloWorld.txt
```

```output
Hello World from DSC!
```

## <a name="re-applying-the-configuration"></a>構成を再適用します。

もう一度適用される構成を表示するには、構成で作成されたテキスト ファイルを削除できます。 使用して、`Start-DSCConfiguration`コマンドレットと、`-UseExisting`パラメーター。 `-UseExisting`パラメーター `Start-DSCConfiguration` "current.mof"ファイルを再適用するを表す最も最近正常に構成を適用します。

```powershell
Remove-Item -Path C:\Temp\HelloWorld.txt
```

## <a name="next-steps"></a>次の手順

- 「[DSC 構成](configurations.md)」で DSC 構成の詳細を確認する。
- 「[DSC リソース](../resources/resources.md)」で利用可能な DSC リソースとカスタム DSC リソースの作成方法を確認する。
- 「[PowerShell ギャラリー](https://www.powershellgallery.com/)」で DSC の構成とリソースを検索する。
