---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成データの使用
ms.openlocfilehash: f2d25b9ced805fb4c91378ebfe840104eb6ce52a
ms.sourcegitcommit: 91786b03704fbd2d185f674df0bc67faddfb6288
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2018
ms.locfileid: "51619179"
---
# <a name="using-configuration-data-in-dsc"></a>DSC で構成データを使用する

> 適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

組み込みの DSC **ConfigurationData** パラメーターを使用して、構成内で使用可能なデータを定義することができます。
これにより、複数のノードや異なる環境で使用可能な 1 つの構成を作成できます。
たとえば、アプリケーションを開発している場合は、開発環境と運用環境の両方に 1 つの構成を使用し、構成データを使用して各環境のデータを指定することができます。

このトピックでは、**ConfigurationData** ハッシュテーブルの構造について説明します。
構成データの使用方法の例については、「[構成データと環境データの分離](separatingEnvData.md)」をご覧ください。

## <a name="the-configurationdata-common-parameter"></a>共通の ConfigurationData パラメーター

DSC 構成では、**ConfigurationData** という共通パラメーターを使用します。このパラメーターは、構成をコンパイルするときに指定します。
構成をコンパイルする方法の詳細については、「[DSC 構成](configurations.md)」を参照してください。

**ConfigurationData** パラメーターはハッシュテーブルであり、**AllNodes** という名前のキーが少なくとも 1 つ必要です。
その他のキーを 1 つ以上含めることもできます。

> [!NOTE]
> このトピックの例では、(**AllNodes** というキーではなく) `NonNodeData` という追加のキーを 1 つしか使用していませんが、追加するキーの数に制限はなく、名前も自由に付けることができます。

```powershell
$MyData =
@{
    AllNodes = @()
    NonNodeData = ""
}
```

**AllNodes** キーの値は配列です。 この配列の各要素もハッシュ テーブルであり、**NodeName** という名前のキーが少なくとも 1 つ必要です。

```powershell
$MyData =
@{
    AllNodes =
    @(
        @{
            NodeName = "VM-1"
        },


        @{
            NodeName = "VM-2"
        },


        @{
            NodeName = "VM-3"
        }
    );

    NonNodeData = ""
}
```

各ハッシュテーブルには他のキーを追加することもできます。

```powershell
$MyData =
@{
    AllNodes =
    @(
        @{
            NodeName = "VM-1"
            Role     = "WebServer"
        },


        @{
            NodeName = "VM-2"
            Role     = "SQLServer"
        },


        @{
            NodeName = "VM-3"
            Role     = "WebServer"
        }
    );

    NonNodeData = ""
}
```

すべてのノードにプロパティを適用するには、**AllNodes** 配列に **NodeName** が `*` のメンバーを作成します。
たとえば、すべてのノードに `LogPath` プロパティを適用するには、次のように入力します。

```powershell
$MyData =
@{
    AllNodes =
    @(
        @{
            NodeName     = "*"
            LogPath      = "C:\Logs"
        },


        @{
            NodeName     = "VM-1"
            Role         = "WebServer"
            SiteContents = "C:\Site1"
            SiteName     = "Website1"
        },


        @{
            NodeName     = "VM-2"
            Role         = "SQLServer"
        },


        @{
            NodeName     = "VM-3"
            Role         = "WebServer"
            SiteContents = "C:\Site2"
            SiteName     = "Website3"
        }
    );
}
```

これは、名前が `LogPath` で `"C:\Logs"` の値を持つプロパティを、その他のブロック (`VM-1`、`VM-2`、および `VM-3`) にそれぞれ追加するのと同じことです。

## <a name="defining-the-configurationdata-hashtable"></a>ConfigurationData ハッシュテーブルの定義

**ConfigurationData** は、(これまでの例のように) 構成として同じスクリプト ファイル内に変数として定義するか、または別個の `.psd1` ファイル内に定義することができます。
**ConfigurationData** を `.psd1` ファイル内で定義するには、構成データを表すハッシュテーブルのみが含まれるファイルを作成します。

たとえば、次の内容を含む `MyData.psd1` という名前のファイルを作成します。

```powershell
@{
    AllNodes =
    @(
        @{
            NodeName    = 'VM-1'
            FeatureName = 'Web-Server'
        },

        @{
            NodeName    = 'VM-2'
            FeatureName = 'Hyper-V'
        }
    )
}
```

## <a name="compiling-a-configuration-with-configuration-data"></a>構成データで構成をコンパイルする

構成データを定義した構成をコンパイルするには、**ConfigurationData** パラメーターの値として構成データを渡します。

これにより、**AllNodes** 配列の各エントリで MOF ファイルが作成されます。
各 MOF ファイルの名前には、対応する配列エントリの `NodeName` プロパティが使用されます。

たとえば、上記 `MyData.psd1` ファイルのように構成データを定義する場合、構成をコンパイルすると `VM-1.mof` ファイルと `VM-2.mof` ファイルの両方が作成されます。

### <a name="compiling-a-configuration-with-configuration-data-using-a-variable"></a>変数を用いた構成データで構成をコンパイルする

構成として同じ `.ps1` ファイル内の変数として定義された構成データを使用するには、構成をコンパイルするときに、**ConfigurationData** パラメーターの値として変数名を渡します。

```powershell
MyDscConfiguration -ConfigurationData $MyData
```

### <a name="compiling-a-configuration-with-configuration-data-using-a-data-file"></a>データ ファイルを用いた構成データで構成をコンパイルする

.psd1 ファイルに定義された構成データを使用するには、構成のコンパイル時に、そのファイルのパスと名前を **ConfigurationData** パラメーターの値として渡します。

```powershell
MyDscConfiguration -ConfigurationData .\MyData.psd1
```

## <a name="using-configurationdata-variables-in-a-configuration"></a>構成での ConfigurationData 変数の使用

DSC 構成スクリプトで使用できる次の特殊な変数を提供します。

- **$AllNodes** は、**ConfigurationData** で定義されたノードのコレクション全体を参照します。 **.Where()** と **.ForEach()** を使用すると、**AllNodes** コレクションをフィルター処理できます。
- **ConfigurationData** は、構成のコンパイル時にパラメーターとして渡されるハッシュ テーブル全体を参照します。
- **MyTypeName**が含まれています、[構成](configurations.md)名前で、変数を使用します。 たとえば、構成で`MyDscConfiguration`、`$MyTypeName`の値になります`MyDscConfiguration`します。
- **Node** は、**.Where()** または **.ForEach()** を使用してフィルター処理された後の **AllNodes** コレクション内にある特定のエントリを参照します。
  - これらのメソッドの詳細については、「[about_arrays](/powershell/reference/3.0/Microsoft.PowerShell.Core/About/about_Arrays.md)」を参照してください。

## <a name="using-non-node-data"></a>ノード外のデータを使用する

上記の例でわかるように、**ConfigurationData** ハッシュテーブルには、必須の **AllNodes** キーだけでなく、複数のキーを含めることができます。
このトピックの例では、追加ノードを 1 つだけ使用し、`NonNodeData` という名前を付けました。
実際は、定義できる追加のキーの数に制限はなく、名前も自由に設定できます。

ノード以外のデータを使用する例は、「[構成データと環境データの分離](separatingEnvData.md)」をご覧ください。

## <a name="see-also"></a>参照

- [構成データでの資格情報オプション](configDataCredentials.md)
- [DSC 構成](configurations.md)