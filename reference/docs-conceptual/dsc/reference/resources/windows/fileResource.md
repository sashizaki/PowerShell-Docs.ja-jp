---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC ファイル リソース
ms.openlocfilehash: 54f4de9b3d337a6b9ad36c143eac70d5ef6b1c15
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560476"
---
# <a name="dsc-file-resource"></a>DSC ファイル リソース

> 適用先:Windows PowerShell 4.0、Windows PowerShell 5.x

Windows PowerShell Desired State Configuration (DSC) の **File** リソースは、ターゲット ノード上でファイルとフォルダーを管理するためのメカニズムを備えています。 **DestinationPath** と **SourcePath** は両方ともターゲット ノードからアクセスできる必要があります。

## <a name="syntax"></a>構文

```Syntax
File [string] #ResourceName
{
    DestinationPath = [string]
    [ Attributes = [string[]] { Archive | Hidden | ReadOnly | System }]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Contents = [string] ]
    [ Credential = [PSCredential] ]
    [ Force = [bool] ]
    [ Recurse = [bool] ]
    [ SourcePath = [string] ]
    [ Type = [string] { Directory | File } ]
    [ MatchSource = [bool] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Properties

|プロパティ |説明 |
|---|---|
|DestinationPath |**Ensure** で **Present** または **Absent** であることを保証するターゲット ノード上の場所。 |
|属性 |対象となるファイルまたはディレクトリの属性の望ましい状態。 有効な値は、_Archive_、_Hidden_、_ReadOnly_、_System_ です。 |
|Checksum |2 つのファイルが同じであるかどうかを決定するときに使用するチェックサム タイプ。 有効な値は、次のとおりです。**SHA-1**、**SHA-256**、**SHA-512**、**createdDate**、**modifiedDate**。 |
|内容 |**File** **型**に使用した場合にのみ有効です。 **Ensure** (保証) するコンテンツがターゲット ファイルで **Present** または **Absent** であることを示します。 |
|資格情報 |ソース ファイルなどのリソースにアクセスするために必要な資格情報。 |
|Force |結果としてエラーになるアクセス操作 (ファイルの上書き、空でないディレクトリの削除など) をオーバーライドします。 既定値は `$false` です。 |
|Recurse |**Directory** **型**に使用した場合にのみ有効です。 すべてのサブディレクトリに対して状態操作を再帰的に実行します。 既定値は `$false` です。 |
|SourcePath |ファイルまたはフォルダー リソースのコピー元のパス。 |
|Type |構成されるリソースの種類。 有効な値は **Directory** と **File** です。 既定値は **File** です。 |
|MatchSource |最初のコピー後にソース ディレクトリに追加された新しいファイルをリソースで監視するかどうかを決定します。 `$true` の値は、最初のコピー後、すべての新しいソース ファイルが指定した場所にコピーされることを示します。 `$false` に設定した場合、リソースではソース ディレクトリの内容がキャッシュされ、最初のコピー後に追加されたファイルはすべて無視されます。 既定値は `$false` です。 |

> [!WARNING]
> **Credential** または **PSRunAsCredential** の値を指定しない場合、リソースはターゲット ノードのコンピューター アカウントを使用して **SourcePath** にアクセスします。 **SourcePath** が UNC 共有の場合、"アクセスが拒否されました" エラーが発生する可能性があります。 アクセス許可が適切に設定されていることを保証するか、**Credential** または **PSRunAsCredential** プロパティを使用して、使用するアカウントを指定します。

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|Ensure |**Destination** にファイルと **Contents** が存在するか、しないかを判断します。 ファイルが存在することを保証するには、このプロパティを **Present** に設定します。 コンテンツが存在しないことを保証するには、**Absent** に設定します。 既定値は **Present** です。 |
|PsDscRunAsCredential |リソース全体を実行するための資格情報を設定します。 |

> [!NOTE]
> **PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。 詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。

### <a name="additional-information"></a>関連情報

- **DestinationPath** のみを指定した場合、リソースではパスが存在すること (**Present**) または存在しないこと (**Absent**) が保証されます。
- **Type** の値が **Directory** の **SourcePath** と **DestinationPath** を指定すると、リソースではソース ディレクトリがコピー先のパスにコピーされます。 プロパティ **Recurse**、**Force**、**MatchSource** で実行されるコピー操作の種類が変更され、**Credential** ではソース ディレクトリへのアクセスに使用するアカウントが決まります。
- **Attributes** プロパティの **ReadOnly** 値を **DestinationPath** と共に指定した場合、**Ensure** **Present** で指定のパスが作成され、**Contents** でファイルのコンテンツが設定されます。 **Ensure** **Absent** 設定で **Attributes** プロパティ全体が無視され、指定のパスで任意のファイルが削除されます。

## <a name="example"></a>例

次の例では、ファイル リソースを使用して、ディレクトリとそのサブディレクトリをプル サーバーからターゲット ノードにコピーします。 操作が成功すると、Log リソースで確認メッセージがイベント ログに書き込まれます。

ソース ディレクトリは、プル サーバーから共有されている UNC パス (`\\PullServer\DemoSource`) です。 **Recurse** プロパティを使用すると、すべてのサブディレクトリも確実にコピーされます。

> [!IMPORTANT]
> ターゲット ノード上の LCM は、既定でローカル システム アカウントのコンテキストで実行されます。 **SourcePath** へのアクセスを許可するには、ターゲット ノードのコンピューター アカウントに適切なアクセス許可を付与します。 **Credential** と **PSDSCRunAsCredential** のいずれでも、LCM が **SourcePath** にアクセスするために使用するコンテキストが変更されます。 それでも **SourcePath** へのアクセスに使用されるアカウントへのアクセスを許可する必要があります。

```powershell
Configuration FileResourceDemo
{
    Node "localhost"
    {
        File DirectoryCopy
        {
            Ensure = "Present" # Ensure the directory is Present on the target node.
            Type = "Directory" # The default is File.
            Recurse = $true # Recursively copy all subdirectories.
            SourcePath = "\\PullServer\DemoSource"
            DestinationPath = "C:\Users\Public\Documents\DSCDemo\DemoDestination"
        }

        Log AfterDirectoryCopy
        {
            # The message below gets written to the Microsoft-Windows-Desired State Configuration/Analytic log
            Message = "Finished running the file resource with ID DirectoryCopy"
            DependsOn = "[File]DirectoryCopy" # Depends on successful execution of the File resource.
        }
    }
}
```

DSC で**資格情報**を使用する方法の詳細については、[実行ユーザー](../../../configurations/runAsUser.md)または[データの資格情報の構成](../../../configurations/configDataCredentials.md)に関する記事を参照してください。
